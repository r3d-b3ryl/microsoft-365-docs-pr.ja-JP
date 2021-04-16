---
title: Chef を使用して Linux で Defender for Endpoint を展開する方法
description: Defender for Endpoint を Linux で Chef で展開する方法について説明します。
keywords: microsoft、Defender、atp、Linux、スキャン、ウイルス対策、エンドポイント用 microsoft Defender (Linux)
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 362222e4737b1a8dd6b8a0a284bf3bfb1903c288
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861452"
---
# <a name="deploy-defender-for-endpoint-on-linux-with-chef"></a>Defender for Endpoint on Linux with Chef の展開

開始する前に:

- まだインストールされていない場合は、unzip をインストールします。 Chef コンポーネントは既にインストールされ、Chef リポジトリ (chef generate repo) が存在し、Defender for Endpoint on Chef マネージ Linux サーバーへの展開に使用されるクックブックを格納 <reponame> します。

既存のリポジトリに新しいクックブックを作成するには、シェフ リポジトリにあるクックブック フォルダー内から次のコマンドを実行します。</br>
`chef generate cookbook mdatp`

このコマンドは、mdatp という新しいクックブックの新しいフォルダー構造を作成します。  MDE 展開の追加に使用するクックブックが既にある場合は、既存のクックブックを使用できます。
クックブックを作成したら、作成しっきり作成したクックブック フォルダー内に files フォルダーを作成します。

`mkdir mdatp/files`

Microsoft Defender Security Center ポータルからダウンロードできる Linux Server Onboarding zip ファイルを、この新しいファイル フォルダーに転送します。

Chef ワークステーションで、mdatp/recipes フォルダーに移動します。 このフォルダーは、クックブックが生成された時点で作成されます。 優先するテキスト エディター (vi や nano など) を使用して、default.rb ファイルの末尾に次の手順を追加します。
-   include_recipe '::onboard_mdatp'
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
   uri                "https://packages.microsoft.com/ubuntu/20.04/prod"
 end
 apt_package "mdatp"
when 'rhel'
 yum_repository 'microsoft-prod' do
   baseurl            "https://packages.microsoft.com/rhel/7/prod/"
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

展開するバージョンと展開するチャネルと一致するバージョン番号、配布名、およびレポ名を変更する必要があります。
次に、mdatp/recipies フォルダーに onboard_mdatp.rb ファイルを作成する必要があります。  そのファイルに次のテキストを追加します。

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

必ず、オンボーディング ファイルの場所にパス名を更新してください。
Chef ワークステーションに展開をテストするには、次のコマンドを実行します ``sudo chef-client -z -o mdatp`` 。
展開後は、Microsoft Defender ATP for Linux 用の Set preferences - Windows セキュリティ ポリシーに基づいて、構成ファイルを作成してサーバーに展開|  [Microsoft Docs](/windows/security/threat-protection/microsoft-defender-atp/linux-preferences).  
構成ファイルを作成してテストしたら、それをクックブック/mdatp/files フォルダーに配置し、オンボーディング パッケージも配置できます。  次に、mdatp/recipies フォルダーに settings_mdatp.rb ファイルを作成し、次のテキストを追加できます。

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

レシピの一部としてこの手順を含めるには、include_recipeフォルダー内settings_mdatp default.rb ファイルに ':: settings_mdatp' を追加します。
crontab を使用して自動更新をスケジュールする [Microsoft Defender for Endpoint (Linux)](linux-update-MDE-Linux.md)の更新プログラムをスケジュールできます。

MDATP クックブックをアンインストールします。

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

