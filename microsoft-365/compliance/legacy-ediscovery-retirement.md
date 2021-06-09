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
ms.openlocfilehash: c5f1ddb4c817ebc316c2e2efdba9a4bc605eb5a2
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842664"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a><span data-ttu-id="bb83d-104">従来の電子情報開示ツールの廃止</span><span class="sxs-lookup"><span data-stu-id="bb83d-104">Retirement of legacy eDiscovery tools</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bb83d-105">Microsoft は、公衆衛生の状況を評価し、これがお客様に与える影響を理解しています。</span><span class="sxs-lookup"><span data-stu-id="bb83d-105">Microsoft has been evaluating the public health situation, and we understand the impact this is having on our customers.</span></span> <span data-ttu-id="bb83d-106">強いパートナーであり、責任あるグローバル市民でありたく思っています。</span><span class="sxs-lookup"><span data-stu-id="bb83d-106">We want to be strong partners and responsible global citizens.</span></span> <span data-ttu-id="bb83d-107">直面している多くの負担の 1 つを軽減するために、この記事で説明する従来の電子情報開示ツールの予定退職を 3 か月遅らせる予定です。</span><span class="sxs-lookup"><span data-stu-id="bb83d-107">To ease one of the many burdens you are facing, we are going to delay the scheduled retirement for the legacy eDiscovery tools described in this article by three months.</span></span> <span data-ttu-id="bb83d-108">**更新された退職日は、以下に反映されます。**</span><span class="sxs-lookup"><span data-stu-id="bb83d-108">**The updated retirement dates are reflected below.**</span></span>

<span data-ttu-id="bb83d-109">長年にわたり、Microsoft は電子情報開示ツールを提供し、電子情報開示ツールを使用して、電子メール コンテンツを検索、プレビュー、およびエクスポートExchange Online。</span><span class="sxs-lookup"><span data-stu-id="bb83d-109">Over the years, Microsoft has provided eDiscovery tools that let you search, preview, and export email content from Exchange Online.</span></span> <span data-ttu-id="bb83d-110">ただし、これらのツールは、Exchange Online や Microsoft 365 グループなどの他の SharePoint Microsoft 365 サービスで非 Exchange コンテンツを検索する効果的な方法を提供しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="bb83d-110">However, these tools no longer offer an effective way to search for non-Exchange content in other Microsoft 365 services, such as SharePoint Online and Microsoft 365 Groups.</span></span> <span data-ttu-id="bb83d-111">この問題に対処するために、Microsoft はさまざまなコンテンツを検索するのに役立つその他の電子情報開示Microsoft 365しています。</span><span class="sxs-lookup"><span data-stu-id="bb83d-111">To address this, Microsoft offers other eDiscovery tools that help you search for a wide variety of Microsoft 365 content.</span></span> <span data-ttu-id="bb83d-112">また、コンプライアンス センターに最新かつ強力な電子情報開示機能を組み込むMicrosoft 365[しています](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="bb83d-112">And we've been working hard to incorporate the most current and powerful eDiscovery functionality in the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span> <span data-ttu-id="bb83d-113">これにより、組織は、コンテンツに関する法的、内部的、その他のドキュメント要求に、Microsoft 365サービスを含む多くのExchange Online。</span><span class="sxs-lookup"><span data-stu-id="bb83d-113">This allows organizations to respond to legal, internal, and other document requests for content across many Microsoft 365 services, including Exchange Online.</span></span>

<span data-ttu-id="bb83d-114">Microsoft 365 コンプライアンス センターでこの新しく強化された電子情報開示機能の結果、Exchange Online および Microsoft 365 の電子メール コンテンツの検索に関連する次の電子情報開示関連の機能が廃止されました。</span><span class="sxs-lookup"><span data-stu-id="bb83d-114">As a result of this new and improved eDiscovery functionality in the Microsoft 365 compliance center, we're retiring the following eDiscovery-related features and functionality related to searching for email content in Exchange Online and Microsoft 365:</span></span>

- <span data-ttu-id="bb83d-115">Exchange 管理センターの[インプレース電子情報開示](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)および[インプレース ホールド](/exchange/security-and-compliance/create-or-remove-in-place-holds)。</span><span class="sxs-lookup"><span data-stu-id="bb83d-115">[In-Place eDiscovery](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) and [In-Place Holds](/exchange/security-and-compliance/create-or-remove-in-place-holds) in the Exchange admin center.</span></span>

- <span data-ttu-id="bb83d-116">電子Exchange Onlineおよび In-Place 保持をサポートする power In-Place Shell コマンドレット (これらのコマンドレットは、 \**-MailboxSearch* コマンドレットとしてまとめて識別されます)。</span><span class="sxs-lookup"><span data-stu-id="bb83d-116">The Exchange Online PowerShell cmdlets that support In-Place eDiscovery and In-Place Holds (these cmdlets are collectively identified as \**-MailboxSearch* cmdlets).</span></span> <span data-ttu-id="bb83d-117">これには、次のコマンドレットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-117">This includes the following cmdlets:</span></span>

  - [<span data-ttu-id="bb83d-118">New-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="bb83d-118">New-MailboxSearch</span></span>](/powershell/module/exchange/new-mailboxsearch)

  - [<span data-ttu-id="bb83d-119">Start-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="bb83d-119">Start-MailboxSearch</span></span>](/powershell/module/exchange/start-mailboxsearch)

  - [<span data-ttu-id="bb83d-120">Stop-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="bb83d-120">Stop-MailboxSearch</span></span>](/powershell/module/exchange/stop-mailboxsearch)

  - [<span data-ttu-id="bb83d-121">Set-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="bb83d-121">Set-MailboxSearch</span></span>](/powershell/module/exchange/set-mailboxsearch)

   > [!NOTE]
   > <span data-ttu-id="bb83d-122">[Get-MailboxSearch](/powershell/module/exchange/get-mailboxsearch)コマンドレットと[Remove-MailboxSearch](/powershell/module/exchange/remove-mailboxsearch)コマンドレットは、他の \*\*\*\*-MailboxSearch\*\*\* コマンドレットが廃止された後に使用できます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-122">The [Get-MailboxSearch](/powershell/module/exchange/get-mailboxsearch) and [Remove-MailboxSearch](/powershell/module/exchange/remove-mailboxsearch) cmdlets will be available after the other \*\*\*\*-MailboxSearch\*\*\* cmdlets are retired so that you can use them to help in your transition to other eDiscovery and hold tools.</span></span> <span data-ttu-id="bb83d-123">ただし、特定の日付 (以下に引用) が終了すると、Microsoft サポートはこれら 2 つのコマンドレットをサポートしなくなりました。</span><span class="sxs-lookup"><span data-stu-id="bb83d-123">However, after a certain date (cited below) Microsoft Support will no longer supports these two cmdlets.</span></span>

- <span data-ttu-id="bb83d-124">Exchange Online PowerShell の [Search-Mailbox](/powershell/module/exchange/search-mailbox) コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="bb83d-124">The [Search-Mailbox](/powershell/module/exchange/search-mailbox) cmdlet in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="bb83d-125">Exchange Web Services API での次の操作。</span><span class="sxs-lookup"><span data-stu-id="bb83d-125">The following operations in the Exchange Web Services API:</span></span>

   - [<span data-ttu-id="bb83d-126">GetSearchableMailboxes</span><span class="sxs-lookup"><span data-stu-id="bb83d-126">GetSearchableMailboxes</span></span>](/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [<span data-ttu-id="bb83d-127">SearchMailboxes</span><span class="sxs-lookup"><span data-stu-id="bb83d-127">SearchMailboxes</span></span>](/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [<span data-ttu-id="bb83d-128">SetHoldOnMailboxes</span><span class="sxs-lookup"><span data-stu-id="bb83d-128">SetHoldOnMailboxes</span></span>](/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [<span data-ttu-id="bb83d-129">GetHoldOnMailboxes</span><span class="sxs-lookup"><span data-stu-id="bb83d-129">GetHoldOnMailboxes</span></span>](/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- <span data-ttu-id="bb83d-130">[Office 365 Advanced eDiscovery v1.0](./overview-ediscovery-20.md)は、Office 365 セキュリティ & コンプライアンス センターの Core 電子情報開示ケースを通じてアクセスされる Advanced eDiscovery の最初のバージョンです。</span><span class="sxs-lookup"><span data-stu-id="bb83d-130">[Office 365 Advanced eDiscovery v1.0](./overview-ediscovery-20.md), which is the first version of Advanced eDiscovery that's accessed through a Core eDiscovery case in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="bb83d-131">v1.0 のAdvanced eDiscoveryは、コア電子情報開示ケースを作成および管理する機能には影響を与えかねない。</span><span class="sxs-lookup"><span data-stu-id="bb83d-131">The retirement of Advanced eDiscovery v1.0 doesn't impact your ability to create and manage Core eDiscovery cases.</span></span>

> [!NOTE]
> <span data-ttu-id="bb83d-132">廃止される電子情報開示機能は、クラウド ベースのバージョンの Microsoft 365およびOffice 365。</span><span class="sxs-lookup"><span data-stu-id="bb83d-132">The eDiscovery functionality being retired only applies to cloud-based versions of Microsoft 365 and Office 365.</span></span> <span data-ttu-id="bb83d-133">オンプレミスバージョンの電子情報開示機能は、ExchangeおよびSharePointまで引き続きサポートされます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-133">eDiscovery functionality in on-premises versions of Exchange and SharePoint will still be supported until further notice.</span></span>

<span data-ttu-id="bb83d-134">この記事の以下のセクションでは、廃止される各機能に関するガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="bb83d-134">The following sections in this article provide guidance about each feature being retired.</span></span> <span data-ttu-id="bb83d-135">この情報には、廃止されたツールの代わりに使用できるタイムラインや代替ツールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bb83d-135">This information including timelines and alternative tools that you can use instead of the retired tool.</span></span>

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a><span data-ttu-id="bb83d-136">In-Place管理センターIn-Place電子情報開示とExchange保持</span><span class="sxs-lookup"><span data-stu-id="bb83d-136">In-Place eDiscovery and In-Place Holds in the Exchange admin center</span></span> 

<span data-ttu-id="bb83d-137">2017 年 7 月 1 日の当初の発表と同様に、In-Place 管理センター (EAC) の Exchange In-Place 電子情報開示 & 保留機能は廃止されます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-137">As per the original announcement on July 1, 2017, the In-Place eDiscovery & Hold functionality in the Exchange admin center (EAC) is being retired.</span></span> <span data-ttu-id="bb83d-138">EAC In-Place [&保持] ページでは、コンテンツを検索、保持、およびエクスポートExchange Online。</span><span class="sxs-lookup"><span data-stu-id="bb83d-138">The In-Place eDiscovery & Holds page in the EAC allowed you to search, hold, and export content from Exchange Online.</span></span> <span data-ttu-id="bb83d-139">In-Place電子情報開示を使用すると、検索結果を探索メールボックスにコピーして、ユーザーまたは他の電子情報開示管理者がコンテンツを確認し、法的、規制、およびパブリック要求に対して利用可能にできます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-139">In-Place eDiscovery also let you copy search results to a discovery mailbox so that you or other eDiscovery managers could review content and make it available for legal, regulatory, and public requests.</span></span>

<span data-ttu-id="bb83d-140">これらの機能 (検索結果を探索メールボックスにコピーする場合を除く) はすべて[、Microsoft 365](./microsoft-365-compliance-center.md)コンプライアンス センターのコンテンツ検索、電子情報開示、および Advanced eDiscovery ツールで利用できます (機能、信頼性、幅広い Microsoft 365 サービスのサポートが強化されています)、できるだけ早くこれらのツールの使用を開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bb83d-140">Because all of these capabilities (except for copying search results to a discovery mailbox) are now available in the content search, eDiscovery and Advanced eDiscovery tools in the [Microsoft 365 compliance center](./microsoft-365-compliance-center.md) (with improved functionality, reliability, and support for a wide range of Microsoft 365 services), we recommend that you start using these tools as soon as possible.</span></span> <span data-ttu-id="bb83d-141">これらの他の電子情報開示ツールへの移行を支援するために、以下の表に、電子情報開示と電子情報開示の保持ではなくIn-PlaceツールIn-Place示します。</span><span class="sxs-lookup"><span data-stu-id="bb83d-141">To help you in the transition to these other eDiscovery tools, the table below lists the tools you can use instead of In-Place eDiscovery and In-Place Hold.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="bb83d-142">影響を受ける組織の範囲</span><span class="sxs-lookup"><span data-stu-id="bb83d-142">Scope of affected organizations</span></span>

- <span data-ttu-id="bb83d-143">Office 365およびMicrosoft 365 Enterprise組織</span><span class="sxs-lookup"><span data-stu-id="bb83d-143">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="bb83d-144">Office 365およびMicrosoft 365 Education組織</span><span class="sxs-lookup"><span data-stu-id="bb83d-144">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="bb83d-145">Office 365およびMicrosoft 365組織。これには、GCC、GCC、DoD が含まれます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-145">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="bb83d-146">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="bb83d-146">Office 365 Germany</span></span>

### <a name="timeline-for-retirement"></a><span data-ttu-id="bb83d-147">退職のタイムライン</span><span class="sxs-lookup"><span data-stu-id="bb83d-147">Timeline for retirement</span></span>

- <span data-ttu-id="bb83d-148">2020 年 7 月 1 日: 新しい検索と保留リストを作成できますが、既存の検索の実行、編集、および削除は、自分のリスクで行います。</span><span class="sxs-lookup"><span data-stu-id="bb83d-148">July 1, 2020: You won't be able to create new searches and holds, but you can still run, edit, and delete existing searches at your own risk.</span></span> <span data-ttu-id="bb83d-149">Microsoft サポートは、EAC In-Place保持&電子情報開示を使用しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="bb83d-149">Microsoft Support will no longer In-Place eDiscovery & Holds in the EAC.</span></span>

- <span data-ttu-id="bb83d-150">2020 年 10 月 1 日: In-Place電子情報開示 & EAC の保持機能は、読み取り専用モードになります。</span><span class="sxs-lookup"><span data-stu-id="bb83d-150">October 1, 2020: The In-Place eDiscovery & Holds functionality in the EAC will be placed in a read-only mode.</span></span> <span data-ttu-id="bb83d-151">これにより、可能な操作は、既存の検索および保留リストの削除のみになります。</span><span class="sxs-lookup"><span data-stu-id="bb83d-151">This means you'll only be able to remove existing searches and holds.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="bb83d-152">代替ツール</span><span class="sxs-lookup"><span data-stu-id="bb83d-152">Alternative tools</span></span>

<span data-ttu-id="bb83d-153">次の表では、廃止される既存の機能を置き換える他のツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bb83d-153">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="bb83d-154">機能</span><span class="sxs-lookup"><span data-stu-id="bb83d-154">Functionality</span></span></th>
<th><span data-ttu-id="bb83d-155">代替ツール</span><span class="sxs-lookup"><span data-stu-id="bb83d-155">Alternative tool</span></span></th>
<th><span data-ttu-id="bb83d-156">コメント</span><span class="sxs-lookup"><span data-stu-id="bb83d-156">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="bb83d-157">法的な目的で検索、エクスポート、ホールドする</span><span class="sxs-lookup"><span data-stu-id="bb83d-157">Search, export, and hold for legal purposes</span></span></td>
<td><span data-ttu-id="bb83d-158">コンプライアンス センターでの電子情報開示のMicrosoft 365ケース</span><span class="sxs-lookup"><span data-stu-id="bb83d-158">Core eDiscovery cases in the Microsoft 365 compliance center</span></span> </td>
<td><p><span data-ttu-id="bb83d-159">コアの電子情報開示ケースの機能を使用すると、電子情報開示と保留リストのIn-PlaceパリティIn-Placeします。</span><span class="sxs-lookup"><span data-stu-id="bb83d-159">Using the capabilities of core eDiscovery cases provide the functional parity to In-Place eDiscovery and In-Place Holds.</span></span> <span data-ttu-id="bb83d-160">エクスポートできるものには、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="bb83d-160">This includes the following:</span></span></p>
<ul>
<li>
<p><span data-ttu-id="bb83d-161">検索は数百万の場所に拡大縮小されます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-161">Search scales to millions of locations</span></span></p>
</li>
<li>
<p><span data-ttu-id="bb83d-162">コンテンツの検索、エクスポート、および保留に関する信頼性の向上</span><span class="sxs-lookup"><span data-stu-id="bb83d-162">Higher reliability for searching, exporting, and placing content on hold</span></span></p>
</li>
<li>
<p><span data-ttu-id="bb83d-163">Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft Teams、Yammer グループ、Microsoft 365 グループ、Office 365 アプリケーションに保存されている他のコンテンツの検索</span><span class="sxs-lookup"><span data-stu-id="bb83d-163">Searching for content in for Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams, Yammer Groups, Microsoft 365 Groups, and other content stored in Office 365 applications</span></span></p></li></ul>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="bb83d-164">保持の目的で保持する</span><span class="sxs-lookup"><span data-stu-id="bb83d-164">Hold for retention purposes</span></span></td>
<td><span data-ttu-id="bb83d-165">コンプライアンス センター Microsoft 365保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="bb83d-165">Retention policies in the Microsoft 365 compliance center</span></span></td>
<td><p><span data-ttu-id="bb83d-166">アイテム保持ポリシーを使用してコンテンツを保持し、必要に応じて保持期間が経過した後に削除できます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-166">You can use Retention policies to retain content and, if desired, delete it after the retention period expires.</span></span> <span data-ttu-id="bb83d-167">その他の機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bb83d-167">Other capabilities include:</span></span></p>
<ul>
<li>
<p><span data-ttu-id="bb83d-168">組織全体にポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="bb83d-168">Applying policies to your entire organization</span></span> </p>
</li><li>
<p><span data-ttu-id="bb83d-169">Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft Teams、Office 365 グループなどの特定のコンテンツの場所にポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="bb83d-169">Applying policies to specific content locations such as Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams, and Office 365 Groups</span></span></p></li>
<li>
<p><span data-ttu-id="bb83d-170">特定のユーザーにポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="bb83d-170">Applying policies to specific users</span></span></p></li></ul>
<p><span data-ttu-id="bb83d-171">詳細については、「アイテム保持ポリシー <a href="/microsoft-365/compliance/retention-policies"> と保持ラベルについて」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="bb83d-171">For more information, see <a href="/microsoft-365/compliance/retention-policies"> Learn about retention policies and retention labels</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bb83d-172">確認のために電子メール検索結果を探索メールボックスにコピーする</span><span class="sxs-lookup"><span data-stu-id="bb83d-172">Copy email search results to a discovery mailbox for review</span></span></td><td><span data-ttu-id="bb83d-173">v2.0 でAdvanced eDiscoveryを確認する</span><span class="sxs-lookup"><span data-stu-id="bb83d-173">Review sets in Advanced eDiscovery v2.0</span></span></td>
<td><p><span data-ttu-id="bb83d-174">サイト内のコンテンツMicrosoft 365簡単に確認できます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-174">Reviewing content in Microsoft 365 has never been easier.</span></span> <span data-ttu-id="bb83d-175">レビュー セットには、次を含む、レビューに必要な時間とデータの削減に役立つ多くの機能があります。</span><span class="sxs-lookup"><span data-stu-id="bb83d-175">Review sets have many great capabilities to help reduce the amount of time and data needed to review, including:</span></span></p>
<ul>
<li><p><span data-ttu-id="bb83d-176">レビュー セットで高速検索クエリを実行し、コンテンツをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="bb83d-176">Perform fast search queries and filter content in a review set</span></span></p></li>
<li><p><span data-ttu-id="bb83d-177">レビュー セット内のコンテンツを分析する。これには、電子メール スレッド、重複に近い検出、テーマ分析、予測コーディングが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-177">Analyze content in a review set; this includes email threading, near-duplicate detection, Themes analysis, and Predictive coding</span></span></p></li>
<li><p><span data-ttu-id="bb83d-178">レビュー セット内のドキュメントをタグ付けする</span><span class="sxs-lookup"><span data-stu-id="bb83d-178">Tag documents in a review set</span></span></p></li>
<li><p><span data-ttu-id="bb83d-179">弁護士クライアント特権コンテンツの識別に役立つタグ付け提案</span><span class="sxs-lookup"><span data-stu-id="bb83d-179">Tagging suggestions to help identify attorney  client privilege content</span></span></p></li></ul>
<p><span data-ttu-id="bb83d-180">詳細については、「<a href="/microsoft-365/compliance/overview-ediscovery-20">Microsoft 365 の Advanced eDiscovery ソリューションの概要</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb83d-180">For more information, see <a href="/microsoft-365/compliance/overview-ediscovery-20">Overview of the Advanced eDiscovery solution in Microsoft 365</a>.</span></span></p>
<p>
<p><span data-ttu-id="bb83d-181">または、検索結果を PST ファイルにエクスポートし、Microsoft 365インポート サービスを使用して、PST を探索メールボックスにインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-181">Alternatively, you can export search results to PST files and then use Microsoft 365 Import service to import the PSTs to a discovery mailbox.</span></span> <span data-ttu-id="bb83d-182">手順については、「ネットワーク アップロードを使用して PST ファイルをインポートしてファイルをインポートする」を<a href="/microsoft-365/compliance/use-network-upload-to-import-pst-files">参照</a>Office 365。</span><span class="sxs-lookup"><span data-stu-id="bb83d-182">For step-by-step instruction, see <a href="/microsoft-365/compliance/use-network-upload-to-import-pst-files">Use network upload to import PST files to Office 365</a>.</span></span>
</tr>
<tr class=even>
  <td><span data-ttu-id="bb83d-183">1 つのメールボックスから別のメールボックスへのメッセージのコピー</span><span class="sxs-lookup"><span data-stu-id="bb83d-183">Copy messages from one mailbox to a different mailbox</span></span></td>
  <td><span data-ttu-id="bb83d-184"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">メールボックスへのアクセス許可の割り当て</a></span><span class="sxs-lookup"><span data-stu-id="bb83d-184"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
  <td><span data-ttu-id="bb83d-185">他のユーザーの電子メールへのアクセス権をユーザーに付与するには (従業員が組織を離れ、他のユーザーに元従業員のメールへのアクセス権を与える必要がある場合など)、そのユーザーに元従業員のメールボックスにアクセスするためのアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb83d-185">To give a person access to another user's email (such as when an employee leaves your organization and you need to give another person access to the former employee's email), we recommended that you assign that person permissions to access the former employee's mailbox.</span></span> <span data-ttu-id="bb83d-186">そのため、メールボックス アイテムを別のユーザー メールボックスまたは共有メールボックスにコピーする代わりに、ソース メールボックスにアクセスするためのユーザーアクセス許可を割り当てるだけ。</span><span class="sxs-lookup"><span data-stu-id="bb83d-186">So instead of copying mailbox items to another user mailbox or a shared mailbox, just assign a user permissions to access the source mailbox.</span></span></td>
  
  </tr>
<tr class="odd">
<td><span data-ttu-id="bb83d-187">回復可能なアイテム フォルダーからアイテムを復元する</span><span class="sxs-lookup"><span data-stu-id="bb83d-187">Restore items from the Recoverable Items folder</span></span></td>
  <td><span data-ttu-id="bb83d-188"><a href="/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</span><span class="sxs-lookup"><span data-stu-id="bb83d-188"><a href="/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</span></span></td>
  <td><span data-ttu-id="bb83d-189">アイテムの削除済みアイテムの保持期間が経過しない<i></i>限り、メールボックス内の完全に削除されたアイテム (ソフト削除済みアイテムとも呼ばれる) を復元できます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-189">You can restore permanently deleted items (also known as <i>soft-deleted</i> items) in mailboxes, as long as the deleted item retention period for an item hasn't expired.</span></span> <span data-ttu-id="bb83d-190">詳細については、「回復可能な<a href="/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">アイテム フォルダー」を参照Exchange Online。</a></span><span class="sxs-lookup"><span data-stu-id="bb83d-190">For more information, see <a href="/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Recoverable Items folder in Exchange Online</a>.</span></span></td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a><span data-ttu-id="bb83d-191">インプレース電子情報開示とインプレース ホールドに関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="bb83d-191">FAQs about In-Place eDiscovery and In-Place Holds</span></span>

<span data-ttu-id="bb83d-192">**EAC で電子情報開示 In-Place保持&検索結果のコピー機能を使用して、弁護士によるレビューのために検索結果を探索メールボックスにコピーします。どのようなオプションがありますか?**</span><span class="sxs-lookup"><span data-stu-id="bb83d-192">**I use the copy search results functionality of In-Place eDiscovery & Holds in the EAC to copy search results to a discovery mailbox for review by attorneys. What options do I have now?**</span></span>

<span data-ttu-id="bb83d-193">今日、この機能をレプリケートする方法は 2 通りあります。</span><span class="sxs-lookup"><span data-stu-id="bb83d-193">There are two ways to replicate this functionality today.</span></span> <span data-ttu-id="bb83d-194">1 つ目は[、v2.0](./view-documents-in-review-set.md)のレビュー セットAdvanced eDiscovery使用します。</span><span class="sxs-lookup"><span data-stu-id="bb83d-194">The first is to use [review sets in Advanced eDiscovery v2.0](./view-documents-in-review-set.md).</span></span> <span data-ttu-id="bb83d-195">レビュー セットには、ドキュメントの高速検索、タグ付け、メール スレッド、重複グループ化に近い、テーマ分析、予測コーディングなど、従来のレビュー ツールに表示される機能の多くがあります。</span><span class="sxs-lookup"><span data-stu-id="bb83d-195">Review sets have many of the same capabilities you see in a traditional review tool like fast search of documents, tagging, email threading, near duplicate grouping, themes analysis, and predictive coding.</span></span> <span data-ttu-id="bb83d-196">引き続き確認のために探索メールボックスを使用する場合、2 番目のオプションは、検索結果を PST ファイルにエクスポートし、Microsoft コンプライアンス センターの [PST](use-network-upload-to-import-pst-files.md) インポート機能を使用して、PST ファイルを探索メールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="bb83d-196">If you still want to use discovery mailboxes for review, the second option is to export search results to PST files and then import the PST files to a discovery mailbox by using the [PST import feature](use-network-upload-to-import-pst-files.md) in the Microsoft compliance center.</span></span>

<span data-ttu-id="bb83d-197">**電子情報開示マネージャーが新しいツールを使用して検索できるコンテンツの場所 (メールボックスやサイトなど) を制御する方法**</span><span class="sxs-lookup"><span data-stu-id="bb83d-197">**How do I control which content locations (such as mailboxes or sites) that can an eDiscovery manager can search using the new tools?**</span></span>

<span data-ttu-id="bb83d-198">またMicrosoft 365コンプライアンス センターは、コンプライアンスの[](set-up-compliance-boundaries.md)境界を使用して、電子情報開示マネージャーが検索できるコンテンツの場所を制御します。</span><span class="sxs-lookup"><span data-stu-id="bb83d-198">The Microsoft 365 compliance center also uses [compliance boundaries](set-up-compliance-boundaries.md) to control which content locations an eDiscovery Manager can search.</span></span> <span data-ttu-id="bb83d-199">コンプライアンスの境界は、政府機関の境界内にとどまる必要がある政府機関や、地理的な下宿主を尊重するために必要な多国籍企業で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-199">Compliance boundaries are useful in government entities that need to stay within agency boundaries or multi-national corporations required to respect geographical boarders.</span></span>

<span data-ttu-id="bb83d-200">**現在の検索と保持をコンプライアンス センターに移動Microsoft 365方法**</span><span class="sxs-lookup"><span data-stu-id="bb83d-200">**How can I move my current searches and holds to the Microsoft 365 compliance center?**</span></span>

<span data-ttu-id="bb83d-201">PowerShell を使用して電子情報開示In-Place EAC から電子情報開示の検索と保持を移行できます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-201">It's possible to migrate In-Place eDiscovery searches and holds from the EAC by using PowerShell.</span></span> <span data-ttu-id="bb83d-202">手順については[、「EAC から](./migrate-legacy-ediscovery-searches-and-holds.md)コンプライアンス センターへの検索と保持の移行Microsoft 365参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb83d-202">For instructions, see [Migrate searches and holds from the EAC to the Microsoft 365 compliance center](./migrate-legacy-ediscovery-searches-and-holds.md).</span></span>

## <a name="-mailboxsearch-cmdlets"></a><span data-ttu-id="bb83d-203">\*-MailboxSearch コマンドレット</span><span class="sxs-lookup"><span data-stu-id="bb83d-203">\*-MailboxSearch cmdlets</span></span>

<span data-ttu-id="bb83d-204">Exchange 管理センターで 2017 年 7 月 1 日に発表された元の通知に基づいて、In-Place 電子情報開示 & ホールド機能と対応する **\* -MailboxSearch** コマンドレットは廃止されます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-204">As per the original notice announced on July 1, 2017 in the Exchange admin center, the In-Place eDiscovery & Hold functionality and the corresponding **\*-MailboxSearch** cmdlets are being retired.</span></span> <span data-ttu-id="bb83d-205">これらのコマンドレットを使用すると、ユーザーは、法的、規制、およびパブリック要求のためにメールボックス コンテンツを検索、保持、およびエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-205">These cmdlets provide users the ability to search, hold, and export mailbox content for legal, regulatory, and public requests.</span></span>

<span data-ttu-id="bb83d-206">これらの機能は[<span class="underline">、パフォーマンス</span>](./microsoft-365-compliance-center.md)とスケーラビリティが向上した Microsoft 365 コンプライアンス センターと Office 365 セキュリティ & コンプライアンス センター PowerShell で利用できる機能なので、これらの強化されたコマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb83d-206">Because these capabilities are now available in the [<span class="underline">Microsoft 365 compliance center</span>](./microsoft-365-compliance-center.md) and Office 365 Security & Compliance Center PowerShell with improved performance and scalability, you should using these improved cmdlets.</span></span> <span data-ttu-id="bb83d-207">これらのコマンドレットには[<span class="underline"> \* 、-ComplianceCase</span>](/powershell/module/exchange/get-compliancecase) [<span class="underline">、-ComplianceSearch、-CaseHoldPolicy、-CaseHoldRule、 \* </span>](/powershell/module/exchange/get-compliancesearch)[<span class="underline"> \* および -ComplianceSearchAction が含まれます</span>](/powershell/module/exchange/get-compliancesearchaction)。 [<span class="underline"> \* </span>](/powershell/module/exchange/get-caseholdpolicy) [<span class="underline"> \* </span>](/powershell/module/exchange/get-caseholdrule)</span><span class="sxs-lookup"><span data-stu-id="bb83d-207">These cmdlets include [<span class="underline">\*-ComplianceCase</span>](/powershell/module/exchange/get-compliancecase), [<span class="underline">\*-ComplianceSearch</span>](/powershell/module/exchange/get-compliancesearch), [<span class="underline">\*-CaseHoldPolicy</span>](/powershell/module/exchange/get-caseholdpolicy), [<span class="underline">\*-CaseHoldRule</span>](/powershell/module/exchange/get-caseholdrule), and [<span class="underline">\*-ComplianceSearchAction</span>](/powershell/module/exchange/get-compliancesearchaction).</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="bb83d-208">影響を受ける組織の範囲</span><span class="sxs-lookup"><span data-stu-id="bb83d-208">Scope of affected organizations</span></span>

- <span data-ttu-id="bb83d-209">Office 365およびMicrosoft 365 Enterprise組織</span><span class="sxs-lookup"><span data-stu-id="bb83d-209">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="bb83d-210">Office 365およびMicrosoft 365 Education組織</span><span class="sxs-lookup"><span data-stu-id="bb83d-210">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="bb83d-211">Office 365およびMicrosoft 365組織。これには、GCC、GCC、DoD が含まれます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-211">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="bb83d-212">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="bb83d-212">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="bb83d-213">タイムライン</span><span class="sxs-lookup"><span data-stu-id="bb83d-213">Timeline</span></span>

- <span data-ttu-id="bb83d-214">2020 年 7 月 1 日: **New-MailboxSearch** を使用して新しい In-Place 電子情報開示検索と In-Place 保留リストを作成することはできませんが、コマンドレットを使用して既存の検索と保持を実行、編集、および削除することができます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-214">July 1, 2020: You won't be able to use **New-MailboxSearch** to create new In-Place eDiscovery searches and In-Place Holds, but you can still use cmdlets to run, edit, and delete existing searches and holds at your own risk.</span></span> <span data-ttu-id="bb83d-215">Microsoft サポートは、このような種類の検索と保留に関するサポートを提供しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="bb83d-215">Microsoft Support will no longer provide assistance for these types of searches and holds.</span></span>

- <span data-ttu-id="bb83d-216">2020 年 10 月 1 日: 前に述べたように、eAC の In-Place 電子情報開示 & Holds 機能は読み取り専用モードになります。</span><span class="sxs-lookup"><span data-stu-id="bb83d-216">October 1, 2020: As previously stated, The In-Place eDiscovery & Holds functionality in the EAC will be placed in a read-only mode.</span></span> <span data-ttu-id="bb83d-217">つまり **、New-MailboxSearch** コマンドレット **、Start-MailboxSearch** コマンドレット、 **または Set-MailboxSearch** コマンドレットを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="bb83d-217">That also means that you won't be able to use the **New-MailboxSearch**, **Start-MailboxSearch**, or **Set-MailboxSearch** cmdlets.</span></span> <span data-ttu-id="bb83d-218">既存の検索と保留リストのみを取得および削除できます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-218">You'll only be able to get and remove existing searches and holds.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="bb83d-219">代替ツール</span><span class="sxs-lookup"><span data-stu-id="bb83d-219">Alternative tools</span></span>

<span data-ttu-id="bb83d-220">次の表では、廃止される既存の機能を置き換える他のツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bb83d-220">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="bb83d-221">機能</span><span class="sxs-lookup"><span data-stu-id="bb83d-221">Functionality</span></span></th>
<th><span data-ttu-id="bb83d-222">代替ツール</span><span class="sxs-lookup"><span data-stu-id="bb83d-222">Alternative tools</span></span></th>
<th><span data-ttu-id="bb83d-223">コメント</span><span class="sxs-lookup"><span data-stu-id="bb83d-223">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="bb83d-224">検索とエクスポート</span><span class="sxs-lookup"><span data-stu-id="bb83d-224">Search and export</span></span></td>
<td><p><span data-ttu-id="bb83d-225"><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span><span class="sxs-lookup"><span data-stu-id="bb83d-225"><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="bb83d-226"><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span><span class="sxs-lookup"><span data-stu-id="bb83d-226"><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p><span data-ttu-id="bb83d-227"><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span><span class="sxs-lookup"><span data-stu-id="bb83d-227"><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span></span></p>
<p> </p></td>
<td><p><span data-ttu-id="bb83d-228">ComplianceSearch コマンドレットと ComplianceSearchAction コマンドレットは、コンテンツの検索とエクスポートに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-228">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and export content.</span></span> <span data-ttu-id="bb83d-229">新しい検索を作成し、検索見積もりを表示するには<strong>、New-、Get-、</strong><strong>および</strong> <strong>Start-ComplianceSearch</strong>コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="bb83d-229">You can create a new search and view the search estimate by using the <strong>New-</strong>, <strong>Get-</strong>, and <strong>Start-ComplianceSearch</strong> cmdlets.</span></span> <span data-ttu-id="bb83d-230">次に <strong>、New-ComplianceSearchAction</strong> コマンドレットを使用して検索結果をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-230">Then you can use the <strong>New-ComplianceSearchAction</strong> cmdlet to export the search results.</span></span> <span data-ttu-id="bb83d-231">これらの検索結果をローカル コンピューターにダウンロードするには、コンプライアンス センターのMicrosoft 365電子情報開示ツールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb83d-231">You'll still have to use the core eDiscovery tool in the Microsoft 365 compliance center to download those search results to your local computer.</span></span></p>
<p>
<p><span data-ttu-id="bb83d-232"><strong>注:</strong>これらのコマンドレットを使用して、コアの電子情報開示ケースに関連付けされていない検索を作成する場合、これらの検索は Microsoft 365 コンプライアンス センター<strong></strong>の [コンテンツ検索] ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-232"><strong>Note:</strong> If you use these cmdlets to create searches that aren't associated with a core eDiscovery case, these searches will be located on the <strong>Content search</strong> page in the Microsoft 365 compliance center.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bb83d-233">メールボックス内のコンテンツを保持する</span><span class="sxs-lookup"><span data-stu-id="bb83d-233">Hold content in a mailbox</span></span></td>
<td><p><span data-ttu-id="bb83d-234"><a href="/powershell/module/exchange/get-caseholdpolicy"><span class="underline">\*-CaseHoldPolicy</span></a></span><span class="sxs-lookup"><span data-stu-id="bb83d-234"><a href="/powershell/module/exchange/get-caseholdpolicy"><span class="underline">\*-CaseHoldPolicy</span></a></span></span></p>
<p><span data-ttu-id="bb83d-235"><a href="/powershell/module/exchange/get-caseholdrule"><span class="underline">\*-CaseHoldRule</span></a></span><span class="sxs-lookup"><span data-stu-id="bb83d-235"><a href="/powershell/module/exchange/get-caseholdrule"><span class="underline">\*-CaseHoldRule</span></a></span></span></p>
<p><span data-ttu-id="bb83d-236"><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span><span class="sxs-lookup"><span data-stu-id="bb83d-236"><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span></span></p>
<p> </p></td>
<td><p><span data-ttu-id="bb83d-237">コンプライアンス センター内Microsoft 365コンプライアンス ケースに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb83d-237">Holds in the Microsoft 365 compliance center must be associated with a ComplianceCase.</span></span> <span data-ttu-id="bb83d-238">まず、コンプライアンス ケースを作成し、CaseHoldPolicy と CaseHoldRule を作成します。</span><span class="sxs-lookup"><span data-stu-id="bb83d-238">First, create the compliance case, and then create a CaseHoldPolicy and a CaseHoldRule.</span></span></p>
<p><span data-ttu-id="bb83d-239"><strong>注:</strong> CaseHoldRule を作成せずに CaseHoldPolicy を作成すると、CaseHoldRule が作成され CaseHoldPolicy に関連付けられるまで、ホールドは操作不能になります。</span><span class="sxs-lookup"><span data-stu-id="bb83d-239"><strong>Note:</strong> Creating a CaseHoldPolicy without a creating CaseHoldRule will render the hold inoperable until the CaseHoldRule is created and associated to the CaseHoldPolicy.</span></span> <span data-ttu-id="bb83d-240">詳細については、コマンドレットのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb83d-240">See the cmdlet documentation for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bb83d-241">検索結果を探索メールボックスにコピーする</span><span class="sxs-lookup"><span data-stu-id="bb83d-241">Copy search results to a discovery mailbox</span></span></td>
<td><span data-ttu-id="bb83d-242">なし</span><span class="sxs-lookup"><span data-stu-id="bb83d-242">None</span></span></td>
<td><span data-ttu-id="bb83d-243">この機能は、すべてのサービスにアクセスできるMicrosoft 365はありません。</span><span class="sxs-lookup"><span data-stu-id="bb83d-243">There's no direct replacement for this functionality because it does not provide access to all Microsoft 365 services.</span></span> <span data-ttu-id="bb83d-244">代替ソリューションについては、以下の FAQ を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb83d-244">See the following FAQ below for alternative solutions.</span></span></td>
</tr>
  <tr class=even>
  <td><span data-ttu-id="bb83d-245">1 つのメールボックスから別のメールボックスへのメッセージのコピー</span><span class="sxs-lookup"><span data-stu-id="bb83d-245">Copy messages from one mailbox to a different mailbox</span></span></td>
  <td><span data-ttu-id="bb83d-246"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">メールボックスへのアクセス許可の割り当て</a></span><span class="sxs-lookup"><span data-stu-id="bb83d-246"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
  <td><span data-ttu-id="bb83d-247">他のユーザーの電子メールへのアクセス権をユーザーに付与するには (従業員が組織を離れ、他のユーザーに元従業員のメールへのアクセス権を与える必要がある場合など)、そのユーザーに元従業員のメールボックスにアクセスするためのアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb83d-247">To give a person access to another user's email (such as when an employee leaves your organization and you need to give another person access to the former employee's email), we recommended that you assign that person permissions to access the former employee's mailbox.</span></span> <span data-ttu-id="bb83d-248">そのため、メールボックス アイテムを別のユーザー メールボックスまたは共有メールボックスにコピーする代わりに、ソース メールボックスにアクセスするためのユーザーアクセス許可を割り当てるだけ。</span><span class="sxs-lookup"><span data-stu-id="bb83d-248">So instead of copying mailbox items to another user mailbox or a shared mailbox, just assign a user permissions to access the source mailbox.</span></span></td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a><span data-ttu-id="bb83d-249">\***-MailboxSearch コマンドレットに関する** よくある質問</span><span class="sxs-lookup"><span data-stu-id="bb83d-249">FAQs about \***-MailboxSearch** cmdlets</span></span>

<span data-ttu-id="bb83d-250">**コピー検索を使用して、他の電子情報開示および法的調査のために電子メール メッセージまたはインスタント メッセージをエクスポートします。これらのコマンドレットが廃止された後、他にどのようなオプションがありますか?**</span><span class="sxs-lookup"><span data-stu-id="bb83d-250">**We use Copy Search to export email messages or instant Messages for purposes other eDiscovery and legal investigations. What other options do we have after these cmdlets are retired?**</span></span>

<span data-ttu-id="bb83d-251">[<span class="underline">Microsoft Graph API</span>](https://developer.microsoft.com/en-us/graph)には、-MailboxSearch コマンドレットを使用するよりもはるかに回復性と拡張性を備えた分析などの目的でデータを抽出するためのメソッドが多数用意 **\*** されています。</span><span class="sxs-lookup"><span data-stu-id="bb83d-251">The [<span class="underline">Microsoft Graph APIs</span>](https://developer.microsoft.com/en-us/graph) provide a number of methods for extracting data for analysis and other purposes that are far more resilient and scalable than the using the **\*-MailboxSearch** cmdlets.</span></span>

<span data-ttu-id="bb83d-252">**検索と保持をコンプライアンス センターに移行Microsoft 365方法**</span><span class="sxs-lookup"><span data-stu-id="bb83d-252">**How can I migrate my searches and holds to the Microsoft 365 compliance center?**</span></span>

<span data-ttu-id="bb83d-253">PowerShell スクリプトを使用して、In-Placeから電子情報開示の検索と保持Exchange移行できます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-253">It's possible to migrate In-Place eDiscovery searches and holds from the Exchange admin center by using a PowerShell script.</span></span> <span data-ttu-id="bb83d-254">詳細については、「従来の電子情報開示の検索と保持をコンプライアンス センターに移行[するMicrosoft 365参照してください](migrate-legacy-eDiscovery-searches-and-holds.md)。</span><span class="sxs-lookup"><span data-stu-id="bb83d-254">For more information, see [Migrate legacy eDiscovery searches and holds to the Microsoft 365 compliance center](migrate-legacy-eDiscovery-searches-and-holds.md).</span></span>

<span data-ttu-id="bb83d-255">**コマンドレットが廃止された後も、検索を削除または取得できますか?**</span><span class="sxs-lookup"><span data-stu-id="bb83d-255">**After the cmdlets are retired, will I still be able to remove or retrieve searches?**</span></span>

<span data-ttu-id="bb83d-256">はい、検索を作成および変更する機能は削除しますが **、Get-MailboxSearch と Remove-MailboxSearch** は、詳細な通知が表示されるまで引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-256">Yes, although we're removing the ability to create and modify searches, you'll still be able to use **Get-MailboxSearch** and **Remove-MailboxSearch** until further notice.</span></span> <span data-ttu-id="bb83d-257">ただし、これらのコマンドレットの使用は、退職日後に自身のリスクにさらされ、Microsoft サポートはサポートを提供できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="bb83d-257">However, the use of these cmdlets will be at your own risk after the retirement dates and Microsoft Support will no longer be able to provide assistance.</span></span>

## <a name="search-mailbox-cmdlet"></a><span data-ttu-id="bb83d-258">Search-Mailbox コマンドレット</span><span class="sxs-lookup"><span data-stu-id="bb83d-258">Search-Mailbox cmdlet</span></span>

<span data-ttu-id="bb83d-259">PowerShell **の Search-Mailbox** コマンドレットExchange Online、2018 年からコマンドレット出力の警告で最初に発表されたので廃止されます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-259">The **Search-Mailbox** cmdlet in Exchange Online PowerShell is being retired as originally announced in a warning in the cmdlet output starting back in 2018.</span></span> <span data-ttu-id="bb83d-260">**Search-Mailbox コマンドレット** は、もともとユーザーのメールボックスを検索し、悪意のあるコンテンツを削除するために使用されています。</span><span class="sxs-lookup"><span data-stu-id="bb83d-260">The **Search-Mailbox** cmdlet was originally used to search a user's mailbox and purge malicious content.</span></span> <span data-ttu-id="bb83d-261">コンテンツを検索および削除するには、Office 365 セキュリティ & コンプライアンス センター PowerShell の **New-ComplianceSearch** コマンドレットと **New-ComplianceSearchAction** コマンドレットの使用を開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bb83d-261">We recommend that you start using the **New-ComplianceSearch** and **New-ComplianceSearchAction** cmdlets in Office 365 Security & Compliance Center PowerShell to search for and purge content.</span></span> <span data-ttu-id="bb83d-262">組み込みのセキュリティ エクスペリエンスでは、電子メール[<span class="underline">Microsoft 365</span>](../security/index.yml)他の多くのセキュリティ機能に対する堅牢な脅威保護が提供Microsoft サービス。</span><span class="sxs-lookup"><span data-stu-id="bb83d-262">For a built-in security experience, the [<span class="underline">Microsoft 365 security features</span>](../security/index.yml) provide robust threat protection for email and many other Microsoft services.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="bb83d-263">影響を受ける組織の範囲</span><span class="sxs-lookup"><span data-stu-id="bb83d-263">Scope of affected organizations</span></span>

- <span data-ttu-id="bb83d-264">Office 365およびMicrosoft 365 Enterprise組織</span><span class="sxs-lookup"><span data-stu-id="bb83d-264">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="bb83d-265">Office 365およびMicrosoft 365 Education組織</span><span class="sxs-lookup"><span data-stu-id="bb83d-265">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="bb83d-266">Office 365およびMicrosoft 365組織。これには、GCC、GCC、DoD が含まれます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-266">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="bb83d-267">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="bb83d-267">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="bb83d-268">タイムライン</span><span class="sxs-lookup"><span data-stu-id="bb83d-268">Timeline</span></span>

-  <span data-ttu-id="bb83d-269">2020 年 7 月 1 日: **Search-Mailbox** コマンドレットは使用できなくなりました。Microsoft サポートはサポートを提供しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="bb83d-269">July 1, 2020: The **Search-Mailbox** cmdlet will no longer be available and Microsoft Support will no longer provide assistance.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="bb83d-270">代替ツール</span><span class="sxs-lookup"><span data-stu-id="bb83d-270">Alternative tools</span></span>

<span data-ttu-id="bb83d-271">次の表では、廃止される既存の機能を置き換える他のツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bb83d-271">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="bb83d-272">機能</span><span class="sxs-lookup"><span data-stu-id="bb83d-272">Functionality</span></span></th>
<th><span data-ttu-id="bb83d-273">代替ツール</span><span class="sxs-lookup"><span data-stu-id="bb83d-273">Alternative tools</span></span></th>
<th><span data-ttu-id="bb83d-274">コメント</span><span class="sxs-lookup"><span data-stu-id="bb83d-274">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="bb83d-275">メールボックスを検索する</span><span class="sxs-lookup"><span data-stu-id="bb83d-275">Search a mailbox</span></span></td>
<td><p><span data-ttu-id="bb83d-276"><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span><span class="sxs-lookup"><span data-stu-id="bb83d-276"><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="bb83d-277"><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span><span class="sxs-lookup"><span data-stu-id="bb83d-277"><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p></a></p></td>
<td><p><span data-ttu-id="bb83d-278">ComplianceSearch コマンドレットと ComplianceSearchAction コマンドレットは、コンテンツの検索とエクスポートに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-278">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and export content.</span></span> <span data-ttu-id="bb83d-279">新しい検索を作成し、検索見積もりを表示するには<strong>、New-、Get-、</strong><strong>および</strong> <strong>Start-ComplianceSearch</strong>コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="bb83d-279">You can create a new search and view the search estimate by using the <strong>New-</strong>, <strong>Get-</strong>, and <strong>Start-ComplianceSearch</strong> cmdlets.</span></span> <span data-ttu-id="bb83d-280">次に <strong>、New-ComplianceSearchAction -Export</strong> コマンドを使用して検索結果をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-280">Then you can use the <strong>New-ComplianceSearchAction -Export</strong> command to export the search results.</span></span> <span data-ttu-id="bb83d-281">これらの検索結果をローカル コンピューターにダウンロードするには、コンプライアンス センターのMicrosoft 365電子情報開示ツールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb83d-281">You'll still have to use the core eDiscovery tool in the Microsoft 365 compliance center to download those search results to your local computer.</span></span></p></p>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="bb83d-282">メールボックスから一括メールを削除する</span><span class="sxs-lookup"><span data-stu-id="bb83d-282">Delete bulk email from a mailbox</span></span></td>
<td><p><span data-ttu-id="bb83d-283"><a href="/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">メールボックスのアーカイブと削除ポリシーを設定する</span></a></span><span class="sxs-lookup"><span data-stu-id="bb83d-283"><a href="/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">Set up an archive and deletion policy for mailboxes</span></a></span></span></p>
<p></p></td>
<td><p><span data-ttu-id="bb83d-284">管理者は、ユーザーのアーカイブ メールボックスにアイテムを自動的に移動し、メールボックスからアイテムを自動的に削除するアーカイブおよび削除ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-284">Admins can create an archiving and deletion policy that automatically moves items to a user's archive mailbox and automatically deletes items from the mailbox.</span></span></p>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="bb83d-285">検索結果を探索メールボックスにコピーする</span><span class="sxs-lookup"><span data-stu-id="bb83d-285">Copy search results to a discovery mailbox</span></span></td>
<td> </td>
<td><span data-ttu-id="bb83d-286">この機能は、すべてのサービスにアクセスできるMicrosoft 365はありません。</span><span class="sxs-lookup"><span data-stu-id="bb83d-286">There's no direct replacement for this functionality because it does not provide access to all Microsoft 365 services.</span></span> <span data-ttu-id="bb83d-287">代替ソリューションについては <strong>、「\*-MailboxSearch コマンドレット</strong> 」の「FAQ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb83d-287">See the FAQs in the <strong>\*-MailboxSearch cmdlets</strong> section for alternative solutions.</span></span> </td>
</tr>
<tr class=odd>
  <td><span data-ttu-id="bb83d-288">1 つのメールボックスから別のメールボックスへのメッセージのコピー</span><span class="sxs-lookup"><span data-stu-id="bb83d-288">Copy messages from one mailbox to a different mailbox</span></span></td>
  <td><span data-ttu-id="bb83d-289"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">メールボックスへのアクセス許可の割り当て</a></span><span class="sxs-lookup"><span data-stu-id="bb83d-289"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
  <td><span data-ttu-id="bb83d-290">他のユーザーの電子メールへのアクセス権をユーザーに付与するには (従業員が組織を離れ、他のユーザーに元従業員のメールへのアクセス権を与える必要がある場合など)、そのユーザーに元従業員のメールボックスにアクセスするためのアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb83d-290">To give a person access to another user's email (such as when an employee leaves your organization and you need to give another person access to the former employee's email), we recommended that you assign that person permissions to access the former employee's mailbox.</span></span> <span data-ttu-id="bb83d-291">そのため、メールボックス アイテムを別のユーザー メールボックスまたは共有メールボックスにコピーする代わりに、ソース メールボックスにアクセスするためのユーザーアクセス許可を割り当てるだけ。</span><span class="sxs-lookup"><span data-stu-id="bb83d-291">So instead of copying mailbox items to another user mailbox or a shared mailbox, just assign a user permissions to access the source mailbox.</span></span></td>
</tr>
<tr class=even>
  <td><span data-ttu-id="bb83d-292">メールボックスからメッセージを削除する</span><span class="sxs-lookup"><span data-stu-id="bb83d-292">Purge messages from a mailbox</span></span></td>
<td><p><span data-ttu-id="bb83d-293"><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span><span class="sxs-lookup"><span data-stu-id="bb83d-293"><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="bb83d-294"><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span><span class="sxs-lookup"><span data-stu-id="bb83d-294"><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p></p></td>
<td><p><span data-ttu-id="bb83d-295">ComplianceSearch コマンドレットと ComplianceSearchAction コマンドレットは、コンテンツの検索と削除に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-295">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and purge content.</span></span> <span data-ttu-id="bb83d-296"><strong>New-ComplianceSearch</strong>コマンドレットと<strong>New-ComplianceSearch</strong>コマンドレットを使用して検索を作成して実行し<strong>、New-ComplianceSearchAction -Purge -PurgeType</strong>コマンドを使用してコンテンツを削除できます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-296">You can create and run a search with <strong>New-ComplianceSearch</strong> and <strong>New-ComplianceSearch</strong> cmdlets, and then you can purge the content by using <strong>New-ComplianceSearchAction -Purge -PurgeType</strong> command.</span></span> <span data-ttu-id="bb83d-297">詳細については、「メッセージの検索と <a href="/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">削除」を参照してください</span></a>。</span><span class="sxs-lookup"><span data-stu-id="bb83d-297">For more information, see <a href="/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">Search for and delete messages</span></a>.</span></span></p>
</td>
</tr>
<tr class="odd"> 
<td><span data-ttu-id="bb83d-298">メールボックスからメッセージを削除する</span><span class="sxs-lookup"><span data-stu-id="bb83d-298">Purge messages from a mailbox</span></span></td>
<td><span data-ttu-id="bb83d-299"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">メールボックスへのアクセス許可の割り当て</a></span><span class="sxs-lookup"><span data-stu-id="bb83d-299"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
<td><span data-ttu-id="bb83d-300">メールボックスからメッセージを削除するには、管理者のアクセス許可を割り当て、従業員のメールボックスにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="bb83d-300">To purge messages from a mailbox, assign an administrator permissions to access the employee's mailbox.</span></span> <span data-ttu-id="bb83d-301">メッセージは、必要に応じて削除およびリサイクルできます。この機能は、Outlook の組み込みの検索機能と表示機能を利用します。</span><span class="sxs-lookup"><span data-stu-id="bb83d-301">Messages can be deleted and recycled as needed taking advantage of the built in search and viewing capabilities in Outlook.</span></span></td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a><span data-ttu-id="bb83d-302">ExchangeWeb サービス API の操作</span><span class="sxs-lookup"><span data-stu-id="bb83d-302">Exchange Web Services API operations</span></span>

<span data-ttu-id="bb83d-303">Exchange Web Services API のこれらの操作は、Exchange 管理センターの In-Place 電子情報開示 & 保留機能と、Exchange Online PowerShell の対応する **\* -MailboxSearch** コマンドレットによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-303">These operations in the Exchange Web Services API are used by the In-Place eDiscovery & Holds feature in the Exchange admin center and the corresponding **\*-MailboxSearch** cmdlets in Exchange Online PowerShell.</span></span> <span data-ttu-id="bb83d-304">また、他の従来の電子情報開示ツールの廃止の一環として廃止されます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-304">They will also be retired as part of retiring the other legacy eDiscovery tools.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="bb83d-305">影響を受ける組織の範囲</span><span class="sxs-lookup"><span data-stu-id="bb83d-305">Scope of affected organizations</span></span>

- <span data-ttu-id="bb83d-306">Office 365およびMicrosoft 365 Enterprise組織</span><span class="sxs-lookup"><span data-stu-id="bb83d-306">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="bb83d-307">Office 365およびMicrosoft 365 Education組織</span><span class="sxs-lookup"><span data-stu-id="bb83d-307">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="bb83d-308">Office 365およびMicrosoft 365組織。これには、GCC、GCC、DoD が含まれます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-308">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="bb83d-309">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="bb83d-309">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="bb83d-310">タイムライン</span><span class="sxs-lookup"><span data-stu-id="bb83d-310">Timeline</span></span>

- <span data-ttu-id="bb83d-311">2020 年 7 月 1 日: GetSearchableMailboxes、SearchMailboxes、SetHoldOnMailboxes、および GetHoldOnMailboxes 操作は使用できなくなりました。Microsoft サポートはサポートを提供しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="bb83d-311">July 1, 2020: The GetSearchableMailboxes, SearchMailboxes, SetHoldOnMailboxes, and GetHoldOnMailboxes operations will no longer be available, and Microsoft Support will no longer provide assistance.</span></span>

## <a name="advanced-ediscovery-v10"></a><span data-ttu-id="bb83d-312">Advanced eDiscovery v1.0</span><span class="sxs-lookup"><span data-stu-id="bb83d-312">Advanced eDiscovery v1.0</span></span>

<span data-ttu-id="bb83d-313">Advanced eDiscovery v1.0 は、コアの電子情報開示ケースで使用できる Advanced eDiscovery のバージョンで、[Advanced eDiscovery に切り替える] を **クリック** して使用できません。</span><span class="sxs-lookup"><span data-stu-id="bb83d-313">Advanced eDiscovery v1.0, which is the version of Advanced eDiscovery available in a core eDiscovery case by clicking **Switch to Advanced eDiscovery**, is being retired.</span></span> <span data-ttu-id="bb83d-314">その機能は、コンプライアンス センターの新Advanced eDiscovery[ソリューション](./ediscovery.md)Microsoft 365されました。</span><span class="sxs-lookup"><span data-stu-id="bb83d-314">Its functionality has been replaced by the new [Advanced eDiscovery solution](./ediscovery.md) in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="bb83d-315">組織で v1.0 を使用Advanced eDiscoveryするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bb83d-315">To determine if your organization is using Advanced eDiscovery v1.0:</span></span>

1. <span data-ttu-id="bb83d-316">[Office 365 セキュリティ/コンプライアンス センター](https://protection.office.com)に移動します。</span><span class="sxs-lookup"><span data-stu-id="bb83d-316">Go to the [Office 365 Security & Compliance Center](https://protection.office.com).</span></span>

2. <span data-ttu-id="bb83d-317">セキュリティ コンプライアンス センターの左側のナビゲーション ウィンドウ&、[電子情報開示>] をクリックし、コア電子情報開示ケースを開きます。 </span><span class="sxs-lookup"><span data-stu-id="bb83d-317">In the left navigation pane of the Security & Compliance Center, click **eDiscovery > eDiscovery**, and open a Core eDiscovery case.</span></span>

3. <span data-ttu-id="bb83d-318">[デバイスに切り替Advanced eDiscovery] ボタン **が表示** された場合は、クリックすると 1.0 バージョンの Advanced eDiscovery に移動します。これは廃止されます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-318">If you see the **Switch to Advanced eDiscovery** button, then clicking it will take you to the 1.0 version of Advanced eDiscovery, which is being retired.</span></span> <span data-ttu-id="bb83d-319">Core eDiscovery でケースを作成および管理する機能は影響を受け取らない。</span><span class="sxs-lookup"><span data-stu-id="bb83d-319">The ability to create and manage cases in Core eDiscovery won't be affected.</span></span> <span data-ttu-id="bb83d-320">v1.0 でケース データを追加および分析する機能 (Advanced eDiscovery に切り替 **える)** をクリックAdvanced eDiscovery削除されます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-320">Only the ability to add and analyze case data in Advanced eDiscovery v1.0 (by clicking **Switch to Advanced eDiscovery**) is being retired.</span></span>

<span data-ttu-id="bb83d-321">Microsoft 365 の新しい Advanced eDiscovery ソリューション *(Advanced eDiscovery v2.0* とも呼ばれる) は、元のソリューションのすべての機能を提供しますが、他の Microsoft 365 サービスのコンテンツを識別し、そのコンテンツを収集し、レビュー担当者が迅速な検索クエリ、タグ付け、分析機能を活用して関連ドキュメントを作成できるレビュー セットに追加するカストディアンベースのアプローチが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bb83d-321">The new Advanced eDiscovery solution in Microsoft 365 (also known as *Advanced eDiscovery v2.0*) provides all of the capabilities of the original solution, but now includes a custodian-based approach of identifying content in other Microsoft 365 services, collecting that content, and then adding it to a review set where reviewers can take advantage of fast search queries, tagging, and analytics features to help cull relevant documents.</span></span> <span data-ttu-id="bb83d-322">Advanced eDiscovery、Microsoft と Microsoft 以外のファイルの種類の両方の処理とネイティブ ビューアーが追加されました。ファイルの種類の完全な一覧は[次](./supported-filetypes-ediscovery20.md)のとおりです。サポートされているメタデータ フィールドは次[のとおりです](./document-metadata-fields-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="bb83d-322">Advanced eDiscovery now includes improved processing and native viewers for both Microsoft and non-Microsoft file types, a full list of file types is [here](./supported-filetypes-ediscovery20.md) and supported metadata fields are [here](./document-metadata-fields-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="bb83d-323">また、新しい Advanced eDiscovery ソリューションでは、強力な保管担当者が管理機能を提供し、さまざまなサービスのコンテンツにホールドを適用し、保留リストのユーザーに通知し、保管担当者の応答を追跡できます(すべて Advanced eDiscovery ケース内)。</span><span class="sxs-lookup"><span data-stu-id="bb83d-323">Also, the new Advanced eDiscovery solution provides a powerful custodian holds management feature that lets you apply holds to content in different services, notify users of the holds, and track custodian responses, all within an Advanced eDiscovery case.</span></span>

<span data-ttu-id="bb83d-324">Advanced eDiscovery v2.0 へのアクセス</span><span class="sxs-lookup"><span data-stu-id="bb83d-324">To access Advanced eDiscovery v2.0:</span></span>

1. <span data-ttu-id="bb83d-325">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com) にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="bb83d-325">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="bb83d-326">Microsoft 365 コンプライアンス センターの左側のナビゲーション ウィンドウで、[**すべてを表示**] をクリックし、**[eDiscovery] > [Advanced]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb83d-326">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Advanced**.</span></span>

<span data-ttu-id="bb83d-327">この時点で、電子情報開示ワークフローを新しい電子情報開示機能に移行Advanced eDiscovery勧めします。</span><span class="sxs-lookup"><span data-stu-id="bb83d-327">At this time, we recommend that you begin to transition your eDiscovery workflow to the new Advanced eDiscovery functionality.</span></span> <span data-ttu-id="bb83d-328">必要に応じて、コンテンツをエクスポートAdvanced eDiscoveryオフラインで保存することで、1.0 ケースをアーカイブできます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-328">If required, you can archive your Advanced eDiscovery 1.0 cases by exporting the content and storing it offline.</span></span> <span data-ttu-id="bb83d-329">2020 年 12 月 31 日まで、既存のケースでは引き続き Advanced eDiscovery v1.0 にアクセスすることができますが、Microsoft サポートは 2020 年 10 月 1 日以降はサポートを提供しない予定です。</span><span class="sxs-lookup"><span data-stu-id="bb83d-329">Although you'll still be able to access Advanced eDiscovery v1.0 in existing cases until December 31, 2020, Microsoft Support won't provide support after October 1, 2020.</span></span> <span data-ttu-id="bb83d-330">詳細については、次のタイムラインを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb83d-330">See the following timeline for more details.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="bb83d-331">影響を受ける組織の範囲</span><span class="sxs-lookup"><span data-stu-id="bb83d-331">Scope of affected organizations</span></span>

- <span data-ttu-id="bb83d-332">Office 365およびMicrosoft 365 Enterprise組織</span><span class="sxs-lookup"><span data-stu-id="bb83d-332">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="bb83d-333">Office 365およびMicrosoft 365 Education組織</span><span class="sxs-lookup"><span data-stu-id="bb83d-333">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="bb83d-334">Office 365およびMicrosoft 365組織。これには、GCC、GCC、DoD が含まれます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-334">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="bb83d-335">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="bb83d-335">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="bb83d-336">タイムライン</span><span class="sxs-lookup"><span data-stu-id="bb83d-336">Timeline</span></span>

- <span data-ttu-id="bb83d-337">2020 年 7 月 1 日: v1.0 の新しいAdvanced eDiscovery作成できない。</span><span class="sxs-lookup"><span data-stu-id="bb83d-337">July 1, 2020: You won't be able to create new Advanced eDiscovery v1.0  cases.</span></span>

- <span data-ttu-id="bb83d-338">2020 年 10 月 1 日: 新しいデータを追加できない (Advanced eDiscovery の検索結果を準備する) 場合。</span><span class="sxs-lookup"><span data-stu-id="bb83d-338">October 1, 2020: You won't be able to add new data (Prepare search results for Advanced eDiscovery) to any cases.</span></span> <span data-ttu-id="bb83d-339">既存のケースのデータを自分のリスクで引き続き操作できます。</span><span class="sxs-lookup"><span data-stu-id="bb83d-339">You'll be able to continue working with data in existing cases at your own risk.</span></span> <span data-ttu-id="bb83d-340">Microsoft サポートはサポートを提供しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="bb83d-340">Microsoft Support will no longer provide assistance.</span></span> 

- <span data-ttu-id="bb83d-341">2020 年 12 月 31 日: v1.0 のケースAdvanced eDiscoveryアクセスできない。</span><span class="sxs-lookup"><span data-stu-id="bb83d-341">December 31, 2020: You won't be able to access Advanced eDiscovery v1.0 cases.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="bb83d-342">代替ツール</span><span class="sxs-lookup"><span data-stu-id="bb83d-342">Alternative tools</span></span>

<span data-ttu-id="bb83d-343">コンプライアンス[Advanced eDiscoveryセンター](./overview-ediscovery-20.md)のMicrosoft 365ソリューション。</span><span class="sxs-lookup"><span data-stu-id="bb83d-343">The [Advanced eDiscovery solution](./overview-ediscovery-20.md) in the Microsoft 365 compliance center.</span></span>