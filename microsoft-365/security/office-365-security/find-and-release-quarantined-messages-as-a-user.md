---
title: Office 365 のユーザーとして検疫済みメッセージを検索して解放する
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 05/19/2018
audience: Consumer/IW
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
description: Office 365 のユーザーとして、自分のスパム検疫メッセージを次の 2 つのうちいずれかの方法で管理できます。1 つは送信されたスパム通知に直接応答する方法 (管理者がこの機能を設定している場合) で、もう 1 つはセキュリティ &amp; コンプライアンス センターでスパム検疫機能を使用する方法です。
ms.openlocfilehash: bcc9b7ed52af0e9920506aa667e51daad7f82c80
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808002"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-office-365"></a><span data-ttu-id="a2642-103">Office 365 のユーザーとして検疫済みメッセージを検索して解放する</span><span class="sxs-lookup"><span data-stu-id="a2642-103">Find and release quarantined messages as a user in Office 365</span></span>

<span data-ttu-id="a2642-104">Office 365 のユーザーとして、自分に配信されずに検疫に送られたメッセージを次の 2 つのうちいずれかの方法で管理できます。1 つは [送信されたスパム通知に直接応答する方法](use-spam-notifications-to-release-and-report-quarantined-messages.md) (管理者がこの機能を設定している場合) で、もう 1 つはセキュリティ &amp; コンプライアンス センターでスパム検疫機能を使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="a2642-104">As an Office 365 user, you can manage messages that were sent to quarantine instead of sent to you in one of two ways: by [responding to spam notifications sent to you directly](use-spam-notifications-to-release-and-report-quarantined-messages.md) (if your admin has set this up), or by using the Security &amp; Compliance Center.</span></span>

> [!NOTE]
> <span data-ttu-id="a2642-105">管理者の場合は、組織内の他のユーザーのために [検疫済みメッセージを管理する](manage-quarantined-messages-and-files.md) ことができます。</span><span class="sxs-lookup"><span data-stu-id="a2642-105">If you're an admin, you can [manage quarantined messages](manage-quarantined-messages-and-files.md) for other people in your organization.</span></span>

## <a name="view-messages-that-were-sent-to-quarantine-instead-of-to-you"></a><span data-ttu-id="a2642-106">自分に配信されずに検疫に送信されたメッセージを表示する</span><span class="sxs-lookup"><span data-stu-id="a2642-106">View messages that were sent to quarantine instead of to you</span></span>

1. <span data-ttu-id="a2642-107">Office 365 にサインインし、職場または学校のアカウントを使用して[セキュリティ/コンプライアンス センター](../../compliance/go-to-the-securitycompliance-center.md)に移動します。</span><span class="sxs-lookup"><span data-stu-id="a2642-107">Sign in to Office 365 and [go to the Security and Compliance Center](../../compliance/go-to-the-securitycompliance-center.md) using your work or school account.</span></span>

2. <span data-ttu-id="a2642-108">左側の [**脅威の管理**] を展開し、[**確認**] を選択して、[**検疫**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a2642-108">On the left, expand **Threat Management**, choose **Review**, and then choose **Quarantine**.</span></span>

    > [!TIP]
    > <span data-ttu-id="a2642-109">[**検疫**] ページ (セキュリティ &amp; コンプライアンス センター内) に直接移動するには、次の URL を使用します。[https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span><span class="sxs-lookup"><span data-stu-id="a2642-109">To go directly to the **Quarantine** page in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span></span>

<span data-ttu-id="a2642-110">既定では、セキュリティ &amp; コンプライアンス センターには、スパムとして検疫されたすべてのメール メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2642-110">By default, the Security &amp; Compliance Center displays all email messages that have been quarantined as spam.</span></span> <span data-ttu-id="a2642-111">メッセージは、受信の [**日付**] に基づいて、最新のものから順に並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="a2642-111">The messages are sorted from newest to oldest based on the **Date** the message was received.</span></span> <span data-ttu-id="a2642-112">各メッセージに [**送信者**]、[**件名**]、および有効期限 ([**有効期限**]) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2642-112">**Sender**, **Subject**, and the expiration date (under **Expires** ) are also displayed for each message.</span></span> <span data-ttu-id="a2642-113">特定のフィールドで並べ替えるには、その列見出しをクリックします。列見出しをもう一度クリックすると、逆の順番に並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="a2642-113">You can sort on a field by clicking the corresponding column header; click a column header a second time to reverse the sort order.</span></span>

<span data-ttu-id="a2642-114">検疫済みメッセージの一覧を表示することも、フィルターを使用して特定のメッセージを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="a2642-114">You can view a list of all quarantined messages, or you can search for specific messages by filtering.</span></span> <span data-ttu-id="a2642-115">一括操作は 100 件以下のアイテムにのみ実行できます。そのため、100 件を越える場合は、フィルターを使って結果セットを小さくすることができます。</span><span class="sxs-lookup"><span data-stu-id="a2642-115">You can only do bulk operations on up to 100 items, so filtering can also help reduce your result set if you have more than that.</span></span> <span data-ttu-id="a2642-116">ドロップダウン リストからオプションを選択することで、メッセージを 1 つの検疫理由についてすばやくフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="a2642-116">You can quickly filter messages for a single quarantine reason by choosing an option from the drop-down list.</span></span> <span data-ttu-id="a2642-117">オプションは以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a2642-117">Options include:</span></span>

- <span data-ttu-id="a2642-118">スパムと識別されたメール。</span><span class="sxs-lookup"><span data-stu-id="a2642-118">Mail identified as spam.</span></span> <span data-ttu-id="a2642-119">検疫済みメッセージは既定で表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2642-119">These quarantined messages are shown by default.</span></span>

- <span data-ttu-id="a2642-120">バルク メールと識別されたメール。</span><span class="sxs-lookup"><span data-stu-id="a2642-120">Mail identified as bulk mail.</span></span>

<span data-ttu-id="a2642-121">特定の検疫済みメッセージを見つけたら、メッセージをダブルクリックして詳細を表示し、処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="a2642-121">After you find a specific quarantined message, click the message to view details about it, and take actions.</span></span> <span data-ttu-id="a2642-122">メッセージは、メールボックスに解放、プレビュー、ダウンロード、または直ちに検疫から削除できます。</span><span class="sxs-lookup"><span data-stu-id="a2642-122">You can release the message to your mailbox, preview the message, download the message, or delete the message from quarantine immediately.</span></span>

> [!NOTE]
> <span data-ttu-id="a2642-123">他のユーザーに送信された検疫済みメッセージを処理するには、Office 365 の管理者アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="a2642-123">You must have admin permissions in Office 365 to work with quarantined messages that were sent to other users.</span></span>

## <a name="to-filter-and-find-quarantined-messages"></a><span data-ttu-id="a2642-124">検疫済みメッセージのフィルター処理と検索</span><span class="sxs-lookup"><span data-stu-id="a2642-124">To filter and find quarantined messages</span></span>

<span data-ttu-id="a2642-125">検疫されたアイテムが多数ある場合は、扱いやすい数に減らすためフィルター処理を行えます。</span><span class="sxs-lookup"><span data-stu-id="a2642-125">If you have a lot of quarantined items, you can reduce the number to a manageable set by filtering them.</span></span>

1. <span data-ttu-id="a2642-126">[**検疫**] ページで、[**迷惑メール**] 検閲メッセージと [**バルク メール**] 検閲メッセージのどちらを表示するのかを選択します。</span><span class="sxs-lookup"><span data-stu-id="a2642-126">On the **Quarantine** page, choose whether you want to view **spam** or **bulk** quarantined messages.</span></span>

2. <span data-ttu-id="a2642-127">[**結果の並べ替え基準**] で、該当するフィルターを設定して条件の任意の組み合わせを選びます (ここではワイルドカードを使用できません)。</span><span class="sxs-lookup"><span data-stu-id="a2642-127">Under **Sort results by**, choose any combination of conditions by setting the appropriate filter or filters (you can't use wildcards at this time).</span></span> <span data-ttu-id="a2642-128">選択できる条件はいくつかあり、次を含みます。</span><span class="sxs-lookup"><span data-stu-id="a2642-128">There are several conditions you can choose, including the following:</span></span>

   - <span data-ttu-id="a2642-129">[**メッセージ ID**] メッセージ ID がわかっている特定のメッセージを選択するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="a2642-129">**Message ID**: Use this to select a specific message when you know the message ID.</span></span>

     <span data-ttu-id="a2642-130">たとえば、目的のメッセージの送信者または宛先が組織内のユーザーで、宛先に届かない場合、メッセージ追跡を使用してメッセージを検索できます (「[セキュリティ/コンプライアンス センターのメッセージ追跡](message-trace-scc.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="a2642-130">For example, if a specific message is sent by, or intended for, a user in your organization, but it never reached its destination, you can search for the message by using a message trace (see [Message trace in the Security & Compliance Center](message-trace-scc.md)).</span></span> <span data-ttu-id="a2642-131">メッセージがメール フロー ルールと一致したため、またはスパムとして識別されたために検疫に送信されたことが判明した場合は、そのメッセージのメッセージ ID を指定することで、検疫内でそのメッセージを簡単に見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="a2642-131">If you discover that the message was sent to quarantine, perhaps because it matched a mail flow rule or was identified as spam, you can then easily find this message in quarantine by specifying its Message ID.</span></span> <span data-ttu-id="a2642-132">完全なメッセージ ID 文字列を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2642-132">Be sure to include the full Message ID string.</span></span> <span data-ttu-id="a2642-133">メッセージ ID には、次のように、山かっこ (\<\>) が含まれる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="a2642-133">This might include angle brackets (\<\>), for example:</span></span>

     `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`

   - <span data-ttu-id="a2642-134">[**送信者のメール アドレス**] 1 つの送信者のメール アドレスによってフィルター処理する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="a2642-134">**Sender email address**: Choose to filter by a single sender email address.</span></span>

   - <span data-ttu-id="a2642-135">[**受信者のメール アドレス**] 1 つの受信者のメール アドレスによってフィルター処理する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="a2642-135">**Recipient email address**: Choose to filter by a single recipient email address.</span></span>

   - <span data-ttu-id="a2642-136">[**件名**] 検索するメール アドレスの件名を入力します。</span><span class="sxs-lookup"><span data-stu-id="a2642-136">**Subject**: Enter the subject of an email address you want to find.</span></span>

   - <span data-ttu-id="a2642-137">[**日付範囲**] メッセージが検疫に送られた日付を使用してフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="a2642-137">**Date range**: You can choose to filter by the date the message was sent to quarantine.</span></span> <span data-ttu-id="a2642-138">日付または日付範囲を指定することができます (時間も指定できます)。</span><span class="sxs-lookup"><span data-stu-id="a2642-138">You can specify the date or a date range, including the time.</span></span>

   - <span data-ttu-id="a2642-139">[**有効期限**] 有効期限によってフィルター処理する場合は、[**高度なフィルター**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a2642-139">**Expiration date**: To filter by expiration date, choose **Advanced filter**.</span></span> <span data-ttu-id="a2642-140">24 時間以内 ([**今日**])、48 時間以内 ([**2 日以内**])、1 週間以内 ([**7 日以内**]) に検疫から削除されるメッセージを選択することができます。また、任意の期間を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="a2642-140">You can select messages that will be deleted from quarantine within the next 24 hours ( **Today**), within the next 48 hours ( **Next 2 days**), within the next week ( **Next 7 days**), or you can select a custom time interval.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="a2642-141">既定では、迷惑メール メッセージとバルク メール メッセージは、検疫に 30 日間保持されます。</span><span class="sxs-lookup"><span data-stu-id="a2642-141">By default, spam and bulk messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="a2642-142">ただし、この期間は設定可能なため、管理者が異なる検疫期間を設定している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a2642-142">However, this time period is configurable and your admin might have set a different quarantine retention period.</span></span> <span data-ttu-id="a2642-143">Office 365 で検疫からメッセージが削除されると、元に戻すことはできません。</span><span class="sxs-lookup"><span data-stu-id="a2642-143">When Office 365 deletes a message from quarantine, you can't get it back.</span></span>

## <a name="view-details-for-a-specific-message"></a><span data-ttu-id="a2642-144">特定のメッセージの詳細情報を表示する</span><span class="sxs-lookup"><span data-stu-id="a2642-144">View details for a specific message</span></span>

<span data-ttu-id="a2642-145">メッセージを選択すると、ページの右側にあるウィンドウにメッセージのプロパティの概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2642-145">After you select a message, you'll see a summary of the message properties in a pane on the right side of the page.</span></span>

- <span data-ttu-id="a2642-146">[**メッセージ ID**] メッセージの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="a2642-146">**Message ID**: The unique identifier for the message.</span></span>

- <span data-ttu-id="a2642-147">[**送信者のアドレス**] メッセージの送信者。</span><span class="sxs-lookup"><span data-stu-id="a2642-147">**Sender Address**: Who sent the message.</span></span>

- <span data-ttu-id="a2642-148">[**受信日**] メッセージを受信した日付。</span><span class="sxs-lookup"><span data-stu-id="a2642-148">**Received**: The date the message was received.</span></span>

- <span data-ttu-id="a2642-149">[**件名**] メッセージの件名欄のテキスト。</span><span class="sxs-lookup"><span data-stu-id="a2642-149">**Subject**: The text of the Subject line in the message.</span></span>

- <span data-ttu-id="a2642-150">[**検疫の理由**] メッセージが [**迷惑メール**] または [**バルク メール**] として識別されたかを表示します。</span><span class="sxs-lookup"><span data-stu-id="a2642-150">**Quarantine reason**: Shows if a message has been identified as **Spam** or **Bulk**.</span></span>

- <span data-ttu-id="a2642-151">[**有効期限**] 検疫からメッセージが削除される日付。</span><span class="sxs-lookup"><span data-stu-id="a2642-151">**Expires**: The date when the message will be deleted from quarantine.</span></span>

- <span data-ttu-id="a2642-152">[**解放済み**] メッセージが解放されたすべてのメール アドレス (ある場合)。</span><span class="sxs-lookup"><span data-stu-id="a2642-152">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="a2642-153">[**未解放**] メッセージがまだ解放されていないすべてのメール アドレス (ある場合)。</span><span class="sxs-lookup"><span data-stu-id="a2642-153">**Not yet released to**: All email addresses (if any) to which the message has not been released.</span></span> <span data-ttu-id="a2642-154">メッセージをメールボックスに解放する場合、[**解放**] を選択できます (メッセージの解放の詳細については、次のセクションを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="a2642-154">You can choose **Release** if you want to release the message to your mailbox (more about releasing messages in the next section).</span></span>

<span data-ttu-id="a2642-155">メッセージについてさらに詳しい情報を確認するには、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="a2642-155">You can get even more details about the message by choosing one of the following options:</span></span>

- <span data-ttu-id="a2642-156">[**メッセージ ヘッダーを表示**] これを選択するとメッセージ ヘッダー テキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2642-156">**View message header**: Choose this to see the message header text.</span></span> <span data-ttu-id="a2642-157">ヘッダーを詳しく分析するには、メッセージ ヘッダー テキストをクリップボードにコピーし、[**Microsoft メッセージ ヘッダー アナライザー**] を選択して、リモート接続アナライザーに移動します (このタスクを実行するために Office 365 を閉じたくない場合は、右クリックして [新しいタブで開く] を選択します)。</span><span class="sxs-lookup"><span data-stu-id="a2642-157">To analyze the header in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose Open in a new tab if you don't want to leave Office 365 to complete this task).</span></span> <span data-ttu-id="a2642-158">メッセージ ヘッダーを [Microsoft メッセージ ヘッダー アナライザー] セクションのページに貼り付け、[ヘッダーを分析] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a2642-158">Paste the message header onto the page in the Message Header Analyzer section, and choose Analyze headers.</span></span>

- <span data-ttu-id="a2642-159">[**メッセージのプレビュー**] メッセージ本文の raw バージョンまたは HTML バージョンを表示できます。</span><span class="sxs-lookup"><span data-stu-id="a2642-159">**Preview message**: Lets you see raw or HTML versions of the message body text.</span></span> <span data-ttu-id="a2642-160">HTML ビューでは、リンクは無効です。</span><span class="sxs-lookup"><span data-stu-id="a2642-160">In the HTML view, links are disabled.</span></span>

## <a name="manage-your-quarantined-messages"></a><span data-ttu-id="a2642-161">検疫されたメッセージを管理する</span><span class="sxs-lookup"><span data-stu-id="a2642-161">Manage your quarantined messages</span></span>

<span data-ttu-id="a2642-162">メッセージまたはメッセージのグループを選択した後に選択できる検疫内のメッセージを管理するための選択肢にはいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="a2642-162">After you select a message or group of messages, you have several options for managing messages in quarantine.</span></span>

- <span data-ttu-id="a2642-163">何もしない。</span><span class="sxs-lookup"><span data-stu-id="a2642-163">Do nothing.</span></span> <span data-ttu-id="a2642-164">何もしないことを選択すると、メッセージは有効期限日に Office 365 によって自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="a2642-164">If you choose to do nothing, the message will be deleted by Office 365 automatically upon expiration.</span></span> <span data-ttu-id="a2642-165">Office 365 によりメッセージが検疫から削除されると、元に戻すことはできないのでご注意ください。</span><span class="sxs-lookup"><span data-stu-id="a2642-165">Remember, when Office 365 deletes a message from quarantine, you can't get it back.</span></span>

- <span data-ttu-id="a2642-166">[**メッセージの解放**] メッセージがメールボックスに送信されるように、検疫されたメッセージ (または一連のメッセージ) を解放します。</span><span class="sxs-lookup"><span data-stu-id="a2642-166">**Release message**: Release a quarantined message (or set of messages) so that the message is sent to your mailbox.</span></span> <span data-ttu-id="a2642-167">メッセージを解放する際は、メッセージを分析のために Microsoft に報告するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="a2642-167">When you release a message, you have the option to report the message to Microsoft for analysis.</span></span>

    <span data-ttu-id="a2642-168">メッセージを報告する (「メッセージを誤検出として報告する」とも呼ばれます) オプションを選択すると、メッセージは Microsoft スパム分析チームに報告されます。</span><span class="sxs-lookup"><span data-stu-id="a2642-168">When you choose to report a message, also called reporting a message as a false positive, the message is reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="a2642-169">チームは誤検出メッセージを評価および分析し、分析結果に応じて、これらのメッセージの配信が許可されるようにサービス全体のスパム コンテンツ フィルター ルールを調整する場合があります。</span><span class="sxs-lookup"><span data-stu-id="a2642-169">The team evaluates and analyzes false positive messages, and, depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow these messages through.</span></span>

- <span data-ttu-id="a2642-170">[**検疫から削除**] メッセージはメールボックスに解放されずに、検疫から直ちに削除されます。</span><span class="sxs-lookup"><span data-stu-id="a2642-170">**Remove from quarantine**: Deletes the message immediately from quarantine without releasing the message to your mailbox.</span></span>
