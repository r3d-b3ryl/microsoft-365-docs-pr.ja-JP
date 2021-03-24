---
title: Microsoft Defender ATP でのカスタム検出の概要
ms.reviewer: ''
description: 高度な検出を使用してカスタム検出を作成し、アラートを生成する方法を理解する
keywords: カスタム検出、アラート、検出ルール、高度な狩猟、ハント、クエリ、応答アクション、間隔、mdatp、microsoft Defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6c9befcc4b1224cacb2ab4eb8530e30a397aab49
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060905"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="7ccb0-104">カスタム検出の概要</span><span class="sxs-lookup"><span data-stu-id="7ccb0-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7ccb0-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="7ccb0-105">**Applies to:**</span></span>
- [<span data-ttu-id="7ccb0-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7ccb0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="7ccb0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7ccb0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7ccb0-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="7ccb0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7ccb0-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="7ccb0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="7ccb0-110">カスタム検出を使用すると、違反の疑いのあるアクティビティやデバイスの設定ミスなど、さまざまなイベントやシステム状態を事前に監視して対応できます。</span><span class="sxs-lookup"><span data-stu-id="7ccb0-110">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured devices.</span></span> <span data-ttu-id="7ccb0-111">これを行うには、アラートと応答アクションを自動的にトリガーするカスタマイズ可能な検出ルールを使用します。</span><span class="sxs-lookup"><span data-stu-id="7ccb0-111">You can do this with customizable detection rules that automatically trigger alerts and response actions.</span></span>

<span data-ttu-id="7ccb0-112">カスタム検出は高度な検索 [で](advanced-hunting-overview.md)機能します。これは、ネットワークからの広範なイベントおよびシステム情報をカバーする強力で柔軟なクエリ言語を提供します。</span><span class="sxs-lookup"><span data-stu-id="7ccb0-112">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="7ccb0-113">一定の間隔で実行し、アラートを生成し、一致するたびに応答アクションを実行する設定できます。</span><span class="sxs-lookup"><span data-stu-id="7ccb0-113">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="7ccb0-114">カスタム検出では、次の機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="7ccb0-114">Custom detections provide:</span></span>
- <span data-ttu-id="7ccb0-115">高度な検索クエリから構築されたルールベースの検出に関するアラート</span><span class="sxs-lookup"><span data-stu-id="7ccb0-115">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="7ccb0-116">ファイルとデバイスに適用される自動応答アクション</span><span class="sxs-lookup"><span data-stu-id="7ccb0-116">Automatic response actions that apply to files and devices</span></span>

## <a name="related-topics"></a><span data-ttu-id="7ccb0-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="7ccb0-117">Related topics</span></span>
- [<span data-ttu-id="7ccb0-118">検出ルールの作成</span><span class="sxs-lookup"><span data-stu-id="7ccb0-118">Create detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="7ccb0-119">検出ルールの表示と管理</span><span class="sxs-lookup"><span data-stu-id="7ccb0-119">View and manage detection rules</span></span>](custom-detections-manage.md)
- [<span data-ttu-id="7ccb0-120">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="7ccb0-120">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
