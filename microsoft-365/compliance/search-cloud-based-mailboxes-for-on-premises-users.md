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
description: Microsoft 365 の電子情報開示ツールを使用して、Exchange ハイブリッド環境のオンプレミス ユーザーの Teams チャット データを検索してエクスポートします。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ab59c179b62903dd5f1ddd9b718f81a1ac78923a
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311803"
---
# <a name="search-for-teams-chat-data-for-on-premises-users"></a><span data-ttu-id="9aeb6-103">オンプレミス ユーザーの Teams チャット データを検索する</span><span class="sxs-lookup"><span data-stu-id="9aeb6-103">Search for Teams chat data for on-premises users</span></span>

<span data-ttu-id="9aeb6-104">組織に Exchange ハイブリッド展開がある場合 (または、組織がオンプレミス Exchange 組織を Office 365 と同期している場合)、Microsoft Teams を有効にしている場合、オンプレミス ユーザーは Teams チャット アプリケーションを使用してインスタント メッセージングを利用できます。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-104">If your organization has an Exchange hybrid deployment (or your organization synchronizes an on-premises Exchange organization with Office 365) and has enabled Microsoft Teams, on-premises users can use the Teams chat application for instant messaging.</span></span> <span data-ttu-id="9aeb6-105">クラウドベースのユーザーの場合、Teams チャット データ (*1x1 または 1xN チャット* とも呼ばれます) は、プライマリ クラウドベースのメールボックスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-105">For a cloud-based user, Teams chat data (also called *1x1 or 1xN chats*) is saved to their primary cloud-based mailbox.</span></span> <span data-ttu-id="9aeb6-106">オンプレミス ユーザーが Teams チャット アプリケーションを使用する場合、そのチャット メッセージはオンプレミスにあるプライマリ メールボックスに保存できません。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-106">When an on-premises user uses the Teams chat application, their chat messages can't be stored in their primary mailbox, which is located on-premises.</span></span> <span data-ttu-id="9aeb6-107">この制限を回避するために、Microsoft は、クラウドベースのストレージ領域を作成する新機能をリリースしました。これにより、電子情報開示ツールを使用して、オンプレミス ユーザーの Teams チャット データを検索およびエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-107">To get around this limitation, Microsoft has released a new feature where a cloud-based storage area is created so that you use eDiscovery tools to search for and export Teams chat data for on-premises users.</span></span>
  
<span data-ttu-id="9aeb6-108">オンプレミス ユーザーがクラウドベースのストレージを有効にするための要件と制限は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-108">Here are the requirements and limitations for enabling cloud-based storage for on-premises users:</span></span>
  
- <span data-ttu-id="9aeb6-109">オンプレミスのディレクトリ サービス (Active Directory など) のユーザー アカウントは、Microsoft 365 のディレクトリ サービスである Azure Active Directory と同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-109">The user accounts in your on-premises directory service (such as Active Directory) must be synchronized with Azure Active Directory, the directory service in Microsoft 365.</span></span> <span data-ttu-id="9aeb6-110">つまり、メール ユーザー アカウントは、Microsoft 365 で作成され、プライマリ メールボックスがオンプレミスの組織に存在するユーザーに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-110">This means that a mail user account is created in Microsoft 365 and is associated with a user whose primary mailbox is located in the on-premises organization.</span></span>

- <span data-ttu-id="9aeb6-111">プライマリ メールボックスがオンプレミスの組織にあるユーザーには、Microsoft Teams ライセンスと Exchange Online Plan 1 の最小ライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-111">The user whose primary mailbox is located in the on-premises organization must be assigned a Microsoft Teams license and a minimum of an Exchange Online Plan 1 license.</span></span>

- <span data-ttu-id="9aeb6-112">組織に Exchange ハイブリッド展開がない場合は、オンプレミスの Exchange スキーマを Azure Active Directory に同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-112">If your organization doesn't have an Exchange hybrid deployment, you must synchronize your on-premises Exchange schema to Azure Active Directory.</span></span> <span data-ttu-id="9aeb6-113">これを行わないと、オンプレミスの Exchange 組織にメール ボックスを持つユーザーのために Exchange Online で重複するクラウド ベースのメール ボックスを作成するリスクがあります。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-113">If you don't do this, you might risk creating duplicate cloud-based mailboxes in Exchange Online for users that have a mailbox in your on-premises Exchange organization.</span></span>

- <span data-ttu-id="9aeb6-114">オンプレミス ユーザーに関連付けられた Teams チャット データのみがクラウドベースのストレージ領域に保存されます。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-114">Only the Teams chat data associated with an on-premises user is stored in the cloud-based storage area.</span></span> <span data-ttu-id="9aeb6-115">オンプレミス ユーザーは、このストレージ領域にアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-115">An on-premises user can't access this storage area in any way.</span></span>

> [!NOTE]
> <span data-ttu-id="9aeb6-116">Teams チャネルに含まれる会話は、チームに関連付けられているクラウドベースのメールボックスに常に保存されます。つまり、チャネルの会話を検索できます。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-116">Teams channel conversations are always stored in the cloud-based mailbox that's associated with the Team, which means you can search for channel conversations.</span></span> <span data-ttu-id="9aeb6-117">Teams チャネルの会話の検索の詳細については、「[Microsoft Teams と Microsoft 365 グループの検索」](content-search-reference.md#searching-microsoft-teams-and-microsoft-365-groups)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-117">For more information about searching Teams channel conversations, see [Searching Microsoft Teams and Microsoft 365 Groups](content-search-reference.md#searching-microsoft-teams-and-microsoft-365-groups).</span></span>
  
## <a name="how-it-works"></a><span data-ttu-id="9aeb6-118">メカニズム</span><span class="sxs-lookup"><span data-stu-id="9aeb6-118">How it works</span></span>

<span data-ttu-id="9aeb6-119">Microsoft Teams 対応のユーザーがオンプレミスのメールボックスを持っていて、そのユーザー アカウント/ID がクラウドに同期されている場合、Microsoft は、オンプレミス ユーザーの 1xN Teams チャット データを関連付けるクラウドベースのストレージを作成します。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-119">If a Microsoft Teams-enabled user has an on-premises mailbox and their user account/identity has been synched to the cloud, Microsoft creates cloud-based storage to associate the on-premises user's 1xN Teams chat data with.</span></span> <span data-ttu-id="9aeb6-120">オンプレミス ユーザーの Teams チャット データは、検索用にインデックス化されます。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-120">Teams chat data for on-premises users is indexed for search.</span></span> <span data-ttu-id="9aeb6-121">これにより、コンテンツ検索 (およびコア電子情報開示と Advanced eDiscovery ケースに関連する検索) を使用して、オンプレミス ユーザーの Teams チャット データを検索、プレビュー、エクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-121">This lets you Use Content search (and searches associated with Core eDiscovery and Advanced eDiscovery cases) to search, preview, and export Teams chat data for on-premises users.</span></span> <span data-ttu-id="9aeb6-122">また、セキュリティ/コンプライアンス センター PowerShell の **\*ComplianceSearch** コマンドレットを使用して、オンプレミス ユーザー向け Teams チャット データを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-122">You can also use **\*ComplianceSearch** cmdlets in the Security & Compliance Center PowerShell to search for Teams chat data for on-premises users.</span></span>
  
<span data-ttu-id="9aeb6-123">次の図は、オンプレミス ユーザー向け Teams チャット データの検索、プレビュー、エクスポートを行う方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-123">The following graphic shows the workflow of how Teams chat data for on-premises users is available to search, preview, and export.</span></span>
  
![Microsoft Teams のオンプレミスユーザー向けのクラウドベース ストレージ](../media/EHAMShard1.png)
  
<span data-ttu-id="9aeb6-125">この機能に加えて、電子情報開示ツールを使用して、クラウドベースの SharePoint サイトの Teams コンテンツ、各 Microsoft チームに関連付けられた Exchange メールボックス、クラウドベースのユーザーの Exchange Online メールボックスの 1xN Teams チャット データを検索、プレビュー、エクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-125">In addition to this capability, you can also use eDiscovery tools to search, preview, and export Teams content in the cloud-based SharePoint site and Exchange mailbox associated with each Microsoft Team and 1xN Teams chat data in the Exchange Online mailbox for cloud-based users.</span></span>

### <a name="how-this-feature-is-supported-in-content-search-and-core-ediscovery-search-tools"></a><span data-ttu-id="9aeb6-126">この機能がコンテンツ検索およびコア電子情報開示検索ツールでサポートされるしくみ</span><span class="sxs-lookup"><span data-stu-id="9aeb6-126">How this feature is supported in Content search and Core eDiscovery search tools</span></span>

<span data-ttu-id="9aeb6-127">Microsoft 365 コンプライアンス センターのコア電子情報開示ケースに関連付けられているコンテンツ検索および検索ツールの UI 要素:</span><span class="sxs-lookup"><span data-stu-id="9aeb6-127">The following UI elements in Content search and in the search tool associated with Core eDiscovery cases in the Microsoft 365 compliance center:</span></span>
  
- <span data-ttu-id="9aeb6-128">[**のユーザー用アプリ コンテンツの追加**] チェックボックスは、コンテンツ検索ツールの **Locations** ウィザード ページに表示され、既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-128">The **Add app content for on-premises users** checkbox is displayed on the **Locations** wizard page in Content search tool and selected by default.</span></span> <span data-ttu-id="9aeb6-129">このチェック ボックスをオンにしておくと、コンテンツ検索でオンプレミス ユーザーのクラウド ベースのストレージが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-129">Keep this checkbox selected to include the cloud-based storage for on-premises users in a content search.</span></span>

    ![[オンプレミス ユーザー向けの Office アプリ コンテンツの追加] チェックボックスが、コンテンツ 検索 UI に追加されます。](../media/EHAMShardCheckBox.png)
  
- <span data-ttu-id="9aeb6-131">検索する特定のユーザーを選択すると、オンプレミス ユーザーを検索できます。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-131">You can search for on-premises users when you choose specific users to search for.</span></span>

## <a name="searching-for-teams-chat-content-for-on-premises-users"></a><span data-ttu-id="9aeb6-132">オンプレミス ユーザーの Teams チャット コンテンツの検索</span><span class="sxs-lookup"><span data-stu-id="9aeb6-132">Searching for Teams chat content for on-premises users</span></span>

<span data-ttu-id="9aeb6-133">Microsoft 365 コンプライアンス センターのコンテンツ検索を使用して、オンプレミス ユーザーの Teams チャット データを検索する方法について示します。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-133">Here's how to use Content search in the Microsoft 365 compliance center to search for Teams chat data for on-premises users.</span></span>
  
1. <span data-ttu-id="9aeb6-134">Microsoft 365 コンプライアンス センターで、[**コンテンツ検索**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-134">In the Microsoft 365 compliance center, go to **Content search**.</span></span>

2. <span data-ttu-id="9aeb6-135">[**検索**] タブ、[**新しい 検索**] をクリックし、新しい検索に名前を付えます。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-135">On the **Searches** tab, click **New search**, and name the new search.</span></span>

3. <span data-ttu-id="9aeb6-136">[**場所**] ページで、 Exchange メールボックスのトグルを [**オン**] に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-136">On the **Locations** page, set the toggle to **On** for Exchange mailboxes.</span></span> <span data-ttu-id="9aeb6-137">[**オンプレミス のユーザー アプリ コンテンツを追加する**] チェック ボックスが既定で 表示およびオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-137">Notice that the **Add app content for on-premises users** checkbox is displayed and selected by default.</span></span>

4. <span data-ttu-id="9aeb6-138">特定のユーザーの Teams コンテンツを検索するには、[**ユーザー、グループ、またはチームを選ぶ**] 選択し、検索に含める特定のユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-138">To search for Teams content for specific users, select **Choose user, groups, or teams** and choose specific users to include in the search.</span></span> <span data-ttu-id="9aeb6-139">それ以外の場合は、[**次へ**] クリックして、オンプレミスユーザーを含むすべてのユーザーの Teams コンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-139">Otherwise, click **Next** to search for Teams content for all users, including  on-premises users</span></span>

5. <span data-ttu-id="9aeb6-140">[**検索条件の定義**] ページで、キーワード クエリを作成し、必要に応じて検索クエリに条件を追加します。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-140">On the **Define your search conditions** page, create a keyword query and add conditions to the search query if necessary.</span></span> <span data-ttu-id="9aeb6-141">Team チャット データのみを検索するには、[**キーワード**] ボックスに次のクエリを追加します。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-141">To only search for Team chats data, you can add the following query in the **Keywords** box:</span></span>

    ```text
    kind:im AND kind:microsoftteams
    ```

6. <span data-ttu-id="9aeb6-142">検索を送信して実行します。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-142">Submit and run the search.</span></span> <span data-ttu-id="9aeb6-143">オンプレミス ユーザーの検索結果は、他の検索結果と同様にプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-143">Any search results for on-premises users can be previewed like any other search results.</span></span> <span data-ttu-id="9aeb6-144">検索結果 (Teams チャット データを含む) を PST ファイルにエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-144">You can also export the search results (including any Teams chat data) to a PST file.</span></span> <span data-ttu-id="9aeb6-145">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-145">For more information, see:</span></span>

    - [<span data-ttu-id="9aeb6-146">検索を作成する</span><span class="sxs-lookup"><span data-stu-id="9aeb6-146">Create a search</span></span>](content-search.md)

    - [<span data-ttu-id="9aeb6-147">検索結果をプレビューする</span><span class="sxs-lookup"><span data-stu-id="9aeb6-147">Preview search results</span></span>](preview-ediscovery-search-results.md)

    - [<span data-ttu-id="9aeb6-148">検索結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="9aeb6-148">Export search results</span></span>](export-search-results.md)

## <a name="using-powershell-to-search-for-teams-chat-data-for-on-premises-users"></a><span data-ttu-id="9aeb6-149">PowerShell を使用してオンプレミス ユーザーの Teams チャット データを検索する</span><span class="sxs-lookup"><span data-stu-id="9aeb6-149">Using PowerShell to search for Teams chat data for on-premises users</span></span>

<span data-ttu-id="9aeb6-150">セキュリティ/コンプライアンス センター PowerShell で、**New-ComplianceSearch** および **Set-ComplianceSearch** コマンドレットを使用して、オンプレミス ユーザーの Teams チャット データを検索できます。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-150">You can use the **New-ComplianceSearch** and **Set-ComplianceSearch** cmdlets in the Security & Compliance Center PowerShell to search for Teams chat data for on-premises users.</span></span> <span data-ttu-id="9aeb6-151">前に説明したように、PowerShell を使用してオンプレミス ユーザーの Teams チャット データを検索するために、サポート要求を送信する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-151">As previously explained, you don't have to submit a support request to use PowerShell to search for Teams chat data for on-premises users.</span></span>
  
1. <span data-ttu-id="9aeb6-152">[セキュリティ/コンプライアンス センター PowerShell に接続します](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-152">[Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="9aeb6-153">次の PowerShell コマンドを実行して、オンプレミス ユーザーの Teams チャット データを検索するコンテンツ検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-153">Run the following PowerShell command to create a content search that searches for Teams chat data for on-premises users.</span></span>

    ```powershell
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

    <span data-ttu-id="9aeb6-154">*IncludeUserAppContent* パラメーターを使用して、*ExchangeLocation* パラメーターで指定されたユーザーのクラウドベースのストレージを指定します。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-154">The *IncludeUserAppContent*  parameter is used to specify the cloud-based storage for the user or users who are specified by the  *ExchangeLocation*  parameter.</span></span> <span data-ttu-id="9aeb6-155">*AllowNotFoundExchangeLocationsEnabled* を使用すると、オンプレミス ユーザーのクラウドベースのストレージを検索できます。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-155">The *AllowNotFoundExchangeLocationsEnabled*  allows you to search the cloud-based storage for on-premises users.</span></span> <span data-ttu-id="9aeb6-156">このパラメーターに `$true` 値を使用すると、検索はメールボックスの存在を検証してから実行されます。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-156">When you use the `$true` value for this parameter, the search doesn't try to validate the existence of the mailbox before it runs.</span></span> <span data-ttu-id="9aeb6-157">このクラウドベースのストレージは通常のクラウドベースのメールボックスとして解決されないため、これはオンプレミス ユーザーのクラウドベースのストレージを検索するために必要です。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-157">This is required to search the cloud-based storage for on-premises users because this cloud-based storage doesn't resolve as a regular cloud-based mailbox.</span></span>

    <span data-ttu-id="9aeb6-158">次の例では、Contoso 組織のオンプレミス ユーザーである Sara Davis のクラウドベースのストレージで、キーワード "redstone" を含む Teams チャットを検索します。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-158">The following example searches for Teams chats that contain keyword "redstone" in the cloud-based storage for Sara Davis, who is an on-premises user in the Contoso organization.</span></span>
  
    ```powershell
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND (kind:im AND kind:microsoftteams)" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   <span data-ttu-id="9aeb6-159">検索を作成したら、必ず **Get-compliancesearch** コマンドレットを使用して、検索を実行してください。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-159">After you create a search, be sure to use the **Start-ComplianceSearch** cmdlet to run the search.</span></span>
  
<span data-ttu-id="9aeb6-160">これらのコマンドレットの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-160">For more information using these cmdlets, see:</span></span>
  
- [<span data-ttu-id="9aeb6-161">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="9aeb6-161">New-ComplianceSearch</span></span>](/powershell/module/exchange/new-compliancesearch)

- [<span data-ttu-id="9aeb6-162">Set-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="9aeb6-162">Set-ComplianceSearch</span></span>](/powershell/module/exchange/set-compliancesearch)

- [<span data-ttu-id="9aeb6-163">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="9aeb6-163">Start-ComplianceSearch</span></span>](/powershell/module/exchange/start-compliancesearch)

## <a name="known-issues"></a><span data-ttu-id="9aeb6-164">既知の問題</span><span class="sxs-lookup"><span data-stu-id="9aeb6-164">Known issues</span></span>

- <span data-ttu-id="9aeb6-165">現在、オンプレミス ユーザーの Teams チャット データを検索、プレビュー、およびエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-165">Currently, you can search, preview, and export Teams chat data for on-premises users.</span></span> <span data-ttu-id="9aeb6-166">また、オンプレミス ユーザーの Teams チャット データをコアまたは高度な電子情報開示ケースに関連付けられた状態で保留に設定し、オンプレミス ユーザーの Teams チャットまたはチャネル メッセージに保持ポリシーを適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-166">You can also place the Teams chat data for an on-premises user on a hold associated with a Core or Advanced eDiscovery case, and apply a retention policy for Teams chats or channel messages for on-premises users.</span></span> <span data-ttu-id="9aeb6-167">ただし、現時点では、オンプレミス ユーザーの他のコンテンツの場所 (Exchange メールボックスや SharePoint サイトなど) に保持ポリシーを適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-167">However at this time, you can't apply a retention policy for other content locations (such as Exchange mailboxes and SharePoint sites) for on-premises users.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="9aeb6-168">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="9aeb6-168">Frequently asked questions</span></span>

<span data-ttu-id="9aeb6-169">**オンプレミス ユーザーのチャット メッセージの検索にサポート リクエストを送信する必要がありますか?**</span><span class="sxs-lookup"><span data-stu-id="9aeb6-169">**Do I have to submit a support request to search for chat messages for on-premises users?**</span></span>

<span data-ttu-id="9aeb6-170">いいえ。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-170">No.</span></span> <span data-ttu-id="9aeb6-171">すべての組織で、この機能は既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-171">This feature is enabled by default for all organizations.</span></span> <span data-ttu-id="9aeb6-172">以前は Microsoft サポートに連絡する必要がありましたが、現在は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-172">At one point, you did have to contact Microsoft Support but that is no longer the case.</span></span>
  
 <span data-ttu-id="9aeb6-173">**すべての組織でこの機能が既定で有効になる前の、オンプレミス ユーザーの古い Teams チャット データを、電子情報開示ツールで検索できますか?**</span><span class="sxs-lookup"><span data-stu-id="9aeb6-173">**Can eDiscovery tools find older Teams chat data for on-premises users before the time that this feature was enabled by default for all organizations?**</span></span>
  
<span data-ttu-id="9aeb6-p116">Microsoft では 2018 年 1 月 31 日にオンプレミス ユーザーの Teams チャット データを保存し始めました。オンプレミスの Teams ユーザーの ID が、この日付以降に Microsoft 365 のオンプレミスの Active Directory と Azure Active Directory 間で同期されている場合、Teams チャット データはクラウドに保存され、電子情報開示ツールを使用して検索することができます。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-p116">Microsoft started storing the Teams chat data for on-premises users on January 31, 2018. So, if the identity of an on-premises Teams user has been synched between you on-premises Active Directory and Azure Active Directory in Microsoft 365 since this date, then their Teams chat data is stored in the cloud and is searchable using eDiscovery tools.</span></span>

 <span data-ttu-id="9aeb6-176">**オンプレミス ユーザーは、クラウドに Teams チャット データを保存するためにライセンスが必要ですか?**</span><span class="sxs-lookup"><span data-stu-id="9aeb6-176">**Do on-premises users need a license to store their Teams chat data in the cloud?**</span></span>
  
<span data-ttu-id="9aeb6-p117">必要です。クラウドベースのストレージにオンプレミス ユーザーの Teams チャット データを保存するには、そのユーザーに Office 365 (または Microsoft 365) の Microsoft Teams ライセンスと Exchange Online Plan ライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-p117">Yes. To store Teams chat data for an on-premises user in a cloud-based storage, the user must be assigned a Microsoft Teams license and an Exchange Online Plan license in Office 365 (or Microsoft 365).</span></span>

<span data-ttu-id="9aeb6-179">**オンプレミス ユーザー向けのクラウドベースのストレージはどこにありますか?**</span><span class="sxs-lookup"><span data-stu-id="9aeb6-179">**Where is the cloud-based storage for on-premises users located?**</span></span>
  
<span data-ttu-id="9aeb6-180">Teams のチャット データは、オンプレミスのユーザーのデータの既定の場所 (PDL) に保存されます。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-180">Teams chat data is stored in the Preferred Data Location (PDL) for an on-premises user.</span></span> <span data-ttu-id="9aeb6-181">PDL は、Single-Geo 環境と Multi-Geo 環境の両方で適用されます。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-181">The PDL is honored in both Single-Geo and Multi-Geo environments.</span></span> <span data-ttu-id="9aeb6-182">詳細については、「[Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-182">For more information, see [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span></span>

<span data-ttu-id="9aeb6-183">**ユーザーのオンプレミス メールボックスがクラウドに移行された場合、Teams チャット データが失われるリスクはありますか?**</span><span class="sxs-lookup"><span data-stu-id="9aeb6-183">**Is there a risk of losing the Teams chat data if the user's on-premises mailbox is migrated to the cloud?**</span></span>
  
<span data-ttu-id="9aeb6-p119">ありません。オンプレミス ユーザーのプライマリ メールボックスをクラウドに移行すると、そのユーザーの Teams チャット データは、新しいクラウドベースのプライマリ メールボックスに移行されます。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-p119">No. When you migrate the primary mailbox of an on-premises user to the cloud, the Teams chat data for that user will be migrated to their new cloud-based primary mailbox.</span></span>
  
 <span data-ttu-id="9aeb6-186">**電子情報開示の保留ポリシーまたはアイテム保持ポリシーをオンプレミス ユーザーに適用することはできますか?**</span><span class="sxs-lookup"><span data-stu-id="9aeb6-186">**Can I apply an eDiscovery hold or retention policies to on-premises users?**</span></span>
  
<span data-ttu-id="9aeb6-187">はい。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-187">Yes.</span></span> <span data-ttu-id="9aeb6-188">オンプレミス ユーザーの Teams チャットおよびチャネル メッセージに電子情報開示の保留または保持ポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-188">You can apply eDiscovery holds or retention policies for Teams chats and channel messages of on-premises users.</span></span> <span data-ttu-id="9aeb6-189">ただし、オンプレミス ユーザーの Teams コンテンツを保存または保留するには、Exchange Online のプラン 2 のライセンスをオンプレミス ユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9aeb6-189">However, to preserve or retain Teams content for on-premises users, an on-premises user must be assigned an Exchange Online Plan 2 license.</span></span>
