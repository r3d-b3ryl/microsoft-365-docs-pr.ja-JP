---
title: セキュリティ/コンプライアンス センター のメッセージ追跡
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ/コンプライアンス センターの&トレースを使用して、メッセージに何が起こったかを確認できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1ce26f7a6cdad15019e2b40eb6f8746e5723d4f0
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290659"
---
# <a name="message-trace-in-the-security--compliance-center"></a><span data-ttu-id="27c5d-103">セキュリティ/コンプライアンス センター のメッセージ追跡</span><span class="sxs-lookup"><span data-stu-id="27c5d-103">Message trace in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="27c5d-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="27c5d-104">**Applies to**</span></span>
- [<span data-ttu-id="27c5d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="27c5d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="27c5d-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="27c5d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="27c5d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="27c5d-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

## <a name="message-trace-features"></a><span data-ttu-id="27c5d-108">メッセージ追跡機能</span><span class="sxs-lookup"><span data-stu-id="27c5d-108">Message trace features</span></span>

<span data-ttu-id="27c5d-109">セキュリティ/コンプライアンス センターのメッセージ追跡&、Exchange Online 組織を経由する電子メール メッセージに従います。</span><span class="sxs-lookup"><span data-stu-id="27c5d-109">Message trace in the Security & Compliance Center follows email messages as they travel through your Exchange Online organization.</span></span> <span data-ttu-id="27c5d-110">メッセージがサービスによって受信、拒否、延期、または配信されたかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-110">You can determine if a message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="27c5d-111">メッセージが最終的な状態になる前に、メッセージに行われた処理も表示します。</span><span class="sxs-lookup"><span data-stu-id="27c5d-111">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="27c5d-112">セキュリティ/コンプライアンス センター&トレースにより、Exchange 管理センター (EAC) で使用できる元のメッセージ追跡が向上します。</span><span class="sxs-lookup"><span data-stu-id="27c5d-112">Message trace in the Security & Compliance Center improves upon the original message trace that was available in the Exchange admin center (EAC).</span></span> <span data-ttu-id="27c5d-113">メッセージ追跡からの情報を使用して、メッセージに何が起こったかについてのユーザーの質問に効率的に回答し、メール フローの問題をトラブルシューティングし、ポリシーの変更を検証できます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-113">You can use the information from message trace to efficiently answer user questions about what happened to messages, troubleshoot mail flow issues, and validate policy changes.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="27c5d-114">メッセージ追跡を行うには、組織の管理、コンプライアンス管理、またはヘルプ デスクの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="27c5d-114">To do a message trace, you need to be a member of the Organization Management, Compliance Management or Help Desk role groups.</span></span> <span data-ttu-id="27c5d-115">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27c5d-115">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
>
> - <span data-ttu-id="27c5d-116">結果に表示されるメッセージの最大数は、選択したレポートの種類によって異なります (詳細については、「レポートの種類の選択 [」セクションを](#choose-report-type) 参照してください)。</span><span class="sxs-lookup"><span data-stu-id="27c5d-116">The maximum number of messages that are displayed in the results depends on the report type you selected (see the [Choose report type](#choose-report-type) section for details).</span></span> <span data-ttu-id="27c5d-117">Exchange Online PowerShell またはスタンドアロンの EOP PowerShell の [Get-HistoricalSearch](https://docs.microsoft.com/powershell/module/exchange/get-historicalsearch) コマンドレットは、結果のすべてのメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="27c5d-117">The [Get-HistoricalSearch](https://docs.microsoft.com/powershell/module/exchange/get-historicalsearch) cmdlet in Exchange Online PowerShell or standalone EOP PowerShell returns all messages in the results.</span></span>

## <a name="open-message-trace"></a><span data-ttu-id="27c5d-118">メッセージ追跡を開く</span><span class="sxs-lookup"><span data-stu-id="27c5d-118">Open message trace</span></span>

1. <span data-ttu-id="27c5d-119">セキュリティ/コンプライアンス センター&開きます <https://protection.office.com> 。</span><span class="sxs-lookup"><span data-stu-id="27c5d-119">Open the Security & Compliance Center at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="27c5d-120">[メール **フロー] を展開** し、[メッセージの追跡 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="27c5d-120">Expand **Mail flow**, and then select **Message trace**.</span></span>

## <a name="message-trace-page"></a><span data-ttu-id="27c5d-121">メッセージ追跡ページ</span><span class="sxs-lookup"><span data-stu-id="27c5d-121">Message trace page</span></span>

<span data-ttu-id="27c5d-122">ここから、[トレースの開始] ボタンをクリックして、新しい既定 **のトレースを開始** できます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-122">From here you can start a new default trace by clicking on the **Start a trace** button.</span></span> <span data-ttu-id="27c5d-123">これにより、最近 2 日間のすべての送信者と受信者のすべてのメッセージが検索されます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-123">This will search for all messages for all senders and recipients for the last two days.</span></span> <span data-ttu-id="27c5d-124">または、使用可能なクエリ カテゴリの保存されたクエリのいずれかを使用して、それらを現在の形式で実行するか、独自のクエリの開始点として使用することができます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-124">Or you can use one of the stored queries from the available query categories and either run them as-is or use them as starting points for your own queries:</span></span>

- <span data-ttu-id="27c5d-125">**既定のクエリ**: Microsoft 365 によって提供される組み込みクエリ。</span><span class="sxs-lookup"><span data-stu-id="27c5d-125">**Default queries**: Built-in queries provided by Microsoft 365.</span></span>

- <span data-ttu-id="27c5d-126">**カスタム クエリ**: 組織の管理者が将来使用するために保存したクエリ。</span><span class="sxs-lookup"><span data-stu-id="27c5d-126">**Custom queries**: Queries saved by admins in your organization for future use.</span></span>

- <span data-ttu-id="27c5d-127">**自動保存されたクエリ**: 最近実行された最後の 10 個のクエリ。</span><span class="sxs-lookup"><span data-stu-id="27c5d-127">**Autosaved queries**: The last ten most recently run queries.</span></span> <span data-ttu-id="27c5d-128">この一覧を使用すると、左側から簡単に選択できます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-128">This list makes it simple to pick up where you left off.</span></span>

<span data-ttu-id="27c5d-129">また、このページには、提出した要求のダウンロード可能なレポート セクションと、ダウンロード可能なレポートがある場合のレポート自体も含まれる。</span><span class="sxs-lookup"><span data-stu-id="27c5d-129">Also on this page is a **Downloadable reports** section for the requests you've submitted, as well as the reports themselves when they're are available for download.</span></span>

## <a name="options-for-a-new-message-trace"></a><span data-ttu-id="27c5d-130">新しいメッセージ追跡のオプション</span><span class="sxs-lookup"><span data-stu-id="27c5d-130">Options for a new message trace</span></span>

### <a name="filter-by-senders-and-recipients"></a><span data-ttu-id="27c5d-131">送信者と受信者によるフィルター処理</span><span class="sxs-lookup"><span data-stu-id="27c5d-131">Filter by senders and recipients</span></span>

<span data-ttu-id="27c5d-132">既定値は [ **すべての送信者]** および **[すべての** 受信者] ですが、次のフィールドを使用して結果をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-132">The default values are **All senders** and **All recipients**, but you can use the following fields to filter the results:</span></span>

- <span data-ttu-id="27c5d-133">**By these people**: Click in this field to select one or more senders from your organization.</span><span class="sxs-lookup"><span data-stu-id="27c5d-133">**By these people**: Click in this field to select one or more senders from your organization.</span></span> <span data-ttu-id="27c5d-134">また、名前の入力を開始すると、検索ページの動作と同様に、リスト内のアイテムが入力した値でフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-134">You can also start to type a name and the items in the list will be filtered by what you've typed, much like how a search page behaves.</span></span>

- <span data-ttu-id="27c5d-135">**To these people**: Click in this field to select one or more recipients in your organization.</span><span class="sxs-lookup"><span data-stu-id="27c5d-135">**To these people**: Click in this field to select one or more recipients in your organization.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="27c5d-136">外部の送信者と受信者の電子メール アドレスを入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-136">You can also type the email addresses of external senders and recipients.</span></span> <span data-ttu-id="27c5d-137">ワイルドカードはサポートされますが (たとえば)、同じフィールドで同時に複数のワイルドカード エントリ `*@contoso.com` を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="27c5d-137">Wildcards are supported (for example, `*@contoso.com`), but you can't use multiple wildcard entries in the same field at the same time.</span></span>
>
> - <span data-ttu-id="27c5d-138">複数の送信者または受信者の一覧をセミコロン () で区切って貼り付けできます `;` 。</span><span class="sxs-lookup"><span data-stu-id="27c5d-138">You can paste multiple senders or recipients lists separated by semicolons (`;`).</span></span> <span data-ttu-id="27c5d-139">スペース ( `\s` )、キャリッジ リターン ( `\r` )、または次の行 ( `\n` )。</span><span class="sxs-lookup"><span data-stu-id="27c5d-139">spaces (`\s`), carriage returns (`\r`), or next lines (`\n`).</span></span>

### <a name="time-range"></a><span data-ttu-id="27c5d-140">時間範囲</span><span class="sxs-lookup"><span data-stu-id="27c5d-140">Time range</span></span>

<span data-ttu-id="27c5d-141">既定値は **2 日ですが**、最大 90 日間の日付/時刻の範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-141">The default value is **2 days**, but you can specify date/time ranges of up to 90 days.</span></span> <span data-ttu-id="27c5d-142">日付/時刻の範囲を使用する場合は、次の問題を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="27c5d-142">When you use date/time ranges, consider these issues:</span></span>

- <span data-ttu-id="27c5d-143">既定では、スライダー ビューでタイム ラインを **使用して** 時間範囲を選択します。</span><span class="sxs-lookup"><span data-stu-id="27c5d-143">By default, you select the time range in **Slider** view using a time line.</span></span> <span data-ttu-id="27c5d-144">表示される日または時刻の設定のみを選択できます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-144">You can only select the day or time settings that are displayed.</span></span> <span data-ttu-id="27c5d-145">間隔内の値を選択すると、開始/終了バブルが最も近い表示設定にスナップされます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-145">Trying to select an in-between value will snap the start/end bubble to the nearest displayed setting.</span></span>

  ![セキュリティ/コンプライアンス センターの新しいメッセージ トレース&範囲](../../media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

  <span data-ttu-id="27c5d-147">ただし、カスタム ビューに切り替えて、開始日と終了日の値(時刻を含む) を指定し、日付/時刻範囲のタイム ゾーンを選択することもできます。 </span><span class="sxs-lookup"><span data-stu-id="27c5d-147">But, you can also switch to **Custom** view where you can specify the **Start date** and **End date** values (including times), and you can also select the **Time zone** for the date/time range.</span></span> <span data-ttu-id="27c5d-148">タイム ゾーンの **設定は** 、クエリ入力とクエリ結果の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-148">Note that the **Time zone** setting applies to both your query inputs and your query results.</span></span>

  ![セキュリティ/コンプライアンス センターの新しいメッセージ追跡のカスタム&範囲](../../media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

  <span data-ttu-id="27c5d-150">10 日以下の場合、結果は概要レポートとしてすぐに **利用** できます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-150">For 10 days or less, the results are available instantly as a **Summary** report.</span></span> <span data-ttu-id="27c5d-151">10 日を少し超える時間範囲を指定した場合、ダウンロード可能な CSV ファイル **(拡張** 概要レポートまたは拡張レポート) としてのみ利用可能な結果が遅延します。</span><span class="sxs-lookup"><span data-stu-id="27c5d-151">If you specify a time range that's even slightly greater than 10 days, the results will be delayed as they are only available as a downloadable CSV file ( **Enhanced summary** or **Extended** reports).</span></span>

  <span data-ttu-id="27c5d-152">さまざまなレポートの種類の詳細については、この記事の「レポートの種類の [選択」](#choose-report-type) セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="27c5d-152">For more information about the different report types, see the [Choose report type](#choose-report-type) section in this article.</span></span>

  > [!NOTE]
  > <span data-ttu-id="27c5d-153">拡張概要レポートと拡張レポートは、アーカイブされたメッセージ 追跡データを使用して準備され、レポートをダウンロードできるまで最大数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="27c5d-153">Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available for download.</span></span> <span data-ttu-id="27c5d-154">同時にレポート要求を送信した他の管理者の数によっては、キューに入っている要求の処理が開始される前に遅延が発生する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="27c5d-154">Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before processing starts for your queued request.</span></span>

- <span data-ttu-id="27c5d-155">スライダー ビューにクエリ **を保存** すると、相対時間範囲 (今日から 3 日など) が保存されます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-155">Saving a query in **Slider** view saves the relative time range (for example, 3 days from today).</span></span> <span data-ttu-id="27c5d-156">カスタム ビューにクエリを保存すると、絶対日付/時刻範囲が保存されます (たとえば、2018-05-06 13:00 ~ 2018-05-08 18:00)。</span><span class="sxs-lookup"><span data-stu-id="27c5d-156">Saving a query in **Custom** view saves the absolute date/time range (for example, 2018-05-06 13:00 to 2018-05-08 18:00).</span></span>

### <a name="more-search-options"></a><span data-ttu-id="27c5d-157">その他の検索オプション</span><span class="sxs-lookup"><span data-stu-id="27c5d-157">More search options</span></span>

#### <a name="delivery-status"></a><span data-ttu-id="27c5d-158">配信状態</span><span class="sxs-lookup"><span data-stu-id="27c5d-158">Delivery status</span></span>

<span data-ttu-id="27c5d-159">既定値の [すべて] **を選択** したままにするか、次のいずれかの値を選択して結果をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-159">You can leave the default value **All** selected, or you can select one of the following values to filter the results:</span></span>

- <span data-ttu-id="27c5d-160">**配信**: メッセージは意図した宛先に正常に配信されました。</span><span class="sxs-lookup"><span data-stu-id="27c5d-160">**Delivered**: The message was successfully delivered to the intended destination.</span></span>

- <span data-ttu-id="27c5d-161">**保留中**: メッセージの配信が試行または再試行されています。</span><span class="sxs-lookup"><span data-stu-id="27c5d-161">**Pending**: Delivery of the message is being attempted or re-attempted.</span></span>

- <span data-ttu-id="27c5d-162">**展開:** 配布グループの受信者が、グループの個々のメンバーに配信される前に展開されました。</span><span class="sxs-lookup"><span data-stu-id="27c5d-162">**Expanded**: A distribution group recipient was expanded before delivery to the individual members of the group.</span></span>

- <span data-ttu-id="27c5d-163">**Failed**: メッセージが配信されません。</span><span class="sxs-lookup"><span data-stu-id="27c5d-163">**Failed**: The message was not delivered.</span></span>

- <span data-ttu-id="27c5d-164">**検疫済** み : メッセージが検疫されました (スパム、バルク メール、またはフィッシングとして)。</span><span class="sxs-lookup"><span data-stu-id="27c5d-164">**Quarantined**: The message was quarantined (as spam, bulk mail, or phishing).</span></span> <span data-ttu-id="27c5d-165">詳細については [、「EOP での検疫済み電子メール メッセージ」を参照してください](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="27c5d-165">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

- <span data-ttu-id="27c5d-166">**スパムとしてフィルター** 処理 : メッセージはスパムとして識別され、拒否またはブロックされました (検疫されていない)。</span><span class="sxs-lookup"><span data-stu-id="27c5d-166">**Filtered as spam**: The message was identified spam, and was rejected or blocked (not quarantined).</span></span>

- <span data-ttu-id="27c5d-167">**状態の取得:** メッセージは Microsoft 365 によって最近受信されましたが、他の状態データはまだ利用できません。</span><span class="sxs-lookup"><span data-stu-id="27c5d-167">**Getting status:** The message was recently received by Microsoft 365, but no other status data is yet available.</span></span> <span data-ttu-id="27c5d-168">数分後に確認してください。</span><span class="sxs-lookup"><span data-stu-id="27c5d-168">Check back in a few minutes.</span></span>

> [!NOTE]
> <span data-ttu-id="27c5d-169">[保留中 **]、[\*\*\*\*検疫済み**]、および [スパムとしてフィルター処理] の値は、10 日未満の検索でのみ使用できます。 </span><span class="sxs-lookup"><span data-stu-id="27c5d-169">The values **Pending,** **Quarantined**, and **Filter as spam** are only available for searches less than 10 days.</span></span> <span data-ttu-id="27c5d-170">また、実際の配信状態と報告された配信状態の間に 5 ~ 10 分の遅延が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="27c5d-170">Also, there might be a 5 to 10 minute delay between the actual and reported delivery status.</span></span>

#### <a name="message-id"></a><span data-ttu-id="27c5d-171">メッセージ ID</span><span class="sxs-lookup"><span data-stu-id="27c5d-171">Message ID</span></span>

<span data-ttu-id="27c5d-172">これは、メッセージ ヘッダーの **Message-ID:** ヘッダー フィールドにあるインターネット メッセージ ID (クライアント ID とも呼ばれる) です。</span><span class="sxs-lookup"><span data-stu-id="27c5d-172">This is the internet message ID (also known as the Client ID) that's found in the **Message-ID:** header field in the message header.</span></span> <span data-ttu-id="27c5d-173">ユーザーは、特定のメッセージを調査するためにこの値を提供できます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-173">Users can give you this value to investigate specific messages.</span></span>

<span data-ttu-id="27c5d-174">この値は、メッセージの有効期間全体にわたって不変です。</span><span class="sxs-lookup"><span data-stu-id="27c5d-174">This value is constant for the lifetime of the message.</span></span> <span data-ttu-id="27c5d-175">Microsoft 365 または Exchange で作成されたメッセージの場合、値の形式は、角かっこ ( ) `<GUID@ServerFQDN>` を含みます \< \> 。</span><span class="sxs-lookup"><span data-stu-id="27c5d-175">For messages created in Microsoft 365 or Exchange, the value is in the format `<GUID@ServerFQDN>`, including the angle brackets (\< \>).</span></span> <span data-ttu-id="27c5d-176">たとえば、`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>` などです。</span><span class="sxs-lookup"><span data-stu-id="27c5d-176">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span> <span data-ttu-id="27c5d-177">他のメッセージング システムでは、異なる構文または値を使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="27c5d-177">Other messaging systems might use different syntax or values.</span></span> <span data-ttu-id="27c5d-178">この値は一意の値と想定されますが、すべての電子メール システムが厳密にこの要件に従うとは言えなっています。</span><span class="sxs-lookup"><span data-stu-id="27c5d-178">This value is supposed to be unique, but not all email systems strictly follow this requirement.</span></span> <span data-ttu-id="27c5d-179">**Message-ID:** ヘッダー フィールドが存在しない場合、または外部ソースからの受信メッセージに対して空白の場合は、任意の値が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-179">If the **Message-ID:** header field doesn't exist or is blank for incoming messages from external sources, an arbitrary value is assigned.</span></span>

<span data-ttu-id="27c5d-180">メッセージ ID を **使用して結果** をフィルター処理する場合は、必ず完全な文字列 (任意の角かっこを含む) を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="27c5d-180">When you use **Message ID** to filter the results, be sure to include the full string, including any angle brackets.</span></span>

#### <a name="direction"></a><span data-ttu-id="27c5d-181">Direction</span><span class="sxs-lookup"><span data-stu-id="27c5d-181">Direction</span></span>

<span data-ttu-id="27c5d-182">既定値の [すべて]を選択のままにするか、受信 **(組織内** の受信者に送信されるメッセージ) または送信 **(組織内** のユーザーから送信されたメッセージ) を選択して結果をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-182">You can leave the default value **All** selected, or you can select **Inbound** (messages sent to recipients in your organization) or **Outbound** (messages sent from users in your organization) to filter the results.</span></span>

#### <a name="original-client-ip-address"></a><span data-ttu-id="27c5d-183">元のクライアント IP アドレス</span><span class="sxs-lookup"><span data-stu-id="27c5d-183">Original client IP address</span></span>

<span data-ttu-id="27c5d-184">クライアント IP アドレスで結果を報告し、大量のスパムやマルウェアを送信しているハッキングされたコンピューターを調査できます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-184">You can filer the results by client IP address to investigate hacked computers that are sending large amounts of spam or malware.</span></span> <span data-ttu-id="27c5d-185">メッセージは複数の送信者から送信されたと思える場合でも、同じコンピューターがすべてのメッセージを生成している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="27c5d-185">Although the messages might appear to come from multiple senders, it's likely that the same computer is generating all of the messages.</span></span>

> [!NOTE]
> <span data-ttu-id="27c5d-186">クライアント IP アドレス情報は 10 日間のみ利用可能で、拡張概要レポートまたは拡張レポート(ダウンロード可能な CSV ファイル) でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-186">The client IP address information is only available for 10 days, and is only available in the **Enhanced summary** or **Extended** reports (downloadable CSV files).</span></span>

### <a name="choose-report-type"></a><span data-ttu-id="27c5d-187">レポートの種類を選択する</span><span class="sxs-lookup"><span data-stu-id="27c5d-187">Choose report type</span></span>

<span data-ttu-id="27c5d-188">使用可能なレポートの種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="27c5d-188">The available report types are:</span></span>

- <span data-ttu-id="27c5d-189">**概要**: 時間範囲が 10 日未満で、追加のフィルター オプションが必要ない場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-189">**Summary**: Available if the time range is less than 10 days, and requires no additional filtering options.</span></span> <span data-ttu-id="27c5d-190">検索結果は、[検索] をクリックした直後に **表示されます**。</span><span class="sxs-lookup"><span data-stu-id="27c5d-190">The results are available almost immediately after you click **Search**.</span></span> <span data-ttu-id="27c5d-191">レポートは最大 20,000 件の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="27c5d-191">The report returns up to 20000 results.</span></span>

- <span data-ttu-id="27c5d-192">**拡張概要** または拡張 **:** これらのレポートは、ダウンロード可能な CSV ファイルとしてのみ使用できます。時間の範囲に関係なく、次の 1 つ以上のフィルターオプションが必要 **です**。 </span><span class="sxs-lookup"><span data-stu-id="27c5d-192">**Enhanced summary** or **Extended**: These reports are only available as downloadable CSV files, and require one or more of the following filtering options regardless of the time range: **By these people**, **To these people**, or **Message ID**.</span></span> <span data-ttu-id="27c5d-193">送信者または受信者に対してワイルドカードを使用できます \* (@contoso.com など)。</span><span class="sxs-lookup"><span data-stu-id="27c5d-193">You can use wildcards for the senders or the recipients (for example, \*@contoso.com).</span></span> <span data-ttu-id="27c5d-194">拡張概要レポートは、最大 5,0000 件の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="27c5d-194">The Enhanced summary report returns up to 50000 results.</span></span> <span data-ttu-id="27c5d-195">拡張レポートは、最大 1000 件の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="27c5d-195">The Extended report returns up to 1000 results.</span></span>

> [!NOTE]
> 
> - <span data-ttu-id="27c5d-196">拡張概要レポートと拡張レポートは、アーカイブされたメッセージ トレース データを使用して準備され、レポートをダウンロードできるまで最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="27c5d-196">Enhanced summary and Extended reports are prepared using archived message trace data, and it can take up to several hours before your report is available to download.</span></span> <span data-ttu-id="27c5d-197">同時にレポート要求を送信した他の管理者の数によっては、キューに入っている要求の処理が開始される前に遅延が発生する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="27c5d-197">Depending on how many other admins have also submitted report requests around the same time, you might also notice a delay before your queued request starts to be processed.</span></span>
> 
> - <span data-ttu-id="27c5d-198">任意の日付/時刻範囲に対して拡張概要レポートまたは拡張レポートを選択することもできますが、通常、アーカイブされたデータの最後の 4 時間は、この 2 種類のレポートではまだ利用できません。</span><span class="sxs-lookup"><span data-stu-id="27c5d-198">While you can select an Enhanced summary or Extended report for any date/time range, commonly the last four hours of archived data will not yet be available for these two types of reports.</span></span>

<span data-ttu-id="27c5d-199">[次へ] をクリックすると、選択したフィルター オプション、レポートの一意の (編集可能な) タイトル、およびメッセージの追跡が完了するときに通知を受け取る電子メール アドレス (編集可能で、組織の受け入れドメインの 1 つにある必要があります) を一覧表示する概要ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-199">When you click **Next**, you're presented with a summary page that lists the filtering options that you selected, a unique (editable) title for the report, and the email address that receives the notification when the message trace completes (also editable, and must be in one of your organization's accepted domains).</span></span> <span data-ttu-id="27c5d-200">[ **レポートの準備] を** クリックしてメッセージ追跡を送信します。</span><span class="sxs-lookup"><span data-stu-id="27c5d-200">Click **Prepare report** to submit the message trace.</span></span> <span data-ttu-id="27c5d-201">メインの [ **メッセージの追跡** ] ページで、[ダウンロード可能なレポート] セクションでレポートの状態 **を確認** できます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-201">On the main **Message trace** page, you can see the status of the report in the **Downloadable reports** section.</span></span>

<span data-ttu-id="27c5d-202">さまざまなレポートの種類で返される情報の詳細については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="27c5d-202">For more information about the information that's returned in the different report types, see the next section.</span></span>

## <a name="message-trace-results"></a><span data-ttu-id="27c5d-203">メッセージ追跡の結果</span><span class="sxs-lookup"><span data-stu-id="27c5d-203">Message trace results</span></span>

<span data-ttu-id="27c5d-204">レポートの種類によって返される情報のレベルは異なります。</span><span class="sxs-lookup"><span data-stu-id="27c5d-204">The different report types return different levels of information.</span></span> <span data-ttu-id="27c5d-205">さまざまなレポートで利用できる情報については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="27c5d-205">The information that's available in the different reports is described in the following sections.</span></span>

### <a name="summary-report-output"></a><span data-ttu-id="27c5d-206">概要レポートの出力</span><span class="sxs-lookup"><span data-stu-id="27c5d-206">Summary report output</span></span>

<span data-ttu-id="27c5d-207">メッセージ追跡を実行すると、結果が一覧表示され、降順の日付/時刻 (最新の日付/時刻) で並べ替えされます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-207">After running the message trace, the results will be listed, sorted by descending date/time (most recent first).</span></span>

![セキュリティ/コンプライアンス センターでのメッセージ追跡の概要&結果](../../media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

<span data-ttu-id="27c5d-209">概要レポートには、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-209">The summary report contains the following information:</span></span>

- <span data-ttu-id="27c5d-210">**日付**: 構成済みの UTC タイム ゾーンを使用して、サービスがメッセージを受信した日時。</span><span class="sxs-lookup"><span data-stu-id="27c5d-210">**Date**: The date and time at which the message was received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="27c5d-211">**Sender**: 送信者の電子メール アドレス (*エイリアス* @ *ドメイン*)。</span><span class="sxs-lookup"><span data-stu-id="27c5d-211">**Sender**: The email address of the sender (*alias*@*domain*).</span></span>

- <span data-ttu-id="27c5d-212">**Recipient**: 受信者または受信者の電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="27c5d-212">**Recipient**: The email address of the recipient or recipients.</span></span> <span data-ttu-id="27c5d-213">複数の受信者に送信されるメッセージの場合、受信者ごとに 1 行が表示されます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-213">For a message sent to multiple recipients, there's one line per recipient.</span></span> <span data-ttu-id="27c5d-214">受信者が配布グループ、動的配布グループ、またはメールが有効なセキュリティ グループである場合、グループは最初の受信者であり、グループの各メンバーは別の行になります。</span><span class="sxs-lookup"><span data-stu-id="27c5d-214">If the recipient is a distribution group, dynamic distribution group, or mail-enabled security group, the group will be the first recipient, and then each member of the group is on a separate line.</span></span>

- <span data-ttu-id="27c5d-215">**件名**: メッセージの **Subject:** フィールドの最初の 256 文字。</span><span class="sxs-lookup"><span data-stu-id="27c5d-215">**Subject**: The first 256 characters of the message's **Subject:** field.</span></span>

- <span data-ttu-id="27c5d-216">**Status**: これらの値については、「配信状態 [」セクションで説明](#delivery-status) されています。</span><span class="sxs-lookup"><span data-stu-id="27c5d-216">**Status**: These values are described in the [Delivery status](#delivery-status) section.</span></span>

<span data-ttu-id="27c5d-217">既定では、最初の 250 件の結果が読み込まれ、すぐに利用できます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-217">By default, the first 250 results are loaded and readily available.</span></span> <span data-ttu-id="27c5d-218">下にスクロールすると、次の結果のバッチが読み込まれると、少し一時停止します。</span><span class="sxs-lookup"><span data-stu-id="27c5d-218">When you scroll down, there's a slight pause as the next batch of results are loaded.</span></span> <span data-ttu-id="27c5d-219">スクロールする代わりに、[すべて読み込む] をクリックすると、すべての結果を最大 10,000 まで読み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="27c5d-219">Instead of scrolling, you can click **Load all** to load all of the results up to a maximum of 10,000.</span></span>

<span data-ttu-id="27c5d-220">列見出しをクリックすると、その列の値を昇順または降順で並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-220">You can click on the column headers to sort the results by the values in that column in ascending or descending order.</span></span>

<span data-ttu-id="27c5d-221">[結果の **フィルター処理] をクリック** すると、1 つ以上の列で結果をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-221">You can click **Filter results** to filter the results by one or more columns.</span></span>

<span data-ttu-id="27c5d-222">1 つ以上の行を選択した後に結果をエクスポートするには、[結果のエクスポート] をクリックし、[すべての結果をエクスポートする]、読み込まれた結果をエクスポートする、**または選択した** エクスポートを選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="27c5d-222">You can export the results after you've selected one or more rows by clicking **Export results** and then selecting **Export all results**, **Export loaded results**, or **Export selected**.</span></span>

#### <a name="find-related-records-for-this-message"></a><span data-ttu-id="27c5d-223">このメッセージの関連レコードを検索する</span><span class="sxs-lookup"><span data-stu-id="27c5d-223">Find related records for this message</span></span>

<span data-ttu-id="27c5d-224">関連するメッセージ レコードは、同じメッセージ ID を共有したレコードです。</span><span class="sxs-lookup"><span data-stu-id="27c5d-224">Related message records are records that shared the same Message ID.</span></span> <span data-ttu-id="27c5d-225">2 人のユーザー間で 1 つのメッセージを送信しても、複数のレコードが生成される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="27c5d-225">Remember, even a single message sent between two people can generate multiple records.</span></span> <span data-ttu-id="27c5d-226">メッセージが配布グループの展開、転送、メール フロー ルール (トランスポート ルールとも呼ばれる) の影響を受ける場合、レコードの数が増えます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-226">The number of records increases when the message is affected by distribution group expansion, forwarding, mail flow rules (also known as transport rules), etc.</span></span>

<span data-ttu-id="27c5d-227">行のチェック ボックスをオンにした後、表示される [関連するレコードの検索]ボタンをクリックするか、[その他のオプション]を選択して、メッセージに関連するレコードを検索できます。 ![ ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> </span><span class="sxs-lookup"><span data-stu-id="27c5d-227">After you select a row's check box, you can find related records for the message by clicking the **Find related** button that appears, or by selecting **More options** ![More](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **Find related records for this message**).</span></span>

<span data-ttu-id="27c5d-228">メッセージ ID の詳細については、この記事の「メッセージ ID」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="27c5d-228">For more information about the Message ID, see the Message ID section earlier in this article.</span></span>

#### <a name="message-trace-details"></a><span data-ttu-id="27c5d-229">メッセージ追跡の詳細</span><span class="sxs-lookup"><span data-stu-id="27c5d-229">Message trace details</span></span>

<span data-ttu-id="27c5d-230">概要レポートの出力では、次のいずれかの方法を使用して、メッセージに関する詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-230">In the summary report output, you can view details about a message by using either of the following methods:</span></span>

- <span data-ttu-id="27c5d-231">行を選択します (チェック ボックスを除く行の任意の場所をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="27c5d-231">Select the row (click anywhere in the row except the check box).</span></span>

- <span data-ttu-id="27c5d-232">行のチェック ボックスをオンにし、[その他のオプション] **をクリックします** ![ 。メッセージ ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **の詳細を表示します**。</span><span class="sxs-lookup"><span data-stu-id="27c5d-232">Select the row's check box and click **More options** ![More](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **View message details**.</span></span>

   ![概要レポートのメッセージ追跡結果の行をダブルクリックした後の詳細は、セキュリティ/コンプライアンス センター&結果](../../media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

<span data-ttu-id="27c5d-234">メッセージ追跡の詳細には、概要レポートには表示されない次の追加情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-234">The message trace details contain the following additional information that's not present in the summary report:</span></span>

- <span data-ttu-id="27c5d-235">**メッセージ イベント**: このセクションには、サービスがメッセージに対して実行するアクションを分類するのに役立つ分類が含まれます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-235">**Message events**: This section contains classifications that help categorize the actions that the service takes on messages.</span></span> <span data-ttu-id="27c5d-236">**発生する可能性がある、より興味深** いイベントの一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="27c5d-236">**Some of the more interesting events** that you might encounter are:</span></span>

  - <span data-ttu-id="27c5d-237">**Receive**: サービスがメッセージを受信しました。</span><span class="sxs-lookup"><span data-stu-id="27c5d-237">**Receive**: The message was received by the service.</span></span>

  - <span data-ttu-id="27c5d-238">**送信**: サービスによってメッセージが送信されました。</span><span class="sxs-lookup"><span data-stu-id="27c5d-238">**Send**: The message was sent by the service.</span></span>

  - <span data-ttu-id="27c5d-239">**Fail**: メッセージの配信に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="27c5d-239">**Fail**: The message failed to be delivered.</span></span>

  - <span data-ttu-id="27c5d-240">**配信**: メッセージがメールボックスに配信されました。</span><span class="sxs-lookup"><span data-stu-id="27c5d-240">**Deliver**: The message was delivered to a mailbox.</span></span>

  - <span data-ttu-id="27c5d-241">**Expand**: メッセージが展開された配布グループに送信されました。</span><span class="sxs-lookup"><span data-stu-id="27c5d-241">**Expand**: The message was sent to a distribution group that was expanded.</span></span>

  - <span data-ttu-id="27c5d-242">**転送**: コンテンツ変換、メッセージ受信者の制限、またはエージェントのために、受信者が分岐メッセージに移動されました。</span><span class="sxs-lookup"><span data-stu-id="27c5d-242">**Transfer**: Recipients were moved to a bifurcated message because of content conversion, message recipient limits, or agents.</span></span>

  - <span data-ttu-id="27c5d-243">**Defer**: メッセージ配信が延期され、後で再試行される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="27c5d-243">**Defer**: The message delivery was postponed and might be re-attempted later.</span></span>

  - <span data-ttu-id="27c5d-244">**解決済** み : メッセージは、Active Directory の検索に基づいて新しい受信者アドレスにリダイレクトされました。</span><span class="sxs-lookup"><span data-stu-id="27c5d-244">**Resolved**: The message was redirected to a new recipient address based on an Active Directory look up.</span></span> <span data-ttu-id="27c5d-245">このイベントが発生した場合、メッセージ トレースの別の行に、メッセージの最終配信状態と併せて、元の受信者のアドレスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-245">When this happens, the original recipient address is listed in a separate row in the message trace along with the final delivery status for the message.</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="27c5d-246">問題のあるメッセージが正常に配信されると、メッセージトレースに複数の **イベント** エントリが生成されます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-246">An uneventful message that's successfully delivered will generate multiple **Event** entries in the message trace.</span></span>
  > 
  > - <span data-ttu-id="27c5d-247">この一覧は、完全な機能を提供することを意図したのではありません。</span><span class="sxs-lookup"><span data-stu-id="27c5d-247">This list is not meant to be exhaustive.</span></span> <span data-ttu-id="27c5d-248">その他のイベントの詳細については、メッセージ追跡ログ [のイベントの種類を参照してください](https://docs.microsoft.com/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log)。</span><span class="sxs-lookup"><span data-stu-id="27c5d-248">For descriptions of more events, see [Event types in the message tracking log](https://docs.microsoft.com/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log).</span></span> <span data-ttu-id="27c5d-249">このリンクは、Exchange Server (オンプレミスの Exchange) トピックです。</span><span class="sxs-lookup"><span data-stu-id="27c5d-249">Note that this link is an Exchange Server (on-premises Exchange) topic.</span></span>

- <span data-ttu-id="27c5d-250">**詳細:** このセクションには、次の詳細が含まれます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-250">**More information**: This section contains the following details:</span></span>

  - <span data-ttu-id="27c5d-251">**メッセージ ID**: この値については、この記事の「 [メッセージ ID」](#message-id) セクションで説明しました。</span><span class="sxs-lookup"><span data-stu-id="27c5d-251">**Message ID**: This value is described in the [Message ID](#message-id) section earlier in this article.</span></span> <span data-ttu-id="27c5d-252">たとえば、`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>` などです。</span><span class="sxs-lookup"><span data-stu-id="27c5d-252">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

  - <span data-ttu-id="27c5d-253">**メッセージ サイズ**   添付ファイルを含むキロバイト (KB) 単位のメッセージのサイズ。</span><span class="sxs-lookup"><span data-stu-id="27c5d-253">**Message size**</span></span>

  - <span data-ttu-id="27c5d-254">**[IP から**]: メッセージを送信したコンピューターの IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="27c5d-254">**From IP**: The IP address of the computer that sent the message.</span></span> <span data-ttu-id="27c5d-255">Exchange Online から送信された送信メッセージの場合、この値は空白です。</span><span class="sxs-lookup"><span data-stu-id="27c5d-255">For outbound messages sent from Exchange Online, this value is blank.</span></span>

  - <span data-ttu-id="27c5d-256">**TO IP**: サービスがメッセージを配信しようとした IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="27c5d-256">**To IP**: The IP address or addresses where the service attempted to deliver the message.</span></span> <span data-ttu-id="27c5d-257">メッセージに複数の受信者がある場合は、これらの受信者が表示されます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-257">If the message has multiple recipients, these are displayed.</span></span> <span data-ttu-id="27c5d-258">Exchange Online に送信された受信メッセージの場合、この値は空白です。</span><span class="sxs-lookup"><span data-stu-id="27c5d-258">For inbound messages sent to Exchange Online, this value is blank.</span></span>

### <a name="enhanced-summary-reports"></a><span data-ttu-id="27c5d-259">拡張概要レポート</span><span class="sxs-lookup"><span data-stu-id="27c5d-259">Enhanced summary reports</span></span>

<span data-ttu-id="27c5d-260">利用可能な (完了した) 拡張概要レポートは、メッセージ追跡の開始時点の [ダウンロード可能なレポート] セクションで確認できます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-260">Available (completed) Enhanced summary reports are available in the **Downloadable reports** section at the beginning message trace.</span></span> <span data-ttu-id="27c5d-261">レポートでは、次の情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-261">The following information is available in the report:</span></span>

- <span data-ttu-id="27c5d-262">**origin_timestamp**: 構成済みの UTC タイム ゾーンを使用して、サービスがメッセージを最初に受信した <sup>\*</sup> 日時です。</span><span class="sxs-lookup"><span data-stu-id="27c5d-262">**origin_timestamp**<sup>\*</sup>: The date and time when the message was initially received by the service, using the configured UTC time zone.</span></span>

- <span data-ttu-id="27c5d-263">**sender_address**: 送信者の電子メール アドレス (*エイリアス* @ *ドメイン*)。</span><span class="sxs-lookup"><span data-stu-id="27c5d-263">**sender_address**: The sender's email address (*alias*@*domain*).</span></span>

- <span data-ttu-id="27c5d-264">**Recipient_status**: 受信者へのメッセージの配信の状態。</span><span class="sxs-lookup"><span data-stu-id="27c5d-264">**Recipient_status**: The status of the delivery of the message to the recipient.</span></span> <span data-ttu-id="27c5d-265">メッセージが複数の受信者に送信された場合は、次の形式で、すべての受信者とそれぞれの対応する状態が表示されます \<*email address*\> ## \<*status*\> 。</span><span class="sxs-lookup"><span data-stu-id="27c5d-265">If the message was sent to multiple recipients, it will show all the recipients and the corresponding status for each, in the format: \<*email address*\>##\<*status*\>.</span></span> <span data-ttu-id="27c5d-266">例:</span><span class="sxs-lookup"><span data-stu-id="27c5d-266">For example:</span></span>

  - <span data-ttu-id="27c5d-267">**##Receive送信は** 、メッセージがサービスによって受信され、目的の送信先に送信されたという意味です。</span><span class="sxs-lookup"><span data-stu-id="27c5d-267">**##Receive, Send** means the message was received by the service and was sent to the intended destination.</span></span>

  - <span data-ttu-id="27c5d-268">**##Receive失敗は** 、サービスがメッセージを受信したが、目的の送信先への配信が失敗した場合を意味します。</span><span class="sxs-lookup"><span data-stu-id="27c5d-268">**##Receive, Fail** means the message was received by the service but delivery to the intended destination failed.</span></span>

  - <span data-ttu-id="27c5d-269">**##Receiveは、メッセージ** がサービスによって受信され、受信者のメールボックスに配信されたという意味です。</span><span class="sxs-lookup"><span data-stu-id="27c5d-269">**##Receive, Deliver** means the message was received by the service and was delivered to the recipient's mailbox.</span></span>

- <span data-ttu-id="27c5d-270">**message_subject**: メッセージの [件名] フィールドの最初の 256 **文字** 。</span><span class="sxs-lookup"><span data-stu-id="27c5d-270">**message_subject**: The first 256 characters of the message's **Subject** field.</span></span>

- <span data-ttu-id="27c5d-271">**total_bytes**: 添付ファイルを含むメッセージのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="27c5d-271">**total_bytes**: The size of the message in bytes, including attachments.</span></span>

- <span data-ttu-id="27c5d-272">**message_id**: この値については、この記事の「 [メッセージ ID」](#message-id) セクションで説明しました。</span><span class="sxs-lookup"><span data-stu-id="27c5d-272">**message_id**: This value is described in the [Message ID](#message-id) section earlier in this article.</span></span> <span data-ttu-id="27c5d-273">たとえば、`<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>` などです。</span><span class="sxs-lookup"><span data-stu-id="27c5d-273">For example, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.</span></span>

- <span data-ttu-id="27c5d-274">**network_message_id**: メッセージのすべてのコピーで保持される一意のメッセージ ID 値です。メッセージの分岐または配布グループの展開によって作成される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="27c5d-274">**network_message_id**: A unique message ID value that persists across all copies of the message that might be created due to bifurcation or distribution group expansion.</span></span> <span data-ttu-id="27c5d-275">値の例は次のようになります `1341ac7b13fb42ab4d4408cf7f55890f` 。</span><span class="sxs-lookup"><span data-stu-id="27c5d-275">An example value is `1341ac7b13fb42ab4d4408cf7f55890f`.</span></span>

- <span data-ttu-id="27c5d-276">**original_client_ip**: 送信者のクライアントの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="27c5d-276">**original_client_ip**: The IP address of the sender's client.</span></span>

- <span data-ttu-id="27c5d-277">**方向**: メッセージが組織に受信 (1) 送信されたかどうか、または組織から送信された (2) かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="27c5d-277">**directionality**: Indicates whether the message was sent inbound (1) to your organization, or whether it was sent outbound (2) from your organization.</span></span>

- <span data-ttu-id="27c5d-278">**connector_id**: 送信元コネクタまたは宛先コネクタの名前。</span><span class="sxs-lookup"><span data-stu-id="27c5d-278">**connector_id**: The name of the source or destination connector.</span></span> <span data-ttu-id="27c5d-279">Exchange Online のコネクタの詳細については、「Configure [mail flow using connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27c5d-279">For more information about connectors in Exchange Online, see [Configure mail flow using connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

- <span data-ttu-id="27c5d-280">**delivery_priority**: メッセージが高、低、または標準の優先度 <sup>\*</sup> で **送信されたかどうか**。  </span><span class="sxs-lookup"><span data-stu-id="27c5d-280">**delivery_priority**<sup>\*</sup>: Whether the message was sent with **High**, **Low**, or **Normal** priority.</span></span>

<span data-ttu-id="27c5d-281"><sup>\*</sup> これらのプロパティは、拡張サマリー レポートでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-281"><sup>\*</sup> These properties are only available in Enhanced summary reports.</span></span>

### <a name="extended-reports"></a><span data-ttu-id="27c5d-282">拡張レポート</span><span class="sxs-lookup"><span data-stu-id="27c5d-282">Extended reports</span></span>

<span data-ttu-id="27c5d-283">利用可能な (完了した) 拡張レポートは、メッセージ追跡の開始時 **の** [ダウンロード可能なレポート] セクションで確認できます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-283">Available (completed) Extended reports are available in the **Downloadable reports** section at the beginning of message trace.</span></span> <span data-ttu-id="27c5d-284">拡張概要レポートの事実上すべての情報は、拡張レポートで使用できます (ただし、origin_timestamp **および\*\*\*\*delivery_priority)。**</span><span class="sxs-lookup"><span data-stu-id="27c5d-284">Virtually all of the information from an Enhanced summary report is available in an Extended report (with the exception of **origin_timestamp** and **delivery_priority**).</span></span> <span data-ttu-id="27c5d-285">次の追加情報は、拡張レポートでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-285">The following additional information is only available in an Extended report:</span></span>

- <span data-ttu-id="27c5d-286">**client_ip**: メッセージを送信した電子メール サーバーまたはメッセージング クライアントの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="27c5d-286">**client_ip**: The IP address of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="27c5d-287">**client_hostname**: メッセージを送信した電子メール サーバーまたはメッセージング クライアントのホスト名または FQDN。</span><span class="sxs-lookup"><span data-stu-id="27c5d-287">**client_hostname**: The host name or FQDN of the email server or messaging client that submitted the message.</span></span>

- <span data-ttu-id="27c5d-288">**server_ip**: 送信元または送信先サーバーの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="27c5d-288">**server_ip**: The IP address of the source or destination server.</span></span>

- <span data-ttu-id="27c5d-289">**server_hostname**: 送信先サーバーのホスト名または FQDN。</span><span class="sxs-lookup"><span data-stu-id="27c5d-289">**server_hostname**: The host name or FQDN of the destination server.</span></span>

- <span data-ttu-id="27c5d-290">**source_context**: ソース フィールドに関連付けられている追加 **の情報** 。</span><span class="sxs-lookup"><span data-stu-id="27c5d-290">**source_context**: Extra information associated with the **source** field.</span></span> <span data-ttu-id="27c5d-291">例:</span><span class="sxs-lookup"><span data-stu-id="27c5d-291">For example:</span></span>

  - `Protocol Filter Agent`

  - `3489061114359050000`

- <span data-ttu-id="27c5d-292">**source**: イベントを担当する Exchange Online コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="27c5d-292">**source**: The Exchange Online component that's responsible for the event.</span></span> <span data-ttu-id="27c5d-293">例:</span><span class="sxs-lookup"><span data-stu-id="27c5d-293">For example:</span></span>

  - `AGENT`

  - `MAILBOXRULE`

  - `SMTP`

- <span data-ttu-id="27c5d-294">**event_id**: これらは、このメッセージ **の関連** レコードの検索に関するセクションで説明されている [Message イベント値に対応](#find-related-records-for-this-message) します。</span><span class="sxs-lookup"><span data-stu-id="27c5d-294">**event_id**: These correspond to the **Message event** values that are explained in the [Find related records for this message](#find-related-records-for-this-message) section.</span></span>

- <span data-ttu-id="27c5d-295">**internal_message_id**: 現在メッセージを処理している Exchange Online サーバーによって割り当てられたメッセージ識別子。</span><span class="sxs-lookup"><span data-stu-id="27c5d-295">**internal_message_id**: A message identifier that's assigned by the Exchange Online server that's currently processing the message.</span></span>

- <span data-ttu-id="27c5d-296">**recipient_address**: メッセージの受信者の電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="27c5d-296">**recipient_address**: The email addresses of the message's recipients.</span></span> <span data-ttu-id="27c5d-297">複数の電子メール アドレスがある場合は、セミコロン (;) で区切られます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-297">Multiple email addresses are separated by the semicolon character (;).</span></span>

- <span data-ttu-id="27c5d-298">**recipient_count**: メッセージ内の受信者の総数です。</span><span class="sxs-lookup"><span data-stu-id="27c5d-298">**recipient_count**: The total number of recipients in the message.</span></span>

- <span data-ttu-id="27c5d-299">**related_recipient_address**: メッセージに関連付けられている他の受信者の電子メール アドレスを表示するために、イベントと `EXPAND` `REDIRECT` `RESOLVE` 一緒に使用されます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-299">**related_recipient_address**: Used with `EXPAND`, `REDIRECT`, and `RESOLVE` events to display other recipient email addresses that are associated with the message.</span></span>

- <span data-ttu-id="27c5d-300">**reference**: このフィールドには、特定の種類のイベントに関する追加情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="27c5d-300">**reference**: This field contains additional information for specific types of events.</span></span> <span data-ttu-id="27c5d-301">例:</span><span class="sxs-lookup"><span data-stu-id="27c5d-301">For example:</span></span>

  - <span data-ttu-id="27c5d-302">**DSN**: このイベントの後に DSN が生成された場合に、関連付けられた配信状態通知 (DSN、配信前レポート、NDR、またはバウンス メッセージとも呼ばれる) の **message_id** 値であるレポート リンクを格納します。</span><span class="sxs-lookup"><span data-stu-id="27c5d-302">**DSN**: Contains the report link, which is the **message_id** value of the associated delivery status notification (also known as a DSN, non-delivery report, NDR, or bounce message) if a DSN is generated subsequent to this event.</span></span> <span data-ttu-id="27c5d-303">これが DSN メッセージの場合、このフィールドには DSN **message_id** 元のメッセージの値が含まれる。</span><span class="sxs-lookup"><span data-stu-id="27c5d-303">If this is a DSN message, this field contains the **message_id** value of the original message that the DSN was generated for.</span></span>

  - <span data-ttu-id="27c5d-304">**EXPAND**: 関連するメッセージ **related_recipient_address** 値を格納します。</span><span class="sxs-lookup"><span data-stu-id="27c5d-304">**EXPAND**: Contains the **related_recipient_address** value of the related messages.</span></span>

  - <span data-ttu-id="27c5d-305">**RECEIVE**: メッセージが他の **message_id** (受信トレイ ルールなど) によって生成された場合、関連するメッセージの値を含む場合があります。</span><span class="sxs-lookup"><span data-stu-id="27c5d-305">**RECEIVE**: Might contain the **message_id** value of the related message if the message was generated by other processes (for example, Inbox rules).</span></span>

  - <span data-ttu-id="27c5d-306">**SEND**: DSN メッセージの **internal_message_id** 値を格納します。</span><span class="sxs-lookup"><span data-stu-id="27c5d-306">**SEND**: Contains the **internal_message_id** value of any DSN messages.</span></span>

  - <span data-ttu-id="27c5d-307">**TRANSFER**: フォーク **されているinternal_message_id** の値を格納します (たとえば、コンテンツ変換、メッセージ受信者の制限、エージェント別)。</span><span class="sxs-lookup"><span data-stu-id="27c5d-307">**TRANSFER**: Contains the **internal_message_id** value of the message that's being forked (for example, by content conversion, message recipient limits, or agents).</span></span>

  - <span data-ttu-id="27c5d-308">**MAILBOXRULE**: 受信 **internal_message_id** 送信メッセージを生成する原因となる受信メッセージの値を格納します。</span><span class="sxs-lookup"><span data-stu-id="27c5d-308">**MAILBOXRULE**: Contains the **internal_message_id** value of the inbound message that caused the Inbox rule to generate the outbound message.</span></span>

    <span data-ttu-id="27c5d-309">他の種類のイベントの場合、通常、このフィールドは空白です。</span><span class="sxs-lookup"><span data-stu-id="27c5d-309">For other types of events, this field is usually blank.</span></span>

- <span data-ttu-id="27c5d-310">**return_path**: メッセージを送信した **MAIL FROM** コマンドで指定された電子メール アドレスを返します。</span><span class="sxs-lookup"><span data-stu-id="27c5d-310">**return_path**: The return email address specified by the **MAIL FROM** command that sent the message.</span></span> <span data-ttu-id="27c5d-311">このフィールドは空にすることはできませんが、null の送信者アドレス値を表す値を持つ場合があります `<>` 。</span><span class="sxs-lookup"><span data-stu-id="27c5d-311">Although this field is never empty, it can have the null sender address value represented as `<>`.</span></span>

- <span data-ttu-id="27c5d-312">**message_info**: メッセージに関する追加情報。</span><span class="sxs-lookup"><span data-stu-id="27c5d-312">**message_info**: Additional information about the message.</span></span> <span data-ttu-id="27c5d-313">例:</span><span class="sxs-lookup"><span data-stu-id="27c5d-313">For example:</span></span>

  - <span data-ttu-id="27c5d-314">イベントのメッセージの配信日時 `DELIVER` `SEND` (UTC)。</span><span class="sxs-lookup"><span data-stu-id="27c5d-314">The message origination date-time in UTC for `DELIVER` and `SEND` events.</span></span> <span data-ttu-id="27c5d-315">配信日時は、メッセージが最初に Exchange Online 組織に入った時刻です。</span><span class="sxs-lookup"><span data-stu-id="27c5d-315">The origination date-time is the time when the message first entered the Exchange Online organization.</span></span> <span data-ttu-id="27c5d-316">UTC の日付と時刻は、ISO 8601 の日付と時刻の形式で表されます。ここで、= 年、= 月、= 日は、時刻コンポーネントの開始を示し `yyyy-mm-ddThh:mm:ss.fffZ` `yyyy` `mm` `dd` `T` `hh` 、= 時、 `mm` 分 `ss` 、= 秒 `fff` 、= `Z` `Zulu` 秒の小数部を示し、UTC を示すもう 1 つの方法です。</span><span class="sxs-lookup"><span data-stu-id="27c5d-316">The UTC date-time is represented in the ISO 8601 date-time format: `yyyy-mm-ddThh:mm:ss.fffZ`, where `yyyy` = year, `mm` = month, `dd` = day, `T` indicates the beginning of the time component, `hh` = hour, `mm` = minute, `ss` = second, `fff` = fractions of a second, and `Z` signifies `Zulu`, which is another way to denote UTC.</span></span>

  - <span data-ttu-id="27c5d-317">認証エラー。</span><span class="sxs-lookup"><span data-stu-id="27c5d-317">Authentication errors.</span></span> <span data-ttu-id="27c5d-318">たとえば、認証エラーが発生した際に使用された認証の値と種類 `11a` が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="27c5d-318">For example, you might see the value `11a` and the type of authentication that was used when the authentication error occurred.</span></span>

- <span data-ttu-id="27c5d-319">**tenant_id**: Exchange Online 組織を表す GUID 値 (例 `39238e87-b5ab-4ef6-a559-af54c6b07b42` : )。</span><span class="sxs-lookup"><span data-stu-id="27c5d-319">**tenant_id**: A GUID value that represents the Exchange Online organization (for example, `39238e87-b5ab-4ef6-a559-af54c6b07b42`).</span></span>

- <span data-ttu-id="27c5d-320">**original_server_ip**: 元のサーバーの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="27c5d-320">**original_server_ip**: The IP address of the original server.</span></span>

- <span data-ttu-id="27c5d-321">**custom_data**: 特定のイベントの種類に関連するデータが格納されています。</span><span class="sxs-lookup"><span data-stu-id="27c5d-321">**custom_data**: Contains data related to specific event types.</span></span> <span data-ttu-id="27c5d-322">詳細については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="27c5d-322">For more information, see the following sections.</span></span>

#### <a name="custom_data-values"></a><span data-ttu-id="27c5d-323">custom_data値</span><span class="sxs-lookup"><span data-stu-id="27c5d-323">custom_data values</span></span>

<span data-ttu-id="27c5d-324">イベント **custom_data** フィールドは、さまざまな Exchange Online エージェントがメッセージ処理の詳細をログ `AGENTINFO` に記録するために使用します。</span><span class="sxs-lookup"><span data-stu-id="27c5d-324">The **custom_data** field for an `AGENTINFO` event is used by a variety of Exchange Online agents to log message processing details.</span></span> <span data-ttu-id="27c5d-325">次のセクションでは、より興味深いエージェントの一部について説明します。</span><span class="sxs-lookup"><span data-stu-id="27c5d-325">Some of the more interesting agents are described in the following sections.</span></span>

#### <a name="spam-filter-agent"></a><span data-ttu-id="27c5d-326">スパム フィルター エージェント</span><span class="sxs-lookup"><span data-stu-id="27c5d-326">Spam filter agent</span></span>

<span data-ttu-id="27c5d-327">最初 **custom_data** 値はスパム フィルター `S:SFA` エージェントからの値です。</span><span class="sxs-lookup"><span data-stu-id="27c5d-327">A **custom_data** value that starts with `S:SFA` is from the spam filter agent.</span></span> <span data-ttu-id="27c5d-328">主な詳細については、次の表で説明します。</span><span class="sxs-lookup"><span data-stu-id="27c5d-328">The key details are described in the following table:</span></span>

****

|<span data-ttu-id="27c5d-329">値</span><span class="sxs-lookup"><span data-stu-id="27c5d-329">Value</span></span>|<span data-ttu-id="27c5d-330">説明</span><span class="sxs-lookup"><span data-stu-id="27c5d-330">Description</span></span>|
|---|---|
|`SFV=NSPM`|<span data-ttu-id="27c5d-331">メッセージがスパムではないとしてマークされ、意図された受信者に送信されました。</span><span class="sxs-lookup"><span data-stu-id="27c5d-331">The message was marked as non-spam and was sent to the intended recipients.</span></span>|
|`SFV=SPM`|<span data-ttu-id="27c5d-332">メッセージはスパム対策フィルター (コンテンツ フィルターとも呼ばれる) によってスパムとしてマークされました。</span><span class="sxs-lookup"><span data-stu-id="27c5d-332">The message was marked as spam by anti-spam filtering (also known as content filtering).</span></span>|
|`SFV=BLK`|<span data-ttu-id="27c5d-333">ブロックする差出人から発信されたメッセージであるため、フィルター処理が省略され、メッセージはブロックされました。</span><span class="sxs-lookup"><span data-stu-id="27c5d-333">Filtering was skipped and the message was blocked because it originated from a blocked sender.</span></span>|
|`SFV=SKS`|<span data-ttu-id="27c5d-334">メッセージはスパム対策フィルターによって処理される前にスパムとしてマークされました。</span><span class="sxs-lookup"><span data-stu-id="27c5d-334">The message was marked as spam prior to being processed by anti-spam filtering.</span></span> <span data-ttu-id="27c5d-335">これには、メッセージを自動的にスパムメールとしてマークし、他のすべてのフィルター処理を省略するトランスポート ルールに一致するメッセージが含まれます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-335">This includes messages where the message matched a mail flow rule (also known as a transport rule) to automatically mark it as spam and bypass all additional filtering.</span></span>|
|`SCL=<number>`|<span data-ttu-id="27c5d-336">さまざまな SCL の値とその意味の詳細については、「[Spam Confidence Level](spam-confidence-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27c5d-336">For more information about the different SCL values and what they mean, see [Spam confidence levels](spam-confidence-levels.md).</span></span>|
|`PCL=<number>`|<span data-ttu-id="27c5d-p155">メッセージの Phishing Confidence Level (PCL) 値。これらの値は、「[Spam Confidence Level](spam-confidence-levels.md)」に記載されている SCL 値と同様に解釈できます。  </span><span class="sxs-lookup"><span data-stu-id="27c5d-p155">The Phishing Confidence Level (PCL) value of the message. These can be interpreted the same way as the SCL values documented in [Spam confidence levels](spam-confidence-levels.md).</span></span>|
|`DI=SB`|<span data-ttu-id="27c5d-339">メッセージの送信者はブロックされました。</span><span class="sxs-lookup"><span data-stu-id="27c5d-339">The sender of the message was blocked.</span></span>|
|`DI=SQ`|<span data-ttu-id="27c5d-340">メッセージは検疫されました。</span><span class="sxs-lookup"><span data-stu-id="27c5d-340">The message was quarantined.</span></span>|
|`DI=SD`|<span data-ttu-id="27c5d-341">メッセージは削除されました。</span><span class="sxs-lookup"><span data-stu-id="27c5d-341">The message was deleted.</span></span>|
|`DI=SJ`|<span data-ttu-id="27c5d-342">メッセージは受信者の迷惑メール フォルダーに送信されました。</span><span class="sxs-lookup"><span data-stu-id="27c5d-342">The message was sent to the recipient's Junk Email folder.</span></span>|
|`DI=SN`|<span data-ttu-id="27c5d-343">メッセージは通常の送信用の配信プールを通じて送信されました。</span><span class="sxs-lookup"><span data-stu-id="27c5d-343">The message was routed through the normal outbound delivery pool.</span></span>|
|`DI=SO`|<span data-ttu-id="27c5d-344">メッセージがより危険度の高い配信プールを経由してルーティングされました。</span><span class="sxs-lookup"><span data-stu-id="27c5d-344">The message was routed through the higher risk delivery pool.</span></span> <span data-ttu-id="27c5d-345">詳細については、「[送信メッセージにおける危険度の高い配信プール](high-risk-delivery-pool-for-outbound-messages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27c5d-345">For more information, see [High-risk delivery pool for outbound messages](high-risk-delivery-pool-for-outbound-messages.md).</span></span>|
|`SFS=[a]|SFS=[b]`|<span data-ttu-id="27c5d-346">これはスパム ルールが一致したことを示します。</span><span class="sxs-lookup"><span data-stu-id="27c5d-346">This denotes that spam rules were matched.</span></span>|
|`IPV=CAL`|<span data-ttu-id="27c5d-347">このメッセージの IP アドレスは接続フィルターの IP 許可一覧に指定されているため、スパム フィルターの通過を許可されました。</span><span class="sxs-lookup"><span data-stu-id="27c5d-347">The message was allowed through the spam filters because the IP address was specified in an IP Allow list in the connection filter.</span></span>|
|`H=<EHLOstring>`|<span data-ttu-id="27c5d-348">接続メール サーバーの HELO または EHLO 文字列。</span><span class="sxs-lookup"><span data-stu-id="27c5d-348">The HELO or EHLO string of the connecting email server.</span></span>|
|`PTR=<ReverseDNS>`|<span data-ttu-id="27c5d-349">送信元の IP アドレスの PTR レコード (逆引き DNS アドレスともいう) です。</span><span class="sxs-lookup"><span data-stu-id="27c5d-349">The PTR record of the sending IP address, also known as the reverse DNS address.</span></span>|
|

<span data-ttu-id="27c5d-350">次のような **custom_data** フィルター処理されたメッセージの値を取得する例を示します。</span><span class="sxs-lookup"><span data-stu-id="27c5d-350">An example **custom_data** value for a message that's filtered for spam like this:</span></span>

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a><span data-ttu-id="27c5d-351">マルウェア フィルター エージェント</span><span class="sxs-lookup"><span data-stu-id="27c5d-351">Malware filter agent</span></span>

<span data-ttu-id="27c5d-352">最初 **custom_data** 値は `S:AMA` マルウェア フィルター エージェントからの値です。</span><span class="sxs-lookup"><span data-stu-id="27c5d-352">A **custom_data** value that starts with `S:AMA` is from the malware filter agent.</span></span> <span data-ttu-id="27c5d-353">主な詳細については、次の表で説明します。</span><span class="sxs-lookup"><span data-stu-id="27c5d-353">The key details are described in the following table:</span></span>

****

|<span data-ttu-id="27c5d-354">値</span><span class="sxs-lookup"><span data-stu-id="27c5d-354">Value</span></span>|<span data-ttu-id="27c5d-355">説明</span><span class="sxs-lookup"><span data-stu-id="27c5d-355">Description</span></span>|
|---|---|
|<span data-ttu-id="27c5d-356">`AMA=SUM|v=1|` または `AMA=EV|v=1`</span><span class="sxs-lookup"><span data-stu-id="27c5d-356">`AMA=SUM|v=1|` or `AMA=EV|v=1`</span></span>|<span data-ttu-id="27c5d-357">このメッセージは、マルウェアが含まれていると判断されました。</span><span class="sxs-lookup"><span data-stu-id="27c5d-357">The message was determined to contain malware.</span></span> <span data-ttu-id="27c5d-358">`SUM` は、マルウェアが任意の数のエンジンによって検出された可能性を示します。</span><span class="sxs-lookup"><span data-stu-id="27c5d-358">`SUM` indicates the malware could've been detected by any number of engines.</span></span> <span data-ttu-id="27c5d-359">`EV` は、マルウェアが特定のエンジンによって検出されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="27c5d-359">`EV` indicates the malware was detected by a specific engine.</span></span> <span data-ttu-id="27c5d-360">エンジンでマルウェアが検出された場合は、後続のアクションをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="27c5d-360">When malware is detected by an engine this triggers the subsequent actions.</span></span>|
|`Action=r`|<span data-ttu-id="27c5d-361">メッセージは置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="27c5d-361">The message was replaced.</span></span>|
|`Action=p`|<span data-ttu-id="27c5d-362">メッセージはバイパスされました。</span><span class="sxs-lookup"><span data-stu-id="27c5d-362">The message was bypassed.</span></span>|
|`Action=d`|<span data-ttu-id="27c5d-363">メッセージは延期されました。</span><span class="sxs-lookup"><span data-stu-id="27c5d-363">The message was deferred.</span></span>|
|`Action=s`|<span data-ttu-id="27c5d-364">メッセージは削除されました。</span><span class="sxs-lookup"><span data-stu-id="27c5d-364">The message was deleted.</span></span>|
|`Action=st`|<span data-ttu-id="27c5d-365">メッセージはバイパスされました。</span><span class="sxs-lookup"><span data-stu-id="27c5d-365">The message was bypassed.</span></span>|
|`Action=sy`|<span data-ttu-id="27c5d-366">メッセージはバイパスされました。</span><span class="sxs-lookup"><span data-stu-id="27c5d-366">The message was bypassed.</span></span>|
|`Action=ni`|<span data-ttu-id="27c5d-367">メッセージは拒否されました。</span><span class="sxs-lookup"><span data-stu-id="27c5d-367">The message was rejected.</span></span>|
|`Action=ne`|<span data-ttu-id="27c5d-368">メッセージは拒否されました。</span><span class="sxs-lookup"><span data-stu-id="27c5d-368">The message was rejected.</span></span>|
|`Action=b`|<span data-ttu-id="27c5d-369">メッセージはブロックされました。</span><span class="sxs-lookup"><span data-stu-id="27c5d-369">The message was blocked.</span></span>|
|`Name=<malware>`|<span data-ttu-id="27c5d-370">検出されたマルウェアの名前。</span><span class="sxs-lookup"><span data-stu-id="27c5d-370">The name of the malware that was detected.</span></span>|
|`File=<filename>`|<span data-ttu-id="27c5d-371">マルウェアを含むファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="27c5d-371">The name of the file that contained the malware.</span></span>|
|

<span data-ttu-id="27c5d-372">マルウェアを **custom_data** 含むメッセージの値の例は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="27c5d-372">An example **custom_data** value for a message that contains malware looks like this:</span></span>

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a><span data-ttu-id="27c5d-373">トランスポート ルール エージェント</span><span class="sxs-lookup"><span data-stu-id="27c5d-373">Transport Rule agent</span></span>

<span data-ttu-id="27c5d-374">最初 **custom_data** の値は、メール フロー ルール (トランスポート ルールとも呼ばれる) のトランスポート ルール `S:TRA` エージェントからの値です。</span><span class="sxs-lookup"><span data-stu-id="27c5d-374">A **custom_data** value that starts with`S:TRA` is from the Transport Rule agent for mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="27c5d-375">主な詳細については、次の表で説明します。</span><span class="sxs-lookup"><span data-stu-id="27c5d-375">The key details are described in the following table:</span></span>

****

|<span data-ttu-id="27c5d-376">値</span><span class="sxs-lookup"><span data-stu-id="27c5d-376">Value</span></span>|<span data-ttu-id="27c5d-377">説明</span><span class="sxs-lookup"><span data-stu-id="27c5d-377">Description</span></span>|
|---|---|
|`ETR|ruleId=<guid>`|<span data-ttu-id="27c5d-378">一致したルールの ID。</span><span class="sxs-lookup"><span data-stu-id="27c5d-378">The rule ID that was matched.</span></span>|
|`St=<datetime>`|<span data-ttu-id="27c5d-379">ルールの一致が発生した日時 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="27c5d-379">The date and time in UTC when the rule match occurred.</span></span>|
|`Action=<ActionDefinition>`|<span data-ttu-id="27c5d-380">適用されたアクション。</span><span class="sxs-lookup"><span data-stu-id="27c5d-380">The action that was applied.</span></span> <span data-ttu-id="27c5d-381">使用可能なアクションの一覧については [、「Exchange Online のメール フロー ルールアクション」を参照してください](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。</span><span class="sxs-lookup"><span data-stu-id="27c5d-381">For a list of available actions, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>|
|`Mode=<Mode>`|<span data-ttu-id="27c5d-382">ルールのモード。</span><span class="sxs-lookup"><span data-stu-id="27c5d-382">The mode of the rule.</span></span> <span data-ttu-id="27c5d-383">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="27c5d-383">Valid values are:</span></span><ul><li><span data-ttu-id="27c5d-384">**[強制**]: ルールのすべてのアクションが適用されます。</span><span class="sxs-lookup"><span data-stu-id="27c5d-384">**Enforce**: All actions on the rule will be enforced.</span></span></li><li><span data-ttu-id="27c5d-385">**ポリシー ヒントを使用したテスト:** ポリシー ヒントアクションは送信されますが、他の強制アクションは実行されません。</span><span class="sxs-lookup"><span data-stu-id="27c5d-385">**Test with Policy Tips:**: Any Policy Tip actions will be sent, but other enforcement actions will not be acted on.</span></span></li><li><span data-ttu-id="27c5d-386">**ポリシー ヒントなしの** テスト : アクションはログ ファイルに一覧表示されますが、送信者には通知されません。強制アクションは実行されません。</span><span class="sxs-lookup"><span data-stu-id="27c5d-386">**Test without Policy Tips**: Actions will be listed in a log file, but senders will not be notified in any way, and enforcement actions will not be acted on.</span></span></li></ul>|
|

<span data-ttu-id="27c5d-387">メール フロー **custom_data** 条件に一致するメッセージの値の例は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="27c5d-387">An example **custom_data** value for a messages that matches the conditions of a mail flow rule looks like this:</span></span>

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`
