---
title: ユーザー リソースの種類
description: ユーザーに関連する最近の Microsoft Defender for Endpoint アラートを取得します。
keywords: apis, graph api, supported apis, get, alerts, recent
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
ms.openlocfilehash: e3b2a567a953883d1d0ecd062159bfee4135dc85
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51197959"
---
# <a name="user-resource-type"></a><span data-ttu-id="9bf31-104">ユーザー リソースの種類</span><span class="sxs-lookup"><span data-stu-id="9bf31-104">User resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9bf31-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="9bf31-105">**Applies to:**</span></span>
- [<span data-ttu-id="9bf31-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9bf31-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="9bf31-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9bf31-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9bf31-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="9bf31-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9bf31-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="9bf31-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="9bf31-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="9bf31-110">Method</span></span>|<span data-ttu-id="9bf31-111">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="9bf31-111">Return Type</span></span> |<span data-ttu-id="9bf31-112">説明</span><span class="sxs-lookup"><span data-stu-id="9bf31-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="9bf31-113">ユーザー関連のアラートの一覧表示</span><span class="sxs-lookup"><span data-stu-id="9bf31-113">List User related alerts</span></span>](get-user-related-alerts.md) | <span data-ttu-id="9bf31-114">[alert](alerts.md) コレクション</span><span class="sxs-lookup"><span data-stu-id="9bf31-114">[alert](alerts.md) collection</span></span> |  <span data-ttu-id="9bf31-115">ユーザーに関連付けられているすべてのアラートを一覧表示 [します](user.md)。</span><span class="sxs-lookup"><span data-stu-id="9bf31-115">List all the alerts that are associated with a [user](user.md).</span></span>
[<span data-ttu-id="9bf31-116">リスト ユーザー関連のデバイス</span><span class="sxs-lookup"><span data-stu-id="9bf31-116">List User related devices</span></span>](get-user-related-machines.md) | <span data-ttu-id="9bf31-117">[machine](machine.md) コレクション</span><span class="sxs-lookup"><span data-stu-id="9bf31-117">[machine](machine.md) collection</span></span> | <span data-ttu-id="9bf31-118">ユーザーがログオンしていたすべてのデバイスを一覧表示 [します](user.md)。</span><span class="sxs-lookup"><span data-stu-id="9bf31-118">List all the devices that were logged on by a [user](user.md).</span></span>
