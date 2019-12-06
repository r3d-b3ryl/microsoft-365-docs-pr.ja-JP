---
title: 分離した SharePoint Online チーム サイト開発/テスト環境
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: d1795031-beef-49ea-a6fc-5da5450d320d
description: '概要: Office 365 開発/テスト環境で、組織の他の部分とは分離した SharePoint Online チーム サイトを構成します。'
ms.openlocfilehash: 7f2f4fa15bd9cc3c78afa0e507aaeaf069f83932
ms.sourcegitcommit: 2468bcb01625f97a322459814d81b9faad717859
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871823"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a><span data-ttu-id="66140-103">Office 365 開発/テスト環境での分離した SharePoint Online チーム サイト</span><span class="sxs-lookup"><span data-stu-id="66140-103">Isolated SharePoint Online team site dev/test environment</span></span>

 <span data-ttu-id="66140-104">**概要:** Office 365 開発/テスト環境で、組織の他の部分とは分離した SharePoint Online チーム サイトを構成します。</span><span class="sxs-lookup"><span data-stu-id="66140-104">**Summary:** Configure a SharePoint Online team site that is isolated from the rest of the organization in your Office 365 dev/test environment.</span></span>

<span data-ttu-id="66140-p101">Office 365 の SharePoint Online チーム サイトは、共通のドキュメント ライブラリや OneNote ノートブックなどのサービスを使用してコラボレーションを行うための場所です。多くの場合、部門または組織全体での幅広いアクセスやコラボレーションが望まれます。しかし、小さなユーザー グループでコラボレーションを行うためにアクセスとアクセス許可を厳しく制御したい場合もあります。</span><span class="sxs-lookup"><span data-stu-id="66140-p101">SharePoint Online team sites in Office 365 are locations for collaboration using a common document library, a OneNote notebook, and other services. In many cases, you want wide access and collaboration across departments or organizations. However, in some cases, you want to tightly control the access and permissions for collaboration among a small group of people.</span></span>

<span data-ttu-id="66140-p102">SharePoint Online チーム サイトへのアクセスとユーザーが実行できる操作は、SharePoint グループとアクセス許可レベルによって制御されます。既定では、SharePoint Online サイトには、3 つのアクセス レベルがあります。</span><span class="sxs-lookup"><span data-stu-id="66140-p102">Access to SharePoint Online team sites and what users can do is controlled by SharePoint groups and permission levels. By default, SharePoint Online sites have three levels of access:</span></span>

- <span data-ttu-id="66140-110">**メンバー** 。サイトでリソースを表示、作成、変更できるユーザー。</span><span class="sxs-lookup"><span data-stu-id="66140-110">**Members**, who can view, create, and modify resources on the site.</span></span>

- <span data-ttu-id="66140-111">**所有者** 。権限の変更を含め、サイトを完全に制御できるユーザー。</span><span class="sxs-lookup"><span data-stu-id="66140-111">**Owners**, who have complete control of the site, including the ability to change permissions.</span></span>

- <span data-ttu-id="66140-112">**訪問者** 。サイトのリソースの表示のみが可能なユーザー。</span><span class="sxs-lookup"><span data-stu-id="66140-112">**Visitors**, who only can view resources on the site.</span></span>

<span data-ttu-id="66140-p103">この記事では、ProjectX という秘密調査プロジェクトのための、分離した SharePoint Online チーム サイトの構成について順を追って説明します。アクセス要件は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="66140-p103">This article steps you through the configuration of an isolated SharePoint Online team site for a secret research project named ProjectX. The access requirements are:</span></span>

- <span data-ttu-id="66140-115">グループ メンバーシップによって制御される SharePoint の編集と表示の権限レベルを持つプロジェクトのメンバーだけがサイトとそのコンテンツ (ドキュメント、OneNote ノートブック、ページ) にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="66140-115">Only members of the project can access the site and its contents (documents, OneNote Notebook, Pages), with edit and view SharePoint permission levels controlled through group membership.</span></span>

- <span data-ttu-id="66140-116">サイトの管理 (サイト レベルの権限の変更を含む) を実行できるのは、サイトの作成者とサイトの管理者グループのメンバーだけです。</span><span class="sxs-lookup"><span data-stu-id="66140-116">Only the site creator and members of an Admins group for the site can perform site administration, which includes modifying site-level permissions.</span></span>

<span data-ttu-id="66140-117">Office 365 開発/テスト環境での分離した SharePoint Online チーム サイトのセットアップには、3 つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="66140-117">There are three phases to setting up an isolated SharePoint Online team site in your Office 365 dev/test environment:</span></span>

1. <span data-ttu-id="66140-118">Office 365 開発/テスト環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="66140-118">Create the Office 365 dev/test environment.</span></span>

2. <span data-ttu-id="66140-119">ProjectX のユーザーとグループを作成する。</span><span class="sxs-lookup"><span data-stu-id="66140-119">Create the users and groups for ProjectX.</span></span>

3. <span data-ttu-id="66140-120">新しい ProjectX SharePoint Online チーム サイトを作成して分離させる。</span><span class="sxs-lookup"><span data-stu-id="66140-120">Create a new ProjectX SharePoint Online team site and isolate it.</span></span>

> [!TIP]
> <span data-ttu-id="66140-121">[ここ](https://aka.ms/catlgstack)をクリックして、One Microsoft Cloud のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="66140-121">Click [here](https://aka.ms/catlgstack) for a visual map to all the articles in the One Microsoft Cloud Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-office-365-devtest-environment"></a><span data-ttu-id="66140-122">フェーズ 1: ライトウェイトの、またはシミュレーションのエンタープライズ Office 365 開発/テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="66140-122">Phase 1: Build out your lightweight or simulated enterprise Office 365 dev/test environment</span></span>

<span data-ttu-id="66140-123">最小要件でのライトウェイトの方法で分離した SharePoint Online チーム サイトを作成する場合は、[Office 365 開発/テスト環境](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment) のフェーズ 2 とフェーズ 3 の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="66140-123">If you just want to create an isolated SharePoint Online team site in a lightweight way with the minimum requirements, follow the instructions in phases 2 and 3 of [Office 365 dev/test environment](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment).</span></span>

<span data-ttu-id="66140-124">シミュレーションのエンタープライズ構成で分離した SharePoint Online チーム サイトを作成する場合は、[Office 365 開発/テスト環境の DirSync](https://docs.microsoft.com/office365/enterprise/dirsync-for-your-office-365-dev-test-environment) の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="66140-124">If you want to create an isolated SharePoint Online team site in a simulated enterprise configuration, follow the instructions in [DirSync for your Office 365 dev/test environment](https://docs.microsoft.com/office365/enterprise/dirsync-for-your-office-365-dev-test-environment).</span></span>

> [!NOTE]
> <span data-ttu-id="66140-125">分離した SharePoint Online サイトを作成する場合は、シミュレートされたエンタープライズ開発/テスト環境を必要としません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。</span><span class="sxs-lookup"><span data-stu-id="66140-125">Creating an isolated SharePoint Online site does not require the simulated enterprise dev/test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="66140-126">この記事は、分離した SharePoint Online サイトをテストして、一般的な組織を表す環境で試してみることができるオプションとして提供されています。</span><span class="sxs-lookup"><span data-stu-id="66140-126">It is provided here as an option so that you can test an isolated SharePoint Online site and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-user-accounts-and-access-groups"></a><span data-ttu-id="66140-127">フェーズ 2: ユーザー アカウントとアクセス グループを作成する</span><span class="sxs-lookup"><span data-stu-id="66140-127">Phase 2: Create user accounts and access groups</span></span>

<span data-ttu-id="66140-128">「[Office 365 PowerShell への接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)」の手順を使用して、全体管理者アカウントで以下から Office 365 の監査サブスクリプション フォームに接続します。</span><span class="sxs-lookup"><span data-stu-id="66140-128">Use the instructions in [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) to connect to your Office 365 trail subscription with your global administrator account from:</span></span>

- <span data-ttu-id="66140-129">自分のコンピューター (軽量の Office 365 開発/テスト環境の場合)。</span><span class="sxs-lookup"><span data-stu-id="66140-129">Your computer (for the lightweight Office 365 dev/test environment).</span></span>

- <span data-ttu-id="66140-130">CLIENT1 仮想マシン (シミュレーションのエンタープライズ Office 365 開発/テスト環境の場合)。</span><span class="sxs-lookup"><span data-stu-id="66140-130">The CLIENT1 virtual machine (for the simulated enterprise Office 365 dev/test environment).</span></span>

<span data-ttu-id="66140-131">ProjectX の SharePoint Online チーム サイト用に新しいアクセス グループを作成するには、Windows PowerShell 用 Microsoft Azure Active Directory モジュールのプロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="66140-131">To create the new access groups for the ProjectX SharePoint Online team site, run these commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```
$groupName="ProjectX-Members"
$groupDesc="People allowed to collaborate for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Admins"
$groupDesc="People allowed to administer SharePoint for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Viewers"
$groupDesc="People allowed to view the SharePoint resources for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
```

<span data-ttu-id="66140-132">組織名 (例: contosotoycompany)、所属地域に該当する 2 文字の国別コードを入力して、Windows PowerShell 用 Windows Azure Active Directory モジュールのプロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="66140-132">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, and then run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="66140-133">**New-MsolUser** コマンドの表示から、デザイナーのリーダーのアカウント用に生成されたパスワードを見つけて、安全な場所に記録しておきます。</span><span class="sxs-lookup"><span data-stu-id="66140-133">From the display of the **New-MsolUser** command, note the generated password for the Lead Designer account and record it in a safe location.</span></span>

<span data-ttu-id="66140-134">次に示すコマンドを Windows PowerShell 用 Microsoft Azure Active Directory モジュールのプロンプトから実行します。</span><span class="sxs-lookup"><span data-stu-id="66140-134">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="66140-135">**New-MsolUser** コマンドの表示から、リサーチのリーダーのアカウント用に生成されたパスワードを見つけて、安全な場所に記録しておきます。</span><span class="sxs-lookup"><span data-stu-id="66140-135">From the display of the **New-MsolUser** command, note the generated password for the Lead Researcher account and record it in a safe location.</span></span>

<span data-ttu-id="66140-136">次に示すコマンドを Windows PowerShell 用 Microsoft Azure Active Directory モジュールのプロンプトから実行します。</span><span class="sxs-lookup"><span data-stu-id="66140-136">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="66140-137">**New-MsolUser** コマンドの表示から、開発 VP 用に生成されたパスワードを見つけて、安全な場所に記録しておきます。</span><span class="sxs-lookup"><span data-stu-id="66140-137">From the display of the **New-MsolUser** command, note the generated password for the Development VP account and record it in a safe location.</span></span>

<span data-ttu-id="66140-138">次に、新しいアクセス グループに新しいアカウントを追加するには、Windows PowerShell 用 Microsoft Azure Active Directory モジュールのプロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="66140-138">Next, to add the new accounts to the new access groups, run these PowerShell commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```
$grpName="ProjectX-Members"
$userUPN="designer@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$userUPN="researcher@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Admins"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userCredential.UserName }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Viewers"
$userUPN="devvp@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
```

<span data-ttu-id="66140-139">結果:</span><span class="sxs-lookup"><span data-stu-id="66140-139">Results:</span></span>

- <span data-ttu-id="66140-140">ProjectX-Members アクセス グループには、デザイナーのリーダーとリサーチのリーダーのユーザー アカウントが含まれます</span><span class="sxs-lookup"><span data-stu-id="66140-140">The ProjectX-Members access group contains the Lead Designer and Lead Researcher user accounts</span></span>

- <span data-ttu-id="66140-141">ProjectX-Admins アクセス グループには、試用版サブスクリプションの全体管理者アカウントが含まれます</span><span class="sxs-lookup"><span data-stu-id="66140-141">The ProjectX-Admins access group contains the global administrator account for your trial subscription</span></span>

- <span data-ttu-id="66140-142">ProjectX-Viewers アクセス グループには、開発 VP のユーザー アカウントが含まれます</span><span class="sxs-lookup"><span data-stu-id="66140-142">The ProjectX-Viewers access group contains the Development VP user account</span></span>

<span data-ttu-id="66140-143">図 1 は、アクセス グループとそのメンバーシップを示しています。</span><span class="sxs-lookup"><span data-stu-id="66140-143">Figure 1 shows the access groups and their membership.</span></span>

<span data-ttu-id="66140-144">**図 1**</span><span class="sxs-lookup"><span data-stu-id="66140-144">**Figure 1**</span></span>

![分離 SharePoint Online グループ サイトの Office 365 グループおよびそのメンバーシップ](../media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)

## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a><span data-ttu-id="66140-146">フェーズ 3: 新しい ProjectX SharePoint Online チーム サイトを作成して分離させる</span><span class="sxs-lookup"><span data-stu-id="66140-146">Phase 3: Create a new ProjectX SharePoint Online team site and isolate it</span></span>

<span data-ttu-id="66140-147">ProjectX 用の SharePoint Online チーム サイトを作成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="66140-147">To create a SharePoint Online team site for ProjectX, do the following:</span></span>

1. <span data-ttu-id="66140-148">ローカル コンピューター (ライトウェイト構成) または CLIENT1 (シミュレーションのエンタープライズ構成) のいずれかのブラウザーを使用して、全体管理者アカウントで Office 365 ポータル ([https://admin.microsoft.com](https://admin.microsoft.com)) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="66140-148">Using a browser on either your local computer (lightweight configuration) or on CLIENT1 (simulated enterprise configuration), sign in to the Office 365 portal ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>

2. <span data-ttu-id="66140-149">タイルのリストで、**[SharePoint]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66140-149">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="66140-150">ブラウザーの新しい SharePoint タブで、 **[+ サイトの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66140-150">On the new SharePoint tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="66140-p105">**[チーム サイト名]** に「 **ProjectX**」と入力します。 **[プライバシーの設定]** で、 **[非公開 - メンバーのみがこのサイトにアクセス可能]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="66140-p105">In **Team site name**, type **ProjectX**. In **Privacy settings**, select **Private - only members can access this site**.</span></span>

5. <span data-ttu-id="66140-153">**[チーム サイトの説明]** に、「 **ProjectX 用の SharePoint サイト**」と入力し、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66140-153">In **Team site description**, type **SharePoint site for ProjectX**, and then click **Next**.</span></span>

6. <span data-ttu-id="66140-154">**[誰を追加しますか]** ウィンドウで、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66140-154">On the **Who do you want to add**? pane, click **Finish**.</span></span>

7. <span data-ttu-id="66140-155">ブラウザーの新しい **[ProjectX-Home]** タブのツールバーで、設定アイコンをクリックし、 **[サイトの権限]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66140-155">On the new **ProjectX-Home** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

8. <span data-ttu-id="66140-156">**[サイトの権限]** ウィンドウで、 **[高度な権限の設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66140-156">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

9. <span data-ttu-id="66140-157">ブラウザーの新しい **[権限:Project X]** タブで、 **[アクセス要求の設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66140-157">In the new **Permissions: Project X** tab in your browser, click **Access Request Settings**.</span></span>

10. <span data-ttu-id="66140-158">**[アクセス要求の設定]** ダイアログ ボックスの **[サイトと個別のファイルおよびフォルダーの共有をメンバーに許可します]** と **[アクセス要求の許可]** をクリアし (これによって、3 つのチェック ボックスがすべてクリアされる)、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66140-158">In the **Access Requests Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow access requests** (so that all three check boxes are cleared), and then click **OK**.</span></span>

11. <span data-ttu-id="66140-159">リストの **[ProjectX のメンバー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66140-159">Click **ProjectX Members** in the list.</span></span>

12. <span data-ttu-id="66140-160">**[ユーザーとグループ]** ページで、 **[新規]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66140-160">On the **People and Groups** page, click **New**.</span></span>

13. <span data-ttu-id="66140-161">**[共有]** ダイアログ ボックスに「 **ProjectX-Members**」と入力し、それを選択して、 **[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66140-161">In the **Share** dialog box, type **ProjectX-Members**, select it, and then click **Share**.</span></span>

14. <span data-ttu-id="66140-162">ブラウザーの戻るボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="66140-162">Click the back button on your browser.</span></span>

15. <span data-ttu-id="66140-163">リストの **[ProjectX の所有者]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66140-163">Click **ProjectX Owners** in the list.</span></span>

16. <span data-ttu-id="66140-164">**[ユーザーとグループ]** ページで、 **[新規]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66140-164">On the **People and Groups** page, click **New**.</span></span>

17. <span data-ttu-id="66140-165">**[共有]** ダイアログ ボックスに「 **ProjectX-Admins**」と入力し、それを選択して、 **[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66140-165">In the **Share** dialog box, type **ProjectX-Admins**, select it, and then click **Share**.</span></span>

18. <span data-ttu-id="66140-166">ブラウザーの戻るボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="66140-166">Click the back button on your browser.</span></span>

19. <span data-ttu-id="66140-167">リストの **[ProjectX の訪問者]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66140-167">Click **ProjectX Visitors** in the list.</span></span>

20. <span data-ttu-id="66140-168">**[ユーザーとグループ]** ページで、 **[新規]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66140-168">On the **People and Groups** page, click **New**.</span></span>

21. <span data-ttu-id="66140-169">**[共有]** ダイアログ ボックスに「 **ProjectX-Viewers**」と入力し、それを選択して、 **[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66140-169">In the **Share** dialog box, type **ProjectX-Viewers**, select it, and then click **Share**.</span></span>

22. <span data-ttu-id="66140-170">ブラウザーの **[ユーザーとグループ]** タブを閉じ、ブラウザーの **[ProjectX-Home]** タブをクリックし、 **[サイトの権限]** ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="66140-170">Close the **People and Groups** tab in your browser, click the **ProjectX-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="66140-171">権限を構成した結果を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="66140-171">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="66140-172">ProjectX Members SharePoint グループに含まれるのは、ProjectX-Members アクセス グループ (デザイナーのリーダーとリサーチのリーダーのユーザー アカウントのみを含む) と ProjectX グループ (全体管理者のユーザー アカウントのみを含む) だけです。</span><span class="sxs-lookup"><span data-stu-id="66140-172">The ProjectX Members SharePoint group contains only the ProjectX-Members access group (which contains only the Lead Designer and Lead Researcher user accounts) and the ProjectX group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="66140-173">ProjectX Owners SharePoint グループに含まれるのは、ProjectX-Admins アクセス グループ (全体管理者のユーザー アカウントのみを含む) だけです。</span><span class="sxs-lookup"><span data-stu-id="66140-173">The ProjectX Owners SharePoint group contains only the ProjectX-Admins access group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="66140-174">ProjectX Visitors SharePoint グループに含まれるのは、ProjectX-Viewers アクセス グループ (開発 VP のユーザー アカウントのみを含む) だけです。</span><span class="sxs-lookup"><span data-stu-id="66140-174">The ProjectX Visitors SharePoint group contains only the ProjectX-Viewers access group (which contains only the Development VP user account).</span></span>

- <span data-ttu-id="66140-175">メンバーはサイト レベルの権限を変更できません (これを実行できるのは、ProjectX-Admins グループのメンバーだけです)。</span><span class="sxs-lookup"><span data-stu-id="66140-175">Members cannot modify site-level permissions (this can only be done by members of the ProjectX-Admins group).</span></span>

- <span data-ttu-id="66140-176">その他のユーザー アカウントは、サイトやそのリソースにアクセスすることも、そのサイトへのアクセスを要求することもできません。</span><span class="sxs-lookup"><span data-stu-id="66140-176">Other user accounts cannot access the site or its resources or request access to the site.</span></span>

<span data-ttu-id="66140-177">図 2 は、SharePoint グループとそのメンバーシップを示しています。</span><span class="sxs-lookup"><span data-stu-id="66140-177">Figure 2 shows the SharePoint groups and their membership.</span></span>

<span data-ttu-id="66140-178">**図 2**</span><span class="sxs-lookup"><span data-stu-id="66140-178">**Figure 2**</span></span>

![分離 SharePoint Online グループ サイトの SharePoint Online グループおよびそのメンバーシップ](../media/595abff4-64f9-49de-a37a-c70c6856936b.png)

<span data-ttu-id="66140-180">デザイナーのリーダーのユーザー アカウントを使用したアクセスをデモンストレーションします。</span><span class="sxs-lookup"><span data-stu-id="66140-180">Now let's demonstrate access using the Lead Designer user account:</span></span>

1. <span data-ttu-id="66140-181">ブラウザーの **[ProjectX-Home]** タブを閉じ、ブラウザーの **[Microsoft Office Home]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="66140-181">Close the **ProjectX-Home** tab in your browser, and then click the **Microsoft Office Home** tab in your browser.</span></span>

2. <span data-ttu-id="66140-182">全体管理者の名前をクリックし、 **[サインアウト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66140-182">Click the name of your global administrator, and then click **Sign out**.</span></span>

3. <span data-ttu-id="66140-183">デザイナーのリーダーのアカウント名とパスワードを使用して、Office 365 ポータル ([https://admin.microsoft.com](https://admin.microsoft.com)) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="66140-183">Sign in to the Office 365 portal ([https://admin.microsoft.com](https://admin.microsoft.com)) using the Lead Designer account name and its password.</span></span>

4. <span data-ttu-id="66140-184">タイルのリストで、**[SharePoint]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66140-184">In the list of tiles, click **SharePoint**.</span></span>

5. <span data-ttu-id="66140-p106">ブラウザーの新しい **[SharePoint]** タブの検索ボックスに「 **ProjectX**」と入力し、検索をアクティブ化した後、 **[ProjectX]** チーム サイトをクリックします。ProjectX チーム サイトのブラウザーに新しいタブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="66140-p106">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site. You should see a new tab in your browser for the ProjectX team site.</span></span>

6. <span data-ttu-id="66140-p107">設定アイコンをクリックします。 **[サイトの権限]** にオプションがありません。サイトの権限を変更できるのは ProjectX-Admins グループのメンバーだけなので、これは正常です。</span><span class="sxs-lookup"><span data-stu-id="66140-p107">Click the settings icon. Notice that there is no option for **Site Permissions**. This is correct because only the members of the ProjectX-Admins group can modify permissions on the site</span></span>

7. <span data-ttu-id="66140-190">お好きなメモ帳やテキスト エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="66140-190">Open Notepad or a text editor of your choice.</span></span>

8. <span data-ttu-id="66140-191">ProjectX チーム サイトの URL をコピーし、メモ帳やテキスト エディターの新しい行に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="66140-191">Copy the URL of the ProjectX team site and paste it on a new line in Notepad or your text editor.</span></span>

9. <span data-ttu-id="66140-192">ブラウザーの新しい **[ProjectX-Home]** タブで、 **[ドキュメント]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66140-192">On the new **ProjectX-Home** tab in your browser, click **Documents**.</span></span>

10. <span data-ttu-id="66140-193">ProjectX ドキュメント フォルダーの URL をコピーし、メモ帳やテキスト エディターの新しい行に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="66140-193">Copy the URL of the ProjectX documents folder and paste it on a new line in Notepad or your text editor.</span></span>

11. <span data-ttu-id="66140-194">ブラウザーの **[ProjectX-Documents]** タブで、 **[新規] > [Word 文書]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="66140-194">On the new **ProjectX-Documents** tab in your browser, click **New > Word document**.</span></span>

12. <span data-ttu-id="66140-195">ページに何らかのテキストを入力し、状態が [**保存済み**] になっていることを待ってから、ブラウザーの [戻る] ボタンをクリックし、ページを更新します。</span><span class="sxs-lookup"><span data-stu-id="66140-195">Type some text on the page, wait for the status to indicate **Saved**, click the back button on your browser, and then refresh the page.</span></span> <span data-ttu-id="66140-196">**ドキュメント**フォルダーに新しい **.docx**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="66140-196">You should see a new **Document.docx** in the **Documents** folder.</span></span>

13. <span data-ttu-id="66140-197">**[Document.docx]** ドキュメントの省略記号をクリックし、 **[リンクの取得]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66140-197">Click the ellipsis for the **Document.docx** document, and then click **Get a link**.</span></span>

14. <span data-ttu-id="66140-198">**['Document.docx' の共有]** ダイアログ ボックスの URL をコピーし、メモ帳かテキスト エディターの新しい行に貼り付けた後、 **['Document.docx' の共有]** ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="66140-198">Copy the URL in the **Share 'Document.docx'** dialog box and paste it on a new line in Notepad or your text editor, and then close the **Share 'Document.docx'** dialog box.</span></span>

15. <span data-ttu-id="66140-199">ブラウザーの **[ProjectX-Documents]** タブと **[SharePoint]** タブを閉じ、 **[Microsoft Office Home]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="66140-199">Close the **ProjectX-Documents** and **SharePoint** tabs in your browser, and then click the **Microsoft Office Home** tab.</span></span>

16. <span data-ttu-id="66140-200">**[デザイナーのリーダー]** の名前をクリックし、 **[サインアウト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66140-200">Click the **Lead Designer** name, and then click **Sign out**.</span></span>

<span data-ttu-id="66140-201">開発 VP のユーザー アカウントを使用したアクセスをデモンストレーションします。</span><span class="sxs-lookup"><span data-stu-id="66140-201">Now let's demonstrate access using the Development VP user account:</span></span>

1. <span data-ttu-id="66140-202">開発 VP のアカウント名とパスワードを使用して、Office 365 ポータル ([https://admin.microsoft.com](https://admin.microsoft.com)) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="66140-202">Sign in to the Office 365 portal ([https://admin.microsoft.com](https://admin.microsoft.com)) using the Development VP account name and its password.</span></span>

2. <span data-ttu-id="66140-203">タイルのリストで、**[SharePoint]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66140-203">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="66140-p109">ブラウザーの新しい **[SharePoint]** タブの検索ボックスに「 **ProjectX**」と入力し、検索をアクティブ化した後、 **[ProjectX]** チーム サイトをクリックします。ProjectX チーム サイトのブラウザーに新しいタブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="66140-p109">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site. You should see a new tab in your browser for the ProjectX team site.</span></span>

4. <span data-ttu-id="66140-206">**[ドキュメント]** をクリックし、 **[Document.docx]** ファイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="66140-206">Click **Documents**, and then click the **Document.docx** file.</span></span>

5. <span data-ttu-id="66140-p110">ブラウザーの **[Document.docx]** タブで、テキストの変更を試みます。" **このドキュメントは読み取り専用です。**" というメッセージが表示されます。開発 VP のユーザー アカウントにはサイトの表示権限しかないため、これは正常です。</span><span class="sxs-lookup"><span data-stu-id="66140-p110">In the **Document.docx** tab in your browser, try to modify the text. You should see a message stating **This document is read-only.** This is expected because the Development VP user account only has view permissions for the site.</span></span>

6. <span data-ttu-id="66140-210">ブラウザーの **[Document.docx]** タブ、 **[ProjectX-Documents]** タブ、 **[SharePoint]** タブを閉じます。</span><span class="sxs-lookup"><span data-stu-id="66140-210">Close the **Document.docx**, **ProjectX-Documents**, and **SharePoint** tabs in your browser.</span></span>

7. <span data-ttu-id="66140-211">**[Microsoft Office Home]** タブをクリックし、 **[開発 VP]** の名前をクリックした後、 **[サインアウト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66140-211">Click the **Microsoft Office Home** tab, click the **Development VP** name, and then click **Sign out**.</span></span>

<span data-ttu-id="66140-212">権限を持たないユーザー アカウントでのアクセスをデモンストレーションします。</span><span class="sxs-lookup"><span data-stu-id="66140-212">Now let's demonstrate access with a user account that has no permissions:</span></span>

1. <span data-ttu-id="66140-213">User 3 のアカウント名とパスワードを使用して、Office 365 ポータル ([https://admin.microsoft.com](https://admin.microsoft.com)) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="66140-213">Sign in to the Office 365 portal ([https://admin.microsoft.com](https://admin.microsoft.com)) using the User 3 account name and its password.</span></span>

2. <span data-ttu-id="66140-214">タイルのリストで、 **[SharePoint]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66140-214">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="66140-p111">ブラウザーの新しい **[SharePoint]** タブの検索ボックスに「 **ProjectX**」と入力し、検索をアクティブ化します。" **検索に一致するものがここにありません。**" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="66140-p111">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box and then activate the search. You should see the message **Nothing here matches your search.**</span></span>

4. <span data-ttu-id="66140-p112">メモ帳またはテキスト エディターで開いたインスタンスから、ProjectX サイトの URL を、ブラウザーのアドレス バーにコピーし、 **Enter** キーを押します。 **[アクセスは拒否されました]** というページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="66140-p112">From the open instance of Notepad or your text editor, copy the URL for the ProjectX site into the address bar of your browser and press **Enter**. You should see an **Access Denied** page.</span></span>

5. <span data-ttu-id="66140-p113">メモ帳またはテキスト エディターから、ProjectX Documents フォルダーの URL を、ブラウザーのアドレス バーにコピーし、 **Enter** キーを押します。 **[アクセスは拒否されました]** というページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="66140-p113">From Notepad or your text editor, copy the URL for the ProjectX Documents folder into the address bar of your browser and press **Enter**. You should see an **Access Denied** page.</span></span>

6. <span data-ttu-id="66140-p114">メモ帳またはテキスト エディターから、Documents.docx ファイルの URL を、ブラウザーのアドレス バーにコピーし、 **Enter** キーを押します。 **[アクセスは拒否されました]** というページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="66140-p114">From Notepad or your text editor, copy the URL for the Documents.docx file into the address bar of your browser and press **Enter**. You should see an **Access Denied** page.</span></span>

7. <span data-ttu-id="66140-223">ブラウザーの **[SharePoint]** タブを閉じ、 **[Microsoft Office Home]** タブをクリックし、 **[User 3]** の名前をクリックし、 **[サインアウト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66140-223">Close the **SharePoint** tab in your browser, click the **Microsoft Office Home** tab, click the **User 3** name, and then click **Sign out**.</span></span>

<span data-ttu-id="66140-224">これで、分離した SharePoint Online サイトをさらにお試しいただけます。</span><span class="sxs-lookup"><span data-stu-id="66140-224">Your isolated SharePoint Online site is now ready for your additional experimentation.</span></span>

## <a name="next-step"></a><span data-ttu-id="66140-225">次のステップ</span><span class="sxs-lookup"><span data-stu-id="66140-225">Next Step</span></span>

<span data-ttu-id="66140-226">分離した SharePoint Online チーム サイトを実稼働に展開する準備ができたら、「[分離した SharePoint Online チーム サイトの設計](design-an-isolated-sharepoint-online-team-site.md)」にある設計に関するステップバイステップの考慮事項を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66140-226">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="66140-227">関連項目</span><span class="sxs-lookup"><span data-stu-id="66140-227">See Also</span></span>

[<span data-ttu-id="66140-228">分離した SharePoint Online チーム サイト</span><span class="sxs-lookup"><span data-stu-id="66140-228">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="66140-229">クラウド導入のテスト ラボ ガイド (TLG)</span><span class="sxs-lookup"><span data-stu-id="66140-229">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)

[<span data-ttu-id="66140-230">基本構成開発/テスト環境</span><span class="sxs-lookup"><span data-stu-id="66140-230">Base Configuration dev/test environment</span></span>](https://docs.microsoft.com/office365/enterprise/base-configuration-dev-test-environment)

[<span data-ttu-id="66140-231">Office 365 開発/テスト環境</span><span class="sxs-lookup"><span data-stu-id="66140-231">Office 365 dev/test environment</span></span>](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment)

[<span data-ttu-id="66140-232">クラウド導入およびハイブリッド ソリューション</span><span class="sxs-lookup"><span data-stu-id="66140-232">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)




