---
title: Defender でのカスタム検出Microsoft 365概要
description: 高度な検出を使用してカスタム検出を作成し、アラートを生成する方法を理解する
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、カスタム検出、スキーマ、kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 748b3534ef1f6ca5736667fc3910bb9fa96d23ff
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952538"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="cde79-104">カスタム検出の概要</span><span class="sxs-lookup"><span data-stu-id="cde79-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="cde79-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="cde79-105">**Applies to:**</span></span>
- <span data-ttu-id="cde79-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cde79-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="cde79-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="cde79-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="cde79-108">カスタム検出を使用すると、侵害の疑いのあるアクティビティや誤った構成されたエンドポイントなど、さまざまなイベントやシステム状態を事前に監視して対応できます。</span><span class="sxs-lookup"><span data-stu-id="cde79-108">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="cde79-109">これは、アラートと応答アクションを自動的にトリガーするカスタマイズ可能な検出ルールによって可能になります。</span><span class="sxs-lookup"><span data-stu-id="cde79-109">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="cde79-110">カスタム検出は高度な検索 [で](advanced-hunting-overview.md)機能します。これは、ネットワークからの広範なイベントおよびシステム情報をカバーする強力で柔軟なクエリ言語を提供します。</span><span class="sxs-lookup"><span data-stu-id="cde79-110">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="cde79-111">一定の間隔で実行し、アラートを生成し、一致するたびに応答アクションを実行する設定できます。</span><span class="sxs-lookup"><span data-stu-id="cde79-111">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="cde79-112">カスタム検出では、次の機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="cde79-112">Custom detections provide:</span></span>
- <span data-ttu-id="cde79-113">高度な検索クエリから構築されたルールベースの検出に関するアラート</span><span class="sxs-lookup"><span data-stu-id="cde79-113">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="cde79-114">自動応答アクション</span><span class="sxs-lookup"><span data-stu-id="cde79-114">Automatic response actions</span></span>

## <a name="see-also"></a><span data-ttu-id="cde79-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="cde79-115">See also</span></span>
- [<span data-ttu-id="cde79-116">カスタム検出ルールの作成と管理</span><span class="sxs-lookup"><span data-stu-id="cde79-116">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="cde79-117">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="cde79-117">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="cde79-118">Microsoft Defender for Endpoint から高度なハンティング クエリを移行する</span><span class="sxs-lookup"><span data-stu-id="cde79-118">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mde.md)
