---
title: デバイス状態
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Microsoft 365 Business の管理者ホームの [デバイスの操作] リストに表示されるさまざまなデバイスの状態について説明します。
ms.openlocfilehash: bed1610814ca0d60adb4b4b3d0018e3e7e6d763f
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2020
ms.locfileid: "42560822"
---
# <a name="device-states"></a><span data-ttu-id="4595f-103">デバイス状態</span><span class="sxs-lookup"><span data-stu-id="4595f-103">Device states</span></span>

<span data-ttu-id="4595f-104">[ **デバイス アクション**] ([管理者のホーム] \> [ **デバイス アクション**]) の一覧にあるデバイスは、次のいずれかの状態になります。</span><span class="sxs-lookup"><span data-stu-id="4595f-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="4595f-106">**状態**</span><span class="sxs-lookup"><span data-stu-id="4595f-106">**Status**</span></span>|<span data-ttu-id="4595f-107">**説明**</span><span class="sxs-lookup"><span data-stu-id="4595f-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4595f-108">Intune で管理</span><span class="sxs-lookup"><span data-stu-id="4595f-108">Managed by Intune</span></span>  <br/> |<span data-ttu-id="4595f-109">Microsoft 365 Business で管理されています。</span><span class="sxs-lookup"><span data-stu-id="4595f-109">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="4595f-110">インベントリからの削除待ち</span><span class="sxs-lookup"><span data-stu-id="4595f-110">Retire pending</span></span>  <br/> |<span data-ttu-id="4595f-111">Microsoft 365 Business はデバイスから会社データを削除する準備をしています。</span><span class="sxs-lookup"><span data-stu-id="4595f-111">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="4595f-112">回収を実行中です</span><span class="sxs-lookup"><span data-stu-id="4595f-112">Retire in progress</span></span>  <br/> |<span data-ttu-id="4595f-113">現在、Microsoft 365 Business はデバイスから会社データを削除しています。</span><span class="sxs-lookup"><span data-stu-id="4595f-113">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="4595f-114">インベントリからの削除失敗</span><span class="sxs-lookup"><span data-stu-id="4595f-114">Retire failed</span></span>  <br/> | <span data-ttu-id="4595f-115">会社データの削除アクションが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="4595f-115">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="4595f-116">削除の取り消し</span><span class="sxs-lookup"><span data-stu-id="4595f-116">Retire canceled</span></span>  <br/> |<span data-ttu-id="4595f-117">"削除" アクションが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="4595f-117">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="4595f-118">ワイプの保留中</span><span class="sxs-lookup"><span data-stu-id="4595f-118">Wipe pending</span></span>  <br/> |<span data-ttu-id="4595f-119">出荷時のリセットを開始するのを待っています。</span><span class="sxs-lookup"><span data-stu-id="4595f-119">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="4595f-120">ワイプを実行中です</span><span class="sxs-lookup"><span data-stu-id="4595f-120">Wipe in progress</span></span>  <br/> |<span data-ttu-id="4595f-121">出荷時のリセットが発行されました。</span><span class="sxs-lookup"><span data-stu-id="4595f-121">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="4595f-122">ワイプ失敗</span><span class="sxs-lookup"><span data-stu-id="4595f-122">Wipe failed</span></span>  <br/> |<span data-ttu-id="4595f-123">出荷時の設定に戻すことができませんでした。</span><span class="sxs-lookup"><span data-stu-id="4595f-123">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="4595f-124">ワイプの取り消し</span><span class="sxs-lookup"><span data-stu-id="4595f-124">Wipe canceled</span></span>  <br/> |<span data-ttu-id="4595f-125">ファクトリワイプがキャンセルされました。</span><span class="sxs-lookup"><span data-stu-id="4595f-125">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="4595f-126">異常</span><span class="sxs-lookup"><span data-stu-id="4595f-126">Unhealthy</span></span>  <br/> |<span data-ttu-id="4595f-127">アクションが保留中 (または進行中) ですが、デバイスは30日以上チェックインされていません。</span><span class="sxs-lookup"><span data-stu-id="4595f-127">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="4595f-128">削除の保留中</span><span class="sxs-lookup"><span data-stu-id="4595f-128">Delete pending</span></span>  <br/> |<span data-ttu-id="4595f-129">削除アクションが保留中です。</span><span class="sxs-lookup"><span data-stu-id="4595f-129">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="4595f-130">検出</span><span class="sxs-lookup"><span data-stu-id="4595f-130">Discovered</span></span>  <br/> |<span data-ttu-id="4595f-131">Microsoft 365 Business はデバイスを検出しました。</span><span class="sxs-lookup"><span data-stu-id="4595f-131">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
