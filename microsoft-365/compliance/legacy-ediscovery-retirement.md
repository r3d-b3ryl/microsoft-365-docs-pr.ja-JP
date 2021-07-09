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
description: In-Placeの電子情報開示とIn-Placeホールド (および対応する PowerShell コマンドレット Exchange Online) は、2020 年前半に廃止されます。 また、Search-Mailbox v1.0 Advanced eDiscoveryおよび v1.0 も同じ期間に廃止されます。
ms.openlocfilehash: 77a7daf36c86cd302f774e5a4b934148d3dfd5a7
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "53340998"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a><span data-ttu-id="66142-104">従来の電子情報開示ツールの廃止</span><span class="sxs-lookup"><span data-stu-id="66142-104">Retirement of legacy eDiscovery tools</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66142-105">この記事で説明する従来の電子情報開示ツールの機能は、Microsoft 365 サービスから削除されたか、まだ使用できますが、サポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="66142-105">The functionality of the legacy eDiscovery tools described in this article has either been removed from the Microsoft 365 service or is still available, but no longer supported.</span></span> <span data-ttu-id="66142-106">引き続き使用可能な機能は、予告なしに削除される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="66142-106">Any functionality that's still available may be removed without notice.</span></span> <span data-ttu-id="66142-107">これらのレガシ ツールを引き続き使用している場合は、Microsoft 365 コンプライアンス センター またはこの記事で説明する代替手段の 1 つで、電子情報開示ツールへの移行を検討してください。</span><span class="sxs-lookup"><span data-stu-id="66142-107">If you're still using any of these legacy tools, consider migrating to the eDiscovery tools in the Microsoft 365 compliance center or one of the alternatives described in this article.</span></span>

<span data-ttu-id="66142-108">長年にわたり、Microsoft は電子情報開示ツールを提供し、電子情報開示ツールを使用して、電子メール コンテンツを検索、プレビュー、およびエクスポートExchange Online。</span><span class="sxs-lookup"><span data-stu-id="66142-108">Over the years, Microsoft has provided eDiscovery tools that let you search, preview, and export email content from Exchange Online.</span></span> <span data-ttu-id="66142-109">ただし、これらのツールは、Exchange Online や Microsoft 365 グループなどの他の SharePoint Microsoft 365 サービスで非 Exchange コンテンツを検索する効果的な方法を提供しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="66142-109">However, these tools no longer offer an effective way to search for non-Exchange content in other Microsoft 365 services, such as SharePoint Online and Microsoft 365 Groups.</span></span> <span data-ttu-id="66142-110">この問題に対処するために、Microsoft はさまざまなコンテンツを検索するのに役立つその他の電子情報開示Microsoft 365しています。</span><span class="sxs-lookup"><span data-stu-id="66142-110">To address this, Microsoft offers other eDiscovery tools that help you search for a wide variety of Microsoft 365 content.</span></span> <span data-ttu-id="66142-111">また、最新かつ強力な電子情報開示機能を最新の電子情報開示機能に組み込む[Microsoft 365 コンプライアンス センター。](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="66142-111">And we've been working hard to incorporate the most current and powerful eDiscovery functionality in the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span> <span data-ttu-id="66142-112">これにより、組織は、コンテンツに関する法的、内部的、その他のドキュメント要求に、Microsoft 365サービスを含む多くのExchange Online。</span><span class="sxs-lookup"><span data-stu-id="66142-112">This allows organizations to respond to legal, internal, and other document requests for content across many Microsoft 365 services, including Exchange Online.</span></span>

<span data-ttu-id="66142-113">Microsoft 365 コンプライアンス センター でこの新しく改善された電子情報開示機能の結果、Exchange Online および Microsoft 365 の電子メール コンテンツの検索に関連する次の電子情報開示関連の機能が廃止されました。</span><span class="sxs-lookup"><span data-stu-id="66142-113">As a result of this new and improved eDiscovery functionality in the Microsoft 365 compliance center, we're retiring the following eDiscovery-related features and functionality related to searching for email content in Exchange Online and Microsoft 365:</span></span>

- <span data-ttu-id="66142-114">Exchange 管理センターの[インプレース電子情報開示](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)および[インプレース ホールド](/exchange/security-and-compliance/create-or-remove-in-place-holds)。</span><span class="sxs-lookup"><span data-stu-id="66142-114">[In-Place eDiscovery](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) and [In-Place Holds](/exchange/security-and-compliance/create-or-remove-in-place-holds) in the Exchange admin center.</span></span>

- <span data-ttu-id="66142-115">電子Exchange Onlineおよび In-Place 保持をサポートする power In-Place Shell コマンドレット (これらのコマンドレットは、 \**-MailboxSearch* コマンドレットとしてまとめて識別されます)。</span><span class="sxs-lookup"><span data-stu-id="66142-115">The Exchange Online PowerShell cmdlets that support In-Place eDiscovery and In-Place Holds (these cmdlets are collectively identified as \**-MailboxSearch* cmdlets).</span></span> <span data-ttu-id="66142-116">これには、次のコマンドレットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="66142-116">This includes the following cmdlets:</span></span>

  - [<span data-ttu-id="66142-117">New-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="66142-117">New-MailboxSearch</span></span>](/powershell/module/exchange/new-mailboxsearch)

  - [<span data-ttu-id="66142-118">Start-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="66142-118">Start-MailboxSearch</span></span>](/powershell/module/exchange/start-mailboxsearch)

  - [<span data-ttu-id="66142-119">Stop-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="66142-119">Stop-MailboxSearch</span></span>](/powershell/module/exchange/stop-mailboxsearch)

  - [<span data-ttu-id="66142-120">Set-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="66142-120">Set-MailboxSearch</span></span>](/powershell/module/exchange/set-mailboxsearch)

   > [!NOTE]
   > <span data-ttu-id="66142-121">[Get-MailboxSearch](/powershell/module/exchange/get-mailboxsearch)コマンドレットと[Remove-MailboxSearch](/powershell/module/exchange/remove-mailboxsearch)コマンドレットは、他の \*\*\*\*-MailboxSearch\*\*\* コマンドレットが廃止された後に使用できます。</span><span class="sxs-lookup"><span data-stu-id="66142-121">The [Get-MailboxSearch](/powershell/module/exchange/get-mailboxsearch) and [Remove-MailboxSearch](/powershell/module/exchange/remove-mailboxsearch) cmdlets will be available after the other \*\*\*\*-MailboxSearch\*\*\* cmdlets are retired so that you can use them to help in your transition to other eDiscovery and hold tools.</span></span> <span data-ttu-id="66142-122">ただし、特定の日付 (以下に引用) が終了すると、Microsoft サポートはこれら 2 つのコマンドレットをサポートしなくなりました。</span><span class="sxs-lookup"><span data-stu-id="66142-122">However, after a certain date (cited below) Microsoft Support will no longer supports these two cmdlets.</span></span>

- <span data-ttu-id="66142-123">Exchange Online PowerShell の [Search-Mailbox](/powershell/module/exchange/search-mailbox) コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="66142-123">The [Search-Mailbox](/powershell/module/exchange/search-mailbox) cmdlet in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="66142-124">Exchange Web Services API での次の操作。</span><span class="sxs-lookup"><span data-stu-id="66142-124">The following operations in the Exchange Web Services API:</span></span>

   - [<span data-ttu-id="66142-125">GetSearchableMailboxes</span><span class="sxs-lookup"><span data-stu-id="66142-125">GetSearchableMailboxes</span></span>](/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [<span data-ttu-id="66142-126">SearchMailboxes</span><span class="sxs-lookup"><span data-stu-id="66142-126">SearchMailboxes</span></span>](/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [<span data-ttu-id="66142-127">SetHoldOnMailboxes</span><span class="sxs-lookup"><span data-stu-id="66142-127">SetHoldOnMailboxes</span></span>](/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [<span data-ttu-id="66142-128">GetHoldOnMailboxes</span><span class="sxs-lookup"><span data-stu-id="66142-128">GetHoldOnMailboxes</span></span>](/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- <span data-ttu-id="66142-129">[Office 365 Advanced eDiscovery v1.0](./overview-ediscovery-20.md)は、Office 365 セキュリティ & コンプライアンス センターの Core 電子情報開示ケースを通じてアクセスされる Advanced eDiscovery の最初のバージョンです。</span><span class="sxs-lookup"><span data-stu-id="66142-129">[Office 365 Advanced eDiscovery v1.0](./overview-ediscovery-20.md), which is the first version of Advanced eDiscovery that's accessed through a Core eDiscovery case in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="66142-130">v1.0 のAdvanced eDiscoveryは、コア電子情報開示ケースを作成および管理する機能には影響を与えかねない。</span><span class="sxs-lookup"><span data-stu-id="66142-130">The retirement of Advanced eDiscovery v1.0 doesn't impact your ability to create and manage Core eDiscovery cases.</span></span>

> [!NOTE]
> <span data-ttu-id="66142-131">廃止される電子情報開示機能は、クラウド ベースのバージョンの Microsoft 365およびOffice 365。</span><span class="sxs-lookup"><span data-stu-id="66142-131">The eDiscovery functionality being retired only applies to cloud-based versions of Microsoft 365 and Office 365.</span></span> <span data-ttu-id="66142-132">オンプレミスバージョンの電子情報開示機能は、ExchangeおよびSharePointまで引き続きサポートされます。</span><span class="sxs-lookup"><span data-stu-id="66142-132">eDiscovery functionality in on-premises versions of Exchange and SharePoint will still be supported until further notice.</span></span>

<span data-ttu-id="66142-133">この記事の以下のセクションでは、廃止される各機能に関するガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="66142-133">The following sections in this article provide guidance about each feature being retired.</span></span> <span data-ttu-id="66142-134">この情報には、廃止されたツールの代わりに使用できるタイムラインや代替ツールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="66142-134">This information including timelines and alternative tools that you can use instead of the retired tool.</span></span>

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a><span data-ttu-id="66142-135">In-Place管理センターIn-Place電子情報開示とExchange保持</span><span class="sxs-lookup"><span data-stu-id="66142-135">In-Place eDiscovery and In-Place Holds in the Exchange admin center</span></span> 

<span data-ttu-id="66142-136">2017 年 7 月 1 日の当初の発表と同様に、In-Place 管理センター (EAC) の Exchange In-Place 電子情報開示 & 保留機能は廃止されます。</span><span class="sxs-lookup"><span data-stu-id="66142-136">As per the original announcement on July 1, 2017, the In-Place eDiscovery & Hold functionality in the Exchange admin center (EAC) is being retired.</span></span> <span data-ttu-id="66142-137">EAC In-Place [&保持] ページでは、コンテンツを検索、保持、およびエクスポートExchange Online。</span><span class="sxs-lookup"><span data-stu-id="66142-137">The In-Place eDiscovery & Holds page in the EAC allowed you to search, hold, and export content from Exchange Online.</span></span> <span data-ttu-id="66142-138">In-Place電子情報開示を使用すると、検索結果を探索メールボックスにコピーして、ユーザーまたは他の電子情報開示管理者がコンテンツを確認し、法的、規制、およびパブリック要求に対して利用可能にできます。</span><span class="sxs-lookup"><span data-stu-id="66142-138">In-Place eDiscovery also let you copy search results to a discovery mailbox so that you or other eDiscovery managers could review content and make it available for legal, regulatory, and public requests.</span></span>

<span data-ttu-id="66142-139">これらの機能 (検索結果を探索メールボックスにコピーする場合を除く) はすべて[、Microsoft 365 コンプライアンス センター](./microsoft-365-compliance-center.md)のコンテンツ検索、電子情報開示、および Advanced eDiscovery ツールで利用できます (機能、信頼性、および幅広い Microsoft 365 サービスのサポートが強化されています)、できるだけ早くこれらのツールの使用を開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="66142-139">Because all of these capabilities (except for copying search results to a discovery mailbox) are now available in the content search, eDiscovery and Advanced eDiscovery tools in the [Microsoft 365 compliance center](./microsoft-365-compliance-center.md) (with improved functionality, reliability, and support for a wide range of Microsoft 365 services), we recommend that you start using these tools as soon as possible.</span></span> <span data-ttu-id="66142-140">これらの他の電子情報開示ツールへの移行を支援するために、以下の表に、電子情報開示と電子情報開示の保持ではなくIn-PlaceツールIn-Place示します。</span><span class="sxs-lookup"><span data-stu-id="66142-140">To help you in the transition to these other eDiscovery tools, the table below lists the tools you can use instead of In-Place eDiscovery and In-Place Hold.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="66142-141">影響を受ける組織の範囲</span><span class="sxs-lookup"><span data-stu-id="66142-141">Scope of affected organizations</span></span>

- <span data-ttu-id="66142-142">Office 365およびMicrosoft 365 Enterprise組織</span><span class="sxs-lookup"><span data-stu-id="66142-142">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="66142-143">Office 365およびMicrosoft 365 Education組織</span><span class="sxs-lookup"><span data-stu-id="66142-143">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="66142-144">Office 365およびMicrosoft 365組織。これには、GCC、GCC、DoD が含まれます。</span><span class="sxs-lookup"><span data-stu-id="66142-144">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="66142-145">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="66142-145">Office 365 Germany</span></span>

### <a name="timeline-for-retirement"></a><span data-ttu-id="66142-146">退職のタイムライン</span><span class="sxs-lookup"><span data-stu-id="66142-146">Timeline for retirement</span></span>

- <span data-ttu-id="66142-147">2020 年 7 月 1 日: 新しい検索と保留リストを作成できますが、既存の検索の実行、編集、および削除は、自分のリスクで行います。</span><span class="sxs-lookup"><span data-stu-id="66142-147">July 1, 2020: You won't be able to create new searches and holds, but you can still run, edit, and delete existing searches at your own risk.</span></span> <span data-ttu-id="66142-148">Microsoft サポートは、EAC In-Place保持&電子情報開示を使用しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="66142-148">Microsoft Support will no longer In-Place eDiscovery & Holds in the EAC.</span></span>

- <span data-ttu-id="66142-149">2020 年 10 月 1 日: In-Place電子情報開示 & EAC の保持機能は、読み取り専用モードになります。</span><span class="sxs-lookup"><span data-stu-id="66142-149">October 1, 2020: The In-Place eDiscovery & Holds functionality in the EAC will be placed in a read-only mode.</span></span> <span data-ttu-id="66142-150">これにより、可能な操作は、既存の検索および保留リストの削除のみになります。</span><span class="sxs-lookup"><span data-stu-id="66142-150">This means you'll only be able to remove existing searches and holds.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="66142-151">代替ツール</span><span class="sxs-lookup"><span data-stu-id="66142-151">Alternative tools</span></span>

<span data-ttu-id="66142-152">次の表では、廃止される既存の機能を置き換える他のツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="66142-152">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="66142-153">機能</span><span class="sxs-lookup"><span data-stu-id="66142-153">Functionality</span></span></th>
<th><span data-ttu-id="66142-154">代替ツール</span><span class="sxs-lookup"><span data-stu-id="66142-154">Alternative tool</span></span></th>
<th><span data-ttu-id="66142-155">コメント</span><span class="sxs-lookup"><span data-stu-id="66142-155">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="66142-156">法的な目的で検索、エクスポート、ホールドする</span><span class="sxs-lookup"><span data-stu-id="66142-156">Search, export, and hold for legal purposes</span></span></td>
<td><span data-ttu-id="66142-157">電子情報開示のコア ケース (Microsoft 365 コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="66142-157">Core eDiscovery cases in the Microsoft 365 compliance center</span></span> </td>
<td><p><span data-ttu-id="66142-158">コアの電子情報開示ケースの機能を使用すると、電子情報開示と保留リストのIn-PlaceパリティIn-Placeします。</span><span class="sxs-lookup"><span data-stu-id="66142-158">Using the capabilities of core eDiscovery cases provide the functional parity to In-Place eDiscovery and In-Place Holds.</span></span> <span data-ttu-id="66142-159">エクスポートできるものには、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="66142-159">This includes the following:</span></span></p>
<ul>
<li>
<p><span data-ttu-id="66142-160">検索は数百万の場所に拡大縮小されます。</span><span class="sxs-lookup"><span data-stu-id="66142-160">Search scales to millions of locations</span></span></p>
</li>
<li>
<p><span data-ttu-id="66142-161">コンテンツの検索、エクスポート、および保留に関する信頼性の向上</span><span class="sxs-lookup"><span data-stu-id="66142-161">Higher reliability for searching, exporting, and placing content on hold</span></span></p>
</li>
<li>
<p><span data-ttu-id="66142-162">Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft Teams、Yammer グループ、Microsoft 365 グループ、Office 365 アプリケーションに保存されている他のコンテンツの検索</span><span class="sxs-lookup"><span data-stu-id="66142-162">Searching for content in for Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams, Yammer Groups, Microsoft 365 Groups, and other content stored in Office 365 applications</span></span></p></li></ul>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="66142-163">保持の目的で保持する</span><span class="sxs-lookup"><span data-stu-id="66142-163">Hold for retention purposes</span></span></td>
<td><span data-ttu-id="66142-164">アイテム保持ポリシーのMicrosoft 365 コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="66142-164">Retention policies in the Microsoft 365 compliance center</span></span></td>
<td><p><span data-ttu-id="66142-165">アイテム保持ポリシーを使用してコンテンツを保持し、必要に応じて保持期間が経過した後に削除できます。</span><span class="sxs-lookup"><span data-stu-id="66142-165">You can use Retention policies to retain content and, if desired, delete it after the retention period expires.</span></span> <span data-ttu-id="66142-166">その他の機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="66142-166">Other capabilities include:</span></span></p>
<ul>
<li>
<p><span data-ttu-id="66142-167">組織全体にポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="66142-167">Applying policies to your entire organization</span></span> </p>
</li><li>
<p><span data-ttu-id="66142-168">Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft Teams、Office 365 グループなどの特定のコンテンツの場所にポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="66142-168">Applying policies to specific content locations such as Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams, and Office 365 Groups</span></span></p></li>
<li>
<p><span data-ttu-id="66142-169">特定のユーザーにポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="66142-169">Applying policies to specific users</span></span></p></li></ul>
<p><span data-ttu-id="66142-170">詳細については、「アイテム保持ポリシー <a href="/microsoft-365/compliance/retention-policies"> と保持ラベルについて」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="66142-170">For more information, see <a href="/microsoft-365/compliance/retention-policies"> Learn about retention policies and retention labels</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="66142-171">確認のために電子メール検索結果を探索メールボックスにコピーする</span><span class="sxs-lookup"><span data-stu-id="66142-171">Copy email search results to a discovery mailbox for review</span></span></td><td><span data-ttu-id="66142-172">v2.0 でAdvanced eDiscoveryを確認する</span><span class="sxs-lookup"><span data-stu-id="66142-172">Review sets in Advanced eDiscovery v2.0</span></span></td>
<td><p><span data-ttu-id="66142-173">サイト内のコンテンツMicrosoft 365簡単に確認できます。</span><span class="sxs-lookup"><span data-stu-id="66142-173">Reviewing content in Microsoft 365 has never been easier.</span></span> <span data-ttu-id="66142-174">レビュー セットには、次を含む、レビューに必要な時間とデータの削減に役立つ多くの機能があります。</span><span class="sxs-lookup"><span data-stu-id="66142-174">Review sets have many great capabilities to help reduce the amount of time and data needed to review, including:</span></span></p>
<ul>
<li><p><span data-ttu-id="66142-175">レビュー セットで高速検索クエリを実行し、コンテンツをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="66142-175">Perform fast search queries and filter content in a review set</span></span></p></li>
<li><p><span data-ttu-id="66142-176">レビュー セット内のコンテンツを分析する。これには、電子メール スレッド、重複に近い検出、テーマ分析、予測コーディングが含まれます。</span><span class="sxs-lookup"><span data-stu-id="66142-176">Analyze content in a review set; this includes email threading, near-duplicate detection, Themes analysis, and Predictive coding</span></span></p></li>
<li><p><span data-ttu-id="66142-177">レビュー セット内のドキュメントをタグ付けする</span><span class="sxs-lookup"><span data-stu-id="66142-177">Tag documents in a review set</span></span></p></li>
<li><p><span data-ttu-id="66142-178">弁護士クライアント特権コンテンツの識別に役立つタグ付け提案</span><span class="sxs-lookup"><span data-stu-id="66142-178">Tagging suggestions to help identify attorney  client privilege content</span></span></p></li></ul>
<p><span data-ttu-id="66142-179">詳細については、「<a href="/microsoft-365/compliance/overview-ediscovery-20">Microsoft 365 の Advanced eDiscovery ソリューションの概要</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66142-179">For more information, see <a href="/microsoft-365/compliance/overview-ediscovery-20">Overview of the Advanced eDiscovery solution in Microsoft 365</a>.</span></span></p>
<p>
<p><span data-ttu-id="66142-180">または、検索結果を PST ファイルにエクスポートし、Microsoft 365インポート サービスを使用して、PST を探索メールボックスにインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="66142-180">Alternatively, you can export search results to PST files and then use Microsoft 365 Import service to import the PSTs to a discovery mailbox.</span></span> <span data-ttu-id="66142-181">手順については、「ネットワーク アップロードを使用して PST ファイルをインポートしてファイルをインポートする」を<a href="/microsoft-365/compliance/use-network-upload-to-import-pst-files">参照</a>Office 365。</span><span class="sxs-lookup"><span data-stu-id="66142-181">For step-by-step instruction, see <a href="/microsoft-365/compliance/use-network-upload-to-import-pst-files">Use network upload to import PST files to Office 365</a>.</span></span>
</tr>
<tr class=even>
  <td><span data-ttu-id="66142-182">1 つのメールボックスから別のメールボックスへのメッセージのコピー</span><span class="sxs-lookup"><span data-stu-id="66142-182">Copy messages from one mailbox to a different mailbox</span></span></td>
  <td><span data-ttu-id="66142-183"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">メールボックスへのアクセス許可の割り当て</a></span><span class="sxs-lookup"><span data-stu-id="66142-183"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
  <td><span data-ttu-id="66142-184">他のユーザーの電子メールへのアクセス権をユーザーに付与するには (従業員が組織を離れ、他のユーザーに元従業員のメールへのアクセス権を与える必要がある場合など)、そのユーザーに元従業員のメールボックスにアクセスするためのアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="66142-184">To give a person access to another user's email (such as when an employee leaves your organization and you need to give another person access to the former employee's email), we recommended that you assign that person permissions to access the former employee's mailbox.</span></span> <span data-ttu-id="66142-185">そのため、メールボックス アイテムを別のユーザー メールボックスまたは共有メールボックスにコピーする代わりに、ソース メールボックスにアクセスするために必要なアクセス許可をユーザーに割り当てるだけで問題ありません。</span><span class="sxs-lookup"><span data-stu-id="66142-185">So instead of copying mailbox items to another user mailbox or a shared mailbox, just assign a user the permissions necessary to access the source mailbox.</span></span></td>
  
  </tr>
<tr class="odd">
<td><span data-ttu-id="66142-186">回復可能なアイテム フォルダーからアイテムを復元する</span><span class="sxs-lookup"><span data-stu-id="66142-186">Restore items from the Recoverable Items folder</span></span></td>
  <td><span data-ttu-id="66142-187"><a href="/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</span><span class="sxs-lookup"><span data-stu-id="66142-187"><a href="/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</span></span></td>
  <td><span data-ttu-id="66142-188">アイテムの削除済みアイテムの保持期間が経過しない<i></i>限り、メールボックス内の完全に削除されたアイテム (ソフト削除済みアイテムとも呼ばれる) を復元できます。</span><span class="sxs-lookup"><span data-stu-id="66142-188">You can restore permanently deleted items (also known as <i>soft-deleted</i> items) in mailboxes, as long as the deleted item retention period for an item hasn't expired.</span></span> <span data-ttu-id="66142-189">詳細については、「回復可能な<a href="/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">アイテム フォルダー」を参照Exchange Online。</a></span><span class="sxs-lookup"><span data-stu-id="66142-189">For more information, see <a href="/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Recoverable Items folder in Exchange Online</a>.</span></span></td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a><span data-ttu-id="66142-190">インプレース電子情報開示とインプレース ホールドに関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="66142-190">FAQs about In-Place eDiscovery and In-Place Holds</span></span>

<span data-ttu-id="66142-191">**EAC で電子情報開示 In-Place保持&検索結果のコピー機能を使用して、弁護士によるレビューのために検索結果を探索メールボックスにコピーします。どのようなオプションがありますか?**</span><span class="sxs-lookup"><span data-stu-id="66142-191">**I use the copy search results functionality of In-Place eDiscovery & Holds in the EAC to copy search results to a discovery mailbox for review by attorneys. What options do I have now?**</span></span>

<span data-ttu-id="66142-192">今日、この機能をレプリケートする方法は 2 通りあります。</span><span class="sxs-lookup"><span data-stu-id="66142-192">There are two ways to replicate this functionality today.</span></span> <span data-ttu-id="66142-193">1 つ目は[、v2.0](./view-documents-in-review-set.md)のレビュー セットAdvanced eDiscovery使用します。</span><span class="sxs-lookup"><span data-stu-id="66142-193">The first is to use [review sets in Advanced eDiscovery v2.0](./view-documents-in-review-set.md).</span></span> <span data-ttu-id="66142-194">レビュー セットには、ドキュメントの高速検索、タグ付け、メール スレッド、重複グループ化に近い、テーマ分析、予測コーディングなど、従来のレビュー ツールに表示される機能の多くがあります。</span><span class="sxs-lookup"><span data-stu-id="66142-194">Review sets have many of the same capabilities you see in a traditional review tool like fast search of documents, tagging, email threading, near duplicate grouping, themes analysis, and predictive coding.</span></span> <span data-ttu-id="66142-195">引き続き確認のために探索メールボックスを使用する場合、2 番目のオプションは、検索結果を PST ファイルにエクスポートし、Microsoft コンプライアンス センターの [PST](use-network-upload-to-import-pst-files.md) インポート機能を使用して、PST ファイルを探索メールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="66142-195">If you still want to use discovery mailboxes for review, the second option is to export search results to PST files and then import the PST files to a discovery mailbox by using the [PST import feature](use-network-upload-to-import-pst-files.md) in the Microsoft compliance center.</span></span>

<span data-ttu-id="66142-196">**電子情報開示マネージャーが新しいツールを使用して検索できるコンテンツの場所 (メールボックスやサイトなど) を制御する方法**</span><span class="sxs-lookup"><span data-stu-id="66142-196">**How do I control which content locations (such as mailboxes or sites) that can an eDiscovery manager can search using the new tools?**</span></span>

<span data-ttu-id="66142-197">またMicrosoft 365 コンプライアンス センターコンプライアンスの境界[を](set-up-compliance-boundaries.md)使用して、電子情報開示マネージャーが検索できるコンテンツの場所を制御します。</span><span class="sxs-lookup"><span data-stu-id="66142-197">The Microsoft 365 compliance center also uses [compliance boundaries](set-up-compliance-boundaries.md) to control which content locations an eDiscovery Manager can search.</span></span> <span data-ttu-id="66142-198">コンプライアンスの境界は、政府機関の境界内にとどまる必要がある政府機関や、地理的な下宿主を尊重するために必要な多国籍企業で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="66142-198">Compliance boundaries are useful in government entities that need to stay within agency boundaries or multi-national corporations required to respect geographical boarders.</span></span>

<span data-ttu-id="66142-199">**現在の検索とホールドを現在の検索先に移動Microsoft 365 コンプライアンス センター?**</span><span class="sxs-lookup"><span data-stu-id="66142-199">**How can I move my current searches and holds to the Microsoft 365 compliance center?**</span></span>

<span data-ttu-id="66142-200">PowerShell を使用して電子情報開示In-Place EAC から電子情報開示の検索と保持を移行できます。</span><span class="sxs-lookup"><span data-stu-id="66142-200">It's possible to migrate In-Place eDiscovery searches and holds from the EAC by using PowerShell.</span></span> <span data-ttu-id="66142-201">手順については、「検索と保持を EAC からサーバーに移行する」[を参照Microsoft 365 コンプライアンス センター。](./migrate-legacy-ediscovery-searches-and-holds.md)</span><span class="sxs-lookup"><span data-stu-id="66142-201">For instructions, see [Migrate searches and holds from the EAC to the Microsoft 365 compliance center](./migrate-legacy-ediscovery-searches-and-holds.md).</span></span>

## <a name="-mailboxsearch-cmdlets"></a><span data-ttu-id="66142-202">\*-MailboxSearch コマンドレット</span><span class="sxs-lookup"><span data-stu-id="66142-202">\*-MailboxSearch cmdlets</span></span>

<span data-ttu-id="66142-203">Exchange 管理センターで 2017 年 7 月 1 日に発表された元の通知に基づいて、In-Place 電子情報開示 & ホールド機能と対応する **\* -MailboxSearch** コマンドレットは廃止されます。</span><span class="sxs-lookup"><span data-stu-id="66142-203">As per the original notice announced on July 1, 2017 in the Exchange admin center, the In-Place eDiscovery & Hold functionality and the corresponding **\*-MailboxSearch** cmdlets are being retired.</span></span> <span data-ttu-id="66142-204">これらのコマンドレットを使用すると、ユーザーは、法的、規制、およびパブリック要求のためにメールボックス コンテンツを検索、保持、およびエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="66142-204">These cmdlets provide users the ability to search, hold, and export mailbox content for legal, regulatory, and public requests.</span></span>

<span data-ttu-id="66142-205">これらの機能は、パフォーマンスとスケーラビリティが向上した Microsoft 365 コンプライアンス センター および[<span class="underline">Office 365</span>](./microsoft-365-compliance-center.md)セキュリティ & コンプライアンス センター PowerShell で利用できる機能なので、これらの強化されたコマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66142-205">Because these capabilities are now available in the [<span class="underline">Microsoft 365 compliance center</span>](./microsoft-365-compliance-center.md) and Office 365 Security & Compliance Center PowerShell with improved performance and scalability, you should using these improved cmdlets.</span></span> <span data-ttu-id="66142-206">これらのコマンドレットには[<span class="underline"> \* 、-ComplianceCase</span>](/powershell/module/exchange/get-compliancecase) [<span class="underline">、-ComplianceSearch、-CaseHoldPolicy、-CaseHoldRule、 \* </span>](/powershell/module/exchange/get-compliancesearch)[<span class="underline"> \* および -ComplianceSearchAction が含まれます</span>](/powershell/module/exchange/get-compliancesearchaction)。 [<span class="underline"> \* </span>](/powershell/module/exchange/get-caseholdpolicy) [<span class="underline"> \* </span>](/powershell/module/exchange/get-caseholdrule)</span><span class="sxs-lookup"><span data-stu-id="66142-206">These cmdlets include [<span class="underline">\*-ComplianceCase</span>](/powershell/module/exchange/get-compliancecase), [<span class="underline">\*-ComplianceSearch</span>](/powershell/module/exchange/get-compliancesearch), [<span class="underline">\*-CaseHoldPolicy</span>](/powershell/module/exchange/get-caseholdpolicy), [<span class="underline">\*-CaseHoldRule</span>](/powershell/module/exchange/get-caseholdrule), and [<span class="underline">\*-ComplianceSearchAction</span>](/powershell/module/exchange/get-compliancesearchaction).</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="66142-207">影響を受ける組織の範囲</span><span class="sxs-lookup"><span data-stu-id="66142-207">Scope of affected organizations</span></span>

- <span data-ttu-id="66142-208">Office 365およびMicrosoft 365 Enterprise組織</span><span class="sxs-lookup"><span data-stu-id="66142-208">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="66142-209">Office 365およびMicrosoft 365 Education組織</span><span class="sxs-lookup"><span data-stu-id="66142-209">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="66142-210">Office 365およびMicrosoft 365組織。これには、GCC、GCC、DoD が含まれます。</span><span class="sxs-lookup"><span data-stu-id="66142-210">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="66142-211">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="66142-211">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="66142-212">タイムライン</span><span class="sxs-lookup"><span data-stu-id="66142-212">Timeline</span></span>

- <span data-ttu-id="66142-213">2020 年 7 月 1 日: **New-MailboxSearch** を使用して新しい In-Place 電子情報開示検索と In-Place 保留リストを作成することはできませんが、コマンドレットを使用して既存の検索と保持を実行、編集、および削除することができます。</span><span class="sxs-lookup"><span data-stu-id="66142-213">July 1, 2020: You won't be able to use **New-MailboxSearch** to create new In-Place eDiscovery searches and In-Place Holds, but you can still use cmdlets to run, edit, and delete existing searches and holds at your own risk.</span></span> <span data-ttu-id="66142-214">Microsoft サポートは、このような種類の検索と保留に関するサポートを提供しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="66142-214">Microsoft Support will no longer provide assistance for these types of searches and holds.</span></span>

- <span data-ttu-id="66142-215">2020 年 10 月 1 日: 前に述べたように、eAC の In-Place 電子情報開示 & Holds 機能は読み取り専用モードになります。</span><span class="sxs-lookup"><span data-stu-id="66142-215">October 1, 2020: As previously stated, The In-Place eDiscovery & Holds functionality in the EAC will be placed in a read-only mode.</span></span> <span data-ttu-id="66142-216">つまり **、New-MailboxSearch** コマンドレット **、Start-MailboxSearch** コマンドレット、 **または Set-MailboxSearch** コマンドレットを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="66142-216">That also means that you won't be able to use the **New-MailboxSearch**, **Start-MailboxSearch**, or **Set-MailboxSearch** cmdlets.</span></span> <span data-ttu-id="66142-217">既存の検索と保留リストのみを取得および削除できます。</span><span class="sxs-lookup"><span data-stu-id="66142-217">You'll only be able to get and remove existing searches and holds.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="66142-218">代替ツール</span><span class="sxs-lookup"><span data-stu-id="66142-218">Alternative tools</span></span>

<span data-ttu-id="66142-219">次の表では、廃止される既存の機能を置き換える他のツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="66142-219">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="66142-220">機能</span><span class="sxs-lookup"><span data-stu-id="66142-220">Functionality</span></span></th>
<th><span data-ttu-id="66142-221">代替ツール</span><span class="sxs-lookup"><span data-stu-id="66142-221">Alternative tools</span></span></th>
<th><span data-ttu-id="66142-222">コメント</span><span class="sxs-lookup"><span data-stu-id="66142-222">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="66142-223">検索とエクスポート</span><span class="sxs-lookup"><span data-stu-id="66142-223">Search and export</span></span></td>
<td><p><span data-ttu-id="66142-224"><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span><span class="sxs-lookup"><span data-stu-id="66142-224"><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="66142-225"><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span><span class="sxs-lookup"><span data-stu-id="66142-225"><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p><span data-ttu-id="66142-226"><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span><span class="sxs-lookup"><span data-stu-id="66142-226"><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span></span></p>
<p> </p></td>
<td><p><span data-ttu-id="66142-227">ComplianceSearch コマンドレットと ComplianceSearchAction コマンドレットは、コンテンツの検索とエクスポートに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="66142-227">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and export content.</span></span> <span data-ttu-id="66142-228">新しい検索を作成し、検索見積もりを表示するには<strong>、New-、Get-、</strong><strong>および</strong> <strong>Start-ComplianceSearch</strong>コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="66142-228">You can create a new search and view the search estimate by using the <strong>New-</strong>, <strong>Get-</strong>, and <strong>Start-ComplianceSearch</strong> cmdlets.</span></span> <span data-ttu-id="66142-229">次に <strong>、New-ComplianceSearchAction</strong> コマンドレットを使用して検索結果をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="66142-229">Then you can use the <strong>New-ComplianceSearchAction</strong> cmdlet to export the search results.</span></span> <span data-ttu-id="66142-230">これらの検索結果をローカル コンピューターにダウンロードするには、Microsoft 365 コンプライアンス センター電子情報開示のコア ツールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66142-230">You'll still have to use the core eDiscovery tool in the Microsoft 365 compliance center to download those search results to your local computer.</span></span></p>
<p>
<p><span data-ttu-id="66142-231"><strong>注:</strong>これらのコマンドレットを使用して、コアの電子情報開示ケースに関連付けされていない検索を作成する場合、これらの検索は、Microsoft 365 コンプライアンス センター の [<strong></strong>コンテンツ検索] ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="66142-231"><strong>Note:</strong> If you use these cmdlets to create searches that aren't associated with a core eDiscovery case, these searches will be located on the <strong>Content search</strong> page in the Microsoft 365 compliance center.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="66142-232">メールボックス内のコンテンツを保持する</span><span class="sxs-lookup"><span data-stu-id="66142-232">Hold content in a mailbox</span></span></td>
<td><p><span data-ttu-id="66142-233"><a href="/powershell/module/exchange/get-caseholdpolicy"><span class="underline">\*-CaseHoldPolicy</span></a></span><span class="sxs-lookup"><span data-stu-id="66142-233"><a href="/powershell/module/exchange/get-caseholdpolicy"><span class="underline">\*-CaseHoldPolicy</span></a></span></span></p>
<p><span data-ttu-id="66142-234"><a href="/powershell/module/exchange/get-caseholdrule"><span class="underline">\*-CaseHoldRule</span></a></span><span class="sxs-lookup"><span data-stu-id="66142-234"><a href="/powershell/module/exchange/get-caseholdrule"><span class="underline">\*-CaseHoldRule</span></a></span></span></p>
<p><span data-ttu-id="66142-235"><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span><span class="sxs-lookup"><span data-stu-id="66142-235"><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span></span></p>
<p> </p></td>
<td><p><span data-ttu-id="66142-236">コンプライアンス ケースにMicrosoft 365 コンプライアンス センターする必要があります。</span><span class="sxs-lookup"><span data-stu-id="66142-236">Holds in the Microsoft 365 compliance center must be associated with a ComplianceCase.</span></span> <span data-ttu-id="66142-237">まず、コンプライアンス ケースを作成し、CaseHoldPolicy と CaseHoldRule を作成します。</span><span class="sxs-lookup"><span data-stu-id="66142-237">First, create the compliance case, and then create a CaseHoldPolicy and a CaseHoldRule.</span></span></p>
<p><span data-ttu-id="66142-238"><strong>注:</strong> CaseHoldRule を作成せずに CaseHoldPolicy を作成すると、CaseHoldRule が作成され CaseHoldPolicy に関連付けられるまで、ホールドは操作不能になります。</span><span class="sxs-lookup"><span data-stu-id="66142-238"><strong>Note:</strong> Creating a CaseHoldPolicy without a creating CaseHoldRule will render the hold inoperable until the CaseHoldRule is created and associated to the CaseHoldPolicy.</span></span> <span data-ttu-id="66142-239">詳細については、コマンドレットのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="66142-239">See the cmdlet documentation for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="66142-240">検索結果を探索メールボックスにコピーする</span><span class="sxs-lookup"><span data-stu-id="66142-240">Copy search results to a discovery mailbox</span></span></td>
<td><span data-ttu-id="66142-241">なし</span><span class="sxs-lookup"><span data-stu-id="66142-241">None</span></span></td>
<td><span data-ttu-id="66142-242">この機能は、すべてのサービスにアクセスできるMicrosoft 365はありません。</span><span class="sxs-lookup"><span data-stu-id="66142-242">There's no direct replacement for this functionality because it does not provide access to all Microsoft 365 services.</span></span> <span data-ttu-id="66142-243">代替ソリューションについては、以下の FAQ を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66142-243">See the following FAQ below for alternative solutions.</span></span></td>
</tr>
  <tr class=even>
  <td><span data-ttu-id="66142-244">1 つのメールボックスから別のメールボックスへのメッセージのコピー</span><span class="sxs-lookup"><span data-stu-id="66142-244">Copy messages from one mailbox to a different mailbox</span></span></td>
  <td><span data-ttu-id="66142-245"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">メールボックスへのアクセス許可の割り当て</a></span><span class="sxs-lookup"><span data-stu-id="66142-245"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
  <td><span data-ttu-id="66142-246">他のユーザーの電子メールへのアクセス権をユーザーに付与するには (従業員が組織を離れ、他のユーザーに元従業員のメールへのアクセス権を与える必要がある場合など)、そのユーザーに元従業員のメールボックスにアクセスするためのアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="66142-246">To give a person access to another user's email (such as when an employee leaves your organization and you need to give another person access to the former employee's email), we recommended that you assign that person permissions to access the former employee's mailbox.</span></span> <span data-ttu-id="66142-247">そのため、メールボックス アイテムを別のユーザー メールボックスまたは共有メールボックスにコピーする代わりに、ソース メールボックスにアクセスするためのユーザーアクセス許可を割り当てるだけ。</span><span class="sxs-lookup"><span data-stu-id="66142-247">So instead of copying mailbox items to another user mailbox or a shared mailbox, just assign a user permissions to access the source mailbox.</span></span></td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a><span data-ttu-id="66142-248">\***-MailboxSearch コマンドレットに関する** よくある質問</span><span class="sxs-lookup"><span data-stu-id="66142-248">FAQs about \***-MailboxSearch** cmdlets</span></span>

<span data-ttu-id="66142-249">**コピー検索を使用して、他の電子情報開示および法的調査のために電子メール メッセージまたはインスタント メッセージをエクスポートします。これらのコマンドレットが廃止された後、他にどのようなオプションがありますか?**</span><span class="sxs-lookup"><span data-stu-id="66142-249">**We use Copy Search to export email messages or instant Messages for purposes other eDiscovery and legal investigations. What other options do we have after these cmdlets are retired?**</span></span>

<span data-ttu-id="66142-250">[<span class="underline">Microsoft Graph API</span>](https://developer.microsoft.com/en-us/graph)には、-MailboxSearch コマンドレットを使用するよりもはるかに回復性と拡張性を備えた分析などの目的でデータを抽出するためのメソッドが多数用意 **\*** されています。</span><span class="sxs-lookup"><span data-stu-id="66142-250">The [<span class="underline">Microsoft Graph APIs</span>](https://developer.microsoft.com/en-us/graph) provide a number of methods for extracting data for analysis and other purposes that are far more resilient and scalable than the using the **\*-MailboxSearch** cmdlets.</span></span>

<span data-ttu-id="66142-251">**検索と保持を移行する方法をMicrosoft 365 コンプライアンス センター?**</span><span class="sxs-lookup"><span data-stu-id="66142-251">**How can I migrate my searches and holds to the Microsoft 365 compliance center?**</span></span>

<span data-ttu-id="66142-252">PowerShell スクリプトを使用して、In-Placeから電子情報開示の検索と保持Exchange移行できます。</span><span class="sxs-lookup"><span data-stu-id="66142-252">It's possible to migrate In-Place eDiscovery searches and holds from the Exchange admin center by using a PowerShell script.</span></span> <span data-ttu-id="66142-253">詳細については、「従来の電子情報開示の検索と保持を移行[する」を参照Microsoft 365 コンプライアンス センター。](migrate-legacy-eDiscovery-searches-and-holds.md)</span><span class="sxs-lookup"><span data-stu-id="66142-253">For more information, see [Migrate legacy eDiscovery searches and holds to the Microsoft 365 compliance center](migrate-legacy-eDiscovery-searches-and-holds.md).</span></span>

<span data-ttu-id="66142-254">**コマンドレットが廃止された後も、検索を削除または取得できますか?**</span><span class="sxs-lookup"><span data-stu-id="66142-254">**After the cmdlets are retired, will I still be able to remove or retrieve searches?**</span></span>

<span data-ttu-id="66142-255">はい、検索を作成および変更する機能は削除しますが **、Get-MailboxSearch と Remove-MailboxSearch** は、詳細な通知が表示されるまで引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="66142-255">Yes, although we're removing the ability to create and modify searches, you'll still be able to use **Get-MailboxSearch** and **Remove-MailboxSearch** until further notice.</span></span> <span data-ttu-id="66142-256">ただし、これらのコマンドレットの使用は、退職日後に自身のリスクにさらされ、Microsoft サポートはサポートを提供できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="66142-256">However, the use of these cmdlets will be at your own risk after the retirement dates and Microsoft Support will no longer be able to provide assistance.</span></span>

## <a name="search-mailbox-cmdlet"></a><span data-ttu-id="66142-257">Search-Mailbox コマンドレット</span><span class="sxs-lookup"><span data-stu-id="66142-257">Search-Mailbox cmdlet</span></span>

<span data-ttu-id="66142-258">PowerShell **の Search-Mailbox** コマンドレットExchange Online、2018 年からコマンドレット出力の警告で最初に発表されたので廃止されます。</span><span class="sxs-lookup"><span data-stu-id="66142-258">The **Search-Mailbox** cmdlet in Exchange Online PowerShell is being retired as originally announced in a warning in the cmdlet output starting back in 2018.</span></span> <span data-ttu-id="66142-259">**Search-Mailbox コマンドレット** は、もともとユーザーのメールボックスを検索し、悪意のあるコンテンツを削除するために使用されています。</span><span class="sxs-lookup"><span data-stu-id="66142-259">The **Search-Mailbox** cmdlet was originally used to search a user's mailbox and purge malicious content.</span></span> <span data-ttu-id="66142-260">コンテンツを検索および削除するには、Office 365 セキュリティ & コンプライアンス センター PowerShell の **New-ComplianceSearch** コマンドレットと **New-ComplianceSearchAction** コマンドレットの使用を開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="66142-260">We recommend that you start using the **New-ComplianceSearch** and **New-ComplianceSearchAction** cmdlets in Office 365 Security & Compliance Center PowerShell to search for and purge content.</span></span> <span data-ttu-id="66142-261">組み込みのセキュリティ エクスペリエンスでは、電子メール[<span class="underline">Microsoft 365</span>](../security/index.yml)他の多くのセキュリティ機能に対する堅牢な脅威保護が提供Microsoft サービス。</span><span class="sxs-lookup"><span data-stu-id="66142-261">For a built-in security experience, the [<span class="underline">Microsoft 365 security features</span>](../security/index.yml) provide robust threat protection for email and many other Microsoft services.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="66142-262">影響を受ける組織の範囲</span><span class="sxs-lookup"><span data-stu-id="66142-262">Scope of affected organizations</span></span>

- <span data-ttu-id="66142-263">Office 365およびMicrosoft 365 Enterprise組織</span><span class="sxs-lookup"><span data-stu-id="66142-263">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="66142-264">Office 365およびMicrosoft 365 Education組織</span><span class="sxs-lookup"><span data-stu-id="66142-264">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="66142-265">Office 365およびMicrosoft 365組織。これには、GCC、GCC、DoD が含まれます。</span><span class="sxs-lookup"><span data-stu-id="66142-265">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="66142-266">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="66142-266">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="66142-267">タイムライン</span><span class="sxs-lookup"><span data-stu-id="66142-267">Timeline</span></span>

-  <span data-ttu-id="66142-268">2020 年 7 月 1 日: **Search-Mailbox** コマンドレットは使用できなくなりました。Microsoft サポートはサポートを提供しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="66142-268">July 1, 2020: The **Search-Mailbox** cmdlet will no longer be available and Microsoft Support will no longer provide assistance.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="66142-269">代替ツール</span><span class="sxs-lookup"><span data-stu-id="66142-269">Alternative tools</span></span>

<span data-ttu-id="66142-270">次の表では、廃止される既存の機能を置き換える他のツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="66142-270">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="66142-271">機能</span><span class="sxs-lookup"><span data-stu-id="66142-271">Functionality</span></span></th>
<th><span data-ttu-id="66142-272">代替ツール</span><span class="sxs-lookup"><span data-stu-id="66142-272">Alternative tools</span></span></th>
<th><span data-ttu-id="66142-273">コメント</span><span class="sxs-lookup"><span data-stu-id="66142-273">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="66142-274">メールボックスを検索する</span><span class="sxs-lookup"><span data-stu-id="66142-274">Search a mailbox</span></span></td>
<td><p><span data-ttu-id="66142-275"><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span><span class="sxs-lookup"><span data-stu-id="66142-275"><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="66142-276"><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span><span class="sxs-lookup"><span data-stu-id="66142-276"><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p></a></p></td>
<td><p><span data-ttu-id="66142-277">ComplianceSearch コマンドレットと ComplianceSearchAction コマンドレットは、コンテンツの検索とエクスポートに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="66142-277">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and export content.</span></span> <span data-ttu-id="66142-278">新しい検索を作成し、検索見積もりを表示するには<strong>、New-、Get-、</strong><strong>および</strong> <strong>Start-ComplianceSearch</strong>コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="66142-278">You can create a new search and view the search estimate by using the <strong>New-</strong>, <strong>Get-</strong>, and <strong>Start-ComplianceSearch</strong> cmdlets.</span></span> <span data-ttu-id="66142-279">次に <strong>、New-ComplianceSearchAction -Export</strong> コマンドを使用して検索結果をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="66142-279">Then you can use the <strong>New-ComplianceSearchAction -Export</strong> command to export the search results.</span></span> <span data-ttu-id="66142-280">これらの検索結果をローカル コンピューターにダウンロードするには、Microsoft 365 コンプライアンス センター電子情報開示のコア ツールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66142-280">You'll still have to use the core eDiscovery tool in the Microsoft 365 compliance center to download those search results to your local computer.</span></span></p></p>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="66142-281">メールボックスから一括メールを削除する</span><span class="sxs-lookup"><span data-stu-id="66142-281">Delete bulk email from a mailbox</span></span></td>
<td><p><span data-ttu-id="66142-282"><a href="/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes"><span class="underline">メールボックスのアーカイブと削除ポリシーを設定する</span></a></span><span class="sxs-lookup"><span data-stu-id="66142-282"><a href="/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes"><span class="underline">Set up an archive and deletion policy for mailboxes</span></a></span></span></p>
<p></p></td>
<td><p><span data-ttu-id="66142-283">管理者は、ユーザーのアーカイブ メールボックスにアイテムを自動的に移動し、メールボックスからアイテムを自動的に削除するアーカイブおよび削除ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="66142-283">Admins can create an archiving and deletion policy that automatically moves items to a user's archive mailbox and automatically deletes items from the mailbox.</span></span></p>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="66142-284">検索結果を探索メールボックスにコピーする</span><span class="sxs-lookup"><span data-stu-id="66142-284">Copy search results to a discovery mailbox</span></span></td>
<td> </td>
<td><span data-ttu-id="66142-285">この機能は、すべてのサービスにアクセスできるMicrosoft 365はありません。</span><span class="sxs-lookup"><span data-stu-id="66142-285">There's no direct replacement for this functionality because it does not provide access to all Microsoft 365 services.</span></span> <span data-ttu-id="66142-286">代替ソリューションについては <strong>、「\*-MailboxSearch コマンドレット</strong> 」の「FAQ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66142-286">See the FAQs in the <strong>\*-MailboxSearch cmdlets</strong> section for alternative solutions.</span></span> </td>
</tr>
<tr class=odd>
  <td><span data-ttu-id="66142-287">1 つのメールボックスから別のメールボックスへのメッセージのコピー</span><span class="sxs-lookup"><span data-stu-id="66142-287">Copy messages from one mailbox to a different mailbox</span></span></td>
  <td><span data-ttu-id="66142-288"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">メールボックスへのアクセス許可の割り当て</a></span><span class="sxs-lookup"><span data-stu-id="66142-288"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
  <td><span data-ttu-id="66142-289">他のユーザーの電子メールへのアクセス権をユーザーに付与するには (従業員が組織を離れ、他のユーザーに元従業員のメールへのアクセス権を与える必要がある場合など)、そのユーザーに元従業員のメールボックスにアクセスするためのアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="66142-289">To give a person access to another user's email (such as when an employee leaves your organization and you need to give another person access to the former employee's email), we recommended that you assign that person permissions to access the former employee's mailbox.</span></span> <span data-ttu-id="66142-290">したがって、メールボックス アイテムを別のユーザー メールボックスまたは共有メールボックスにコピーする代わりに、ソース メールボックスにアクセスするためのユーザーアクセス許可を割り当てるだけ。</span><span class="sxs-lookup"><span data-stu-id="66142-290">So instead of copying mailbox items to another user mailbox or a shared mailbox, just assign a user permission to access the source mailbox.</span></span></td>
</tr>
<tr class=even>
  <td><span data-ttu-id="66142-291">メールボックスからメッセージを削除する</span><span class="sxs-lookup"><span data-stu-id="66142-291">Purge messages from a mailbox</span></span></td>
<td><p><span data-ttu-id="66142-292"><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span><span class="sxs-lookup"><span data-stu-id="66142-292"><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="66142-293"><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span><span class="sxs-lookup"><span data-stu-id="66142-293"><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p></p></td>
<td><p><span data-ttu-id="66142-294">ComplianceSearch コマンドレットと ComplianceSearchAction コマンドレットは、コンテンツの検索と削除に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="66142-294">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and purge content.</span></span> <span data-ttu-id="66142-295"><strong>New-ComplianceSearch</strong>コマンドレットと<strong>New-ComplianceSearch</strong>コマンドレットを使用して検索を作成して実行し<strong>、New-ComplianceSearchAction -Purge -PurgeType</strong>コマンドを使用してコンテンツを削除できます。</span><span class="sxs-lookup"><span data-stu-id="66142-295">You can create and run a search with <strong>New-ComplianceSearch</strong> and <strong>New-ComplianceSearch</strong> cmdlets, and then you can purge the content by using <strong>New-ComplianceSearchAction -Purge -PurgeType</strong> command.</span></span> <span data-ttu-id="66142-296">詳細については、「メッセージの検索と <a href="/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">削除」を参照してください</span></a>。</span><span class="sxs-lookup"><span data-stu-id="66142-296">For more information, see <a href="/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">Search for and delete messages</span></a>.</span></span></p>
</td>
</tr>
<tr class="odd"> 
<td><span data-ttu-id="66142-297">メールボックスからメッセージを削除する</span><span class="sxs-lookup"><span data-stu-id="66142-297">Purge messages from a mailbox</span></span></td>
<td><span data-ttu-id="66142-298"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">メールボックスへのアクセス許可の割り当て</a></span><span class="sxs-lookup"><span data-stu-id="66142-298"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
<td><span data-ttu-id="66142-299">メールボックスからメッセージを削除するには、管理者のアクセス許可を割り当て、従業員のメールボックスにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="66142-299">To purge messages from a mailbox, assign an administrator permissions to access the employee's mailbox.</span></span> <span data-ttu-id="66142-300">メッセージは、必要に応じて削除およびリサイクルできます。この機能は、Outlook。</span><span class="sxs-lookup"><span data-stu-id="66142-300">Messages can be deleted and recycled as needed taking advantage of the built-in search and viewing capabilities in Outlook.</span></span></td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a><span data-ttu-id="66142-301">ExchangeWeb サービス API の操作</span><span class="sxs-lookup"><span data-stu-id="66142-301">Exchange Web Services API operations</span></span>

<span data-ttu-id="66142-302">Exchange Web Services API のこれらの操作は、Exchange 管理センターの In-Place 電子情報開示 & 保留機能と、Exchange Online PowerShell の対応する **\* -MailboxSearch** コマンドレットによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="66142-302">These operations in the Exchange Web Services API are used by the In-Place eDiscovery & Holds feature in the Exchange admin center and the corresponding **\*-MailboxSearch** cmdlets in Exchange Online PowerShell.</span></span> <span data-ttu-id="66142-303">また、他の従来の電子情報開示ツールの廃止の一環として廃止されます。</span><span class="sxs-lookup"><span data-stu-id="66142-303">They will also be retired as part of retiring the other legacy eDiscovery tools.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="66142-304">影響を受ける組織の範囲</span><span class="sxs-lookup"><span data-stu-id="66142-304">Scope of affected organizations</span></span>

- <span data-ttu-id="66142-305">Office 365およびMicrosoft 365 Enterprise組織</span><span class="sxs-lookup"><span data-stu-id="66142-305">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="66142-306">Office 365およびMicrosoft 365 Education組織</span><span class="sxs-lookup"><span data-stu-id="66142-306">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="66142-307">Office 365およびMicrosoft 365組織。これには、GCC、GCC、DoD が含まれます。</span><span class="sxs-lookup"><span data-stu-id="66142-307">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="66142-308">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="66142-308">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="66142-309">タイムライン</span><span class="sxs-lookup"><span data-stu-id="66142-309">Timeline</span></span>

- <span data-ttu-id="66142-310">2020 年 7 月 1 日: GetSearchableMailboxes、SearchMailboxes、SetHoldOnMailboxes、および GetHoldOnMailboxes 操作は使用できなくなりました。Microsoft サポートはサポートを提供しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="66142-310">July 1, 2020: The GetSearchableMailboxes, SearchMailboxes, SetHoldOnMailboxes, and GetHoldOnMailboxes operations will no longer be available, and Microsoft Support will no longer provide assistance.</span></span>

## <a name="advanced-ediscovery-v10"></a><span data-ttu-id="66142-311">Advanced eDiscovery v1.0</span><span class="sxs-lookup"><span data-stu-id="66142-311">Advanced eDiscovery v1.0</span></span>

<span data-ttu-id="66142-312">Advanced eDiscovery v1.0 は、コアの電子情報開示ケースで使用できる Advanced eDiscovery のバージョンで、[Advanced eDiscovery に切り替える] を **クリック** して使用できません。</span><span class="sxs-lookup"><span data-stu-id="66142-312">Advanced eDiscovery v1.0, which is the version of Advanced eDiscovery available in a core eDiscovery case by clicking **Switch to Advanced eDiscovery**, is being retired.</span></span> <span data-ttu-id="66142-313">その機能は、新しいソリューション Advanced eDiscovery[に](./ediscovery.md)置き換Microsoft 365 コンプライアンス センター。</span><span class="sxs-lookup"><span data-stu-id="66142-313">Its functionality has been replaced by the new [Advanced eDiscovery solution](./ediscovery.md) in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="66142-314">組織で v1.0 を使用Advanced eDiscoveryするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="66142-314">To determine if your organization is using Advanced eDiscovery v1.0:</span></span>

1. <span data-ttu-id="66142-315">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com) にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="66142-315">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="66142-316">コンプライアンス センターの左側のナビゲーション ウィンドウで、[電子情報開示] >コア] **をクリックし、Core** 電子情報開示ケースを開きます。</span><span class="sxs-lookup"><span data-stu-id="66142-316">In the left navigation pane of the compliance center, click **eDiscovery > Core**, and open a Core eDiscovery case.</span></span>

3. <span data-ttu-id="66142-317">[デバイスに切り替Advanced eDiscovery] ボタン **が表示** された場合は、クリックすると 1.0 バージョンの Advanced eDiscovery に移動します。これは廃止されます。</span><span class="sxs-lookup"><span data-stu-id="66142-317">If you see the **Switch to Advanced eDiscovery** button, then clicking it will take you to the 1.0 version of Advanced eDiscovery, which is being retired.</span></span> <span data-ttu-id="66142-318">Core eDiscovery でケースを作成および管理する機能は影響を受け取らない。</span><span class="sxs-lookup"><span data-stu-id="66142-318">The ability to create and manage cases in Core eDiscovery won't be affected.</span></span> <span data-ttu-id="66142-319">v1.0 でケース データを追加および分析する機能 (Advanced eDiscovery に切り替 **える)** をクリックAdvanced eDiscovery削除されます。</span><span class="sxs-lookup"><span data-stu-id="66142-319">Only the ability to add and analyze case data in Advanced eDiscovery v1.0 (by clicking **Switch to Advanced eDiscovery**) is being retired.</span></span>

<span data-ttu-id="66142-320">Microsoft 365 の新しい Advanced eDiscovery ソリューション *(Advanced eDiscovery v2.0* とも呼ばれる) は、元のソリューションのすべての機能を提供しますが、他の Microsoft 365 サービスのコンテンツを識別し、そのコンテンツを収集し、レビュー担当者が迅速な検索クエリ、タグ付け、分析機能を活用して関連ドキュメントを作成できるレビュー セットに追加するカストディアンベースのアプローチが含まれています。</span><span class="sxs-lookup"><span data-stu-id="66142-320">The new Advanced eDiscovery solution in Microsoft 365 (also known as *Advanced eDiscovery v2.0*) provides all of the capabilities of the original solution, but now includes a custodian-based approach of identifying content in other Microsoft 365 services, collecting that content, and then adding it to a review set where reviewers can take advantage of fast search queries, tagging, and analytics features to help cull relevant documents.</span></span> <span data-ttu-id="66142-321">Advanced eDiscovery、Microsoft と Microsoft 以外のファイルの種類の両方の処理とネイティブ ビューアーが追加されました。ファイルの種類の完全な一覧は[次](./supported-filetypes-ediscovery20.md)のとおりです。サポートされているメタデータ フィールドは次[のとおりです](./document-metadata-fields-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="66142-321">Advanced eDiscovery now includes improved processing and native viewers for both Microsoft and non-Microsoft file types, a full list of file types is [here](./supported-filetypes-ediscovery20.md) and supported metadata fields are [here](./document-metadata-fields-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="66142-322">また、新しい Advanced eDiscovery ソリューションでは、強力な保管担当者が管理機能を提供し、さまざまなサービスのコンテンツにホールドを適用し、保留リストのユーザーに通知し、保管担当者の応答を追跡できます(すべて Advanced eDiscovery ケース内)。</span><span class="sxs-lookup"><span data-stu-id="66142-322">Also, the new Advanced eDiscovery solution provides a powerful custodian holds management feature that lets you apply holds to content in different services, notify users of the holds, and track custodian responses, all within an Advanced eDiscovery case.</span></span>

<span data-ttu-id="66142-323">Advanced eDiscovery v2.0 へのアクセス</span><span class="sxs-lookup"><span data-stu-id="66142-323">To access Advanced eDiscovery v2.0:</span></span>

1. <span data-ttu-id="66142-324">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com) にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="66142-324">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="66142-325">Microsoft 365 コンプライアンス センターの左側のナビゲーション ウィンドウで、[**すべてを表示**] をクリックし、**[eDiscovery] > [Advanced]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66142-325">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Advanced**.</span></span>

<span data-ttu-id="66142-326">この時点で、電子情報開示ワークフローを新しい電子情報開示機能に移行Advanced eDiscovery勧めします。</span><span class="sxs-lookup"><span data-stu-id="66142-326">At this time, we recommend that you begin to transition your eDiscovery workflow to the new Advanced eDiscovery functionality.</span></span> <span data-ttu-id="66142-327">必要に応じて、コンテンツをエクスポートAdvanced eDiscoveryオフラインで保存することで、1.0 ケースをアーカイブできます。</span><span class="sxs-lookup"><span data-stu-id="66142-327">If necessary, you can archive your Advanced eDiscovery 1.0 cases by exporting the content and storing it offline.</span></span> <span data-ttu-id="66142-328">2020 年 12 月 31 日まで、既存のケースでは引き続き Advanced eDiscovery v1.0 にアクセスすることができますが、Microsoft サポートは 2020 年 10 月 1 日以降はサポートを提供しない予定です。</span><span class="sxs-lookup"><span data-stu-id="66142-328">Although you'll still be able to access Advanced eDiscovery v1.0 in existing cases until December 31, 2020, Microsoft Support won't provide support after October 1, 2020.</span></span> <span data-ttu-id="66142-329">詳細については、次のタイムラインを参照してください。</span><span class="sxs-lookup"><span data-stu-id="66142-329">See the following timeline for more details.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="66142-330">影響を受ける組織の範囲</span><span class="sxs-lookup"><span data-stu-id="66142-330">Scope of affected organizations</span></span>

- <span data-ttu-id="66142-331">Office 365およびMicrosoft 365 Enterprise組織</span><span class="sxs-lookup"><span data-stu-id="66142-331">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="66142-332">Office 365およびMicrosoft 365 Education組織</span><span class="sxs-lookup"><span data-stu-id="66142-332">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="66142-333">Office 365およびMicrosoft 365組織。これには、GCC、GCC、DoD が含まれます。</span><span class="sxs-lookup"><span data-stu-id="66142-333">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="66142-334">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="66142-334">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="66142-335">タイムライン</span><span class="sxs-lookup"><span data-stu-id="66142-335">Timeline</span></span>

- <span data-ttu-id="66142-336">2020 年 7 月 1 日: v1.0 の新しいAdvanced eDiscovery作成できない。</span><span class="sxs-lookup"><span data-stu-id="66142-336">July 1, 2020: You won't be able to create new Advanced eDiscovery v1.0  cases.</span></span>

- <span data-ttu-id="66142-337">2020 年 10 月 1 日: 新しいデータを追加できない (Advanced eDiscovery の検索結果を準備する) 場合。</span><span class="sxs-lookup"><span data-stu-id="66142-337">October 1, 2020: You won't be able to add new data (Prepare search results for Advanced eDiscovery) to any cases.</span></span> <span data-ttu-id="66142-338">既存のケースのデータを自分のリスクで引き続き操作できます。</span><span class="sxs-lookup"><span data-stu-id="66142-338">You'll be able to continue working with data in existing cases at your own risk.</span></span> <span data-ttu-id="66142-339">Microsoft サポートはサポートを提供しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="66142-339">Microsoft Support will no longer provide assistance.</span></span> 

- <span data-ttu-id="66142-340">2020 年 12 月 31 日: v1.0 のケースAdvanced eDiscoveryアクセスできない。</span><span class="sxs-lookup"><span data-stu-id="66142-340">December 31, 2020: You won't be able to access Advanced eDiscovery v1.0 cases.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="66142-341">代替ツール</span><span class="sxs-lookup"><span data-stu-id="66142-341">Alternative tools</span></span>

<span data-ttu-id="66142-342">この[Advanced eDiscoveryソリューション](./overview-ediscovery-20.md)Microsoft 365 コンプライアンス センター。</span><span class="sxs-lookup"><span data-stu-id="66142-342">The [Advanced eDiscovery solution](./overview-ediscovery-20.md) in the Microsoft 365 compliance center.</span></span>