---
title: セキュリティ/コンプライアンス センター のメッセージ追跡
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ コンプライアンス センターのメッセージ追跡&、メッセージがどうなったかを見つけ出します。
ms.openlocfilehash: c6e1f8f9280c84ab6ff6a1572d902ed1d4d4caa3
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827053"
---
# <a name="message-trace-in-the-security--compliance-center"></a><span data-ttu-id="f748d-103">セキュリティ/コンプライアンス センター のメッセージ追跡</span><span class="sxs-lookup"><span data-stu-id="f748d-103">Message trace in the Security & Compliance Center</span></span>

## <a name="message-trace-features"></a><span data-ttu-id="f748d-104">メッセージ追跡機能</span><span class="sxs-lookup"><span data-stu-id="f748d-104">Message trace features</span></span>

<span data-ttu-id="f748d-105">コンプライアンス センターのメッセージ追跡は&Exchange Online 組織を通過する電子メール メッセージをたみります。</span><span class="sxs-lookup"><span data-stu-id="f748d-105">Message trace in the Security & Compliance Center follows email messages as they travel through your Exchange Online organization.</span></span> <span data-ttu-id="f748d-106">メッセージがサービスによって受信、拒否、延期、配信されたかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f748d-106">You can determine if a message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="f748d-107">メッセージが最終的な状態になる前に、メッセージに行われた処理も表示します。</span><span class="sxs-lookup"><span data-stu-id="f748d-107">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="f748d-108">コンプライアンス センターのメッセージ追跡&、Exchange 管理センター (EAC) で利用できる元のメッセージ追跡に関して、機能が強化されています。</span><span class="sxs-lookup"><span data-stu-id="f748d-108">Message trace in the Security & Compliance Center improves upon the original message trace that was available in the Exchange admin center (EAC).</span></span> <span data-ttu-id="f748d-109">メッセージ追跡から情報を使用して、メッセージに対する変更点に関するユーザーの質問に効率的に回答し、メール フローの問題をトラブルシューティングし、ポリシーの変更を検証することができます。</span><span class="sxs-lookup"><span data-stu-id="f748d-109">You can use the information from message trace to efficiently answer user questions about what happened to messages, troubleshoot mail flow issues, and validate policy changes.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="f748d-110">メッセージトレースを行うには、組織管理、コンプライアンス管理、またはヘルプ デスクの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f748d-110">To do a message trace, you need to be a member of the Organization Management, Compliance Management or Help Desk role groups.</span></span> <span data-ttu-id="f748d-111">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f748d-111">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
>
> - <span data-ttu-id="f748d-112">結果に表示されるメッセージの最大数は、選択したレポートの種類によって異なります (詳細については、「 [レポートの種類を選択する」セクション](#choose-report-type) を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="f748d-112">The maximum number of messages that are displayed in the results depends on the report type you selected (see the [Choose report type](#choose-report-type) section for details).</span></span> <span data-ttu-id="f748d-113">Exchange Online PowerShell [の Get-HistoricalSearch](https://docs.microsoft.com/powershell/module/exchange/get-historicalsearch) コマンドレットまたはスタンドアロン EOP PowerShell は、すべてのメッセージを結果で返します。</span><span class="sxs-lookup"><span data-stu-id="f748d-113">The [Get-HistoricalSearch](https://docs.microsoft.com/powershell/module/exchange/get-historicalsearch) cmdlet in Exchange Online PowerShell or standalone EOP PowerShell returns all messages in the results.</span></span>

## <a name="open-message-trace"></a><span data-ttu-id="f748d-114">メッセージ追跡を開く</span><span class="sxs-lookup"><span data-stu-id="f748d-114">Open message trace</span></span>

1. <span data-ttu-id="f748d-115">[監視] & [インストール] を開きます <https://protection.office.com> 。</span><span class="sxs-lookup"><span data-stu-id="f748d-115">Open the Security & Compliance Center at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="f748d-116">メール **フローを展開し**、[メッセージ追跡] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f748d-116">Expand **Mail flow**, and then select **Message trace**.</span></span>

## <a name="message-trace-page"></a><span data-ttu-id="f748d-117">メッセージ追跡ページ</span><span class="sxs-lookup"><span data-stu-id="f748d-117">Message trace page</span></span>

<span data-ttu-id="f748d-118">ここから、[トレースの開始] ボタンをクリックして新しい既定 **のトレースを開始** できます。</span><span class="sxs-lookup"><span data-stu-id="f748d-118">From here you can start a new default trace by clicking on the **Start a trace** button.</span></span> <span data-ttu-id="f748d-119">これにより、過去 2 日間のすべての送信者と受信者のすべてのメッセージが検索されます。</span><span class="sxs-lookup"><span data-stu-id="f748d-119">This will search for all messages for all senders and recipients for the last two days.</span></span> <span data-ttu-id="f748d-120">または、利用可能なクエリ カテゴリの保存されたクエリを使用してそのクエリをその他で実行するか、独自のクエリの開始点として使用します。</span><span class="sxs-lookup"><span data-stu-id="f748d-120">Or you can use one of the stored queries from the available query categories and either run them as-is or use them as starting points for your own queries:</span></span>

- <span data-ttu-id="f748d-121">**既定のクエリ**: Microsoft 365 によって提供される組み込みのクエリ。</span><span class="sxs-lookup"><span data-stu-id="f748d-121">**Default queries**: Built-in queries provided by Microsoft 365.</span></span>

- <span data-ttu-id="f748d-122">**カスタム クエリ**: 将来使用できるように組織の管理者によって保存されたクエリ。</span><span class="sxs-lookup"><span data-stu-id="f748d-122">**Custom queries**: Queries saved by admins in your organization for future use.</span></span>

- <span data-ttu-id="f748d-123">**オート保存されたクエリ**: 最後に実行されたクエリを最後に 10 回。</span><span class="sxs-lookup"><span data-stu-id="f748d-123">**Autosaved queries**: The last ten most recently run queries.</span></span> <span data-ttu-id="f748d-124">この一覧では、前の箇下の位置から簡単に切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="f748d-124">This list makes it simple to pick up where you left off.</span></span>

<span data-ttu-id="f748d-125">また、このページは **提出した要求** 、およびダウンロード可能な場合はレポートを説明するダウンロードレポート セクションから構成されます。</span><span class="sxs-lookup"><span data-stu-id="f748d-125">Also on this page is a **Downloadable reports** section for the requests you've submitted, as well as the reports themselves when they're are available for download.</span></span>

## <a name="options-for-a-new-message-trace"></a><span data-ttu-id="f748d-126">新しいメッセージ追跡用のオプション</span><span class="sxs-lookup"><span data-stu-id="f748d-126">Options for a new message trace</span></span>

### <a name="filter-by-senders-and-recipients"></a><span data-ttu-id="f748d-127">送信者と受信者でフィルター処理</span><span class="sxs-lookup"><span data-stu-id="f748d-127">Filter by senders and recipients</span></span>

<span data-ttu-id="f748d-128">既定値は All **senders と All** recipients **ですが**、次のフィールドを使用して結果をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="f748d-128">The default values are **All senders** and **All recipients**, but you can use the following fields to filter the results:</span></span>

- <span data-ttu-id="f748d-129">**ユーザー別:** このフィールドをクリックして、組織から 1 人または複数の送信者を選択します。</span><span class="sxs-lookup"><span data-stu-id="f748d-129">**By these people**: Click in this field to select one or more senders from your organization.</span></span> <span data-ttu-id="f748d-130">また、検索ページの機能と同様に、名前の入力を始めにして、リスト内のアイテムを入力した内容によってフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="f748d-130">You can also start to type a name and the items in the list will be filtered by what you've typed, much like how a search page behaves.</span></span>

- <span data-ttu-id="f748d-131">**これらのユーザーに対**して: このフィールドをクリックして、組織内の 1 人または複数の受信者を選択します。</span><span class="sxs-lookup"><span data-stu-id="f748d-131">**To these people**: Click in this field to select one or more recipients in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="f748d-132">また、外部の送信者と受信者の電子メール アドレスを入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="f748d-132">You can also type the email addresses of external senders and recipients.</span></span> <span data-ttu-id="f748d-133">ワイルドカードがサポートされていますが (たとえば `*@contoso.com` 、)同じフィールドに同時に複数のワイルドカード エントリを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="f748d-133">Wildcards are supported (for example, `*@contoso.com`), but you can't use multiple wildcard entries in the same field at the same time.</span></span> <br/><br/> <span data-ttu-id="f748d-134">複数の送信者または受信者一覧をセミコロン ( ) で区切って貼り付ける場合 `;` 。</span><span class="sxs-lookup"><span data-stu-id="f748d-134">You can paste multiple senders or recipients lists separated by semicolons (`;`).</span></span> <span data-ttu-id="f748d-135">スペース ( ) `\s` の値、キャリッジ リゲージン ( `\r` ) または次の行 ( ) `\n` を返します。</span><span class="sxs-lookup"><span data-stu-id="f748d-135">spaces (`\s`), carriage returns (`\r`), or next lines (`\n`).</span></span>

### <a name="time-range"></a><span data-ttu-id="f748d-136">時間範囲</span><span class="sxs-lookup"><span data-stu-id="f748d-136">Time range</span></span>

<span data-ttu-id="f748d-137">既定値は **2 日です**が、最大 90 日間の日付/時間の範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f748d-137">The default value is **2 days**, but you can specify date/time ranges of up to 90 days.</span></span> <span data-ttu-id="f748d-138">日付/時刻の範囲を使用する場合は、次の問題を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="f748d-138">When you use date/time ranges, consider these issues:</span></span>

- <span data-ttu-id="f748d-139">既定では、タイムラインを使用してスラ **イダー ビュー** の時間範囲を選択します。</span><span class="sxs-lookup"><span data-stu-id="f748d-139">By default, you select the time range in **Slider** view using a time line.</span></span> <span data-ttu-id="f748d-140">表示された日付または時刻の設定のみを選択できます。</span><span class="sxs-lookup"><span data-stu-id="f748d-140">You can only select the day or time settings that are displayed.</span></span> <span data-ttu-id="f748d-141">間の値を選択しようとすると、表示される設定の末尾にスナップします。</span><span class="sxs-lookup"><span data-stu-id="f748d-141">Trying to select an in-between value will snap the start/end bubble to the nearest displayed setting.</span></span>

  ![セキュリティ センター内の新しいメッセージ追跡のスライダーの&時間範囲](../../media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

  <span data-ttu-id="f748d-143">カスタム ビューに切り替**えると、[開始**日] と [**End date\*\*\*\*終了**日] の値 (時刻を含む) を指定できます。また、日付/時刻の範囲として**タイム**ゾーンを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="f748d-143">But, you can also switch to **Custom** view where you can specify the **Start date** and **End date** values (including times), and you can also select the **Time zone** for the date/time range.</span></span> <span data-ttu-id="f748d-144">タイム ゾーン設定 **は、** クエリ入力とクエリ結果の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="f748d-144">Note that the **Time zone** setting applies to both your query inputs and your query results.</span></span>

  ![セキュリティ センター のセキュリティ センターの新しいメッセージ追跡のカスタム &時間範囲](../../media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

  <span data-ttu-id="f748d-146">10 日以内の場合は、結果を概要レポートとして即時 **に利用** できます。</span><span class="sxs-lookup"><span data-stu-id="f748d-146">For 10 days or less, the results are available instantly as a **Summary** report.</span></span> <span data-ttu-id="f748d-147">10 日を少し遅く指定した場合、結果はダウンロード可能な CSV **ファイル** (拡張概要レポートまたは拡張レポート) としてのみ利用可能なため **、遅延** されます。</span><span class="sxs-lookup"><span data-stu-id="f748d-147">If you specify a time range that's even slightly greater than 10 days, the results will be delayed as they are only available as a downloadable CSV file ( **Enhanced summary** or **Extended** reports).</span></span>

  <span data-ttu-id="f748d-148">別のレポートの種類の詳細については、このトピックの「 [レポートの種類を選択する](#choose-report-type) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f748d-148">For more information about the different report types, see the [Choose report type](#choose-report-type) section in this topic.</span></span>

  <span data-ttu-id="f748d-149">**注**: 拡張された概要レポートおよび拡張レポートは、アーカイブされたメッセージ追跡データを使用して準備されるもので、レポートがダウンロード可能になるまでに数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f748d-149">**Note**: Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available for download.</span></span> <span data-ttu-id="f748d-150">他の管理者が同時にレポート要求を送信したことによっては、キューに登録された要求の処理が開始されるまで時間が長くなることがあります。</span><span class="sxs-lookup"><span data-stu-id="f748d-150">Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before processing starts for your queued request.</span></span>

- <span data-ttu-id="f748d-151">スライダー **ビューにクエリを** 保存すると、相対的な時間範囲 (たとえば、現在から 3 日) を節約できます。</span><span class="sxs-lookup"><span data-stu-id="f748d-151">Saving a query in **Slider** view saves the relative time range (for example, 3 days from today).</span></span> <span data-ttu-id="f748d-152">カスタム ビューにクエリ **を保存** すると、絶対日付/時刻範囲 (たとえば、2018-05-06 13:00 ~ 2018-05-08 18:00) を保存します。</span><span class="sxs-lookup"><span data-stu-id="f748d-152">Saving a query in **Custom** view saves the absolute date/time range (for example, 2018-05-06 13:00 to 2018-05-08 18:00).</span></span>

### <a name="more-search-options"></a><span data-ttu-id="f748d-153">その他の検索オプション</span><span class="sxs-lookup"><span data-stu-id="f748d-153">More search options</span></span>

#### <a name="delivery-status"></a><span data-ttu-id="f748d-154">配信状態</span><span class="sxs-lookup"><span data-stu-id="f748d-154">Delivery status</span></span>

<span data-ttu-id="f748d-155">既定値 [All] は選択 **された** ままにするか、次のいずれかの値を選択して結果をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="f748d-155">You can leave the default value **All** selected, or you can select one of the following values to filter the results:</span></span>

- <span data-ttu-id="f748d-156">**配信済**み: メッセージは目的の宛先に正常に配信されました。</span><span class="sxs-lookup"><span data-stu-id="f748d-156">**Delivered**: The message was successfully delivered to the intended destination.</span></span>

- <span data-ttu-id="f748d-157">**保留**中: メッセージの配信を試行または再試行しています。</span><span class="sxs-lookup"><span data-stu-id="f748d-157">**Pending**: Delivery of the message is being attempted or re-attempted.</span></span>

- <span data-ttu-id="f748d-158">**[展開済**み]: 配布グループの受信者が展開され、その後グループの個々のメンバーに配信されました。</span><span class="sxs-lookup"><span data-stu-id="f748d-158">**Expanded**: A distribution group recipient was expanded before delivery to the individual members of the group.</span></span>

- <span data-ttu-id="f748d-159">**失敗**: メッセージは配信されませんでした。</span><span class="sxs-lookup"><span data-stu-id="f748d-159">**Failed**: The message was not delivered.</span></span>

- <span data-ttu-id="f748d-160">**検疫**済み: メッセージは検疫されました (スパム、バルク メール、フィッシングとして)。</span><span class="sxs-lookup"><span data-stu-id="f748d-160">**Quarantined**: The message was quarantined (as spam, bulk mail, or phishing).</span></span> <span data-ttu-id="f748d-161">詳細については [、EOP の検疫済み電子メール メッセージを参照してください](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="f748d-161">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

- <span data-ttu-id="f748d-162">**スパムとしてフィルター処理**しました。メッセージはスパムと特定され、拒否またはブロックされた (検疫されなかった) されました。</span><span class="sxs-lookup"><span data-stu-id="f748d-162">**Filtered as spam**: The message was identified spam, and was rejected or blocked (not quarantined).</span></span>

- <span data-ttu-id="f748d-163">**状態の取得:** メッセージは Microsoft 365 によって最近受信されたが、その他の状態データはまだ利用できません。</span><span class="sxs-lookup"><span data-stu-id="f748d-163">**Getting status:** The message was recently received by Microsoft 365, but no other status data is yet available.</span></span> <span data-ttu-id="f748d-164">数分後にチェックインしてください。</span><span class="sxs-lookup"><span data-stu-id="f748d-164">Check back in a few minutes.</span></span>

<span data-ttu-id="f748d-165">**注**: スパムとして**Pending、Quarantined、Filter\*\*\*\*Pending,\*\*\*\*の値を使用**できるのは、10 日未満です。</span><span class="sxs-lookup"><span data-stu-id="f748d-165">**Note**: The values **Pending,** **Quarantined**, and **Filter as spam** are only available for searches less than 10 days.</span></span> <span data-ttu-id="f748d-166">また、実際の配信状態と報告された配信状態の間に 5 分から 10 分の遅延が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="f748d-166">Also, there might be a 5 to 10 minute delay between the actual and reported delivery status.</span></span>

#### <a name="message-id"></a><span data-ttu-id="f748d-167">メッセージ ID</span><span class="sxs-lookup"><span data-stu-id="f748d-167">Message ID</span></span>

<span data-ttu-id="f748d-168">これは、メッセージ ヘッダーの **Message-ID:** ヘッダー フィールドに含まれているインターネット メッセージ ID (クライアント ID とも呼ばれる) です。</span><span class="sxs-lookup"><span data-stu-id="f748d-168">This is the internet message ID (also known as the Client ID) that's found in the **Message-ID:** header field in the message header.</span></span> <span data-ttu-id="f748d-169">ユーザーからこの値が返って、特定のメッセージを調査できます。</span><span class="sxs-lookup"><span data-stu-id="f748d-169">Users can give you this value to investigate specific messages.</span></span>

<span data-ttu-id="f748d-170">この値は、メッセージの有効期間全体にわたって不変です。</span><span class="sxs-lookup"><span data-stu-id="f748d-170">This value is constant for the lifetime of the message.</span></span> <span data-ttu-id="f748d-171">Microsoft 365 または Exchange で作成されたメッセージの場合、値は角かっこ ( ) を含む `<GUID@ServerFQDN>` 形式になります \< \> 。</span><span class="sxs-lookup"><span data-stu-id="f748d-171">For messages created in Microsoft 365 or Exchange, the value is in the format `<GUID@ServerFQDN>`, including the angle brackets (\< \>).</span></span> <span data-ttu-id="f748d-172">たとえば、`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>` などです。</span><span class="sxs-lookup"><span data-stu-id="f748d-172">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span> <span data-ttu-id="f748d-173">他のメッセージング システムは異なる構文や値を使用します。</span><span class="sxs-lookup"><span data-stu-id="f748d-173">Other messaging systems might use different syntax or values.</span></span> <span data-ttu-id="f748d-174">この値は一意であると見なされますが、すべてのメール システムがこの要件を実際に従う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f748d-174">This value is supposed to be unique, but not all email systems strictly follow this requirement.</span></span> <span data-ttu-id="f748d-175">**Message-ID: ヘッダー フィールドが**存在しないか、外部ソースからの受信メッセージ用に空白の場合は任意の値が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="f748d-175">If the **Message-ID:** header field doesn't exist or is blank for incoming messages from external sources, an arbitrary value is assigned.</span></span>

<span data-ttu-id="f748d-176">メッセージ ID を **使用して結果** をフィルター処理する場合は、角かっこを含む完全な文字列を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="f748d-176">When you use **Message ID** to filter the results, be sure to include the full string, including any angle brackets.</span></span>

#### <a name="direction"></a><span data-ttu-id="f748d-177">Direction</span><span class="sxs-lookup"><span data-stu-id="f748d-177">Direction</span></span>

<span data-ttu-id="f748d-178">既定値 [All] **は選択した** ままにするか、[ **受信** ] (組織内の受信者に送信されたメッセージ) または **[送信** ] (組織内のユーザーから送信されたメッセージ) を選択して結果をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="f748d-178">You can leave the default value **All** selected, or you can select **Inbound** (messages sent to recipients in your organization) or **Outbound** (messages sent from users in your organization) to filter the results.</span></span>

#### <a name="original-client-ip-address"></a><span data-ttu-id="f748d-179">元のクライアント IP アドレス</span><span class="sxs-lookup"><span data-stu-id="f748d-179">Original client IP address</span></span>

<span data-ttu-id="f748d-180">大量のスパムまたはマルウェアを送信しているハッキングされたコンピューターを調査するために、クライアント IP アドレスごとに結果をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="f748d-180">You can filer the results by client IP address to investigate hacked computers that are sending large amounts of spam or malware.</span></span> <span data-ttu-id="f748d-181">メッセージは複数の送信者から送信されたように見えるかもしねませんが、同じコンピューターがすべてのメッセージを生成している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f748d-181">Although the messages might appear to come from multiple senders, it's likely that the same computer is generating all of the messages.</span></span>

<span data-ttu-id="f748d-182">**注**: クライアント IP アドレス情報は 10 日間のみ利用可能で、拡張概要**レポートまたは拡張**レポート (ダウンロード可能な CSV ファイル) でのみ利用できます。 **Extended**</span><span class="sxs-lookup"><span data-stu-id="f748d-182">**Note**: The client IP address information is only available for 10 days, and is only available in the **Enhanced summary** or **Extended** reports (downloadable CSV files).</span></span>

### <a name="choose-report-type"></a><span data-ttu-id="f748d-183">レポートの種類を選</span><span class="sxs-lookup"><span data-stu-id="f748d-183">Choose report type</span></span>

<span data-ttu-id="f748d-184">使用できるレポートの種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f748d-184">The available report types are:</span></span>

- <span data-ttu-id="f748d-185">**概要**: 時間範囲が 10 日未満で、追加のフィルター処理オプションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="f748d-185">**Summary**: Available if the time range is less than 10 days, and requires no additional filtering options.</span></span> <span data-ttu-id="f748d-186">結果は、[検索] をクリックした直後に表示 **されます**。</span><span class="sxs-lookup"><span data-stu-id="f748d-186">The results are available almost immediately after you click **Search**.</span></span> <span data-ttu-id="f748d-187">このレポートで返される結果の最大数は 20000 です。</span><span class="sxs-lookup"><span data-stu-id="f748d-187">The report returns up to 20000 results.</span></span>

- <span data-ttu-id="f748d-188">**拡張概要**または**拡張**: これらのレポートはダウンロード可能な CSV ファイルとしてのみ利用可能で、時間範囲にかかわらず次のフィルター オプションの 1 つ以上が**必要です**。**これらの**ユーザーは、これらのユーザー、**これらの**ユーザー、またはメッセージ ID 。</span><span class="sxs-lookup"><span data-stu-id="f748d-188">**Enhanced summary** or **Extended**: These reports are only available as downloadable CSV files, and require one or more of the following filtering options regardless of the time range: **By these people**, **To these people**, or **Message ID**.</span></span> <span data-ttu-id="f748d-189">送信者または受信者にワイルドカードを使用できます (たとえば \* 、@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="f748d-189">You can use wildcards for the senders or the recipients (for example, \*@contoso.com).</span></span> <span data-ttu-id="f748d-190">拡張概要レポートは、最大 50000 の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="f748d-190">The Enhanced summary report returns up to 50000 results.</span></span> <span data-ttu-id="f748d-191">拡張レポートは最大 1000 の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="f748d-191">The Extended report returns up to 1000 results.</span></span>

<span data-ttu-id="f748d-192">**注**:</span><span class="sxs-lookup"><span data-stu-id="f748d-192">**Notes**:</span></span>

- <span data-ttu-id="f748d-193">拡張された概要レポートと拡張レポートは、アーカイブ済みメッセージの追跡データを使用して準備されます。レポートがダウンロード可能になるまでに数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f748d-193">Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available to download.</span></span> <span data-ttu-id="f748d-194">他の管理者が同時にレポート要求を送信した場合、キューに入れ済み要求の処理が開始されるまでに遅延が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="f748d-194">Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before your queued request starts to be processed.</span></span>

- <span data-ttu-id="f748d-195">日付/時刻の範囲に関する拡張概要レポートまたは拡張レポートを選択できますが、一般に、アーカイブされたデータの過去 4 時間は、これら 2 種類のレポートではまだ利用できません。</span><span class="sxs-lookup"><span data-stu-id="f748d-195">While you can select an Enhanced summary or Extended report for any date/time range, commonly the last four hours of archived data will not yet be available for these two types of reports.</span></span>

<span data-ttu-id="f748d-196">[ **次へ] をクリック**すると、選択したフィルター オプション、レポートの一意の (編集可能な) タイトル、メッセージの追跡が完了した (また、編集可能で、組織の承認済みドメインのいずれかに入れる) に表示される通知を受け取る電子メール アドレスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f748d-196">When you click **Next**, you're presented with a summary page that lists the filtering options that you selected, a unique (editable) title for the report, and the email address that receives the notification when the message trace completes (also editable, and must be in one of your organization's accepted domains).</span></span> <span data-ttu-id="f748d-197">[ **レポートの準備] を** クリックして、メッセージ追跡を送信します。</span><span class="sxs-lookup"><span data-stu-id="f748d-197">Click **Prepare report** to submit the message trace.</span></span> <span data-ttu-id="f748d-198">メイン メッセージ追跡 **ページでは** 、ダウンロード可能なレポート セクションにレポートの **状態が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="f748d-198">On the main **Message trace** page, you can see the status of the report in the **Downloadable reports** section.</span></span>

<span data-ttu-id="f748d-199">さまざまなレポートの種類で返される詳細については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f748d-199">For more information about the information that's returned in the different report types, see the next section.</span></span>

## <a name="message-trace-results"></a><span data-ttu-id="f748d-200">メッセージ追跡の結果</span><span class="sxs-lookup"><span data-stu-id="f748d-200">Message trace results</span></span>

<span data-ttu-id="f748d-201">レポートの種類が異なると、さまざまなレベルの情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="f748d-201">The different report types return different levels of information.</span></span> <span data-ttu-id="f748d-202">次のセクションでは、各レポートで使用可能な情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="f748d-202">The information that's available in the different reports is described in the following sections.</span></span>

### <a name="summary-report-output"></a><span data-ttu-id="f748d-203">概要レポートの出力</span><span class="sxs-lookup"><span data-stu-id="f748d-203">Summary report output</span></span>

<span data-ttu-id="f748d-204">メッセージ追跡を実行した後、結果がリスト表示され、昇順に並べ替えることができます (最新のもの順)。</span><span class="sxs-lookup"><span data-stu-id="f748d-204">After running the message trace, the results will be listed, sorted by descending date/time (most recent first).</span></span>

![セキュリティ グループ ポリシー コンプライアンス センターでのメッセージ追跡の&結果](../../media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

<span data-ttu-id="f748d-206">概要レポートには以下の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f748d-206">The summary report contains the following information:</span></span>

- <span data-ttu-id="f748d-207">**日付**: 構成済みの UTC タイム ゾーンを使用して、サービスがメッセージを受信した日時。</span><span class="sxs-lookup"><span data-stu-id="f748d-207">**Date**: The date and time at which the message was received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="f748d-208">**Sender:** 送信者の電子メール アドレス (*alias* @ *ドメイン*)。</span><span class="sxs-lookup"><span data-stu-id="f748d-208">**Sender**: The email address of the sender (*alias*@*domain*).</span></span>

- <span data-ttu-id="f748d-209">**Recipient:** 受信者の電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="f748d-209">**Recipient**: The email address of the recipient or recipients.</span></span> <span data-ttu-id="f748d-210">複数の受信者に送信されるメッセージの場合は、受信者ごとに 1 行に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f748d-210">For a message sent to multiple recipients, there's one line per recipient.</span></span> <span data-ttu-id="f748d-211">受信者が配布グループ、動的配布グループ、またはメールが有効なセキュリティ グループである場合、グループが最初の受信者になり、そのグループの各メンバーが別個の行に作成されます。</span><span class="sxs-lookup"><span data-stu-id="f748d-211">If the recipient is a distribution group, dynamic distribution group, or mail-enabled security group, the group will be the first recipient, and then each member of the group is on a separate line.</span></span>

- <span data-ttu-id="f748d-212">**Subject**: メッセージの件名フィールドの最初の 256 **文字** 。</span><span class="sxs-lookup"><span data-stu-id="f748d-212">**Subject**: The first 256 characters of the message's **Subject:** field.</span></span>

- <span data-ttu-id="f748d-213">**Status:** これらの値は、「配信の状態」 [セクションに記述](#delivery-status) されています。</span><span class="sxs-lookup"><span data-stu-id="f748d-213">**Status**: These values are described in the [Delivery status](#delivery-status) section.</span></span>

<span data-ttu-id="f748d-214">既定では、最初の 250 の結果が読み込まれ、使用可能です。</span><span class="sxs-lookup"><span data-stu-id="f748d-214">By default, the first 250 results are loaded and readily available.</span></span> <span data-ttu-id="f748d-215">スクロールダウンすると、次の結果のバッチが読み込まれるので、少し一時停止します。</span><span class="sxs-lookup"><span data-stu-id="f748d-215">When you scroll down, there's a slight pause as the next batch of results are loaded.</span></span> <span data-ttu-id="f748d-216">スクロールではなく、[すべて読み込む] を **クリック** すると、すべての結果を最大 10,000 まで読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="f748d-216">Instead of scrolling, you can click **Load all** to load all of the results up to a maximum of 10,000.</span></span>

<span data-ttu-id="f748d-217">列見出しをクリックすると、その列の値の昇順または下昇順で結果を並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="f748d-217">You can click on the column headers to sort the results by the values in that column in ascending or descending order.</span></span>

<span data-ttu-id="f748d-218">[結果をフィルター **処理] をクリック** すると、1 つまたは複数の列で結果をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="f748d-218">You can click **Filter results** to filter the results by one or more columns.</span></span>

<span data-ttu-id="f748d-219">[エクスポート結果] をクリックし、[**すべての**結果のエクスポート]、読み込まれた結果のエクスポート、または [**選択**したエクスポート] を選択**して**、1 行または複数行を選び、**結果をエクスポートできます**。</span><span class="sxs-lookup"><span data-stu-id="f748d-219">You can export the results after you've selected one or more rows by clicking **Export results** and then selecting **Export all results**, **Export loaded results**, or **Export selected**.</span></span>

#### <a name="find-related-records-for-this-message"></a><span data-ttu-id="f748d-220">このメッセージの関連レコードを検索する</span><span class="sxs-lookup"><span data-stu-id="f748d-220">Find related records for this message</span></span>

<span data-ttu-id="f748d-221">関連するメッセージ レコードは、同じメッセージ ID を共有するレコードです。</span><span class="sxs-lookup"><span data-stu-id="f748d-221">Related message records are records that shared the same Message ID.</span></span> <span data-ttu-id="f748d-222">2 人のユーザー間で送信されたメッセージが 1 つであっても、複数のレコードが生成される場合があります。</span><span class="sxs-lookup"><span data-stu-id="f748d-222">Remember, even a single message sent between two people can generate multiple records.</span></span> <span data-ttu-id="f748d-223">メッセージが配布グループの拡張、転送、メール フロー ルール (トランスポート ルールとも呼ばれる) などの影響を受けると、レコードの数が増加します。</span><span class="sxs-lookup"><span data-stu-id="f748d-223">The number of records increases when the message is affected by distribution group expansion, forwarding, mail flow rules (also known as transport rules), etc.</span></span>

<span data-ttu-id="f748d-224">行のチェック ボックスをオンにした後、表示される [**関連**情報] ボタンをクリックするか、このメッセージに関連するその他の**More options**オプションを選択して、メッセージの関連 ![ ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **するレコードを見つけ出します**。</span><span class="sxs-lookup"><span data-stu-id="f748d-224">After you select a row's check box, you can find related records for the message by clicking the **Find related** button that appears, or by selecting **More options** ![More](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **Find related records for this message**).</span></span>

<span data-ttu-id="f748d-225">メッセージ ID の詳細については、前述のメッセージ ID のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f748d-225">For more information about the Message ID, see the Message ID section earlier in this topic.</span></span>

#### <a name="message-trace-details"></a><span data-ttu-id="f748d-226">メッセージ追跡の詳細</span><span class="sxs-lookup"><span data-stu-id="f748d-226">Message trace details</span></span>

<span data-ttu-id="f748d-227">概要レポートの出力では、次のいずれかの方法を使用してメッセージに関する詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="f748d-227">In the summary report output, you can view details about a message by using either of the following methods:</span></span>

- <span data-ttu-id="f748d-228">行を選択します (チェック ボックス以外の行の任意の場所をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="f748d-228">Select the row (click anywhere in the row except the check box).</span></span>

- <span data-ttu-id="f748d-229">行のチェック ボックスをオンにし、[その他のオプションの **表示]** ![ ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f748d-229">Select the row's check box and click **More options** ![More](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **View message details**.</span></span>

   ![概要レポート メッセージの追跡結果の行をダブルクリックした後の詳細は、セキュリティ/コンプライアンス &詳細](../../media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

<span data-ttu-id="f748d-231">メッセージ追跡の詳細には、概要レポートにない次の追加情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f748d-231">The message trace details contain the following additional information that's not present in the summary report:</span></span>

- <span data-ttu-id="f748d-232">**メッセージ イベント**: このセクションには、サービスがメッセージに対して実行するアクションの分類に役立つ分類が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f748d-232">**Message events**: This section contains classifications that help categorize the actions that the service takes on messages.</span></span> <span data-ttu-id="f748d-233">**発生する可能性のあるイベントの一** 部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f748d-233">**Some of the more interesting events** that you might encounter are:</span></span>

  - <span data-ttu-id="f748d-234">**受信**: メッセージはサービスによって受信された。</span><span class="sxs-lookup"><span data-stu-id="f748d-234">**Receive**: The message was received by the service.</span></span>

  - <span data-ttu-id="f748d-235">**Send:** メッセージがサービスによって送信された。</span><span class="sxs-lookup"><span data-stu-id="f748d-235">**Send**: The message was sent by the service.</span></span>

  - <span data-ttu-id="f748d-236">**Fail:** メッセージ配信に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="f748d-236">**Fail**: The message failed to be delivered.</span></span>

  - <span data-ttu-id="f748d-237">**配信**: メッセージはメールボックスに配信されました。</span><span class="sxs-lookup"><span data-stu-id="f748d-237">**Deliver**: The message was delivered to a mailbox.</span></span>

  - <span data-ttu-id="f748d-238">**Expand**: 展開された配布グループにメッセージが送信されました。</span><span class="sxs-lookup"><span data-stu-id="f748d-238">**Expand**: The message was sent to a distribution group that was expanded.</span></span>

  - <span data-ttu-id="f748d-239">**転送**: コンテンツ変換、メッセージの受信者制限、またはエージェントが原因で、エラーが発生したメッセージに受信者が移動されました。</span><span class="sxs-lookup"><span data-stu-id="f748d-239">**Transfer**: Recipients were moved to a bifurcated message because of content conversion, message recipient limits, or agents.</span></span>

  - <span data-ttu-id="f748d-240">**Defer**: メッセージ配信が延期され、後で再試行される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f748d-240">**Defer**: The message delivery was postponed and might be re-attempted later.</span></span>

  - <span data-ttu-id="f748d-241">**Resolved**: メッセージは Active Directory 検索に基づいて受信者のアドレスにリダイレクトされました。</span><span class="sxs-lookup"><span data-stu-id="f748d-241">**Resolved**: The message was redirected to a new recipient address based on an Active Directory look up.</span></span> <span data-ttu-id="f748d-242">このイベントが発生した場合、メッセージ トレースの別の行に、メッセージの最終配信状態と併せて、元の受信者のアドレスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f748d-242">When this happens, the original recipient address is listed in a separate row in the message trace along with the final delivery status for the message.</span></span>

  <span data-ttu-id="f748d-243">注:</span><span class="sxs-lookup"><span data-stu-id="f748d-243">Notes:</span></span>

  - <span data-ttu-id="f748d-244">メッセージ追跡では、イベント処理が成功したメッセージが複数の **イベント** エントリを生成します。</span><span class="sxs-lookup"><span data-stu-id="f748d-244">An uneventful message that's successfully delivered will generate multiple **Event** entries in the message trace.</span></span>

  - <span data-ttu-id="f748d-245">この一覧は、まだ使用できないことを目的としていません。</span><span class="sxs-lookup"><span data-stu-id="f748d-245">This list is not meant to be exhaustive.</span></span> <span data-ttu-id="f748d-246">詳細なイベントの説明については、メッセージ追跡 [ログのイベントの種類を参照してください](https://docs.microsoft.com/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log)。</span><span class="sxs-lookup"><span data-stu-id="f748d-246">For descriptions of more events, see [Event types in the message tracking log](https://docs.microsoft.com/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log).</span></span> <span data-ttu-id="f748d-247">このリンクは、(Exchange Serverオンプレミスの Exchange) トピックであるためです。</span><span class="sxs-lookup"><span data-stu-id="f748d-247">Note that this link is an Exchange Server (on-premises Exchange) topic.</span></span>

- <span data-ttu-id="f748d-248">**詳細:** このセクションには、以下の詳細情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f748d-248">**More information**: This section contains the following details:</span></span>

  - <span data-ttu-id="f748d-249">**メッセージ ID**: この値については、このトピック [で前述したメッセージ ID](#message-id) に関するセクションで説明しています。</span><span class="sxs-lookup"><span data-stu-id="f748d-249">**Message ID**: This value is described in the [Message ID](#message-id) section earlier in this topic.</span></span> <span data-ttu-id="f748d-250">たとえば、`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>` などです。</span><span class="sxs-lookup"><span data-stu-id="f748d-250">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

  - <span data-ttu-id="f748d-251">**メッセージ サイズ**   添付ファイルを含むキロバイト (KB) 単位のメッセージのサイズ。</span><span class="sxs-lookup"><span data-stu-id="f748d-251">**Message size**</span></span>

  - <span data-ttu-id="f748d-252">**From IP:** The IP address of the computer that sent the message.</span><span class="sxs-lookup"><span data-stu-id="f748d-252">**From IP**: The IP address of the computer that sent the message.</span></span> <span data-ttu-id="f748d-253">Exchange Online から送信された送信メッセージの場合、この値は空白です。</span><span class="sxs-lookup"><span data-stu-id="f748d-253">For outbound messages sent from Exchange Online, this value is blank.</span></span>

  - <span data-ttu-id="f748d-254">**IP:** サービスがメッセージを配信しようとした IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="f748d-254">**To IP**: The IP address or addresses where the service attempted to deliver the message.</span></span> <span data-ttu-id="f748d-255">メッセージに複数の受信者が含される場合は、次の受信者が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f748d-255">If the message has multiple recipients, these are displayed.</span></span> <span data-ttu-id="f748d-256">Exchange Online に送信された受信メッセージの場合、この値は空白です。</span><span class="sxs-lookup"><span data-stu-id="f748d-256">For inbound messages sent to Exchange Online, this value is blank.</span></span>

### <a name="enhanced-summary-reports"></a><span data-ttu-id="f748d-257">拡張概要レポート</span><span class="sxs-lookup"><span data-stu-id="f748d-257">Enhanced summary reports</span></span>

<span data-ttu-id="f748d-258">選択したメッセージ追跡の開始レポート セクションには、拡張 **された概要レポート** が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f748d-258">Available (completed) Enhanced summary reports are available in the **Downloadable reports** section at the beginning message trace.</span></span> <span data-ttu-id="f748d-259">このレポートでは次の情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f748d-259">The following information is available in the report:</span></span>

- <span data-ttu-id="f748d-260">**origin_timestamp:** <sup>\*</sup> 構成済みの UTC タイム ゾーンを使用して、サービスがメッセージを最初に受信した日時。</span><span class="sxs-lookup"><span data-stu-id="f748d-260">**origin_timestamp**<sup>\*</sup>: The date and time when the message was initially received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="f748d-261">**sender_address**: 送信者の電子メール アドレス ( エイリア*ス* @ *ドメイン*)。</span><span class="sxs-lookup"><span data-stu-id="f748d-261">**sender_address**: The sender's email address (*alias*@*domain*).</span></span>

- <span data-ttu-id="f748d-262">**Recipient_status:** 受信者へのメッセージの配信状態です。</span><span class="sxs-lookup"><span data-stu-id="f748d-262">**Recipient_status**: The status of the delivery of the message to the recipient.</span></span> <span data-ttu-id="f748d-263">メッセージが複数の受信者に送信された場合は、すべての受信者と対応する状態が次の形式で \<*email address*\> 表示されます。 ## \<*status*\></span><span class="sxs-lookup"><span data-stu-id="f748d-263">If the message was sent to multiple recipients, it will show all the recipients and the corresponding status for each, in the format: \<*email address*\>##\<*status*\>.</span></span> <span data-ttu-id="f748d-264">たとえば、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="f748d-264">For example:</span></span>

  - <span data-ttu-id="f748d-265">**##Receive、送信** は、メッセージがサービスによって受信され、指定された宛先に送信されたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="f748d-265">**##Receive, Send** means the message was received by the service and was sent to the intended destination.</span></span>

  - <span data-ttu-id="f748d-266">**##Receive Fail は** メッセージがサービスによって受信されたが、指定された宛先に配信できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="f748d-266">**##Receive, Fail** means the message was received by the service but delivery to the intended destination failed.</span></span>

  - <span data-ttu-id="f748d-267">**##Receive は、** メッセージがサービスによって受信され、受信者のメールボックスに配信されたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="f748d-267">**##Receive, Deliver** means the message was received by the service and was delivered to the recipient's mailbox.</span></span>

- <span data-ttu-id="f748d-268">**message_subject:** メッセージの [件名] フィールドの最初の 256 **文字** 。</span><span class="sxs-lookup"><span data-stu-id="f748d-268">**message_subject**: The first 256 characters of the message's **Subject** field.</span></span>

- <span data-ttu-id="f748d-269">**total_bytes:** 添付ファイルを含むバイト単位のメッセージのサイズ。</span><span class="sxs-lookup"><span data-stu-id="f748d-269">**total_bytes**: The size of the message in bytes, including attachments.</span></span>

- <span data-ttu-id="f748d-270">**message_id**: この値は、このトピック [で前述したメッセージ ID](#message-id) に関するセクションで説明されています。</span><span class="sxs-lookup"><span data-stu-id="f748d-270">**message_id**: This value is described in the [Message ID](#message-id) section earlier in this topic.</span></span> <span data-ttu-id="f748d-271">たとえば、`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>` などです。</span><span class="sxs-lookup"><span data-stu-id="f748d-271">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

- <span data-ttu-id="f748d-272">**network_message_id:** メッセージのすべてのコピーで分割や配布グループの展開により作成される可能性がある一意のメッセージ ID。</span><span class="sxs-lookup"><span data-stu-id="f748d-272">**network_message_id**: A unique message ID value that persists across all copies of the message that might be created due to bifurcation or distribution group expansion.</span></span> <span data-ttu-id="f748d-273">値の例は `1341ac7b13fb42ab4d4408cf7f55890f` .</span><span class="sxs-lookup"><span data-stu-id="f748d-273">An example value is `1341ac7b13fb42ab4d4408cf7f55890f`.</span></span>

- <span data-ttu-id="f748d-274">**original_client_ip:** 送信者のクライアントの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="f748d-274">**original_client_ip**: The IP address of the sender's client.</span></span>

- <span data-ttu-id="f748d-275">**directionality:** メッセージが組織への受信 (1) か、組織からの送信 (2) メッセージであるかを示します。</span><span class="sxs-lookup"><span data-stu-id="f748d-275">**directionality**: Indicates whether the message was sent inbound (1) to your organization, or whether it was sent outbound (2) from your organization.</span></span>

- <span data-ttu-id="f748d-276">**connector_id:** 送信元コネクタまたは送信先コネクタの名前です。</span><span class="sxs-lookup"><span data-stu-id="f748d-276">**connector_id**: The name of the source or destination connector.</span></span> <span data-ttu-id="f748d-277">Exchange Online のコネクタの詳細については、「Exchange Online の [コネクタを使ったメール フローの構成」Officeしてください](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。</span><span class="sxs-lookup"><span data-stu-id="f748d-277">For more information about connectors in Exchange Online, see [Configure mail flow using connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

- <span data-ttu-id="f748d-278">**delivery_priority:** <sup>\*</sup> メッセージが送信された情報が高**Low**、**低**、または標準優先度の**どうか**。</span><span class="sxs-lookup"><span data-stu-id="f748d-278">**delivery_priority**<sup>\*</sup>: Whether the message was sent with **High**, **Low**, or **Normal** priority.</span></span>

<span data-ttu-id="f748d-279"><sup>\*</sup>これらのプロパティは、拡張された概要レポートでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f748d-279"><sup>\*</sup>These properties are only available in Enhanced summary reports.</span></span>

### <a name="extended-reports"></a><span data-ttu-id="f748d-280">拡張レポート</span><span class="sxs-lookup"><span data-stu-id="f748d-280">Extended reports</span></span>

<span data-ttu-id="f748d-281">拡張レポートは、メッセージ追跡の開始 **時点でダウンロード可能** なレポート セクションで確認できます。</span><span class="sxs-lookup"><span data-stu-id="f748d-281">Available (completed) Extended reports are available in the **Downloadable reports** section at the beginning of message trace.</span></span> <span data-ttu-id="f748d-282">拡張概要レポートのすべての情報は **(origin_timestamp** および delivery_priority ) を例外として拡張レポート **で使用できます**。</span><span class="sxs-lookup"><span data-stu-id="f748d-282">Virtually all of the information from an Enhanced summary report is available in an Extended report (with the exception of **origin_timestamp** and **delivery_priority**).</span></span> <span data-ttu-id="f748d-283">以下の追加情報は拡張レポートでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f748d-283">The following additional information is only available in an Extended report:</span></span>

- <span data-ttu-id="f748d-284">**client_ip:** メッセージを送信した電子メール サーバーまたはメッセージング クライアントの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="f748d-284">**client_ip**: The IP address of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="f748d-285">**client_hostname:** メッセージを送信した電子メール サーバーまたはメッセージング クライアントのホスト名または FQDN です。</span><span class="sxs-lookup"><span data-stu-id="f748d-285">**client_hostname**: The host name or FQDN of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="f748d-286">**server_ip:** 送信元サーバーまたは送信先サーバーの IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="f748d-286">**server_ip**: The IP address of the source or destination server.</span></span>

- <span data-ttu-id="f748d-287">**server_hostname:** 送信先サーバーのホスト名または FQDN。</span><span class="sxs-lookup"><span data-stu-id="f748d-287">**server_hostname**: The host name or FQDN of the destination server.</span></span>

- <span data-ttu-id="f748d-288">**source_context**: ソース フィールドに関連付 **けられている追加情報** です。</span><span class="sxs-lookup"><span data-stu-id="f748d-288">**source_context**: Extra information associated with the **source** field.</span></span> <span data-ttu-id="f748d-289">たとえば、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="f748d-289">For example:</span></span>

  - `Protocol Filter Agent`

  - `3489061114359050000`

- <span data-ttu-id="f748d-290">**ソース**:イベントを処理する Exchange Online コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="f748d-290">**source**: The Exchange Online component that's responsible for the event.</span></span> <span data-ttu-id="f748d-291">たとえば、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="f748d-291">For example:</span></span>

  - `AGENT`

  - `MAILBOXRULE`

  - `SMTP`

- <span data-ttu-id="f748d-292">**event_id**: These correspond to the **Message event** values that are explained in the Find related records for [this message](#find-related-records-for-this-message) section.</span><span class="sxs-lookup"><span data-stu-id="f748d-292">**event_id**: These correspond to the **Message event** values that are explained in the [Find related records for this message](#find-related-records-for-this-message) section.</span></span>

- <span data-ttu-id="f748d-293">**internal_message_id:** 現在メッセージを処理している Exchange Online サーバーによって割り当てられたメッセージ識別子。</span><span class="sxs-lookup"><span data-stu-id="f748d-293">**internal_message_id**: A message identifier that's assigned by the Exchange Online server that's currently processing the message.</span></span>

- <span data-ttu-id="f748d-294">**recipient_address:** メッセージ受信者の電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="f748d-294">**recipient_address**: The email addresses of the message's recipients.</span></span> <span data-ttu-id="f748d-295">複数の電子メール アドレスがある場合は、セミコロン (;) で区切られます。</span><span class="sxs-lookup"><span data-stu-id="f748d-295">Multiple email addresses are separated by the semicolon character (;).</span></span>

- <span data-ttu-id="f748d-296">**recipient_count:** メッセージ内の受信者の合計数。</span><span class="sxs-lookup"><span data-stu-id="f748d-296">**recipient_count**: The total number of recipients in the message.</span></span>

- <span data-ttu-id="f748d-297">**related_recipient_address**: " `EXPAND` " で `REDIRECT` 、、および `RESOLVE` イベントと共に使用され、メッセージに関連付けられている他の受信者の電子メール アドレスを表示します。</span><span class="sxs-lookup"><span data-stu-id="f748d-297">**related_recipient_address**: Used with `EXPAND`, `REDIRECT`, and `RESOLVE` events to display other recipient email addresses that are associated with the message.</span></span>

- <span data-ttu-id="f748d-298">**reference:** このフィールドには、特定の種類のイベントについての追加情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f748d-298">**reference**: This field contains additional information for specific types of events.</span></span> <span data-ttu-id="f748d-299">たとえば、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="f748d-299">For example:</span></span>

  - <span data-ttu-id="f748d-300">**DSN:** レポート リンクが含まれます。これは、この **イベントの後** に DSN が生成された場合に、関連する配信状態通知 (DSN、配信不能レポート、NDR、またはバウンス メッセージとも呼ばれる) の message_id 値です。</span><span class="sxs-lookup"><span data-stu-id="f748d-300">**DSN**: Contains the report link, which is the **message_id** value of the associated delivery status notification (also known as a DSN, non-delivery report, NDR, or bounce message) if a DSN is generated subsequent to this event.</span></span> <span data-ttu-id="f748d-301">これが DSN メッセージの場合、このフィールドには、DSN **message_id** 生成された元のメッセージの値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f748d-301">If this is a DSN message, this field contains the **message_id** value of the original message that the DSN was generated for.</span></span>

  - <span data-ttu-id="f748d-302">**EXPAND**: 関連 **メッセージrelated_recipient_address** の値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f748d-302">**EXPAND**: Contains the **related_recipient_address** value of the related messages.</span></span>

  - <span data-ttu-id="f748d-303">**Receive**:他の **プロセスによってmessage_id** によって生成された場合、関連するメッセージの受信トレイ値を含む RECEIVE 。受信トレイ ルールなどがあります。</span><span class="sxs-lookup"><span data-stu-id="f748d-303">**RECEIVE**: Might contain the **message_id** value of the related message if the message was generated by other processes (for example, Inbox rules).</span></span>

  - <span data-ttu-id="f748d-304">**SEND:** すべての DSN **internal_message_id** の値を含む。</span><span class="sxs-lookup"><span data-stu-id="f748d-304">**SEND**: Contains the **internal_message_id** value of any DSN messages.</span></span>

  - <span data-ttu-id="f748d-305">**TRANSFER:\*\*\*\*会議internal_message_id**されているメッセージの値 (たとえば、コンテンツ変換、メッセージの受信者の制限、エージェント単位) が格納されます。</span><span class="sxs-lookup"><span data-stu-id="f748d-305">**TRANSFER**: Contains the **internal_message_id** value of the message that's being forked (for example, by content conversion, message recipient limits, or agents).</span></span>

  - <span data-ttu-id="f748d-306">**MAILBOXRULE:\*\*\*\*受信internal_message_id**生成メッセージを生成する原因となってき、受信メッセージの値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f748d-306">**MAILBOXRULE**: Contains the **internal_message_id** value of the inbound message that caused the Inbox rule to generate the outbound message.</span></span>

    <span data-ttu-id="f748d-307">その他の種類のイベントの場合、このフィールドは通常空白です。</span><span class="sxs-lookup"><span data-stu-id="f748d-307">For other types of events, this field is usually blank.</span></span>

- <span data-ttu-id="f748d-308">**return_path:** メッセージを送信した MAIL FROM コマンドで **指定された** リターン電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="f748d-308">**return_path**: The return email address specified by the **MAIL FROM** command that sent the message.</span></span> <span data-ttu-id="f748d-309">このフィールドが空であることはありませんが、空の送信者アドレス値が表されている場合があります `<>` 。</span><span class="sxs-lookup"><span data-stu-id="f748d-309">Although this field is never empty, it can have the null sender address value represented as `<>`.</span></span>

- <span data-ttu-id="f748d-310">**message_info:** メッセージに関する追加情報です。</span><span class="sxs-lookup"><span data-stu-id="f748d-310">**message_info**: Additional information about the message.</span></span> <span data-ttu-id="f748d-311">たとえば、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="f748d-311">For example:</span></span>

  - <span data-ttu-id="f748d-312">メッセージの発生日時 (UTC とイベント `DELIVER` の日時 `SEND` )。</span><span class="sxs-lookup"><span data-stu-id="f748d-312">The message origination date-time in UTC for `DELIVER` and `SEND` events.</span></span> <span data-ttu-id="f748d-313">発生日時は、そのメッセージが最初に Exchange Online 組織に入力した日時です。</span><span class="sxs-lookup"><span data-stu-id="f748d-313">The origination date-time is the time when the message first entered the Exchange Online organization.</span></span> <span data-ttu-id="f748d-314">UTC の日付と時刻は、ISO 8601 の日付と時刻形式で表されます。 `yyyy-mm-ddThh:mm:ss.fffZ` ここで `yyyy` 、= year, `mm` = month, = day は時間コンポーネントの開始を示 `dd` `T` し `hh` 、= 時間 `mm` 、= 分 `ss` 、= 秒、 `fff` 秒の `Z` `Zulu` 小数部、およびその 2 つ目の区切り文字 。UTC を指定する別の方法です。</span><span class="sxs-lookup"><span data-stu-id="f748d-314">The UTC date-time is represented in the ISO 8601 date-time format: `yyyy-mm-ddThh:mm:ss.fffZ`, where `yyyy` = year, `mm` = month, `dd` = day, `T` indicates the beginning of the time component, `hh` = hour, `mm` = minute, `ss` = second, `fff` = fractions of a second, and `Z` signifies `Zulu`, which is another way to denote UTC.</span></span>

  - <span data-ttu-id="f748d-315">認証エラー。</span><span class="sxs-lookup"><span data-stu-id="f748d-315">Authentication errors.</span></span> <span data-ttu-id="f748d-316">たとえば、認証エラーが発生すると `11a` 、使用された認証の種類と種類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f748d-316">For example, you might see the value `11a` and the type of authentication that was used when the authentication error occurred.</span></span>

- <span data-ttu-id="f748d-317">**tenant_id**: Exchange Online 組織を表す GUID 値です (例 `39238e87-b5ab-4ef6-a559-af54c6b07b42` :</span><span class="sxs-lookup"><span data-stu-id="f748d-317">**tenant_id**: A GUID value that represents the Exchange Online organization (for example, `39238e87-b5ab-4ef6-a559-af54c6b07b42`).</span></span>

- <span data-ttu-id="f748d-318">**original_server_ip**: 元のサーバーの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="f748d-318">**original_server_ip**: The IP address of the original server.</span></span>

- <span data-ttu-id="f748d-319">**custom_data**: 特定のイベントの種類に関連するデータが格納されています。</span><span class="sxs-lookup"><span data-stu-id="f748d-319">**custom_data**: Contains data related to specific event types.</span></span> <span data-ttu-id="f748d-320">詳細については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f748d-320">For more information, see the following sections.</span></span>

#### <a name="custom_data-values"></a><span data-ttu-id="f748d-321">custom_data値</span><span class="sxs-lookup"><span data-stu-id="f748d-321">custom_data values</span></span>

<span data-ttu-id="f748d-322">イベント **custom_data** フィールドは `AGENTINFO` 、さまざまな Exchange Online エージェントによってメッセージ処理の詳細を記録するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f748d-322">The **custom_data** field for an `AGENTINFO` event is used by a variety of Exchange Online agents to log message processing details.</span></span> <span data-ttu-id="f748d-323">一般的に役に示すいくつかのエージェントについては、以下のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="f748d-323">Some of the more interesting agents are described in the following sections.</span></span>

#### <a name="spam-filter-agent"></a><span data-ttu-id="f748d-324">スパム フィルター エージェント</span><span class="sxs-lookup"><span data-stu-id="f748d-324">Spam filter agent</span></span>

<span data-ttu-id="f748d-325">最初 **custom_data** の値は `S:SFA` 、スパム フィルター エージェントの値です。</span><span class="sxs-lookup"><span data-stu-id="f748d-325">A **custom_data** value that starts with `S:SFA` is from the spam filter agent.</span></span> <span data-ttu-id="f748d-326">キーの詳細を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="f748d-326">The key details are described in the following table:</span></span>

****

|<span data-ttu-id="f748d-327">値</span><span class="sxs-lookup"><span data-stu-id="f748d-327">Value</span></span>|<span data-ttu-id="f748d-328">説明</span><span class="sxs-lookup"><span data-stu-id="f748d-328">Description</span></span>|
|---|---|
|`SFV=NSPM`|<span data-ttu-id="f748d-329">メッセージがスパムではないとしてマークされ、意図された受信者に送信されました。</span><span class="sxs-lookup"><span data-stu-id="f748d-329">The message was marked as non-spam and was sent to the intended recipients.</span></span>|
|`SFV=SPM`|<span data-ttu-id="f748d-330">メッセージは、スパム対策フィルター (コンテンツ フィルターとも呼ばれる) によってスパムとしてマークされました。</span><span class="sxs-lookup"><span data-stu-id="f748d-330">The message was marked as spam by anti-spam filtering (also known as content filtering).</span></span>|
|`SFV=BLK`|<span data-ttu-id="f748d-331">ブロックする差出人から発信されたメッセージであるため、フィルター処理が省略され、メッセージはブロックされました。</span><span class="sxs-lookup"><span data-stu-id="f748d-331">Filtering was skipped and the message was blocked because it originated from a blocked sender.</span></span>|
|`SFV=SKS`|<span data-ttu-id="f748d-332">スパム対策フィルター処理の処理前に、メッセージがスパムとしてマークされました。</span><span class="sxs-lookup"><span data-stu-id="f748d-332">The message was marked as spam prior to being processed by anti-spam filtering.</span></span> <span data-ttu-id="f748d-333">これには、メッセージを自動的にスパムメールとしてマークし、他のすべてのフィルター処理を省略するトランスポート ルールに一致するメッセージが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f748d-333">This includes messages where the message matched a mail flow rule (also known as a transport rule) to automatically mark it as spam and bypass all additional filtering.</span></span>|
|`SCL=<number>`|<span data-ttu-id="f748d-334">さまざまな SCL の値とその意味の詳細については、「[Spam Confidence Level](spam-confidence-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f748d-334">For more information about the different SCL values and what they mean, see [Spam confidence levels](spam-confidence-levels.md).</span></span>|
|`PCL=<number>`|<span data-ttu-id="f748d-p155">メッセージの Phishing Confidence Level (PCL) 値。これらの値は、「[Spam Confidence Level](spam-confidence-levels.md)」に記載されている SCL 値と同様に解釈できます。  </span><span class="sxs-lookup"><span data-stu-id="f748d-p155">The Phishing Confidence Level (PCL) value of the message. These can be interpreted the same way as the SCL values documented in [Spam confidence levels](spam-confidence-levels.md).</span></span>|
|`DI=SB`|<span data-ttu-id="f748d-337">メッセージの送信者はブロックされました。</span><span class="sxs-lookup"><span data-stu-id="f748d-337">The sender of the message was blocked.</span></span>|
|`DI=SQ`|<span data-ttu-id="f748d-338">メッセージは検疫されました。</span><span class="sxs-lookup"><span data-stu-id="f748d-338">The message was quarantined.</span></span>|
|`DI=SD`|<span data-ttu-id="f748d-339">メッセージは削除されました。</span><span class="sxs-lookup"><span data-stu-id="f748d-339">The message was deleted.</span></span>|
|`DI=SJ`|<span data-ttu-id="f748d-340">メッセージは受信者の迷惑メール フォルダーに送信されました。</span><span class="sxs-lookup"><span data-stu-id="f748d-340">The message was sent to the recipient's Junk Email folder.</span></span>|
|`DI=SN`|<span data-ttu-id="f748d-341">メッセージは通常の送信用の配信プールを通じて送信されました。</span><span class="sxs-lookup"><span data-stu-id="f748d-341">The message was routed through the normal outbound delivery pool.</span></span>|
|`DI=SO`|<span data-ttu-id="f748d-342">メッセージがより危険度の高い配信プールを経由してルーティングされました。</span><span class="sxs-lookup"><span data-stu-id="f748d-342">The message was routed through the higher risk delivery pool.</span></span> <span data-ttu-id="f748d-343">詳細については、「[送信メッセージにおける危険度の高い配信プール](high-risk-delivery-pool-for-outbound-messages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f748d-343">For more information, see [High-risk delivery pool for outbound messages](high-risk-delivery-pool-for-outbound-messages.md).</span></span>|
|`SFS=[a]|SFS=[b]`|<span data-ttu-id="f748d-344">これはスパム ルールが一致したことを示します。</span><span class="sxs-lookup"><span data-stu-id="f748d-344">This denotes that spam rules were matched.</span></span>|
|`IPV=CAL`|<span data-ttu-id="f748d-345">このメッセージの IP アドレスは接続フィルターの IP 許可一覧に指定されているため、スパム フィルターの通過を許可されました。</span><span class="sxs-lookup"><span data-stu-id="f748d-345">The message was allowed through the spam filters because the IP address was specified in an IP Allow list in the connection filter.</span></span>|
|`H=<EHLOstring>`|<span data-ttu-id="f748d-346">接続メール サーバーの HELO または EHLO 文字列。</span><span class="sxs-lookup"><span data-stu-id="f748d-346">The HELO or EHLO string of the connecting email server.</span></span>|
|`PTR=<ReverseDNS>`|<span data-ttu-id="f748d-347">送信元の IP アドレスの PTR レコード (逆引き DNS アドレスともいう) です。</span><span class="sxs-lookup"><span data-stu-id="f748d-347">The PTR record of the sending IP address, also known as the reverse DNS address.</span></span>|
|

<span data-ttu-id="f748d-348">スパムに **custom_data** されたメッセージの値の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f748d-348">An example **custom_data** value for a message that's filtered for spam like this:</span></span>

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a><span data-ttu-id="f748d-349">マルウェア フィルター エージェント</span><span class="sxs-lookup"><span data-stu-id="f748d-349">Malware filter agent</span></span>

<span data-ttu-id="f748d-350">マルウェア **custom_data** 基始値 `S:AMA` の取得が通用です。</span><span class="sxs-lookup"><span data-stu-id="f748d-350">A **custom_data** value that starts with `S:AMA` is from the malware filter agent.</span></span> <span data-ttu-id="f748d-351">キーの詳細を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="f748d-351">The key details are described in the following table:</span></span>

****

|<span data-ttu-id="f748d-352">値</span><span class="sxs-lookup"><span data-stu-id="f748d-352">Value</span></span>|<span data-ttu-id="f748d-353">説明</span><span class="sxs-lookup"><span data-stu-id="f748d-353">Description</span></span>|
|---|---|
|<span data-ttu-id="f748d-354">`AMA=SUM|v=1|` または `AMA=EV|v=1`</span><span class="sxs-lookup"><span data-stu-id="f748d-354">`AMA=SUM|v=1|` or `AMA=EV|v=1`</span></span>|<span data-ttu-id="f748d-355">このメッセージは、マルウェアが含まれていると判断されました。</span><span class="sxs-lookup"><span data-stu-id="f748d-355">The message was determined to contain malware.</span></span> <span data-ttu-id="f748d-356">`SUM` は、マルウェアがいくつでも検出された可能性を示します。</span><span class="sxs-lookup"><span data-stu-id="f748d-356">`SUM` indicates the malware could've been detected by any number of engines.</span></span> <span data-ttu-id="f748d-357">`EV` は、特定のエンジンによってマルウェアが検出されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="f748d-357">`EV` indicates the malware was detected by a specific engine.</span></span> <span data-ttu-id="f748d-358">エンジンでマルウェアが検出された場合は、後続のアクションをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="f748d-358">When malware is detected by an engine this triggers the subsequent actions.</span></span>|
|`Action=r`|<span data-ttu-id="f748d-359">メッセージは置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="f748d-359">The message was replaced.</span></span>|
|`Action=p`|<span data-ttu-id="f748d-360">メッセージはバイパスされました。</span><span class="sxs-lookup"><span data-stu-id="f748d-360">The message was bypassed.</span></span>|
|`Action=d`|<span data-ttu-id="f748d-361">メッセージは延期されました。</span><span class="sxs-lookup"><span data-stu-id="f748d-361">The message was deferred.</span></span>|
|`Action=s`|<span data-ttu-id="f748d-362">メッセージは削除されました。</span><span class="sxs-lookup"><span data-stu-id="f748d-362">The message was deleted.</span></span>|
|`Action=st`|<span data-ttu-id="f748d-363">メッセージはバイパスされました。</span><span class="sxs-lookup"><span data-stu-id="f748d-363">The message was bypassed.</span></span>|
|`Action=sy`|<span data-ttu-id="f748d-364">メッセージはバイパスされました。</span><span class="sxs-lookup"><span data-stu-id="f748d-364">The message was bypassed.</span></span>|
|`Action=ni`|<span data-ttu-id="f748d-365">メッセージは拒否されました。</span><span class="sxs-lookup"><span data-stu-id="f748d-365">The message was rejected.</span></span>|
|`Action=ne`|<span data-ttu-id="f748d-366">メッセージは拒否されました。</span><span class="sxs-lookup"><span data-stu-id="f748d-366">The message was rejected.</span></span>|
|`Action=b`|<span data-ttu-id="f748d-367">メッセージはブロックされました。</span><span class="sxs-lookup"><span data-stu-id="f748d-367">The message was blocked.</span></span>|
|`Name=<malware>`|<span data-ttu-id="f748d-368">検出されたマルウェアの名前。</span><span class="sxs-lookup"><span data-stu-id="f748d-368">The name of the malware that was detected.</span></span>|
|`File=<filename>`|<span data-ttu-id="f748d-369">マルウェアを含むファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="f748d-369">The name of the file that contained the malware.</span></span>|
|

<span data-ttu-id="f748d-370">マルウェアを **custom_data** を含むメッセージの値の例は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f748d-370">An example **custom_data** value for a message that contains malware looks like this:</span></span>

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a><span data-ttu-id="f748d-371">トランスポート ルール エージェント</span><span class="sxs-lookup"><span data-stu-id="f748d-371">Transport Rule agent</span></span>

<span data-ttu-id="f748d-372">メール **custom_data** ルール (トランスポート ルール `S:TRA` とも呼ばれる) のトランスポート ルール エージェントから始めつ役割の値です。</span><span class="sxs-lookup"><span data-stu-id="f748d-372">A **custom_data** value that starts with`S:TRA` is from the Transport Rule agent for mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="f748d-373">キーの詳細を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="f748d-373">The key details are described in the following table:</span></span>

****

|<span data-ttu-id="f748d-374">値</span><span class="sxs-lookup"><span data-stu-id="f748d-374">Value</span></span>|<span data-ttu-id="f748d-375">説明</span><span class="sxs-lookup"><span data-stu-id="f748d-375">Description</span></span>|
|---|---|
|`ETR|ruleId=<guid>`|<span data-ttu-id="f748d-376">一致したルールの ID。</span><span class="sxs-lookup"><span data-stu-id="f748d-376">The rule ID that was matched.</span></span>|
|`St=<datetime>`|<span data-ttu-id="f748d-377">ルールの一致が発生した日時 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="f748d-377">The date and time in UTC when the rule match occurred.</span></span>|
|`Action=<ActionDefinition>`|<span data-ttu-id="f748d-378">適用されたアクション。</span><span class="sxs-lookup"><span data-stu-id="f748d-378">The action that was applied.</span></span> <span data-ttu-id="f748d-379">使用可能なアクションの一覧については、「Exchange Online 内 [」の「メール フロー ルールのアクション」を参照してください](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。</span><span class="sxs-lookup"><span data-stu-id="f748d-379">For a list of available actions, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>|
|`Mode=<Mode>`|<span data-ttu-id="f748d-380">ルールのモード。</span><span class="sxs-lookup"><span data-stu-id="f748d-380">The mode of the rule.</span></span> <span data-ttu-id="f748d-381">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f748d-381">Valid values are:</span></span><ul><li><span data-ttu-id="f748d-382">**Enforce**: All actions on the rule will be enforced.</span><span class="sxs-lookup"><span data-stu-id="f748d-382">**Enforce**: All actions on the rule will be enforced.</span></span></li><li><span data-ttu-id="f748d-383">**ポリシー ヒントありのテスト:** ポリシー ヒント アクションが送信されますが、他の強制アクションは実行されません。</span><span class="sxs-lookup"><span data-stu-id="f748d-383">**Test with Policy Tips:**: Any Policy Tip actions will be sent, but other enforcement actions will not be acted on.</span></span></li><li><span data-ttu-id="f748d-384">**ポリシー ヒントなしのテスト**: アクションはログ ファイルにリストされますが、送信者には通知されず、強制アクションは実行されません。</span><span class="sxs-lookup"><span data-stu-id="f748d-384">**Test without Policy Tips**: Actions will be listed in a log file, but senders will not be notified in any way, and enforcement actions will not be acted on.</span></span></li></ul>|
|

<span data-ttu-id="f748d-385">メール **フロー custom_data** 条件に一致するメッセージの値の例は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f748d-385">An example **custom_data** value for a messages that matches the conditions of a mail flow rule looks like this:</span></span>

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`
