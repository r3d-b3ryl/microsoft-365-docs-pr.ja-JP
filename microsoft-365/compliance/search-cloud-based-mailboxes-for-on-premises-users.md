---
title: オンプレミス ユーザーのクラウドベース メールボックスの検索
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
description: セキュリティ/コンプライアンス センターのコンテンツ検索ツールを使用して、Exchange ハイブリッド展開のオンプレミス ユーザーが使用している Microsoft Teams チャット データ (1xN チャットと呼ばれます) を検索してエクスポートします。
ms.openlocfilehash: ab523c0d2d334d3d2366711e241b3bafa2e0002f
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352120"
---
# <a name="searching-cloud-based-mailboxes-for-on-premises-users"></a><span data-ttu-id="d3f30-103">オンプレミス ユーザーのクラウドベース メールボックスの検索</span><span class="sxs-lookup"><span data-stu-id="d3f30-103">Searching cloud-based mailboxes for on-premises users</span></span>

<span data-ttu-id="d3f30-104">組織に Exchange ハイブリッド展開がある場合 (または、組織がオンプレミス Exchange 組織を Office 365 と同期している場合)、Microsoft Teams を有効にしている場合、ユーザーは Teams チャット アプリケーションを使用してインスタント メッセージングを利用できます。</span><span class="sxs-lookup"><span data-stu-id="d3f30-104">If your organization has an Exchange hybrid deployment (or your organization synchronizes an on-premises Exchange organization with Office 365) and has enabled Microsoft Teams, users can use the Teams chat application for instant messaging.</span></span> <span data-ttu-id="d3f30-105">クラウドベースのユーザーの場合、Teams チャット データ (*1xN チャット*とも呼ばれます) は、プライマリ クラウドベースのメールボックスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="d3f30-105">For a cloud-based user, the Teams chat data (also called *1xN chats*) is saved to their primary cloud-based mailbox.</span></span> <span data-ttu-id="d3f30-106">オンプレミスのユーザーが Teams チャット アプリケーションを使用する場合、そのユーザーのプライマリ メールボックスはオンプレミスに配置されます。</span><span class="sxs-lookup"><span data-stu-id="d3f30-106">When an on-premises user uses the Team chat application, their primary mailbox is located on-premises.</span></span> <span data-ttu-id="d3f30-107">この制限を回避するために、Microsoft は、オンプレミス ユーザーの Teams チャットデータを格納するために、クラウドベースのストレージ領域 (オンプレミス ユーザーのクラウドベースのメールボックスと呼ばれます) を作成する新機能をリリースしました。</span><span class="sxs-lookup"><span data-stu-id="d3f30-107">To get around this limitation, Microsoft has released a new feature where a cloud-based storage area (called a cloud-based mailbox for on-premises users) is created to store Teams chat data for on-premises users.</span></span> <span data-ttu-id="d3f30-108">これにより、セキュリティ/コンプライアンス センターのコンテンツ検索ツールを使用して、オンプレミス ユーザー向け Teams チャットデータを検索してエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="d3f30-108">This lets you use the Content Search tool in the Security & Compliance Center to search and export Teams chat data for on-premises users.</span></span> 
  
<span data-ttu-id="d3f30-109">オンプレミス ユーザーに対してクラウドベースのメールボックスを設定するための要件と制限について説明します。</span><span class="sxs-lookup"><span data-stu-id="d3f30-109">Here are the requirements and limitations for setting up cloud-based mailboxes for on-premises users:</span></span>
  
- <span data-ttu-id="d3f30-110">オンプレミスのディレクトリ サービス (Active Directory など) のユーザー アカウントは、Microsoft 365 のディレクトリ サービスである Azure Active Directory と同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3f30-110">The user accounts in your on-premises directory service (such as Active Directory) must be synchronized with Azure Active Directory, the directory service in Microsoft 365.</span></span> <span data-ttu-id="d3f30-111">つまり、メール ユーザー アカウントは、Microsoft 365 で作成され、プライマリ メールボックスがオンプレミスの組織に存在するユーザーに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="d3f30-111">This means that a mail user account is created in Microsoft 365 and is associated with a user whose primary mailbox is located in the on-premises organization.</span></span>

- <span data-ttu-id="d3f30-112">プライマリ メールボックスがオンプレミスの組織にあるユーザーには、Microsoft Teams ライセンスと Exchange Online Plan 1 の最小ライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3f30-112">The user whose primary mailbox is located in the on-premises organization must be assigned a Microsoft Teams license and a minimum of an Exchange Online Plan 1 license.</span></span>

- <span data-ttu-id="d3f30-113">オンプレミス ユーザーのクラウドベースのメールボックスには、Teams チャット データのみが保存されます。</span><span class="sxs-lookup"><span data-stu-id="d3f30-113">The cloud-based mailbox for on-premises users is used only store Teams chat data.</span></span> <span data-ttu-id="d3f30-114">オンプレミス ユーザーは、クラウドベースのメールボックスにサインインしたり、何らかの方法でアクセスしたりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d3f30-114">An on-premises user can't sign in to the cloud-based mailbox or access in any way.</span></span> <span data-ttu-id="d3f30-115">メール メッセージの送受信には使用できません。</span><span class="sxs-lookup"><span data-stu-id="d3f30-115">It can't be used to send or receive email messages.</span></span> 

- <span data-ttu-id="d3f30-116">組織がオンプレミス ユーザーに対してクラウドベースのメールボックスで Teams チャット データを検索できるようにするには、Microsoft サポートに要求を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3f30-116">You have to submit a request to Microsoft Support to enable your organization to search for Teams chat data in the cloud-based mailboxes for on-premises users.</span></span> <span data-ttu-id="d3f30-117">この記事の「[Microsoft サポートに要求を送信してこの機能有効にする](#filing-a-request-with-microsoft-support-to-enable-this-feature)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3f30-117">See [Filing a request with Microsoft Support to enable this feature](#filing-a-request-with-microsoft-support-to-enable-this-feature) in this article.</span></span> 

> [!NOTE]
> <span data-ttu-id="d3f30-118">Teams チャネルに含まれる会話は、チームに関連付けられているクラウドベースのメールボックスに常に保存されます。</span><span class="sxs-lookup"><span data-stu-id="d3f30-118">Teams channel conversations are always stored in the cloud-based mailbox that's associated with the Team.</span></span> <span data-ttu-id="d3f30-119">つまり、コンテンツ検索を使用して、サポート要求を提出せずにチャネル会話を検索できます。</span><span class="sxs-lookup"><span data-stu-id="d3f30-119">That means you can use Content Search to search channel conversations without have to file a support request.</span></span> <span data-ttu-id="d3f30-120">Teams チャネルの会話の検索の詳細については、「[Microsoft Teams と Microsoft 365 グループの検索」](content-search.md#searching-microsoft-teams-and-microsoft-365-groups)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3f30-120">For more information about searching Teams channel conversations, see [Searching Microsoft Teams and Microsoft 365 Groups](content-search.md#searching-microsoft-teams-and-microsoft-365-groups).</span></span>
  
## <a name="how-it-works"></a><span data-ttu-id="d3f30-121">動作のしくみ</span><span class="sxs-lookup"><span data-stu-id="d3f30-121">How it works</span></span>

<span data-ttu-id="d3f30-122">Microsoft Teams 対応ユーザーがオンプレミス メールボックスを持ち、ユーザー アカウント/ ID がクラウドに同期されている場合、Microsoft は 1xN Teams チャット データを保存するクラウドベースのメールボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="d3f30-122">If a Microsoft Teams-enabled user has an on-premises mailbox and their user account/identity has been synched to the cloud, Microsoft creates a cloud-based mailbox to store 1xN Teams chat data.</span></span> <span data-ttu-id="d3f30-123">Teams チャット データがクラウドベースのメールボックスに保存されると、検索用にインデックスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d3f30-123">After the Teams chat data is stored in the cloud-based mailbox, it's indexed for search.</span></span> <span data-ttu-id="d3f30-124">これにより、コンテンツ検索 (および電子情報開示ケースに関連付けられている検索) を使用して、オンプレミス ユーザーのために Teams チャット データを検索、プレビュー、エクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="d3f30-124">This lets you Use Content Search (and searches associated with eDiscovery cases) to search, preview, and export Teams chat data for on-premises users.</span></span> <span data-ttu-id="d3f30-125">また、セキュリティ/コンプライアンス センター PowerShell の **\*ComplianceSearch** コマンドレットを使用して、オンプレミス ユーザー向け Teams チャット データを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="d3f30-125">You can also use **\*ComplianceSearch** cmdlets in the Security & Compliance Center PowerShell to search for Teams chat data for on-premises users.</span></span> 
  
<span data-ttu-id="d3f30-126">次の図は、オンプレミス ユーザー向け Teams チャット データの検索、プレビュー、エクスポートを行う方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d3f30-126">The following graphic shows the workflow of how Teams chat data for on-premises users is available to search, preview, and export.</span></span>
  
![Microsoft Teams のオンプレミスユーザー向けのクラウドベース ストレージ](../media/EHAMShard1.png)
  
<span data-ttu-id="d3f30-128">この新しい機能に加えて、コンテンツ検索を使用して、クラウドベースの SharePoint サイトの Teams コンテンツ、各 Microsoft Team に関連付けられた Exchange メールボックス、クラウドベースのユーザーの Exchange Online メールボックスの 1xN Teams チャット データを検索、プレビュー、エクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="d3f30-128">In addition to this new capability, you can still use Content Search to search, preview, and export Teams content in the cloud-based SharePoint site and Exchange mailbox associated with each Microsoft Team and 1xN Teams chat data in the Exchange Online mailbox for cloud-based users.</span></span>

## <a name="filing-a-request-with-microsoft-support-to-enable-this-feature"></a><span data-ttu-id="d3f30-129">Microsoft サポートに要求を送信してこの機能有効にする</span><span class="sxs-lookup"><span data-stu-id="d3f30-129">Filing a request with Microsoft Support to enable this feature</span></span>

<span data-ttu-id="d3f30-130">組織がセキュリティ/コンプライアンス センターのグラフィカル ユーザー インターフェイスを使用して、オンプレミスユーザー向けクラウドベースのメールボックスで Teams チャット データを検索できるようにするには、Microsoft サポートに要求を提出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3f30-130">You must file a request with Microsoft Support to enable your organization to use the graphical user interface in the Security & Compliance Center to search for Teams chat data in the cloud-based mailboxes for on-premises users.</span></span> <span data-ttu-id="d3f30-131">この機能は、セキュリティ/ コンプライアンス センターの PowerShell で使用できます。</span><span class="sxs-lookup"><span data-stu-id="d3f30-131">This feature is available in Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="d3f30-132">PowerShell を使用してオンプレミス ユーザーの Teams チャット データを検索するために、サポート要求を送信する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d3f30-132">You don't have to submit a support request to use PowerShell to search for Teams chat data for on-premises users.</span></span>
  
<span data-ttu-id="d3f30-133">Microsoft サポートに要求を送信するときには、次の情報を含めてください。</span><span class="sxs-lookup"><span data-stu-id="d3f30-133">Include the following information when you submit the request to Microsoft Support:</span></span>
  
- <span data-ttu-id="d3f30-134">組織の既定のドメイン名。</span><span class="sxs-lookup"><span data-stu-id="d3f30-134">The default domain name of your organization.</span></span>

- <span data-ttu-id="d3f30-135">組織のテナント名とテナント ID。</span><span class="sxs-lookup"><span data-stu-id="d3f30-135">The tenant name and tenant ID of your organization.</span></span> <span data-ttu-id="d3f30-136">これらは、Azure Active Directory ポータル (**管理** \> **プロパティ**の下) にあります。</span><span class="sxs-lookup"><span data-stu-id="d3f30-136">You can find these in the Azure Active Directory portal (under **Manage** \> **Properties**).</span></span> <span data-ttu-id="d3f30-137">「[Microsoft 365 テナント ID を見つける](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d3f30-137">See [Find your Microsoft 365 tenant ID](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id).</span></span>

- <span data-ttu-id="d3f30-138">サポート要求の目的に関する次のタイトルまたは説明：「オンプレミス ユーザーのアプリケーション コンテンツ検索を有効にする」。</span><span class="sxs-lookup"><span data-stu-id="d3f30-138">The following title or description of the purpose of the support request: "Enable Application Content Search for On-premises Users".</span></span> <span data-ttu-id="d3f30-139">これにより、要求を実装する電子情報開示エンジニアリング チームが要求をルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="d3f30-139">This helps route the request to the eDiscovery engineering team who will implement the request.</span></span>

<span data-ttu-id="d3f30-140">技術的な変更が行われた後、Microsoft サポートは、展開予定日を送信します。</span><span class="sxs-lookup"><span data-stu-id="d3f30-140">After the engineering change is made, Microsoft Support will send you an estimated deployment date.</span></span> <span data-ttu-id="d3f30-141">通常、サポート要求の送信後、展開プロセスには 2 ~ 3 週間かかります。</span><span class="sxs-lookup"><span data-stu-id="d3f30-141">The deployment process usually takes 2–3 weeks after you submit the support request.</span></span>
  
### <a name="what-happens-after-this-feature-is-enabled"></a><span data-ttu-id="d3f30-142">この機能を有効にするとどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="d3f30-142">What happens after this feature is enabled?</span></span>

<span data-ttu-id="d3f30-143">組織にこの機能が展開されると、コンテンツ検索およびセキュリティ/コンプライアンス センターの電子情報開示ケースに関連付けられた検索で次の変更が行われます。</span><span class="sxs-lookup"><span data-stu-id="d3f30-143">After this feature is deployed in your organization, the following changes are made in Content Search and in searches associated with an eDiscovery case in the Security & Compliance Center:</span></span>
  
- <span data-ttu-id="d3f30-144">[**オンプレミス ユーザー向けの Office アプリ コンテンツの追加**] チェックボックスが、コンテンツ 検索の[**場所**] の下に追加されます。</span><span class="sxs-lookup"><span data-stu-id="d3f30-144">The **Add Office app content for on-premises users** checkbox is added under the **Locations** in Content Search.</span></span>

    ![[オンプレミス ユーザー向けの Office アプリ コンテンツの追加] チェックボックスが、コンテンツ 検索 UI に追加されます。](../media/599e751e-17bd-408d-a18c-127538de6e85.png)
  
- <span data-ttu-id="d3f30-146">オンプレミス ユーザーは、検索するユーザー メールボックスを選択するために使用するコンテンツの場所選択ツールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d3f30-146">On-premises users are displayed in the content locations picker that you use to select user mailboxes to search.</span></span>

## <a name="searching-for-teams-chat-content-in-cloud-based-mailboxes-for-on-premises-users"></a><span data-ttu-id="d3f30-147">オンプレミス ユーザー向けクラウドベース メールボックスで Teams チャット コンテンツを検索する</span><span class="sxs-lookup"><span data-stu-id="d3f30-147">Searching for Teams chat content in cloud-based mailboxes for on-premises users</span></span>

<span data-ttu-id="d3f30-148">この機能を有効にすると、セキュリティ/コンプライアンス センターのコンテンツ検索を使用して、オンプレミス ユーザー向けクラウドベースのメールボックスで Teams チャット データを検索できます。</span><span class="sxs-lookup"><span data-stu-id="d3f30-148">After the feature has been enabled, you can use Content Search in the Security & Compliance Center to search for Teams chat data in the cloud-based mailboxes for on-premises users.</span></span>
  
1. <span data-ttu-id="d3f30-149">セキュリティ/コンプライアンス センターで、[**検索**] \> [**コンテンツ検索**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="d3f30-149">In the Security & Compliance Center, go to **Search** \> **Content search**</span></span>

2. <span data-ttu-id="d3f30-150">[**検索**] ページで、[![追加アイコン](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **新しい検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3f30-150">On the **Search** page, click ![Add icon](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**.</span></span>

    <span data-ttu-id="d3f30-151">前に説明したように、[**オンプレミス ユーザー向けの Office アプリ コンテンツの追加**] チェックボックスが、[**場所**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="d3f30-151">As previously explained, the **Add Office app content for on-premises users** checkbox is displayed under **Locations**.</span></span> <span data-ttu-id="d3f30-152">既定では、オンになっています。</span><span class="sxs-lookup"><span data-stu-id="d3f30-152">It's selected by default.</span></span>

3. <span data-ttu-id="d3f30-153">キーワード クエリを作成し、必要に応じて検索クエリに条件を追加します。</span><span class="sxs-lookup"><span data-stu-id="d3f30-153">Create the keyword query and add conditions to the search query if necessary.</span></span> <span data-ttu-id="d3f30-154">Team チャット データのみを検索するには、[**キーワード]** ボックスに次のクエリを追加します。</span><span class="sxs-lookup"><span data-stu-id="d3f30-154">To only search for Team chats data, you can add the following query in the **Keywords** box:</span></span>

    ```text
    kind:im
    ```

4. <span data-ttu-id="d3f30-155">この時点で、[**場所**] の下で、次のいずれかのオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="d3f30-155">At this point, you can choose one of the following options under **Locations**:</span></span>

    - <span data-ttu-id="d3f30-156">**[すべての場所]:** 組織内のすべてのユーザーのメールボックスを検索するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="d3f30-156">**All locations:** Select this option to search the mailboxes of all users in your organization.</span></span> <span data-ttu-id="d3f30-157">チェックボックスを選択すると、オンプレミス ユーザーのクラウドベースのすべてのメールボックスも検索対象となります。</span><span class="sxs-lookup"><span data-stu-id="d3f30-157">When the checkbox is selected, all cloud-based mailboxes for on-premises users will also be searched.</span></span>

    - <span data-ttu-id="d3f30-158">**特定の場所:** このオプションを選択し、[**変更**\>] をクリックし、ユーザー、グループ、チームを選択して、特定のメールボックスを検索します。</span><span class="sxs-lookup"><span data-stu-id="d3f30-158">**Specific locations:** Select this option and then click **Modify** \> Choose user, groups, or teams to search specific mailboxes.</span></span> <span data-ttu-id="d3f30-159">前に説明したように、場所の選択ツールを使用して、オンプレミス ユーザーを検索できます。</span><span class="sxs-lookup"><span data-stu-id="d3f30-159">As previously explained, the locations picker lets you search for on-premises users.</span></span>

5. <span data-ttu-id="d3f30-160">検索を保存して実行します。</span><span class="sxs-lookup"><span data-stu-id="d3f30-160">Save and run the search.</span></span> <span data-ttu-id="d3f30-161">オンプレミス ユーザー向けクラウドベースのメールボックスからの検索結果は、他の検索結果と同様にプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="d3f30-161">Any search results from the cloud-based mailboxes for on-premises users can be previewed like any other search results.</span></span> <span data-ttu-id="d3f30-162">検索結果 (Teams チャット データを含む) を PST ファイルにエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d3f30-162">You can also export the search results (including any Teams chat data) to a PST file.</span></span> <span data-ttu-id="d3f30-163">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3f30-163">For more information, see:</span></span> 

    - [<span data-ttu-id="d3f30-164">検索を作成する</span><span class="sxs-lookup"><span data-stu-id="d3f30-164">Create a search</span></span>](content-search.md#create-a-search)

    - [<span data-ttu-id="d3f30-165">検索結果をプレビューする</span><span class="sxs-lookup"><span data-stu-id="d3f30-165">Preview search results</span></span>](content-search.md#preview-search-results)

    - [<span data-ttu-id="d3f30-166">コンテンツ検索の結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="d3f30-166">Export Content Search results</span></span>](export-search-results.md)

## <a name="using-powershell-to-search-for-teams-chat-data-in-cloud-based-mailboxes-for-on-premises-users"></a><span data-ttu-id="d3f30-167">PowerShell を使用して、オンプレミス ユーザー向けクラウド ベースのメールボックスで Teams チャット データを検索する</span><span class="sxs-lookup"><span data-stu-id="d3f30-167">Using PowerShell to search for Teams chat data in cloud-based mailboxes for on-premises users</span></span>

<span data-ttu-id="d3f30-168">セキュリティ/コンプライアンス センター PowerShell で、**New-ComplianceSearch** および **Set-ComplianceSearch** コマンドレットを使用して、オンプレミス ユーザー向けクラウドベース メールボックスを検索できます。</span><span class="sxs-lookup"><span data-stu-id="d3f30-168">You can use the **New-ComplianceSearch** and **Set-ComplianceSearch** cmdlets in the Security & Compliance Center PowerShell to search the cloud-based mailbox for on-premises users.</span></span> <span data-ttu-id="d3f30-169">前に説明したように、PowerShell を使用してオンプレミス ユーザーの Teams チャット データを検索するために、サポート要求を送信する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d3f30-169">As previously explained, you don't have to submit a support request to use PowerShell to search for Teams chat data for on-premises users.</span></span> 
  
1. <span data-ttu-id="d3f30-170">[セキュリティ/コンプライアンス センターの PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d3f30-170">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="d3f30-171">次の PowerShell コマンドを実行して、オンプレミスユーザーのクラウドベースのメールボックスを検索するコンテンツ検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="d3f30-171">Run the following PowerShell command to create a content search that searches the cloud-based mailboxes of on-premises users.</span></span>

    ```powershell
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

    <span data-ttu-id="d3f30-172">*IncludeUserAppContent* パラメーターを使用して、*ExchangeLocation* パラメーターで指定されたユーザーのクラウドベースのメールボックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="d3f30-172">The *IncludeUserAppContent*  parameter is used to specify the cloud-based mailbox for the user or users who are specified by the  *ExchangeLocation*  parameter.</span></span> <span data-ttu-id="d3f30-173">*AllowNotFoundExchangeLocationsEnabled* により、オンプレミス ユーザーがクラウドベースのメールボックスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d3f30-173">The  *AllowNotFoundExchangeLocationsEnabled*  allows cloud-based mailboxes for on-premises users.</span></span> <span data-ttu-id="d3f30-174">このパラメーターに `$true` 値を使用すると、検索はメールボックスの存在を検証してから実行されます。</span><span class="sxs-lookup"><span data-stu-id="d3f30-174">When you use the `$true` value for this parameter, the search doesn't try to validate the existence of the mailbox before it runs.</span></span> <span data-ttu-id="d3f30-175">これらの種類のメールボックスは通常のメールボックスとして解決されないため、これはオンプレミ スユーザーのクラウドベースのメールボックスを検索するために必要です。</span><span class="sxs-lookup"><span data-stu-id="d3f30-175">This is required to search the cloud-based mailboxes for on-premises users because these types of mailboxes don't resolve as regular mailboxes.</span></span>

    <span data-ttu-id="d3f30-176">次の例では、Contoso 組織のオンプレミス ユーザーである Sara Davis のクラウドベースのメールボックスで、キーワード "redstone" を含む Teams チャット (インスタント メッセージ) を検索します。</span><span class="sxs-lookup"><span data-stu-id="d3f30-176">The following example searches for Teams chats (which are instant messages) that contain keyword "redstone" in the cloud-based mailbox of Sara Davis, who is an on-premises user in the Contoso organization.</span></span>
  
    ```powershell
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND kind:im" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   <span data-ttu-id="d3f30-177">検索を作成したら、必ず **Get-compliancesearch** コマンドレットを使用して、検索を実行してください。</span><span class="sxs-lookup"><span data-stu-id="d3f30-177">After you create a search, be sure to use the **Start-ComplianceSearch** cmdlet to run the search.</span></span> 
  
<span data-ttu-id="d3f30-178">これらのコマンドレットの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3f30-178">For more information using these cmdlets, see:</span></span>
  
- [<span data-ttu-id="d3f30-179">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="d3f30-179">New-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch)

- [<span data-ttu-id="d3f30-180">Set-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="d3f30-180">Set-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-compliancesearch)

- [<span data-ttu-id="d3f30-181">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="d3f30-181">Start-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/start-compliancesearch)

## <a name="known-issues"></a><span data-ttu-id="d3f30-182">既知の問題</span><span class="sxs-lookup"><span data-stu-id="d3f30-182">Known issues</span></span>

- <span data-ttu-id="d3f30-183">現在、オンプレミス ユーザー向けクラウドベースのメールボックスのコンテンツを検索、プレビュー、エクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="d3f30-183">Currently, you can search, preview, and export content in cloud-based mailboxes for on-premises users.</span></span> <span data-ttu-id="d3f30-184">また、オンプレミス ユーザー向けクラウドベースのメールボックスを電子情報開示ケースに関連付けられた状態で保留にし、オンプレミスユーザー向けクラウドベースのメールボックスに Teams チャットまたはチャネル メッセージの保持ポリシーを適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d3f30-184">You can also place a cloud-based mailbox for an on-premises user on a hold associated with an eDiscovery case, and apply a retention policy for Teams chats or channel messages to cloud-based mailboxes for on-premises users.</span></span> <span data-ttu-id="d3f30-185">ただし、現時点では、他のコンテンツの場所 (Exchange メールボックス、SharePoint サイトなど) の保持ポリシーをオンプレミス ユーザー向けクラウドベースのメールボックスに適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d3f30-185">However at this time, you can't apply a retention policy for other content locations (such as Exchange mailboxes and SharePoint sites) to cloud-based mailboxes for on-premises users.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="d3f30-186">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="d3f30-186">Frequently asked questions</span></span>

 <span data-ttu-id="d3f30-187">**オンプレミスユーザー向けクラウドベースのメールボックスはどこにありますか?**</span><span class="sxs-lookup"><span data-stu-id="d3f30-187">**Where are cloud-based mailboxes for on-premises users located?**</span></span>
  
<span data-ttu-id="d3f30-188">クラウドベースのメールボックスが作成され、組織と同じデータ センターに格納されます。</span><span class="sxs-lookup"><span data-stu-id="d3f30-188">Cloud-based mailboxes are created and stored in the same datacenter as your organization.</span></span>
  
 <span data-ttu-id="d3f30-189">**サポート要求を送信する以外の要件はありますか?**</span><span class="sxs-lookup"><span data-stu-id="d3f30-189">**Are there any other requirements other than submitting a support request?**</span></span>
  
 <span data-ttu-id="d3f30-190">前に説明したように、オンプレミス メールボックスを持つユーザーの ID は、クラウドベースの組織と同期して、Office 365 の各オンプレミス ユーザー アカウントに対応するメール ユーザー アカウントが作成されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3f30-190">As previously explained, the identities of users with on-prem mailboxes must be synchronized to your cloud-based organization so that a corresponding mail user account is created for each on-premises user account in Office 365.</span></span> <span data-ttu-id="d3f30-191">また、組織には、Office 365 Enterprise E1、E3、E5 などの Office 365 Enterprise サブスクリプションも必要です。</span><span class="sxs-lookup"><span data-stu-id="d3f30-191">Your organization must also have an Office 365 enterprise subscription, such as an Office 365 Enterprise E1, E3, or E5 subscription.</span></span>
  
 <span data-ttu-id="d3f30-192">**ユーザーのオンプレミス メールボックスがクラウドに移行された場合、Teams チャット データが失われるリスクはありますか?**</span><span class="sxs-lookup"><span data-stu-id="d3f30-192">**Is there a risk of losing the Teams chat data if the user's on-premises mailbox is migrated to the cloud?**</span></span>
  
<span data-ttu-id="d3f30-193">いいえ。</span><span class="sxs-lookup"><span data-stu-id="d3f30-193">No.</span></span> <span data-ttu-id="d3f30-194">オンプレミス ユーザーのプライマリ メールボックスをクラウドに移行すると、そのユーザーの Teams チャット データは、新しいクラウドベースのプライマリ メールボックスに移行されます。</span><span class="sxs-lookup"><span data-stu-id="d3f30-194">When you migrate the primary mailbox of an on-premises user to the cloud, the Teams chat data for that user will be migrated to their new cloud-based primary mailbox.</span></span>
  
 <span data-ttu-id="d3f30-195">**電子情報開示の保留ポリシーまたはアイテム保持ポリシーをオンプレミス ユーザーに適用することはできますか?**</span><span class="sxs-lookup"><span data-stu-id="d3f30-195">**Can I apply an eDiscovery hold or retention policies to on-premises users?**</span></span>
  
<span data-ttu-id="d3f30-196">はい。</span><span class="sxs-lookup"><span data-stu-id="d3f30-196">Yes.</span></span> <span data-ttu-id="d3f30-197">Teams チャットとチャネル メッセージの電子情報開示保留リストまたは保持ポリシーを、オンプレミス ユーザー向けクラウドベースのメールボックスに適用できます。</span><span class="sxs-lookup"><span data-stu-id="d3f30-197">You can apply eDiscovery holds or retention policies for Teams chats and channel messages to cloud-based mailboxes for on-premises users.</span></span>
  
 <span data-ttu-id="d3f30-198">**この機能を有効にするように組織が要求を送信する前に、コンテンツ検索で、オンプレミスユーザー向けの古い Teams チャットを検索できますか?**</span><span class="sxs-lookup"><span data-stu-id="d3f30-198">**Can Content Search find older Teams chats for on-premises users before the time my organization submitted the request to enable this feature?**</span></span>
  
<span data-ttu-id="d3f30-199">Microsoft は、2018年1月31日にオンプレミスユーザー向け Teams チャット データの保存を開始しました。</span><span class="sxs-lookup"><span data-stu-id="d3f30-199">Microsoft started storing the Teams chat data for on-premises users on January 31, 2018.</span></span> <span data-ttu-id="d3f30-200">そのため、オンプレミスの Teams ユーザーの ID が、この日付以降に Active Directory と Azure Active Directory の間で同期されている場合、Teams チャット データはクラウドベースのメールボックスに保存され、コンテンツ検索を使用して検索できます。</span><span class="sxs-lookup"><span data-stu-id="d3f30-200">So, if the identity of an on-premises Teams user has been synched between Active Directory and Azure Active Directory since this date, then their Teams chat data is stored in a cloud-based mailbox and is searchable using Content Search.</span></span> <span data-ttu-id="d3f30-201">Microsoft は、2018年1月31日より前の Teams チャット データをオンプレミスのメールボックスに保存する作業も行っています。</span><span class="sxs-lookup"><span data-stu-id="d3f30-201">Microsoft is also working on storing Teams chat data from prior to January 31, 2018 in the cloud-based mailboxes for on-premises users.</span></span> <span data-ttu-id="d3f30-202">これに関する詳細については、間もなく利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="d3f30-202">More information about this will be available soon.</span></span>

 <span data-ttu-id="d3f30-203">**オンプレミス ユーザーは、クラウドベース メールボックスに Teams チャット データを保存するためにライセンスが必要ですか?**</span><span class="sxs-lookup"><span data-stu-id="d3f30-203">**Do on-premises users need a license to store Teams chat data in a cloud-based mailbox?**</span></span>
  
<span data-ttu-id="d3f30-204">はい。</span><span class="sxs-lookup"><span data-stu-id="d3f30-204">Yes.</span></span> <span data-ttu-id="d3f30-205">クラウドベースのメールボックスにオンプレミスユーザーの Teams チャット データを保存するには、そのユーザーに Office 365 (または Microsoft 365) の Microsoft Teams ライセンスと Exchange Online Plan ライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3f30-205">To store Teams chat data for an on-premises user in a cloud-based mailbox, the user must be assigned a Microsoft Teams license and an Exchange Online Plan license in Office 365 (or Microsoft 365).</span></span>
