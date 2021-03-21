---
title: Microsoft 365 の主要な電子情報開示ケースの使用を開始する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: この記事では、Microsoft 365 のコア電子情報開示の使用を開始する方法について説明します。 電子情報開示のアクセス許可を割り当て、ケースを作成したら、メンバーの追加、電子情報開示ホールドの作成、調査に関連するデータの検索とエクスポートを行います。
ms.openlocfilehash: 4a814b2e0019f86e4a4fc0e26d19df4411402749
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919763"
---
# <a name="get-started-with-core-ediscovery"></a><span data-ttu-id="019b5-104">コア電子情報開示を開始する</span><span class="sxs-lookup"><span data-stu-id="019b5-104">Get started with Core eDiscovery</span></span>

<span data-ttu-id="019b5-105">Microsoft 365 のコア電子情報開示は、組織が Microsoft 365 および 365 でコンテンツを検索およびエクスポートするために使用できる基本的な電子情報開示Office提供します。</span><span class="sxs-lookup"><span data-stu-id="019b5-105">Core eDiscovery in Microsoft 365 provides a basic eDiscovery tool that organizations can use to search and export content in Microsoft 365 and Office 365.</span></span> <span data-ttu-id="019b5-106">また、コア電子情報開示を使用して、Exchange メールボックス、SharePoint サイト、OneDrive アカウント、Microsoft Teams などのコンテンツの場所に電子情報開示を保持することもできます。</span><span class="sxs-lookup"><span data-stu-id="019b5-106">You can also use Core eDiscovery to place an eDiscovery hold on content locations, such as Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft Teams.</span></span> <span data-ttu-id="019b5-107">コア電子情報開示を展開する必要は何もありませんが、コンテンツの検索、エクスポート、および保持にコア電子情報開示を使用する前に、IT 管理者と電子情報開示マネージャーが完了する必要があるいくつかの前提条件タスクがあります。</span><span class="sxs-lookup"><span data-stu-id="019b5-107">Nothing is needed to deploy Core eDiscovery, but there are some prerequisite tasks that an IT admin and eDiscovery manager have to complete before your organization can start using Core eDiscovery to search, export, and preserve content.</span></span>

<span data-ttu-id="019b5-108">この記事では、Core eDiscovery のセットアップに必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="019b5-108">This article discusses the steps necessary to set up Core eDiscovery.</span></span> <span data-ttu-id="019b5-109">これには、コア電子情報開示にアクセスし、コンテンツの場所に電子情報開示を保持するために必要な適切なライセンスを確保し、IT チーム、法務チーム、調査チームに権限を割り当て、ケースにアクセスして管理する方法が含まれます。</span><span class="sxs-lookup"><span data-stu-id="019b5-109">This includes ensuring the proper licensing required to access Core eDiscovery and place an eDiscovery hold on content locations, as well as assigning permissions to your IT, legal, and investigation team so they can access and manage cases.</span></span> <span data-ttu-id="019b5-110">この記事では、ケースを使用してコンテンツを検索およびエクスポートする方法の概要も説明します。</span><span class="sxs-lookup"><span data-stu-id="019b5-110">This article also provides a high-level overview of using cases to search for and export content.</span></span>

## <a name="step-1-verify-and-assign-appropriate-licenses"></a><span data-ttu-id="019b5-111">手順 1: 適切なライセンスを確認して割り当てる</span><span class="sxs-lookup"><span data-stu-id="019b5-111">Step 1: Verify and assign appropriate licenses</span></span>

<span data-ttu-id="019b5-112">コア電子情報開示のライセンスには、適切な組織のサブスクリプションとユーザーごとのライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="019b5-112">Licensing for Core eDiscovery requires the appropriate organization subscription and per-user licensing.</span></span>

- <span data-ttu-id="019b5-113">**組織のサブスクリプション:** Microsoft 365 コンプライアンス センターまたは Office 365 セキュリティ & コンプライアンス センターのコア電子情報開示にアクセスし、保持機能とエクスポート機能を使用するには、組織に Microsoft 365 E3 または Office 365 E3 サブスクリプション以上が必要です。</span><span class="sxs-lookup"><span data-stu-id="019b5-113">**Organization subscription:** To access Core eDiscovery in the Microsoft 365 compliance center or the Office 365 Security & Compliance Center and use the hold and export features, your organization must have a Microsoft 365 E3 or Office 365 E3 subscription or higher.</span></span>

- <span data-ttu-id="019b5-114">**ユーザーごとのライセンス:** メールボックスとサイトに電子情報開示ホールドを設定するには、組織のサブスクリプションに応じて、次のいずれかのライセンスをユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="019b5-114">**Per-user licensing:** To place an eDiscovery hold on mailboxes and sites, a user must be assigned one of the following licenses, depending on your organization subscription:</span></span>

  - <span data-ttu-id="019b5-115">Microsoft 365 E3 または Office 365 E3 ライセンス以上</span><span class="sxs-lookup"><span data-stu-id="019b5-115">A Microsoft 365 E3 or Office 365 E3 license or higher</span></span>

   <span data-ttu-id="019b5-116">OR</span><span class="sxs-lookup"><span data-stu-id="019b5-116">OR</span></span>

  - <span data-ttu-id="019b5-117">Office 365 E1 ライセンスと Exchange Online プラン 2 または Exchange Online Archiving アドオン ライセンス</span><span class="sxs-lookup"><span data-stu-id="019b5-117">Office 365 E1 license with an Exchange Online Plan 2 or Exchange Online Archiving add-on license</span></span>

  <span data-ttu-id="019b5-118">AND</span><span class="sxs-lookup"><span data-stu-id="019b5-118">AND</span></span>

  - <span data-ttu-id="019b5-119">Officeプラン 2 または OneDrive for Business Plan 2 アドオン ライセンスを使用して 365 E1 ライセンスを作成する</span><span class="sxs-lookup"><span data-stu-id="019b5-119">Office 365 E1 license with an SharePoint Online Plan 2 or OneDrive for Business Plan 2 add-on license</span></span>
  
  <span data-ttu-id="019b5-120">ライセンスを割り当てる方法については、「ユーザーにライセンスを割り当 [てる」を参照してください](../admin/manage/assign-licenses-to-users.md)。</span><span class="sxs-lookup"><span data-stu-id="019b5-120">For information about how to assign licenses, see [Assign licenses to users](../admin/manage/assign-licenses-to-users.md).</span></span>

<span data-ttu-id="019b5-121">ライセンスの詳細については、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="019b5-121">For information about licensing:</span></span>

- <span data-ttu-id="019b5-122">[Microsoft 365](/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx)コンプライアンス ライセンス&のソリューションをダウンロードして参照してください。</span><span class="sxs-lookup"><span data-stu-id="019b5-122">Download and see the "Discover & Respond" solution in the [Microsoft 365 Compliance Licensing Comparison](/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx).</span></span>

- <span data-ttu-id="019b5-123">「セキュリティ [とコンプライアンス &サービスの説明」を参照してください](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)。</span><span class="sxs-lookup"><span data-stu-id="019b5-123">See the [Security & Compliance Center service description](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span>

## <a name="step-2-assign-ediscovery-permissions"></a><span data-ttu-id="019b5-124">手順 2: 電子情報開示のアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="019b5-124">Step 2: Assign eDiscovery permissions</span></span>

<span data-ttu-id="019b5-125">Core 電子情報開示にアクセスしたり、コア電子情報開示ケースのメンバーとして追加したりするには、ユーザーに適切なアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="019b5-125">To access Core eDiscovery or be added as a member of a Core eDiscovery case, a user must be assigned the appropriate permissions.</span></span> <span data-ttu-id="019b5-126">具体的には、ユーザーを電子情報開示マネージャーの役割グループのメンバーとして、Office 365 セキュリティ &コンプライアンス センターに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="019b5-126">Specifically, a user must be added as a member of the eDiscovery Manager role group in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="019b5-127">この役割グループのメンバーは、コア電子情報開示ケースを作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="019b5-127">Members of this role group can create and manage Core eDiscovery cases.</span></span> <span data-ttu-id="019b5-128">メンバーの追加と削除、ユーザーへの電子情報開示の保持、検索の作成と編集、コア電子情報開示ケースからのコンテンツのエクスポートを行います。</span><span class="sxs-lookup"><span data-stu-id="019b5-128">They can add and remove members, place an eDiscovery hold on users, create and edit searches, and export content from a Core eDiscovery case.</span></span>

<span data-ttu-id="019b5-129">電子情報開示マネージャーの役割グループにユーザーを追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="019b5-129">Complete the following steps to add users to the eDiscovery Manager role group:</span></span>

1. <span data-ttu-id="019b5-130">Microsoft 365 または 365 組織の管理者アカウントの資格情報を使用して、Office [https://protection.office.com/permissions](https://protection.office.com/permissions) サインインします。</span><span class="sxs-lookup"><span data-stu-id="019b5-130">Go to [https://protection.office.com/permissions](https://protection.office.com/permissions) and sign in using the credentials for an admin account in your Microsoft 365 or Office 365 organization.</span></span>

2. <span data-ttu-id="019b5-131">[アクセス許可 **] ページで** 、電子情報開示マネージャー **の役割グループを** 選択します。</span><span class="sxs-lookup"><span data-stu-id="019b5-131">On the **Permissions** page, select the **eDiscovery Manager** role group.</span></span>

3. <span data-ttu-id="019b5-132">[電子情報開示マネージャー] フライアウト ページで、[電子情報開示マネージャー] セクション **の横** にある [ **編集] をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="019b5-132">On the eDiscovery Manager flyout page, click **Edit** next to the **eDiscovery Manager** section.</span></span>

4. <span data-ttu-id="019b5-133">役割グループの **編集ウィザードの [電子情報開示マネージャー** の選択] ページで、[探索マネージャーの選択 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="019b5-133">On the **Choose eDiscovery Manager** page in the edit role group wizard, click **Choose Discovery Manager**.</span></span>

5. <span data-ttu-id="019b5-134">[ **追加]** をクリックし、役割グループに追加するすべてのユーザーのチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="019b5-134">Click **Add** then select the checkbox for all users you want to add to the role group.</span></span>

6. <span data-ttu-id="019b5-135">[追加 **] を** クリックして選択したユーザーを追加し、[完了] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="019b5-135">Click **Add** to add the selected users, and then click **Done**.</span></span>

7. <span data-ttu-id="019b5-136">[ **保存]** をクリックしてユーザーを役割グループに追加し、[閉じる] をクリック **して** 手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="019b5-136">Click **Save** to add the users to the role group, and then click **Close** to complete the step.</span></span>

### <a name="more-information-about-the-ediscovery-manager-role-group"></a><span data-ttu-id="019b5-137">電子情報開示マネージャー役割グループの詳細</span><span class="sxs-lookup"><span data-stu-id="019b5-137">More information about the eDiscovery Manager role group</span></span>

<span data-ttu-id="019b5-138">電子情報開示マネージャーの役割グループには、2 つのサブグループがあります。</span><span class="sxs-lookup"><span data-stu-id="019b5-138">There are two subgroups in the eDiscovery Manager role group.</span></span> <span data-ttu-id="019b5-139">これらのサブグループの違いは、スコープに基づきます。</span><span class="sxs-lookup"><span data-stu-id="019b5-139">The difference between these subgroups is based on scope.</span></span>

- <span data-ttu-id="019b5-140">**電子情報開示マネージャー:** 作成したコア電子情報開示ケースまたはメンバーであるコア電子情報開示ケースを表示および管理できます。</span><span class="sxs-lookup"><span data-stu-id="019b5-140">**eDiscovery Manager:** Can view and manage the Core eDiscovery cases they create or are a member of.</span></span> <span data-ttu-id="019b5-141">別の電子情報開示マネージャーがケースを作成しても、そのケースのメンバーとして 2 番目の電子情報開示マネージャーを追加しない場合、2 番目の電子情報開示マネージャーは、コンプライアンス センターの [コア電子情報開示] ページでケースを表示または開くことができません。</span><span class="sxs-lookup"><span data-stu-id="019b5-141">If another eDiscovery Manager creates a case but doesn't add a second eDiscovery Manager as a member of that case, the second eDiscovery Manager won't be able to view or open the case on the Core eDiscovery page in the compliance center.</span></span> <span data-ttu-id="019b5-142">一般に、組織内のほとんどのユーザーは、電子情報開示マネージャー サブグループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="019b5-142">In general, most people in your organization can be added to the eDiscovery Manager subgroup.</span></span>

- <span data-ttu-id="019b5-143">**電子情報開示管理者:** 電子情報開示マネージャーが実行できるすべてのケース管理タスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="019b5-143">**eDiscovery Administrator:** Can perform all case management tasks that an eDiscovery Manager can do.</span></span> <span data-ttu-id="019b5-144">さらに、電子情報開示管理者は、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="019b5-144">Additionally, an eDiscovery Administrator can:</span></span>

  - <span data-ttu-id="019b5-145">[コア電子情報開示] ページに一覧表示されているすべてのケースを表示します。</span><span class="sxs-lookup"><span data-stu-id="019b5-145">View all cases that are listed on the Core eDiscovery page.</span></span>
  
  - <span data-ttu-id="019b5-146">自分自身をケースのメンバーとして追加した後、組織のすべてのケースを管理します。</span><span class="sxs-lookup"><span data-stu-id="019b5-146">Manage any case in the organization after they add themselves as a member of the case.</span></span>

  - <span data-ttu-id="019b5-147">組織内のすべてのケースのケース データにアクセスしてエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="019b5-147">Access and export case data for any case in the organization.</span></span>

  <span data-ttu-id="019b5-148">アクセス範囲が広いため、電子情報開示管理者のサブグループのメンバーになっている管理者は少数です。</span><span class="sxs-lookup"><span data-stu-id="019b5-148">Because of the broad scope of access, an organization should have only a few admins who are members of the eDiscovery Administrators subgroup.</span></span>

<span data-ttu-id="019b5-149">電子情報開示のアクセス許可と、電子情報開示マネージャー役割グループに割り当てられている各役割の説明の詳細については、「Assign [eDiscovery permissions」を参照してください](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="019b5-149">For more information about eDiscovery permissions and a description of each role that's assigned to the eDiscovery Manager role group, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

## <a name="step-3-create-a-core-ediscovery-case"></a><span data-ttu-id="019b5-150">手順 3: コア電子情報開示ケースを作成する</span><span class="sxs-lookup"><span data-stu-id="019b5-150">Step 3: Create a Core eDiscovery case</span></span>

<span data-ttu-id="019b5-151">次の手順では、ケースを作成し、コア電子情報開示の使用を開始します。</span><span class="sxs-lookup"><span data-stu-id="019b5-151">The next step is to create a case and start using Core eDiscovery.</span></span> <span data-ttu-id="019b5-152">ケースを作成し、メンバーを追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="019b5-152">Complete the following steps to create a case and add members.</span></span> <span data-ttu-id="019b5-153">ケースを作成するユーザーは、メンバーとして自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="019b5-153">The user who creates the case is automatically added as a member.</span></span>

1. <span data-ttu-id="019b5-154">適切な電子情報開示アクセス許可が割り当てられているユーザー アカウントの資格情報を使用して、アクセスして [https://compliance.microsoft.com](https://compliance.microsoft.com) サインインします。</span><span class="sxs-lookup"><span data-stu-id="019b5-154">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for a user account that has been assigned the appropriate eDiscovery permissions.</span></span> <span data-ttu-id="019b5-155">組織の管理役割グループのメンバーは、コア電子情報開示ケースを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="019b5-155">Members of the Organization Management role group can also create Core eDiscovery cases.</span></span>

2. <span data-ttu-id="019b5-156">Microsoft 365 コンプライアンス センターの左側のナビゲーション ウィンドウで、[すべて表示] をクリックし、[電子情報開示] >**クリックします**。</span><span class="sxs-lookup"><span data-stu-id="019b5-156">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="019b5-157">[コア電子 **情報開示] ページで** 、[ケースの作成 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="019b5-157">On the **Core eDiscovery** page, click **Create a case**.</span></span>

4. <span data-ttu-id="019b5-158">[新しい **ケース] フライ** アウト ページで、ケースに名前 (必須) を付け、オプションのケース番号と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="019b5-158">On the **New case** flyout page, give the case a name (required), and then type an optional case number and description.</span></span> <span data-ttu-id="019b5-159">ケース名は、組織内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="019b5-159">The case name must be unique in your organization.</span></span>

5. <span data-ttu-id="019b5-160">[保存 **] を** クリックしてケースを作成します。</span><span class="sxs-lookup"><span data-stu-id="019b5-160">Click **Save** to create the case.</span></span>

   <span data-ttu-id="019b5-161">新しいケースが作成され、[コア電子情報開示] ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="019b5-161">The new case is created and displayed on the Core eDiscovery page.</span></span> <span data-ttu-id="019b5-162">[更新] を **クリックして** 新しいケースを表示する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="019b5-162">You may have to click **Refresh** to display the new case.</span></span> 

## <a name="step-4-optional-add-members-to-a-core-ediscovery-case"></a><span data-ttu-id="019b5-163">手順 4 (オプション): コア電子情報開示ケースにメンバーを追加する</span><span class="sxs-lookup"><span data-stu-id="019b5-163">Step 4 (optional): Add members to a Core eDiscovery case</span></span>

<span data-ttu-id="019b5-164">手順 3 でケースを作成し、ケースを使用する唯一のユーザーである場合は、この手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="019b5-164">If you create a case in Step 3 and you're the only person who will use the case, then you don't have to perform this step.</span></span> <span data-ttu-id="019b5-165">ケースを使用して、電子情報開示ホールドの作成、コンテンツの検索、または検索結果のエクスポートを開始できます。</span><span class="sxs-lookup"><span data-stu-id="019b5-165">You can start using the case to create eDiscovery holds, search for content, or export search results.</span></span> <span data-ttu-id="019b5-166">他のユーザー (または役割グループ) にケースへのアクセス権を与える場合は、この手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="019b5-166">Perform this step if you want to give other users (or roles group) access to the case.</span></span>

1. <span data-ttu-id="019b5-167">Microsoft  365 コンプライアンス センターの [コア電子情報開示] ページで、メンバーを追加するケースの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="019b5-167">On the **Core eDiscovery** page in the Microsoft 365 compliance center, click the name of the case that you want to add members to.</span></span>

2. <span data-ttu-id="019b5-168">[このケース **の管理] フライ** アウト ページの **[メンバーの** 管理] で、[追加] **をクリックして** ケースにメンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="019b5-168">On the **Manage this case** flyout page, under **Manage members**, click **Add** to add members to the case.</span></span> 

    <span data-ttu-id="019b5-169">役割グループをケースのメンバーとして追加する場合も選択できます。</span><span class="sxs-lookup"><span data-stu-id="019b5-169">You can also choose to add role group as members of a case.</span></span> <span data-ttu-id="019b5-170">[役割 **グループの管理] で、[** 追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="019b5-170">Under **Manage role groups**, click **Add**.</span></span> <span data-ttu-id="019b5-171">ケースに割り当てできるのは、自分がメンバーである役割グループのみです。</span><span class="sxs-lookup"><span data-stu-id="019b5-171">You can only assign the role groups that you are a member of to a case.</span></span> <span data-ttu-id="019b5-172">役割グループは、電子情報開示ケースにメンバーを割り当てできるユーザーを制御する理由です。</span><span class="sxs-lookup"><span data-stu-id="019b5-172">That's because role groups control who can assign members to an eDiscovery case.</span></span>

3. <span data-ttu-id="019b5-173">ケースのメンバーとして追加できるユーザーまたは役割グループの一覧で、追加するユーザー (または役割グループ) の名前の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="019b5-173">In the list of people or role groups that can be added as members of the case, click the check box next to the names of the people (or role groups) that you want to add.</span></span> <span data-ttu-id="019b5-174">メンバーとして追加できるユーザーが多数いる場合は、[**検索**] ボックスを使用してリストで特定のユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="019b5-174">If you have a large list of people who can added as members, use the **Search** box to search for a specific person in the list.</span></span>
  
4. <span data-ttu-id="019b5-175">ケースのメンバーとして追加するユーザーまたは役割グループを選択した後、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="019b5-175">After you select the people or role groups to add as members of the case, click **Add**.</span></span>

5. <span data-ttu-id="019b5-176">[**保存**] をクリックして、ケース メンバーの新しいリストを保存します。</span><span class="sxs-lookup"><span data-stu-id="019b5-176">Click **Save** to save the new list of case members.</span></span>

## <a name="explore-the-core-ediscovery-workflow"></a><span data-ttu-id="019b5-177">コア電子情報開示ワークフローの詳細</span><span class="sxs-lookup"><span data-stu-id="019b5-177">Explore the Core eDiscovery workflow</span></span>

<span data-ttu-id="019b5-178">コア電子情報開示の使用を開始するには、関心のあるユーザー向け電子情報開示ホールドを作成し、調査に関連するコンテンツを検索し、そのデータをエクスポートして詳細を確認する簡単なワークフローを次に示します。</span><span class="sxs-lookup"><span data-stu-id="019b5-178">To get you started using core eDiscovery, here's a simple workflow of creating eDiscovery holds for people of interest, searching for content that relevant to your investigation, and then exporting that data for further review.</span></span> <span data-ttu-id="019b5-179">これらの各手順では、探索できるいくつかの拡張コア電子情報開示機能も強調表示します。</span><span class="sxs-lookup"><span data-stu-id="019b5-179">In each of these steps, we'll also highlight some extended Core eDiscovery functionality that you can explore.</span></span>

![コア電子情報開示ワークフロー](../media/CoreEdiscoveryWorkflow.png)

1. <span data-ttu-id="019b5-181">**[電子情報開示ホールドを作成します](create-ediscovery-holds.md)**。</span><span class="sxs-lookup"><span data-stu-id="019b5-181">**[Create an eDiscovery hold](create-ediscovery-holds.md)**.</span></span> <span data-ttu-id="019b5-182">ケースを作成した後の最初の手順は、調査に関心のあるユーザーのコンテンツの場所に保留 (電子情報開示 *ホールドとも呼* ばれる) を配置します。</span><span class="sxs-lookup"><span data-stu-id="019b5-182">The first step after creating a case is placing a hold (also called an *eDiscovery hold*) on the content locations of the people of interest in your investigation.</span></span> <span data-ttu-id="019b5-183">コンテンツの場所には、Exchange メールボックス、SharePoint サイト、OneDrive アカウント、Microsoft Teams および 365 グループに関連付けられているメールボックスとサイトOfficeがあります。</span><span class="sxs-lookup"><span data-stu-id="019b5-183">Content locations include Exchange mailboxes, SharePoint sites, OneDrive accounts, as well as the mailboxes and sites associated with Microsoft Teams and Office 365 Groups.</span></span> <span data-ttu-id="019b5-184">この手順は省略可能ですが、電子情報開示ホールドを作成すると、調査中にケースに関連する可能性のあるコンテンツが保持されます。</span><span class="sxs-lookup"><span data-stu-id="019b5-184">While this step is optional, creating an eDiscovery hold preserves content that may be relevant to the case during the investigation.</span></span> <span data-ttu-id="019b5-185">電子情報開示ホールドを作成する場合は、特定のコンテンツの場所のすべてのコンテンツを保持するか、クエリ ベースの保持を作成して、保留クエリに一致するコンテンツのみを保持できます。</span><span class="sxs-lookup"><span data-stu-id="019b5-185">When you create an eDiscovery hold you can preserve all content in specific content locations or you can create a query-based hold to preserve only the content that matches a hold query.</span></span> <span data-ttu-id="019b5-186">コンテンツの保持に加えて、電子情報開示ホールドを作成するもう 1 つの適切な理由は、次の手順で検索を作成して実行するときに、(検索する各場所を選択する必要がある代わりに) 保留のコンテンツの場所をすばやく検索する方法です。</span><span class="sxs-lookup"><span data-stu-id="019b5-186">In addition to preserving content, another good reason to create eDiscovery holds is to quickly search the content locations on hold (instead of having to select each location to search) when you create and run searches in the next step.</span></span> <span data-ttu-id="019b5-187">調査が完了したら、作成した保留を解除できます。</span><span class="sxs-lookup"><span data-stu-id="019b5-187">After you complete your investigation, you can release any hold that you created.</span></span>

2. <span data-ttu-id="019b5-188">**[コンテンツを検索します](search-for-content-in-core-ediscovery.md)**。</span><span class="sxs-lookup"><span data-stu-id="019b5-188">**[Search for content](search-for-content-in-core-ediscovery.md)**.</span></span> <span data-ttu-id="019b5-189">電子情報開示ホールドを作成した後、組み込みの検索ツールを使用して保留のコンテンツの場所を検索します。</span><span class="sxs-lookup"><span data-stu-id="019b5-189">After you create eDiscovery holds, use the built-in search tool to search the content locations on hold.</span></span> <span data-ttu-id="019b5-190">他のコンテンツの場所で、ケースに関連する可能性のあるデータを検索できます。</span><span class="sxs-lookup"><span data-stu-id="019b5-190">You can also search other content locations for data that may be relevant to the case.</span></span> <span data-ttu-id="019b5-191">ケースに関連付けられたさまざまな検索を作成して実行できます。</span><span class="sxs-lookup"><span data-stu-id="019b5-191">You can create and run different searches that are associated with the case.</span></span> <span data-ttu-id="019b5-192">キーワード、プロパティ、および条件を使用して、[](keyword-queries-and-search-conditions.md)ケースに最も関連性の高いデータを含む検索結果を返す検索クエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="019b5-192">You use keywords, properties, and conditions to [build search queries](keyword-queries-and-search-conditions.md) that return search results with the data that's most likely relevant to the case.</span></span> <span data-ttu-id="019b5-193">以下のことも実行できます。</span><span class="sxs-lookup"><span data-stu-id="019b5-193">You can also:</span></span>

   - <span data-ttu-id="019b5-194">検索クエリを絞り込み、結果を絞り込むのに役立つ検索統計を表示します。</span><span class="sxs-lookup"><span data-stu-id="019b5-194">View search statistics that may help you refine a search query to narrow the results.</span></span>

   - <span data-ttu-id="019b5-195">検索結果をプレビューして、関連するデータが見つかったかどうかを迅速に確認します。</span><span class="sxs-lookup"><span data-stu-id="019b5-195">Preview the search results to quickly verify whether the relevant data is being found.</span></span>

   - <span data-ttu-id="019b5-196">クエリを修正し、検索を再実行します。</span><span class="sxs-lookup"><span data-stu-id="019b5-196">Revise a query and rerun the search.</span></span>

3. <span data-ttu-id="019b5-197">**[検索結果をエクスポートおよびダウンロードします](export-content-in-core-ediscovery.md)**。</span><span class="sxs-lookup"><span data-stu-id="019b5-197">**[Export and download search results](export-content-in-core-ediscovery.md)**.</span></span> <span data-ttu-id="019b5-198">調査に関連するデータを検索して検索した後、Office 365 からエクスポートして、調査チーム外のユーザーによるレビューを行います。</span><span class="sxs-lookup"><span data-stu-id="019b5-198">After you search for and find data that's relevant to your investigation, you can export it out of Office 365 for review by people outside of the investigation team.</span></span> <span data-ttu-id="019b5-199">データのエクスポートは 2 段階のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="019b5-199">Exporting data is a two-step process.</span></span> <span data-ttu-id="019b5-200">最初の手順は、365 からケース内の検索の結果をエクスポートOfficeです。</span><span class="sxs-lookup"><span data-stu-id="019b5-200">The first step is to export the results of a search in the case out of Office 365.</span></span> <span data-ttu-id="019b5-201">これは、検索の結果を Microsoft が提供する Azure Storage の場所にコピーすることで実現されます。</span><span class="sxs-lookup"><span data-stu-id="019b5-201">This is accomplished by copying the results of a search to a Microsoft-provided Azure Storage location.</span></span> <span data-ttu-id="019b5-202">次の手順では、電子情報開示エクスポート ツールを使用してコンテンツをローカル コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="019b5-202">The next step is to use the eDiscovery Export tool to download the content to a local computer.</span></span> <span data-ttu-id="019b5-203">エクスポートされたデータ ファイルに加えて、エクスポート パッケージの格納には、エクスポート レポート、概要レポート、およびエラー レポートも含まれます。</span><span class="sxs-lookup"><span data-stu-id="019b5-203">In addition to the exported data files, the contains of the export package also contains an export report, a summary report, and an error report.</span></span>