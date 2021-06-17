---
title: Microsoft Defender for Endpoint API リリース ノート
description: Microsoft Defender for Endpoint セットの API に対して行われた更新プログラムのリリース ノート。
keywords: Microsoft Defender for Endpoint API リリース ノート、mde、API、Microsoft Defender for Endpoint API、更新プログラム、メモ、リリース
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: a0191a52c64b32b314d4b2f2f36c85b060226ad6
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984654"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a><span data-ttu-id="2895b-104">Microsoft Defender for Endpoint API リリース ノート</span><span class="sxs-lookup"><span data-stu-id="2895b-104">Microsoft Defender for Endpoint API release notes</span></span>

<span data-ttu-id="2895b-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="2895b-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="2895b-106">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="2895b-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2895b-107">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="2895b-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="2895b-108">次の情報は、Microsoft Defender for Endpoint API に対して行われた更新プログラムと、その更新日を示しています。</span><span class="sxs-lookup"><span data-stu-id="2895b-108">The following information lists the updates made to the Microsoft Defender for Endpoint APIs and the dates they were made.</span></span>

> [!TIP]
> <span data-ttu-id="2895b-109">RSS フィード: 次の URL をコピーしてフィード リーダーに貼り付け、このページが更新された場合に通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="2895b-109">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
>
> ```http
> /api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
> ```

## <a name="release-notes---newest-to-oldest-ddmmyyyy"></a><span data-ttu-id="2895b-110">リリース ノート - 最新から最も古い (dd.mm.yyyy)</span><span class="sxs-lookup"><span data-stu-id="2895b-110">Release notes - newest to oldest (dd.mm.yyyy)</span></span>

### <a name="06102021"></a><span data-ttu-id="2895b-111">06.10.2021</span><span class="sxs-lookup"><span data-stu-id="2895b-111">06.10.2021</span></span>

- <span data-ttu-id="2895b-112">新しいエクスポート評価 API メソッド - デルタ エクスポート ソフトウェア脆弱性評価 _(OData)_ デバイスごとの評価方法とプロパティのエクスポート [を追加しました](get-assessment-methods-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="2895b-112">Added new Export assessment API method  - _Delta Export software vulnerabilities assessment (OData)_ [Export assessment methods and properties per device](get-assessment-methods-properties.md).</span></span>

### <a name="05252021"></a><span data-ttu-id="2895b-113">05.25.2021</span><span class="sxs-lookup"><span data-stu-id="2895b-113">05.25.2021</span></span>

- <span data-ttu-id="2895b-114">デバイスごとに新しい API [Export の評価方法とプロパティを追加しました](get-assessment-methods-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="2895b-114">Added new API [Export assessment methods and properties per device](get-assessment-methods-properties.md).</span></span>

### <a name="03052021"></a><span data-ttu-id="2895b-115">03.05.2021</span><span class="sxs-lookup"><span data-stu-id="2895b-115">03.05.2021</span></span>

- <span data-ttu-id="2895b-116">新しい API: [修復アクティビティのメソッドとプロパティを追加しました](get-remediation-methods-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="2895b-116">Added new API: [Remediation activity methods and properties](get-remediation-methods-properties.md).</span></span>

### <a name="10022021"></a><span data-ttu-id="2895b-117">10.02.2021</span><span class="sxs-lookup"><span data-stu-id="2895b-117">10.02.2021</span></span>

- <span data-ttu-id="2895b-118">新しい API が[追加されました。](batch-update-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="2895b-118">Added new API: [Batch update alerts](batch-update-alerts.md).</span></span>

### <a name="25012021"></a><span data-ttu-id="2895b-119">25.01.2021</span><span class="sxs-lookup"><span data-stu-id="2895b-119">25.01.2021</span></span>

- <span data-ttu-id="2895b-120">Advanced [Hunting API](run-advanced-query-api.md) のレート制限が 1 分あたり 15 ~ 45 要求に更新されました。</span><span class="sxs-lookup"><span data-stu-id="2895b-120">Updated rate limitations for [Advanced Hunting API](run-advanced-query-api.md) from 15 to 45 requests per minute.</span></span>

### <a name="21012021"></a><span data-ttu-id="2895b-121">21.01.2021</span><span class="sxs-lookup"><span data-stu-id="2895b-121">21.01.2021</span></span>

- <span data-ttu-id="2895b-122">新しい API を追加しました: [タグでデバイスを検索します](machine-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="2895b-122">Added new API: [Find devices by tag](machine-tags.md).</span></span>
- <span data-ttu-id="2895b-123">新しい API: インポート [インジケーターを追加しました](import-ti-indicators.md)。</span><span class="sxs-lookup"><span data-stu-id="2895b-123">Added new API: [Import Indicators](import-ti-indicators.md).</span></span>

### <a name="03012021"></a><span data-ttu-id="2895b-124">03.01.2021</span><span class="sxs-lookup"><span data-stu-id="2895b-124">03.01.2021</span></span>

- <span data-ttu-id="2895b-125">更新されたアラート証拠: 追加 ***detectionStatus** _, _*_parentProcessFilePath_*_ および _ *_parentProcessFileName_** プロパティ。</span><span class="sxs-lookup"><span data-stu-id="2895b-125">Updated Alert evidence: added ***detectionStatus** _, _*_parentProcessFilePath_*_ and _ *_parentProcessFileName_** properties.</span></span>
- <span data-ttu-id="2895b-126">更新された [Alert エンティティ](alerts.md): ***detectorId プロパティが追加*** されました。</span><span class="sxs-lookup"><span data-stu-id="2895b-126">Updated [Alert entity](alerts.md): added ***detectorId*** property.</span></span>

### <a name="15122020"></a><span data-ttu-id="2895b-127">15.12.2020</span><span class="sxs-lookup"><span data-stu-id="2895b-127">15.12.2020</span></span>

- <span data-ttu-id="2895b-128">更新された [Device エンティティ](machine.md) : ***IpInterfaces リストが追加*** されました。</span><span class="sxs-lookup"><span data-stu-id="2895b-128">Updated [Device](machine.md) entity: added ***IpInterfaces*** list.</span></span> <span data-ttu-id="2895b-129">「リスト [デバイス」を参照してください](get-machines.md)。</span><span class="sxs-lookup"><span data-stu-id="2895b-129">See [List devices](get-machines.md).</span></span>

### <a name="04112020"></a><span data-ttu-id="2895b-130">04.11.2020</span><span class="sxs-lookup"><span data-stu-id="2895b-130">04.11.2020</span></span>

- <span data-ttu-id="2895b-131">新しい API を追加しました: [デバイスの値を設定します](set-device-value.md)。</span><span class="sxs-lookup"><span data-stu-id="2895b-131">Added new API: [Set device value](set-device-value.md).</span></span>
- <span data-ttu-id="2895b-132">更新された [Device エンティティ](machine.md) : ***deviceValue プロパティが追加*** されました。</span><span class="sxs-lookup"><span data-stu-id="2895b-132">Updated [Device](machine.md) entity: added ***deviceValue*** property.</span></span>

### <a name="01092020"></a><span data-ttu-id="2895b-133">01.09.2020</span><span class="sxs-lookup"><span data-stu-id="2895b-133">01.09.2020</span></span>

- <span data-ttu-id="2895b-134">関連する Evidence を使用して Alert エンティティを展開するオプションを追加しました。</span><span class="sxs-lookup"><span data-stu-id="2895b-134">Added option to expand the Alert entity with its related Evidence.</span></span> <span data-ttu-id="2895b-135">「リスト [通知」を参照してください](get-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="2895b-135">See [List Alerts](get-alerts.md).</span></span>
