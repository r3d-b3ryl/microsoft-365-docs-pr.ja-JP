---
title: Microsoft 365 Defender のカスタム検出の概要
description: 高度な検索を使用してカスタム検出を作成し、アラートを生成する方法を理解する
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、カスタム検出、スキーマ、kusto、Microsoft 365、Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ae9617a55fd5efb40a3aba07202ebfb1494d4db6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928810"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="b39d0-104">カスタム検出の概要</span><span class="sxs-lookup"><span data-stu-id="b39d0-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b39d0-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="b39d0-105">**Applies to:**</span></span>
- <span data-ttu-id="b39d0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b39d0-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="b39d0-107">カスタム検出を使用すると、侵害の疑いのあるアクティビティや正しく構成されていないエンドポイントなど、さまざまなイベントやシステム状態を事前に監視して対応できます。</span><span class="sxs-lookup"><span data-stu-id="b39d0-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="b39d0-108">これは、アラートと応答アクションを自動的にトリガーするカスタマイズ可能な検出ルールによって可能になります。</span><span class="sxs-lookup"><span data-stu-id="b39d0-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="b39d0-109">カスタム検出は高度な検索 [に](advanced-hunting-overview.md)対応します。強力で柔軟なクエリ言語が提供され、ネットワークから広範なイベントおよびシステム情報を扱います。</span><span class="sxs-lookup"><span data-stu-id="b39d0-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="b39d0-110">一致する場合は常に、一定の間隔で実行し、アラートを生成し、対応アクションを実行する設定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b39d0-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="b39d0-111">カスタム検出では、次の機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="b39d0-111">Custom detections provide:</span></span>
- <span data-ttu-id="b39d0-112">高度な検索クエリから構築されたルールベースの検出に関するアラート</span><span class="sxs-lookup"><span data-stu-id="b39d0-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="b39d0-113">自動応答アクション</span><span class="sxs-lookup"><span data-stu-id="b39d0-113">Automatic response actions</span></span>

## <a name="related-topic"></a><span data-ttu-id="b39d0-114">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b39d0-114">Related topic</span></span>
- [<span data-ttu-id="b39d0-115">カスタム検出ルールの作成と管理</span><span class="sxs-lookup"><span data-stu-id="b39d0-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="b39d0-116">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="b39d0-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
