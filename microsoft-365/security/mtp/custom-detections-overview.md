---
title: Microsoft 365 Defender のカスタム検出の概要
description: 高度な検索を使用してユーザー設定の検出を作成し、通知を生成する方法について説明します。
keywords: 高度な検索、脅威の探し、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、カスタム検出、スキーマ、kusto、microsoft 365、Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: fe2b9f1b52fa2c8d9031bb58597992f3dda91520
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843914"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="d2587-104">カスタム検出の概要</span><span class="sxs-lookup"><span data-stu-id="d2587-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d2587-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d2587-105">**Applies to:**</span></span>
- <span data-ttu-id="d2587-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d2587-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d2587-107">カスタム検出を使用すると、疑いのある違反のアクティビティや不適切なエンドポイントを含む、さまざまなイベントやシステム状態を事前に監視して応答することができます。</span><span class="sxs-lookup"><span data-stu-id="d2587-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="d2587-108">これは、通知を自動的にトリガーするカスタマイズ可能な検出ルール、および応答アクションによって可能になります。</span><span class="sxs-lookup"><span data-stu-id="d2587-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="d2587-109">カスタム検出は [高度な](advanced-hunting-overview.md)検索を使用して動作します。これにより、さまざまなイベントおよびシステム情報をネットワークからカバーする強力で柔軟なクエリ言語が提供されます。</span><span class="sxs-lookup"><span data-stu-id="d2587-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="d2587-110">それらを定期的に実行するように設定して、一致するものがある場合は警告を生成し、応答アクションを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="d2587-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="d2587-111">カスタム検出の提供:</span><span class="sxs-lookup"><span data-stu-id="d2587-111">Custom detections provide:</span></span>
- <span data-ttu-id="d2587-112">高度な検索クエリから構築されたルールベースの検出に関する警告</span><span class="sxs-lookup"><span data-stu-id="d2587-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="d2587-113">自動応答アクション</span><span class="sxs-lookup"><span data-stu-id="d2587-113">Automatic response actions</span></span>

## <a name="related-topic"></a><span data-ttu-id="d2587-114">関連トピック</span><span class="sxs-lookup"><span data-stu-id="d2587-114">Related topic</span></span>
- [<span data-ttu-id="d2587-115">カスタム検出ルールを作成および管理する</span><span class="sxs-lookup"><span data-stu-id="d2587-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="d2587-116">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="d2587-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
