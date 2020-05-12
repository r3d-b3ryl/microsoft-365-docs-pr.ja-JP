---
title: 開発/テスト環境でセキュリティの分離を使用してチームを構成する
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- M365solutions
ms.custom: ''
description: 従業員がいつでもどこからでもリモートで作業できるようにするセキュリティとインフラストラクチャを構成します。
ms.openlocfilehash: 5c2de3fbb174bdf1dccc8ef8371dca1ae1bfddf0
ms.sourcegitcommit: 9c828bc27cd73a1bb85e9fe38d818190025ebb3f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "44159397"
---
# <a name="configure-a-team-with-security-isolation-in-a-devtest-environment"></a><span data-ttu-id="96d5f-103">開発/テスト環境でセキュリティの分離を使用してチームを構成する</span><span class="sxs-lookup"><span data-stu-id="96d5f-103">Configure a team with security isolation in a dev/test environment</span></span>

<span data-ttu-id="96d5f-104">この記事では、開発/テスト環境で[セキュリティを分離したチーム](secure-teams-security-isolation.md)を作るための詳細な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="96d5f-104">This article provides step-by-step instructions to create a [team with security isolation](secure-teams-security-isolation.md) in a dev/test environment.</span></span>

![会社戦略の分離チームの構成](../media/team-security-isolation-dev-test/team-security-isolation-dev-test-config.png)

<span data-ttu-id="96d5f-106">こうしたチームを運用環境に展開する前に、この開発/テスト環境を使用して、特定のニーズに合わせて設定を検証し、微調整します。</span><span class="sxs-lookup"><span data-stu-id="96d5f-106">Use this dev/test environment to experiment and fine-tune settings for your specific needs before deploying this type of team in production.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="96d5f-107">フェーズ 1: Microsoft 365 Enterprise のテスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="96d5f-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="96d5f-108">最小要件で機密チームと高機密チームを簡易な方法でテストする場合は、「[軽量な基本構成](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="96d5f-108">If you just want to test sensitive and highly sensitive teams in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).</span></span>

<span data-ttu-id="96d5f-109">シミュレーションのエンタープライズで機密チームと高機密チームをテストするには、「[パスワード ハッシュの同期](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="96d5f-109">If you want to test sensitive and highly sensitive teams in a simulated enterprise, follow the instructions in [Password hash synchronization](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment).</span></span>

>[!Note]
><span data-ttu-id="96d5f-110">セキュリティ分離を使用してチームをテストする場合、シミュレーションのエンタープライズ テスト環境は必要ありません。シミュレーションのエンタープライズ テスト環境には、インターネットに接続されたシミュレーションのイントラネット、Active Directory Domain Services (AD DS) フォレスト用のディレクトリ同期が含まれています。</span><span class="sxs-lookup"><span data-stu-id="96d5f-110">Testing an team with security isolation does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="96d5f-111">この機能は、セキュリティ分離を使用してチームをテストし、一般的な組織と類似した環境で試していただけるようオプションとしてここで提供されています。</span><span class="sxs-lookup"><span data-stu-id="96d5f-111">It is provided here as an option so that you can test a team with security isolation and experiment with it in an environment that represents a typical organization.</span></span>
>
    
## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-group-and-users"></a><span data-ttu-id="96d5f-112">フェーズ 2: Azure Active Directory (AD) グループとユーザーを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="96d5f-112">Phase 2: Create and configure your Azure Active Directory (AD) group and users</span></span>

<span data-ttu-id="96d5f-113">このフェーズでは、架空の組織用の Azure AD のグループとユーザーを作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="96d5f-113">In this phase, you create and configure an Azure AD group and users for your fictional organization.</span></span>
  
<span data-ttu-id="96d5f-114">まず、Azure ポータルでセキュリティ グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="96d5f-114">First, create a security group with the Azure portal.</span></span>
  
1. <span data-ttu-id="96d5f-115">ブラウザーで新しいタブを開き、Azure portal ([https://portal.azure.com](https://portal.azure.com)) に移動します。</span><span class="sxs-lookup"><span data-stu-id="96d5f-115">Create a separate tab in your browser, and then go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span> <span data-ttu-id="96d5f-116">必要に応じて、Microsoft 365 E5 の試用版または有料サブスクリプション用の全体管理者アカウントの資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-116">If needed, sign in with the credentials of the global administrator account for your Microsoft 365 E5 trial or paid subscription.</span></span>
    
2. <span data-ttu-id="96d5f-117">Azure Portal で **[Azure Active Directory] > [グループ]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-117">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>
    
3. <span data-ttu-id="96d5f-118">**[グループ] - [すべてのグループ]** ブレードで、**[+ 新しいグループ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-118">On the **Groups - All groups** blade, click **+ New group**.</span></span>
    
4. <span data-ttu-id="96d5f-119">**[グループ]** ブレードでの手順:</span><span class="sxs-lookup"><span data-stu-id="96d5f-119">On the **Group** blade:</span></span>
    
  - <span data-ttu-id="96d5f-120">**[グループの種類]** で **[セキュリティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="96d5f-120">Select **Security** in **Group type**.</span></span>
    
  - <span data-ttu-id="96d5f-121">**[名前]** に「**C スイート**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="96d5f-121">Type **C-Suite** in **Name**.</span></span>
    
  - <span data-ttu-id="96d5f-122">**[メンバーシップの種類]** で **[割り当て済み]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="96d5f-122">Select **Assigned** in **Membership type**.</span></span>
      
5. <span data-ttu-id="96d5f-123">**[作成]** をクリックして、 **[グループ]** ブレードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="96d5f-123">Click **Create**, and then close the **Group** blade.</span></span>
    
<span data-ttu-id="96d5f-124">次に、新しい **C スイート** グループのメンバーに Microsoft 365 E5 ライセンスが自動的に割り当てられるように、自動ライセンスを設定します。</span><span class="sxs-lookup"><span data-stu-id="96d5f-124">Next, configure automatic licensing so that members of the new **C-Suite** group is automatically assigned a Microsoft 365 E5 license.</span></span>
  
1. <span data-ttu-id="96d5f-125">Azure Portal で **[Azure Active Directory] > [ライセンス] > [すべての製品]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-125">In the Azure portal, click **Azure Active Directory > Licenses > All products**.</span></span>
    
2. <span data-ttu-id="96d5f-126">一覧で、「**Microsoft 365 Enterprise E5**」を選択し、**[割り当て]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-126">In the list, select **Microsoft 365 Enterprise E5**, and then click **Assign**.</span></span>
    
3. <span data-ttu-id="96d5f-127">**[ライセンスの割り当て]** ブレードで、 **[ユーザーとグループ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-127">In the **Assign license** blade, click **Users and groups**.</span></span>
    
4. <span data-ttu-id="96d5f-128">グループの一覧で、[**C スイト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="96d5f-128">In the list of groups, select the **C-Suite** group.</span></span>
    
5. <span data-ttu-id="96d5f-129">**[選択]** をクリックし、 **[割り当て]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-129">Click **Select**, and then click **Assign**.</span></span>
    
6. <span data-ttu-id="96d5f-130">ブラウザーの [Azure Portal] タブを閉じます。</span><span class="sxs-lookup"><span data-stu-id="96d5f-130">Close the Azure portal tab in your browser.</span></span>
    
<span data-ttu-id="96d5f-131">次に、[Graph 用 Azure Active Directory PowerShell モジュールに接続します](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="96d5f-131">Next, [connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="96d5f-132">組織名、場所、および共通のパスワードを入力し、PowerShell コマンド プロンプトまたは Integrated Script Environment (ISE) からこれらのコマンドを実行し、新しいユーザー アカウントを作成し、それぞれの C スイト グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="96d5f-132">Fill in your organization name, your location, and a common password, and then run these commands from the PowerShell command prompt or Integrated Script Environment (ISE) to create new user accounts and add them to the C-Suite group:</span></span>
  
```powershell
$orgName="<organization name, such as contoso-test for the contoso-test.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$groupName="C-Suite"
$userNames=@("CEO","CFO","CIO") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
```

> [!NOTE]
> <span data-ttu-id="96d5f-133">ここで共通のパスワードを使用することで、自動化と、開発/テスト環境の構成を容易にします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-133">The use of a common password here is for automation and ease of configuration for a dev/test environment.</span></span> <span data-ttu-id="96d5f-134">運用環境のサブスクリプションは避けるように強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-134">Obviously, this is highly discouraged for production subscriptions.</span></span> 
  
<span data-ttu-id="96d5f-135">次の手順を使用して、グループ ベースのライセンスが正しく機能していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="96d5f-135">Use these steps to verify that group-based licensing is working correctly.</span></span>
  
1. <span data-ttu-id="96d5f-136">[Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-136">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
    
2. <span data-ttu-id="96d5f-137">ブラウザーの新しい **[Microsoft 365 管理センター]** タブで、**[ユーザー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-137">From the new **Microsoft 365 admin center** tab of your browser, click **Users**.</span></span>
    
3. <span data-ttu-id="96d5f-138">ユーザーの一覧で、**[CEO]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-138">In the list of users, click **CEO**.</span></span>
    
4. <span data-ttu-id="96d5f-139">**CEO** ユーザー アカウントのプロパティが一覧表示されているウィンドウで、**製品ライセンス**内に **Microsoft 365 Enterprise E5** のライセンスが割り当てられている ことを確認します。</span><span class="sxs-lookup"><span data-stu-id="96d5f-139">In the pane that lists the properties of the **CEO** user account, verify that it has been assigned the **Microsoft 365 Enterprise E5** license in **Product licenses**.</span></span>
    
## <a name="phase-3-create-your-team"></a><span data-ttu-id="96d5f-140">フェーズ 3: チームを作成する</span><span class="sxs-lookup"><span data-stu-id="96d5f-140">Phase 3: Create your team</span></span>

<span data-ttu-id="96d5f-141">このフェーズでは、シニア リーダーシップ チームのメンバーが会社の戦略に協力できるように、セキュリティを分離したチームを作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="96d5f-141">In this phase, you create and configure a team with security isolation for members of the senior leadership team to collaborate on company strategy.</span></span>

<span data-ttu-id="96d5f-142">まず、[この記事](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)の手順に進む前に、Microsoft Teams、Office 365 グループ、SharePoint サイトのコンテンツを保護するために秘密度ラベルを有効にします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-142">First, enable sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites before you proceed with the steps in [this article](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

<span data-ttu-id="96d5f-143">次に、チームを作ります。</span><span class="sxs-lookup"><span data-stu-id="96d5f-143">Next, create the team:</span></span>

1. <span data-ttu-id="96d5f-144">Teams で、アプリの左側にある **[Teams]** をクリックして、チーム リストの下部にある **[チームに参加またはチームの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-144">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="96d5f-145">**[チームの作成]** (最初のカード、左上隅) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-145">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="96d5f-146">**[初めからチームを作成する]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="96d5f-146">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="96d5f-147">**[秘密度]**] リストで、既定のままにします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-147">In the **Sensitivity** list, keep the default.</span></span>
5. <span data-ttu-id="96d5f-148">**[プライバシー]** で、**[プライベート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-148">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="96d5f-149">**会社戦略**と入力し、[**作成**]  >  [**閉じる**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-149">Type **Company Strategy**, and then click **Create** > **Close**.</span></span>

<span data-ttu-id="96d5f-150">次に、秘密度ラベルを次の設定で構成します。</span><span class="sxs-lookup"><span data-stu-id="96d5f-150">Next, you need to configure a sensitivity label with the following settings:</span></span>

- <span data-ttu-id="96d5f-151">ラベルの名前は「会社戦略」です</span><span class="sxs-lookup"><span data-stu-id="96d5f-151">The name of the label is Company Strategy</span></span>
- <span data-ttu-id="96d5f-152">暗号化が有効になっています</span><span class="sxs-lookup"><span data-stu-id="96d5f-152">Encryption is enabled</span></span>
- <span data-ttu-id="96d5f-153">会社戦略グループには、共同編集のアクセス許可があります</span><span class="sxs-lookup"><span data-stu-id="96d5f-153">The Company Strategy group has Co-Author permissions</span></span>

<span data-ttu-id="96d5f-154">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="96d5f-154">Follow these steps:</span></span>

1. <span data-ttu-id="96d5f-155">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com)を開きます。</span><span class="sxs-lookup"><span data-stu-id="96d5f-155">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="96d5f-156">**[ソリューション]** で、**[情報保護]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-156">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="96d5f-157">**[ラベルの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-157">Click **Create a label**.</span></span>
4. <span data-ttu-id="96d5f-158">ラベル名に**会社戦略**と入力します。</span><span class="sxs-lookup"><span data-stu-id="96d5f-158">Type **Company Strategy** for the label name.</span></span>
5. <span data-ttu-id="96d5f-159">ツール ヒントに**シニア リーダーシップの会社戦略文書**と入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-159">Type **Senior leadership company strategy documents** as the tool tip, and then click **Next**.</span></span>
6. <span data-ttu-id="96d5f-160">**[暗号化]** ページの **[暗号化]** ドロップダウンで、**[適用]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="96d5f-160">On the **Encryption** page, in the **Encryption** dropdown, choose **Apply**.</span></span>
7. <span data-ttu-id="96d5f-161">チームのアクセス許可を追加するには:</span><span class="sxs-lookup"><span data-stu-id="96d5f-161">To add the team permissions:</span></span><br>
  <span data-ttu-id="96d5f-162">a.</span><span class="sxs-lookup"><span data-stu-id="96d5f-162">a.</span></span> <span data-ttu-id="96d5f-163">**[アクセス許可の割り当て]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-163">Click **Assign permissions**.</span></span><br>
  <span data-ttu-id="96d5f-164">b.</span><span class="sxs-lookup"><span data-stu-id="96d5f-164">b.</span></span> <span data-ttu-id="96d5f-165">**[ユーザーまたはグループの追加]** をクリックして、**会社戦略**を選択してから [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-165">Click **Add users or groups**, select **Company Strategy**, and then click **Add**.</span></span><br>
  <span data-ttu-id="96d5f-166">c. </span><span class="sxs-lookup"><span data-stu-id="96d5f-166">c.</span></span> <span data-ttu-id="96d5f-167">**[アクセス許可の選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-167">Click **Choose permissions**.</span></span><br>
  <span data-ttu-id="96d5f-168">d. </span><span class="sxs-lookup"><span data-stu-id="96d5f-168">d.</span></span> <span data-ttu-id="96d5f-169">ドロップダウン リストから **[共同編集者]** を選択し、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-169">Choose **Co-Author** from the dropdown list, and then click **Save**.</span></span><br>
8. <span data-ttu-id="96d5f-170">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-170">Click **Next**.</span></span>
9. <span data-ttu-id="96d5f-171">**[コンテンツのマーキング]** ページで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-171">On the **Content marking** page, click **Next**.</span></span>
10. <span data-ttu-id="96d5f-172">**[サイトとグループの設定]** ページで、**[サイトとグループの設定]** を **[オン]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="96d5f-172">On the **Site and group settings** page, set **Site and group settings** to **On**.</span></span>
11. <span data-ttu-id="96d5f-173">**[Office 365 グループに接続されているチーム サイトのプライバシー]** ドロップダウンで、**[非公開 - メンバーのみがサイトにアクセス可能]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="96d5f-173">In the **Privacy of Office 365 group-connected team sites** dropdown, choose **Private - only members can access the site**.</span></span>
12. <span data-ttu-id="96d5f-174">**[非管理対象デバイス]** で、**[アクセスをブロックする]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="96d5f-174">Under **Unmanaged devices**, choose **Block access**.</span></span>
13. <span data-ttu-id="96d5f-175">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-175">Click **Next**.</span></span>
14. <span data-ttu-id="96d5f-176">**[Office アプリの自動ラベル付け]** ページで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-176">On the **Auto-labeling for Office apps** page, click **Next**.</span></span>
15. <span data-ttu-id="96d5f-177">**[送信]** をクリックしてから、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-177">Click **Submit**, and then click **Done**.</span></span>

<span data-ttu-id="96d5f-178">次に、新しいラベルを次の手順で発行します。</span><span class="sxs-lookup"><span data-stu-id="96d5f-178">Next, publish the new label with these steps:</span></span> 

1. <span data-ttu-id="96d5f-179">Microsoft 365 コンプライアンス センターまたは **[情報保護]** ページで、**[ラベル ポリシー]** タブを選びます。</span><span class="sxs-lookup"><span data-stu-id="96d5f-179">In the Microsoft 365 compliance center, on the **Information protection** page, choose the **Label policies** tab.</span></span>
2. <span data-ttu-id="96d5f-180">**[ラベルの発行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-180">Click **Publish labels**.</span></span>
3. <span data-ttu-id="96d5f-181">**[発行する秘密度ラベルの選択]** ページで、**[発行する秘密度ラベルの選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-181">On the **Choose sensitivity labels to publish** page, click **Choose sensitivity labels to publish**.</span></span>
4. <span data-ttu-id="96d5f-182">**会社戦略**を選択し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-182">Select **Company Strategy**, and then click **Add**.</span></span>
5. <span data-ttu-id="96d5f-183">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-183">Click **Next**.</span></span>
6. <span data-ttu-id="96d5f-184">[**ユーザーとグループに発行**] ページで、[**ユーザーとグループの選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-184">On the **Publish to users and groups** page, click **Choose users and groups**.</span></span>
7. <span data-ttu-id="96d5f-185">[**追加**] をクリックし、**会社戦略**を選択します。</span><span class="sxs-lookup"><span data-stu-id="96d5f-185">Click **Add**, and then select **Company Strategy**.</span></span>
8. <span data-ttu-id="96d5f-186">**[追加]** をクリックし、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-186">Click **Add**, and then click **Done**.</span></span>
9. <span data-ttu-id="96d5f-187">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-187">Click **Next**.</span></span>
10. <span data-ttu-id="96d5f-188">[ポリシーの設定] ページで、**[ユーザーはラベルを削除するか、分類ラベルを下げるために正当な理由を提供する必要がある]** チェック ボックスをオンにし、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-188">On the Policy settings page, select the **Users must provide justification to remove a label or lower classification label** check box, and then click **Next**.</span></span>
11. <span data-ttu-id="96d5f-189">ポリシー名として**会社戦略**と入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-189">Type **Company Strategy** for the policy name, and then click **Next**.</span></span>
12. <span data-ttu-id="96d5f-190">**[送信]** をクリックしてから、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-190">Click **Submit** and then click **Done**.</span></span>

<span data-ttu-id="96d5f-191">発行後に**会社戦略**ラベルが使用可能になるまでに、しばらく時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="96d5f-191">It may take some time for the **Company Strategy** label to become available after it's been published.</span></span>

<span data-ttu-id="96d5f-192">次に、新しいラベルを**会社戦略**チームに適用し、既定の共有リンクの種類を更新して、意図したよりも広い対象ユーザーにファイルやフォルダーが不用意に共有されるリスクを軽減します。</span><span class="sxs-lookup"><span data-stu-id="96d5f-192">Next, apply your new label to the **Company Strategy** team and update the default sharing link type to reduce the risk of accidentally sharing files and folders to a wider audience than intended.</span></span> 

1. <span data-ttu-id="96d5f-193">[SharePoint 管理センター](https://admin.microsoft.com/sharepoint)を開きます。</span><span class="sxs-lookup"><span data-stu-id="96d5f-193">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="96d5f-194">**[サイト]** で、**[アクティブなサイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-194">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="96d5f-195">**会社戦略**サイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-195">Click the **Company Strategy** site.</span></span>
4. <span data-ttu-id="96d5f-196">**[ポリシー]** タブで、**[秘密度]** の下側にある **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-196">On the **Policies** tab, under **Sensitivity**, click **Edit**.</span></span>
5. <span data-ttu-id="96d5f-197">**会社戦略**ラベルを選択し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-197">Select the **Company Strategy** label, and then click **Save**.</span></span>
6. <span data-ttu-id="96d5f-198">**[ポリシー]** タブで、**[外部共有]** の下側にある **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-198">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="96d5f-199">[**組織内のユーザーのみ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="96d5f-199">Choose **Only people in your organization**.</span></span>
6. <span data-ttu-id="96d5f-200">[**既定の共有リンクの種類**] で、[**組織レベルの設定と同じ**] チェック ボックスをオフにして、[**既存のアクセス権を持つユーザー**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="96d5f-200">Under **Default sharing** link type, clear the **Same as organization-level setting** check box, and select **People with existing access**.</span></span>
7. <span data-ttu-id="96d5f-201">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-201">Click **Save**.</span></span>

<span data-ttu-id="96d5f-202">次に、**会社戦略**チームの所有者のみのサイト共有を構成します。</span><span class="sxs-lookup"><span data-stu-id="96d5f-202">Next, configure owners-only site sharing for the **Company Strategy** team.</span></span>

1. <span data-ttu-id="96d5f-203">Teams で、**会社戦略**チームの **[全般]** タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="96d5f-203">In Teams, navigate to the **General** tab of the **Company Strategy** team.</span></span>
2. <span data-ttu-id="96d5f-204">チームのツール バーで、**[ファイル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-204">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="96d5f-205">省略記号をクリックし、**[SharePoint で開く]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-205">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="96d5f-206">基となる SharePoint サイトのツール バーで、設定アイコンをクリックしてから、**[サイトの権限]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-206">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="96d5f-207">[サイトの権限] ウィンドウで、**[サイトの共有]** の **[メンバーが共有する方法を変更]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-207">In the Site permissions pane, under **Site Sharing**, click **Change how members can share**.</span></span>
6. <span data-ttu-id="96d5f-208">**[共有アクセス許可]** で、**[サイト所有者のみが、ファイル、フォルダー、およびサイトを共有できます]** を選択して、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96d5f-208">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>
7. <span data-ttu-id="96d5f-209">[**アクセス許可**] および [**設定**] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="96d5f-209">Close the **Permissions** and **Settings** panes.</span></span>

<span data-ttu-id="96d5f-210">会社戦略グループのメンバーとしてサインインすると、Word、Excel、PowerPoint のホーム ツール バーの [**秘密度**] オプションに**会社戦略**が表示されています。</span><span class="sxs-lookup"><span data-stu-id="96d5f-210">If you sign in as a member of the Company Strategy group, you will see **Company Strategy** in the **Sensitivity** option in the Home toolbar of Word, Excel, and PowerPoint.</span></span> <span data-ttu-id="96d5f-211">ラベルをファイルに割り当てるには、[**秘密度**] オプションから**会社戦略**ラベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="96d5f-211">Select the **Company Strategy** label from the **Sensitivity** option to assign the label to a file.</span></span>

<span data-ttu-id="96d5f-212">会社戦略チームの最終的な構成をここに示します。</span><span class="sxs-lookup"><span data-stu-id="96d5f-212">Here is the resulting configuration for the Company Strategy team.</span></span>

![会社戦略の分離チームの構成](../media/team-security-isolation-dev-test/team-security-isolation-dev-test-config.png)

<span data-ttu-id="96d5f-214">チーム内のファイルには、会社戦略グループのメンバーによって割り当てられた会社戦略の秘密度ラベルを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="96d5f-214">Files in the team can have the Company Strategy sensitivity label assigned by the members of the Company Strategy group.</span></span> <span data-ttu-id="96d5f-215">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="96d5f-215">Here is an example.</span></span>

![会社戦略の秘密度ラベルが適用されたファイルの例](../media/team-security-isolation-dev-test/team-security-isolation-dev-test-config-example.png)
 
## <a name="next-step"></a><span data-ttu-id="96d5f-217">次の手順</span><span class="sxs-lookup"><span data-stu-id="96d5f-217">Next step</span></span>

<span data-ttu-id="96d5f-218">実稼働環境への展開の準備ができたら、詳細な設定情報は、「[セキュリティの分離を使用してチームを構成する](secure-teams-security-isolation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96d5f-218">When you are ready for production deployment, see [Configure a team with security isolation](secure-teams-security-isolation.md) for detailed configuration information.</span></span>
