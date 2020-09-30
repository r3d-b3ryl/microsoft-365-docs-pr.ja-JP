---
title: オンプレミス ユーザーの Teams チャット データを検索する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MST160
- MET150
ms.assetid: 3f7dde1a-a8ea-4366-86da-8ee6777f357c
description: Exchange ハイブリッド展開のオンプレミス　ユーザーの Teams チャットデータを検索してエクスポートするには、セキュリティ / コンプライアンス センターのコンテンツ検索ツールを使用します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 60bb207463c360d98623caed4024bb87deb5fdfc
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277095"
---
# <a name="search-for-teams-chat-data-for-on-premises-users"></a><span data-ttu-id="7f085-103">オンプレミス ユーザーの Teams チャット データを検索する</span><span class="sxs-lookup"><span data-stu-id="7f085-103">Search for Teams chat data for on-premises users</span></span>

<span data-ttu-id="7f085-104">組織に Exchange ハイブリッド展開がある場合 (または、組織がオンプレミス Exchange 組織を Office 365 と同期している場合)、Microsoft Teams を有効にしている場合、オンプレミス ユーザーは Teams チャット アプリケーションを使用してインスタント メッセージングを利用できます。</span><span class="sxs-lookup"><span data-stu-id="7f085-104">If your organization has an Exchange hybrid deployment (or your organization synchronizes an on-premises Exchange organization with Office 365) and has enabled Microsoft Teams, on-premises users can use the Teams chat application for instant messaging.</span></span> <span data-ttu-id="7f085-105">クラウドベースのユーザーの場合、Teams チャット データ (*1x1 または 1xN チャット*とも呼ばれます) は、プライマリ クラウドベースのメールボックスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="7f085-105">For a cloud-based user, Teams chat data (also called *1x1 or 1xN chats*) is saved to their primary cloud-based mailbox.</span></span> <span data-ttu-id="7f085-106">オンプレミス ユーザーが Teams チャット アプリケーションを使用する場合、そのチャット メッセージはオンプレミスにあるプライマリ メールボックスに保存できません。</span><span class="sxs-lookup"><span data-stu-id="7f085-106">When an on-premises user uses the Teams chat application, their chat messages can't be stored in their primary mailbox, which is located on-premises.</span></span> <span data-ttu-id="7f085-107">この制限を回避するために、Microsoft は、クラウドベースのストレージ領域を作成する新機能をリリースしました。これにより、電子情報開示ツールを使用して、オンプレミス ユーザーの Teams チャット データを検索およびエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="7f085-107">To get around this limitation, Microsoft has released a new feature where a cloud-based storage area is created so that you use eDiscovery tools to search for and export Teams chat data for on-premises users.</span></span>
  
<span data-ttu-id="7f085-108">オンプレミス ユーザーがクラウドベースのストレージを有効にするための要件と制限は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7f085-108">Here are the requirements and limitations for enabling cloud-based storage for on-premises users:</span></span>
  
- <span data-ttu-id="7f085-109">オンプレミスのディレクトリ サービス (Active Directory など) のユーザー アカウントは、Microsoft 365 のディレクトリ サービスである Azure Active Directory と同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f085-109">The user accounts in your on-premises directory service (such as Active Directory) must be synchronized with Azure Active Directory, the directory service in Microsoft 365.</span></span> <span data-ttu-id="7f085-110">つまり、メール ユーザー アカウントは、Microsoft 365 で作成され、プライマリ メールボックスがオンプレミスの組織に存在するユーザーに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="7f085-110">This means that a mail user account is created in Microsoft 365 and is associated with a user whose primary mailbox is located in the on-premises organization.</span></span>

- <span data-ttu-id="7f085-111">プライマリ メールボックスがオンプレミスの組織にあるユーザーには、Microsoft Teams ライセンスと Exchange Online Plan 1 の最小ライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f085-111">The user whose primary mailbox is located in the on-premises organization must be assigned a Microsoft Teams license and a minimum of an Exchange Online Plan 1 license.</span></span>

- <span data-ttu-id="7f085-112">オンプレミス ユーザーに関連付けられた Teams チャット データのみがクラウドベースのストレージ領域に保存されます。</span><span class="sxs-lookup"><span data-stu-id="7f085-112">Only Teams chat data associated with an on-premises user is stored in the cloud-based storage area.</span></span> <span data-ttu-id="7f085-113">オンプレミス ユーザーは、このストレージ領域にアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7f085-113">An on-premises user can't access this storage area in any way.</span></span>

- <span data-ttu-id="7f085-114">組織がオンプレミス ユーザーに対して Teams チャット データを検索できるようにするには、Microsoft サポートに要求を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f085-114">You have to submit a request to Microsoft Support to enable your organization to search for Teams chat data for on-premises users.</span></span> <span data-ttu-id="7f085-115">この記事の「[Microsoft サポートに要求を送信してこの機能有効にする](#filing-a-request-with-microsoft-support-to-enable-this-feature)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f085-115">See [Filing a request with Microsoft Support to enable this feature](#filing-a-request-with-microsoft-support-to-enable-this-feature) in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="7f085-116">Teams チャネルに含まれる会話は、チームに関連付けられているクラウドベースのメールボックスに常に保存されます。</span><span class="sxs-lookup"><span data-stu-id="7f085-116">Teams channel conversations are always stored in the cloud-based mailbox that's associated with the Team.</span></span> <span data-ttu-id="7f085-117">つまり、コンテンツ検索を使用して、サポート要求を提出せずにチャネル会話を検索できます。</span><span class="sxs-lookup"><span data-stu-id="7f085-117">That means you can use Content Search to search channel conversations without have to file a support request.</span></span> <span data-ttu-id="7f085-118">Teams チャネルの会話の検索の詳細については、「[Microsoft Teams と Microsoft 365 グループの検索」](content-search.md#searching-microsoft-teams-and-microsoft-365-groups)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f085-118">For more information about searching Teams channel conversations, see [Searching Microsoft Teams and Microsoft 365 Groups](content-search.md#searching-microsoft-teams-and-microsoft-365-groups).</span></span>
  
## <a name="how-it-works"></a><span data-ttu-id="7f085-119">メカニズム</span><span class="sxs-lookup"><span data-stu-id="7f085-119">How it works</span></span>

<span data-ttu-id="7f085-120">Microsoft Teams 対応のユーザーがオンプレミスのメールボックスを持っていて、そのユーザー アカウント/ID がクラウドに同期されている場合、Microsoft は、オンプレミス ユーザーの 1xN Teams チャット データを関連付けるクラウドベースのストレージを作成します。</span><span class="sxs-lookup"><span data-stu-id="7f085-120">If a Microsoft Teams-enabled user has an on-premises mailbox and their user account/identity has been synched to the cloud, Microsoft creates cloud-based storage to associate the on-premises user's 1xN Teams chat data with.</span></span> <span data-ttu-id="7f085-121">オンプレミス ユーザーの Teams チャット データは、検索用にインデックス化されます。</span><span class="sxs-lookup"><span data-stu-id="7f085-121">Teams chat data for on-premises users is indexed for search.</span></span> <span data-ttu-id="7f085-122">これにより、コンテンツ検索 (およびコアおよび高度な電子情報開示ケースに関連する検索) を使用して、オンプレミス ユーザーのために Teams チャット データを検索、プレビュー、エクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="7f085-122">This lets you Use Content Search (and searches associated with Core and Advanced eDiscovery cases) to search, preview, and export Teams chat data for on-premises users.</span></span> <span data-ttu-id="7f085-123">また、セキュリティ/コンプライアンス センター PowerShell の **\*ComplianceSearch** コマンドレットを使用して、オンプレミス ユーザー向け Teams チャット データを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="7f085-123">You can also use **\*ComplianceSearch** cmdlets in the Security & Compliance Center PowerShell to search for Teams chat data for on-premises users.</span></span>
  
<span data-ttu-id="7f085-124">次の図は、オンプレミス ユーザー向け Teams チャット データの検索、プレビュー、エクスポートを行う方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7f085-124">The following graphic shows the workflow of how Teams chat data for on-premises users is available to search, preview, and export.</span></span>
  
![Microsoft Teams のオンプレミスユーザー向けのクラウドベース ストレージ](../media/EHAMShard1.png)
  
<span data-ttu-id="7f085-126">この新しい機能に加えて、コンテンツ検索を使用して、クラウドベースの SharePoint サイトの Teams コンテンツ、各 Microsoft Team に関連付けられた Exchange メールボックス、クラウドベースのユーザーの Exchange Online メールボックスの 1xN Teams チャット データを検索、プレビュー、エクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="7f085-126">In addition to this new capability, you can still use Content Search to search, preview, and export Teams content in the cloud-based SharePoint site and Exchange mailbox associated with each Microsoft Team and 1xN Teams chat data in the Exchange Online mailbox for cloud-based users.</span></span>

## <a name="filing-a-request-with-microsoft-support-to-enable-this-feature"></a><span data-ttu-id="7f085-127">Microsoft サポートに要求を送信してこの機能有効にする</span><span class="sxs-lookup"><span data-stu-id="7f085-127">Filing a request with Microsoft Support to enable this feature</span></span>

<span data-ttu-id="7f085-128">組織がセキュリティ/コンプライアンス センターのグラフィカル ユーザー インターフェイスを使用して、オンプレミス ユーザーの Teams チャット データを検索できるようにするには、Microsoft サポートに要求を提出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f085-128">You must file a request with Microsoft Support to enable your organization to use the graphical user interface in the Security & Compliance Center to search for Teams chat data for on-premises users.</span></span> <span data-ttu-id="7f085-129">この機能は、セキュリティ/ コンプライアンス センターの PowerShell で使用できます。</span><span class="sxs-lookup"><span data-stu-id="7f085-129">This feature is available in Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="7f085-130">PowerShell を使用してオンプレミス ユーザーの Teams チャット データを検索するために、サポート要求を送信する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7f085-130">You don't have to submit a support request to use PowerShell to search for Teams chat data for on-premises users.</span></span>
  
<span data-ttu-id="7f085-131">Microsoft サポートに要求を送信するときには、次の情報を含めてください。</span><span class="sxs-lookup"><span data-stu-id="7f085-131">Include the following information when you submit the request to Microsoft Support:</span></span>
  
- <span data-ttu-id="7f085-132">組織の既定のドメイン名。</span><span class="sxs-lookup"><span data-stu-id="7f085-132">The default domain name of your organization.</span></span>

- <span data-ttu-id="7f085-133">組織のテナント名とテナント ID。</span><span class="sxs-lookup"><span data-stu-id="7f085-133">The tenant name and tenant ID of your organization.</span></span> <span data-ttu-id="7f085-134">これらは、Azure Active Directory ポータル (**管理** \> **プロパティ**の下) にあります。</span><span class="sxs-lookup"><span data-stu-id="7f085-134">You can find these in the Azure Active Directory portal (under **Manage** \> **Properties**).</span></span> <span data-ttu-id="7f085-135">「[Microsoft 365 テナント ID を見つける](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7f085-135">See [Find your Microsoft 365 tenant ID](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id).</span></span>

- <span data-ttu-id="7f085-136">サポート要求の目的に関する次のタイトルまたは説明：「オンプレミス ユーザーのアプリケーション コンテンツ検索を有効にする」。</span><span class="sxs-lookup"><span data-stu-id="7f085-136">The following title or description of the purpose of the support request: "Enable Application Content Search for On-premises Users".</span></span> <span data-ttu-id="7f085-137">これにより、要求を実装する電子情報開示エンジニアリング チームが要求をルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="7f085-137">This helps route the request to the eDiscovery engineering team who will implement the request.</span></span>

<span data-ttu-id="7f085-138">技術的な変更が行われた後、Microsoft サポートは、展開予定日を送信します。</span><span class="sxs-lookup"><span data-stu-id="7f085-138">After the engineering change is made, Microsoft Support will send you an estimated deployment date.</span></span> <span data-ttu-id="7f085-139">通常、サポート要求の送信後、展開プロセスには 2 ~ 3 週間かかります。</span><span class="sxs-lookup"><span data-stu-id="7f085-139">The deployment process usually takes 2–3 weeks after you submit the support request.</span></span>
  
### <a name="what-happens-after-this-feature-is-enabled"></a><span data-ttu-id="7f085-140">この機能を有効にするとどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="7f085-140">What happens after this feature is enabled?</span></span>

<span data-ttu-id="7f085-141">組織にこの機能が展開されると、コンテンツ検索およびセキュリティ/コンプライアンス センターの電子情報開示ケースに関連付けられた検索で次の変更が行われます。</span><span class="sxs-lookup"><span data-stu-id="7f085-141">After this feature is deployed in your organization, the following changes are made in Content Search and in searches associated with an eDiscovery case in the Security & Compliance Center:</span></span>
  
- <span data-ttu-id="7f085-142">[**オンプレミス ユーザー向けの Office アプリ コンテンツの追加**] チェックボックスが、コンテンツ 検索の[**場所**] の下に追加されます。</span><span class="sxs-lookup"><span data-stu-id="7f085-142">The **Add Office app content for on-premises users** checkbox is added under the **Locations** in Content Search.</span></span>

    ![[オンプレミス ユーザー向けの Office アプリ コンテンツの追加] チェックボックスが、コンテンツ 検索 UI に追加されます。](../media/599e751e-17bd-408d-a18c-127538de6e85.png)
  
- <span data-ttu-id="7f085-144">オンプレミス ユーザーは、検索するユーザー メールボックスを選択するために使用するコンテンツの場所選択ツールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7f085-144">On-premises users are displayed in the content locations picker that you use to select user mailboxes to search.</span></span>

## <a name="searching-for-teams-chat-content-for-on-premises-users"></a><span data-ttu-id="7f085-145">オンプレミス ユーザーの Teams チャット コンテンツの検索</span><span class="sxs-lookup"><span data-stu-id="7f085-145">Searching for Teams chat content for on-premises users</span></span>

<span data-ttu-id="7f085-146">この機能を有効にすると、セキュリティ/コンプライアンス センターのコンテンツ検索を使用して、オンプレミス ユーザーの Teams チャット データを検索できます。</span><span class="sxs-lookup"><span data-stu-id="7f085-146">After the feature has been enabled, you can use Content Search in the Security & Compliance Center to search for Teams chat data for on-premises users.</span></span>
  
1. <span data-ttu-id="7f085-147">セキュリティ/コンプライアンス センターで、[**検索**] \> [**コンテンツ検索**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="7f085-147">In the Security & Compliance Center, go to **Search** \> **Content search**</span></span>

2. <span data-ttu-id="7f085-148">[**検索**] ページで、[![追加アイコン](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **新しい検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7f085-148">On the **Search** page, click ![Add icon](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**.</span></span>

    <span data-ttu-id="7f085-149">前に説明したように、[**オンプレミス ユーザー向けの Office アプリ コンテンツの追加**] チェックボックスが、[**場所**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7f085-149">As previously explained, the **Add Office app content for on-premises users** checkbox is displayed under **Locations**.</span></span> <span data-ttu-id="7f085-150">既定では、オンになっています。</span><span class="sxs-lookup"><span data-stu-id="7f085-150">It's selected by default.</span></span>

3. <span data-ttu-id="7f085-151">キーワード クエリを作成し、必要に応じて検索クエリに条件を追加します。</span><span class="sxs-lookup"><span data-stu-id="7f085-151">Create the keyword query and add conditions to the search query if necessary.</span></span> <span data-ttu-id="7f085-152">Team チャット データのみを検索するには、[**キーワード]** ボックスに次のクエリを追加します。</span><span class="sxs-lookup"><span data-stu-id="7f085-152">To only search for Team chats data, you can add the following query in the **Keywords** box:</span></span>

    ```text
    kind:im
    ```

4. <span data-ttu-id="7f085-153">この時点で、[**場所**] の下で、次のいずれかのオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="7f085-153">At this point, you can choose one of the following options under **Locations**:</span></span>

    - <span data-ttu-id="7f085-154">**[すべての場所]:** 組織内のすべてのユーザーのメールボックスを検索するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="7f085-154">**All locations:** Select this option to search the mailboxes of all users in your organization.</span></span> <span data-ttu-id="7f085-155">チェックボックスを選択すると、オンプレミス ユーザーの Teams チャット データのすべてのクラウドベースのストレージも検索されます。</span><span class="sxs-lookup"><span data-stu-id="7f085-155">When the checkbox is selected, all cloud-based storage of Teams chat data for on-premises users will also be searched.</span></span>

    - <span data-ttu-id="7f085-156">**特定の場所:** このオプションを選択し、[**変更**\>] をクリックし、ユーザー、グループ、チームを選択して、特定のメールボックスを検索します。</span><span class="sxs-lookup"><span data-stu-id="7f085-156">**Specific locations:** Select this option and then click **Modify** \> Choose user, groups, or teams to search specific mailboxes.</span></span> <span data-ttu-id="7f085-157">前に説明したように、場所の選択ツールを使用して、オンプレミス ユーザーの Teams チャット データをを検索できます。</span><span class="sxs-lookup"><span data-stu-id="7f085-157">As previously explained, the locations picker lets you search for Teams chat data for on-premises users.</span></span>

5. <span data-ttu-id="7f085-158">検索を保存して実行します。</span><span class="sxs-lookup"><span data-stu-id="7f085-158">Save and run the search.</span></span> <span data-ttu-id="7f085-159">オンプレミス ユーザーの検索結果は、他の検索結果と同様にプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="7f085-159">Any search results for on-premises users can be previewed like any other search results.</span></span> <span data-ttu-id="7f085-160">検索結果 (Teams チャット データを含む) を PST ファイルにエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7f085-160">You can also export the search results (including any Teams chat data) to a PST file.</span></span> <span data-ttu-id="7f085-161">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f085-161">For more information, see:</span></span>

    - [<span data-ttu-id="7f085-162">検索を作成する</span><span class="sxs-lookup"><span data-stu-id="7f085-162">Create a search</span></span>](content-search.md#create-a-search)

    - [<span data-ttu-id="7f085-163">検索結果をプレビューする</span><span class="sxs-lookup"><span data-stu-id="7f085-163">Preview search results</span></span>](content-search.md#preview-search-results)

    - [<span data-ttu-id="7f085-164">コンテンツ検索の結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="7f085-164">Export Content Search results</span></span>](export-search-results.md)

## <a name="using-powershell-to-search-for-teams-chat-data-for-on-premises-users"></a><span data-ttu-id="7f085-165">PowerShell を使用してオンプレミス ユーザーの Teams チャット データを検索する</span><span class="sxs-lookup"><span data-stu-id="7f085-165">Using PowerShell to search for Teams chat data for on-premises users</span></span>

<span data-ttu-id="7f085-166">セキュリティ/コンプライアンス センター PowerShell で、**New-ComplianceSearch** および **Set-ComplianceSearch** コマンドレットを使用して、オンプレミス ユーザーの Teams チャット データを検索できます。</span><span class="sxs-lookup"><span data-stu-id="7f085-166">You can use the **New-ComplianceSearch** and **Set-ComplianceSearch** cmdlets in the Security & Compliance Center PowerShell to search for Teams chat data for on-premises users.</span></span> <span data-ttu-id="7f085-167">前に説明したように、PowerShell を使用してオンプレミス ユーザーの Teams チャット データを検索するために、サポート要求を送信する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7f085-167">As previously explained, you don't have to submit a support request to use PowerShell to search for Teams chat data for on-premises users.</span></span>
  
1. <span data-ttu-id="7f085-168">[セキュリティ/コンプライアンス センター PowerShell に接続します](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="7f085-168">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="7f085-169">次の PowerShell コマンドを実行して、オンプレミス ユーザーの Teams チャット データを検索するコンテンツ検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="7f085-169">Run the following PowerShell command to create a content search that searches for Teams chat data for on-premises users.</span></span>

    ```powershell
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

    <span data-ttu-id="7f085-170">*IncludeUserAppContent* パラメーターを使用して、*ExchangeLocation* パラメーターで指定されたユーザーのクラウドベースのストレージを指定します。</span><span class="sxs-lookup"><span data-stu-id="7f085-170">The *IncludeUserAppContent*  parameter is used to specify the cloud-based storage for the user or users who are specified by the  *ExchangeLocation*  parameter.</span></span> <span data-ttu-id="7f085-171">*AllowNotFoundExchangeLocationsEnabled* を使用すると、オンプレミス ユーザーのクラウドベースのストレージを検索できます。</span><span class="sxs-lookup"><span data-stu-id="7f085-171">The *AllowNotFoundExchangeLocationsEnabled*  allows you to search the cloud-based storage for on-premises users.</span></span> <span data-ttu-id="7f085-172">このパラメーターに `$true` 値を使用すると、検索はメールボックスの存在を検証してから実行されます。</span><span class="sxs-lookup"><span data-stu-id="7f085-172">When you use the `$true` value for this parameter, the search doesn't try to validate the existence of the mailbox before it runs.</span></span> <span data-ttu-id="7f085-173">このクラウドベースのストレージは通常のクラウドベースのメールボックスとして解決されないため、これはオンプレミス ユーザーのクラウドベースのストレージを検索するために必要です。</span><span class="sxs-lookup"><span data-stu-id="7f085-173">This is required to search the cloud-based storage for on-premises users because this cloud-based storage doesn't resolve as a regular cloud-based mailbox.</span></span>

    <span data-ttu-id="7f085-174">次の例では、Contoso 組織のオンプレミス ユーザーである Sara Davis のクラウドベースのストレージで、キーワード "redstone" を含む Teams チャット (インスタント メッセージ) を検索します。</span><span class="sxs-lookup"><span data-stu-id="7f085-174">The following example searches for Teams chats (which are instant messages) that contain keyword "redstone" in the cloud-based storage for Sara Davis, who is an on-premises user in the Contoso organization.</span></span>
  
    ```powershell
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND kind:im" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   <span data-ttu-id="7f085-175">検索を作成したら、必ず **Get-compliancesearch** コマンドレットを使用して、検索を実行してください。</span><span class="sxs-lookup"><span data-stu-id="7f085-175">After you create a search, be sure to use the **Start-ComplianceSearch** cmdlet to run the search.</span></span> 
  
<span data-ttu-id="7f085-176">これらのコマンドレットの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f085-176">For more information using these cmdlets, see:</span></span>
  
- [<span data-ttu-id="7f085-177">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="7f085-177">New-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch)

- [<span data-ttu-id="7f085-178">Set-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="7f085-178">Set-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-compliancesearch)

- [<span data-ttu-id="7f085-179">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="7f085-179">Start-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/start-compliancesearch)

## <a name="known-issues"></a><span data-ttu-id="7f085-180">既知の問題</span><span class="sxs-lookup"><span data-stu-id="7f085-180">Known issues</span></span>

- <span data-ttu-id="7f085-181">現在、オンプレミス ユーザーの Teams チャット データを検索、プレビュー、およびエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="7f085-181">Currently, you can search, preview, and export Teams chat data for on-premises users.</span></span> <span data-ttu-id="7f085-182">また、オンプレミス ユーザーの Teams チャット データをコアまたは高度な電子情報開示ケースに関連付けられた状態で保留に設定し、オンプレミス ユーザーの Teams チャットまたはチャネル メッセージに保持ポリシーを適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="7f085-182">You can also place the Teams chat data for an on-premises user on a hold associated with a Core or Advanced eDiscovery case, and apply a retention policy for Teams chats or channel messages for on-premises users.</span></span> <span data-ttu-id="7f085-183">ただし、現時点では、オンプレミス ユーザーの他のコンテンツの場所 (Exchange メールボックスや SharePoint サイトなど) に保持ポリシーを適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="7f085-183">However at this time, you can't apply a retention policy for other content locations (such as Exchange mailboxes and SharePoint sites) for on-premises users.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="7f085-184">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="7f085-184">Frequently asked questions</span></span>

 <span data-ttu-id="7f085-185">**オンプレミス ユーザー向けのクラウドベースのストレージはどこにありますか?**</span><span class="sxs-lookup"><span data-stu-id="7f085-185">**Where is the cloud-based storage for on-premises users located?**</span></span>
  
<span data-ttu-id="7f085-186">クラウドベースのストレージは、組織と同じデータセンターでプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="7f085-186">Cloud-based storage is provisioned in the same datacenter as your organization.</span></span>
  
 <span data-ttu-id="7f085-187">**サポート要求を送信する以外の要件はありますか?**</span><span class="sxs-lookup"><span data-stu-id="7f085-187">**Are there any other requirements other than submitting a support request?**</span></span>
  
 <span data-ttu-id="7f085-188">前に説明したように、オンプレミス メールボックスを持つユーザーの ID は、クラウドベースの組織と同期して、Office 365 の各オンプレミス ユーザー アカウントに対応するメール ユーザー アカウントが作成されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f085-188">As previously explained, the identities of users with on-prem mailboxes must be synchronized to your cloud-based organization so that a corresponding mail user account is created for each on-premises user account in Office 365.</span></span> <span data-ttu-id="7f085-189">また、組織には、Office 365 Enterprise E1、E3、E5 などの Office 365 Enterprise サブスクリプションも必要です。</span><span class="sxs-lookup"><span data-stu-id="7f085-189">Your organization must also have an Office 365 enterprise subscription, such as an Office 365 Enterprise E1, E3, or E5 subscription.</span></span>
  
 <span data-ttu-id="7f085-190">**ユーザーのオンプレミス メールボックスがクラウドに移行された場合、Teams チャット データが失われるリスクはありますか?**</span><span class="sxs-lookup"><span data-stu-id="7f085-190">**Is there a risk of losing the Teams chat data if the user's on-premises mailbox is migrated to the cloud?**</span></span>
  
<span data-ttu-id="7f085-191">いいえ。</span><span class="sxs-lookup"><span data-stu-id="7f085-191">No.</span></span> <span data-ttu-id="7f085-192">オンプレミス ユーザーのプライマリ メールボックスをクラウドに移行すると、そのユーザーの Teams チャット データは、新しいクラウドベースのプライマリ メールボックスに移行されます。</span><span class="sxs-lookup"><span data-stu-id="7f085-192">When you migrate the primary mailbox of an on-premises user to the cloud, the Teams chat data for that user will be migrated to their new cloud-based primary mailbox.</span></span>
  
 <span data-ttu-id="7f085-193">**電子情報開示の保留ポリシーまたはアイテム保持ポリシーをオンプレミス ユーザーに適用することはできますか?**</span><span class="sxs-lookup"><span data-stu-id="7f085-193">**Can I apply an eDiscovery hold or retention policies to on-premises users?**</span></span>
  
<span data-ttu-id="7f085-194">はい。</span><span class="sxs-lookup"><span data-stu-id="7f085-194">Yes.</span></span> <span data-ttu-id="7f085-195">オンプレミス ユーザーの Teams チャットおよびチャネル メッセージに電子情報開示の保留または保持ポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="7f085-195">You can apply eDiscovery holds or retention policies for Teams chats and channel messages of on-premises users.</span></span>
  
 <span data-ttu-id="7f085-196">**この機能を有効にするように組織が要求を送信する前に、コンテンツ検索で、オンプレミス ユーザーの Teams チャット データを検索できますか?**</span><span class="sxs-lookup"><span data-stu-id="7f085-196">**Can Content Search find older Teams chat data for on-premises users before the time my organization submitted the request to enable this feature?**</span></span>
  
<span data-ttu-id="7f085-197">Microsoft は、2018年1月31日にオンプレミス ユーザー向け Teams チャット データの保存を開始しました。</span><span class="sxs-lookup"><span data-stu-id="7f085-197">Microsoft started storing the Teams chat data for on-premises users on January 31, 2018.</span></span> <span data-ttu-id="7f085-198">そのため、オンプレミスの Teams ユーザーの ID が、この日付以降に Active Directory と Azure Active Directory の間で同期されている場合、Teams チャット データはクラウドに保存され、コンテンツ検索を使用して検索できます。</span><span class="sxs-lookup"><span data-stu-id="7f085-198">So, if the identity of an on-premises Teams user has been synched between Active Directory and Azure Active Directory since this date, then their Teams chat data is stored in the cloud and is searchable using Content Search.</span></span> <span data-ttu-id="7f085-199">Microsoft は、2018 年 1 月 31 日より前の Teams チャット データをオンプレミスのストレージに保存する作業も行っています。</span><span class="sxs-lookup"><span data-stu-id="7f085-199">Microsoft is also working on storing Teams chat data from prior to January 31, 2018 in the cloud-based storage for on-premises users.</span></span> <span data-ttu-id="7f085-200">これに関する詳細については、間もなく利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="7f085-200">More information about this will be available soon.</span></span>

 <span data-ttu-id="7f085-201">**オンプレミス ユーザーは、クラウドに Teams チャット データを保存するためにライセンスが必要ですか?**</span><span class="sxs-lookup"><span data-stu-id="7f085-201">**Do on-premises users need a license to store their Teams chat data in the cloud?**</span></span>
  
<span data-ttu-id="7f085-202">はい。</span><span class="sxs-lookup"><span data-stu-id="7f085-202">Yes.</span></span> <span data-ttu-id="7f085-203">クラウドベースのストレージにオンプレミス ユーザーの Teams チャット データを保存するには、そのユーザーに Office 365 (または Microsoft 365) の Microsoft Teams ライセンスと Exchange Online Plan ライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f085-203">To store Teams chat data for an on-premises user in a cloud-based storage, the user must be assigned a Microsoft Teams license and an Exchange Online Plan license in Office 365 (or Microsoft 365).</span></span>
