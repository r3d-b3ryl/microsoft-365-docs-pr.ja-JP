---
title: Microsoft Defender for Office 365 (MDO) メール エンティティ ページ
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft Defender for Office 365 E5 および ATP P1 および ATP P2 のお客様は、電子メール エンティティ ページを使用して各メールの 360 度のビューを取得できます。
ms.openlocfilehash: 0fbf3843aa6e6cef1e748d3b71a68a42efd6fc24
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205313"
---
# <a name="the-email-entity-page"></a><span data-ttu-id="a4480-103">メール エンティティ ページ</span><span class="sxs-lookup"><span data-stu-id="a4480-103">The Email entity page</span></span>

<span data-ttu-id="a4480-104">**この記事の内容:**</span><span class="sxs-lookup"><span data-stu-id="a4480-104">**In this article:**</span></span>
- [<span data-ttu-id="a4480-105">電子メール エンティティ ページにアクセスする</span><span class="sxs-lookup"><span data-stu-id="a4480-105">Reach the email entity page</span></span>](#reach-the-email-entity-page)
- [<span data-ttu-id="a4480-106">電子メール エンティティ ページの読み取り</span><span class="sxs-lookup"><span data-stu-id="a4480-106">Read the email entity page</span></span>](#read-the-email-entity-page)
- <span data-ttu-id="a4480-107">[[電子メール エンティティ] ページ タブを使用する](#use-email-entity-page-tabs)</span><span class="sxs-lookup"><span data-stu-id="a4480-107">[Use email entity page tabs](#use-email-entity-page-tabs)</span></span>
- <span data-ttu-id="a4480-108">[[電子メール エンティティ] ページの新機能](#new-to-the-email-entity-page)</span><span class="sxs-lookup"><span data-stu-id="a4480-108">[New to the email entity page](#new-to-the-email-entity-page)</span></span>

<span data-ttu-id="a4480-109">microsoft Defender for Office 365 (または MDO) E5、MDO P1 と P2 の管理者は、[電子メール] エンティティ ページを使用して電子メールを 360 度表示 **します**。</span><span class="sxs-lookup"><span data-stu-id="a4480-109">Admins of Microsoft Defender for Office 365 (or MDO) E5, and MDO P1 and P2 have a 360-degree view of email using the **Email entity page**.</span></span> <span data-ttu-id="a4480-110">この移動先の電子メール ページは、Threat Explorer の 「電子メールの詳細」 フライアウトで配信される情報 [を強化するために作成されました](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views)。</span><span class="sxs-lookup"><span data-stu-id="a4480-110">This go-to email page was created to enhance information delivered on the [Threat Explorer 'email details' fly-out](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views).</span></span>

## <a name="reach-the-email-entity-page"></a><span data-ttu-id="a4480-111">電子メール エンティティ ページにアクセスする</span><span class="sxs-lookup"><span data-stu-id="a4480-111">Reach the email entity page</span></span>

<span data-ttu-id="a4480-112">既存の Office セキュリティ とコンプライアンス センター (protection.office.com) または新しい Microsoft 365 セキュリティ センター (security.microsoft.com) のいずれかを使用すると、電子メール エンティティ ページを表示して使用できます。</span><span class="sxs-lookup"><span data-stu-id="a4480-112">Either of the existing Office Security and Compliance center (protection.office.com) or new Microsoft 365 Security center (security.microsoft.com) will let you see and use the email entity page..</span></span>

|<span data-ttu-id="a4480-113">中央</span><span class="sxs-lookup"><span data-stu-id="a4480-113">Center</span></span>  |<span data-ttu-id="a4480-114">URL</span><span class="sxs-lookup"><span data-stu-id="a4480-114">URL</span></span>  |<span data-ttu-id="a4480-115">ナビゲーション</span><span class="sxs-lookup"><span data-stu-id="a4480-115">Navigation</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="a4480-116">セキュリティとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="a4480-116">Security & Compliance</span></span> |<span data-ttu-id="a4480-117">protection.office.com</span><span class="sxs-lookup"><span data-stu-id="a4480-117">protection.office.com</span></span> | <span data-ttu-id="a4480-118">脅威管理> エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="a4480-118">Threat Management > Explorer</span></span>   |
|<span data-ttu-id="a4480-119">Microsoft 365 セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="a4480-119">Microsoft 365 security center</span></span> |<span data-ttu-id="a4480-120">security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a4480-120">security.microsoft.com</span></span> | <span data-ttu-id="a4480-121">メール & コラボレーション > エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="a4480-121">Email & Collaboration > Explorer</span></span> |

<span data-ttu-id="a4480-122">脅威エクスプローラーで、調査中のメールの件名を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4480-122">In Threat Explorer, select the subject of an email you're investigating.</span></span> <span data-ttu-id="a4480-123">そのメールのメール のフライアウトの上部にゴールド バーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4480-123">A gold bar will display at the top of the email fly-out for that mail.</span></span> <span data-ttu-id="a4480-124">新しいページへのこの招待には、「新しい電子メール エンティティ ページを強化されたデータで試してみてください。..」と読み上げられます。</span><span class="sxs-lookup"><span data-stu-id="a4480-124">This invitation to the new page, reads 'Try out our new email entity page with enriched data...'.</span></span> <span data-ttu-id="a4480-125">新しいページを表示する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="a4480-125">Select to view the new page.</span></span>

:::image type="content" source="../../media/email-entities-1-navigation-to-ee.png" alt-text="新しいエクスペリエンスに移動するには、*強化されたデータを含む新しい電子メール エンティティ ページを試す* という言葉が付くゴールド バナーが表示されます。":::

:::image type="content" source="../../media/email-entities-2-eep.png" alt-text="電子メール エンティティ ページの次の図は、表示される見出しに焦点を当てします。電子メール ヘッダーがここに表示されます。":::

> [!NOTE]
> <span data-ttu-id="a4480-128">このページを表示および使用するために必要なアクセス許可は、脅威エクスプローラーを表示する場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="a4480-128">The permissions needed to view and use this page are the same as to view Threat Explorer.</span></span> <span data-ttu-id="a4480-129">管理者は、グローバル管理者またはグローバル リーダー、またはセキュリティ管理者またはセキュリティ リーダーのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4480-129">The admin must be a member of Global admin or global reader, or Security admin or security reader.</span></span>

## <a name="read-the-email-entity-page"></a><span data-ttu-id="a4480-130">電子メール エンティティ ページの読み取り</span><span class="sxs-lookup"><span data-stu-id="a4480-130">Read the email entity page</span></span>

<span data-ttu-id="a4480-131">構造は、読みやすく、一目で移動するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="a4480-131">The structure is designed to be easy to read and navigate through at a glance.</span></span> <span data-ttu-id="a4480-132">ページの上部に沿ってさまざまなタブを使用すると、より詳細に調査できます。</span><span class="sxs-lookup"><span data-stu-id="a4480-132">Various tabs along the top of the page allow you to investigate in more detail.</span></span> <span data-ttu-id="a4480-133">レイアウトのしくみを次に示します。</span><span class="sxs-lookup"><span data-stu-id="a4480-133">Here's how the layout works:</span></span>

1. <span data-ttu-id="a4480-134">最も必要なフィールドは、フライアウトの左側にあります。これらの詳細は 'スティッキー' で、フライアウトの残りの部分で移動するタブに関係なく、左側に固定されます。</span><span class="sxs-lookup"><span data-stu-id="a4480-134">The most required fields are on the left side of the fly-out. These details are 'sticky', meaning they're anchored to the left no matter the tab you navigate to in the rest of the fly-out.</span></span>

    :::image type="content" source="../../media/email-entities-3-left-panel.png" alt-text="左側が強調表示された電子メール エンティティ ページのグラフィック。メール配信に関するタイトルと事実はここです。":::

2. <span data-ttu-id="a4480-136">右上隅には、電子メールで実行できるアクションがあります。</span><span class="sxs-lookup"><span data-stu-id="a4480-136">On the top-right corner are the actions that can be taken on an email.</span></span> <span data-ttu-id="a4480-137">エクスプローラーで実行できるアクションは、電子メール エンティティ ページでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="a4480-137">Any actions that can be taken through Explorer will also be available through email entity page.</span></span>

    :::image type="content" source="../../media/email-entities-5-preview.png" alt-text="今回は、*right* 側が強調表示された電子メール エンティティ ページのグラフィック。[メールプレビュー] や [検疫に移動] のようなアクションは次のとおりです。":::

3. <span data-ttu-id="a4480-139">ページの残りの部分を並べ替え、より詳細な分析を行います。</span><span class="sxs-lookup"><span data-stu-id="a4480-139">Deeper analysis can be done by sorting through the rest of the page.</span></span> <span data-ttu-id="a4480-140">メール検出の詳細、メール認証の状態、ヘッダーを確認します。</span><span class="sxs-lookup"><span data-stu-id="a4480-140">Check the email detection details, email authentication status, and header.</span></span> <span data-ttu-id="a4480-141">この領域はケースバイケースで確認する必要がありますが、これらのタブの情報は任意の電子メールで使用できます。</span><span class="sxs-lookup"><span data-stu-id="a4480-141">This area should be looked on a case-by-case basis, but the info in these tabs is available for any email.</span></span>

    :::image type="content" source="../../media/email-entities-4-middle-panel.png" alt-text="このページのメイン パネルには、電子メール ヘッダーと認証状態が含まれます。":::

### <a name="use-email-entity-page-tabs"></a><span data-ttu-id="a4480-143">[電子メール エンティティ] ページ タブを使用する</span><span class="sxs-lookup"><span data-stu-id="a4480-143">Use email entity page tabs</span></span>

<span data-ttu-id="a4480-144">エンティティ ページの上部にあるタブを使用すると、電子メールを効率的に調査できます。</span><span class="sxs-lookup"><span data-stu-id="a4480-144">The tabs along the top of the entity page will allow you to investigate email efficiently.</span></span>

1. <span data-ttu-id="a4480-145">**タイムライン**: メールのタイムライン ビュー (脅威エクスプローラーのタイムラインごとに) は、メールで発生する配信後イベントへの元の配信を示します。</span><span class="sxs-lookup"><span data-stu-id="a4480-145">**Timeline**: The timeline view for an email (per the Threat Explorer timeline) shows the original delivery to post-delivery events that happen on an email.</span></span> <span data-ttu-id="a4480-146">配信後のアクションがないメールの場合、タイムライン ビューに元の配信行が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4480-146">For emails that have no post-delivery actions, the view shows the original delivery row in timeline view.</span></span> <span data-ttu-id="a4480-147">次のようなイベント: ゼロ時間自動削除 (ZAP)、修復、URL クリック、et cetera、system、admin、user などのソースからのイベントは、発生した順序でここに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4480-147">Events like: Zero-hour auto purge (ZAP), Remediate, URL clicks, et cetera, from sources like: system, admin, and user, show up here, in the order in which they occurred.</span></span>
2. <span data-ttu-id="a4480-148">**分析**: 分析は、管理者が電子メールを詳細に分析するのに役立つフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="a4480-148">**Analysis**: Analysis shows fields that help admins analyze an email in depth.</span></span> <span data-ttu-id="a4480-149">管理者が検出、送信者/受信者、および電子メール認証の詳細について理解する必要がある場合は、[分析] タブを使用する必要があります。添付ファイルと URL のリンクは、このページの [関連エンティティ] にも表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4480-149">For cases where admins need to understand more about detection, sender / recipient, and email authentication details, they should use the Analysis tab. Links for Attachments and URLs are also found on this page, under 'Related Entities'.</span></span> <span data-ttu-id="a4480-150">添付ファイルと特定された脅威の両方に番号が付きます。クリックすると、添付ファイルと URL ページに直接アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a4480-150">Both attachments and identified threats are numbered here, and clicking will take you straight to the Attachments and URL pages.</span></span> <span data-ttu-id="a4480-151">このタブには、メール ヘッダーを表示する [ヘッダー *の表示] オプションがあります*。</span><span class="sxs-lookup"><span data-stu-id="a4480-151">This tab also has a View header option to *show the email header*.</span></span> <span data-ttu-id="a4480-152">管理者は、メール ヘッダーの詳細をメイン パネルの情報と並べて比較して、わかりやすくすることができます。</span><span class="sxs-lookup"><span data-stu-id="a4480-152">Admins can compare any detail from email headers, side by side with information on the main panel, for clarity.</span></span>
3. <span data-ttu-id="a4480-153">**添付** ファイル : 電子メールで見つかった添付ファイルと、添付ファイルに見つかった他の詳細を調べる。</span><span class="sxs-lookup"><span data-stu-id="a4480-153">**Attachments**: This examines attachments found in the email with other details found on attachments.</span></span> <span data-ttu-id="a4480-154">現在、表示される添付ファイルの数は 10 に制限されています。</span><span class="sxs-lookup"><span data-stu-id="a4480-154">The number of attachments shown is currently limited to 10.</span></span> <span data-ttu-id="a4480-155">悪意のある添付ファイルの削除の詳細もここに示されています。</span><span class="sxs-lookup"><span data-stu-id="a4480-155">Notice that detonation details for attachments found to be malicious is also shown here.</span></span>
4. <span data-ttu-id="a4480-156">**URL :** このタブには、メールに含まれる URL と URL に関するその他の詳細が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4480-156">**URLs**: This tab lists URLs found in the email with other details about the URLs.</span></span> <span data-ttu-id="a4480-157">URL の数は現在 10 に制限されますが、これらの 10 は悪意のある URL を最初に *表示するために優先順位が付けられています*。</span><span class="sxs-lookup"><span data-stu-id="a4480-157">The number of URLs is limited to 10 right now, but these 10 are prioritized to show *malicious URLs first*.</span></span> <span data-ttu-id="a4480-158">事前設定により、時間と推測作業が節約されます。</span><span class="sxs-lookup"><span data-stu-id="a4480-158">Prioritization saves you time and guess-work.</span></span> <span data-ttu-id="a4480-159">悪意のあると検出され、削除された URL もここに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4480-159">The URLs which were found to be malicious and detonated will also be shown here.</span></span>
5. <span data-ttu-id="a4480-160">**類似の電子メール**: このタブには、このメールに固有のネットワーク メッセージ *ID +* 受信者の組み合わせに似たすべてのメールが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4480-160">**Similar emails**: This tab lists all emails similar to the *network message id + recipient* combination specific to this email.</span></span> <span data-ttu-id="a4480-161">類似性は、メッセージの *本文にのみ基* づいて行います。</span><span class="sxs-lookup"><span data-stu-id="a4480-161">Similarity is based on the *body of the message*, only.</span></span> <span data-ttu-id="a4480-162">メールに対して「類似」として分類する決定には、添付ファイルの考慮事項は含 *めされません*。</span><span class="sxs-lookup"><span data-stu-id="a4480-162">The determinations made on mails to categorize them as 'similar' don't include a consideration of *attachments*.</span></span>

## <a name="new-to-the-email-entity-page"></a><span data-ttu-id="a4480-163">[電子メール エンティティ] ページの新機能</span><span class="sxs-lookup"><span data-stu-id="a4480-163">New to the email entity page</span></span>

<span data-ttu-id="a4480-164">この電子メール エンティティ ページには、新しい機能があります。</span><span class="sxs-lookup"><span data-stu-id="a4480-164">There are new capabilities that come with this email entity page.</span></span> <span data-ttu-id="a4480-165">リストを次に示します。</span><span class="sxs-lookup"><span data-stu-id="a4480-165">Here's the list.</span></span>

### <a name="email-preview-for-cloud-mailboxes"></a><span data-ttu-id="a4480-166">クラウド メールボックスのメール プレビュー</span><span class="sxs-lookup"><span data-stu-id="a4480-166">Email preview for Cloud mailboxes</span></span>
<span data-ttu-id="a4480-167">メールがまだクラウドに存在する場合、管理者はクラウドメールボックス内のメールをプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="a4480-167">Admins can preview emails in Cloud mailboxes, ***if*** the mails are still present in the Cloud.</span></span> <span data-ttu-id="a4480-168">(管理者またはユーザーによる) ソフト削除、または ZAP (検疫) の場合、メールはクラウドの場所に存在しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="a4480-168">In case of a soft delete (by an admin, or user), or ZAP (to quarantine), emails are no longer present in the Cloud location.</span></span> <span data-ttu-id="a4480-169">その場合、管理者はそれらの特定のメールをプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="a4480-169">In that case, admins won't be able to preview those specific mails.</span></span> <span data-ttu-id="a4480-170">削除された電子メール、または配信に失敗した電子メールは、実際にはメールボックスに入れたことがない。</span><span class="sxs-lookup"><span data-stu-id="a4480-170">Emails that were dropped, or where delivery failed, never actually made it into the mailbox.</span></span> <span data-ttu-id="a4480-171">その結果、管理者はそれらのメールもプレビューできません。</span><span class="sxs-lookup"><span data-stu-id="a4480-171">As a result, admins won’t be able to preview those emails either.</span></span>

> [!WARNING]
><span data-ttu-id="a4480-172">メールのプレビューには、管理者に割り当てるには、 \***Preview** _ という特別な役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="a4480-172">Previewing emails requires a special role called \***Preview** _ to be assigned to admins.</span></span> <span data-ttu-id="a4480-173">*security.microsoft.com この* 役割を追加するには、[&] の [>] の [>] の [メール& コラボレーション ロール]  、または [protection.office.com のアクセス許可]*にアクセスします*。 </span><span class="sxs-lookup"><span data-stu-id="a4480-173">You can add this role by going to _ *Permissions & roles*\* > **Email & collaboration roles** in *security.microsoft.com*, or **Permissions** in *protection.office.com*.</span></span> <span data-ttu-id="a4480-174">[プレビュー ***]*** 役割を任意の役割グループに追加するか、組織内の管理者が脅威エクスプローラーで作業できる役割グループのコピーを追加します。</span><span class="sxs-lookup"><span data-stu-id="a4480-174">Add the ***Preview*** role to any of the role groups, or a copy of a role group that allows admins in your organization to work in Threat Explorer.</span></span>

### <a name="detonation-details"></a><span data-ttu-id="a4480-175">Detonation の詳細</span><span class="sxs-lookup"><span data-stu-id="a4480-175">Detonation details</span></span>

<span data-ttu-id="a4480-176">これらの詳細は、電子メールの添付ファイルと URL に固有です。</span><span class="sxs-lookup"><span data-stu-id="a4480-176">These details are specific to email attachments and URLs.</span></span>

<span data-ttu-id="a4480-177">ユーザーは、メールボックス内に見つかった既知の悪意のある添付ファイルまたはハイパーリンクに関する強化された起発の詳細を表示します。たとえば、Detonation Chain、Detonation Summary、Screenshot、および Observed behavior details を使用すると、添付ファイルまたは URL が悪意のあると見なされ、削除されたと見なされた理由をユーザーが理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a4480-177">Users will see enriched detonation details for known malicious attachments or hyperlinks found in their mailboxes, including Detonation chain, Detonation summary, Screenshot, and Observed behavior details to help customers understand why the attachment or URL was deemed malicious and detonated.</span></span>
 
- <span data-ttu-id="a4480-178">*Detonation chain*: 1 つのファイルまたは URL のデトレーションによって、複数の起起をトリガーできます。</span><span class="sxs-lookup"><span data-stu-id="a4480-178">*Detonation chain*: A single file or URL detonation can trigger multiple detonations.</span></span> <span data-ttu-id="a4480-179">Detonation チェーンは、元の悪意のあるファイルまたは評決を引き起こした URL、および起訴によって発生した他のすべてのファイルまたは URL を含む、起訴のパスを追跡します。</span><span class="sxs-lookup"><span data-stu-id="a4480-179">The Detonation chain tracks the path of detonations, including the original malicious file or URL that caused the verdict, and all other files or URLs effected by the detonation.</span></span> <span data-ttu-id="a4480-180">これらの URL または添付ファイルは、電子メールに直接存在しない場合がありますが、その分析を含めて、ファイルまたは URL が悪意のあると見つかった理由を判断する上で重要です。</span><span class="sxs-lookup"><span data-stu-id="a4480-180">These URLs or attached files may not be directly present in the email, but including that analysis is important to determining why the file or URL was found to be malicious.</span></span>
- <span data-ttu-id="a4480-181">*Detonation の概要*: 次の情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="a4480-181">*Detonation summary*: This gives information on:</span></span>
    - <span data-ttu-id="a4480-182">Detonation 時間範囲。</span><span class="sxs-lookup"><span data-stu-id="a4480-182">Detonation time range.</span></span>
    - <span data-ttu-id="a4480-183">添付ファイルまたは URL の評決。</span><span class="sxs-lookup"><span data-stu-id="a4480-183">Verdict of the attached file, or URL.</span></span>
    - <span data-ttu-id="a4480-184">関連情報 (ファイル番号、URL、IPs、またはドメイン)。</span><span class="sxs-lookup"><span data-stu-id="a4480-184">Related info (file number, URLs, IPs, or Domains), which are other entities examined during detonation.</span></span>
- <span data-ttu-id="a4480-185">*Detonation スクリーンショット*: これは、デトレーション プロセス中に撮影されたスクリーンショットを示します。</span><span class="sxs-lookup"><span data-stu-id="a4480-185">*Detonation screenshot*: This shows screenshot(s) taken during detonation process.</span></span>
- <span data-ttu-id="a4480-186">*起立の詳細*: これらは、起起中に行った各プロセスの正確な動作の詳細です。</span><span class="sxs-lookup"><span data-stu-id="a4480-186">*Detonation details*: These are the exact behavior details of each process that took place during the detonation.</span></span>

:::image type="content" source="../../media/email-entities-6-detonation-page.png" alt-text="見出し *Deep Analysis*の下のチェーン、概要、起起の詳細、およびスクリーンショットを示す起起の概要のスクリーンショット。":::

### <a name="other-innovations"></a><span data-ttu-id="a4480-188">その他の技術革新</span><span class="sxs-lookup"><span data-stu-id="a4480-188">Other innovations</span></span>

<span data-ttu-id="a4480-189">*タグ*: ユーザーに適用されるタグです。</span><span class="sxs-lookup"><span data-stu-id="a4480-189">*Tags*: These are tags applied to users.</span></span> <span data-ttu-id="a4480-190">ユーザーが受信者の場合、管理者には受信者タグが *表示* されます。</span><span class="sxs-lookup"><span data-stu-id="a4480-190">If the user is a recipient, admins will see a *recipient* tag.</span></span> <span data-ttu-id="a4480-191">同様に、ユーザーが送信者の場合は *送信者タグです* 。</span><span class="sxs-lookup"><span data-stu-id="a4480-191">Likewise, if the user is a sender, a *sender* tag.</span></span> <span data-ttu-id="a4480-192">これは、電子メール エンティティ ページの左側に表示されます (スティッキーと説明されている部分では、ページに固定されます)。</span><span class="sxs-lookup"><span data-stu-id="a4480-192">This will appear in the left side of the email entities page (in the part that's described as *sticky* and, thus, anchored to the page).</span></span>

<span data-ttu-id="a4480-193">*最新の配信場所*: 最新の配信場所は、ZAP のようなシステムアクション、または削除済みアイテムへの移動、完了のような管理アクションの後に電子メールが届いた場所です。</span><span class="sxs-lookup"><span data-stu-id="a4480-193">*Latest delivery location*: The latest delivery location is the location where an email landed after system actions like ZAP, or admin actions like Move to Deleted Items, finish.</span></span> <span data-ttu-id="a4480-194">最新の配信場所は、メッセージの現在の場所を管理者に通知する *目的ではありません* 。</span><span class="sxs-lookup"><span data-stu-id="a4480-194">Latest delivery location is not intended to inform admins of the message's *current* location.</span></span> <span data-ttu-id="a4480-195">たとえば、ユーザーがメッセージを削除した場合、またはメッセージをアーカイブに移動した場合、配信場所は更新されません。</span><span class="sxs-lookup"><span data-stu-id="a4480-195">For example, if a user deletes a message, or moves it to archive, the delivery location won't be updated.</span></span> <span data-ttu-id="a4480-196">ただし、システムアクションが実行され、場所が更新された場合 (ZAP など、検疫に移動する電子メールなど)、これにより[最新の配信場所] が [検疫] に更新されます。</span><span class="sxs-lookup"><span data-stu-id="a4480-196">However, if a system action has taken place and updated the location (like a ZAP resulting in an email moving to Quarantine) this would update the Latest delivery location to Quarantine.</span></span>

<span data-ttu-id="a4480-197">*メールの詳細*: [分析] タブで使用できる電子メールの詳細を *理解するために必要* な詳細。</span><span class="sxs-lookup"><span data-stu-id="a4480-197">*Email details*: Details required for a deeper understanding of email available in the *Analysis* tab.</span></span>

- <span data-ttu-id="a4480-198">*Exchange トランスポート ルール (ETRs* または Mailflow ルール) : これらのルールは、トランスポート層のメッセージに適用され、フィッシングおよびスパムの評決よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="a4480-198">*Exchange Transport Rules (ETRs or Mailflow rules)*: These rules are applied to a message at the transport layer and take precedence over phish and spam verdicts.</span></span> <span data-ttu-id="a4480-199">これらは Exchange 管理センターでのみ作成および変更できますが、ETR がメッセージに適用される場合は、ETR 名と GUID がここに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4480-199">These can be only created and modified in the Exchange admin center, but if any ETR applies to a message, the ETR name and GUID will be shown here.</span></span> <span data-ttu-id="a4480-200">追跡の目的で有用な情報。</span><span class="sxs-lookup"><span data-stu-id="a4480-200">Valuable information for tracking purposes.</span></span>
    
- <span data-ttu-id="a4480-201">*System Overrides*: これは、システムによって指定された配信場所 (脅威と検出技術による) を上書きして、メッセージを対象とした配信場所に対して例外を作成する手段です。</span><span class="sxs-lookup"><span data-stu-id="a4480-201">*System Overrides*: This is a means of making exceptions to the delivery location intended for a message by overriding the delivery location given by system (as per the threat and detection tech).</span></span>
    
- <span data-ttu-id="a4480-202">*迷惑メールボックス ルール*: 'Junk' は、すべてのメールボックスで既定で有効になっている非表示の受信トレイ ルールです。</span><span class="sxs-lookup"><span data-stu-id="a4480-202">*Junk Mailbox Rule*: 'Junk' is hidden Inbox rule that's enabled by default in every mailbox.</span></span>
    - <span data-ttu-id="a4480-203">メールボックスで迷惑メール ルールが有効になっている場合、Exchange Online Protection (EOP) は、いくつかの条件に従ってメッセージを迷惑メールに移動できます。</span><span class="sxs-lookup"><span data-stu-id="a4480-203">When the Junk email rule is enabled on the mailbox, Exchange Online Protection (EOP) is able to move messages to Junk according to some criteria.</span></span> <span data-ttu-id="a4480-204">この移動は、スパム フィルターの評決アクション [メッセージを迷惑メール フォルダーに移動する] またはメールボックスの [送信者のブロック] リストに基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="a4480-204">The move can be based on spam filtering verdict action *Move message to Junk Email folder*, or on the Blocked Senders list on the mailbox.</span></span> <span data-ttu-id="a4480-205">迷惑メール ルールを無効にすると、メールボックスの差出人セーフ リストに基づいて迷惑メール フォルダーにメッセージが配信されません。</span><span class="sxs-lookup"><span data-stu-id="a4480-205">Disabling the Junk email rule prevents the delivery of messages to the Junk email folder based on the *Safe Senders* list on the mailbox.</span></span>
    - <span data-ttu-id="a4480-206">メールボックスで迷惑メール ルールが無効になっている場合、EOP はスパム フィルターの評決アクション [迷惑メール フォルダーにメッセージを移動する] またはメールボックスのセーフ リスト コレクションに基づいてメッセージを迷惑メール フォルダーに移動できません。</span><span class="sxs-lookup"><span data-stu-id="a4480-206">When the junk email rule is *disabled* on the mailbox, EOP can't move messages to the Junk Email folder based on the spam filtering verdict action *Move message to Junk Email folder*, or the safe list collection on the mailbox.</span></span>
    
- <span data-ttu-id="a4480-207">*バルク準拠レベル (BCL)*: メッセージのバルク 苦情レベル (BCL)。</span><span class="sxs-lookup"><span data-stu-id="a4480-207">*Bulk Compliant Level (BCL)*: The Bulk Complaint Level (BCL) of the message.</span></span> <span data-ttu-id="a4480-208">BCL が高いほど、バルク メール メッセージが苦情を生成する可能性が高くなります (電子メールがスパムである可能性が高い場合、自然な結果)。</span><span class="sxs-lookup"><span data-stu-id="a4480-208">A higher BCL indicates a bulk mail message is more likely to generate complaints (the natural result if the email is likely to be spam).</span></span>
    
- <span data-ttu-id="a4480-209">*スパム信頼レベル (SCL)*: メッセージのスパム信頼レベル (SCL)。</span><span class="sxs-lookup"><span data-stu-id="a4480-209">*Spam Confidence Level (SCL)*: The spam confidence level (SCL) of the message.</span></span> <span data-ttu-id="a4480-210">値が高いほど、メッセージがスパムである可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="a4480-210">A higher value indicates the message is more likely to be spam.</span></span>

- <span data-ttu-id="a4480-211">*ドメイン名*: 送信者のドメイン名です。</span><span class="sxs-lookup"><span data-stu-id="a4480-211">*Domain Name*: Is the sender domain name.</span></span>
    
- <span data-ttu-id="a4480-212">*ドメイン所有者*: 送信ドメインの所有者を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4480-212">*Domain Owner*: Specifies the owner of the sending domain.</span></span>
    
- <span data-ttu-id="a4480-213">*ドメインの場所*: 送信ドメインの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4480-213">*Domain Location*: Specifies the location of the sending domain.</span></span>
    
- <span data-ttu-id="a4480-214">*ドメイン作成日*: 送信ドメインの作成日を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4480-214">*Domain Created Date*: Specifies the date of creation of the sending domain.</span></span> <span data-ttu-id="a4480-215">新しく作成されたドメインは、他のシグナルが疑わしい動作を示す場合には注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="a4480-215">A newly created domain is something you could be cautious of if other signals indicate some suspicious behavior.</span></span>

<span data-ttu-id="a4480-216">*電子メール認証*: Microsoft 365 で使用される電子メール認証方法には、SPF、DKIM、DMARC が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a4480-216">*Email Authentication*: Email authentication methods used by Microsoft 365 include SPF, DKIM, and DMARC.</span></span>

- <span data-ttu-id="a4480-217">Sender Policy Framework **(SPF):** メッセージの SPF チェックの結果について説明します。</span><span class="sxs-lookup"><span data-stu-id="a4480-217">Sender Policy Framework (**SPF**):  Describes results for SPF check for the message.</span></span> <span data-ttu-id="a4480-218">次の値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a4480-218">Possible values can be:</span></span>
    - <span data-ttu-id="a4480-219">パス (IP アドレス): 渡されたメッセージの SPF チェックで、送信者の IP アドレスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a4480-219">Pass (IP address): The SPF check for the message passed and includes the sender's IP address.</span></span> <span data-ttu-id="a4480-220">送信者のドメインに代わってメールを送信または中継する許可がクライアントに与えられています。</span><span class="sxs-lookup"><span data-stu-id="a4480-220">The client is authorized to send or relay email on behalf of the sender's domain.</span></span>
    - <span data-ttu-id="a4480-221">Fail (IP address): メッセージの SPF チェックが失敗し、送信者の IP アドレスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a4480-221">Fail (IP address): The SPF check for the message failed and includes the sender's IP address.</span></span> <span data-ttu-id="a4480-222">hard fail と呼ばれることもあります。</span><span class="sxs-lookup"><span data-stu-id="a4480-222">This is sometimes called hard fail.</span></span>
    - <span data-ttu-id="a4480-223">Softfail (理由): SPF レコードは、ホストを送信が許可されていないが、移行中として指定しました。</span><span class="sxs-lookup"><span data-stu-id="a4480-223">Softfail (reason): The SPF record designated the host as not being allowed to send but is in transition.</span></span>
    - <span data-ttu-id="a4480-224">ニュートラル: SPF レコードには、IP アドレスの送信が承認されているかどうかを明示的に示します。</span><span class="sxs-lookup"><span data-stu-id="a4480-224">Neutral: The SPF record explicitly states that it does not assert whether the IP address is authorized to send.</span></span>
    - <span data-ttu-id="a4480-225">なし: ドメインに SPF レコードが存在しないか、SPF レコードが結果に評価されます。</span><span class="sxs-lookup"><span data-stu-id="a4480-225">None: The domain doesn't have an SPF record, or the SPF record doesn't evaluate to a result.</span></span>
    - <span data-ttu-id="a4480-226">Temperror: 一時的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="a4480-226">Temperror: A temporary error has occurred.</span></span> <span data-ttu-id="a4480-227">たとえば、DNS エラーです。</span><span class="sxs-lookup"><span data-stu-id="a4480-227">For example, a DNS error.</span></span> <span data-ttu-id="a4480-228">同じチェックが後で成功する場合があります。</span><span class="sxs-lookup"><span data-stu-id="a4480-228">The same check later might succeed.</span></span>
    - <span data-ttu-id="a4480-229">Permerror: 永続的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="a4480-229">Permerror: A permanent error has occurred.</span></span> <span data-ttu-id="a4480-230">たとえば、ドメインに不正な形式の SPF レコードがある場合などです。</span><span class="sxs-lookup"><span data-stu-id="a4480-230">For example, the domain has a badly formatted SPF record.</span></span>

- <span data-ttu-id="a4480-231">DomainKeys Identified Mail (**DKIM**):</span><span class="sxs-lookup"><span data-stu-id="a4480-231">DomainKeys Identified Mail (**DKIM**):</span></span>
    - <span data-ttu-id="a4480-232">Pass: 渡されたメッセージの DKIM チェックを示します。</span><span class="sxs-lookup"><span data-stu-id="a4480-232">Pass: Indicates the DKIM check for the message passed.</span></span>
    - <span data-ttu-id="a4480-233">Fail (Reason): 失敗したメッセージの DKIM チェックと、その理由を示します。</span><span class="sxs-lookup"><span data-stu-id="a4480-233">Fail (reason): Indicates the DKIM check for the message failed and why.</span></span> <span data-ttu-id="a4480-234">たとえば、メッセージが署名されていない場合、署名を認証できない場合などです。</span><span class="sxs-lookup"><span data-stu-id="a4480-234">For example, if the message was not signed or the signature was not verified.</span></span>
    - <span data-ttu-id="a4480-235">なし: メッセージが署名されていないかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="a4480-235">None: Indicates that the message was not signed.</span></span> <span data-ttu-id="a4480-236">これは、ドメインに DKIM レコードがあるかどうかや、DKIM レコードが結果を評価しない (このメッセージが署名されていない点のみ) ことを示しますが、これらを示さない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="a4480-236">This may or may not indicate that the domain has a DKIM record or the DKIM record does not evaluate to a result, only that this message was not signed.</span></span>

- <span data-ttu-id="a4480-237">ドメイン ベースのメッセージ認証、レポート、準拠 **(DMARC):**</span><span class="sxs-lookup"><span data-stu-id="a4480-237">Domain-based Message Authentication, Reporting and Conformance (**DMARC**):</span></span>
    - <span data-ttu-id="a4480-238">Pass: 渡されたメッセージの DMARC チェックを示します。</span><span class="sxs-lookup"><span data-stu-id="a4480-238">Pass: Indicates the DMARC check for the message passed.</span></span>
    - <span data-ttu-id="a4480-239">Fail: メッセージの DMARC チェックが失敗したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="a4480-239">Fail: Indicates the DMARC check for the message failed.</span></span>
    - <span data-ttu-id="a4480-240">Bestguesspass: ドメインの DMARC TXT レコードが存在しないが、存在していた場合は、メッセージの DMARC チェックが渡されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="a4480-240">Bestguesspass: Indicates that no DMARC TXT record for the domain exists, but if one had existed, the DMARC check for the message would have passed.</span></span>
    - <span data-ttu-id="a4480-241">なし: DNS の送信ドメインに DMARC TXT レコードが存在しないかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="a4480-241">None: Indicates that no DMARC TXT record exists for the sending domain in DNS.</span></span>

<span data-ttu-id="a4480-242">*複合認証*: これは、メッセージが本物かどうかを判断するために、SPF、DKIM、DMARC のような電子メール認証を組み合わせ、Microsoft 365 で使用される値です。</span><span class="sxs-lookup"><span data-stu-id="a4480-242">*Composite Authentication*: This is a value is used by Microsoft 365 to combine email authentication like SPF, DKIM, and DMARC, to determine if the message is authentic.</span></span> <span data-ttu-id="a4480-243">評価の *基礎としてメールの From:* ドメインを使用します。</span><span class="sxs-lookup"><span data-stu-id="a4480-243">It uses the *From:* domain of the mail as the basis of evaluation.</span></span>