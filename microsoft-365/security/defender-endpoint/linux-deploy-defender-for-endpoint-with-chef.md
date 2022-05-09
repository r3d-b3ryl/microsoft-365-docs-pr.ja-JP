---
title: Chef を使用して Linux に Defender for Endpoint をデプロイする方法
description: Chef を使用して Linux 上に Defender for Endpoint をデプロイする方法について説明します
keywords: microsoft, defender, atp, Linux, スキャン, ウイルス対策, Microsoft Defender for endpoint (Linux)
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: lovina-saldanha
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 799fc4d163b120b4197b6cd044efe4740e4a3cc7
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2022
ms.locfileid: "61941926"
---
# <a name="deploy-defender-for-endpoint-on-linux-with-chef"></a>Chef を使用して Linux 用 Microsoft Defender for Endpoint を展開する

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

作業を開始する前に:まだインストールされていない場合は、解凍してインストールします。

Chef コンポーネントは既にインストールされており、Chef リポジトリが存在し (chef generate repo \<reponame\>)、Chef マネージド Linux サーバー上の Defender for Endpoint へのデプロイに使用されるクックブックを格納します。

既存のリポジトリに新しいクックブックを作成するには、chef リポジトリにある cookbooks フォルダー内から次のコマンドを実行します。

```bash
chef generate cookbook mdatp
```

このコマンドは、mdatp という名前の新しいクックブックの新しいフォルダー構造を作成します。 MDE デプロイの追加に使用するクックブックが既にある場合は、既存のクックブックを使用することもできます。
クックブックが作成されたら、作成したばかりのクックブック フォルダー内にファイル フォルダーを作成します。

```bash
mkdir mdatp/files
```

Microsoft 365 Defender ポータルからダウンロードできる Linux Server オンボード zip ファイルをこの新しいファイル フォルダーに転送します。

Chef ワークステーションで、mdatp/recipes フォルダーに移動します。 このフォルダーは、クックブックが生成されたときに作成されます。 任意のテキスト エディター (vi や nano など) を使用して、default.rb ファイルの末尾に次の手順を追加します。

- include_recipe '::onboard_mdatp'
- include_recipe '::install_mdatp'

次に、default.rb ファイルを保存して閉じます。

次に、レシピ フォルダーに install_mdatp.rb という名前の新しいレシピ ファイルを作成し、このテキストをファイルに追加します。

```powershell
#Add Microsoft Defender
Repo
case node['platform_family']
when 'debian'
 apt_repository 'MDAPRepo' do
   arch               'amd64'
   cache_rebuild      true
   cookbook           false
   deb_src            false
   key                'BC528686B50D79E339D3721CEB3E94ADBE1229CF'
   keyserver          "keyserver.ubuntu.com"
   distribution       'focal'
   repo_name          'microsoft-prod'
   components         ['main']
   trusted            true
   uri                "https://packages.microsoft.com/config/ubuntu/20.04/prod"
 end
 apt_package "mdatp"
when 'rhel'
 yum_repository 'microsoft-prod' do
   baseurl            "https://packages.microsoft.com/config/rhel/7/prod/"
   description        "Microsoft Defender for Endpoint"
   enabled            true
   gpgcheck           true
   gpgkey             "https://packages.microsoft.com/keys/microsoft.asc"
 end
 if node['platform_version'] <= 8 then
    yum_package "mdatp"
 else
    dnf_package "mdatp"
 end
end
```

デプロイ先のバージョンとデプロイするチャネルと一致するように、バージョン番号、ディストリビューション、リポジトリ名を変更する必要があります。
次に、mdatp/recipies フォルダーに onboard_mdatp.rb ファイルを作成する必要があります。 そのファイルに次のテキストを追加します。

```powershell
#Create MDATP Directory
mdatp = "/etc/opt/microsoft/mdatp"
zip_path = "/path/to/chef-repo/cookbooks/mdatp/files/WindowsDefenderATPOnboardingPackage.zip"

directory "#{mdatp}" do
  owner 'root'
  group 'root'
  mode 0755
  recursive true
end

#Extract WindowsDefenderATPOnbaordingPackage.zip into /etc/opt/microsoft/mdatp

bash 'Extract Onbaording Json MDATP' do
  code <<-EOS
  unzip #{zip_path} -d #{mdatp}
  EOS
  not_if { ::File.exist?('/etc/opt/microsoft/mdatp/mdatp_onboard.json') }
end
```

必ず、パス名をオンボード ファイルの場所に更新してください。
Chef ワークステーションにデプロイをテストするには、実行するだけです ``sudo chef-client -z -o mdatp``。
デプロイ後は、[Linux でのMicrosoft Defender for Endpointの設定の設定](/linux-preferences.md)に基づいて、構成ファイルを作成してサーバーにデプロイすることを検討する必要があります。
構成ファイルを作成してテストしたら、それを cookbook/mdatp/files フォルダーに配置し、オンボード パッケージも配置できます。 次に、mdatp/recipies フォルダーに settings_mdatp.rb ファイルを作成し、次のテキストを追加できます。

```powershell
#Copy the configuration file
cookbook_file '/etc/opt/microsoft/mdatp/managed/mdatp_managed.json' do
  source 'mdatp_managed.json'
  owner 'root'
  group 'root'
  mode '0755'
  action :create
end
```

この手順をレシピの一部として含めるには、レシピ フォルダー内の default.rb ファイルに ':: settings_mdatp' include_recipe追加するだけです。
crontab を使用して自動更新をスケジュールすることもできます[。Microsoft Defender for Endpoint (Linux) の更新をスケジュール](linux-update-MDE-Linux.md)することもできます。

MDATP のクックブックをアンインストールします。

```powershell
#Uninstall the Defender package
case node['platform_family']
when 'debian'
 apt_package "mdatp" do
   action :remove
 end
when 'rhel'
 if node['platform_version'] <= 8
then
    yum_package "mdatp" do
      action :remove
    end
 else
    dnf_package "mdatp" do
      action :remove
    end
 end
end
```
