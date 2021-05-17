---
title: デバイス状態
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: ビジネス向け管理ホームの [デバイスアクション] リストで、さまざまなデバイスMicrosoft 365確認します。
ms.openlocfilehash: e6f1b428413d094e0a1ce3afb026528074038736
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578469"
---
# <a name="device-states"></a><span data-ttu-id="5af74-103">デバイス状態</span><span class="sxs-lookup"><span data-stu-id="5af74-103">Device states</span></span>

<span data-ttu-id="5af74-104">この記事は、このMicrosoft 365 Business Premium。</span><span class="sxs-lookup"><span data-stu-id="5af74-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="5af74-105">[ **デバイス アクション**] ([管理者のホーム] \> [ **デバイス アクション**]) の一覧にあるデバイスは、次のいずれかの状態になります。</span><span class="sxs-lookup"><span data-stu-id="5af74-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="5af74-107">**状態**</span><span class="sxs-lookup"><span data-stu-id="5af74-107">**Status**</span></span>|<span data-ttu-id="5af74-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="5af74-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5af74-109">Intune で管理</span><span class="sxs-lookup"><span data-stu-id="5af74-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="5af74-110">管理は、Microsoft 365 Business Premium。</span><span class="sxs-lookup"><span data-stu-id="5af74-110">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="5af74-111">インベントリからの削除待ち</span><span class="sxs-lookup"><span data-stu-id="5af74-111">Retire pending</span></span>  <br/> |<span data-ttu-id="5af74-112">Microsoft 365 Business Premiumから会社のデータを削除する準備が整っています。</span><span class="sxs-lookup"><span data-stu-id="5af74-112">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="5af74-113">回収を実行中です</span><span class="sxs-lookup"><span data-stu-id="5af74-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="5af74-114">Microsoft 365 Business Premium現在、デバイスから会社のデータを削除しています。</span><span class="sxs-lookup"><span data-stu-id="5af74-114">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="5af74-115">インベントリからの削除失敗</span><span class="sxs-lookup"><span data-stu-id="5af74-115">Retire failed</span></span>  <br/> | <span data-ttu-id="5af74-116">会社データの削除アクションが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="5af74-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="5af74-117">取り消しを取り消す</span><span class="sxs-lookup"><span data-stu-id="5af74-117">Retire canceled</span></span>  <br/> |<span data-ttu-id="5af74-118">削除アクションが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="5af74-118">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="5af74-119">ワイプの保留中</span><span class="sxs-lookup"><span data-stu-id="5af74-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="5af74-120">出荷時のリセットを開始するのを待っています。</span><span class="sxs-lookup"><span data-stu-id="5af74-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="5af74-121">ワイプを実行中です</span><span class="sxs-lookup"><span data-stu-id="5af74-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="5af74-122">出荷時のリセットが発行されました。</span><span class="sxs-lookup"><span data-stu-id="5af74-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="5af74-123">ワイプ失敗</span><span class="sxs-lookup"><span data-stu-id="5af74-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="5af74-124">出荷時のリセットが行えなかった。</span><span class="sxs-lookup"><span data-stu-id="5af74-124">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="5af74-125">ワイプがキャンセルされました</span><span class="sxs-lookup"><span data-stu-id="5af74-125">Wipe canceled</span></span>  <br/> |<span data-ttu-id="5af74-126">出荷時のワイプが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="5af74-126">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="5af74-127">異常</span><span class="sxs-lookup"><span data-stu-id="5af74-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="5af74-128">アクションは保留中 (または進行中) ですが、デバイスは 30 日以上チェックインされません。</span><span class="sxs-lookup"><span data-stu-id="5af74-128">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="5af74-129">削除の保留中</span><span class="sxs-lookup"><span data-stu-id="5af74-129">Delete pending</span></span>  <br/> |<span data-ttu-id="5af74-130">削除アクションが保留中です。</span><span class="sxs-lookup"><span data-stu-id="5af74-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="5af74-131">検出</span><span class="sxs-lookup"><span data-stu-id="5af74-131">Discovered</span></span>  <br/> |<span data-ttu-id="5af74-132">Microsoft 365 Business Premiumデバイスが検出されました。</span><span class="sxs-lookup"><span data-stu-id="5af74-132">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
