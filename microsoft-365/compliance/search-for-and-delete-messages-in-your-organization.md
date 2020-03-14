---
title: Office 365 組織でのメール メッセージの検索と削除
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
search.appverid:
- MOE150
- MET150
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: Office 365 セキュリティ/コンプライアンス センターの検索と消去機能を使って、組織のすべてのメールボックスからメール メッセージを検索し、削除できます。
ms.openlocfilehash: 27340bf832feee0dc7b5222f187816b0dfa1bb59
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/13/2020
ms.locfileid: "42634165"
---
# <a name="search-for-and-delete-email-messages-in-your-office-365-organization"></a><span data-ttu-id="a36c8-103">Office 365 組織でのメール メッセージの検索と削除</span><span class="sxs-lookup"><span data-stu-id="a36c8-103">Search for and delete email messages in your Office 365 organization</span></span>

<span data-ttu-id="a36c8-104">**この記事は管理者向けです。メールボックスで削除するアイテムを探している場合は、「[クイック検索を使ってメッセージまたはアイテムを検索する](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)」を参照してください。**|</span><span class="sxs-lookup"><span data-stu-id="a36c8-104">**This article is for administrators. Are you trying to find items in your mailbox that you want to delete? See [Find a message or item with Instant Search](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**|</span></span>
   
<span data-ttu-id="a36c8-105">Office 365 のコンテンツ検索機能を使って、組織のすべてのメールボックスにあるメール メッセージを検索し削除できます。</span><span class="sxs-lookup"><span data-stu-id="a36c8-105">You can use the Content Search feature in Office 365 to search for and delete an email message from all mailboxes in your organization.</span></span> <span data-ttu-id="a36c8-106">この機能を使用して、次のように有害な、またはリスクが高い可能性があるメールを検索し、削除することができます。</span><span class="sxs-lookup"><span data-stu-id="a36c8-106">This can help you find and remove potentially harmful or high-risk email, such as:</span></span>
  
- <span data-ttu-id="a36c8-107">危険性のある添付ファイルやウイルスを含むメッセージ</span><span class="sxs-lookup"><span data-stu-id="a36c8-107">Messages that contain dangerous attachments or viruses</span></span>
    
- <span data-ttu-id="a36c8-108">フィッシング メッセージ</span><span class="sxs-lookup"><span data-stu-id="a36c8-108">Phishing messages</span></span>
    
- <span data-ttu-id="a36c8-109">機密データを含むメッセージ</span><span class="sxs-lookup"><span data-stu-id="a36c8-109">Messages that contain sensitive data</span></span>
    
> [!CAUTION]
> <span data-ttu-id="a36c8-110">検索と消去は、必要なアクセス許可が割り当てられていれば、誰でも組織のメールボックスからメール メッセージを削除できる強力な機能です。</span><span class="sxs-lookup"><span data-stu-id="a36c8-110">Search and purge is a powerful feature that allows anyone that is assigned the necessary permissions to delete email messages from mailboxes in your organization.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="a36c8-111">始める前に</span><span class="sxs-lookup"><span data-stu-id="a36c8-111">Before you begin</span></span>

- <span data-ttu-id="a36c8-112">コンテンツ検索を作成して実行するには、**電子情報開示管理者**役割グループのメンバーであるか、**コンプライアンス検索**の管理役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a36c8-112">To create and run a Content Search, you have to be a member of the **eDiscovery Manager** role group or be assigned the **Compliance Search** management role.</span></span> <span data-ttu-id="a36c8-113">メッセージを削除するには、**Organization Management** 役割グループのメンバーであるか、**検索と消去**の管理役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a36c8-113">To delete messages, you have to be a member of the **Organization Management** role group or be assigned the **Search And Purge** management role.</span></span> <span data-ttu-id="a36c8-114">ユーザーを役割グループに追加する方法の詳細については、「[セキュリティ/コンプライアンス センターの電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a36c8-114">For information about adding users to a role group, see [Assign eDiscovery permissions in the Security & Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="a36c8-115">メッセージを削除するには、セキュリティ/コンプライアンス センターの PowerShell を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a36c8-115">You have to use Security & Compliance Center PowerShell to delete messages.</span></span> <span data-ttu-id="a36c8-116">接続方法については、「[手順 2](#step-2-connect-to-security--compliance-center-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a36c8-116">See [Step 2](#step-2-connect-to-security--compliance-center-powershell) for instructions about how to connect.</span></span>
    
- <span data-ttu-id="a36c8-117">メールボックスごとに最大 10 個のアイテムを一度に削除できます。</span><span class="sxs-lookup"><span data-stu-id="a36c8-117">A maximum of 10 items per mailbox can be removed at one time.</span></span> <span data-ttu-id="a36c8-118">メッセージを検索し削除するための機能はインシデント対応ツールを意図したものなので、この制限により、メールボックスからすばやくかつ確実にメッセージを削除できます。</span><span class="sxs-lookup"><span data-stu-id="a36c8-118">Because the capability to search for and remove messages is intended to be an incident-response tool, this limit helps ensure that messages are quickly removed from mailboxes.</span></span> <span data-ttu-id="a36c8-119">これは、ユーザーのメールボックスをクリーンアップするための機能ではありません。</span><span class="sxs-lookup"><span data-stu-id="a36c8-119">This feature isn't intended to clean up user mailboxes.</span></span>
    
- <span data-ttu-id="a36c8-120">コンテンツ検索で検索と削除アクションを実行してアイテムを削除できるメールボックスの最大数は 50,000 個です。</span><span class="sxs-lookup"><span data-stu-id="a36c8-120">The maximum number of mailboxes in a Content Search that you can delete items in by doing a search and purge action is 50,000.</span></span> <span data-ttu-id="a36c8-121">コンテンツ検索 ([手順 1](#step-1-create-a-content-search-to-find-the-message-to-delete) で作成) に 50,000 を超えるソース メールボックスが含まれる場合、削除アクション (手順 3 で作成) は失敗します。</span><span class="sxs-lookup"><span data-stu-id="a36c8-121">If the Content Search (that you create in [Step 1](#step-1-create-a-content-search-to-find-the-message-to-delete)) has more than 50,000 source mailboxes, the purge action (that you create in Step 3) will fail.</span></span> <span data-ttu-id="a36c8-122">50,000 を超えるメールボックスに対して検索と削除の操作を実行するためのヒントについては、「[詳細情報](#more-information)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a36c8-122">See the [More information](#more-information) section for a tip on performing a search and purge operation on more than 50,000 mailboxes.</span></span> 
    
- <span data-ttu-id="a36c8-123">この記事の手順は、Exchange Online のメールボックスとパブリック フォルダーにあるアイテムを削除する場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a36c8-123">The procedure in this article can only be used to delete items in Exchange Online mailboxes and public folders.</span></span> <span data-ttu-id="a36c8-124">SharePoint や OneDrive for Business のサイトからコンテンツを削除する場合には使用できません。</span><span class="sxs-lookup"><span data-stu-id="a36c8-124">You can't use it to delete content from SharePoint or OneDrive for Business sites.</span></span>
    
## <a name="step-1-create-a-content-search-to-find-the-message-to-delete"></a><span data-ttu-id="a36c8-125">手順 1: コンテンツ検索を作成して、削除するメッセージを探す</span><span class="sxs-lookup"><span data-stu-id="a36c8-125">Step 1: Create a Content Search to find the message to delete</span></span>

<span data-ttu-id="a36c8-126">最初の手順は、組織のメールボックスから削除するメッセージを見つけるコンテンツ検索を作成し、実行することです。</span><span class="sxs-lookup"><span data-stu-id="a36c8-126">The first step is to create and run a Content Search to find the message that you want to remove from mailboxes in your organization.</span></span> <span data-ttu-id="a36c8-127">セキュリティ/コンプライアンス センターを使用するか、**New-ComplianceSearch** コマンドレットと **Start-ComplianceSearch** コマンドレットを実行すると、検索を作成できます。</span><span class="sxs-lookup"><span data-stu-id="a36c8-127">You can create the search by using the Security & Compliance Center or by running the **New-ComplianceSearch** and **Start-ComplianceSearch** cmdlets.</span></span> <span data-ttu-id="a36c8-128">[手順 3](#step-3-delete-the-message) で **New-ComplianceSearchAction -Purge** コマンドを実行すると、この検索のクエリに一致するメッセージは削除されます。</span><span class="sxs-lookup"><span data-stu-id="a36c8-128">The messages that match the query for this search will be deleted by running the **New-ComplianceSearchAction -Purge** command in [Step 3](#step-3-delete-the-message).</span></span> <span data-ttu-id="a36c8-129">コンテンツ検索を作成し、検索クエリを構成する方法については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a36c8-129">For information about creating a Content Search and configuring search queries, see the following topics:</span></span> 
  
- [<span data-ttu-id="a36c8-130">Office 365 のコンテンツ検索</span><span class="sxs-lookup"><span data-stu-id="a36c8-130">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="a36c8-131">コンテンツ検索のキーワード クエリ</span><span class="sxs-lookup"><span data-stu-id="a36c8-131">Keyword queries for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="a36c8-132">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="a36c8-132">New-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearch)
    
- [<span data-ttu-id="a36c8-133">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="a36c8-133">Start-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/Start-ComplianceSearch)
    
> [!NOTE]
> <span data-ttu-id="a36c8-134">この手順で作成するコンテンツ検索で検索されるコンテンツの場所に、SharePoint や OneDrive for Business のサイトを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="a36c8-134">The content locations that are searched in the Content Search that you create in this step can't include SharePoint or OneDrive for Business sites.</span></span> <span data-ttu-id="a36c8-135">メール メッセージに使われるコンテンツ検索には、メールボックスとパブリック フォルダーのみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a36c8-135">You can include only mailboxes and public folders in a Content Search that will be used to email messages.</span></span> <span data-ttu-id="a36c8-136">コンテンツ検索にサイトが含まれる場合、**New-ComplianceSearchAction** コマンドレットを実行すると、手順 3 でエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="a36c8-136">If the Content Search includes sites, you'll receive an error in Step 3 when you run the **New-ComplianceSearchAction** cmdlet.</span></span> 
  
### <a name="tips-for-finding-messages-to-remove"></a><span data-ttu-id="a36c8-137">削除するメッセージを見つけるためのヒント</span><span class="sxs-lookup"><span data-stu-id="a36c8-137">Tips for finding messages to remove</span></span>

<span data-ttu-id="a36c8-p109">検索クエリの目標は、削除するメッセージだけに検索結果を絞り込むことです。次にヒントを示します。</span><span class="sxs-lookup"><span data-stu-id="a36c8-p109">The goal of the search query is to narrow the results of the search to only the message or messages that you want to remove. Here are some tips:</span></span>
  
- <span data-ttu-id="a36c8-140">メッセージの件名に使われているテキストまたはフレーズを正確に記憶している場合は、検索クエリの **Subject** プロパティをご利用ください。</span><span class="sxs-lookup"><span data-stu-id="a36c8-140">If you know the exact text or phrase used in the subject line of the message, use the **Subject** property in the search query.</span></span> 
    
- <span data-ttu-id="a36c8-141">メッセージの正確な日付 (または期間) がわかる場合は、検索クエリに **Received** プロパティを含めます。</span><span class="sxs-lookup"><span data-stu-id="a36c8-141">If you know that exact date (or date range) of the message, include the **Received** property in the search query.</span></span> 
    
- <span data-ttu-id="a36c8-142">メッセージの送信者がわかる場合は、検索クエリに **From** プロパティを含めます。</span><span class="sxs-lookup"><span data-stu-id="a36c8-142">If you know who sent the message, include the **From** property in the search query.</span></span> 
    
- <span data-ttu-id="a36c8-143">検索結果をプレビューして、検索が、削除を希望するメッセージだけを返したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a36c8-143">Preview the search results to verify that the search returned only the message (or messages) that you want to delete.</span></span>
    
- <span data-ttu-id="a36c8-144">検索見積もりの統計情報 (セキュリティ/コンプライアンス センターの検索の詳細ウィンドウや、[Get-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517934) コマンドレットを使用して表示される情報) を使用して、結果の合計数のカウントを取得します。</span><span class="sxs-lookup"><span data-stu-id="a36c8-144">Use the search estimate statistics (displayed in the details pane of the search in the Security & Compliance Center or by using the [Get-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517934) cmdlet) to get a count of the total number of results.</span></span> 
    
<span data-ttu-id="a36c8-145">不審な電子メール メッセージを検索するクエリの 2 つの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a36c8-145">Here are two examples of queries to find suspicious email messages.</span></span>
  
- <span data-ttu-id="a36c8-146">このクエリは、2016 年 4 月 13 日から 2016 年 4 月 14 日までの間にユーザーが受信し、単語 "action" と "required" が件名に含まれるメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="a36c8-146">This query returns messages that were received by users between April 13, 2016 and April 14, 2016 and that contain the words "action" and "required" in the subject line.</span></span>
    
    ```powershell
    (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
    ```

- <span data-ttu-id="a36c8-147">このクエリは、chatsuwloginsset12345@outlook.com から送信され、完全に一致する語句 "Update your account information" (アカウント情報を更新してください) が件名に含まれているメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="a36c8-147">This query returns messages that were sent by chatsuwloginsset12345@outlook.com and that contain the exact phrase "Update your account information" in the subject line.</span></span>
    
    ```powershell
    (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
    ```

## <a name="step-2-connect-to-security--compliance-center-powershell"></a><span data-ttu-id="a36c8-148">手順 2: セキュリティ/コンプライアンス センターの PowerShell に接続する</span><span class="sxs-lookup"><span data-stu-id="a36c8-148">Step 2: Connect to Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="a36c8-149">次に、組織のセキュリティ/コンプライアンス センターの PowerShell に接続します。</span><span class="sxs-lookup"><span data-stu-id="a36c8-149">The next step is to connect to Security & Compliance Center PowerShell for your organization.</span></span> <span data-ttu-id="a36c8-150">詳細な手順については、「[セキュリティ/コンプライアンス センターの PowerShell への接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a36c8-150">For step-by-step instructions, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
  
<span data-ttu-id="a36c8-151">Office 365 アカウントで多要素認証 (MFA) やフェデレーション認証を使用する場合、次のトピックの手順ではセキュリティ/コンプライアンス センターの PowerShell に接続できません。</span><span class="sxs-lookup"><span data-stu-id="a36c8-151">If your Office 365 account uses multi-factor authentication (MFA) or federated authentication, you can't use the instructions in the previous topic on connecting to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="a36c8-152">代わりに、「[多要素認証を使用してセキュリティ/コンプライアンス センターの PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell)」の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a36c8-152">Instead, see the instructions in the topic [Connect to Security & Compliance Center PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell).</span></span>
  
## <a name="step-3-delete-the-message"></a><span data-ttu-id="a36c8-153">手順 3:メッセージを削除する</span><span class="sxs-lookup"><span data-stu-id="a36c8-153">Step 3: Delete the message</span></span>

<span data-ttu-id="a36c8-154">削除するメッセージを返すコンテンツ検索を作成して検索条件を絞り、セキュリティ/コンプライアンス センターの PowerShell に接続したら、最後に **New-ComplianceSearchAction** コマンドレットを実行して、メッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="a36c8-154">After you've created and refined a Content Search to return the message that you want to remove and are connected to Security & Compliance Center PowerShell, the final step is to run the **New-ComplianceSearchAction** cmdlet to delete the message.</span></span> <span data-ttu-id="a36c8-155">メッセージは、論理的に削除することも、物理的に削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="a36c8-155">You can soft- or hard-delete the message.</span></span> <span data-ttu-id="a36c8-156">論理的に削除したアイテムは、ユーザーの [回復可能なアイテム] フォルダーに移動され、削除済みアイテムの保持期間が切れるまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="a36c8-156">A soft-deleted message is moved to a user's Recoverable Items folder and retained until the deleted item retention period expires.</span></span> <span data-ttu-id="a36c8-157">物理的に削除したメッセージは、メールボックスから完全に削除するようにマークされ、管理フォルダー用アシスタントによって次回そのメールボックスが処理される際に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="a36c8-157">Hard-deleted messages are marked for permanent removal from the mailbox and will be permanently removed the next time the mailbox is processed by the Managed Folder Assistant.</span></span> <span data-ttu-id="a36c8-158">そのメールボックスで単一アイテムの回復が有効になっている場合、物理的に削除したアイテムは、削除済みアイテムの保持期間が切れると完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="a36c8-158">If single item recovery is enabled for the mailbox, hard-deleted items will be permanently removed after the deleted item retention period expires.</span></span> <span data-ttu-id="a36c8-159">メールボックスが保留中になっている場合は、削除したメッセージは、そのアイテムの保留期間が切れるか、その保留がメールボックスから削除されるまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="a36c8-159">If a mailbox is placed on hold, deleted messages are preserved until the hold duration for the item expires or until the hold is removed from the mailbox.</span></span>
  
<span data-ttu-id="a36c8-160">次の例では、"Remove Phishing Message"(フィッシング メッセージの削除) という名前のコンテンツ検索によって返された検索結果がコマンドによって論理的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="a36c8-160">In the following example, the command soft-deletes the search results returned by a Content Search named "Remove Phishing Message".</span></span> 

```powershell
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```

<span data-ttu-id="a36c8-161">Remove Phishing Message コンテンツ検索によって返されたアイテムを物理的に削除するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a36c8-161">To hard-delete the items returned by the  "Remove Phishing Message" content search, you would run this command:</span></span>

```powershell
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```

<span data-ttu-id="a36c8-162">前のコマンドを実行してメッセージを論理的または物理的に削除する場合、*SearchName* パラメーターで指定される検索は、手順 1 で作成したコンテンツ検索になります。</span><span class="sxs-lookup"><span data-stu-id="a36c8-162">When you run the previous command to soft- or hard-delete messages, the search specified by the  *SearchName*  parameter is the Content Search that you created in Step 1.</span></span> 
  
<span data-ttu-id="a36c8-163">詳細については、「[New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearchAction)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a36c8-163">For more information, see [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearchAction).</span></span>

## <a name="more-information"></a><span data-ttu-id="a36c8-164">詳細情報</span><span class="sxs-lookup"><span data-stu-id="a36c8-164">More information</span></span>

- <span data-ttu-id="a36c8-165">**検索と削除の操作の状態を取得するにはどうすればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="a36c8-165">**How do you get status on the search and remove operation?**</span></span>

    <span data-ttu-id="a36c8-166">**Get-ComplianceSearchAction** を実行すると、その削除操作の状態を取得できます。</span><span class="sxs-lookup"><span data-stu-id="a36c8-166">Run the **Get-ComplianceSearchAction** to get the status on the delete operation.</span></span> <span data-ttu-id="a36c8-167">**New-ComplianceSearchAction** コマンドレットを実行したときに作成されるオブジェクトは、`<name of Content Search>_Purge` という形式で名前付けされます。</span><span class="sxs-lookup"><span data-stu-id="a36c8-167">The object that is created when you run the **New-ComplianceSearchAction** cmdlet is named using this format:  `<name of Content Search>_Purge`.</span></span> 
    
- <span data-ttu-id="a36c8-168">**メッセージを削除するとどうなりますか?**</span><span class="sxs-lookup"><span data-stu-id="a36c8-168">**What happens after you delete a message?**</span></span>

   <span data-ttu-id="a36c8-169">`New-ComplianceSearchAction -Purge -PurgeType HardDelete` コマンドを使用して削除されたメッセージは、Purges フォルダーに移動され、ユーザーはアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="a36c8-169">A message that's deleted with the  `New-ComplianceSearchAction -Purge -PurgeType HardDelete` command is moved to the Purges folder and can't be accessed by the user.</span></span> <span data-ttu-id="a36c8-170">Purges フォルダーに移動されたメッセージは、そのメールボックスで単一アイテムの回復が有効になっている場合、削除済みアイテムの保持期間が切れるまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="a36c8-170">After the message is moved to the Purges folder, the message is retained for the duration of the deleted item retention period if single item recovery is enabled for the mailbox.</span></span> <span data-ttu-id="a36c8-171">(Office 365 では、新しいメールボックスを作成すると、既定で単一アイテムの回復が有効になります)。削除済みアイテムの保持期間を過ぎると、そのメッセージは完全に削除するようにマークされ、管理フォルダー用アシスタントによって次回そのメールボックスが処理される際に Office 365 から消去されます。</span><span class="sxs-lookup"><span data-stu-id="a36c8-171">(In Office 365, single item recovery is enabled by default when a new mailbox is created.) After the deleted item retention period expires, the message is marked for permanent deletion and will be purged from Office 365 the next time the mailbox is processed by the Managed Folder assistant.</span></span> 

   <span data-ttu-id="a36c8-172">`New-ComplianceSearchAction -Purge -PurgeType SoftDelete` コマンドを使用すると、メッセージは、ユーザーの回復可能なアイテム フォルダーの Deletions フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="a36c8-172">If you use the `New-ComplianceSearchAction -Purge -PurgeType SoftDelete` command, messages are moved to the Deletions folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="a36c8-173">Office 365 から直ちに削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="a36c8-173">It isn't immediately purged from Office 365.</span></span> <span data-ttu-id="a36c8-174">ユーザーは、メールボックスに構成されている削除したアイテムの保持期間に基づき、その期間は削除済みアイテム フォルダーのメッセージを復元できます。</span><span class="sxs-lookup"><span data-stu-id="a36c8-174">The user can recover messages in the Deleted Items folder for the duration based on the deleted item retention period configured for the mailbox.</span></span> <span data-ttu-id="a36c8-175">この保持期間を過ぎるか、過ぎる前にユーザーがメッセージを消去すると、メッセージは Purges フォルダーに移動され、ユーザーはアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="a36c8-175">After this retention period expires (or if user purges the message before it expires), the message is moved to the Purges folder and can no longer be accessed by the user.</span></span> <span data-ttu-id="a36c8-176">Purges フォルダーに移動されたメッセージは、そのメールボックスで単一アイテムの回復が有効になっている場合、メールボックスに構成されている削除済みアイテムの保持期間が切れるまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="a36c8-176">Once in the Purges folder, the message is retained for the duration based on the deleted item retention period configured for the mailbox if single items recovery is enabled for the mailbox.</span></span> <span data-ttu-id="a36c8-177">(Office 365 では、新しいメールボックスを作成すると、既定で単一アイテムの回復が有効になります)。削除済みアイテムの保持期間を過ぎると、そのメッセージは完全に削除するようにマークされ、管理フォルダー用アシスタントによって次回そのメールボックスが処理される際に Office 365 から消去されます。</span><span class="sxs-lookup"><span data-stu-id="a36c8-177">(In Office 365, single item recovery is enabled by default when a new mailbox is created.) After the deleted item retention period expires, the message is marked for permanent deletion and will be purged from Office 365 the next time that the mailbox is processed by the Managed Folder assistant.</span></span> 
    
- <span data-ttu-id="a36c8-178">**50,000 を超えるメールボックスからメッセージを削除するにはどうすればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="a36c8-178">**What if you have to delete a message from more than 50,000 mailboxes?**</span></span>

    <span data-ttu-id="a36c8-179">前述のとおり、検索と削除の操作を実行できるメールボックスの上限は 50,000 です。</span><span class="sxs-lookup"><span data-stu-id="a36c8-179">As previously stated, you can perform a search and purge operation on a maximum of 50,000 mailboxes.</span></span> <span data-ttu-id="a36c8-180">50,000 を超えるメールボックスに対して検索と削除の操作を実行する必要がある場合は、検索対象となるメールボックスの数を 50,000 未満に減らす一時的な検索権限フィルターを作成することをご検討ください。</span><span class="sxs-lookup"><span data-stu-id="a36c8-180">If you have to do a search and purge operation on more than 50,000 mailboxes, consider creating temporary search permissions filters that would reduce the number of mailboxes that would be searched to less than 50,000 mailboxes.</span></span> <span data-ttu-id="a36c8-181">たとえば、異なる部署、都道府県、国のメールボックスが組織内にある場合、そのようなメールボックスのプロパティのいずれかを基にメールボックスの検索権限フィルターを作成して、組織のメールボックスのサブセットを検索できます。</span><span class="sxs-lookup"><span data-stu-id="a36c8-181">For example, if your organization contains mailboxes in different departments, states, or countries, you can create a mailbox search permissions filter based on one of those mailbox properties to search a subset of mailboxes in your organization.</span></span> <span data-ttu-id="a36c8-182">検索権限フィルターを作成したら、検索を作成 (手順 1 を参照) し、メッセージを削除 (手順 3 を参照) します。</span><span class="sxs-lookup"><span data-stu-id="a36c8-182">After you create the search permissions filter, you would create the search (described in Step 1) and then delete the message (described in Step 3).</span></span> <span data-ttu-id="a36c8-183">その後、フィルターを編集し、別のメールボックスのセット内のメッセージを検索して削除できます。</span><span class="sxs-lookup"><span data-stu-id="a36c8-183">Then you can edit the filter to search for and purge messages in a different set of mailboxes.</span></span> <span data-ttu-id="a36c8-184">検索権限フィルターの作成の詳細については、「[コンテンツ検索用にアクセス許可フィルターを設定する](permissions-filtering-for-content-search.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a36c8-184">For more information about creating search permissions filters, see [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md).</span></span>
    
- <span data-ttu-id="a36c8-185">**検索結果に含まれるインデックスのないアイテムも削除されますか?**</span><span class="sxs-lookup"><span data-stu-id="a36c8-185">**Will unindexed items included in the search results be deleted?**</span></span>

    <span data-ttu-id="a36c8-186">いいえ。\`New-ComplianceSearchAction -Purge コマンドでは、インデックスのないアイテムは削除されません。</span><span class="sxs-lookup"><span data-stu-id="a36c8-186">No, the  \`New-ComplianceSearchAction -Purge command doesn't delete unindexed items.</span></span> 
    
- <span data-ttu-id="a36c8-187">**メッセージが、インプレース ホールドまたは訴訟ホールドが設定されたメールボックスから削除されたり、Office 365 の保持ポリシーに割り当てられたりするとどうなりますか?**</span><span class="sxs-lookup"><span data-stu-id="a36c8-187">**What happens if a message is deleted from a mailbox that has been placed on In-Place Hold or Litigation Hold or is assigned to an Office 365 retention policy?**</span></span>

    <span data-ttu-id="a36c8-188">消去されて Purges フォルダーに移動されたメッセージは、保持期間が切れるまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="a36c8-188">After the message is purged and moved to the Purges folder, the message is retained until the hold duration expires.</span></span> <span data-ttu-id="a36c8-189">保持期間が無期限である場合は、ホールドが解除されるか、または保持期間が変更されるまで、アイテムは保持されます。</span><span class="sxs-lookup"><span data-stu-id="a36c8-189">If the hold duration is unlimited, then items are retained until the hold is removed or the hold duration is changed.</span></span>
    
- <span data-ttu-id="a36c8-190">**検索と削除のワークフローが、セキュリティ/コンプライアンス センターのさまざまな役割グループに分けられているのはなぜですか?**</span><span class="sxs-lookup"><span data-stu-id="a36c8-190">**Why is the search and remove workflow divided among different security and compliance center role groups?**</span></span>

    <span data-ttu-id="a36c8-191">前述したように、メールボックスを検索するには、電子情報開示管理者役割グループのメンバーであるか、コンプライアンス検索の管理の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a36c8-191">As previously explained, a person has to be a member of the eDiscovery Manager role group or be assigned the Compliance Search management role to search mailboxes.</span></span> <span data-ttu-id="a36c8-192">メッセージを削除するには、組織管理役割グループのメンバーであるか、検索と消去の管理の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a36c8-192">To delete messages, a person has to be a member of the Organization Management role group or be assigned the Search And Purge management role.</span></span> <span data-ttu-id="a36c8-193">この制限によって、組織のメールボックスを検索できるユーザーとメッセージを削除できるユーザーを制御できます。</span><span class="sxs-lookup"><span data-stu-id="a36c8-193">This makes it possible to control who can search mailboxes in the organization and who can delete messages.</span></span> 
