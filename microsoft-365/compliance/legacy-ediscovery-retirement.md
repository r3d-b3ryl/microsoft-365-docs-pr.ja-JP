---
title: 従来の電子情報開示ツールの廃止
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: In-Place電子情報開示とIn-Place保留 (および対応する PowerShell コマンドレット) は、2020 年上半期に廃止されます。 このSearch-Mailbox Advanced eDiscovery v1.0 も同じ期間に廃止されます。
ms.openlocfilehash: a40cc67b29e33d61d6750792f6a773622a73f678
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750880"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a><span data-ttu-id="1d94c-104">従来の電子情報開示ツールの廃止</span><span class="sxs-lookup"><span data-stu-id="1d94c-104">Retirement of legacy eDiscovery tools</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d94c-105">Microsoft は、公衆の健康状況を評価しています。お客様に対する影響を理解しています。</span><span class="sxs-lookup"><span data-stu-id="1d94c-105">Microsoft has been evaluating the public health situation, and we understand the impact this is having on our customers.</span></span> <span data-ttu-id="1d94c-106">私たちは、強力なパートナーであり、責任を持つグローバル市民でありしたいと考えています。</span><span class="sxs-lookup"><span data-stu-id="1d94c-106">We want to be strong partners and responsible global citizens.</span></span> <span data-ttu-id="1d94c-107">直面している多くの負担の 1 つを軽減するために、この記事で説明する従来の電子情報開示ツールの予定されたサポート期間を 3 か月遅らせる予定です。</span><span class="sxs-lookup"><span data-stu-id="1d94c-107">To ease one of the many burdens you are facing, we are going to delay the scheduled retirement for the legacy eDiscovery tools described in this article by three months.</span></span> <span data-ttu-id="1d94c-108">**更新された終了日を以下に示します。**</span><span class="sxs-lookup"><span data-stu-id="1d94c-108">**The updated retirement dates are reflected below.**</span></span>

<span data-ttu-id="1d94c-109">長年にわたり、Microsoft は Exchange Online から電子メール コンテンツを検索、プレビュー、エクスポートできる電子情報開示ツールを提供してきました。</span><span class="sxs-lookup"><span data-stu-id="1d94c-109">Over the years, Microsoft has provided eDiscovery tools that let you search, preview, and export email content from Exchange Online.</span></span> <span data-ttu-id="1d94c-110">ただし、これらのツールは、SharePoint Online や Microsoft 365 グループなどの他の Microsoft 365 サービスで Exchange 以外のコンテンツを検索する効果的な方法を提供しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="1d94c-110">However, these tools no longer offer an effective way to search for non-Exchange content in other Microsoft 365 services, such as SharePoint Online and Microsoft 365 Groups.</span></span> <span data-ttu-id="1d94c-111">この問題に対処するために、Microsoft はさまざまな Microsoft 365 コンテンツの検索に役立つ他の電子情報開示ツールを提供しています。</span><span class="sxs-lookup"><span data-stu-id="1d94c-111">To address this, Microsoft offers other eDiscovery tools that help you search for a wide variety of Microsoft 365 content.</span></span> <span data-ttu-id="1d94c-112">また、Microsoft 365 コンプライアンス センターに最新かつ強力な電子情報開示機能を組み込む取[り組みにも取り組み続け、](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="1d94c-112">And we've been working hard to incorporate the most current and powerful eDiscovery functionality in the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span> <span data-ttu-id="1d94c-113">これにより、組織は Exchange Online を含む多くの Microsoft 365 サービスのコンテンツに対する法的、内部的、その他のドキュメント要求に対応できます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-113">This allows organizations to respond to legal, internal, and other document requests for content across many Microsoft 365 services, including Exchange Online.</span></span>

<span data-ttu-id="1d94c-114">この Microsoft 365 コンプライアンス センターの電子情報開示機能の新機能および強化された結果、Exchange Online と Microsoft 365 の電子メール コンテンツの検索に関連する次の電子情報開示関連の機能は廃止されます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-114">As a result of this new and improved eDiscovery functionality in the Microsoft 365 compliance center, we're retiring the following eDiscovery-related features and functionality related to searching for email content in Exchange Online and Microsoft 365:</span></span>

- <span data-ttu-id="1d94c-115">Exchange 管理センターの[インプレース電子情報開示](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)および[インプレース ホールド](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds)。</span><span class="sxs-lookup"><span data-stu-id="1d94c-115">[In-Place eDiscovery](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) and [In-Place Holds](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds) in the Exchange admin center.</span></span>

- <span data-ttu-id="1d94c-116">電子情報開示と In-Place 保持をサポートする Exchange Online Power In-Place Shell コマンドレット (これらのコマンドレットは、まとめて \**-MailboxSearch* コマンドレットとして識別されます)。</span><span class="sxs-lookup"><span data-stu-id="1d94c-116">The Exchange Online PowerShell cmdlets that support In-Place eDiscovery and In-Place Holds (these cmdlets are collectively identified as \**-MailboxSearch* cmdlets).</span></span> <span data-ttu-id="1d94c-117">これには、次のコマンドレットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-117">This includes the following cmdlets:</span></span>

  - [<span data-ttu-id="1d94c-118">New-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="1d94c-118">New-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-mailboxsearch)

  - [<span data-ttu-id="1d94c-119">Start-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="1d94c-119">Start-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/start-mailboxsearch)

  - [<span data-ttu-id="1d94c-120">Stop-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="1d94c-120">Stop-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/stop-mailboxsearch)

  - [<span data-ttu-id="1d94c-121">Set-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="1d94c-121">Set-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-mailboxsearch)

   > [!NOTE]
   > <span data-ttu-id="1d94c-122">[Get-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/get-mailboxsearch)コマンドレットと[Remove-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/remove-mailboxsearch)コマンドレットは、他の \*\*\*\*-MailboxSearch\*\*_ コマンドレットが廃止された後に使用できます。このコマンドレットを使用すると、他の電子情報開示および保持ツールへの移行に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-122">The [Get-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/get-mailboxsearch) and [Remove-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/remove-mailboxsearch) cmdlets will be available after the other \*\*\*\*-MailboxSearch\*\*_ cmdlets are retired so that you can use them to help in your transition to other eDiscovery and hold tools.</span></span> <span data-ttu-id="1d94c-123">ただし、特定の日付 (下記を参照) が終了すると、Microsoft サポートはこれら 2 つのコマンドレットをサポートしなくなりました。</span><span class="sxs-lookup"><span data-stu-id="1d94c-123">However, after a certain date (cited below) Microsoft Support will no longer supports these two cmdlets.</span></span>

- <span data-ttu-id="1d94c-124">Exchange Online PowerShell の [Search-Mailbox](https://docs.microsoft.com/powershell/module/exchange/search-mailbox) コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="1d94c-124">The [Search-Mailbox](https://docs.microsoft.com/powershell/module/exchange/search-mailbox) cmdlet in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="1d94c-125">Exchange Web Services API での次の操作。</span><span class="sxs-lookup"><span data-stu-id="1d94c-125">The following operations in the Exchange Web Services API:</span></span>

   - [<span data-ttu-id="1d94c-126">GetSearchableMailboxes</span><span class="sxs-lookup"><span data-stu-id="1d94c-126">GetSearchableMailboxes</span></span>](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [<span data-ttu-id="1d94c-127">SearchMailboxes</span><span class="sxs-lookup"><span data-stu-id="1d94c-127">SearchMailboxes</span></span>](https://docs.microsoft.com/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [<span data-ttu-id="1d94c-128">SetHoldOnMailboxes</span><span class="sxs-lookup"><span data-stu-id="1d94c-128">SetHoldOnMailboxes</span></span>](https://docs.microsoft.com/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [<span data-ttu-id="1d94c-129">GetHoldOnMailboxes</span><span class="sxs-lookup"><span data-stu-id="1d94c-129">GetHoldOnMailboxes</span></span>](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- <span data-ttu-id="1d94c-130">[Office 365 Advanced eDiscovery v1.0](office-365-advanced-ediscovery.md)は、Office 365 セキュリティ & コンプライアンス センターのコア電子情報開示ケースを通じてアクセスされる Advanced eDiscovery の最初のバージョンです。</span><span class="sxs-lookup"><span data-stu-id="1d94c-130">[Office 365 Advanced eDiscovery v1.0](office-365-advanced-ediscovery.md), which is the first version of Advanced eDiscovery that's accessed through a Core eDiscovery case in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="1d94c-131">Advanced eDiscovery v1.0 のサポートがサポートされなしても、コア電子情報開示ケースを作成および管理する機能に影響はありません。</span><span class="sxs-lookup"><span data-stu-id="1d94c-131">The retirement of Advanced eDiscovery v1.0 doesn't impact your ability to create and manage Core eDiscovery cases.</span></span>

> [!NOTE]
> <span data-ttu-id="1d94c-132">廃止される電子情報開示機能は、クラウドベースのバージョンの Microsoft 365 および Office 365 にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-132">The eDiscovery functionality being retired only applies to cloud-based versions of Microsoft 365 and Office 365.</span></span> <span data-ttu-id="1d94c-133">Exchange と SharePoint のオンプレミス バージョンの電子情報開示機能は、今後の通知まで引き続きサポートされます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-133">eDiscovery functionality in on-premises versions of Exchange and SharePoint will still be supported until further notice.</span></span>

<span data-ttu-id="1d94c-134">この記事の以下のセクションでは、廃止される各機能に関するガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="1d94c-134">The following sections in this article provide guidance about each feature being retired.</span></span> <span data-ttu-id="1d94c-135">この情報には、廃止されたツールの代わりに使用できるタイムラインや代替ツールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1d94c-135">This information including timelines and alternative tools that you can use instead of the retired tool.</span></span>

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a><span data-ttu-id="1d94c-136">In-Place Exchange 管理センターIn-Place電子情報開示と電子情報開示の保留</span><span class="sxs-lookup"><span data-stu-id="1d94c-136">In-Place eDiscovery and In-Place Holds in the Exchange admin center</span></span> 

<span data-ttu-id="1d94c-137">2017 年 7 月 1 日の最初の発表と同様に、Exchange 管理センター (EAC) の In-Place 電子情報開示 & 保持機能は廃止されます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-137">As per the original announcement on July 1, 2017, the In-Place eDiscovery & Hold functionality in the Exchange admin center (EAC) is being retired.</span></span> <span data-ttu-id="1d94c-138">EAC In-Place電子情報開示&保留リスト] ページを使用すると、Exchange Online からコンテンツを検索、保持、およびエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-138">The In-Place eDiscovery & Holds page in the EAC allowed you to search, hold, and export content from Exchange Online.</span></span> <span data-ttu-id="1d94c-139">In-Place電子情報開示を使用すると、検索結果を探索メールボックスにコピーして、自分または他の電子情報開示管理者がコンテンツを確認し、法律、規制、および公開要求で利用できるようすることができます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-139">In-Place eDiscovery also let you copy search results to a discovery mailbox so that you or other eDiscovery managers could review content and make it available for legal, regulatory, and public requests.</span></span>

<span data-ttu-id="1d94c-140">これらの機能 (検索結果を探索メールボックスにコピーする機能を除く) はすべて [、Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) コンプライアンス センターのコンテンツ検索、電子情報開示、および Advanced eDiscovery ツール (幅広い Microsoft 365 サービスの機能、信頼性、サポートが強化されたツール) で利用できるようなったため、これらのツールはできるだけ早く使用を開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1d94c-140">Because all of these capabilities (except for copying search results to a discovery mailbox) are now available in the content search, eDiscovery and Advanced eDiscovery tools in the [Microsoft 365 compliance center](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) (with improved functionality, reliability, and support for a wide range of Microsoft 365 services), we recommend that you start using these tools as soon as possible.</span></span> <span data-ttu-id="1d94c-141">これらの他の電子情報開示ツールへの移行を支援するために、次の表に、電子情報開示と保持の代わりに使用できるツールIn-Place示In-Placeします。</span><span class="sxs-lookup"><span data-stu-id="1d94c-141">To help you in the transition to these other eDiscovery tools, the table below lists the tools you can use instead of In-Place eDiscovery and In-Place Hold.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="1d94c-142">影響を受ける組織の範囲</span><span class="sxs-lookup"><span data-stu-id="1d94c-142">Scope of affected organizations</span></span>

- <span data-ttu-id="1d94c-143">Office 365 および Microsoft 365 Enterprise 組織</span><span class="sxs-lookup"><span data-stu-id="1d94c-143">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="1d94c-144">Office 365 および Microsoft 365 Education 組織</span><span class="sxs-lookup"><span data-stu-id="1d94c-144">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="1d94c-145">Office 365 および Microsoft 365 Government 組織これには、GCC、GCC High、DoD が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-145">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="1d94c-146">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="1d94c-146">Office 365 Germany</span></span>

### <a name="timeline-for-retirement"></a><span data-ttu-id="1d94c-147">退職のタイムライン</span><span class="sxs-lookup"><span data-stu-id="1d94c-147">Timeline for retirement</span></span>

- <span data-ttu-id="1d94c-148">2020 年 7 月 1 日: 新しい検索と保留リストを作成できないが、既存の検索の実行、編集、および削除は自分のリスクで行える。</span><span class="sxs-lookup"><span data-stu-id="1d94c-148">July 1, 2020: You won't be able to create new searches and holds, but you can still run, edit, and delete existing searches at your own risk.</span></span> <span data-ttu-id="1d94c-149">Microsoft サポートは、EAC In-Place電子情報開示&保留を無効にしました。</span><span class="sxs-lookup"><span data-stu-id="1d94c-149">Microsoft Support will no longer In-Place eDiscovery & Holds in the EAC.</span></span>

- <span data-ttu-id="1d94c-150">2020 年 10 月 1 日: eAC の In-Place 電子情報開示 & 保留機能は読み取り専用モードになります。</span><span class="sxs-lookup"><span data-stu-id="1d94c-150">October 1, 2020: The In-Place eDiscovery & Holds functionality in the EAC will be placed in a read-only mode.</span></span> <span data-ttu-id="1d94c-151">これにより、可能な操作は、既存の検索および保留リストの削除のみになります。</span><span class="sxs-lookup"><span data-stu-id="1d94c-151">This means you'll only be able to remove existing searches and holds.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="1d94c-152">代替ツール</span><span class="sxs-lookup"><span data-stu-id="1d94c-152">Alternative tools</span></span>

<span data-ttu-id="1d94c-153">次の表に、廃止される既存の機能を置き換える場合に使用できるその他のツールを示します。</span><span class="sxs-lookup"><span data-stu-id="1d94c-153">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="1d94c-154">機能</span><span class="sxs-lookup"><span data-stu-id="1d94c-154">Functionality</span></span></th>
<th><span data-ttu-id="1d94c-155">代替ツール</span><span class="sxs-lookup"><span data-stu-id="1d94c-155">Alternative tool</span></span></th>
<th><span data-ttu-id="1d94c-156">コメント</span><span class="sxs-lookup"><span data-stu-id="1d94c-156">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="1d94c-157">法的な目的での検索、エクスポート、および保留</span><span class="sxs-lookup"><span data-stu-id="1d94c-157">Search, export, and hold for legal purposes</span></span></td>
<td><span data-ttu-id="1d94c-158">Microsoft 365 コンプライアンス センターのコア電子情報開示ケース</span><span class="sxs-lookup"><span data-stu-id="1d94c-158">Core eDiscovery cases in the Microsoft 365 compliance center</span></span> </td>
<td><p><span data-ttu-id="1d94c-159">コア電子情報開示ケースの機能を使用すると、電子情報開示と電子情報開示In-Place保留リストをIn-Placeできます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-159">Using the capabilities of core eDiscovery cases provide the functional parity to In-Place eDiscovery and In-Place Holds.</span></span> <span data-ttu-id="1d94c-160">エクスポートできるものには、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="1d94c-160">This includes the following:</span></span></p>
<ul>
<li>
<p><span data-ttu-id="1d94c-161">検索の規模は数百万の場所に拡大</span><span class="sxs-lookup"><span data-stu-id="1d94c-161">Search scales to millions of locations</span></span></p>
</li>
<li>
<p><span data-ttu-id="1d94c-162">コンテンツの検索、エクスポート、保留に関する信頼性の向上</span><span class="sxs-lookup"><span data-stu-id="1d94c-162">Higher reliability for searching, exporting, and placing content on hold</span></span></p>
</li>
<li>
<p><span data-ttu-id="1d94c-163">Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft Teams、Yammer グループ、Microsoft 365 グループ、および Office 365 アプリケーションに保存されているその他のコンテンツの検索</span><span class="sxs-lookup"><span data-stu-id="1d94c-163">Searching for content in for Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams, Yammer Groups, Microsoft 365 Groups, and other content stored in Office 365 applications</span></span></p></li></ul>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="1d94c-164">保持の目的で保持する</span><span class="sxs-lookup"><span data-stu-id="1d94c-164">Hold for retention purposes</span></span></td>
<td><span data-ttu-id="1d94c-165">Microsoft 365 コンプライアンス センターのアイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="1d94c-165">Retention policies in the Microsoft 365 compliance center</span></span></td>
<td><p><span data-ttu-id="1d94c-166">アイテム保持ポリシーを使用してコンテンツを保持し、必要に応じて、保持期間が経過した後に削除できます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-166">You can use Retention policies to retain content and, if desired, delete it after the retention period expires.</span></span> <span data-ttu-id="1d94c-167">その他の機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1d94c-167">Other capabilities include:</span></span></p>
<ul>
<li>
<p><span data-ttu-id="1d94c-168">組織全体へのポリシーの適用</span><span class="sxs-lookup"><span data-stu-id="1d94c-168">Applying policies to your entire organization</span></span> </p>
</li><li>
<p><span data-ttu-id="1d94c-169">Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft Teams、および Office 365 グループなどの特定のコンテンツの場所にポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="1d94c-169">Applying policies to specific content locations such as Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams, and Office 365 Groups</span></span></p></li>
<li>
<p><span data-ttu-id="1d94c-170">特定のユーザーにポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="1d94c-170">Applying policies to specific users</span></span></p></li></ul>
<p><span data-ttu-id="1d94c-171">詳細については、「アイテム保持ポリシー <a href="https://docs.microsoft.com/microsoft-365/compliance/retention-policies"> と保持ラベルについて」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="1d94c-171">For more information, see <a href="https://docs.microsoft.com/microsoft-365/compliance/retention-policies"> Learn about retention policies and retention labels</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="1d94c-172">確認のために電子メール検索結果を探索メールボックスにコピーする</span><span class="sxs-lookup"><span data-stu-id="1d94c-172">Copy email search results to a discovery mailbox for review</span></span></td><td><span data-ttu-id="1d94c-173">Advanced eDiscovery v2.0 のレビュー セット</span><span class="sxs-lookup"><span data-stu-id="1d94c-173">Review sets in Advanced eDiscovery v2.0</span></span></td>
<td><p><span data-ttu-id="1d94c-174">Microsoft 365 のコンテンツを簡単に確認できます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-174">Reviewing content in Microsoft 365 has never been easier.</span></span> <span data-ttu-id="1d94c-175">レビュー セットには、レビューに必要な時間とデータの量を減らすのに役立つ多くの大きな機能があります。次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="1d94c-175">Review sets have many great capabilities to help reduce the amount of time and data needed to review, including:</span></span></p>
<ul>
<li><p><span data-ttu-id="1d94c-176">レビュー セットで高速検索クエリを実行し、コンテンツをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="1d94c-176">Perform fast search queries and filter content in a review set</span></span></p></li>
<li><p><span data-ttu-id="1d94c-177">レビュー セット内のコンテンツを分析するこれには、電子メールのスレッド化、ほぼ重複した検出、テーマの分析、予測コーディングが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-177">Analyze content in a review set; this includes email threading, near-duplicate detection, Themes analysis, and Predictive coding</span></span></p></li>
<li><p><span data-ttu-id="1d94c-178">レビュー セット内のドキュメントをタグ付けする</span><span class="sxs-lookup"><span data-stu-id="1d94c-178">Tag documents in a review set</span></span></p></li>
<li><p><span data-ttu-id="1d94c-179">弁護士依頼人特権コンテンツの識別に役立つタグ付けの提案</span><span class="sxs-lookup"><span data-stu-id="1d94c-179">Tagging suggestions to help identify attorney  client privilege content</span></span></p></li></ul>
<p><span data-ttu-id="1d94c-180">詳細については、「<a href="https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20">Microsoft 365 の Advanced eDiscovery ソリューションの概要</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d94c-180">For more information, see <a href="https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20">Overview of the Advanced eDiscovery solution in Microsoft 365</a>.</span></span></p>
<p>
<p><span data-ttu-id="1d94c-181">または、検索結果を PST ファイルにエクスポートし、Microsoft 365 インポート サービスを使用して PST を探索メールボックスにインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-181">Alternatively, you can export search results to PST files and then use Microsoft 365 Import service to import the PSTs to a discovery mailbox.</span></span> <span data-ttu-id="1d94c-182">For step-by-step instruction, see <a href="https://docs.microsoft.com/microsoft-365/compliance/use-network-upload-to-import-pst-files">Use network upload to import PST files to Office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="1d94c-182">For step-by-step instruction, see <a href="https://docs.microsoft.com/microsoft-365/compliance/use-network-upload-to-import-pst-files">Use network upload to import PST files to Office 365</a>.</span></span>
</tr>
<tr class=even>
  <td><span data-ttu-id="1d94c-183">1 つのメールボックスから別のメールボックスにメッセージをコピーする</span><span class="sxs-lookup"><span data-stu-id="1d94c-183">Copy messages from one mailbox to a different mailbox</span></span></td>
  <td><span data-ttu-id="1d94c-184"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">メールボックスへのアクセス許可の割り当て</a></span><span class="sxs-lookup"><span data-stu-id="1d94c-184"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
  <td><span data-ttu-id="1d94c-185">別のユーザーの電子メールへのアクセス権をユーザーに付与するには (従業員が組織を離れ、別のユーザーに元従業員の電子メールへのアクセス権を付与する必要がある場合など)、そのユーザーに元従業員のメールボックスへのアクセス許可を割り当て推奨します。</span><span class="sxs-lookup"><span data-stu-id="1d94c-185">To give a person access to another user's email (such as when an employee leaves your organization and you need to give another person access to the former employee's email), we recommended that you assign that person permissions to access the former employee's mailbox.</span></span> <span data-ttu-id="1d94c-186">そのため、メールボックス アイテムを別のユーザーのメールボックスまたは共有メールボックスにコピーする代わりに、ソース メールボックスにアクセスするためのアクセス許可をユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d94c-186">So instead of copying mailbox items to another user mailbox or a shared mailbox, just assign a user permissions to access the source mailbox.</span></span></td>
  
  </tr>
<tr class="odd">
<td><span data-ttu-id="1d94c-187">[回復可能なアイテム] フォルダーからアイテムを復元する</span><span class="sxs-lookup"><span data-stu-id="1d94c-187">Restore items from the Recoverable Items folder</span></span></td>
  <td><span data-ttu-id="1d94c-188"><a href="https://docs.microsoft.com/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</span><span class="sxs-lookup"><span data-stu-id="1d94c-188"><a href="https://docs.microsoft.com/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</span></span></td>
  <td><span data-ttu-id="1d94c-189">アイテムの削除済みアイテムの保持期間が経過しない<i></i>限り、メールボックス内の完全に削除されたアイテム (回復可能な削除済みアイテムとも呼ばれる) を復元できます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-189">You can restore permanently deleted items (also known as <i>soft-deleted</i> items) in mailboxes, as long as the deleted item retention period for an item hasn't expired.</span></span> <span data-ttu-id="1d94c-190">詳細については <a href="https://docs.microsoft.com/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">、「Exchange Online の回復可能なアイテム フォルダー」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="1d94c-190">For more information, see <a href="https://docs.microsoft.com/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Recoverable Items folder in Exchange Online</a>.</span></span></td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a><span data-ttu-id="1d94c-191">インプレース電子情報開示とインプレース ホールドに関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="1d94c-191">FAQs about In-Place eDiscovery and In-Place Holds</span></span>

<span data-ttu-id="1d94c-192">_ *I use the copy search results functionality of In-Place eDiscovery & Holds in the EAC to copy search results to a discovery mailbox for review by attorneys.現在、どのようなオプションがありますか?*\*</span><span class="sxs-lookup"><span data-stu-id="1d94c-192">_ *I use the copy search results functionality of In-Place eDiscovery & Holds in the EAC to copy search results to a discovery mailbox for review by attorneys. What options do I have now?*\*</span></span>

<span data-ttu-id="1d94c-193">現在、この機能をレプリケートする方法は 2 種類あります。</span><span class="sxs-lookup"><span data-stu-id="1d94c-193">There are two ways to replicate this functionality today.</span></span> <span data-ttu-id="1d94c-194">1 つ目は [、Advanced eDiscovery v2.0 のレビュー セットを使用する方法です](https://docs.microsoft.com/microsoft-365/compliance/view-documents-in-review-set)。</span><span class="sxs-lookup"><span data-stu-id="1d94c-194">The first is to use [review sets in Advanced eDiscovery v2.0](https://docs.microsoft.com/microsoft-365/compliance/view-documents-in-review-set).</span></span> <span data-ttu-id="1d94c-195">レビュー セットには、ドキュメントの高速検索、タグ付け、電子メールのスレッド処理、重複するグループ化に近い、テーマ分析、予測コーディングなど、従来のレビュー ツールに表示される機能と同じ機能が多数備備されています。</span><span class="sxs-lookup"><span data-stu-id="1d94c-195">Review sets have many of the same capabilities you see in a traditional review tool like fast search of documents, tagging, email threading, near duplicate grouping, themes analysis, and predictive coding.</span></span> <span data-ttu-id="1d94c-196">引き続き確認のために探索メールボックスを使用する場合、2 つ目のオプションは、検索結果を PST ファイルにエクスポートし、Microsoft コンプライアンス センターの PST インポート機能を使用して [PST](use-network-upload-to-import-pst-files.md) ファイルを探索メールボックスにインポートする方法です。</span><span class="sxs-lookup"><span data-stu-id="1d94c-196">If you still want to use discovery mailboxes for review, the second option is to export search results to PST files and then import the PST files to a discovery mailbox by using the [PST import feature](use-network-upload-to-import-pst-files.md) in the Microsoft compliance center.</span></span>

<span data-ttu-id="1d94c-197">**電子情報開示マネージャーが新しいツールを使用して検索できるコンテンツの場所 (メールボックスやサイトなど) を制御する方法**</span><span class="sxs-lookup"><span data-stu-id="1d94c-197">**How do I control which content locations (such as mailboxes or sites) that can an eDiscovery manager can search using the new tools?**</span></span>

<span data-ttu-id="1d94c-198">また、Microsoft 365 コンプライアンス[](set-up-compliance-boundaries.md)センターは、コンプライアンスの境界を使用して、電子情報開示マネージャーが検索できるコンテンツの場所を制御します。</span><span class="sxs-lookup"><span data-stu-id="1d94c-198">The Microsoft 365 compliance center also uses [compliance boundaries](set-up-compliance-boundaries.md) to control which content locations an eDiscovery Manager can search.</span></span> <span data-ttu-id="1d94c-199">コンプライアンスの境界は、政府機関の境界内に存在する必要がある政府機関や、地理的な下手を尊重するために必要な多国籍企業で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-199">Compliance boundaries are useful in government entities that need to stay within agency boundaries or multi-national corporations required to respect geographical boarders.</span></span>

<span data-ttu-id="1d94c-200">**現在の検索と保留を Microsoft 365 コンプライアンス センターに移動する方法**</span><span class="sxs-lookup"><span data-stu-id="1d94c-200">**How can I move my current searches and holds to the Microsoft 365 compliance center?**</span></span>

<span data-ttu-id="1d94c-201">PowerShell を使用して、In-Place検索と保留を EAC から移行できます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-201">It's possible to migrate In-Place eDiscovery searches and holds from the EAC by using PowerShell.</span></span> <span data-ttu-id="1d94c-202">手順については [、「EAC から Microsoft 365](https://go.microsoft.com/fwlink/?linkid=2114224)コンプライアンス センターへの検索と保留の移行」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d94c-202">For instructions, see [Migrate searches and holds from the EAC to the Microsoft 365 compliance center](https://go.microsoft.com/fwlink/?linkid=2114224).</span></span>

## <a name="-mailboxsearch-cmdlets"></a><span data-ttu-id="1d94c-203">\*-MailboxSearch コマンドレット</span><span class="sxs-lookup"><span data-stu-id="1d94c-203">\*-MailboxSearch cmdlets</span></span>

<span data-ttu-id="1d94c-204">Exchange 管理センターで 2017 年 7 月 1 日に発表された最初の通知に基づいて、In-Place 電子情報開示 & の保持機能と対応する **\* -MailboxSearch** コマンドレットは廃止されます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-204">As per the original notice announced on July 1, 2017 in the Exchange admin center, the In-Place eDiscovery & Hold functionality and the corresponding **\*-MailboxSearch** cmdlets are being retired.</span></span> <span data-ttu-id="1d94c-205">これらのコマンドレットを使用すると、ユーザーは、法的、規制、および公的な要求のためにメールボックスの内容を検索、保持、およびエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-205">These cmdlets provide users the ability to search, hold, and export mailbox content for legal, regulatory, and public requests.</span></span>

<span data-ttu-id="1d94c-206">これらの機能は [<span class="underline">、Microsoft 365</span>](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) コンプライアンス センターと Office 365 セキュリティ & コンプライアンス センターの PowerShell で利用できます。パフォーマンスとスケーラビリティが向上したため、これらの強化されたコマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d94c-206">Because these capabilities are now available in the [<span class="underline">Microsoft 365 compliance center</span>](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) and Office 365 Security & Compliance Center PowerShell with improved performance and scalability, you should using these improved cmdlets.</span></span> <span data-ttu-id="1d94c-207">これらのコマンドレットには[<span class="underline">、-ComplianceCase、-ComplianceSearch、-CaseHoldPolicy、-CaseHoldRule、 \* </span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)および[<span class="underline"> \* -ComplianceSearchAction が含まれます</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)。 [<span class="underline"> \* </span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch) [<span class="underline"> \* </span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy) [<span class="underline"> \* </span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule)</span><span class="sxs-lookup"><span data-stu-id="1d94c-207">These cmdlets include [<span class="underline">\*-ComplianceCase</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase), [<span class="underline">\*-ComplianceSearch</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch), [<span class="underline">\*-CaseHoldPolicy</span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy), [<span class="underline">\*-CaseHoldRule</span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule), and [<span class="underline">\*-ComplianceSearchAction</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction).</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="1d94c-208">影響を受ける組織の範囲</span><span class="sxs-lookup"><span data-stu-id="1d94c-208">Scope of affected organizations</span></span>

- <span data-ttu-id="1d94c-209">Office 365 および Microsoft 365 Enterprise 組織</span><span class="sxs-lookup"><span data-stu-id="1d94c-209">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="1d94c-210">Office 365 および Microsoft 365 Education 組織</span><span class="sxs-lookup"><span data-stu-id="1d94c-210">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="1d94c-211">Office 365 および Microsoft 365 Government 組織これには、GCC、GCC High、DoD が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-211">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="1d94c-212">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="1d94c-212">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="1d94c-213">タイムライン</span><span class="sxs-lookup"><span data-stu-id="1d94c-213">Timeline</span></span>

- <span data-ttu-id="1d94c-214">2020 年 7 月 1 日: **New-MailboxSearch** を使用して新しい In-Place 電子情報開示検索と In-Place 保留リストを作成することはできませんが、コマンドレットを使用して、既存の検索と保持を実行、編集、および削除することができます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-214">July 1, 2020: You won't be able to use **New-MailboxSearch** to create new In-Place eDiscovery searches and In-Place Holds, but you can still use cmdlets to run, edit, and delete existing searches and holds at your own risk.</span></span> <span data-ttu-id="1d94c-215">Microsoft サポートは、これらの種類の検索と保留リストに対するサポートを提供しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="1d94c-215">Microsoft Support will no longer provide assistance for these types of searches and holds.</span></span>

- <span data-ttu-id="1d94c-216">2020 年 10 月 1 日: 前に説明したように、EAC の In-Place 電子情報開示 & 保留機能は読み取り専用モードになります。</span><span class="sxs-lookup"><span data-stu-id="1d94c-216">October 1, 2020: As previously stated, The In-Place eDiscovery & Holds functionality in the EAC will be placed in a read-only mode.</span></span> <span data-ttu-id="1d94c-217">つまり **、New-MailboxSearch、Start-MailboxSearch、\*\*\*\*または Set-MailboxSearch** コマンドレットを使用することはできません。 </span><span class="sxs-lookup"><span data-stu-id="1d94c-217">That also means that you won't be able to use the **New-MailboxSearch**, **Start-MailboxSearch**, or **Set-MailboxSearch** cmdlets.</span></span> <span data-ttu-id="1d94c-218">既存の検索と保留リストのみを取得および削除できます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-218">You'll only be able to get and remove existing searches and holds.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="1d94c-219">代替ツール</span><span class="sxs-lookup"><span data-stu-id="1d94c-219">Alternative tools</span></span>

<span data-ttu-id="1d94c-220">次の表に、廃止される既存の機能を置き換える場合に使用できるその他のツールを示します。</span><span class="sxs-lookup"><span data-stu-id="1d94c-220">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="1d94c-221">機能</span><span class="sxs-lookup"><span data-stu-id="1d94c-221">Functionality</span></span></th>
<th><span data-ttu-id="1d94c-222">代替ツール</span><span class="sxs-lookup"><span data-stu-id="1d94c-222">Alternative tools</span></span></th>
<th><span data-ttu-id="1d94c-223">コメント</span><span class="sxs-lookup"><span data-stu-id="1d94c-223">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="1d94c-224">検索とエクスポート</span><span class="sxs-lookup"><span data-stu-id="1d94c-224">Search and export</span></span></td>
<td><p><span data-ttu-id="1d94c-225"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span><span class="sxs-lookup"><span data-stu-id="1d94c-225"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="1d94c-226"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span><span class="sxs-lookup"><span data-stu-id="1d94c-226"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p><span data-ttu-id="1d94c-227"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span><span class="sxs-lookup"><span data-stu-id="1d94c-227"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span></span></p>
<p> </p></td>
<td><p><span data-ttu-id="1d94c-228">ComplianceSearch コマンドレットと ComplianceSearchAction コマンドレットは、コンテンツの検索とエクスポートに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-228">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and export content.</span></span> <span data-ttu-id="1d94c-229">New-、Get-、および<strong>Start-ComplianceSearch</strong>コマンドレット<strong></strong>を使用して<strong></strong>、新しい検索を作成し、検索の見積もりを表示できます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-229">You can create a new search and view the search estimate by using the <strong>New-</strong>, <strong>Get-</strong>, and <strong>Start-ComplianceSearch</strong> cmdlets.</span></span> <span data-ttu-id="1d94c-230">その後 <strong>、New-ComplianceSearchAction コマンドレット</strong> を使用して検索結果をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-230">Then you can use the <strong>New-ComplianceSearchAction</strong> cmdlet to export the search results.</span></span> <span data-ttu-id="1d94c-231">これらの検索結果をローカル コンピューターにダウンロードするには、Microsoft 365 コンプライアンス センターのコア電子情報開示ツールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d94c-231">You'll still have to use the core eDiscovery tool in the Microsoft 365 compliance center to download those search results to your local computer.</span></span></p>
<p>
<p><span data-ttu-id="1d94c-232"><strong>注:</strong>これらのコマンドレットを使用して、コア電子情報開示ケースに関連付けされていない検索を作成する場合、これらの検索は Microsoft 365<strong></strong>コンプライアンス センターの [コンテンツ検索] ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-232"><strong>Note:</strong> If you use these cmdlets to create searches that aren't associated with a core eDiscovery case, these searches will be located on the <strong>Content search</strong> page in the Microsoft 365 compliance center.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1d94c-233">メールボックス内のコンテンツを保持する</span><span class="sxs-lookup"><span data-stu-id="1d94c-233">Hold content in a mailbox</span></span></td>
<td><p><span data-ttu-id="1d94c-234"><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy"><span class="underline">\*-CaseHoldPolicy</span></a></span><span class="sxs-lookup"><span data-stu-id="1d94c-234"><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy"><span class="underline">\*-CaseHoldPolicy</span></a></span></span></p>
<p><span data-ttu-id="1d94c-235"><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule"><span class="underline">\*-CaseHoldRule</span></a></span><span class="sxs-lookup"><span data-stu-id="1d94c-235"><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule"><span class="underline">\*-CaseHoldRule</span></a></span></span></p>
<p><span data-ttu-id="1d94c-236"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span><span class="sxs-lookup"><span data-stu-id="1d94c-236"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span></span></p>
<p> </p></td>
<td><p><span data-ttu-id="1d94c-237">Microsoft 365 コンプライアンス センターの保留は、ComplianceCase に関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d94c-237">Holds in the Microsoft 365 compliance center must be associated with a ComplianceCase.</span></span> <span data-ttu-id="1d94c-238">まず、コンプライアンス ケースを作成し、次に CaseHoldPolicy と CaseHoldRule を作成します。</span><span class="sxs-lookup"><span data-stu-id="1d94c-238">First, create the compliance case, and then create a CaseHoldPolicy and a CaseHoldRule.</span></span></p>
<p><span data-ttu-id="1d94c-239"><strong>注:</strong> CaseHoldRule を作成せずに CaseHoldPolicy を作成すると、CaseHoldRule が作成され、CaseHoldPolicy に関連付けられるまで、ホールドは操作できません。</span><span class="sxs-lookup"><span data-stu-id="1d94c-239"><strong>Note:</strong> Creating a CaseHoldPolicy without a creating CaseHoldRule will render the hold inoperable until the CaseHoldRule is created and associated to the CaseHoldPolicy.</span></span> <span data-ttu-id="1d94c-240">詳細については、コマンドレットのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d94c-240">See the cmdlet documentation for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="1d94c-241">検索結果を探索メールボックスにコピーする</span><span class="sxs-lookup"><span data-stu-id="1d94c-241">Copy search results to a discovery mailbox</span></span></td>
<td><span data-ttu-id="1d94c-242">なし</span><span class="sxs-lookup"><span data-stu-id="1d94c-242">None</span></span></td>
<td><span data-ttu-id="1d94c-243">この機能は、すべての Microsoft 365 サービスにアクセスできないので、直接置き換えはありません。</span><span class="sxs-lookup"><span data-stu-id="1d94c-243">There's no direct replacement for this functionality because it does not provide access to all Microsoft 365 services.</span></span> <span data-ttu-id="1d94c-244">代替ソリューションについては、以下の FAQ を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d94c-244">See the following FAQ below for alternative solutions.</span></span></td>
</tr>
  <tr class=even>
  <td><span data-ttu-id="1d94c-245">1 つのメールボックスから別のメールボックスにメッセージをコピーする</span><span class="sxs-lookup"><span data-stu-id="1d94c-245">Copy messages from one mailbox to a different mailbox</span></span></td>
  <td><span data-ttu-id="1d94c-246"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">メールボックスへのアクセス許可の割り当て</a></span><span class="sxs-lookup"><span data-stu-id="1d94c-246"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
  <td><span data-ttu-id="1d94c-247">別のユーザーの電子メールへのアクセス権をユーザーに付与するには (従業員が組織を離れ、別のユーザーに元従業員の電子メールへのアクセス権を付与する必要がある場合など)、そのユーザーに元従業員のメールボックスへのアクセス許可を割り当て推奨します。</span><span class="sxs-lookup"><span data-stu-id="1d94c-247">To give a person access to another user's email (such as when an employee leaves your organization and you need to give another person access to the former employee's email), we recommended that you assign that person permissions to access the former employee's mailbox.</span></span> <span data-ttu-id="1d94c-248">そのため、メールボックス アイテムを別のユーザーのメールボックスまたは共有メールボックスにコピーする代わりに、ソース メールボックスにアクセスするためのアクセス許可をユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d94c-248">So instead of copying mailbox items to another user mailbox or a shared mailbox, just assign a user permissions to access the source mailbox.</span></span></td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a><span data-ttu-id="1d94c-249">\***-MailboxSearch コマンドレットに関する** FAQ</span><span class="sxs-lookup"><span data-stu-id="1d94c-249">FAQs about \***-MailboxSearch** cmdlets</span></span>

<span data-ttu-id="1d94c-250">**コピー検索を使用して、他の電子情報開示や法的調査のために、電子メール メッセージまたはインスタント メッセージをエクスポートします。これらのコマンドレットが廃止された後、他にどのようなオプションがありますか?**</span><span class="sxs-lookup"><span data-stu-id="1d94c-250">**We use Copy Search to export email messages or instant Messages for purposes other eDiscovery and legal investigations. What other options do we have after these cmdlets are retired?**</span></span>

<span data-ttu-id="1d94c-251">[<span class="underline">Microsoft Graph API</span>](https://developer.microsoft.com/en-us/graph)は、-MailboxSearch コマンドレットを使用する方法よりもはるかに回復力があり、拡張性に優れた、分析などの目的でデータを **\*** 抽出するための多くの方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="1d94c-251">The [<span class="underline">Microsoft Graph APIs</span>](https://developer.microsoft.com/en-us/graph) provide a number of methods for extracting data for analysis and other purposes that are far more resilient and scalable than the using the **\*-MailboxSearch** cmdlets.</span></span>

<span data-ttu-id="1d94c-252">**検索と保留を Microsoft 365 コンプライアンス センターに移行する方法**</span><span class="sxs-lookup"><span data-stu-id="1d94c-252">**How can I migrate my searches and holds to the Microsoft 365 compliance center?**</span></span>

<span data-ttu-id="1d94c-253">PowerShell スクリプトを使用In-Place Exchange 管理センターから電子情報開示の検索と保留を移行できます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-253">It's possible to migrate In-Place eDiscovery searches and holds from the Exchange admin center by using a PowerShell script.</span></span> <span data-ttu-id="1d94c-254">詳細については、「従来の電子情報開示の検索と保留を [Microsoft 365](migrate-legacy-eDiscovery-searches-and-holds.md)コンプライアンス センターに移行する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d94c-254">For more information, see [Migrate legacy eDiscovery searches and holds to the Microsoft 365 compliance center](migrate-legacy-eDiscovery-searches-and-holds.md).</span></span>

<span data-ttu-id="1d94c-255">**コマンドレットが廃止された後でも、検索を削除または取得できますか?**</span><span class="sxs-lookup"><span data-stu-id="1d94c-255">**After the cmdlets are retired, will I still be able to remove or retrieve searches?**</span></span>

<span data-ttu-id="1d94c-256">はい。検索を作成および変更する機能は削除しますが **、Get-MailboxSearch** と **Remove-MailboxSearch** は、さらに通知されるまで引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-256">Yes, although we're removing the ability to create and modify searches, you'll still be able to use **Get-MailboxSearch** and **Remove-MailboxSearch** until further notice.</span></span> <span data-ttu-id="1d94c-257">ただし、これらのコマンドレットの使用は、終了日後にユーザー自身のリスクにさらされ、Microsoft サポートはサポートを提供できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="1d94c-257">However, the use of these cmdlets will be at your own risk after the retirement dates and Microsoft Support will no longer be able to provide assistance.</span></span>

## <a name="search-mailbox-cmdlet"></a><span data-ttu-id="1d94c-258">Search-Mailboxコマンドレット</span><span class="sxs-lookup"><span data-stu-id="1d94c-258">Search-Mailbox cmdlet</span></span>

<span data-ttu-id="1d94c-259">Exchange Online PowerShell の **Search-Mailbox** コマンドレットは、2018 年からコマンドレット出力の警告で最初に発表されたので廃止されます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-259">The **Search-Mailbox** cmdlet in Exchange Online PowerShell is being retired as originally announced in a warning in the cmdlet output starting back in 2018.</span></span> <span data-ttu-id="1d94c-260">**Search-Mailbox コマンドレットは**、もともとユーザーのメールボックスを検索し、悪意のあるコンテンツを削除するために使用されています。</span><span class="sxs-lookup"><span data-stu-id="1d94c-260">The **Search-Mailbox** cmdlet was originally used to search a user's mailbox and purge malicious content.</span></span> <span data-ttu-id="1d94c-261">Office 365 Security & Compliance Center PowerShell で **New-ComplianceSearch** コマンドレットと **New-ComplianceSearchAction** コマンドレットを使用して、コンテンツの検索と削除を開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1d94c-261">We recommend that you start using the **New-ComplianceSearch** and **New-ComplianceSearchAction** cmdlets in Office 365 Security & Compliance Center PowerShell to search for and purge content.</span></span> <span data-ttu-id="1d94c-262">組み込みのセキュリティ エクスペリエンスのために [<span class="underline">、Microsoft 365 のセキュリティ</span>](https://docs.microsoft.com/microsoft-365/security/) 機能は、電子メールや他の多くの Microsoft サービスに対して堅牢な脅威保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="1d94c-262">For a built-in security experience, the [<span class="underline">Microsoft 365 security features</span>](https://docs.microsoft.com/microsoft-365/security/) provide robust threat protection for email and many other Microsoft services.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="1d94c-263">影響を受ける組織の範囲</span><span class="sxs-lookup"><span data-stu-id="1d94c-263">Scope of affected organizations</span></span>

- <span data-ttu-id="1d94c-264">Office 365 および Microsoft 365 Enterprise 組織</span><span class="sxs-lookup"><span data-stu-id="1d94c-264">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="1d94c-265">Office 365 および Microsoft 365 Education 組織</span><span class="sxs-lookup"><span data-stu-id="1d94c-265">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="1d94c-266">Office 365 および Microsoft 365 Government 組織これには、GCC、GCC High、DoD が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-266">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="1d94c-267">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="1d94c-267">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="1d94c-268">タイムライン</span><span class="sxs-lookup"><span data-stu-id="1d94c-268">Timeline</span></span>

-  <span data-ttu-id="1d94c-269">2020 年 7 月 1 日: **Search-Mailbox** コマンドレットは使用できなくなったので、Microsoft サポートはサポートを提供しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="1d94c-269">July 1, 2020: The **Search-Mailbox** cmdlet will no longer be available and Microsoft Support will no longer provide assistance.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="1d94c-270">代替ツール</span><span class="sxs-lookup"><span data-stu-id="1d94c-270">Alternative tools</span></span>

<span data-ttu-id="1d94c-271">次の表に、廃止される既存の機能を置き換える場合に使用できるその他のツールを示します。</span><span class="sxs-lookup"><span data-stu-id="1d94c-271">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="1d94c-272">機能</span><span class="sxs-lookup"><span data-stu-id="1d94c-272">Functionality</span></span></th>
<th><span data-ttu-id="1d94c-273">代替ツール</span><span class="sxs-lookup"><span data-stu-id="1d94c-273">Alternative tools</span></span></th>
<th><span data-ttu-id="1d94c-274">コメント</span><span class="sxs-lookup"><span data-stu-id="1d94c-274">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="1d94c-275">メールボックスを検索する</span><span class="sxs-lookup"><span data-stu-id="1d94c-275">Search a mailbox</span></span></td>
<td><p><span data-ttu-id="1d94c-276"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span><span class="sxs-lookup"><span data-stu-id="1d94c-276"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="1d94c-277"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span><span class="sxs-lookup"><span data-stu-id="1d94c-277"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p></a></p></td>
<td><p><span data-ttu-id="1d94c-278">ComplianceSearch コマンドレットと ComplianceSearchAction コマンドレットは、コンテンツの検索とエクスポートに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-278">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and export content.</span></span> <span data-ttu-id="1d94c-279">New-、Get-、および<strong>Start-ComplianceSearch</strong>コマンドレット<strong></strong>を使用して<strong></strong>、新しい検索を作成し、検索の見積もりを表示できます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-279">You can create a new search and view the search estimate by using the <strong>New-</strong>, <strong>Get-</strong>, and <strong>Start-ComplianceSearch</strong> cmdlets.</span></span> <span data-ttu-id="1d94c-280">次に <strong>、New-ComplianceSearchAction -Export</strong> コマンドを使用して検索結果をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-280">Then you can use the <strong>New-ComplianceSearchAction -Export</strong> command to export the search results.</span></span> <span data-ttu-id="1d94c-281">これらの検索結果をローカル コンピューターにダウンロードするには、Microsoft 365 コンプライアンス センターのコア電子情報開示ツールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d94c-281">You'll still have to use the core eDiscovery tool in the Microsoft 365 compliance center to download those search results to your local computer.</span></span></p></p>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="1d94c-282">メールボックスからバルク メールを削除する</span><span class="sxs-lookup"><span data-stu-id="1d94c-282">Delete bulk email from a mailbox</span></span></td>
<td><p><span data-ttu-id="1d94c-283"><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">メールボックスのアーカイブと削除ポリシーを設定する</span></a></span><span class="sxs-lookup"><span data-stu-id="1d94c-283"><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">Set up an archive and deletion policy for mailboxes</span></a></span></span></p>
<p></p></td>
<td><p><span data-ttu-id="1d94c-284">管理者は、アイテムをユーザーのアーカイブ メールボックスに自動的に移動し、メールボックスからアイテムを自動的に削除するアーカイブおよび削除ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-284">Admins can create an archiving and deletion policy that automatically moves items to a user's archive mailbox and automatically deletes items from the mailbox.</span></span></p>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="1d94c-285">検索結果を探索メールボックスにコピーする</span><span class="sxs-lookup"><span data-stu-id="1d94c-285">Copy search results to a discovery mailbox</span></span></td>
<td> </td>
<td><span data-ttu-id="1d94c-286">この機能は、すべての Microsoft 365 サービスにアクセスできないので、直接置き換えはありません。</span><span class="sxs-lookup"><span data-stu-id="1d94c-286">There's no direct replacement for this functionality because it does not provide access to all Microsoft 365 services.</span></span> <span data-ttu-id="1d94c-287">代替ソリューションについては <strong>、「\*-MailboxSearch コマンドレット</strong> 」セクションの FAQ を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d94c-287">See the FAQs in the <strong>\*-MailboxSearch cmdlets</strong> section for alternative solutions.</span></span> </td>
</tr>
<tr class=odd>
  <td><span data-ttu-id="1d94c-288">1 つのメールボックスから別のメールボックスにメッセージをコピーする</span><span class="sxs-lookup"><span data-stu-id="1d94c-288">Copy messages from one mailbox to a different mailbox</span></span></td>
  <td><span data-ttu-id="1d94c-289"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">メールボックスへのアクセス許可の割り当て</a></span><span class="sxs-lookup"><span data-stu-id="1d94c-289"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
  <td><span data-ttu-id="1d94c-290">別のユーザーの電子メールへのアクセス権をユーザーに付与するには (従業員が組織を離れ、別のユーザーに元従業員の電子メールへのアクセス権を付与する必要がある場合など)、そのユーザーに元従業員のメールボックスへのアクセス許可を割り当て推奨します。</span><span class="sxs-lookup"><span data-stu-id="1d94c-290">To give a person access to another user's email (such as when an employee leaves your organization and you need to give another person access to the former employee's email), we recommended that you assign that person permissions to access the former employee's mailbox.</span></span> <span data-ttu-id="1d94c-291">そのため、メールボックス アイテムを別のユーザーのメールボックスまたは共有メールボックスにコピーする代わりに、ソース メールボックスにアクセスするためのアクセス許可をユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d94c-291">So instead of copying mailbox items to another user mailbox or a shared mailbox, just assign a user permissions to access the source mailbox.</span></span></td>
</tr>
<tr class=even>
  <td><span data-ttu-id="1d94c-292">メールボックスからメッセージを消去する</span><span class="sxs-lookup"><span data-stu-id="1d94c-292">Purge messages from a mailbox</span></span></td>
<td><p><span data-ttu-id="1d94c-293"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span><span class="sxs-lookup"><span data-stu-id="1d94c-293"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="1d94c-294"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span><span class="sxs-lookup"><span data-stu-id="1d94c-294"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p></p></td>
<td><p><span data-ttu-id="1d94c-295">ComplianceSearch コマンドレットと ComplianceSearchAction コマンドレットは、コンテンツの検索と削除に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-295">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and purge content.</span></span> <span data-ttu-id="1d94c-296"><strong>New-ComplianceSearch</strong>コマンドレットと<strong>New-ComplianceSearch</strong>コマンドレットを使用して検索を作成して実行し<strong>、New-ComplianceSearchAction -Purge -PurgeType</strong>コマンドを使用してコンテンツを削除できます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-296">You can create and run a search with <strong>New-ComplianceSearch</strong> and <strong>New-ComplianceSearch</strong> cmdlets, and then you can purge the content by using <strong>New-ComplianceSearchAction -Purge -PurgeType</strong> command.</span></span> <span data-ttu-id="1d94c-297">詳細については、「メッセージの検索 <a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">と削除」を参照してください</span></a>。</span><span class="sxs-lookup"><span data-stu-id="1d94c-297">For more information, see <a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">Search for and delete messages</span></a>.</span></span></p>
</td>
</tr>
<tr class="odd"> 
<td><span data-ttu-id="1d94c-298">メールボックスからメッセージを消去する</span><span class="sxs-lookup"><span data-stu-id="1d94c-298">Purge messages from a mailbox</span></span></td>
<td><span data-ttu-id="1d94c-299"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">メールボックスへのアクセス許可の割り当て</a></span><span class="sxs-lookup"><span data-stu-id="1d94c-299"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
<td><span data-ttu-id="1d94c-300">メールボックスからメッセージを削除するには、従業員のメールボックスにアクセスするための管理者権限を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d94c-300">To purge messages from a mailbox, assign an administrator permissions to access the employee's mailbox.</span></span> <span data-ttu-id="1d94c-301">Outlook の組み込みの検索および表示機能を利用して、必要に応じてメッセージを削除およびリサイクルできます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-301">Messages can be deleted and recycled as needed taking advantage of the built in search and viewing capabilities in Outlook.</span></span></td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a><span data-ttu-id="1d94c-302">Exchange Web サービス API の操作</span><span class="sxs-lookup"><span data-stu-id="1d94c-302">Exchange Web Services API operations</span></span>

<span data-ttu-id="1d94c-303">Exchange Web サービス API のこれらの操作は、Exchange 管理センターの In-Place 電子情報開示 & 保留リスト機能と、Exchange Online PowerShell の対応する **\* -MailboxSearch** コマンドレットによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-303">These operations in the Exchange Web Services API are used by the In-Place eDiscovery & Holds feature in the Exchange admin center and the corresponding **\*-MailboxSearch** cmdlets in Exchange Online PowerShell.</span></span> <span data-ttu-id="1d94c-304">また、他の従来の電子情報開示ツールの廃止の一環として廃止されます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-304">They will also be retired as part of retiring the other legacy eDiscovery tools.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="1d94c-305">影響を受ける組織の範囲</span><span class="sxs-lookup"><span data-stu-id="1d94c-305">Scope of affected organizations</span></span>

- <span data-ttu-id="1d94c-306">Office 365 および Microsoft 365 Enterprise 組織</span><span class="sxs-lookup"><span data-stu-id="1d94c-306">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="1d94c-307">Office 365 および Microsoft 365 Education 組織</span><span class="sxs-lookup"><span data-stu-id="1d94c-307">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="1d94c-308">Office 365 および Microsoft 365 Government 組織これには、GCC、GCC High、DoD が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-308">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="1d94c-309">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="1d94c-309">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="1d94c-310">タイムライン</span><span class="sxs-lookup"><span data-stu-id="1d94c-310">Timeline</span></span>

- <span data-ttu-id="1d94c-311">2020 年 7 月 1 日: GetSearchableMailboxes、SearchMailboxes、SetHoldOnMailboxes、および GetHoldOnMailboxes 操作は利用できなくなりました。また、Microsoft サポートはサポートを提供しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="1d94c-311">July 1, 2020: The GetSearchableMailboxes, SearchMailboxes, SetHoldOnMailboxes, and GetHoldOnMailboxes operations will no longer be available, and Microsoft Support will no longer provide assistance.</span></span>

## <a name="advanced-ediscovery-v10"></a><span data-ttu-id="1d94c-312">Advanced eDiscovery v1.0</span><span class="sxs-lookup"><span data-stu-id="1d94c-312">Advanced eDiscovery v1.0</span></span>

<span data-ttu-id="1d94c-313">Advanced eDiscovery v1.0 は、Advanced eDiscovery への切り替えボタンをクリックしてコアの電子情報開示ケースで利用できる Advanced **eDiscovery** のバージョンで廃止されます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-313">Advanced eDiscovery v1.0, which is the version of Advanced eDiscovery available in a core eDiscovery case by clicking **Switch to Advanced eDiscovery**, is being retired.</span></span> <span data-ttu-id="1d94c-314">その機能は、Microsoft 365 コンプライアンス センターの新しい [Advanced eDiscovery](https://aka.ms/edisco) ソリューションに置き換えられた。</span><span class="sxs-lookup"><span data-stu-id="1d94c-314">Its functionality has been replaced by the new [Advanced eDiscovery solution](https://aka.ms/edisco) in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="1d94c-315">組織が Advanced eDiscovery v1.0 を使用しているかどうかを確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1d94c-315">To determine if your organization is using Advanced eDiscovery v1.0:</span></span>

1. <span data-ttu-id="1d94c-316">[Office 365 セキュリティ/コンプライアンス センター&します](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="1d94c-316">Go to the [Office 365 Security & Compliance Center](https://protection.office.com).</span></span>

2. <span data-ttu-id="1d94c-317">セキュリティ/コンプライアンス センターの左側のナビゲーション ウィンドウで&電子情報開示の>をクリックし、Core 電子情報開示ケースを開きます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-317">In the left navigation pane of the Security & Compliance Center, click **eDiscovery > eDiscovery**, and open a Core eDiscovery case.</span></span>

3. <span data-ttu-id="1d94c-318">[Advanced **eDiscovery** に切り替える] ボタンが表示された場合、それをクリックすると 1.0 バージョンの Advanced eDiscovery に移動し、廃止されます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-318">If you see the **Switch to Advanced eDiscovery** button, then clicking it will take you to the 1.0 version of Advanced eDiscovery, which is being retired.</span></span> <span data-ttu-id="1d94c-319">コア電子情報開示でケースを作成および管理する機能は影響を受け取らない。</span><span class="sxs-lookup"><span data-stu-id="1d94c-319">The ability to create and manage cases in Core eDiscovery won't be affected.</span></span> <span data-ttu-id="1d94c-320">Advanced eDiscovery v1.0 で ([Advanced **eDiscovery** に切り替える] をクリックして) ケース データを追加および分析する機能だけが廃止されます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-320">Only the ability to add and analyze case data in Advanced eDiscovery v1.0 (by clicking **Switch to Advanced eDiscovery**) is being retired.</span></span>

<span data-ttu-id="1d94c-321">Microsoft 365 の新しい Advanced eDiscovery ソリューション *(Advanced eDiscovery v2.0* とも呼ばれる) は、元のソリューションのすべての機能を提供しますが、現在では、他の Microsoft 365 サービスのコンテンツを識別し、そのコンテンツを収集し、レビュー担当者が高速検索クエリ、タグ付け、分析機能を利用して関連ドキュメントを作成できるレビュー セットに追加するカストディアン ベースのアプローチが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1d94c-321">The new Advanced eDiscovery solution in Microsoft 365 (also known as *Advanced eDiscovery v2.0*) provides all of the capabilities of the original solution, but now includes a custodian-based approach of identifying content in other Microsoft 365 services, collecting that content, and then adding it to a review set where reviewers can take advantage of fast search queries, tagging, and analytics features to help cull relevant documents.</span></span> <span data-ttu-id="1d94c-322">Advanced eDiscovery には、Microsoft と Microsoft 以外の両方のファイルの種類の処理とネイティブ ビューアーが改善されました。ファイルの種類の完全な一覧が [ここに](https://docs.microsoft.com/microsoft-365/compliance/supported-filetypes-ediscovery20) 記載され、サポートされているメタデータ フィールドがここに [含まれています](https://docs.microsoft.com/microsoft-365/compliance/document-metadata-fields-in-advanced-ediscovery)。</span><span class="sxs-lookup"><span data-stu-id="1d94c-322">Advanced eDiscovery now includes improved processing and native viewers for both Microsoft and non-Microsoft file types, a full list of file types is [here](https://docs.microsoft.com/microsoft-365/compliance/supported-filetypes-ediscovery20) and supported metadata fields are [here](https://docs.microsoft.com/microsoft-365/compliance/document-metadata-fields-in-advanced-ediscovery).</span></span> <span data-ttu-id="1d94c-323">また、新しい Advanced eDiscovery ソリューションは強力な保管担当者保留管理機能を提供します。この管理機能を使用すると、さまざまなサービスのコンテンツに保留を適用し、保留をユーザーに通知し、保管担当者の応答を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-323">Also, the new Advanced eDiscovery solution provides a powerful custodian holds management feature that lets you apply holds to content in different services, notify users of the holds, and track custodian responses, all within an Advanced eDiscovery case.</span></span>

<span data-ttu-id="1d94c-324">Advanced eDiscovery v2.0 へのアクセス</span><span class="sxs-lookup"><span data-stu-id="1d94c-324">To access Advanced eDiscovery v2.0:</span></span>

1. <span data-ttu-id="1d94c-325">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com) にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="1d94c-325">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="1d94c-326">Microsoft 365 コンプライアンス センターの左側のナビゲーション ウィンドウで、[**すべてを表示**] をクリックし、**[eDiscovery] > [Advanced]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d94c-326">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Advanced**.</span></span>

<span data-ttu-id="1d94c-327">現時点では、電子情報開示ワークフローの新しい Advanced eDiscovery 機能への移行を開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1d94c-327">At this time, we recommend that you begin to transition your eDiscovery workflow to the new Advanced eDiscovery functionality.</span></span> <span data-ttu-id="1d94c-328">必要に応じて、コンテンツをエクスポートしてオフラインで保存することで、Advanced eDiscovery 1.0 ケースをアーカイブできます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-328">If required, you can archive your Advanced eDiscovery 1.0 cases by exporting the content and storing it offline.</span></span> <span data-ttu-id="1d94c-329">既存のケースでは、2020 年 12 月 31 日まで Advanced eDiscovery v1.0 に引き続きアクセスすることができますが、2020 年 10 月 1 日以降、Microsoft サポートはサポートを提供し続けなかった。</span><span class="sxs-lookup"><span data-stu-id="1d94c-329">Although you'll still be able to access Advanced eDiscovery v1.0 in existing cases until December 31, 2020, Microsoft Support won't provide support after October 1, 2020.</span></span> <span data-ttu-id="1d94c-330">詳細については、次のタイムラインを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d94c-330">See the following timeline for more details.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="1d94c-331">影響を受ける組織の範囲</span><span class="sxs-lookup"><span data-stu-id="1d94c-331">Scope of affected organizations</span></span>

- <span data-ttu-id="1d94c-332">Office 365 および Microsoft 365 Enterprise 組織</span><span class="sxs-lookup"><span data-stu-id="1d94c-332">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="1d94c-333">Office 365 および Microsoft 365 Education 組織</span><span class="sxs-lookup"><span data-stu-id="1d94c-333">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="1d94c-334">Office 365 および Microsoft 365 Government 組織これには、GCC、GCC High、DoD が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-334">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="1d94c-335">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="1d94c-335">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="1d94c-336">タイムライン</span><span class="sxs-lookup"><span data-stu-id="1d94c-336">Timeline</span></span>

- <span data-ttu-id="1d94c-337">2020 年 7 月 1 日: 新しい Advanced eDiscovery v1.0 ケースを作成できない。</span><span class="sxs-lookup"><span data-stu-id="1d94c-337">July 1, 2020: You won't be able to create new Advanced eDiscovery v1.0  cases.</span></span>

- <span data-ttu-id="1d94c-338">2020 年 10 月 1 日: 新しいデータ (Advanced eDiscovery の検索結果を準備する) をケースに追加できない。</span><span class="sxs-lookup"><span data-stu-id="1d94c-338">October 1, 2020: You won't be able to add new data (Prepare search results for Advanced eDiscovery) to any cases.</span></span> <span data-ttu-id="1d94c-339">既存のケースでは、自分のリスクでデータの操作を続行できます。</span><span class="sxs-lookup"><span data-stu-id="1d94c-339">You'll be able to continue working with data in existing cases at your own risk.</span></span> <span data-ttu-id="1d94c-340">Microsoft サポートはサポートを提供しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="1d94c-340">Microsoft Support will no longer provide assistance.</span></span> 

- <span data-ttu-id="1d94c-341">2020 年 12 月 31 日: Advanced eDiscovery v1.0 ケースにアクセスできない。</span><span class="sxs-lookup"><span data-stu-id="1d94c-341">December 31, 2020: You won't be able to access Advanced eDiscovery v1.0 cases.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="1d94c-342">代替ツール</span><span class="sxs-lookup"><span data-stu-id="1d94c-342">Alternative tools</span></span>

<span data-ttu-id="1d94c-343">Microsoft 365 コンプライアンス センターの Advanced [eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) ソリューション。</span><span class="sxs-lookup"><span data-stu-id="1d94c-343">The [Advanced eDiscovery solution](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) in the Microsoft 365 compliance center.</span></span>
