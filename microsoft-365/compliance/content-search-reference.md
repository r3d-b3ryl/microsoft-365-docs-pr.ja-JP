---
title: コンテンツ検索の機能のリファレンス
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.custom:
- seo-marvel-apr2020
description: この記事には、Microsoft 365 コンプライアンス センターのコンテンツ検索電子情報開示ツールに関する参照情報が含まれており、コンテンツ検索に関する多くの詳細情報を知ることができます。
ms.openlocfilehash: 14660b4cfcd09f5346fa8d0d901880d0a6c774c2
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538485"
---
# <a name="feature-reference-for-content-search"></a><span data-ttu-id="07d85-103">コンテンツ検索の機能のリファレンス</span><span class="sxs-lookup"><span data-stu-id="07d85-103">Feature reference for Content search</span></span>

<span data-ttu-id="07d85-104">この記事では、コンテンツ検索の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="07d85-104">This article describes features and functionality of Content search.</span></span>

## <a name="content-search-limits"></a><span data-ttu-id="07d85-105">コンテンツ検索の制限</span><span class="sxs-lookup"><span data-stu-id="07d85-105">Content search limits</span></span>

<span data-ttu-id="07d85-106">コンテンツ検索に適用される制限については、「[コンテンツ検索の制限](limits-for-content-search.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07d85-106">For a description of the limits that are applied to Content searches, see [Limits for Content search](limits-for-content-search.md).</span></span>
  
## <a name="building-a-search-query"></a><span data-ttu-id="07d85-107">検索クエリの作成</span><span class="sxs-lookup"><span data-stu-id="07d85-107">Building a search query</span></span>

<span data-ttu-id="07d85-108">検索クエリの作成、ブール検索演算子と検索条件の使用、組織外のユーザーと共有する機密情報の種類とコンテンツの検索の詳細については、「[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07d85-108">For detailed information about creating a search query, using Boolean search operators and search conditions, and searching for sensitive information types and content shared with users outside your organization, see [Keyword queries and search conditions for Content Search ](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="07d85-109">キーワード リストを使用して検索クエリを作成する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="07d85-109">Keep the following things in mind when using the keyword list to create a search query.</span></span>
  
- <span data-ttu-id="07d85-110">[**キーワード リストの表示**] チェック ボックスをオンにしてから、キーワードをそれぞれ別の行に入力し、各行のキーワード (またはキーワード フレーズ) が **OR** 演算子でつながれる検索クエリを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07d85-110">You have to select the **Show keyword list** checkbox and then type each keyword in a separate row to create a search query where the keywords (or keyword phrases) in each row are connected by the **OR** operator.</span></span> <span data-ttu-id="07d85-111">キーワード ボックスにキーワードのリストを貼り付けるか、キーワードを入力してから **Enter** キーを押すと、**OR** 演算子でつながれません。</span><span class="sxs-lookup"><span data-stu-id="07d85-111">If you paste a list of keywords in the keyword box or press the **Enter** key after typing a keyword, they won't be connected by the **OR** operator.</span></span> <span data-ttu-id="07d85-112">キーワードのリストを追加する方法の正しくない例と正しい例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="07d85-112">Here are incorrect and correct examples of how to add a list of keywords.</span></span>
    
    <span data-ttu-id="07d85-113">**正しくない例**</span><span class="sxs-lookup"><span data-stu-id="07d85-113">**Incorrect**</span></span>
    
    ![キーワード リストの正しくない書式設定方法 (キーワード ボックスにリストを貼り付ける)](../media/fb54e3df-232a-439a-b3d7-27a60ec76a4c.png)
  
    <span data-ttu-id="07d85-115">**正しい例**</span><span class="sxs-lookup"><span data-stu-id="07d85-115">**Correct**</span></span>
    
    ![キーワード リストの正しい書式設定方法 (チェックボックスをオンにしてからリストを貼り付ける)](../media/5d511a7b-c1f9-499c-bffe-e075bfc9adec.png)
  
- <span data-ttu-id="07d85-117">Excel ファイルまたはテキスト形式ファイルでキーワードまたはキーワード フレーズのリストを準備してから、キーワード リストに自分のリストをコピーして貼り付けることもできます。</span><span class="sxs-lookup"><span data-stu-id="07d85-117">You can also prepare a list of keywords or keyword phrases in an Excel file or a plain text file, and then copy and paste your list into the keyword list.</span></span> <span data-ttu-id="07d85-118">これを行うには、[**キーワード リストの表示**] チェック ボックスをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="07d85-118">To do this, you have to select the **Show keyword list** check box.</span></span> <span data-ttu-id="07d85-119">次に、キーワード リストの最初の行をクリックして、リストを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="07d85-119">Then, click the first row in the keyword list and paste your list.</span></span> <span data-ttu-id="07d85-120">Excel またはテキスト ファイルの行はそれぞれ、キーワード リストの別の行に貼り付けられます。</span><span class="sxs-lookup"><span data-stu-id="07d85-120">Each line from the Excel or text file is pasted into separate row in the keyword list.</span></span> 
    
- <span data-ttu-id="07d85-p103">キーワード リストを使用してクエリを作成したら、検索クエリが意図したものであることを確認することをお勧めします。詳細ウィンドウの **[クエリ]** の下に表示される検索クエリでは、キーワードは **(c:s)** というテキストで区切られます。これは、キーワードが **OR** 演算子と機能的に同様の論理演算子で接続されていることを示します。同様に、検索クエリに条件が含まれている場合、キーワードと条件は **(c:c)** というテキストで区切られます。これは、キーワードが **AND** 演算子と機能的に同様の論理演算子で条件に接続されていることを示します。キーワード リストと条件を使用した場合の結果として (詳細ウィンドウに) 表示される検索クエリの例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="07d85-p103">After you create a query using the keyword list, it's a good idea to verify the search query syntax to make the search query is what you intended. In the search query that's displayed under **Query** in the details pane, the keywords are separated by the text **(c:s)**. This indicates that the keywords are connected by a logical operator similar in functionality to the **OR** operator. Similarly, if your search query includes conditions, the keywords and the conditions are separated by the text **(c:c)**. This indicates that the keywords are connected to the conditions with a logical operator similar in functionality to the **AND** operator. Here's an example of the search query (displayed in the Details pane) that results when using the keyword list and a condition.</span></span> 
    
    ![キーワード リストと条件を使用して作成するクエリの例](../media/b463750c-57fa-4602-9fed-0d5a420db3ad.png)
  
- <span data-ttu-id="07d85-128">コンテンツ検索を実行すると、Microsoft 365 はサポートされていない文字と、大文字にできないブール演算子を検索クエリで自動的にチェックします。</span><span class="sxs-lookup"><span data-stu-id="07d85-128">When you run a content search, Microsoft 365 automatically checks your search query for unsupported characters and for Boolean operators that may not be capitalized.</span></span> <span data-ttu-id="07d85-129">サポートされていない文字は非表示になっていることがよくあり、通常、検索エラーを発生させたり、意図しない結果を返したりする原因になります。</span><span class="sxs-lookup"><span data-stu-id="07d85-129">Unsupported characters are often hidden and typically cause a search error or return unintended results.</span></span> <span data-ttu-id="07d85-130">確認されているサポートされていない文字の詳細については、「[[コンテンツ検索] クエリでエラーを確認する](check-your-content-search-query-for-errors.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07d85-130">For more information about the unsupported characters that are checked, see [Check your Content Search query for errors](check-your-content-search-query-for-errors.md).</span></span>
    
- <span data-ttu-id="07d85-131">英語以外の文字 (中国語の文字など) のキーワードを含む検索クエリがある場合は、[**クエリ言語-国/地域**] ![コンテンツ検索のクエリ言語-国/地域アイコン](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png)をクリックし、言語-国の文化コード値を選択して検索できます。</span><span class="sxs-lookup"><span data-stu-id="07d85-131">If you have a search query that contains keywords for non-English characters (such as Chinese characters), you can click **Query language-country/region**![Query language-country/region icon in Content search](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) and select a language-country culture code value for the search.</span></span> <span data-ttu-id="07d85-132">デフォルトの言語/地域はニュートラルです。</span><span class="sxs-lookup"><span data-stu-id="07d85-132">The default language/region is neutral.</span></span> <span data-ttu-id="07d85-133">コンテンツ検索の言語設定を変更する必要があるかどうかをどのように確認できますか。</span><span class="sxs-lookup"><span data-stu-id="07d85-133">How can you tell if you need to change the language setting for a content search?</span></span> <span data-ttu-id="07d85-134">特定のコンテンツの場所に検索対象の英語以外の文字が含まれているにも関わらず検索で結果が返されない場合は、言語設定が原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="07d85-134">If you're certain content locations contain the non-English characters you're searching for, but the search returns no results, the language setting may be the cause.</span></span>
  
## <a name="partially-indexed-items"></a><span data-ttu-id="07d85-135">部分的にインデックスが作成されたアイテム</span><span class="sxs-lookup"><span data-stu-id="07d85-135">Partially indexed items</span></span>

- <span data-ttu-id="07d85-136">予想される検索結果には、メールボックス内の部分的にインデックスが作成されたアイテムが含まれます。</span><span class="sxs-lookup"><span data-stu-id="07d85-136">Partially indexed items in mailboxes are included in the estimated search results.</span></span> <span data-ttu-id="07d85-137">SharePoint と OneDrive からの部分的にインデックスが作成されたアイテムは、予想される検索結果に含まれません。</span><span class="sxs-lookup"><span data-stu-id="07d85-137">Partially indexed items from SharePoint and OneDrive aren't included in the estimated search results.</span></span> <span data-ttu-id="07d85-138">詳細については、「[電子情報開示で部分的にインデックスが作成されたアイテム](partially-indexed-items-in-content-search.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07d85-138">For more information, see [Partially indexed items in eDiscovery](partially-indexed-items-in-content-search.md).</span></span>

## <a name="searching-onedrive-accounts"></a><span data-ttu-id="07d85-139">OneDrive アカウントの検索</span><span class="sxs-lookup"><span data-stu-id="07d85-139">Searching OneDrive accounts</span></span>

- <span data-ttu-id="07d85-140">組織内の OneDrive サイトの URL のリストを収集するには、「[Create a list of all OneDrive locations in your organization (組織内のすべてのOneDriveロケーションのリストを作成する)](/onedrive/list-onedrive-urls)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07d85-140">To collect a list of the URLs for the OneDrive sites in your organization, see [Create a list of all OneDrive locations in your organization](/onedrive/list-onedrive-urls).</span></span> <span data-ttu-id="07d85-141">この記事内のスクリプトは、すべての OneDrive サイトのリストを含むテキスト ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="07d85-141">This script in this article creates a text file that contains a list of all OneDrive sites.</span></span> <span data-ttu-id="07d85-142">このスクリプトを実行するには、SharePoint Online 管理シェルをインストールして使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07d85-142">To run this script, you have to install and use the SharePoint Online Management Shell.</span></span> <span data-ttu-id="07d85-143">検索する各 OneDrive サイトに組織の個人用サイト ドメインの URL を必ず追加してください。</span><span class="sxs-lookup"><span data-stu-id="07d85-143">Be sure to append the URL for your organization's MySite domain to each OneDrive site that you want to search.</span></span> <span data-ttu-id="07d85-144">これは、すべての OneDrive を含むドメインです。例: `https://contoso-my.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="07d85-144">This is the domain that contains all your OneDrive; for example,  `https://contoso-my.sharepoint.com`.</span></span> <span data-ttu-id="07d85-145">ユーザーの OneDrive サイトの URL の例は次のとおりです。`https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`</span><span class="sxs-lookup"><span data-stu-id="07d85-145">Here's an example of a URL for a user's OneDrive site:  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.</span></span>
    
    <span data-ttu-id="07d85-146">ユーザーのプリンシパル名 (UPN) が変更される稀なケースにおいては、OneDrive の場所のURLが変更され、新しい UPN が組み込まれます。</span><span class="sxs-lookup"><span data-stu-id="07d85-146">In the rare case of a person's user principal name (UPN) being changed, the URL for their OneDrive location is changed to incorporate the new UPN.</span></span> <span data-ttu-id="07d85-147">このような場合は、ユーザーの新しい OneDrive の URL を追加し古い OneDrive の URL を削除して、コンテンツ検索を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07d85-147">If this happens, you have to modify a content search by adding the user's new OneDrive URL and removing the old one.</span></span> <span data-ttu-id="07d85-148">詳細については、「[UPN の変更による OneDrive URL への影響](/onedrive/upn-changes)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="07d85-148">For more information, see [How UPN changes affect the OneDrive URL](/onedrive/upn-changes).</span></span>
  
## <a name="searching-microsoft-teams-and-microsoft-365-groups"></a><span data-ttu-id="07d85-149">Microsoft Teams と Microsoft 365 グループの検索</span><span class="sxs-lookup"><span data-stu-id="07d85-149">Searching Microsoft Teams and Microsoft 365 Groups</span></span>

<span data-ttu-id="07d85-p109">Microsoft Team または Microsoft 365 グループに関連付けられているメールボックスを検索することができます。Microsoft Teams は Microsoft 365 グループ上に構築されているため、検索方法がよく似ています。どちらの場合も、グループまたはチームのメールボックスのみが検索されます。グループ メンバーまたはチーム メンバーのメールボックスは検索されません。検索するには、検索に明示的に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07d85-p109">You can search the mailbox that's associated with a Microsoft Team or Microsoft 365 Group. Because Microsoft Teams is built on Microsoft 365 Groups, searching them is similar. In both cases, only the group or team mailbox is searched. The mailboxes of the group or team members aren't searched. To search them, you have to specifically add them to the search.</span></span>
  
<span data-ttu-id="07d85-155">Microsoft Teams と Microsoft 365 グループのコンテンツを検索する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="07d85-155">Keep the following things in mind when searching for content in Microsoft Teams and Microsoft 365 Groups.</span></span>
  
- <span data-ttu-id="07d85-156">Teams と Microsoft 365 グループにあるコンテンツを検索するには、チームまたはグループに関連付けられているメールボックスと SharePoint サイトを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07d85-156">To search for content located in Teams and Microsoft 365 Groups, you have to specify the mailbox and SharePoint site that are associated with a team or group.</span></span>

- <span data-ttu-id="07d85-157">プライベートチャネルのコンテンツは、チームのメールボックスではなく、ユーザーのメールボックスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="07d85-157">Content from private channels is stored in each user's mailbox, not the team mailbox.</span></span> <span data-ttu-id="07d85-158">プライベートチャネルのコンテンツを検索する方法については、「[プライベートチャネルの電子情報開示](/microsoftteams/ediscovery-investigation#ediscovery-of-private-channels)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07d85-158">To search for content in private channels, see [eDiscovery of private channels](/microsoftteams/ediscovery-investigation#ediscovery-of-private-channels).</span></span>
    
- <span data-ttu-id="07d85-159">チームまたは Microsoft 365 グループのプロパティを表示するには、Exchange Online で **Get-UnifiedGroup** コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="07d85-159">Run the **Get-UnifiedGroup** cmdlet in Exchange Online to view properties for a team or a Microsoft 365 Group.</span></span> <span data-ttu-id="07d85-160">これは、チームまたはグループに関連付けられているサイトの URL を取得するのに適した方法です。</span><span class="sxs-lookup"><span data-stu-id="07d85-160">This is a good way to get the URL for the site that's associated with a team or a group.</span></span> <span data-ttu-id="07d85-161">たとえば、次のコマンドは、上級管理職チームという名前の Microsoft 365 グループの選択されたプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="07d85-161">For example, the following command displays selected properties for a Microsoft 365 Group named Senior Leadership Team:</span></span> 
    
  ```text
  Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
  DisplayName            : Senior Leadership Team
  Alias                  : seniorleadershipteam
  PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
  SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
  ```

    > [!NOTE]
    > <span data-ttu-id="07d85-162">**Get-UnifiedGroup** コマンドレットを実行するには、Exchange Online で View-Only Recipients という役割が割り当てられているか、View-Only Recipients という役割が割り当てられている役割グループに属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="07d85-162">To run the **Get-UnifiedGroup** cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span> 
  
- <span data-ttu-id="07d85-p112">ユーザーのメールボックスを検索すると、ユーザーが属しているチームまたは Microsoft 365 グループは検索されません。同様に、チームまたは Microsoft 365 グループを検索する場合は、指定したグループ メールボックスとグループ サイトのみが検索されます。検索に明示的に追加しない限り、グループ メンバーのメールボックスと OneDrive for Business アカウントは検索されません。</span><span class="sxs-lookup"><span data-stu-id="07d85-p112">When a user's mailbox is searched, any team or Microsoft 365 Group that the user is a member of won't be searched. Similarly, when you search a team or a Microsoft 365 Group, only the group mailbox and group site that you specify is searched. The mailboxes and OneDrive for Business accounts of group members aren't searched unless you explicitly add them to the search.</span></span>

- <span data-ttu-id="07d85-166">チームまたは Microsoft 365 グループのメンバーの一覧を取得するには、Microsoft 365 管理センターの **[ホーム] \> [グループ]** ページでプロパティを表示できます。</span><span class="sxs-lookup"><span data-stu-id="07d85-166">To get a list of the members of a team or a Microsoft 365 Group, you can view the properties on the **Home \> Groups** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="07d85-167">または、Exchange Online PowerShell で次のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="07d85-167">Alternatively, you can run the following command in Exchange Online PowerShell:</span></span> 

  ```powershell
  Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
  ```

    > [!NOTE]
    > <span data-ttu-id="07d85-168">**Get-UnifiedGroupLinks** コマンドレットを実行するには、Exchange Online で View-Only Recipients という役割が割り当てられているか、View-Only Recipients という役割が割り当てられている役割グループに属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="07d85-168">To run the **Get-UnifiedGroupLinks** cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span> 
  
- <span data-ttu-id="07d85-p114">Teams チャネルに含まれる会話は、チームに関連付けられているメールボックスに保存されます。同様に、チャネルでチーム メンバーが共有するファイルはチームの SharePoint サイトに保存されます。そのため、チャネル内の会話とファイルを検索するには、コンテンツの場所としてチーム メールボックスと SharePoint サイトを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07d85-p114">Conversations that are part of a Teams channel are stored in the mailbox that's associated with the team. Similarly, files that team members share in a channel are stored on the team's SharePoint site. Therefore, you have to add the team mailbox and SharePoint site as a content location to search conversations and files in a channel.</span></span>
    
- <span data-ttu-id="07d85-p115">または、Teams のチャット リストに含まれる会話はチャットに参加したユーザーの Exchange Online メールボックスに保存されます。チャットの会話でユーザーが共有するファイルは、ファイルを共有するユーザーの OneDrive for Business アカウントに保存されます。そのため、チャット リストの会話やファイルを検索するには、コンテンツの場所として個々のユーザーのメールボックスと OneDrive for Business アカウントを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07d85-p115">Alternatively, conversations that are part of the Chat list in Teams are stored in the Exchange Online mailbox of the users who participate in the chat. And files that a user shares in Chat conversations are stored in the OneDrive for Business account of the user who shares the file. Therefore, you have to add the individual user mailboxes and OneDrive for Business accounts as content locations to search conversations and files in the Chat list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="07d85-175">Exchange ハイブリッド展開では、オンプレミスのメールボックスを持つユーザーは、Teams のチャット リストの一部である会話に参加する場合があります。</span><span class="sxs-lookup"><span data-stu-id="07d85-175">In an Exchange hybrid deployment, users with an on-premises mailbox might participate in conversations that are part of the Chat list in Teams.</span></span> <span data-ttu-id="07d85-176">この場合も、これらの会話のコンテンツは、オンプレミスのメールボックスを持つユーザーのためにクラウドベースの記憶域 (*オンプレミス ユーザーのクラウドベースのメールボックス* と呼ばれます) に保存されるため、検索可能です。</span><span class="sxs-lookup"><span data-stu-id="07d85-176">In this case, content from these conversations is also searchable because it's saved to a cloud-based storage area (called a *cloud-based mailbox for on-premises users*) for users who have an on-premises mailbox.</span></span> <span data-ttu-id="07d85-177">詳細については、「[PowerShell を使用してオンプレミス ユーザーの Teams チャット データを検索する](search-cloud-based-mailboxes-for-on-premises-users.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07d85-177">For more information, see [Search for Teams chat data for on-premises users](search-cloud-based-mailboxes-for-on-premises-users.md).</span></span>
  
- <span data-ttu-id="07d85-p117">各チームまたは各チーム チャネルには、メモと共同作業用の Wiki が含まれています。Wiki コンテンツは、.mht 形式のファイルに自動的に保存されます。このファイルは、チームの SharePoint サイトの Teams Wiki データ ドキュメント ライブラリに保存されます。検索するコンテンツの場所としてチームの SharePoint サイトを指定すると、コンテンツ検索ツールを使用して Wiki を検索することができます。</span><span class="sxs-lookup"><span data-stu-id="07d85-p117">Every team or team channel contains a Wiki for note-taking and collaboration. The Wiki content is automatically saved to a file with a .mht format. This file is stored in the Teams Wiki Data document library on the team's SharePoint site. You can use the Content Search tool to search the Wiki by specifying the team's SharePoint site as the content location to search.</span></span>

    > [!NOTE]
    > <span data-ttu-id="07d85-p118">Wiki でチームまたはチャネル (チームの SharePoint サイトを検索する場合) を検索する機能は、2017 年 6 月 22 日にリリースされました。その日付以降に保存または更新された Wiki ページは検索できるようになります。その日付より前に保存または更新された Wiki ページは、検索には使用できません。</span><span class="sxs-lookup"><span data-stu-id="07d85-p118">The capability to search the Wiki for a team or channel (when you search the team's SharePoint site) was released on June 22, 2017. Wiki pages that were saved or updated on that date or after are available to be searched. Wiki pages last saved or updated before that date aren't available for search.</span></span>

- <span data-ttu-id="07d85-p119">Teams チャネルでの会議と通話の概要情報は、会議または通話にダイヤルしたユーザーのメールボックスにも保存されます。つまり、コンテンツ検索を使用してこれらの概要レコードを検索することができます。概要情報は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="07d85-p119">Summary information for meetings and calls in a Teams channel are also stored in the mailboxes of users who dialed into the meeting or call. This means you can use Content Search to search these summary records. Summary information includes:</span></span>
  
  - <span data-ttu-id="07d85-188">会議または通話の日付、開始時刻、終了時刻、および継続時間</span><span class="sxs-lookup"><span data-stu-id="07d85-188">Date, start time, end time, and duration of a meeting or call</span></span>

  - <span data-ttu-id="07d85-189">各参加者の会議または通話の参加日時と退出日時</span><span class="sxs-lookup"><span data-stu-id="07d85-189">The date and time when each participant joined or left the meeting or call</span></span>

  - <span data-ttu-id="07d85-190">ボイスメールに送信された通話</span><span class="sxs-lookup"><span data-stu-id="07d85-190">Calls sent to voice mail</span></span>

  - <span data-ttu-id="07d85-191">不在着信</span><span class="sxs-lookup"><span data-stu-id="07d85-191">Missed or unanswered calls</span></span>

  - <span data-ttu-id="07d85-192">2 つの個別の通話として表される呼び出し転送</span><span class="sxs-lookup"><span data-stu-id="07d85-192">Call transfers, which are represented as two separate calls</span></span>

  <span data-ttu-id="07d85-193">会議と通話の概要レコードが検索できるようになるまで最大 8 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="07d85-193">It can take up to 8 hours for meeting and call summary records to be available to be searched.</span></span>

  <span data-ttu-id="07d85-194">検索結果では、会議の概要は "**種類**" フィールドで [**会議**] として識別されます。通話の概要は [**通話**] として識別されます。</span><span class="sxs-lookup"><span data-stu-id="07d85-194">In the search results, meeting summaries are identified as **Meeting** in the **Type field**, and call summaries are identified as **Call**.</span></span> <span data-ttu-id="07d85-195">また、Teams チャネルと 1xN チャットに含まれる会話は、"**種類**" フィールドで [**IM**] として識別されます。</span><span class="sxs-lookup"><span data-stu-id="07d85-195">Also, conversations that are part of a Teams channel and 1xN chats are identified as **IM** in the **Type** field.</span></span>
  
  ![Teams の会議、通話および 1xN チャットは "種類" フィールドで識別されます。](../media/O365-ContentSearch-Teams-MessageKind.png)

   <span data-ttu-id="07d85-197">詳細については、[Microsoft Teams が開始した通話と会議の電子情報開示](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-launches-ediscovery-for-calling-and-meetings/ba-p/210947)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07d85-197">For more information, see [Microsoft Teams launches eDiscovery for calls and meetings](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-launches-ediscovery-for-calling-and-meetings/ba-p/210947).</span></span>

- <span data-ttu-id="07d85-198">Teams チャネルのアプリ、1:1 チャット、1xN チャットで生成されたカード コンテンツは、メールボックスに保存され、検索することができます。</span><span class="sxs-lookup"><span data-stu-id="07d85-198">Card content generated by apps in Teams channels, 1:1 chats, and 1xN chats is stored in mailboxes and can be searched.</span></span> <span data-ttu-id="07d85-199">*カード* とは、短いコンテンツを対象とした UI コンテナです。</span><span class="sxs-lookup"><span data-stu-id="07d85-199">A *card* is a UI container for short pieces of content.</span></span> <span data-ttu-id="07d85-200">カードには複数のプロパティと添付ファイル、およびカード アクションをトリガーするボタンを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="07d85-200">Cards can have multiple properties and attachments, and can include buttons that can trigger card actions.</span></span> <span data-ttu-id="07d85-201">詳細については、「[カード](/microsoftteams/platform/task-modules-and-cards/what-are-cards)」を参照してください</span><span class="sxs-lookup"><span data-stu-id="07d85-201">For more information, see [Cards](/microsoftteams/platform/task-modules-and-cards/what-are-cards)</span></span>

  <span data-ttu-id="07d85-202">他の Teams のコンテンツと同様に、カードのコンテンツが保存されている場所は、カードが使用された場所に基づいています。</span><span class="sxs-lookup"><span data-stu-id="07d85-202">Like other Teams content, where card content is stored is based on where the card was used.</span></span> <span data-ttu-id="07d85-203">Teams チャネルで使用したカードのコンテンツは、Teams グループのメールボックスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="07d85-203">Content for cards used in a Teams channel is stored in the Teams group mailbox.</span></span> <span data-ttu-id="07d85-204">1:1 チャットおよび 1xN チャットのカード コンテンツは、チャット参加者のメールボックスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="07d85-204">Card content for 1:1 and 1xN chats are stored in the mailboxes of the chat participants.</span></span>

  <span data-ttu-id="07d85-205">カード コンテンツの検索には、検索条件として `kind:microsoftteams` または `itemclass:IPM.SkypeTeams.Message` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="07d85-205">To search for card content, you can use the `kind:microsoftteams` or `itemclass:IPM.SkypeTeams.Message` search conditions.</span></span> <span data-ttu-id="07d85-206">検索結果をレビューする場合、Teams チャネルのボットによって生成されたカード コンテンツは `<appname>@teams.microsoft.com` として **送信者/作成者** のメール プロパティを持ち、`appname` はカード コンテンツを生成したアプリの名前です。</span><span class="sxs-lookup"><span data-stu-id="07d85-206">When reviewing search results, card content generated by bots in a Teams channel have the **Sender/Author** email property as `<appname>@teams.microsoft.com`, where `appname` is the name of the app that generated the card content.</span></span> <span data-ttu-id="07d85-207">カード コンテンツがユーザーによって生成された場合、**送信者/作成者** の値がユーザーを識別します。</span><span class="sxs-lookup"><span data-stu-id="07d85-207">If card content was generated by a user, the value of **Sender/Author** identifies the user.</span></span>

  <span data-ttu-id="07d85-208">コンテンツの検索結果でカード コンテンツを表示すると、そのコンテンツはメッセージの添付ファイルとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="07d85-208">When viewing card content in Content search results, the content appears as an attachment to the message.</span></span> <span data-ttu-id="07d85-209">添付ファイルには `appname.html` と名付けられ、`appname` はカード コンテンツを生成したアプリの名前です。</span><span class="sxs-lookup"><span data-stu-id="07d85-209">The attachment is named `appname.html`, where `appname` is the name of the app that generated the card content.</span></span> <span data-ttu-id="07d85-210">次のスクリーンショットは、カード コンテンツ (Asana という名前のアプリが対象) が Teams や検索結果でどのように表示されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="07d85-210">The following screenshots show how card content (for an app named Asana) appears in Teams and in the results of a search.</span></span>

  <span data-ttu-id="07d85-211">**Teams でのカード コンテンツ**</span><span class="sxs-lookup"><span data-stu-id="07d85-211">**Card content in Teams**</span></span>

  ![Teams チャネル メッセージでのカード コンテンツ](../media/CardContentTeams.png)

  <span data-ttu-id="07d85-213">**検索結果でのカード コンテンツ**</span><span class="sxs-lookup"><span data-stu-id="07d85-213">**Card content in search results**</span></span>
  
  ![コンテンツ検索の結果での同じカード コンテンツ](../media/CardContentEdiscoverySearchResults.png)

  > [!NOTE]
  > <span data-ttu-id="07d85-215">現時点でカード コンテンツの画像を検索結果に表示するには (前のスクリーンショット内のチェックマークなど)、検索結果を表示するために使用する同一のブラウザー セッション内で、別のタブを使用して Teams (https://teams.microsoft.com) にサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="07d85-215">To display images from card content in search results at this time (such as the checkmarks in the previous screenshot), you have to be signed into Teams (at https://teams.microsoft.com) in a different tab in the same browser session that you use to view the search results.</span></span> <span data-ttu-id="07d85-216">それ以外の場合には、画像のプレースホルダーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="07d85-216">Otherwise, image placeholders are displayed.</span></span>

- <span data-ttu-id="07d85-217">"**Kind**" 電子メール プロパティまたは "**メッセージの種類**" 検索条件を使用すると、Teams のコンテンツのみを検索できます。</span><span class="sxs-lookup"><span data-stu-id="07d85-217">You can use the **Kind** email property or the **Message kind** search condition to search specifically for content in Teams.</span></span>
  
  - <span data-ttu-id="07d85-218">キーワード検索クエリの一部として **Kind** プロパティを使用するには、検索クエリの **[キーワード]** ボックスに `kind:microsoftteams` と入力します。</span><span class="sxs-lookup"><span data-stu-id="07d85-218">To use the **Kind** property as part of the keyword search query, in the **Keywords** box of a search query, type `kind:microsoftteams`.</span></span>

    ![[キーワード] ボックスで kind:microsoftteams を使用する](../media/O365-ContentSearch-Teams-Keywords.png)
  
  - <span data-ttu-id="07d85-220">検索条件を使用するには、**[メッセージの種類]** 条件を追加し、値 `microsoftteams` を使用します。</span><span class="sxs-lookup"><span data-stu-id="07d85-220">To use a search condition, add the **Message kind** condition and use the value `microsoftteams`.</span></span>

    ![値 microsoftteams で [メッセージの種類] 条件を使用します。](../media/O365-ContentSearch-Teams-MessageKindCondition.png)

   <span data-ttu-id="07d85-222">条件は **AND** 演算子によってキーワード クエリに論理的に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="07d85-222">Conditions are logically connected to the keyword query by the **AND** operator.</span></span> <span data-ttu-id="07d85-223">つまり、アイテムは検索結果として返されるためにキーワード クエリと検索条件の両方に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07d85-223">That means an item must match both the keyword query and the search condition to be returned in the search results.</span></span> <span data-ttu-id="07d85-224">詳細については、「[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions)」の "条件を使用するためのガイドライン" セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="07d85-224">For more information, see the "Guidelines for using conditions" section in [Keyword queries and search conditions for Content Search.](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions)</span></span>
  
## <a name="searching-yammer-groups"></a><span data-ttu-id="07d85-225">Yammer グループの検索</span><span class="sxs-lookup"><span data-stu-id="07d85-225">Searching Yammer Groups</span></span>

<span data-ttu-id="07d85-226">**ItemClass** メール プロパティまたは **[タイプ]** 検索条件を使用して、Yammer グループの会話アイテムを具体的に検索できます。</span><span class="sxs-lookup"><span data-stu-id="07d85-226">You can use the **ItemClass** email property or the **Type** search condition to search specifically for conversation items in Yammer Groups.</span></span>

  - <span data-ttu-id="07d85-227">キーワード検索クエリの一部として **ItemClass** プロパティを使用するには、検索クエリの **[キーワード]** ボックスで、次のいずれか (またはすべて) の property:value のペアを入力します。</span><span class="sxs-lookup"><span data-stu-id="07d85-227">To use the **ItemClass** property as part of the keyword search query, in the **Keywords** box of a search query, you can type one (or all) of the following property:value pairs:</span></span>

     - <span data-ttu-id="07d85-228">ItemClass:IPM.Yammer.message</span><span class="sxs-lookup"><span data-stu-id="07d85-228">ItemClass:IPM.Yammer.message</span></span>
     - <span data-ttu-id="07d85-229">ItemClass:IPM.Yammer.poll</span><span class="sxs-lookup"><span data-stu-id="07d85-229">ItemClass:IPM.Yammer.poll</span></span>
     - <span data-ttu-id="07d85-230">ItemClass:IPM.Yammer.praise</span><span class="sxs-lookup"><span data-stu-id="07d85-230">ItemClass:IPM.Yammer.praise</span></span>
     - <span data-ttu-id="07d85-231">ItemClass:IPM.Yammer.question</span><span class="sxs-lookup"><span data-stu-id="07d85-231">ItemClass:IPM.Yammer.question</span></span>
  
    <span data-ttu-id="07d85-232">たとえば、次の検索クエリを使用して、Yammer のメッセージと Yammer の称賛アイテムを取得できます。</span><span class="sxs-lookup"><span data-stu-id="07d85-232">For example, you can use the following search query to return Yammer messages and Yammer praise items:</span></span>

    ![ItemClass プロパティを使用して、Yammer アイテムを検索する](../media/YammerContentSearch1.png)
  
  - <span data-ttu-id="07d85-234">または、**[タイプ]** メール条件を使用し、**[Yammer メッセージ]** を選択して、Yammer アイテムを返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="07d85-234">Alternatively, you can use the **Type** email condition and select **Yammer messages** to return Yammer items.</span></span> <span data-ttu-id="07d85-235">たとえば、次の検索クエリでは、"社外秘" キーワードを含むすべての Yammer の会話アイテムが返されます。</span><span class="sxs-lookup"><span data-stu-id="07d85-235">For example, the following search query will return all Yammer conversation items that contain the keyword "confidential".</span></span> 

    ![[タイプ] 条件カードを使用して Yammer の会話アイテムを検索する](../media/YammerContentSearch2.png)

## <a name="searching-inactive-mailboxes"></a><span data-ttu-id="07d85-237">非アクティブなメールボックスの検索</span><span class="sxs-lookup"><span data-stu-id="07d85-237">Searching inactive mailboxes</span></span>

<span data-ttu-id="07d85-238">コンテンツ検索で非アクティブなメールボックスを検索できます。</span><span class="sxs-lookup"><span data-stu-id="07d85-238">You can search inactive mailboxes in a content search.</span></span> <span data-ttu-id="07d85-239">組織内の非アクティブなメールボックスのリストを取得するには、Exchange Online PowerShell でコマンド `Get-Mailbox -InactiveMailboxOnly` を実行します。</span><span class="sxs-lookup"><span data-stu-id="07d85-239">To get a list of the inactive mailboxes in your organization, run the command  `Get-Mailbox -InactiveMailboxOnly` in Exchange Online PowerShell.</span></span> <span data-ttu-id="07d85-240">または、セキュリティ/コンプライアンス センターの [**情報ガバナンス**] \> [**保持**] に移動して、[**詳細**] ![ナビゲーション バーの省略記号](../media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \> [**非アクティブなメールボックス**] をクリックすることもできます。</span><span class="sxs-lookup"><span data-stu-id="07d85-240">Alternatively, you can go to **Information governance** \> **Retention** in the Security & Compliance Center, and then click **More**![Navigation Bar ellipses](../media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \> **Inactive mailboxes**.</span></span>
  
<span data-ttu-id="07d85-241">非アクティブなメールボックスを検索するときの留意点を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="07d85-241">Here are a few things to keep in mind when searching inactive mailboxes.</span></span>

- <span data-ttu-id="07d85-242">既存のコンテンツ検索にユーザー メールボックスが含まれ、そのメールボックスが非アクティブになった場合、非アクティブになった後に検索を再実行すると、コンテンツ検索は非アクティブなメールボックスの検索を続行します。</span><span class="sxs-lookup"><span data-stu-id="07d85-242">If an existing content search includes a user mailbox and that mailbox is made inactive, the content search will continue to search the inactive mailbox when you rerun the search after it becomes inactive.</span></span>

- <span data-ttu-id="07d85-p129">場合によっては、ユーザーは同じ SMTP アドレスを持つアクティブなメールボックスおよび非アクティブなメールボックスを所有している可能性があります。この場合、コンテンツ検索の場所として選択した特定のメールボックスのみが検索されます。つまり、検索にユーザーのメールボックスを追加する場合に、アクティブなメールボックスと非アクティブなメールボックスの両方が検索されることは想定できません。検索に明示的に追加したメールボックスのみが検索されます。</span><span class="sxs-lookup"><span data-stu-id="07d85-p129">Sometimes a user may have an active mailbox and an inactive mailbox that have the same SMTP address. In this case, only the specific mailbox that you select as a location for a content search is searched. In other words, if you add a user's mailbox to a search, you can't assume that both their active and inactive mailboxes are searched. Only the mailbox that you explicitly add to the search is searched.</span></span>

- <span data-ttu-id="07d85-247">Security＆Compliance Center PowerShell を使用してコンテンツ検索を作成し、非アクティブなメールボックスを検索できます。</span><span class="sxs-lookup"><span data-stu-id="07d85-247">You can use Security & Compliance Center PowerShell to create a content search to search an inactive mailbox.</span></span> <span data-ttu-id="07d85-248">これを行うには、ピリオド (.) を事前に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07d85-248">To do this, you have to pre-append a period ( .</span></span> <span data-ttu-id="07d85-249">非アクティブなメールボックスのメール アドレスに。</span><span class="sxs-lookup"><span data-stu-id="07d85-249">) to the email address of the inactive mailbox.</span></span> <span data-ttu-id="07d85-250">たとえば次のコマンドは、メール アドレス pavelb@contoso.onmicrosoft.com を含む非アクティブなメールボックスを検索するコンテンツ検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="07d85-250">For example, the following command creates a content search that searches an inactive mailbox with the email address pavelb@contoso.onmicrosoft.com:</span></span>

   ```powershell
   New-ComplianceSearch -Name InactiveMailboxSearch -ExchangeLocation .pavelb@contoso.onmicrosoft.com -AllowNotFoundExchangeLocationsEnabled $true
   ```

- <span data-ttu-id="07d85-p131">同じ SMTP アドレスを持つアクティブなメールボックスと非アクティブなメールボックスを所有しないようにすることを強くお勧めします。非アクティブなメールボックスに割り当てられている SMTP アドレスを再使用する場合は、非アクティブなメールボックスを復元するか、非アクティブなメールボックスのコンテンツをアクティブなメールボックス (またはアクティブなメールボックスのアーカイブ) に復元して、非アクティブなメールボックスを削除することをお勧めします。詳細については、以下のいずれかのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="07d85-p131">We strongly recommend that you avoid having an active mailbox and inactive mailbox with the same SMTP address. If you need to reuse the SMTP address that is assigned to an inactive mailbox, we recommend that you recover the inactive mailbox or restore the contents of an inactive mailbox to an active mailbox (or the archive of an active mailbox), and then delete the inactive mailbox. For more information, see one of the following topics:</span></span>

  - [<span data-ttu-id="07d85-254">Office 365 で非アクティブなメールボックスを回復する</span><span class="sxs-lookup"><span data-stu-id="07d85-254">Recover an inactive mailbox in Office 365</span></span>](recover-an-inactive-mailbox.md)

  - [<span data-ttu-id="07d85-255">Office 365 の非アクティブなメールボックスを復元する</span><span class="sxs-lookup"><span data-stu-id="07d85-255">Restore an inactive mailbox in Office 365</span></span>](restore-an-inactive-mailbox.md)

  - [<span data-ttu-id="07d85-256">Office 365 の非アクティブなメールボックスを削除する</span><span class="sxs-lookup"><span data-stu-id="07d85-256">Delete an inactive mailbox in Office 365</span></span>](delete-an-inactive-mailbox.md)

## <a name="searching-disconnected-or-de-licensed-mailboxes"></a><span data-ttu-id="07d85-257">切断された、またはライセンスを解除されたメールボックスを検索する</span><span class="sxs-lookup"><span data-stu-id="07d85-257">Searching disconnected or de-licensed mailboxes</span></span>

<span data-ttu-id="07d85-258">Exchange Online ライセンス (または Microsoft 365 ライセンス全体) がユーザー アカウントまたは Azure Active Directory から削除されると、ユーザーのメールボックスは *切断された* メールボックスになります。</span><span class="sxs-lookup"><span data-stu-id="07d85-258">If the Exchange Online license (or the entire Microsoft 365 license) is removed from a user account or in Azure Active Directory, the user's mailbox becomes a *disconnected* mailbox.</span></span> <span data-ttu-id="07d85-259">これは、このメールボックスがユーザー アカウントに関連付けられていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="07d85-259">This means that the mailbox is no longer associated with the user account.</span></span> <span data-ttu-id="07d85-260">切断されたメールボックスを検索すると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="07d85-260">Here's what happens when searching disconnected mailboxes:</span></span>

- <span data-ttu-id="07d85-261">ライセンスがメールボックスから削除されている場合は、メールボックスを検索できなくなります。</span><span class="sxs-lookup"><span data-stu-id="07d85-261">If the license is removed from a mailbox, the mailbox is no longer searchable.</span></span> 

- <span data-ttu-id="07d85-262">既存のコンテンツ検索にライセンスが削除されたメールボックスが含まれている場合は、コンテンツ検索を再実行すると切断されたメールボックスの検索結果が一切返されなくなります。</span><span class="sxs-lookup"><span data-stu-id="07d85-262">If an existing content search includes a mailbox in which the license is removed, no search results from the disconnected mailbox will be returned if you rerun the content search.</span></span>

- <span data-ttu-id="07d85-263">検索するための Exchange コンテンツの場所として、コンテンツ検索を作成して切断されたメールボックスを指定するのに **New-ComplianceSearch** コマンドレットを使用する場合は、コンテンツ検索からは切断されたメールボックスの検索結果が一切返されません。</span><span class="sxs-lookup"><span data-stu-id="07d85-263">If you use the **New-ComplianceSearch** cmdlet to create a content search and specify a disconnected mailbox as the Exchange content location to search, the content search won't return any search results from the disconnected mailbox.</span></span>

<span data-ttu-id="07d85-264">検索できるように切断されたメールボックスにデータを保持する必要がある場合は、ライセンスを削除する前に、メールボックスに保留を適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07d85-264">If you need to preserve the data in a disconnected mailbox so that it's searchable, you must place a hold on the mailbox before removing the license.</span></span> <span data-ttu-id="07d85-265">これによりデータが保持され、保留が削除されるまで、切断されたメールボックスを検索できます。</span><span class="sxs-lookup"><span data-stu-id="07d85-265">This preserves the data and keeps the disconnected mailbox searchable until the hold is removed.</span></span> <span data-ttu-id="07d85-266">保留に関する詳細情報については、[Exchange Online メールボックスに適用されている保留の種類を特定する方法](identify-a-hold-on-an-exchange-online-mailbox.md)をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="07d85-266">For more information about holds, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

## <a name="searching-for-content-in-a-sharepoint-multi-geo-environment"></a><span data-ttu-id="07d85-267">SharePoint Multi-Geo 環境のコンテンツを検索する</span><span class="sxs-lookup"><span data-stu-id="07d85-267">Searching for content in a SharePoint Multi-Geo environment</span></span>

<span data-ttu-id="07d85-268">電子情報開示マネージャーが、[SharePoint Multi-Geo 環境](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)内の複数の地域の SharePoint および OneDrive でコンテンツを検索する必要がある場合、これを実行できるようにするには次の操作を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07d85-268">If it's necessary for an eDiscovery manager to search for content in SharePoint and OneDrive in different regions in a [SharePoint multi-geo environment](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md), then you need to do the following things to make that happen:</span></span>

1. <span data-ttu-id="07d85-269">電子情報開示マネージャーが検索する必要があるサテライト地域の場所ごとに、個別のユーザー アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="07d85-269">Create a separate user account for each satellite geo location that the eDiscovery manager needs to search.</span></span> <span data-ttu-id="07d85-270">その地域の場所にあるサイトのコンテンツを検索するには、電子情報開示マネージャーは、その場所用に作成されたアカウントにサインインしてからコンテンツ検索を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07d85-270">To search for content in sites in that geo location, the eDiscovery manager must sign in to the account you created for that location and then run a content search.</span></span>

2. <span data-ttu-id="07d85-271">電子情報開示マネージャーが検索する必要がある各サテライトの地理的位置 (および対応するユーザー アカウント) 用に、検索のアクセス許可フィルターを作成します。</span><span class="sxs-lookup"><span data-stu-id="07d85-271">Create a search permissions filter for each satellite geo location (and corresponding user account) the eDiscovery manager needs to search.</span></span> <span data-ttu-id="07d85-272">それぞれの検索のアクセス許可フィルターにより、特定の場所と関連付けられているユーザー アカウントに電子情報開示マネージャーがサインインした際に、コンテンツ検索の対象がその地理的位置に限定されます。</span><span class="sxs-lookup"><span data-stu-id="07d85-272">Each of these search permissions filters limits the scope of the content search to a specific geo location when the eDiscovery manager is signed in to the user account associated with that location.</span></span>

> [!TIP]
> <span data-ttu-id="07d85-273">[Advanced eDiscovery](overview-ediscovery-20.md) の検索ツールを使用する場合はこの方法を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="07d85-273">You don't have to use this strategy when using the search tool in [Advanced eDiscovery](overview-ediscovery-20.md).</span></span> <span data-ttu-id="07d85-274">これは、Advanced eDiscovery で SharePoint サイトと OneDrive アカウントを検索すると、すべてのデータセンターが検索されるためです。</span><span class="sxs-lookup"><span data-stu-id="07d85-274">That's because all datacenters are searched when you search SharePoint sites and OneDrive accounts in Advanced eDiscovery.</span></span> <span data-ttu-id="07d85-275">地域限定のユーザー アカウントと検索のアクセス許可フィルターを使用するこの方法を使用する必要があるのは、コンテンツ検索ツールを使用して[電子情報開示のケース](./get-started-core-ediscovery.md)と関連付けられている検索を実行する場合のみです。</span><span class="sxs-lookup"><span data-stu-id="07d85-275">You have to use this strategy of region-specific user accounts and search permissions filters only when using the Content Search tool and running searches associated with [eDiscovery cases](./get-started-core-ediscovery.md).</span></span>

<span data-ttu-id="07d85-276">たとえば、電子情報開示マネージャーが、北米、ヨーロッパ、アジア太平洋のサテライトの場所で SharePoint と OneDrive のコンテンツを検索する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="07d85-276">For example, let's say that an eDiscovery manager needs to search for SharePoint and OneDrive content in satellite locations in North American, Europe, and Asia Pacific.</span></span> <span data-ttu-id="07d85-277">最初の手順では、1 つの場所で 1 つずつ、ユーザー アカウントを 3 つ作成します。</span><span class="sxs-lookup"><span data-stu-id="07d85-277">The first step is to create three users accounts, one for each location.</span></span> <span data-ttu-id="07d85-278">次の手順では、1 つの場所で 1 つずつ、*かつ* それぞれの場所のユーザー アカウント用に、検索のアクセス許可フィルターを 3 つ作成します。</span><span class="sxs-lookup"><span data-stu-id="07d85-278">The next step is to create three search permissions filters, one for each location *and* corresponding user account.</span></span> <span data-ttu-id="07d85-279">このシナリオでの 3 つの検索のアクセス許可フィルターの例を示します。</span><span class="sxs-lookup"><span data-stu-id="07d85-279">Here are examples of the three search permissions filters for this scenario.</span></span> <span data-ttu-id="07d85-280">それぞれの例では、**Region** によりその地域の SharePoint データセンターの場所が指定され、**Users** パラメーターにより対応するユーザー アカウントが指定されています。</span><span class="sxs-lookup"><span data-stu-id="07d85-280">In each of these examples, the **Region** specifies the SharePoint datacenter location for that geo and the **Users** parameter specifies the corresponding user account.</span></span>

<span data-ttu-id="07d85-281">**北アメリカ**</span><span class="sxs-lookup"><span data-stu-id="07d85-281">**North America**</span></span>

```powershell
New-ComplianceSecurityFilter -FilterName "SPMultiGeo-NAM" -Users ediscovery-nam@contoso.com -Region NAM -Action ALL
```

<span data-ttu-id="07d85-282">**ヨーロッパ**</span><span class="sxs-lookup"><span data-stu-id="07d85-282">**Europe**</span></span>

```powershell
New-ComplianceSecurityFilter -FilterName "SPMultiGeo-EUR" -Users ediscovery-eur@contoso.com -Region EUR -Action ALL
```

<span data-ttu-id="07d85-283">**アジア太平洋**</span><span class="sxs-lookup"><span data-stu-id="07d85-283">**Asia Pacific**</span></span>

```powershell
New-ComplianceSecurityFilter -FilterName "SPMultiGeo-APC" -Users ediscovery-apc@contoso.com -Region APC -Action ALL
```

<span data-ttu-id="07d85-284">検索のアクセス許可フィルターを使用して複数地域環境のコンテンツを検索する場合は、次の点にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="07d85-284">Keep the following things in mind when using search permissions filters to search for content in multi-geo environments:</span></span>

- <span data-ttu-id="07d85-285">**Region** パラメーターにより、指定されたサテライトの場所が検索されます。</span><span class="sxs-lookup"><span data-stu-id="07d85-285">The **Region** parameter directs searches to the specified satellite location.</span></span> <span data-ttu-id="07d85-286">電子情報開示マネージャーが、検索のアクセス許可フィルターで指定された対象以外の SharePoint サイトと OneDrive サイトのみを検索すると、検索結果は何も返されません。</span><span class="sxs-lookup"><span data-stu-id="07d85-286">If an eDiscovery manager only searches SharePoint and OneDrive sites outside of the region specified in the search permissions filter, no search results are returned.</span></span> 

- <span data-ttu-id="07d85-287">Exchange メールボックスの検索は、**Region** パラメーターにより制御されません。</span><span class="sxs-lookup"><span data-stu-id="07d85-287">The **Region** parameter doesn't control searches of Exchange mailboxes.</span></span> <span data-ttu-id="07d85-288">メールボックスを検索すると、すべてのデータセンターが検索されます。</span><span class="sxs-lookup"><span data-stu-id="07d85-288">All datacenters are searched when you search mailboxes.</span></span>

<span data-ttu-id="07d85-289">複数地域環境での検索のアクセス許可フィルターの使用に関する詳細については、[電子情報開示調査のためにコンプライアンスの境界を設定する](set-up-compliance-boundaries.md#searching-and-exporting-content-in-multi-geo-environments) の「複数地域環境でのコンテンツの検索とエクスポート」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="07d85-289">For more information about using search permissions filters in a multi-geo environment, see the "Searching and exporting content in Multi-Geo environments" section in [Set up compliance boundaries for eDiscovery investigations](set-up-compliance-boundaries.md#searching-and-exporting-content-in-multi-geo-environments).</span></span>
