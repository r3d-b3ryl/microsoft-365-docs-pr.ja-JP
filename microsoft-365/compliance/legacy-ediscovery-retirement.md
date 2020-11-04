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
description: Exchange Online の電子情報開示と In-Place ホールド (および対応する PowerShell コマンドレット) は、2020の前半で廃止されます。 In-Place。 Search-Mailbox コマンドレットと Advanced eDiscovery v 1.0 も、同じ期間内に廃止されます。
ms.openlocfilehash: e8edda9436d62e07d0f64126a012791080766aba
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877468"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a><span data-ttu-id="ae71e-104">従来の電子情報開示ツールの廃止</span><span class="sxs-lookup"><span data-stu-id="ae71e-104">Retirement of legacy eDiscovery tools</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ae71e-105">Microsoft は、衛生衛生状況を評価しており、お客様に対する影響について理解しています。</span><span class="sxs-lookup"><span data-stu-id="ae71e-105">Microsoft has been evaluating the public health situation, and we understand the impact this is having on our customers.</span></span> <span data-ttu-id="ae71e-106">Sdl は、強力なパートナーと責任を持つグローバル市民を求めています。</span><span class="sxs-lookup"><span data-stu-id="ae71e-106">We want to be strong partners and responsible global citizens.</span></span> <span data-ttu-id="ae71e-107">お客様が直面している多くの状況の1つを簡単にするために、この記事で説明した従来の電子情報開示ツールを3か月で延期する予定です。</span><span class="sxs-lookup"><span data-stu-id="ae71e-107">To ease one of the many burdens you are facing, we are going to delay the scheduled retirement for the legacy eDiscovery tools described in this article by three months.</span></span> <span data-ttu-id="ae71e-108">**更新された退職日は次のように反映されます。**</span><span class="sxs-lookup"><span data-stu-id="ae71e-108">**The updated retirement dates are reflected below.**</span></span>

<span data-ttu-id="ae71e-109">長年、Microsoft では、Exchange Online からの電子メールコンテンツの検索、プレビュー、およびエクスポートを可能にする電子情報開示ツールを提供しています。</span><span class="sxs-lookup"><span data-stu-id="ae71e-109">Over the years, Microsoft has provided eDiscovery tools that let you search, preview, and export email content from Exchange Online.</span></span> <span data-ttu-id="ae71e-110">ただし、これらのツールでは、SharePoint Online や Microsoft 365 グループなど、他の Microsoft 365 services の Exchange 以外のコンテンツを効率的に検索する方法は提供されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="ae71e-110">However, these tools no longer offer an effective way to search for non-Exchange content in other Microsoft 365 services, such as SharePoint Online and Microsoft 365 Groups.</span></span> <span data-ttu-id="ae71e-111">このことを説明するために、Microsoft は、さまざまな Microsoft 365 コンテンツを検索するのに役立つその他の電子情報開示ツールを提供しています。</span><span class="sxs-lookup"><span data-stu-id="ae71e-111">To address this, Microsoft offers other eDiscovery tools that help you search for a wide variety of Microsoft 365 content.</span></span> <span data-ttu-id="ae71e-112">また、マイクロソフトは、 [Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com)で最新の強力な電子情報開示機能を組み込むために努力してきました。</span><span class="sxs-lookup"><span data-stu-id="ae71e-112">And we've been working hard to incorporate the most current and powerful eDiscovery functionality in the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span> <span data-ttu-id="ae71e-113">これにより、組織は、Exchange Online などの多くの Microsoft 365 サービスにわたって、法的、社内、およびその他のコンテンツに関するドキュメント要求に対応することができます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-113">This allows organizations to respond to legal, internal, and other document requests for content across many Microsoft 365 services, including Exchange Online.</span></span>

<span data-ttu-id="ae71e-114">この新しい電子情報開示機能の結果として、Microsoft 365 コンプライアンスセンターでは、Exchange Online および Microsoft 365 での電子メールコンテンツの検索に関連する以下の電子情報開示関連の機能を廃止しています。</span><span class="sxs-lookup"><span data-stu-id="ae71e-114">As a result of this new and improved eDiscovery functionality in the Microsoft 365 compliance center, we're retiring the following eDiscovery-related features and functionality related to searching for email content in Exchange Online and Microsoft 365:</span></span>

- <span data-ttu-id="ae71e-115">Exchange 管理センターの[インプレース電子情報開示](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)および[インプレース ホールド](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds)。</span><span class="sxs-lookup"><span data-stu-id="ae71e-115">[In-Place eDiscovery](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) and [In-Place Holds](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds) in the Exchange admin center.</span></span>

- <span data-ttu-id="ae71e-116">電子情報開示と In-Place の保持 In-Place をサポートする Exchange Online の PowerShell コマンドレット (これらのコマンドレットは、 *get-mailboxsearch* コマンドレットと総称して識別されます)。</span><span class="sxs-lookup"><span data-stu-id="ae71e-116">The Exchange Online PowerShell cmdlets that support In-Place eDiscovery and In-Place Holds (these cmdlets are collectively identified as \* *-MailboxSearch* cmdlets).</span></span> <span data-ttu-id="ae71e-117">これには、次のコマンドレットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-117">This includes the following cmdlets:</span></span>

  - [<span data-ttu-id="ae71e-118">New-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="ae71e-118">New-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-mailboxsearch)

  - [<span data-ttu-id="ae71e-119">Start-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="ae71e-119">Start-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/start-mailboxsearch)

  - [<span data-ttu-id="ae71e-120">Stop-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="ae71e-120">Stop-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/stop-mailboxsearch)

  - [<span data-ttu-id="ae71e-121">Set-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="ae71e-121">Set-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-mailboxsearch)

   > [!NOTE]
   > <span data-ttu-id="ae71e-122">[Get-mailboxsearch](https://docs.microsoft.com/powershell/module/exchange/get-mailboxsearch)および[get-mailboxsearch](https://docs.microsoft.com/powershell/module/exchange/remove-mailboxsearch)コマンドレットは、他の \* \* \* \* \* \* \* \* \* _ コマンドレットを破棄した後で使用できるようになります。これを使用して、他の電子情報開示および保持ツールへの移行に役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-122">The [Get-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/get-mailboxsearch) and [Remove-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/remove-mailboxsearch) cmdlets will be available after the other \*\*\*\*-MailboxSearch\*\*_ cmdlets are retired so that you can use them to help in your transition to other eDiscovery and hold tools.</span></span> <span data-ttu-id="ae71e-123">ただし、特定の日付 (後述) の Microsoft サポートは、これら2つのコマンドレットをサポートしなくなります。</span><span class="sxs-lookup"><span data-stu-id="ae71e-123">However, after a certain date (cited below) Microsoft Support will no longer supports these two cmdlets.</span></span>

- <span data-ttu-id="ae71e-124">Exchange Online PowerShell の [Search-Mailbox](https://docs.microsoft.com/powershell/module/exchange/search-mailbox) コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="ae71e-124">The [Search-Mailbox](https://docs.microsoft.com/powershell/module/exchange/search-mailbox) cmdlet in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="ae71e-125">Exchange Web Services API での次の操作。</span><span class="sxs-lookup"><span data-stu-id="ae71e-125">The following operations in the Exchange Web Services API:</span></span>

   - [<span data-ttu-id="ae71e-126">GetSearchableMailboxes</span><span class="sxs-lookup"><span data-stu-id="ae71e-126">GetSearchableMailboxes</span></span>](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [<span data-ttu-id="ae71e-127">SearchMailboxes</span><span class="sxs-lookup"><span data-stu-id="ae71e-127">SearchMailboxes</span></span>](https://docs.microsoft.com/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [<span data-ttu-id="ae71e-128">SetHoldOnMailboxes</span><span class="sxs-lookup"><span data-stu-id="ae71e-128">SetHoldOnMailboxes</span></span>](https://docs.microsoft.com/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [<span data-ttu-id="ae71e-129">GetHoldOnMailboxes</span><span class="sxs-lookup"><span data-stu-id="ae71e-129">GetHoldOnMailboxes</span></span>](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- <span data-ttu-id="ae71e-130">Office [365 Advanced ediscovery v 1.0](office-365-advanced-ediscovery.md)。これは、Office 365 セキュリティ & コンプライアンスセンターの主要な電子情報開示ケースによってアクセスされる、高度な電子情報開示の最初のバージョンです。</span><span class="sxs-lookup"><span data-stu-id="ae71e-130">[Office 365 Advanced eDiscovery v1.0](office-365-advanced-ediscovery.md), which is the first version of Advanced eDiscovery that's accessed through a Core eDiscovery case in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="ae71e-131">高度な電子情報開示 v2.0 の廃止は、コア電子情報開示ケースの作成と管理の能力に影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="ae71e-131">The retirement of Advanced eDiscovery v1.0 doesn't impact your ability to create and manage Core eDiscovery cases.</span></span>

> [!NOTE]
> <span data-ttu-id="ae71e-132">廃止される電子情報開示の機能は、クラウドベースのバージョンの Microsoft 365 および Office 365 にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-132">The eDiscovery functionality being retired only applies to cloud-based versions of Microsoft 365 and Office 365.</span></span> <span data-ttu-id="ae71e-133">オンプレミスバージョンの Exchange と SharePoint の電子情報開示機能は、今後の通知まで引き続きサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-133">eDiscovery functionality in on-premises versions of Exchange and SharePoint will still be supported until further notice.</span></span>

<span data-ttu-id="ae71e-134">この記事の以下のセクションでは、廃止される各機能についてのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="ae71e-134">The following sections in this article provide guidance about each feature being retired.</span></span> <span data-ttu-id="ae71e-135">この情報は、廃止ツールの代わりに使用できるタイムラインおよび代替ツールを含みます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-135">This information including timelines and alternative tools that you can use instead of the retired tool.</span></span>

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a><span data-ttu-id="ae71e-136">Exchange 管理センターでの電子情報開示と In-Place の保持の In-Place</span><span class="sxs-lookup"><span data-stu-id="ae71e-136">In-Place eDiscovery and In-Place Holds in the Exchange admin center</span></span> 

<span data-ttu-id="ae71e-137">2017年7月1日の元のアナウンスによると、Exchange 管理センター (EAC) の In-Place 電子情報開示 & 保持機能は廃止されています。</span><span class="sxs-lookup"><span data-stu-id="ae71e-137">As per the original announcement on July 1, 2017, the In-Place eDiscovery & Hold functionality in the Exchange admin center (EAC) is being retired.</span></span> <span data-ttu-id="ae71e-138">EAC の電子情報開示 & In-Place は、Exchange Online からコンテンツを検索、保持、およびエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-138">The In-Place eDiscovery & Holds page in the EAC allowed you to search, hold, and export content from Exchange Online.</span></span> <span data-ttu-id="ae71e-139">また、電子情報開示マネージャーは、検索結果を証拠開示用メールボックスにコピーして、自分または他の電子情報開示マネージャーがコンテンツをレビューし、法的、規制、およびパブリック要求に対して使用できるようにすることも In-Place ます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-139">In-Place eDiscovery also let you copy search results to a discovery mailbox so that you or other eDiscovery managers could review content and make it available for legal, regulatory, and public requests.</span></span>

<span data-ttu-id="ae71e-140">これらのすべての機能 (検索結果を証拠開示用メールボックスにコピーする場合を除く) は、 [microsoft 365 コンプライアンスセンター](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) のコンテンツ検索、電子情報開示、および高度な電子情報開示ツールで利用できるようになりました (強化された機能、信頼性、および幅広い microsoft 365 サービスのサポート)。</span><span class="sxs-lookup"><span data-stu-id="ae71e-140">Because all of these capabilities (except for copying search results to a discovery mailbox) are now available in the content search, eDiscovery and Advanced eDiscovery tools in the [Microsoft 365 compliance center](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) (with improved functionality, reliability, and support for a wide range of Microsoft 365 services), we recommend that you start using these tools as soon as possible.</span></span> <span data-ttu-id="ae71e-141">他の電子情報開示ツールへの移行を支援するために、次の表に、In-Place eDiscovery および In-Place ホールドではなく使用できるツールを示します。</span><span class="sxs-lookup"><span data-stu-id="ae71e-141">To help you in the transition to these other eDiscovery tools, the table below lists the tools you can use instead of In-Place eDiscovery and In-Place Hold.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="ae71e-142">影響を受ける組織の範囲</span><span class="sxs-lookup"><span data-stu-id="ae71e-142">Scope of affected organizations</span></span>

- <span data-ttu-id="ae71e-143">Office 365 と Microsoft 365 エンタープライズ組織</span><span class="sxs-lookup"><span data-stu-id="ae71e-143">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="ae71e-144">Office 365 および Microsoft 365 エデュケーション組織</span><span class="sxs-lookup"><span data-stu-id="ae71e-144">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="ae71e-145">Office 365 および Microsoft 365 Government 組織。これには GCC、GCC High、DoD が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-145">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="ae71e-146">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="ae71e-146">Office 365 Germany</span></span>

### <a name="timeline-for-retirement"></a><span data-ttu-id="ae71e-147">定年後のタイムライン</span><span class="sxs-lookup"><span data-stu-id="ae71e-147">Timeline for retirement</span></span>

- <span data-ttu-id="ae71e-148">2020年7月1日: 新しい検索と保持を作成することはできませんが、既存の検索の実行、編集、および削除は、自分の責任で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-148">July 1, 2020: You won't be able to create new searches and holds, but you can still run, edit, and delete existing searches at your own risk.</span></span> <span data-ttu-id="ae71e-149">Microsoft サポートは、EAC での電子情報開示 & の保持 In-Place しなくなります。</span><span class="sxs-lookup"><span data-stu-id="ae71e-149">Microsoft Support will no longer In-Place eDiscovery & Holds in the EAC.</span></span>

- <span data-ttu-id="ae71e-150">2020年10月1日: In-Place 電子情報開示 & は、EAC の機能を読み取り専用モードで保持します。</span><span class="sxs-lookup"><span data-stu-id="ae71e-150">October 1, 2020: The In-Place eDiscovery & Holds functionality in the EAC will be placed in a read-only mode.</span></span> <span data-ttu-id="ae71e-151">これにより、可能な操作は、既存の検索および保留リストの削除のみになります。</span><span class="sxs-lookup"><span data-stu-id="ae71e-151">This means you'll only be able to remove existing searches and holds.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="ae71e-152">代替ツール</span><span class="sxs-lookup"><span data-stu-id="ae71e-152">Alternative tools</span></span>

<span data-ttu-id="ae71e-153">次の表では、廃止される既存の機能を置き換えるために使用できるその他のツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ae71e-153">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="ae71e-154">機能</span><span class="sxs-lookup"><span data-stu-id="ae71e-154">Functionality</span></span></th>
<th><span data-ttu-id="ae71e-155">代替ツール</span><span class="sxs-lookup"><span data-stu-id="ae71e-155">Alternative tool</span></span></th>
<th><span data-ttu-id="ae71e-156">コメント</span><span class="sxs-lookup"><span data-stu-id="ae71e-156">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="ae71e-157">法的な目的のための検索、エクスポート、保持</span><span class="sxs-lookup"><span data-stu-id="ae71e-157">Search, export, and hold for legal purposes</span></span></td>
<td><span data-ttu-id="ae71e-158">Microsoft 365 コンプライアンスセンターのコア電子情報開示ケース</span><span class="sxs-lookup"><span data-stu-id="ae71e-158">Core eDiscovery cases in the Microsoft 365 compliance center</span></span> </td>
<td><p><span data-ttu-id="ae71e-159">コア電子情報開示ケースの機能を使用すると、In-Place 電子情報開示と In-Place 保持に機能するパリティが提供されます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-159">Using the capabilities of core eDiscovery cases provide the functional parity to In-Place eDiscovery and In-Place Holds.</span></span> <span data-ttu-id="ae71e-160">エクスポートできるものには、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="ae71e-160">This includes the following:</span></span></p>
<ul>
<li>
<p><span data-ttu-id="ae71e-161">数百万の場所への検索を拡大/縮小</span><span class="sxs-lookup"><span data-stu-id="ae71e-161">Search scales to millions of locations</span></span></p>
</li>
<li>
<p><span data-ttu-id="ae71e-162">コンテンツの検索、エクスポート、および配置の信頼性が向上します。</span><span class="sxs-lookup"><span data-stu-id="ae71e-162">Higher reliability for searching, exporting, and placing content on hold</span></span></p>
</li>
<li>
<p><span data-ttu-id="ae71e-163">Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft Teams、Yammer グループ、Microsoft 365 グループ、Office 365 アプリケーションに格納されているその他のコンテンツのコンテンツを検索する</span><span class="sxs-lookup"><span data-stu-id="ae71e-163">Searching for content in for Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams, Yammer Groups, Microsoft 365 Groups, and other content stored in Office 365 applications</span></span></p></li></ul>
<p><span data-ttu-id="ae71e-164">詳細については、「 <a href="https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations"> Office 365 で法的調査を管理</a>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae71e-164">For more information, see <a href="https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations"> Manage legal investigations in Office 365</a>.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ae71e-165">保持の目的で保持</span><span class="sxs-lookup"><span data-stu-id="ae71e-165">Hold for retention purposes</span></span></td>
<td><span data-ttu-id="ae71e-166">Microsoft 365 コンプライアンスセンターのアイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="ae71e-166">Retention policies in the Microsoft 365 compliance center</span></span></td>
<td><p><span data-ttu-id="ae71e-167">保持ポリシーを使用してコンテンツを保持できます。必要に応じて、保存期間の期限が切れた後にアイテムを削除します。</span><span class="sxs-lookup"><span data-stu-id="ae71e-167">You can use Retention policies to retain content and, if desired, delete it after the retention period expires.</span></span> <span data-ttu-id="ae71e-168">その他の機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ae71e-168">Other capabilities include:</span></span></p>
<ul>
<li>
<p><span data-ttu-id="ae71e-169">組織全体へのポリシーの適用</span><span class="sxs-lookup"><span data-stu-id="ae71e-169">Applying policies to your entire organization</span></span> </p>
</li><li>
<p><span data-ttu-id="ae71e-170">Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft Teams、Office 365 グループなどの特定のコンテンツの場所へのポリシーの適用</span><span class="sxs-lookup"><span data-stu-id="ae71e-170">Applying policies to specific content locations such as Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams, and Office 365 Groups</span></span></p></li>
<li>
<p><span data-ttu-id="ae71e-171">特定のユーザーへのポリシーの適用</span><span class="sxs-lookup"><span data-stu-id="ae71e-171">Applying policies to specific users</span></span></p></li></ul>
<p><span data-ttu-id="ae71e-172">詳細については、「 <a href="https://docs.microsoft.com/microsoft-365/compliance/retention-policies"> アイテム保持ポリシーと保持ラベルについて</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae71e-172">For more information, see <a href="https://docs.microsoft.com/microsoft-365/compliance/retention-policies"> Learn about retention policies and retention labels</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ae71e-173">レビューのために電子メール検索結果を証拠開示用メールボックスにコピーする</span><span class="sxs-lookup"><span data-stu-id="ae71e-173">Copy email search results to a discovery mailbox for review</span></span></td><td><span data-ttu-id="ae71e-174">上級電子情報開示の設定を確認する v2.0 v 2.0</span><span class="sxs-lookup"><span data-stu-id="ae71e-174">Review sets in Advanced eDiscovery v2.0</span></span></td>
<td><p><span data-ttu-id="ae71e-175">Microsoft 365 のコンテンツを確認するのは、これよりも簡単ではありません。</span><span class="sxs-lookup"><span data-stu-id="ae71e-175">Reviewing content in Microsoft 365 has never been easier.</span></span> <span data-ttu-id="ae71e-176">レビューセットには、次のような時間とデータを減らすために役立つさまざまな機能があります。</span><span class="sxs-lookup"><span data-stu-id="ae71e-176">Review sets have many great capabilities to help reduce the amount of time and data needed to review, including:</span></span></p>
<ul>
<li><p><span data-ttu-id="ae71e-177">クイック検索クエリを実行して、レビューセット内のコンテンツをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="ae71e-177">Perform fast search queries and filter content in a review set</span></span></p></li>
<li><p><span data-ttu-id="ae71e-178">レビューセットのコンテンツを分析する。これには、電子メールスレッド処理、ほぼ重複した検出、テーマの分析、および予測コーディングが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-178">Analyze content in a review set; this includes email threading, near-duplicate detection, Themes analysis, and Predictive coding</span></span></p></li>
<li><p><span data-ttu-id="ae71e-179">レビュー セット内のドキュメントをタグ付けする</span><span class="sxs-lookup"><span data-stu-id="ae71e-179">Tag documents in a review set</span></span></p></li>
<li><p><span data-ttu-id="ae71e-180">弁護士クライアント権限の内容を識別するのに役立つ提案のタグ付け</span><span class="sxs-lookup"><span data-stu-id="ae71e-180">Tagging suggestions to help identify attorney  client privilege content</span></span></p></li></ul>
<p><span data-ttu-id="ae71e-181">詳細については、「<a href="https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20">Microsoft 365 の Advanced eDiscovery ソリューションの概要</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae71e-181">For more information, see <a href="https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20">Overview of the Advanced eDiscovery solution in Microsoft 365</a>.</span></span></p>
<p>
<p><span data-ttu-id="ae71e-182">または、検索結果を PST ファイルにエクスポートし、Microsoft 365 インポートサービスを使用して Pst を探索メールボックスにインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-182">Alternatively, you can export search results to PST files and then use Microsoft 365 Import service to import the PSTs to a discovery mailbox.</span></span> <span data-ttu-id="ae71e-183">詳細な手順については、「 <a href="https://docs.microsoft.com/microsoft-365/compliance/use-network-upload-to-import-pst-files">ネットワークアップロードを使用して PST ファイルを Office 365 にインポートする</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae71e-183">For step-by-step instruction, see <a href="https://docs.microsoft.com/microsoft-365/compliance/use-network-upload-to-import-pst-files">Use network upload to import PST files to Office 365</a>.</span></span>
</tr>
<tr class=even>
  <td><span data-ttu-id="ae71e-184">あるメールボックスから別のメールボックスにメッセージをコピーする</span><span class="sxs-lookup"><span data-stu-id="ae71e-184">Copy messages from one mailbox to a different mailbox</span></span></td>
  <td><span data-ttu-id="ae71e-185"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">メールボックスへのアクセス許可の割り当て</a></span><span class="sxs-lookup"><span data-stu-id="ae71e-185"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
  <td><span data-ttu-id="ae71e-186">他のユーザーの電子メールにアクセスできるようにする (従業員が組織を離れたときに、別のユーザーに元従業員の電子メールへのアクセス権を付与する必要がある場合など) には、元従業員のメールボックスにアクセスするためのアクセス許可を割り当てることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ae71e-186">To give a person access to another user's email (such as when an employee leaves your organization and you need to give another person access to the former employee's email), we recommended that you assign that person permissions to access the former employee's mailbox.</span></span> <span data-ttu-id="ae71e-187">そのため、メールボックスアイテムを別のユーザーのメールボックスまたは共有メールボックスにコピーするのではなく、移動元のメールボックスにアクセスするためのユーザー権限のみを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-187">So instead of copying mailbox items to another user mailbox or a shared mailbox, just assign a user permissions to access the source mailbox.</span></span></td>
  
  </tr>
<tr class="odd">
<td><span data-ttu-id="ae71e-188">回復可能なアイテムフォルダーからアイテムを復元する</span><span class="sxs-lookup"><span data-stu-id="ae71e-188">Restore items from the Recoverable Items folder</span></span></td>
  <td><span data-ttu-id="ae71e-189"><a href="https://docs.microsoft.com/powershell/module/exchange/Restore-RecoverableItems">復元-回復した Ableitems</span><span class="sxs-lookup"><span data-stu-id="ae71e-189"><a href="https://docs.microsoft.com/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</span></span></td>
  <td><span data-ttu-id="ae71e-190">アイテムの削除済みアイテムの保存期間が期限切れになっていない限り、メールボックス内の完全に削除されたアイテム ( <i>回復可能な</i> アイテムとも呼ばれる) を復元することができます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-190">You can restore permanently deleted items (also known as <i>soft-deleted</i> items) in mailboxes, as long as the deleted item retention period for an item hasn't expired.</span></span> <span data-ttu-id="ae71e-191">詳細については、「 <a href="https://docs.microsoft.com/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Exchange Online の回復可能なアイテムフォルダー</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae71e-191">For more information, see <a href="https://docs.microsoft.com/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Recoverable Items folder in Exchange Online</a>.</span></span></td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a><span data-ttu-id="ae71e-192">インプレース電子情報開示とインプレース ホールドに関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="ae71e-192">FAQs about In-Place eDiscovery and In-Place Holds</span></span>

<span data-ttu-id="ae71e-193">*EAC の電子情報開示 & ホールド In-Place のコピー検索結果機能を使用して、で検索結果を証拠開示用メールボックスにコピーし、弁護士による確認を行います。現在、どのようなオプションがありますか?*\*</span><span class="sxs-lookup"><span data-stu-id="ae71e-193">_ *I use the copy search results functionality of In-Place eDiscovery & Holds in the EAC to copy search results to a discovery mailbox for review by attorneys. What options do I have now?*\*</span></span>

<span data-ttu-id="ae71e-194">現在、この機能をレプリケートする方法は2つあります。</span><span class="sxs-lookup"><span data-stu-id="ae71e-194">There are two ways to replicate this functionality today.</span></span> <span data-ttu-id="ae71e-195">最初に、 [Advanced eDiscovery v2.0 のレビューセット](https://docs.microsoft.com/microsoft-365/compliance/view-documents-in-review-set)を使用します。</span><span class="sxs-lookup"><span data-stu-id="ae71e-195">The first is to use [review sets in Advanced eDiscovery v2.0](https://docs.microsoft.com/microsoft-365/compliance/view-documents-in-review-set).</span></span> <span data-ttu-id="ae71e-196">レビューセットには、ドキュメントの高速検索、タグ付け、電子メールのスレッド処理、グループの複製、テーマの分析、予測コーディングなど、従来のレビューツールで提供されている機能の多くがあります。</span><span class="sxs-lookup"><span data-stu-id="ae71e-196">Review sets have many of the same capabilities you see in a traditional review tool like fast search of documents, tagging, email threading, near duplicate grouping, themes analysis, and predictive coding.</span></span> <span data-ttu-id="ae71e-197">引き続き証拠開示用メールボックスをレビュー用に使用する場合、2番目のオプションは、Microsoft コンプライアンスセンターの [pst インポート機能](use-network-upload-to-import-pst-files.md) を使用して、検索結果を pst ファイルにエクスポートし、その pst ファイルを探索メールボックスにインポートすることです。</span><span class="sxs-lookup"><span data-stu-id="ae71e-197">If you still want to use discovery mailboxes for review, the second option is to export search results to PST files and then import the PST files to a discovery mailbox by using the [PST import feature](use-network-upload-to-import-pst-files.md) in the Microsoft compliance center.</span></span>

<span data-ttu-id="ae71e-198">**電子情報開示マネージャーが新しいツールを使用して検索できるコンテンツの場所 (メールボックスやサイトなど) を制御するにはどうすればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="ae71e-198">**How do I control which content locations (such as mailboxes or sites) that can an eDiscovery manager can search using the new tools?**</span></span>

<span data-ttu-id="ae71e-199">また、Microsoft 365 コンプライアンスセンターは、 [コンプライアンスの境界](set-up-compliance-boundaries.md) を使用して、電子情報開示マネージャーが検索できるコンテンツの場所を制御します。</span><span class="sxs-lookup"><span data-stu-id="ae71e-199">The Microsoft 365 compliance center also uses [compliance boundaries](set-up-compliance-boundaries.md) to control which content locations an eDiscovery Manager can search.</span></span> <span data-ttu-id="ae71e-200">コンプライアンスの境界は、地域の boarders を尊重するために必要とされる政府機関または多国籍企業内にとどまる必要がある政府機関にとって便利です。</span><span class="sxs-lookup"><span data-stu-id="ae71e-200">Compliance boundaries are useful in government entities that need to stay within agency boundaries or multi-national corporations required to respect geographical boarders.</span></span>

<span data-ttu-id="ae71e-201">**現在の検索と保持を Microsoft 365 コンプライアンスセンターに移動するにはどうすればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="ae71e-201">**How can I move my current searches and holds to the Microsoft 365 compliance center?**</span></span>

<span data-ttu-id="ae71e-202">PowerShell を使用して EAC から電子情報開示の検索と保持を移行 In-Place ことができます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-202">It's possible to migrate In-Place eDiscovery searches and holds from the EAC by using PowerShell.</span></span> <span data-ttu-id="ae71e-203">手順については、「 [Migrate 検索と保持を EAC から Microsoft 365 コンプライアンスセンターに移行する」を](https://go.microsoft.com/fwlink/?linkid=2114224)参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae71e-203">For instructions, see [Migrate searches and holds from the EAC to the Microsoft 365 compliance center](https://go.microsoft.com/fwlink/?linkid=2114224).</span></span>

## <a name="-mailboxsearch-cmdlets"></a><span data-ttu-id="ae71e-204">\*-Get-mailboxsearch コマンドレット</span><span class="sxs-lookup"><span data-stu-id="ae71e-204">\*-MailboxSearch cmdlets</span></span>

<span data-ttu-id="ae71e-205">Exchange 管理センターで2017年7月1日に発表された元の通知のように、In-Place 電子情報開示 & は機能を保持し、対応する **\* -get-mailboxsearch** コマンドレットは廃止されます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-205">As per the original notice announced on July 1, 2017 in the Exchange admin center, the In-Place eDiscovery & Hold functionality and the corresponding **\*-MailboxSearch** cmdlets are being retired.</span></span> <span data-ttu-id="ae71e-206">これらのコマンドレットを使用すると、ユーザーは法律、規制、およびパブリックの要求について、メールボックスのコンテンツを検索、保持、エクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-206">These cmdlets provide users the ability to search, hold, and export mailbox content for legal, regulatory, and public requests.</span></span>

<span data-ttu-id="ae71e-207">これらの機能は、パフォーマンスとスケーラビリティが向上した [<span class="underline">Microsoft 365 コンプライアンスセンター</span>](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) および Office 365 Security & コンプライアンスセンターの PowerShell で利用できるようになったため、これらの強化されたコマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae71e-207">Because these capabilities are now available in the [<span class="underline">Microsoft 365 compliance center</span>](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) and Office 365 Security & Compliance Center PowerShell with improved performance and scalability, you should using these improved cmdlets.</span></span> <span data-ttu-id="ae71e-208">これらのコマンドレットには、 [<span class="underline"> \* -get-compliancecase</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)、 [<span class="underline"> \* -new-compliancesearch</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)、 [<span class="underline"> \* -CaseHoldPolicy</span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)、 [<span class="underline"> \* -new-caseholdrule</span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule)、および[<span class="underline"> \* -new-compliancesearchaction</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)があります。</span><span class="sxs-lookup"><span data-stu-id="ae71e-208">These cmdlets include [<span class="underline">\*-ComplianceCase</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase), [<span class="underline">\*-ComplianceSearch</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch), [<span class="underline">\*-CaseHoldPolicy</span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy), [<span class="underline">\*-CaseHoldRule</span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule), and [<span class="underline">\*-ComplianceSearchAction</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction).</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="ae71e-209">影響を受ける組織の範囲</span><span class="sxs-lookup"><span data-stu-id="ae71e-209">Scope of affected organizations</span></span>

- <span data-ttu-id="ae71e-210">Office 365 と Microsoft 365 エンタープライズ組織</span><span class="sxs-lookup"><span data-stu-id="ae71e-210">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="ae71e-211">Office 365 および Microsoft 365 エデュケーション組織</span><span class="sxs-lookup"><span data-stu-id="ae71e-211">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="ae71e-212">Office 365 および Microsoft 365 Government 組織。これには GCC、GCC High、DoD が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-212">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="ae71e-213">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="ae71e-213">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="ae71e-214">タイムライン</span><span class="sxs-lookup"><span data-stu-id="ae71e-214">Timeline</span></span>

- <span data-ttu-id="ae71e-215">2020年7月1日: **get-mailboxsearch** を使用して新しい In-Place 電子情報開示検索と In-Place 保持を作成することはできませんが、コマンドレットを使用して、既存の検索と保持を自分のリスクで実行、編集、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-215">July 1, 2020: You won't be able to use **New-MailboxSearch** to create new In-Place eDiscovery searches and In-Place Holds, but you can still use cmdlets to run, edit, and delete existing searches and holds at your own risk.</span></span> <span data-ttu-id="ae71e-216">Microsoft サポートでは、これらの種類の検索と保留リストのサポートが提供されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="ae71e-216">Microsoft Support will no longer provide assistance for these types of searches and holds.</span></span>

- <span data-ttu-id="ae71e-217">2020年10月1日: 前述したように In-Place、EAC の電子情報開示 & は、の機能を読み取り専用モードで保持します。</span><span class="sxs-lookup"><span data-stu-id="ae71e-217">October 1, 2020: As previously stated, The In-Place eDiscovery & Holds functionality in the EAC will be placed in a read-only mode.</span></span> <span data-ttu-id="ae71e-218">これはまた、 **get-mailboxsearch** 、 **get-mailboxsearch** 、または **get-mailboxsearch** コマンドレットを使用できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="ae71e-218">That also means that you won't be able to use the **New-MailboxSearch** , **Start-MailboxSearch** , or **Set-MailboxSearch** cmdlets.</span></span> <span data-ttu-id="ae71e-219">既存の検索と保持を取得して削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="ae71e-219">You'll only be able to get and remove existing searches and holds.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="ae71e-220">代替ツール</span><span class="sxs-lookup"><span data-stu-id="ae71e-220">Alternative tools</span></span>

<span data-ttu-id="ae71e-221">次の表では、廃止される既存の機能を置き換えるために使用できるその他のツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ae71e-221">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="ae71e-222">機能</span><span class="sxs-lookup"><span data-stu-id="ae71e-222">Functionality</span></span></th>
<th><span data-ttu-id="ae71e-223">代替ツール</span><span class="sxs-lookup"><span data-stu-id="ae71e-223">Alternative tools</span></span></th>
<th><span data-ttu-id="ae71e-224">コメント</span><span class="sxs-lookup"><span data-stu-id="ae71e-224">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="ae71e-225">検索とエクスポート</span><span class="sxs-lookup"><span data-stu-id="ae71e-225">Search and export</span></span></td>
<td><p><span data-ttu-id="ae71e-226"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-New-compliancesearch</span></a></span><span class="sxs-lookup"><span data-stu-id="ae71e-226"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="ae71e-227"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-New-compliancesearchaction</span></a></span><span class="sxs-lookup"><span data-stu-id="ae71e-227"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p><span data-ttu-id="ae71e-228"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">\*-Get-compliancecase</span></a></span><span class="sxs-lookup"><span data-stu-id="ae71e-228"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span></span></p>
<p> </p></td>
<td><p><span data-ttu-id="ae71e-229">New-compliancesearch および New-compliancesearchaction コマンドレットは、コンテンツの検索とエクスポートを支援するために連携しています。</span><span class="sxs-lookup"><span data-stu-id="ae71e-229">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and export content.</span></span> <span data-ttu-id="ae71e-230"><strong>新しい検索</strong><strong>を作成</strong>し、 <strong>new-compliancesearch</strong>コマンドレットを使用して検索の推定値を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-230">You can create a new search and view the search estimate by using the <strong>New-</strong>, <strong>Get-</strong>, and <strong>Start-ComplianceSearch</strong> cmdlets.</span></span> <span data-ttu-id="ae71e-231">その後、 <strong>new-compliancesearchaction</strong> コマンドレットを使用して、検索結果をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-231">Then you can use the <strong>New-ComplianceSearchAction</strong> cmdlet to export the search results.</span></span> <span data-ttu-id="ae71e-232">引き続き、Microsoft 365 コンプライアンスセンターのコア電子情報開示ツールを使用して、それらの検索結果をローカルコンピューターにダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae71e-232">You'll still have to use the core eDiscovery tool in the Microsoft 365 compliance center to download those search results to your local computer.</span></span></p>
<p>
<p><span data-ttu-id="ae71e-233"><strong>注:</strong> これらのコマンドレットを使用して、コア電子情報開示ケースに関連付けられていない検索を作成すると、これらの検索は Microsoft 365 コンプライアンスセンターの [ <strong>コンテンツ検索</strong> ] ページに配置されます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-233"><strong>Note:</strong> If you use these cmdlets to create searches that aren't associated with a core eDiscovery case, these searches will be located on the <strong>Content search</strong> page in the Microsoft 365 compliance center.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ae71e-234">メールボックス内のコンテンツを保持する</span><span class="sxs-lookup"><span data-stu-id="ae71e-234">Hold content in a mailbox</span></span></td>
<td><p><span data-ttu-id="ae71e-235"><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy"><span class="underline">\*-CaseHoldPolicy</span></a></span><span class="sxs-lookup"><span data-stu-id="ae71e-235"><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy"><span class="underline">\*-CaseHoldPolicy</span></a></span></span></p>
<p><span data-ttu-id="ae71e-236"><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule"><span class="underline">\*-New-caseholdrule</span></a></span><span class="sxs-lookup"><span data-stu-id="ae71e-236"><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule"><span class="underline">\*-CaseHoldRule</span></a></span></span></p>
<p><span data-ttu-id="ae71e-237"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">\*-Get-compliancecase</span></a></span><span class="sxs-lookup"><span data-stu-id="ae71e-237"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span></span></p>
<p> </p></td>
<td><p><span data-ttu-id="ae71e-238">Microsoft 365 コンプライアンスセンターのホールドは、Get-compliancecase に関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae71e-238">Holds in the Microsoft 365 compliance center must be associated with a ComplianceCase.</span></span> <span data-ttu-id="ae71e-239">最初に、コンプライアンスケースを作成し、CaseHoldPolicy と New-caseholdrule を作成します。</span><span class="sxs-lookup"><span data-stu-id="ae71e-239">First, create the compliance case, and then create a CaseHoldPolicy and a CaseHoldRule.</span></span></p>
<p><span data-ttu-id="ae71e-240"><strong>注:</strong> New-caseholdrule を作成せずに CaseHoldPolicy を作成すると、New-caseholdrule が作成されて CaseHoldPolicy に関連付けられるまで、保留が操作不能になります。</span><span class="sxs-lookup"><span data-stu-id="ae71e-240"><strong>Note:</strong> Creating a CaseHoldPolicy without a creating CaseHoldRule will render the hold inoperable until the CaseHoldRule is created and associated to the CaseHoldPolicy.</span></span> <span data-ttu-id="ae71e-241">詳細については、コマンドレットのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae71e-241">See the cmdlet documentation for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ae71e-242">検索結果を探索メールボックスにコピーする</span><span class="sxs-lookup"><span data-stu-id="ae71e-242">Copy search results to a discovery mailbox</span></span></td>
<td><span data-ttu-id="ae71e-243">なし</span><span class="sxs-lookup"><span data-stu-id="ae71e-243">None</span></span></td>
<td><span data-ttu-id="ae71e-244">この機能は、Microsoft 365 のすべてのサービスへのアクセスを提供しないので、直接交換することはできません。</span><span class="sxs-lookup"><span data-stu-id="ae71e-244">There's no direct replacement for this functionality because it does not provide access to all Microsoft 365 services.</span></span> <span data-ttu-id="ae71e-245">代替ソリューションについては、以下の FAQ を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae71e-245">See the following FAQ below for alternative solutions.</span></span></td>
</tr>
  <tr class=even>
  <td><span data-ttu-id="ae71e-246">あるメールボックスから別のメールボックスにメッセージをコピーする</span><span class="sxs-lookup"><span data-stu-id="ae71e-246">Copy messages from one mailbox to a different mailbox</span></span></td>
  <td><span data-ttu-id="ae71e-247"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">メールボックスへのアクセス許可の割り当て</a></span><span class="sxs-lookup"><span data-stu-id="ae71e-247"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
  <td><span data-ttu-id="ae71e-248">他のユーザーの電子メールにアクセスできるようにする (従業員が組織を離れたときに、別のユーザーに元従業員の電子メールへのアクセス権を付与する必要がある場合など) には、元従業員のメールボックスにアクセスするためのアクセス許可を割り当てることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ae71e-248">To give a person access to another user's email (such as when an employee leaves your organization and you need to give another person access to the former employee's email), we recommended that you assign that person permissions to access the former employee's mailbox.</span></span> <span data-ttu-id="ae71e-249">そのため、メールボックスアイテムを別のユーザーのメールボックスまたは共有メールボックスにコピーするのではなく、移動元のメールボックスにアクセスするためのユーザー権限のみを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-249">So instead of copying mailbox items to another user mailbox or a shared mailbox, just assign a user permissions to access the source mailbox.</span></span></td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a><span data-ttu-id="ae71e-250">Get-mailboxsearch コマンドレットについて **の** faq</span><span class="sxs-lookup"><span data-stu-id="ae71e-250">FAQs about \* **-MailboxSearch** cmdlets</span></span>

<span data-ttu-id="ae71e-251">**コピー検索を使用して、他の電子情報開示や法的調査を目的とした電子メールメッセージまたはインスタントメッセージをエクスポートします。これらのコマンドレットが廃止された後に、他にどのようなオプションがありますか?**</span><span class="sxs-lookup"><span data-stu-id="ae71e-251">**We use Copy Search to export email messages or instant Messages for purposes other eDiscovery and legal investigations. What other options do we have after these cmdlets are retired?**</span></span>

<span data-ttu-id="ae71e-252">[<span class="underline">Microsoft Graph api</span>](https://developer.microsoft.com/en-us/graph)には、 **\* get-mailboxsearch** コマンドレットを使用するよりも復元性と拡張性が高いため、分析用のデータを抽出するためのさまざまな方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="ae71e-252">The [<span class="underline">Microsoft Graph APIs</span>](https://developer.microsoft.com/en-us/graph) provide a number of methods for extracting data for analysis and other purposes that are far more resilient and scalable than the using the **\*-MailboxSearch** cmdlets.</span></span>

<span data-ttu-id="ae71e-253">**Microsoft 365 コンプライアンスセンターに、検索と保持を移行する方法を教えてください。**</span><span class="sxs-lookup"><span data-stu-id="ae71e-253">**How can I migrate my searches and holds to the Microsoft 365 compliance center?**</span></span>

<span data-ttu-id="ae71e-254">PowerShell スクリプトを使用して、Exchange 管理センターから電子情報開示の検索と保持を移行 In-Place ことができます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-254">It's possible to migrate In-Place eDiscovery searches and holds from the Exchange admin center by using a PowerShell script.</span></span> <span data-ttu-id="ae71e-255">詳細については、「 [Microsoft 365 コンプライアンスセンターへの従来の電子情報開示検索と保持の移行](migrate-legacy-eDiscovery-searches-and-holds.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae71e-255">For more information, see [Migrate legacy eDiscovery searches and holds to the Microsoft 365 compliance center](migrate-legacy-eDiscovery-searches-and-holds.md).</span></span>

<span data-ttu-id="ae71e-256">**コマンドレットが廃止された後でも、検索を削除または取得することはできますか?**</span><span class="sxs-lookup"><span data-stu-id="ae71e-256">**After the cmdlets are retired, will I still be able to remove or retrieve searches?**</span></span>

<span data-ttu-id="ae71e-257">はい。検索を作成および変更する機能を削除していますが、さらに通知されるまで **get-mailboxsearch** を使用して、 **get-mailboxsearch を削除** することもできます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-257">Yes, although we're removing the ability to create and modify searches, you'll still be able to use **Get-MailboxSearch** and **Remove-MailboxSearch** until further notice.</span></span> <span data-ttu-id="ae71e-258">ただし、これらのコマンドレットを使用することは、退職後にお客様の責任があります。</span><span class="sxs-lookup"><span data-stu-id="ae71e-258">However, the use of these cmdlets will be at your own risk after the retirement dates and Microsoft Support will no longer be able to provide assistance.</span></span>

## <a name="search-mailbox-cmdlet"></a><span data-ttu-id="ae71e-259">Search-Mailbox コマンドレット</span><span class="sxs-lookup"><span data-stu-id="ae71e-259">Search-Mailbox cmdlet</span></span>

<span data-ttu-id="ae71e-260">Exchange Online PowerShell の **Search メールボックス** コマンドレットは、2018で開始されるコマンドレットの出力で、最初に通知されたとおりに廃止されています。</span><span class="sxs-lookup"><span data-stu-id="ae71e-260">The **Search-Mailbox** cmdlet in Exchange Online PowerShell is being retired as originally announced in a warning in the cmdlet output starting back in 2018.</span></span> <span data-ttu-id="ae71e-261">最初は、 **検索-メールボックス** コマンドレットを使用して、ユーザーのメールボックスを検索し、悪意のあるコンテンツを削除しました。</span><span class="sxs-lookup"><span data-stu-id="ae71e-261">The **Search-Mailbox** cmdlet was originally used to search a user's mailbox and purge malicious content.</span></span> <span data-ttu-id="ae71e-262">コンテンツを検索して削除するには、Office 365 セキュリティ & コンプライアンスセンターの PowerShell で **new-compliancesearch** および **new-compliancesearchaction** コマンドレットの使用を開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ae71e-262">We recommend that you start using the **New-ComplianceSearch** and **New-ComplianceSearchAction** cmdlets in Office 365 Security & Compliance Center PowerShell to search for and purge content.</span></span> <span data-ttu-id="ae71e-263">組み込みのセキュリティ機能については、 [<span class="underline">microsoft 365 のセキュリティ機能</span>](https://docs.microsoft.com/microsoft-365/security/) により、電子メールやその他の多くの microsoft サービスに対する堅牢な脅威保護が提供されます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-263">For a built-in security experience, the [<span class="underline">Microsoft 365 security features</span>](https://docs.microsoft.com/microsoft-365/security/) provide robust threat protection for email and many other Microsoft services.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="ae71e-264">影響を受ける組織の範囲</span><span class="sxs-lookup"><span data-stu-id="ae71e-264">Scope of affected organizations</span></span>

- <span data-ttu-id="ae71e-265">Office 365 と Microsoft 365 エンタープライズ組織</span><span class="sxs-lookup"><span data-stu-id="ae71e-265">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="ae71e-266">Office 365 および Microsoft 365 エデュケーション組織</span><span class="sxs-lookup"><span data-stu-id="ae71e-266">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="ae71e-267">Office 365 および Microsoft 365 Government 組織。これには GCC、GCC High、DoD が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-267">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="ae71e-268">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="ae71e-268">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="ae71e-269">タイムライン</span><span class="sxs-lookup"><span data-stu-id="ae71e-269">Timeline</span></span>

-  <span data-ttu-id="ae71e-270">2020年7月1日: **検索-メールボックス** コマンドレットが使用できなくなり、Microsoft サポートからサポートが提供されなくなります。</span><span class="sxs-lookup"><span data-stu-id="ae71e-270">July 1, 2020: The **Search-Mailbox** cmdlet will no longer be available and Microsoft Support will no longer provide assistance.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="ae71e-271">代替ツール</span><span class="sxs-lookup"><span data-stu-id="ae71e-271">Alternative tools</span></span>

<span data-ttu-id="ae71e-272">次の表では、廃止される既存の機能を置き換えるために使用できるその他のツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ae71e-272">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="ae71e-273">機能</span><span class="sxs-lookup"><span data-stu-id="ae71e-273">Functionality</span></span></th>
<th><span data-ttu-id="ae71e-274">代替ツール</span><span class="sxs-lookup"><span data-stu-id="ae71e-274">Alternative tools</span></span></th>
<th><span data-ttu-id="ae71e-275">コメント</span><span class="sxs-lookup"><span data-stu-id="ae71e-275">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="ae71e-276">メールボックスを検索する</span><span class="sxs-lookup"><span data-stu-id="ae71e-276">Search a mailbox</span></span></td>
<td><p><span data-ttu-id="ae71e-277"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-New-compliancesearch</span></a></span><span class="sxs-lookup"><span data-stu-id="ae71e-277"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="ae71e-278"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-New-compliancesearchaction</span></a></span><span class="sxs-lookup"><span data-stu-id="ae71e-278"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p></a></p></td>
<td><p><span data-ttu-id="ae71e-279">New-compliancesearch および New-compliancesearchaction コマンドレットは、コンテンツの検索とエクスポートを支援するために連携しています。</span><span class="sxs-lookup"><span data-stu-id="ae71e-279">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and export content.</span></span> <span data-ttu-id="ae71e-280"><strong>新しい検索</strong><strong>を作成</strong>し、 <strong>new-compliancesearch</strong>コマンドレットを使用して検索の推定値を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-280">You can create a new search and view the search estimate by using the <strong>New-</strong>, <strong>Get-</strong>, and <strong>Start-ComplianceSearch</strong> cmdlets.</span></span> <span data-ttu-id="ae71e-281">その後、 <strong>new-compliancesearchaction</strong> コマンドを使用して検索結果をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-281">Then you can use the <strong>New-ComplianceSearchAction -Export</strong> command to export the search results.</span></span> <span data-ttu-id="ae71e-282">引き続き、Microsoft 365 コンプライアンスセンターのコア電子情報開示ツールを使用して、それらの検索結果をローカルコンピューターにダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae71e-282">You'll still have to use the core eDiscovery tool in the Microsoft 365 compliance center to download those search results to your local computer.</span></span></p></p>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="ae71e-283">メールボックスからバルクメールを削除する</span><span class="sxs-lookup"><span data-stu-id="ae71e-283">Delete bulk email from a mailbox</span></span></td>
<td><p><span data-ttu-id="ae71e-284"><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">メールボックスのアーカイブと削除ポリシーを設定する</span></a></span><span class="sxs-lookup"><span data-stu-id="ae71e-284"><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">Set up an archive and deletion policy for mailboxes</span></a></span></span></p>
<p></p></td>
<td><p><span data-ttu-id="ae71e-285">管理者は、ユーザーのアーカイブメールボックスにアイテムを自動的に移動し、メールボックスからアイテムを自動的に削除するアーカイブポリシーと削除ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-285">Admins can create an archiving and deletion policy that automatically moves items to a user's archive mailbox and automatically deletes items from the mailbox.</span></span></p>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="ae71e-286">検索結果を探索メールボックスにコピーする</span><span class="sxs-lookup"><span data-stu-id="ae71e-286">Copy search results to a discovery mailbox</span></span></td>
<td> </td>
<td><span data-ttu-id="ae71e-287">この機能は、Microsoft 365 のすべてのサービスへのアクセスを提供しないので、直接交換することはできません。</span><span class="sxs-lookup"><span data-stu-id="ae71e-287">There's no direct replacement for this functionality because it does not provide access to all Microsoft 365 services.</span></span> <span data-ttu-id="ae71e-288">代替ソリューションについては、「 <strong>get-mailboxsearch コマンドレット</strong> 」セクションの faq を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae71e-288">See the FAQs in the <strong>\*-MailboxSearch cmdlets</strong> section for alternative solutions.</span></span> </td>
</tr>
<tr class=odd>
  <td><span data-ttu-id="ae71e-289">あるメールボックスから別のメールボックスにメッセージをコピーする</span><span class="sxs-lookup"><span data-stu-id="ae71e-289">Copy messages from one mailbox to a different mailbox</span></span></td>
  <td><span data-ttu-id="ae71e-290"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">メールボックスへのアクセス許可の割り当て</a></span><span class="sxs-lookup"><span data-stu-id="ae71e-290"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
  <td><span data-ttu-id="ae71e-291">他のユーザーの電子メールにアクセスできるようにする (従業員が組織を離れたときに、別のユーザーに元従業員の電子メールへのアクセス権を付与する必要がある場合など) には、元従業員のメールボックスにアクセスするためのアクセス許可を割り当てることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ae71e-291">To give a person access to another user's email (such as when an employee leaves your organization and you need to give another person access to the former employee's email), we recommended that you assign that person permissions to access the former employee's mailbox.</span></span> <span data-ttu-id="ae71e-292">そのため、メールボックスアイテムを別のユーザーのメールボックスまたは共有メールボックスにコピーするのではなく、移動元のメールボックスにアクセスするためのユーザー権限のみを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-292">So instead of copying mailbox items to another user mailbox or a shared mailbox, just assign a user permissions to access the source mailbox.</span></span></td>
</tr>
<tr class=even>
  <td><span data-ttu-id="ae71e-293">メールボックスからメッセージを削除する</span><span class="sxs-lookup"><span data-stu-id="ae71e-293">Purge messages from a mailbox</span></span></td>
<td><p><span data-ttu-id="ae71e-294"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-New-compliancesearch</span></a></span><span class="sxs-lookup"><span data-stu-id="ae71e-294"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="ae71e-295"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-New-compliancesearchaction</span></a></span><span class="sxs-lookup"><span data-stu-id="ae71e-295"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p></p></td>
<td><p><span data-ttu-id="ae71e-296">New-compliancesearch および New-compliancesearchaction コマンドレットは、コンテンツの検索と削除を支援するために連携しています。</span><span class="sxs-lookup"><span data-stu-id="ae71e-296">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and purge content.</span></span> <span data-ttu-id="ae71e-297"><strong>New-compliancesearch</strong>および<strong>new-compliancesearch</strong>コマンドレットを使用して検索を作成して実行することができます。その後、 <strong>new-compliancesearchaction</strong>コマンドを使用してコンテンツを削除できます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-297">You can create and run a search with <strong>New-ComplianceSearch</strong> and <strong>New-ComplianceSearch</strong> cmdlets, and then you can purge the content by using <strong>New-ComplianceSearchAction -Purge -PurgeType</strong> command.</span></span> <span data-ttu-id="ae71e-298">詳細については、「 <a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">メッセージを検索して削除する</span></a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae71e-298">For more information, see <a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">Search for and delete messages</span></a>.</span></span></p>
</td>
</tr>
<tr class="odd"> 
<td><span data-ttu-id="ae71e-299">メールボックスからメッセージを削除する</span><span class="sxs-lookup"><span data-stu-id="ae71e-299">Purge messages from a mailbox</span></span></td>
<td><span data-ttu-id="ae71e-300"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">メールボックスへのアクセス許可の割り当て</a></span><span class="sxs-lookup"><span data-stu-id="ae71e-300"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
<td><span data-ttu-id="ae71e-301">メールボックスからメッセージを削除するには、従業員のメールボックスにアクセスするためのアクセス許可を管理者に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-301">To purge messages from a mailbox, assign an administrator permissions to access the employee's mailbox.</span></span> <span data-ttu-id="ae71e-302">メッセージを削除し、必要に応じて再利用して、Outlook の組み込みの検索と表示機能を活用することができます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-302">Messages can be deleted and recycled as needed taking advantage of the built in search and viewing capabilities in Outlook.</span></span></td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a><span data-ttu-id="ae71e-303">Exchange Web サービス API の操作</span><span class="sxs-lookup"><span data-stu-id="ae71e-303">Exchange Web Services API operations</span></span>

<span data-ttu-id="ae71e-304">Exchange Web サービス API のこれらの操作は、exchange 管理センターの In-Place 電子情報開示 & 保持機能、および Exchange Online PowerShell の **\* get-mailboxsearch** コマンドレットで使用されます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-304">These operations in the Exchange Web Services API are used by the In-Place eDiscovery & Holds feature in the Exchange admin center and the corresponding **\*-MailboxSearch** cmdlets in Exchange Online PowerShell.</span></span> <span data-ttu-id="ae71e-305">また、他の従来の電子情報開示ツールを撤去する際にも廃止されます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-305">They will also be retired as part of retiring the other legacy eDiscovery tools.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="ae71e-306">影響を受ける組織の範囲</span><span class="sxs-lookup"><span data-stu-id="ae71e-306">Scope of affected organizations</span></span>

- <span data-ttu-id="ae71e-307">Office 365 と Microsoft 365 エンタープライズ組織</span><span class="sxs-lookup"><span data-stu-id="ae71e-307">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="ae71e-308">Office 365 および Microsoft 365 エデュケーション組織</span><span class="sxs-lookup"><span data-stu-id="ae71e-308">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="ae71e-309">Office 365 および Microsoft 365 Government 組織。これには GCC、GCC High、DoD が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-309">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="ae71e-310">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="ae71e-310">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="ae71e-311">タイムライン</span><span class="sxs-lookup"><span data-stu-id="ae71e-311">Timeline</span></span>

- <span data-ttu-id="ae71e-312">2020年7月1日: GetSearchableMailboxes ボックス、Searchemail メールボックス、SetHoldOnMailboxes、および GetHoldOnMailboxes 操作を使用できなくなり、Microsoft サポートからサポートが提供されなくなります。</span><span class="sxs-lookup"><span data-stu-id="ae71e-312">July 1, 2020: The GetSearchableMailboxes, SearchMailboxes, SetHoldOnMailboxes, and GetHoldOnMailboxes operations will no longer be available, and Microsoft Support will no longer provide assistance.</span></span>

## <a name="advanced-ediscovery-v10"></a><span data-ttu-id="ae71e-313">Advanced eDiscovery v1.0</span><span class="sxs-lookup"><span data-stu-id="ae71e-313">Advanced eDiscovery v1.0</span></span>

<span data-ttu-id="ae71e-314">Advanced eDiscovery v2.0 は、[ **Advanced ediscovery に切り替え** ] をクリックすることで、コア電子情報開示のケースで利用可能なアドバンスト ediscovery のバージョンで、廃止される予定です。</span><span class="sxs-lookup"><span data-stu-id="ae71e-314">Advanced eDiscovery v1.0, which is the version of Advanced eDiscovery available in a core eDiscovery case by clicking **Switch to Advanced eDiscovery** , is being retired.</span></span> <span data-ttu-id="ae71e-315">この機能は、Microsoft 365 コンプライアンスセンターの新しい [高度な電子情報開示ソリューション](https://aka.ms/edisco) に置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="ae71e-315">Its functionality has been replaced by the new [Advanced eDiscovery solution](https://aka.ms/edisco) in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="ae71e-316">組織が Advanced eDiscovery v2.0 を使用しているかどうかを判断するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="ae71e-316">To determine if your organization is using Advanced eDiscovery v1.0:</span></span>

1. <span data-ttu-id="ae71e-317">[Office 365 セキュリティ & コンプライアンスセンター](https://protection.office.com)に移動します。</span><span class="sxs-lookup"><span data-stu-id="ae71e-317">Go to the [Office 365 Security & Compliance Center](https://protection.office.com).</span></span>

2. <span data-ttu-id="ae71e-318">セキュリティ & コンプライアンスセンターの左側のナビゲーションウィンドウで、[電子情報開示 **> 電子** 情報開示] をクリックし、コア電子情報開示ケースを開きます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-318">In the left navigation pane of the Security & Compliance Center, click **eDiscovery > eDiscovery** , and open a Core eDiscovery case.</span></span>

3. <span data-ttu-id="ae71e-319">[ **高度な電子情報開示に切り替え** ] ボタンが表示されている場合は、それをクリックすると、[advanced ediscovery] の1.0 バージョンに移動します。これは廃止されています。</span><span class="sxs-lookup"><span data-stu-id="ae71e-319">If you see the **Switch to Advanced eDiscovery** button, then clicking it will take you to the 1.0 version of Advanced eDiscovery, which is being retired.</span></span> <span data-ttu-id="ae71e-320">コア電子情報開示でケースを作成して管理する機能は影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="ae71e-320">The ability to create and manage cases in Core eDiscovery won't be affected.</span></span> <span data-ttu-id="ae71e-321">高度な電子情報開示のサポート案件データを追加および分析する機能 ([ **Advanced ediscovery への切り替え** ] をクリックする) は廃止されています。</span><span class="sxs-lookup"><span data-stu-id="ae71e-321">Only the ability to add and analyze case data in Advanced eDiscovery v1.0 (by clicking **Switch to Advanced eDiscovery** ) is being retired.</span></span>

<span data-ttu-id="ae71e-322">Microsoft 365 の新しい高度な電子情報開示ソリューション ( *上級電子情報開示* v2.0 とも呼ばれる) は、元のソリューションのすべての機能を提供していますが、他の Microsoft 365 サービスのコンテンツを特定し、そのコンテンツを収集して、レビュー担当者が fast search クエリ、タグ付け、および分析機能を利用して関連するドキュメントを選別できる</span><span class="sxs-lookup"><span data-stu-id="ae71e-322">The new Advanced eDiscovery solution in Microsoft 365 (also known as *Advanced eDiscovery v2.0* ) provides all of the capabilities of the original solution, but now includes a custodian-based approach of identifying content in other Microsoft 365 services, collecting that content, and then adding it to a review set where reviewers can take advantage of fast search queries, tagging, and analytics features to help cull relevant documents.</span></span> <span data-ttu-id="ae71e-323">上級電子情報開示では、Microsoft および Microsoft 以外のファイルの種類の処理機能とネイティブビューアーが向上しています。 [ここ](https://docs.microsoft.com/microsoft-365/compliance/supported-filetypes-ediscovery20) では、ファイルの種類の完全なリストと、サポートされているメタデータフィールドについて [説明します](https://docs.microsoft.com/microsoft-365/compliance/document-metadata-fields-in-advanced-ediscovery)。</span><span class="sxs-lookup"><span data-stu-id="ae71e-323">Advanced eDiscovery now includes improved processing and native viewers for both Microsoft and non-Microsoft file types, a full list of file types is [here](https://docs.microsoft.com/microsoft-365/compliance/supported-filetypes-ediscovery20) and supported metadata fields are [here](https://docs.microsoft.com/microsoft-365/compliance/document-metadata-fields-in-advanced-ediscovery).</span></span> <span data-ttu-id="ae71e-324">また、新しい高度な電子情報開示ソリューションは、強力な電子情報開示ケース内で、さまざまなサービスのコンテンツに保持を適用したり、保留リストのユーザーに通知したり、保管担当者応答を追跡したりする強力な保管担当者ホールド管理機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="ae71e-324">Also, the new Advanced eDiscovery solution provides a powerful custodian holds management feature that lets you apply holds to content in different services, notify users of the holds, and track custodian responses, all within an Advanced eDiscovery case.</span></span>

<span data-ttu-id="ae71e-325">Advanced eDiscovery v2.0 へのアクセス</span><span class="sxs-lookup"><span data-stu-id="ae71e-325">To access Advanced eDiscovery v2.0:</span></span>

1. <span data-ttu-id="ae71e-326">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com) にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ae71e-326">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="ae71e-327">Microsoft 365 コンプライアンス センターの左側のナビゲーション ウィンドウで、[ **すべてを表示** ] をクリックし、 **[eDiscovery] > [Advanced]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae71e-327">In the left navigation pane of the Microsoft 365 compliance center, click **Show all** , and then click **eDiscovery > Advanced**.</span></span>

<span data-ttu-id="ae71e-328">現時点では、新しい高度な電子情報開示の機能への電子情報開示ワークフローの移行を開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ae71e-328">At this time, we recommend that you begin to transition your eDiscovery workflow to the new Advanced eDiscovery functionality.</span></span> <span data-ttu-id="ae71e-329">必要に応じて、コンテンツをエクスポートしてオフラインで格納することで、高度な電子情報開示1.0 ケースをアーカイブできます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-329">If required, you can archive your Advanced eDiscovery 1.0 cases by exporting the content and storing it offline.</span></span> <span data-ttu-id="ae71e-330">2020年12月31日まで、既存のケースでは Advanced eDiscovery v2.0 へのアクセスが引き続き可能ですが、Microsoft サポートは2020年10月1日以降サポートされません。</span><span class="sxs-lookup"><span data-stu-id="ae71e-330">Although you'll still be able to access Advanced eDiscovery v1.0 in existing cases until December 31, 2020, Microsoft Support won't provide support after October 1, 2020.</span></span> <span data-ttu-id="ae71e-331">詳細については、次のタイムラインを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae71e-331">See the following timeline for more details.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="ae71e-332">影響を受ける組織の範囲</span><span class="sxs-lookup"><span data-stu-id="ae71e-332">Scope of affected organizations</span></span>

- <span data-ttu-id="ae71e-333">Office 365 と Microsoft 365 エンタープライズ組織</span><span class="sxs-lookup"><span data-stu-id="ae71e-333">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="ae71e-334">Office 365 および Microsoft 365 エデュケーション組織</span><span class="sxs-lookup"><span data-stu-id="ae71e-334">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="ae71e-335">Office 365 および Microsoft 365 Government 組織。これには GCC、GCC High、DoD が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-335">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="ae71e-336">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="ae71e-336">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="ae71e-337">タイムライン</span><span class="sxs-lookup"><span data-stu-id="ae71e-337">Timeline</span></span>

- <span data-ttu-id="ae71e-338">2020年7月1日: 新しい Advanced eDiscovery v2.0 のケースを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="ae71e-338">July 1, 2020: You won't be able to create new Advanced eDiscovery v1.0  cases.</span></span>

- <span data-ttu-id="ae71e-339">2020年10月1日: 新しいデータ (高度な電子情報開示の検索結果を準備する) をいつでも追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="ae71e-339">October 1, 2020: You won't be able to add new data (Prepare search results for Advanced eDiscovery) to any cases.</span></span> <span data-ttu-id="ae71e-340">既存のケースでは、ユーザー自身のリスクで引き続きデータを操作できます。</span><span class="sxs-lookup"><span data-stu-id="ae71e-340">You'll be able to continue working with data in existing cases at your own risk.</span></span> <span data-ttu-id="ae71e-341">Microsoft サポートからサポートが提供されなくなります。</span><span class="sxs-lookup"><span data-stu-id="ae71e-341">Microsoft Support will no longer provide assistance.</span></span> 

- <span data-ttu-id="ae71e-342">2020年12月31日: 高度な電子情報開示 v 1.0 のケースにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="ae71e-342">December 31, 2020: You won't be able to access Advanced eDiscovery v1.0 cases.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="ae71e-343">代替ツール</span><span class="sxs-lookup"><span data-stu-id="ae71e-343">Alternative tools</span></span>

<span data-ttu-id="ae71e-344">Microsoft 365 コンプライアンスセンターの [高度な電子情報開示ソリューション](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) 。</span><span class="sxs-lookup"><span data-stu-id="ae71e-344">The [Advanced eDiscovery solution](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) in the Microsoft 365 compliance center.</span></span>
