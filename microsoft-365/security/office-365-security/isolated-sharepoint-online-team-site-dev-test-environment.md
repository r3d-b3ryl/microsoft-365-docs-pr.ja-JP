---
title: Office 365 開発/テスト環境での分離した SharePoint Online チーム サイト
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: d1795031-beef-49ea-a6fc-5da5450d320d
description: '概要: Microsoft 365 開発/テスト環境で、組織の他の部分から分離された SharePoint Online チーム サイトを構成します。'
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 103ba1ddb2b5123db80be91f40c4fce8c6e2eb3d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286611"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a><span data-ttu-id="2b1fc-103">分離した SharePoint Online チーム サイト開発/テスト環境</span><span class="sxs-lookup"><span data-stu-id="2b1fc-103">Isolated SharePoint Online team site dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2b1fc-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="2b1fc-104">**Applies to**</span></span>
- [<span data-ttu-id="2b1fc-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2b1fc-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2b1fc-106">Microsoft Defender for Office 365 プラン 1</span><span class="sxs-lookup"><span data-stu-id="2b1fc-106">Microsoft Defender for Office 365 plan 1</span></span>](office-365-atp.md)
- <span data-ttu-id="2b1fc-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2b1fc-107">SharePoint Online</span></span> 


 <span data-ttu-id="2b1fc-108">**概要:** Microsoft 365 開発/テスト環境で、組織の他の部分から分離された SharePoint Online チーム サイトを構成します。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-108">**Summary:** Configure a SharePoint Online team site that is isolated from the rest of the organization in your Microsoft 365 dev/test environment.</span></span>

<span data-ttu-id="2b1fc-109">Microsoft 365 の SharePoint Online チーム サイトは、共通のドキュメント ライブラリ、OneNote ノートブック、その他のサービスを使用して共同作業を行う場所です。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-109">SharePoint Online team sites in Microsoft 365 are locations for collaboration using a common document library, a OneNote notebook, and other services.</span></span> <span data-ttu-id="2b1fc-110">多くの場合、部門または組織全体での幅広いアクセスやコラボレーションが望まれます。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-110">In many cases, you want wide access and collaboration across departments or organizations.</span></span> <span data-ttu-id="2b1fc-111">しかし、小さなユーザー グループでコラボレーションを行うためにアクセスとアクセス許可を厳しく制御したい場合もあります。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-111">However, in some cases, you want to tightly control the access and permissions for collaboration among a small group of people.</span></span>

<span data-ttu-id="2b1fc-p102">SharePoint Online チーム サイトへのアクセスとユーザーが実行できる操作は、SharePoint グループとアクセス許可レベルによって制御されます。既定では、SharePoint Online サイトには、3 つのアクセス レベルがあります。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-p102">Access to SharePoint Online team sites and what users can do is controlled by SharePoint groups and permission levels. By default, SharePoint Online sites have three levels of access:</span></span>

- <span data-ttu-id="2b1fc-114">**メンバー** 。サイトでリソースを表示、作成、変更できるユーザー。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-114">**Members**, who can view, create, and modify resources on the site.</span></span>
- <span data-ttu-id="2b1fc-115">**所有者** 。権限の変更を含め、サイトを完全に制御できるユーザー。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-115">**Owners**, who have complete control of the site, including the ability to change permissions.</span></span>
- <span data-ttu-id="2b1fc-116">**訪問者** 。サイトのリソースの表示のみが可能なユーザー。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-116">**Visitors**, who only can view resources on the site.</span></span>

<span data-ttu-id="2b1fc-p103">この記事では、ProjectX という秘密調査プロジェクトのための、分離した SharePoint Online チーム サイトの構成について順を追って説明します。アクセス要件は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-p103">This article steps you through the configuration of an isolated SharePoint Online team site for a secret research project named ProjectX. The access requirements are:</span></span>

- <span data-ttu-id="2b1fc-119">グループ メンバーシップによって制御される SharePoint の編集と表示の権限レベルを持つプロジェクトのメンバーだけがサイトとそのコンテンツ (ドキュメント、OneNote ノートブック、ページ) にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-119">Only members of the project can access the site and its contents (documents, OneNote Notebook, Pages), with edit and view SharePoint permission levels controlled through group membership.</span></span>

- <span data-ttu-id="2b1fc-120">サイトの管理 (サイト レベルの権限の変更を含む) を実行できるのは、サイトの作成者とサイトの管理者グループのメンバーだけです。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-120">Only the site creator and members of an Admins group for the site can perform site administration, which includes modifying site-level permissions.</span></span>

<span data-ttu-id="2b1fc-121">Microsoft 365 開発/テスト環境で分離した SharePoint Online チーム サイトをセットアップするには、次の 3 つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-121">There are three phases to setting up an isolated SharePoint Online team site in your Microsoft 365 dev/test environment:</span></span>

1. <span data-ttu-id="2b1fc-122">Microsoft 365 開発/テスト環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-122">Create the Microsoft 365 dev/test environment.</span></span>

2. <span data-ttu-id="2b1fc-123">ProjectX のユーザーとグループを作成する。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-123">Create the users and groups for ProjectX.</span></span>

3. <span data-ttu-id="2b1fc-124">新しい ProjectX SharePoint Online チーム サイトを作成して分離させる。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-124">Create a new ProjectX SharePoint Online team site and isolate it.</span></span>

> [!TIP]
> <span data-ttu-id="2b1fc-125">
            [ここ](https://aka.ms/catlgstack)をクリックして、One Microsoft Cloud のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-125">Click [here](https://aka.ms/catlgstack) for a visual map to all the articles in the One Microsoft Cloud Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-microsoft-365-devtest-environment"></a><span data-ttu-id="2b1fc-126">フェーズ 1: 軽量またはシミュレーションのエンタープライズ Microsoft 365 開発/テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="2b1fc-126">Phase 1: Build out your lightweight or simulated enterprise Microsoft 365 dev/test environment</span></span>

<span data-ttu-id="2b1fc-127">最小要件で、分離した SharePoint Online チーム サイトを軽量な方法で作成する場合は、軽量な基本構成のフェーズ 2 とフェーズ 3 の手順に従 [ってください](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-127">If you just want to create an isolated SharePoint Online team site in a lightweight way with the minimum requirements, follow the instructions in phases 2 and 3 of [The lightweight base configuration](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>

<span data-ttu-id="2b1fc-128">シミュレーションのエンタープライズ構成で分離した SharePoint Online チーム サイトを作成する場合は [、「Microsoft 365](../../enterprise/password-hash-sync-m365-ent-test-environment.md)テスト環境のパスワード ハッシュ同期」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-128">If you want to create an isolated SharePoint Online team site in a simulated enterprise configuration, follow the instructions in [Password hash synchronization for your Microsoft 365 test environment](../../enterprise/password-hash-sync-m365-ent-test-environment.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2b1fc-129">分離した SharePoint Online サイトを作成する場合、シミュレーションのエンタープライズ開発/テスト環境は必要とされません。これには、インターネットに接続されたシミュレートされたイントラネットと、Active Directory ドメイン サービス (AD DS) フォレストのディレクトリ同期が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-129">Creating an isolated SharePoint Online site does not require the simulated enterprise dev/test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="2b1fc-130">ここでは、分離した SharePoint Online サイトをテストし、一般的な組織を表す環境でテストを行うオプションとして提供されています。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-130">It is provided here as an option so that you can test an isolated SharePoint Online site and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-user-accounts-and-access-groups"></a><span data-ttu-id="2b1fc-131">フェーズ 2: ユーザー アカウントとアクセス グループを作成する</span><span class="sxs-lookup"><span data-stu-id="2b1fc-131">Phase 2: Create user accounts and access groups</span></span>

<span data-ttu-id="2b1fc-132">「Connect to [Office 365 PowerShell」](../../enterprise/connect-to-microsoft-365-powershell.md) の手順を使用して、グローバル管理者アカウントで試用版サブスクリプションに接続します。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-132">Use the instructions in [Connect to Office 365 PowerShell](../../enterprise/connect-to-microsoft-365-powershell.md) to connect to your trial subscription with your global administrator account from:</span></span>

- <span data-ttu-id="2b1fc-133">コンピューター (軽量な Microsoft 365 開発/テスト環境用)。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-133">Your computer (for the lightweight Microsoft 365 dev/test environment).</span></span>

- <span data-ttu-id="2b1fc-134">CLIENT1 仮想マシン (シミュレーションのエンタープライズ Microsoft 365 開発/テスト環境用)。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-134">The CLIENT1 virtual machine (for the simulated enterprise Microsoft 365 dev/test environment).</span></span>

<span data-ttu-id="2b1fc-135">ProjectX の SharePoint Online チーム サイト用に新しいアクセス グループを作成するには、Windows PowerShell 用 Microsoft Azure Active Directory モジュールのプロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-135">To create the new access groups for the ProjectX SharePoint Online team site, run these commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
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

<span data-ttu-id="2b1fc-136">組織名 (例: contosotoycompany)、所属地域に該当する 2 文字の国別コードを入力して、Windows PowerShell 用 Windows Azure Active Directory モジュールのプロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-136">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, and then run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="2b1fc-137">**New-MsolUser** コマンドの表示から、デザイナーのリーダーのアカウント用に生成されたパスワードを見つけて、安全な場所に記録しておきます。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-137">From the display of the **New-MsolUser** command, note the generated password for the Lead Designer account and record it in a safe location.</span></span>

<span data-ttu-id="2b1fc-138">次に示すコマンドを Windows PowerShell 用 Microsoft Azure Active Directory モジュールのプロンプトから実行します。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-138">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="2b1fc-139">**New-MsolUser** コマンドの表示から、リサーチのリーダーのアカウント用に生成されたパスワードを見つけて、安全な場所に記録しておきます。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-139">From the display of the **New-MsolUser** command, note the generated password for the Lead Researcher account and record it in a safe location.</span></span>

<span data-ttu-id="2b1fc-140">次に示すコマンドを Windows PowerShell 用 Microsoft Azure Active Directory モジュールのプロンプトから実行します。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-140">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="2b1fc-141">**New-MsolUser** コマンドの表示から、開発 VP 用に生成されたパスワードを見つけて、安全な場所に記録しておきます。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-141">From the display of the **New-MsolUser** command, note the generated password for the Development VP account and record it in a safe location.</span></span>

<span data-ttu-id="2b1fc-142">次に、新しいアクセス グループに新しいアカウントを追加するには、Windows PowerShell 用 Microsoft Azure Active Directory モジュールのプロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-142">Next, to add the new accounts to the new access groups, run these PowerShell commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
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

<span data-ttu-id="2b1fc-143">結果:</span><span class="sxs-lookup"><span data-stu-id="2b1fc-143">Results:</span></span>

- <span data-ttu-id="2b1fc-144">ProjectX-Members アクセス グループには、デザイナーのリーダーとリサーチのリーダーのユーザー アカウントが含まれます</span><span class="sxs-lookup"><span data-stu-id="2b1fc-144">The ProjectX-Members access group contains the Lead Designer and Lead Researcher user accounts</span></span>

- <span data-ttu-id="2b1fc-145">ProjectX-Admins アクセス グループには、試用版サブスクリプションの全体管理者アカウントが含まれます</span><span class="sxs-lookup"><span data-stu-id="2b1fc-145">The ProjectX-Admins access group contains the global administrator account for your trial subscription</span></span>

- <span data-ttu-id="2b1fc-146">ProjectX-Viewers アクセス グループには、開発 VP のユーザー アカウントが含まれます</span><span class="sxs-lookup"><span data-stu-id="2b1fc-146">The ProjectX-Viewers access group contains the Development VP user account</span></span>

<span data-ttu-id="2b1fc-147">図 1 は、アクセス グループとそのメンバーシップを示しています。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-147">Figure 1 shows the access groups and their membership.</span></span>

<span data-ttu-id="2b1fc-148">**図 1**:</span><span class="sxs-lookup"><span data-stu-id="2b1fc-148">**Figure 1**:</span></span>

![分離された SharePoint Online グループ サイトの Microsoft 365 グループとそのメンバーシップ](../../media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)

## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a><span data-ttu-id="2b1fc-150">フェーズ 3: 新しい ProjectX SharePoint Online チーム サイトを作成して分離させる</span><span class="sxs-lookup"><span data-stu-id="2b1fc-150">Phase 3: Create a new ProjectX SharePoint Online team site and isolate it</span></span>

<span data-ttu-id="2b1fc-151">ProjectX 用の SharePoint Online チーム サイトを作成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-151">To create a SharePoint Online team site for ProjectX, do the following:</span></span>

1. <span data-ttu-id="2b1fc-152">ローカル コンピューター (ライトウェイト構成) または CLIENT1 (シミュレーションのエンタープライズ構成) のいずれかのブラウザーを使用して、グローバル管理者アカウントを使用して Microsoft 365 管理センター () にサインインします。 <https://admin.microsoft.com></span><span class="sxs-lookup"><span data-stu-id="2b1fc-152">Using a browser on either your local computer (lightweight configuration) or on CLIENT1 (simulated enterprise configuration), sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="2b1fc-153">タイルのリストで、 **[SharePoint]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-153">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="2b1fc-154">ブラウザーの新しい SharePoint タブで、 **[+ サイトの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-154">On the new SharePoint tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="2b1fc-p105">**[チーム サイト名]** に「 **ProjectX**」と入力します。 **[プライバシーの設定]** で、 **[非公開 - メンバーのみがこのサイトにアクセス可能]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-p105">In **Team site name**, type **ProjectX**. In **Privacy settings**, select **Private - only members can access this site**.</span></span>

5. <span data-ttu-id="2b1fc-157">**[チーム サイトの説明]** に、「 **ProjectX 用の SharePoint サイト**」と入力し、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-157">In **Team site description**, type **SharePoint site for ProjectX**, and then click **Next**.</span></span>

6. <span data-ttu-id="2b1fc-158">**[誰を追加しますか]** ウィンドウで、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-158">On the **Who do you want to add**? pane, click **Finish**.</span></span>

7. <span data-ttu-id="2b1fc-159">ブラウザーの新しい **[ProjectX-Home]** タブのツールバーで、設定アイコンをクリックし、 **[サイトの権限]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-159">On the new **ProjectX-Home** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

8. <span data-ttu-id="2b1fc-160">**[サイトの権限]** ウィンドウで、 **[高度な権限の設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-160">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

9. <span data-ttu-id="2b1fc-161">ブラウザーの新しい **[権限:Project X]** タブで、 **[アクセス要求の設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-161">In the new **Permissions: Project X** tab in your browser, click **Access Request Settings**.</span></span>

10. <span data-ttu-id="2b1fc-162">**[アクセス要求の設定]** ダイアログ ボックスの **[サイトと個別のファイルおよびフォルダーの共有をメンバーに許可します]** と **[アクセス要求の許可]** をクリアし (これによって、3 つのチェック ボックスがすべてクリアされる)、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-162">In the **Access Requests Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow access requests** (so that all three check boxes are cleared), and then click **OK**.</span></span>

11. <span data-ttu-id="2b1fc-163">リストの **[ProjectX のメンバー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-163">Click **ProjectX Members** in the list.</span></span>

12. <span data-ttu-id="2b1fc-164">**[ユーザーとグループ]** ページで、 **[新規]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-164">On the **People and Groups** page, click **New**.</span></span>

13. <span data-ttu-id="2b1fc-165">**[共有]** ダイアログ ボックスに「 **ProjectX-Members**」と入力し、それを選択して、 **[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-165">In the **Share** dialog box, type **ProjectX-Members**, select it, and then click **Share**.</span></span>

14. <span data-ttu-id="2b1fc-166">ブラウザーの戻るボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-166">Click the back button on your browser.</span></span>

15. <span data-ttu-id="2b1fc-167">リストの **[ProjectX の所有者]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-167">Click **ProjectX Owners** in the list.</span></span>

16. <span data-ttu-id="2b1fc-168">**[ユーザーとグループ]** ページで、 **[新規]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-168">On the **People and Groups** page, click **New**.</span></span>

17. <span data-ttu-id="2b1fc-169">**[共有]** ダイアログ ボックスに「 **ProjectX-Admins**」と入力し、それを選択して、 **[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-169">In the **Share** dialog box, type **ProjectX-Admins**, select it, and then click **Share**.</span></span>

18. <span data-ttu-id="2b1fc-170">ブラウザーの戻るボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-170">Click the back button on your browser.</span></span>

19. <span data-ttu-id="2b1fc-171">リストの **[ProjectX の訪問者]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-171">Click **ProjectX Visitors** in the list.</span></span>

20. <span data-ttu-id="2b1fc-172">**[ユーザーとグループ]** ページで、 **[新規]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-172">On the **People and Groups** page, click **New**.</span></span>

21. <span data-ttu-id="2b1fc-173">**[共有]** ダイアログ ボックスに「 **ProjectX-Viewers**」と入力し、それを選択して、 **[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-173">In the **Share** dialog box, type **ProjectX-Viewers**, select it, and then click **Share**.</span></span>

22. <span data-ttu-id="2b1fc-174">ブラウザーの **[ユーザーとグループ]** タブを閉じ、ブラウザーの **[ProjectX-Home]** タブをクリックし、 **[サイトの権限]** ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-174">Close the **People and Groups** tab in your browser, click the **ProjectX-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="2b1fc-175">権限を構成した結果を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-175">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="2b1fc-176">ProjectX Members SharePoint グループに含まれるのは、ProjectX-Members アクセス グループ (デザイナーのリーダーとリサーチのリーダーのユーザー アカウントのみを含む) と ProjectX グループ (全体管理者のユーザー アカウントのみを含む) だけです。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-176">The ProjectX Members SharePoint group contains only the ProjectX-Members access group (which contains only the Lead Designer and Lead Researcher user accounts) and the ProjectX group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="2b1fc-177">ProjectX Owners SharePoint グループに含まれるのは、ProjectX-Admins アクセス グループ (全体管理者のユーザー アカウントのみを含む) だけです。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-177">The ProjectX Owners SharePoint group contains only the ProjectX-Admins access group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="2b1fc-178">ProjectX Visitors SharePoint グループに含まれるのは、ProjectX-Viewers アクセス グループ (開発 VP のユーザー アカウントのみを含む) だけです。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-178">The ProjectX Visitors SharePoint group contains only the ProjectX-Viewers access group (which contains only the Development VP user account).</span></span>

- <span data-ttu-id="2b1fc-179">メンバーはサイト レベルの権限を変更できません (これを実行できるのは、ProjectX-Admins グループのメンバーだけです)。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-179">Members cannot modify site-level permissions (this can only be done by members of the ProjectX-Admins group).</span></span>

- <span data-ttu-id="2b1fc-180">その他のユーザー アカウントは、サイトやそのリソースにアクセスすることも、そのサイトへのアクセスを要求することもできません。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-180">Other user accounts cannot access the site or its resources or request access to the site.</span></span>

<span data-ttu-id="2b1fc-181">図 2 は、SharePoint グループとそのメンバーシップを示しています。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-181">Figure 2 shows the SharePoint groups and their membership.</span></span>

<span data-ttu-id="2b1fc-182">**図 2**</span><span class="sxs-lookup"><span data-stu-id="2b1fc-182">**Figure 2**</span></span>

![分離 SharePoint Online グループ サイトの SharePoint Online グループおよびそのメンバーシップ](../../media/595abff4-64f9-49de-a37a-c70c6856936b.png)

<span data-ttu-id="2b1fc-184">デザイナーのリーダーのユーザー アカウントを使用したアクセスをデモンストレーションします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-184">Now let's demonstrate access using the Lead Designer user account:</span></span>

1. <span data-ttu-id="2b1fc-185">ブラウザーの **[ProjectX-Home]** タブを閉じ、ブラウザーの **[Microsoft Office Home]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-185">Close the **ProjectX-Home** tab in your browser, and then click the **Microsoft Office Home** tab in your browser.</span></span>

2. <span data-ttu-id="2b1fc-186">全体管理者の名前をクリックし、 **[サインアウト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-186">Click the name of your global administrator, and then click **Sign out**.</span></span>

3. <span data-ttu-id="2b1fc-187">リード デザイナーのアカウント名とパスワードを使用して、Microsoft 365 管理センター <https://admin.microsoft.com> () にサインインします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-187">Sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using the Lead Designer account name and its password.</span></span>

4. <span data-ttu-id="2b1fc-188">タイルのリストで、 **[SharePoint]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-188">In the list of tiles, click **SharePoint**.</span></span>

5. <span data-ttu-id="2b1fc-p106">ブラウザーの新しい **[SharePoint]** タブの検索ボックスに「 **ProjectX**」と入力し、検索をアクティブ化した後、 **[ProjectX]** チーム サイトをクリックします。ProjectX チーム サイトのブラウザーに新しいタブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-p106">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site. You should see a new tab in your browser for the ProjectX team site.</span></span>

6. <span data-ttu-id="2b1fc-p107">設定アイコンをクリックします。 **[サイトの権限]** にオプションがありません。サイトの権限を変更できるのは ProjectX-Admins グループのメンバーだけなので、これは正常です。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-p107">Click the settings icon. Notice that there is no option for **Site Permissions**. This is correct because only the members of the ProjectX-Admins group can modify permissions on the site</span></span>

7. <span data-ttu-id="2b1fc-194">お好きなメモ帳やテキスト エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-194">Open Notepad or a text editor of your choice.</span></span>

8. <span data-ttu-id="2b1fc-195">ProjectX チーム サイトの URL をコピーし、メモ帳やテキスト エディターの新しい行に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-195">Copy the URL of the ProjectX team site and paste it on a new line in Notepad or your text editor.</span></span>

9. <span data-ttu-id="2b1fc-196">ブラウザーの新しい **[ProjectX-Home]** タブで、 **[ドキュメント]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-196">On the new **ProjectX-Home** tab in your browser, click **Documents**.</span></span>

10. <span data-ttu-id="2b1fc-197">ProjectX ドキュメント フォルダーの URL をコピーし、メモ帳やテキスト エディターの新しい行に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-197">Copy the URL of the ProjectX documents folder and paste it on a new line in Notepad or your text editor.</span></span>

11. <span data-ttu-id="2b1fc-198">ブラウザーの **[ProjectX-Documents]** タブで、 **[新規] > [Word 文書]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-198">On the new **ProjectX-Documents** tab in your browser, click **New > Word document**.</span></span>

12. <span data-ttu-id="2b1fc-199">ページにテキストを入力し、状態が [保存済み] と表示されるのを待ち、ブラウザーの [戻る] ボタンをクリックして、ページを更新します。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-199">Type some text on the page, wait for the status to indicate **Saved**, click the back button on your browser, and then refresh the page.</span></span> <span data-ttu-id="2b1fc-200">ドキュメント フォルダーに新 **Document.docx** が **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-200">You should see a new **Document.docx** in the **Documents** folder.</span></span>

13. <span data-ttu-id="2b1fc-201">**[Document.docx]** ドキュメントの省略記号をクリックし、 **[リンクの取得]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-201">Click the ellipsis for the **Document.docx** document, and then click **Get a link**.</span></span>

14. <span data-ttu-id="2b1fc-202">**['Document.docx' の共有]** ダイアログ ボックスの URL をコピーし、メモ帳かテキスト エディターの新しい行に貼り付けた後、 **['Document.docx' の共有]** ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-202">Copy the URL in the **Share 'Document.docx'** dialog box and paste it on a new line in Notepad or your text editor, and then close the **Share 'Document.docx'** dialog box.</span></span>

15. <span data-ttu-id="2b1fc-203">ブラウザーの **[ProjectX-Documents]** タブと **[SharePoint]** タブを閉じ、 **[Microsoft Office Home]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-203">Close the **ProjectX-Documents** and **SharePoint** tabs in your browser, and then click the **Microsoft Office Home** tab.</span></span>

16. <span data-ttu-id="2b1fc-204">**[デザイナーのリーダー]** の名前をクリックし、 **[サインアウト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-204">Click the **Lead Designer** name, and then click **Sign out**.</span></span>

<span data-ttu-id="2b1fc-205">開発 VP のユーザー アカウントを使用したアクセスをデモンストレーションします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-205">Now let's demonstrate access using the Development VP user account:</span></span>

1. <span data-ttu-id="2b1fc-206">開発 VP アカウント名とパスワードを使用して、Microsoft 365 管理センター ( <https://admin.microsoft.com> ) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-206">Sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using the Development VP account name and its password.</span></span>

2. <span data-ttu-id="2b1fc-207">タイルのリストで、 **[SharePoint]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-207">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="2b1fc-p109">ブラウザーの新しい **[SharePoint]** タブの検索ボックスに「 **ProjectX**」と入力し、検索をアクティブ化した後、 **[ProjectX]** チーム サイトをクリックします。ProjectX チーム サイトのブラウザーに新しいタブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-p109">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site. You should see a new tab in your browser for the ProjectX team site.</span></span>

4. <span data-ttu-id="2b1fc-210">**[ドキュメント]** をクリックし、 **[Document.docx]** ファイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-210">Click **Documents**, and then click the **Document.docx** file.</span></span>

5. <span data-ttu-id="2b1fc-p110">ブラウザーの **[Document.docx]** タブで、テキストの変更を試みます。" **このドキュメントは読み取り専用です。**" というメッセージが表示されます。開発 VP のユーザー アカウントにはサイトの表示権限しかないため、これは正常です。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-p110">In the **Document.docx** tab in your browser, try to modify the text. You should see a message stating **This document is read-only.** This is expected because the Development VP user account only has view permissions for the site.</span></span>

6. <span data-ttu-id="2b1fc-214">ブラウザーの **[Document.docx]** タブ、 **[ProjectX-Documents]** タブ、 **[SharePoint]** タブを閉じます。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-214">Close the **Document.docx**, **ProjectX-Documents**, and **SharePoint** tabs in your browser.</span></span>

7. <span data-ttu-id="2b1fc-215">**[Microsoft Office Home]** タブをクリックし、 **[開発 VP]** の名前をクリックした後、 **[サインアウト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-215">Click the **Microsoft Office Home** tab, click the **Development VP** name, and then click **Sign out**.</span></span>

<span data-ttu-id="2b1fc-216">権限を持たないユーザー アカウントでのアクセスをデモンストレーションします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-216">Now let's demonstrate access with a user account that has no permissions:</span></span>

1. <span data-ttu-id="2b1fc-217">User 3 アカウント名とパスワードを使用して、Microsoft 365 管理センター <https://admin.microsoft.com> () にサインインします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-217">Sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using the User 3 account name and its password.</span></span>

2. <span data-ttu-id="2b1fc-218">タイルのリストで、 **[SharePoint]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-218">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="2b1fc-p111">ブラウザーの新しい **[SharePoint]** タブの検索ボックスに「 **ProjectX**」と入力し、検索をアクティブ化します。" **検索に一致するものがここにありません。**" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-p111">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box and then activate the search. You should see the message **Nothing here matches your search.**</span></span>

4. <span data-ttu-id="2b1fc-p112">メモ帳またはテキスト エディターで開いたインスタンスから、ProjectX サイトの URL を、ブラウザーのアドレス バーにコピーし、 **Enter** キーを押します。 **[アクセスは拒否されました]** というページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-p112">From the open instance of Notepad or your text editor, copy the URL for the ProjectX site into the address bar of your browser and press **Enter**. You should see an **Access Denied** page.</span></span>

5. <span data-ttu-id="2b1fc-p113">メモ帳またはテキスト エディターから、ProjectX Documents フォルダーの URL を、ブラウザーのアドレス バーにコピーし、 **Enter** キーを押します。 **[アクセスは拒否されました]** というページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-p113">From Notepad or your text editor, copy the URL for the ProjectX Documents folder into the address bar of your browser and press **Enter**. You should see an **Access Denied** page.</span></span>

6. <span data-ttu-id="2b1fc-p114">メモ帳またはテキスト エディターから、Documents.docx ファイルの URL を、ブラウザーのアドレス バーにコピーし、 **Enter** キーを押します。 **[アクセスは拒否されました]** というページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-p114">From Notepad or your text editor, copy the URL for the Documents.docx file into the address bar of your browser and press **Enter**. You should see an **Access Denied** page.</span></span>

7. <span data-ttu-id="2b1fc-227">ブラウザーの **[SharePoint]** タブを閉じ、 **[Microsoft Office Home]** タブをクリックし、 **[User 3]** の名前をクリックし、 **[サインアウト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-227">Close the **SharePoint** tab in your browser, click the **Microsoft Office Home** tab, click the **User 3** name, and then click **Sign out**.</span></span>

<span data-ttu-id="2b1fc-228">これで、分離した SharePoint Online サイトをさらにお試しいただけます。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-228">Your isolated SharePoint Online site is now ready for your additional experimentation.</span></span>

## <a name="next-step"></a><span data-ttu-id="2b1fc-229">次のステップ</span><span class="sxs-lookup"><span data-stu-id="2b1fc-229">Next Step</span></span>

<span data-ttu-id="2b1fc-230">分離した SharePoint Online チーム サイトを実稼働に展開する準備ができたら、「[分離した SharePoint Online チーム サイトの設計](design-an-isolated-sharepoint-online-team-site.md)」にある設計に関するステップバイステップの考慮事項を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b1fc-230">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2b1fc-231">関連項目</span><span class="sxs-lookup"><span data-stu-id="2b1fc-231">See Also</span></span>

[<span data-ttu-id="2b1fc-232">分離した SharePoint Online チーム サイト</span><span class="sxs-lookup"><span data-stu-id="2b1fc-232">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="2b1fc-233">クラウド導入のテスト ラボ ガイド (TLG)</span><span class="sxs-lookup"><span data-stu-id="2b1fc-233">Cloud adoption Test Lab Guides (TLGs)</span></span>](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[<span data-ttu-id="2b1fc-234">シミュレートされたエンタープライズ基本構成</span><span class="sxs-lookup"><span data-stu-id="2b1fc-234">The simulated enterprise base configuration</span></span>](../../enterprise/simulated-ent-base-configuration-microsoft-365-enterprise.md)

[<span data-ttu-id="2b1fc-235">軽量な基本構成</span><span class="sxs-lookup"><span data-stu-id="2b1fc-235">The lightweight base configuration</span></span>](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md)

[<span data-ttu-id="2b1fc-236">Microsoft 365 ソリューションおよびアーキテクチャ センター</span><span class="sxs-lookup"><span data-stu-id="2b1fc-236">Microsoft 365 solution and architecture center</span></span>](../../solutions/index.yml)