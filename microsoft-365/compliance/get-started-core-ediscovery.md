---
title: Microsoft 365 のコア電子情報開示ケースの概要
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
description: この記事では、Microsoft 365 でコア電子情報開示の使用を開始する方法について説明します。 電子情報開示のアクセス許可を割り当ててケースを作成したら、メンバーを追加し、電子情報開示の保留リストを作成して、調査に関連するデータを検索してエクスポートできます。
ms.openlocfilehash: c9c3d8c3832703e8dbbcf8b2c04a566af0f5eb6b
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943386"
---
# <a name="get-started-with-core-ediscovery"></a><span data-ttu-id="43ec6-104">コア電子情報開示を開始する</span><span class="sxs-lookup"><span data-stu-id="43ec6-104">Get started with Core eDiscovery</span></span>

<span data-ttu-id="43ec6-105">Microsoft 365 のコア電子情報開示ツールには、組織が Microsoft 365 および Office 365 でコンテンツを検索およびエクスポートするために使用できる基本的な電子情報開示ツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="43ec6-105">Core eDiscovery in Microsoft 365 provides a basic eDiscovery tool that organizations can use to search and export content in Microsoft 365 and Office 365.</span></span> <span data-ttu-id="43ec6-106">また、コア電子情報開示を使用して、Exchange メールボックス、SharePoint サイト、OneDrive アカウント、Microsoft Teams などのコンテンツの場所に電子情報開示の保持を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="43ec6-106">You can also use Core eDiscovery to place an eDiscovery hold on content locations, such as Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft Teams.</span></span> <span data-ttu-id="43ec6-107">コア電子情報開示の展開には何も必要ありませんが、IT 管理者と電子情報開示マネージャーがコンテンツを検索、エクスポート、および保持するためにコア電子情報開示を使用して開始する前に、いくつかの前提条件のタスクを完了させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="43ec6-107">Nothing is needed to deploy Core eDiscovery, but there are some prerequisite tasks that an IT admin and eDiscovery manager have to complete before your organization can start using Core eDiscovery to search, export, and preserve content.</span></span>

<span data-ttu-id="43ec6-108">この記事では、コア電子情報開示を設定するために必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="43ec6-108">This article discusses the steps necessary to set up Core eDiscovery.</span></span> <span data-ttu-id="43ec6-109">これには、コア電子情報開示にアクセスして、コンテンツの場所に対して電子情報開示を保持するための適切なライセンスが必要になるだけでなく、お客様がサポート案件にアクセスして管理できるように、IT、法務、調査チームにアクセス許可を割り当てることも含まれます。</span><span class="sxs-lookup"><span data-stu-id="43ec6-109">This includes ensuring the proper licensing required to access Core eDiscovery and place an eDiscovery hold on content locations, as well as assigning permissions to your IT, legal, and investigation team so they can access and manage cases.</span></span> <span data-ttu-id="43ec6-110">この記事では、ケースを使用したコンテンツの検索とエクスポートの概要についても説明します。</span><span class="sxs-lookup"><span data-stu-id="43ec6-110">This article also provides a high-level overview of using cases to search for and export content.</span></span>

## <a name="step-1-verify-and-assign-appropriate-licenses"></a><span data-ttu-id="43ec6-111">手順 1: 適切なライセンスを確認して割り当てる</span><span class="sxs-lookup"><span data-stu-id="43ec6-111">Step 1: Verify and assign appropriate licenses</span></span>

<span data-ttu-id="43ec6-112">コア電子情報開示のライセンスには、適切な組織のサブスクリプションとユーザーごとのライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="43ec6-112">Licensing for Core eDiscovery requires the appropriate organization subscription and per-user licensing.</span></span>

- <span data-ttu-id="43ec6-113">**組織のサブスクリプション:** Microsoft 365 コンプライアンスセンターまたは Office 365 セキュリティ & コンプライアンスセンターでコア電子情報開示にアクセスして、ホールド機能とエクスポート機能を使用するには、組織に Microsoft 365 E3 または Office 365 E3 サブスクリプションがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="43ec6-113">**Organization subscription:** To access Core eDiscovery in the Microsoft 365 compliance center or the Office 365 Security & Compliance Center and use the hold and export features, your organization must have a Microsoft 365 E3 or Office 365 E3 subscription or higher.</span></span>

- <span data-ttu-id="43ec6-114">**ユーザーごとのライセンス:** メールボックスおよびサイトに電子情報開示を保持するには、組織のサブスクリプションに応じて、次のいずれかのライセンスをユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="43ec6-114">**Per-user licensing:** To place an eDiscovery hold on mailboxes and sites, a user must be assigned one of the following licenses, depending on your organization subscription:</span></span>

  - <span data-ttu-id="43ec6-115">Microsoft 365 E3 または Office 365 E3 ライセンス以降</span><span class="sxs-lookup"><span data-stu-id="43ec6-115">A Microsoft 365 E3 or Office 365 E3 license or higher</span></span>

   <span data-ttu-id="43ec6-116">OR</span><span class="sxs-lookup"><span data-stu-id="43ec6-116">OR</span></span>

  - <span data-ttu-id="43ec6-117">Exchange Online プラン2または Exchange Online アーカイブアドオンライセンスを使用した Microsoft 365 E1 または Office 365 E1 ライセンス</span><span class="sxs-lookup"><span data-stu-id="43ec6-117">A Microsoft 365 E1 or Office 365 E1 license with an Exchange Online Plan 2 or Exchange Online Archiving add-on license</span></span>

  <span data-ttu-id="43ec6-118">AND</span><span class="sxs-lookup"><span data-stu-id="43ec6-118">AND</span></span>

  - <span data-ttu-id="43ec6-119">SharePoint Online プラン2または OneDrive for Business プラン2アドオンライセンスを使用した Microsoft 365 E1 または Office 365 E1 ライセンス</span><span class="sxs-lookup"><span data-stu-id="43ec6-119">A Microsoft 365 E1 or Office 365 E1 license with an SharePoint Online Plan 2 or OneDrive for Business Plan 2 add-on license</span></span>
  
  <span data-ttu-id="43ec6-120">ライセンスを割り当てる方法については、「[ユーザーへのライセンスの割り当て](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43ec6-120">For information about how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

<span data-ttu-id="43ec6-121">ライセンスの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43ec6-121">For information about licensing:</span></span>

- <span data-ttu-id="43ec6-122">「 [Microsoft 365 コンプライアンスライセンスの比較](https://docs.microsoft.com/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx)」に記載されている「Discover & 応答」ソリューションをダウンロードして参照してください。</span><span class="sxs-lookup"><span data-stu-id="43ec6-122">Download and see the "Discover & Respond" solution in the [Microsoft 365 Compliance Licensing Comparison](https://docs.microsoft.com/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx).</span></span>

- <span data-ttu-id="43ec6-123">「 [Security & コンプライアンスセンターサービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43ec6-123">See the [Security & Compliance Center service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span>

## <a name="step-2-assign-ediscovery-permissions"></a><span data-ttu-id="43ec6-124">手順 2: 電子情報開示のアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="43ec6-124">Step 2: Assign eDiscovery permissions</span></span>

<span data-ttu-id="43ec6-125">コア電子情報開示ケースのメンバとして、コア電子情報開示ケースのメンバーとして追加するには、ユーザーに適切なアクセス許可が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="43ec6-125">To access Core eDiscovery or be added as a member of a Core eDiscovery case, a user must be assigned the appropriate permissions.</span></span> <span data-ttu-id="43ec6-126">具体的には、Office 365 セキュリティ & コンプライアンスセンターで、電子情報開示マネージャーの役割グループのメンバーとしてユーザーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43ec6-126">Specifically, a user must be added as a member of the eDiscovery Manager role group in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="43ec6-127">この役割グループのメンバーは、コア電子情報開示ケースを作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="43ec6-127">Members of this role group can create and manage Core eDiscovery cases.</span></span> <span data-ttu-id="43ec6-128">ユーザーは、メンバーを追加および削除したり、ユーザーに電子情報開示を保持したり、検索を作成および編集したり、コア電子情報開示ケースからコンテンツをエクスポートしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="43ec6-128">They can add and remove members, place an eDiscovery hold on users, create and edit searches, and export content from a Core eDiscovery case.</span></span>

<span data-ttu-id="43ec6-129">電子情報開示マネージャーの役割グループにユーザーを追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="43ec6-129">Complete the following steps to add users to the eDiscovery Manager role group:</span></span>

1. <span data-ttu-id="43ec6-130">に[https://protection.office.com/permissions](https://protection.office.com/permissions)移動し、Microsoft 365 または Office 365 組織の管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="43ec6-130">Go to [https://protection.office.com/permissions](https://protection.office.com/permissions) and sign in using the credentials for an admin account in your Microsoft 365 or Office 365 organization.</span></span>

2. <span data-ttu-id="43ec6-131">[**権限**] ページで、**電子情報開示マネージャー**の役割グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="43ec6-131">On the **Permissions** page, select the **eDiscovery Manager** role group.</span></span>

3. <span data-ttu-id="43ec6-132">[電子情報開示マネージャーのポップアップ] ページで、[**電子情報開示マネージャー** ] セクションの横にある [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43ec6-132">On the eDiscovery Manager flyout page, click **Edit** next to the **eDiscovery Manager** section.</span></span>

4. <span data-ttu-id="43ec6-133">役割グループの編集ウィザードの [**電子情報開示マネージャーの選択**] ページで、[**探索マネージャーの選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43ec6-133">On the **Choose eDiscovery Manager** page in the edit role group wizard, click **Choose Discovery Manager**.</span></span>

5. <span data-ttu-id="43ec6-134">[**追加**] をクリックして、役割グループに追加するすべてのユーザーのチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="43ec6-134">Click **Add** then select the checkbox for all users you want to add to the role group.</span></span>

6. <span data-ttu-id="43ec6-135">[**追加**] をクリックして選択したユーザーを追加し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43ec6-135">Click **Add** to add the selected users, and then click **Done**.</span></span>

7. <span data-ttu-id="43ec6-136">[**保存**] をクリックしてユーザーを役割グループに追加し、[**閉じる**] をクリックして手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="43ec6-136">Click **Save** to add the users to the role group, and then click **Close** to complete the step.</span></span>

### <a name="more-information-about-the-ediscovery-manager-role-group"></a><span data-ttu-id="43ec6-137">電子情報開示マネージャーの役割グループの詳細情報</span><span class="sxs-lookup"><span data-stu-id="43ec6-137">More information about the eDiscovery Manager role group</span></span>

<span data-ttu-id="43ec6-138">電子情報開示マネージャーの役割グループには、2つのサブグループがあります。</span><span class="sxs-lookup"><span data-stu-id="43ec6-138">There are two subgroups in the eDiscovery Manager role group.</span></span> <span data-ttu-id="43ec6-139">これらのサブグループの違いは、スコープに基づきます。</span><span class="sxs-lookup"><span data-stu-id="43ec6-139">The difference between these subgroups is based on scope.</span></span>

- <span data-ttu-id="43ec6-140">**電子情報開示マネージャー:** が作成またはメンバーとなっているコア電子情報開示ケースを表示および管理できます。</span><span class="sxs-lookup"><span data-stu-id="43ec6-140">**eDiscovery Manager:** Can view and manage the Core eDiscovery cases they create or are a member of.</span></span> <span data-ttu-id="43ec6-141">別の電子情報開示マネージャーが作成したケースのメンバーとして2番目の電子情報開示マネージャーを追加しなかった場合、2番目の電子情報開示マネージャーは、コンプライアンスセンターのコア電子情報開示ページでケースを表示または開くことができません。</span><span class="sxs-lookup"><span data-stu-id="43ec6-141">If another eDiscovery Manager creates a case but doesn't add a second eDiscovery Manager as a member of that case, the second eDiscovery Manager won't be able to view or open the case on the Core eDiscovery page in the compliance center.</span></span> <span data-ttu-id="43ec6-142">一般に、組織内のほとんどのユーザーは電子情報開示マネージャーサブグループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="43ec6-142">In general, most people in your organization can be added to the eDiscovery Manager subgroup.</span></span>

- <span data-ttu-id="43ec6-143">**電子情報開示管理者:** 電子情報開示マネージャーが実行できるすべてのケース管理タスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="43ec6-143">**eDiscovery Administrator:** Can perform all case management tasks that an eDiscovery Manager can do.</span></span> <span data-ttu-id="43ec6-144">さらに、電子情報開示管理者は、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="43ec6-144">Additionally, an eDiscovery Administrator can:</span></span>

  - <span data-ttu-id="43ec6-145">コア電子情報開示ページに記載されているすべてのケースを表示します。</span><span class="sxs-lookup"><span data-stu-id="43ec6-145">View all cases that are listed on the Core eDiscovery page.</span></span>
  
  - <span data-ttu-id="43ec6-146">ケースのメンバーとして自身を追加した後、組織内のケースを管理します。</span><span class="sxs-lookup"><span data-stu-id="43ec6-146">Manage any case in the organization after they add themselves as a member of the case.</span></span>

  - <span data-ttu-id="43ec6-147">組織内のあらゆるケースについて、ケースデータにアクセスしてエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="43ec6-147">Access and export case data for any case in the organization.</span></span>

  <span data-ttu-id="43ec6-148">広範なアクセス許可のため、組織には、電子情報開示管理者サブグループのメンバーである管理者を少数しか持たないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="43ec6-148">Because of the broad scope of access, an organization should have only a few admins who are members of the eDiscovery Administrators subgroup.</span></span>

<span data-ttu-id="43ec6-149">電子情報開示のアクセス許可と、電子情報開示マネージャーの役割グループに割り当てられている各役割の説明については、「[電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43ec6-149">For more information about eDiscovery permissions and a description of each role that's assigned to the eDiscovery Manager role group, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

## <a name="step-3-create-a-core-ediscovery-case"></a><span data-ttu-id="43ec6-150">手順 3: コア電子情報開示ケースを作成する</span><span class="sxs-lookup"><span data-stu-id="43ec6-150">Step 3: Create a Core eDiscovery case</span></span>

<span data-ttu-id="43ec6-151">次の手順では、ケースを作成し、コア電子情報開示を使用して作業を開始します。</span><span class="sxs-lookup"><span data-stu-id="43ec6-151">The next step is to create a case and start using Core eDiscovery.</span></span> <span data-ttu-id="43ec6-152">ケースを作成してメンバーを追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="43ec6-152">Complete the following steps to create a case and add members.</span></span> <span data-ttu-id="43ec6-153">ケースを作成したユーザーは、自動的にメンバーとして追加されます。</span><span class="sxs-lookup"><span data-stu-id="43ec6-153">The user who creates the case is automatically added as a member.</span></span>

1. <span data-ttu-id="43ec6-154">に[https://compliance.microsoft.com](https://compliance.microsoft.com)移動し、適切な電子情報開示のアクセス許可が割り当てられているユーザーアカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="43ec6-154">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for a user account that has been assigned the appropriate eDiscovery permissions.</span></span> <span data-ttu-id="43ec6-155">組織の管理役割グループのメンバーは、コア電子情報開示ケースを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="43ec6-155">Members of the Organization Management role group can also create Core eDiscovery cases.</span></span>

2. <span data-ttu-id="43ec6-156">Microsoft 365 コンプライアンスセンターの左側のナビゲーションウィンドウで、[**すべて表示**] をクリックし、[**電子情報開示 > Core**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43ec6-156">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="43ec6-157">[**コア電子情報開示**] ページで、[**ケースの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43ec6-157">On the **Core eDiscovery** page, click **Create a case**.</span></span>

4. <span data-ttu-id="43ec6-158">[**新しいケース**のポップアップ] ページで、ケース名 (必須) を指定し、オプションのケース番号と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="43ec6-158">On the **New case** flyout page, give the case a name (required), and then type an optional case number and description.</span></span> <span data-ttu-id="43ec6-159">ケース名は、組織内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="43ec6-159">The case name must be unique in your organization.</span></span>

5. <span data-ttu-id="43ec6-160">[**保存**] をクリックしてケースを作成します。</span><span class="sxs-lookup"><span data-stu-id="43ec6-160">Click **Save** to create the case.</span></span>

   <span data-ttu-id="43ec6-161">新しいケースが作成され、[コア電子情報開示] ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="43ec6-161">The new case is created and displayed on the Core eDiscovery page.</span></span> <span data-ttu-id="43ec6-162">新しいケースを表示するには、[**更新**] をクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="43ec6-162">You may have to click **Refresh** to display the new case.</span></span> 

## <a name="step-4-optional-add-members-to-a-core-ediscovery-case"></a><span data-ttu-id="43ec6-163">手順 4 (省略可能): コア電子情報開示ケースにメンバーを追加する</span><span class="sxs-lookup"><span data-stu-id="43ec6-163">Step 4 (optional): Add members to a Core eDiscovery case</span></span>

<span data-ttu-id="43ec6-164">手順3でケースを作成し、そのケースを使用するユーザーが初めての場合は、この手順を実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="43ec6-164">If you create a case in Step 3 and you're the only person who will use the case, then you don't have to perform this step.</span></span> <span data-ttu-id="43ec6-165">ケースの使用を開始して、電子情報開示の保持を作成したり、コンテンツを検索したり、検索結果をエクスポートしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="43ec6-165">You can start using the case to create eDiscovery holds, search for content, or export search results.</span></span> <span data-ttu-id="43ec6-166">他のユーザー (またはロールグループ) にケースへのアクセス権を付与する場合は、この手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="43ec6-166">Perform this step if you want to give other users (or roles group) access to the case.</span></span>

1. <span data-ttu-id="43ec6-167">Microsoft 365 コンプライアンスセンターの [**コア電子情報開示**] ページで、メンバーを追加するケースの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43ec6-167">On the **Core eDiscovery** page in the Microsoft 365 compliance center, click the name of the case that you want to add members to.</span></span>

2. <span data-ttu-id="43ec6-168">[**このケースの管理**] ページの [**メンバーの管理**] で、[**追加**] をクリックしてケースにメンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="43ec6-168">On the **Manage this case** flyout page, under **Manage members**, click **Add** to add members to the case.</span></span> 

    <span data-ttu-id="43ec6-169">また、役割グループをケースのメンバーとして追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="43ec6-169">You can also choose to add role group as members of a case.</span></span> <span data-ttu-id="43ec6-170">[**役割グループの管理**] で、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43ec6-170">Under **Manage role groups**, click **Add**.</span></span> <span data-ttu-id="43ec6-171">メンバーになっている役割グループのみをケースに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="43ec6-171">You can only assign the role groups that you are a member of to a case.</span></span> <span data-ttu-id="43ec6-172">これは、役割グループが電子情報開示ケースにメンバーを割り当てることができることを制御するためです。</span><span class="sxs-lookup"><span data-stu-id="43ec6-172">That's because role groups control who can assign members to an eDiscovery case.</span></span>

3. <span data-ttu-id="43ec6-173">ケースのメンバーとして追加できるユーザーまたは役割グループの一覧で、追加するユーザー (または役割グループ) の名前の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="43ec6-173">In the list of people or role groups that can be added as members of the case, click the check box next to the names of the people (or role groups) that you want to add.</span></span> <span data-ttu-id="43ec6-174">メンバーとして追加できるユーザーが多数いる場合は、[**検索**] ボックスを使用してリストで特定のユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="43ec6-174">If you have a large list of people who can added as members, use the **Search** box to search for a specific person in the list.</span></span>
  
4. <span data-ttu-id="43ec6-175">ケースのメンバーとして追加する人物または役割グループを選択したら、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43ec6-175">After you select the people or role groups to add as members of the case, click **Add**.</span></span>

5. <span data-ttu-id="43ec6-176">[**保存**] をクリックして、ケース メンバーの新しいリストを保存します。</span><span class="sxs-lookup"><span data-stu-id="43ec6-176">Click **Save** to save the new list of case members.</span></span>

## <a name="explore-the-core-ediscovery-workflow"></a><span data-ttu-id="43ec6-177">コア電子情報開示ワークフローを参照する</span><span class="sxs-lookup"><span data-stu-id="43ec6-177">Explore the Core eDiscovery workflow</span></span>

<span data-ttu-id="43ec6-178">コア電子情報開示の使用を開始するには、興味のあるユーザーに対して電子情報開示の保留リストを作成し、調査に関連するコンテンツを検索し、そのデータをエクスポートしてさらにレビューを行う簡単なワークフローを次に示します。</span><span class="sxs-lookup"><span data-stu-id="43ec6-178">To get you started using core eDiscovery, here's a simple workflow of creating eDiscovery holds for people of interest, searching for content that relevant to your investigation, and then exporting that data for further review.</span></span> <span data-ttu-id="43ec6-179">これらの各ステップでは、調査できる拡張コア電子情報開示機能についても取り上げます。</span><span class="sxs-lookup"><span data-stu-id="43ec6-179">In each of these steps, we'll also highlight some extended Core eDiscovery functionality that you can explore.</span></span>

![コア電子情報開示ワークフロー](../media/CoreEdiscoveryWorkflow.png)

1. <span data-ttu-id="43ec6-181">**[電子情報開示ホールドを作成](create-ediscovery-holds.md)** します。</span><span class="sxs-lookup"><span data-stu-id="43ec6-181">**[Create an eDiscovery hold](create-ediscovery-holds.md)**.</span></span> <span data-ttu-id="43ec6-182">ケースを作成した後の最初の手順は、調査対象のユーザーのコンテンツの場所に保留 (*電子情報開示ホールド*とも呼ばれます) を置くことです。</span><span class="sxs-lookup"><span data-stu-id="43ec6-182">The first step after creating a case is placing a hold (also called an *eDiscovery hold*) on the content locations of the people of interest in your investigation.</span></span> <span data-ttu-id="43ec6-183">コンテンツの場所には、Exchange メールボックス、SharePoint サイト、OneDrive アカウントに加えて、Microsoft Teams および Office 365 グループに関連付けられているメールボックスやサイトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="43ec6-183">Content locations include Exchange mailboxes, SharePoint sites, OneDrive accounts, as well as the mailboxes and sites associated with Microsoft Teams and Office 365 Groups.</span></span> <span data-ttu-id="43ec6-184">この手順はオプションですが、電子情報開示保持を作成すると、調査中にそのケースに関連する可能性があるコンテンツが保持されます。</span><span class="sxs-lookup"><span data-stu-id="43ec6-184">While this step is optional, creating an eDiscovery hold preserves content that may be relevant to the case during the investigation.</span></span> <span data-ttu-id="43ec6-185">電子情報開示の保持を作成すると、特定のコンテンツの場所にあるすべてのコンテンツを保持できます。または、クエリベースの保持を作成して保留クエリに一致するコンテンツのみを保持することができます。</span><span class="sxs-lookup"><span data-stu-id="43ec6-185">When you create an eDiscovery hold you can preserve all content in specific content locations or you can create a query-based hold to preserve only the content that matches a hold query.</span></span> <span data-ttu-id="43ec6-186">コンテンツの保持に加えて、電子情報開示の保持を作成するもう1つの理由として、次の手順で検索を作成して実行するときに、コンテンツの場所をすばやく検索することができます (検索する場所を選択するのではなく)。</span><span class="sxs-lookup"><span data-stu-id="43ec6-186">In addition to preserving content, another good reason to create eDiscovery holds is to quickly search the content locations on hold (instead of having to select each location to search) when you create and run searches in the next step.</span></span> <span data-ttu-id="43ec6-187">調査を完了したら、作成した保留を解除できます。</span><span class="sxs-lookup"><span data-stu-id="43ec6-187">After you complete your investigation, you can release any hold that you created.</span></span>

2. <span data-ttu-id="43ec6-188">**[コンテンツを検索](search-for-content-in-core-ediscovery.md)** します。</span><span class="sxs-lookup"><span data-stu-id="43ec6-188">**[Search for content](search-for-content-in-core-ediscovery.md)**.</span></span> <span data-ttu-id="43ec6-189">電子情報開示の保留リストを作成したら、組み込みの検索ツールを使用して、保留中のコンテンツの場所を検索します。</span><span class="sxs-lookup"><span data-stu-id="43ec6-189">After you create eDiscovery holds, use the built-in search tool to search the content locations on hold.</span></span> <span data-ttu-id="43ec6-190">ケースに関連する可能性があるデータについて、他のコンテンツの場所を検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="43ec6-190">You can also search other content locations for data that may be relevant to the case.</span></span> <span data-ttu-id="43ec6-191">ケースに関連付けられている異なる検索を作成して実行できます。</span><span class="sxs-lookup"><span data-stu-id="43ec6-191">You can create and run different searches that are associated with the case.</span></span> <span data-ttu-id="43ec6-192">キーワード、プロパティ、および条件を使用して、検索結果を返す[検索クエリを作成](keyword-queries-and-search-conditions.md)し、ケースに最も関連があると考えられるデータを検索します。</span><span class="sxs-lookup"><span data-stu-id="43ec6-192">You use keywords, properties, and conditions to [build search queries](keyword-queries-and-search-conditions.md) that return search results with the data that's most likely relevant to the case.</span></span> <span data-ttu-id="43ec6-193">次のようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="43ec6-193">You can also:</span></span>

   - <span data-ttu-id="43ec6-194">検索クエリを絞り込んで結果を絞り込むために役立つ検索統計を表示します。</span><span class="sxs-lookup"><span data-stu-id="43ec6-194">View search statistics that may help you refine a search query to narrow the results.</span></span>

   - <span data-ttu-id="43ec6-195">検索結果をプレビューして、関連するデータが検出されたかどうかをすばやく確認します。</span><span class="sxs-lookup"><span data-stu-id="43ec6-195">Preview the search results to quickly verify whether the relevant data is being found.</span></span>

   - <span data-ttu-id="43ec6-196">クエリを変更して、検索を再実行します。</span><span class="sxs-lookup"><span data-stu-id="43ec6-196">Revise a query and rerun the search.</span></span>

3. <span data-ttu-id="43ec6-197">**[検索結果をエクスポートしてダウンロード](export-content-in-core-ediscovery.md)** します。</span><span class="sxs-lookup"><span data-stu-id="43ec6-197">**[Export and download search results](export-content-in-core-ediscovery.md)**.</span></span> <span data-ttu-id="43ec6-198">調査に関連するデータを検索して検索した後、調査チーム外のユーザーによってレビューを受けるために、Office 365 の外部でエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="43ec6-198">After you search for and find data that's relevant to your investigation, you can export it out of Office 365 for review by people outside of the investigation team.</span></span> <span data-ttu-id="43ec6-199">データのエクスポートは、2つの手順で行います。</span><span class="sxs-lookup"><span data-stu-id="43ec6-199">Exporting data is a two-step process.</span></span> <span data-ttu-id="43ec6-200">最初の手順として、Office 365 で検索結果をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="43ec6-200">The first step is to export the results of a search in the case out of Office 365.</span></span> <span data-ttu-id="43ec6-201">これは、Microsoft が提供する Azure ストレージの場所に検索結果をコピーすることによって実現されます。</span><span class="sxs-lookup"><span data-stu-id="43ec6-201">This is accomplished by copying the results of a search to a Microsoft-provided Azure Storage location.</span></span> <span data-ttu-id="43ec6-202">次の手順では、電子情報開示エクスポートツールを使用して、コンテンツをローカルコンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="43ec6-202">The next step is to use the eDiscovery Export tool to download the content to a local computer.</span></span> <span data-ttu-id="43ec6-203">エクスポートされたデータファイルに加えて、エクスポートパッケージの格納にはエクスポートレポート、概要レポート、およびエラーレポートも含まれます。</span><span class="sxs-lookup"><span data-stu-id="43ec6-203">In addition to the exported data files, the contains of the export package also contains an export report, a summary report, and an error report.</span></span>
