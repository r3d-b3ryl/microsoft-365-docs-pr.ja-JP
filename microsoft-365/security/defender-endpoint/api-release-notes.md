---
title: Microsoft Defender for Endpoint API リリース ノート
description: Microsoft Defender for Endpoint セットの API に対して行われた更新プログラムのリリース ノート。
keywords: エンドポイント API リリース ノート、mde、api、mdatp api、更新プログラム、メモ、リリース用 microsoft Defender
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
ms.technology: mde
ms.openlocfilehash: e37841fa17a5998c431c6a76b878f20ef1b06d10
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51061804"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a><span data-ttu-id="c537b-104">Microsoft Defender for Endpoint API リリース ノート</span><span class="sxs-lookup"><span data-stu-id="c537b-104">Microsoft Defender for Endpoint API release notes</span></span>

<span data-ttu-id="c537b-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="c537b-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="c537b-106">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="c537b-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c537b-107">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="c537b-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="c537b-108">次の情報は、Microsoft Defender for Endpoint API に対して行われた更新プログラムと、その更新日を示しています。</span><span class="sxs-lookup"><span data-stu-id="c537b-108">The following information lists the updates made to the Microsoft Defender for Endpoint APIs and the dates they were made.</span></span>


> [!TIP]
> <span data-ttu-id="c537b-109">RSS フィード: 次の URL をコピーしてフィード リーダーに貼り付け、このページが更新された場合に通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c537b-109">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span> 
>```
>https://docs.microsoft.com/api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
>```


### <a name="10022021"></a><span data-ttu-id="c537b-110">10.02.2021</span><span class="sxs-lookup"><span data-stu-id="c537b-110">10.02.2021</span></span>
<hr>

- <span data-ttu-id="c537b-111">新しい API が[追加されました。](batch-update-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="c537b-111">Added new API: [Batch update alerts](batch-update-alerts.md).</span></span> 

<br>

### <a name="25012021"></a><span data-ttu-id="c537b-112">25.01.2021</span><span class="sxs-lookup"><span data-stu-id="c537b-112">25.01.2021</span></span>
<hr>

- <span data-ttu-id="c537b-113">Advanced [Hunting API](run-advanced-query-api.md) のレート制限が 1 分あたり 15 ~ 45 要求に更新されました。</span><span class="sxs-lookup"><span data-stu-id="c537b-113">Updated rate limitations for [Advanced Hunting API](run-advanced-query-api.md) from 15 to 45 requests per minute.</span></span> 

<br>

### <a name="21012021"></a><span data-ttu-id="c537b-114">21.01.2021</span><span class="sxs-lookup"><span data-stu-id="c537b-114">21.01.2021</span></span>
<hr>

- <span data-ttu-id="c537b-115">新しい API を追加しました: [タグでデバイスを検索します](machine-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="c537b-115">Added new API: [Find devices by tag](machine-tags.md).</span></span> 
- <span data-ttu-id="c537b-116">新しい API: インポート [インジケーターを追加しました](import-ti-indicators.md)。</span><span class="sxs-lookup"><span data-stu-id="c537b-116">Added new API: [Import Indicators](import-ti-indicators.md).</span></span> 

<br>

### <a name="03012021"></a><span data-ttu-id="c537b-117">03.01.2021</span><span class="sxs-lookup"><span data-stu-id="c537b-117">03.01.2021</span></span>
<hr>

- <span data-ttu-id="c537b-118">更新されたアラート証拠: 追加 ***detectionStatus** _, _*_parentProcessFilePath_*_ および _ *_parentProcessFileName_** プロパティ。</span><span class="sxs-lookup"><span data-stu-id="c537b-118">Updated Alert evidence: added ***detectionStatus** _, _*_parentProcessFilePath_*_ and _ *_parentProcessFileName_** properties.</span></span>
- <span data-ttu-id="c537b-119">更新された [Alert エンティティ](alerts.md): ***detectorId プロパティが追加*** されました。</span><span class="sxs-lookup"><span data-stu-id="c537b-119">Updated [Alert entity](alerts.md): added ***detectorId*** property.</span></span>

<br>

### <a name="15122020"></a><span data-ttu-id="c537b-120">15.12.2020</span><span class="sxs-lookup"><span data-stu-id="c537b-120">15.12.2020</span></span>
<hr>

- <span data-ttu-id="c537b-121">更新された [Device エンティティ](machine.md) : ***IpInterfaces リストが追加*** されました。</span><span class="sxs-lookup"><span data-stu-id="c537b-121">Updated [Device](machine.md) entity: added ***IpInterfaces*** list.</span></span> <span data-ttu-id="c537b-122">「リスト [デバイス」を参照してください](get-machines.md)。</span><span class="sxs-lookup"><span data-stu-id="c537b-122">See [List devices](get-machines.md).</span></span>

<br>

### <a name="04112020"></a><span data-ttu-id="c537b-123">04.11.2020</span><span class="sxs-lookup"><span data-stu-id="c537b-123">04.11.2020</span></span>
<hr>

- <span data-ttu-id="c537b-124">新しい API を追加しました: [デバイスの値を設定します](set-device-value.md)。</span><span class="sxs-lookup"><span data-stu-id="c537b-124">Added new API: [Set device value](set-device-value.md).</span></span>
- <span data-ttu-id="c537b-125">更新された [Device エンティティ](machine.md) : ***deviceValue プロパティが追加*** されました。</span><span class="sxs-lookup"><span data-stu-id="c537b-125">Updated [Device](machine.md) entity: added ***deviceValue*** property.</span></span>

<br>

### <a name="01092020"></a><span data-ttu-id="c537b-126">01.09.2020</span><span class="sxs-lookup"><span data-stu-id="c537b-126">01.09.2020</span></span>
<hr>

- <span data-ttu-id="c537b-127">関連する Evidence を使用して Alert エンティティを展開するオプションを追加しました。</span><span class="sxs-lookup"><span data-stu-id="c537b-127">Added option to expand the Alert entity with its related Evidence.</span></span> <span data-ttu-id="c537b-128">「リスト [通知」を参照してください](get-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="c537b-128">See [List Alerts](get-alerts.md).</span></span>

<br>
<br>