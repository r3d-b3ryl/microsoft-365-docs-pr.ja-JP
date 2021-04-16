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
# <a name="deploy-defender-for-endpoint-on-linux-with-chef"></a><span data-ttu-id="20766-104">Defender for Endpoint on Linux with Chef の展開</span><span class="sxs-lookup"><span data-stu-id="20766-104">Deploy Defender for Endpoint on Linux with Chef</span></span>

<span data-ttu-id="20766-105">開始する前に:</span><span class="sxs-lookup"><span data-stu-id="20766-105">Before you begin:</span></span>

- <span data-ttu-id="20766-106">まだインストールされていない場合は、unzip をインストールします。</span><span class="sxs-lookup"><span data-stu-id="20766-106">Install unzip if it’s not already installed.</span></span> <span data-ttu-id="20766-107">Chef コンポーネントは既にインストールされ、Chef リポジトリ (chef generate repo) が存在し、Defender for Endpoint on Chef マネージ Linux サーバーへの展開に使用されるクックブックを格納 <reponame> します。</span><span class="sxs-lookup"><span data-stu-id="20766-107">The Chef components are already installed and a Chef repository exists (chef generate repo <reponame>) to store the cookbook that will be used to deploy to Defender for Endpoint on Chef managed Linux servers.</span></span>

<span data-ttu-id="20766-108">既存のリポジトリに新しいクックブックを作成するには、シェフ リポジトリにあるクックブック フォルダー内から次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="20766-108">You can create a new cookbook in your existing repository by running the following command from inside the cookbooks folder that is in your chef repository:</span></span></br>
`chef generate cookbook mdatp`

<span data-ttu-id="20766-109">このコマンドは、mdatp という新しいクックブックの新しいフォルダー構造を作成します。</span><span class="sxs-lookup"><span data-stu-id="20766-109">This command will create a new folder structure for the new cookbook called mdatp.</span></span>  <span data-ttu-id="20766-110">MDE 展開の追加に使用するクックブックが既にある場合は、既存のクックブックを使用できます。</span><span class="sxs-lookup"><span data-stu-id="20766-110">You can also use an existing cookbook if you already have one you’d like to use to add the MDE deployment into.</span></span>
<span data-ttu-id="20766-111">クックブックを作成したら、作成しっきり作成したクックブック フォルダー内に files フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="20766-111">After the cookbook is created, create a files folder inside the cookbook folder that just got created:</span></span>

`mkdir mdatp/files`

<span data-ttu-id="20766-112">Microsoft Defender Security Center ポータルからダウンロードできる Linux Server Onboarding zip ファイルを、この新しいファイル フォルダーに転送します。</span><span class="sxs-lookup"><span data-stu-id="20766-112">Transfer the Linux Server Onboarding zip file that can be downloaded from the Microsoft Defender Security Center portal to this new files folder.</span></span>

<span data-ttu-id="20766-113">Chef ワークステーションで、mdatp/recipes フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="20766-113">On the Chef Workstation, navigate to the mdatp/recipes folder.</span></span> <span data-ttu-id="20766-114">このフォルダーは、クックブックが生成された時点で作成されます。</span><span class="sxs-lookup"><span data-stu-id="20766-114">This folder is created when the cookbook was generated.</span></span> <span data-ttu-id="20766-115">優先するテキスト エディター (vi や nano など) を使用して、default.rb ファイルの末尾に次の手順を追加します。</span><span class="sxs-lookup"><span data-stu-id="20766-115">Use your preferred text editor (like vi or nano) to add the following instructions to the end of the default.rb file:</span></span>
-   <span data-ttu-id="20766-116">include_recipe '::onboard_mdatp'</span><span class="sxs-lookup"><span data-stu-id="20766-116">include_recipe '::onboard_mdatp'</span></span>
- <span data-ttu-id="20766-117">include_recipe '::install_mdatp'</span><span class="sxs-lookup"><span data-stu-id="20766-117">include_recipe '::install_mdatp'</span></span>

<span data-ttu-id="20766-118">次に、default.rb ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="20766-118">Then save and close the default.rb file.</span></span>
<span data-ttu-id="20766-119">次に、レシピ フォルダーに install_mdatp.rb という名前の新しいレシピ ファイルを作成し、このテキストをファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="20766-119">Next create a new recipe file named install_mdatp.rb in the recipes folder and add this text to the file:</span></span>

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

<span data-ttu-id="20766-120">展開するバージョンと展開するチャネルと一致するバージョン番号、配布名、およびレポ名を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20766-120">You’ll need to modify the version number, distribution, and repo name to match the version you’re deploying to and the channel you’d like to deploy.</span></span>
<span data-ttu-id="20766-121">次に、mdatp/recipies フォルダーに onboard_mdatp.rb ファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20766-121">Next you should create an onboard_mdatp.rb file in the mdatp/recipies folder.</span></span>  <span data-ttu-id="20766-122">そのファイルに次のテキストを追加します。</span><span class="sxs-lookup"><span data-stu-id="20766-122">Add the following text to that file:</span></span>

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

<span data-ttu-id="20766-123">必ず、オンボーディング ファイルの場所にパス名を更新してください。</span><span class="sxs-lookup"><span data-stu-id="20766-123">Make sure to update the path name to the location of the onboarding file.</span></span>
<span data-ttu-id="20766-124">Chef ワークステーションに展開をテストするには、次のコマンドを実行します ``sudo chef-client -z -o mdatp`` 。</span><span class="sxs-lookup"><span data-stu-id="20766-124">To test deploy it on the Chef workstation, just run ``sudo chef-client -z -o mdatp``.</span></span>
<span data-ttu-id="20766-125">展開後は、Microsoft Defender ATP for Linux 用の Set preferences - Windows セキュリティ ポリシーに基づいて、構成ファイルを作成してサーバーに展開|  [Microsoft Docs](/windows/security/threat-protection/microsoft-defender-atp/linux-preferences).</span><span class="sxs-lookup"><span data-stu-id="20766-125">After your deployment you should consider creating and deploying a configuration file to the servers based on  [Set preferences for Microsoft Defender ATP for Linux - Windows security | Microsoft Docs](/windows/security/threat-protection/microsoft-defender-atp/linux-preferences).</span></span>  
<span data-ttu-id="20766-126">構成ファイルを作成してテストしたら、それをクックブック/mdatp/files フォルダーに配置し、オンボーディング パッケージも配置できます。</span><span class="sxs-lookup"><span data-stu-id="20766-126">After you've created and tested your configuration file, you can place it into the cookbook/mdatp/files folder where you also placed the onboarding package.</span></span>  <span data-ttu-id="20766-127">次に、mdatp/recipies フォルダーに settings_mdatp.rb ファイルを作成し、次のテキストを追加できます。</span><span class="sxs-lookup"><span data-stu-id="20766-127">Then you can create a settings_mdatp.rb file in the mdatp/recipies folder and add this text:</span></span>

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

<span data-ttu-id="20766-128">レシピの一部としてこの手順を含めるには、include_recipeフォルダー内settings_mdatp default.rb ファイルに ':: settings_mdatp' を追加します。</span><span class="sxs-lookup"><span data-stu-id="20766-128">To include this step as part of the recipe just add include_recipe ':: settings_mdatp' to your default.rb file within the recipe folder.</span></span>
<span data-ttu-id="20766-129">crontab を使用して自動更新をスケジュールする [Microsoft Defender for Endpoint (Linux)](linux-update-MDE-Linux.md)の更新プログラムをスケジュールできます。</span><span class="sxs-lookup"><span data-stu-id="20766-129">You can also use crontab to schedule automatic updates [Schedule an update of the Microsoft Defender for Endpoint (Linux)](linux-update-MDE-Linux.md).</span></span>

<span data-ttu-id="20766-130">MDATP クックブックをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="20766-130">Uninstall MDATP cookbook:</span></span>

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

