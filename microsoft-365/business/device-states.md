---
title: デバイス状態
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Microsoft 365 Business のデバイスの状態について説明します。
ms.openlocfilehash: 15114835a5014f5bfac600eac79bcdffdaec481a
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32276985"
---
# <a name="device-states"></a><span data-ttu-id="2d526-103">デバイス状態</span><span class="sxs-lookup"><span data-stu-id="2d526-103">Device states</span></span>

## <a name="device-states"></a><span data-ttu-id="2d526-104">デバイス状態</span><span class="sxs-lookup"><span data-stu-id="2d526-104">Device states</span></span>

<span data-ttu-id="2d526-105">[ **デバイス アクション**] ([管理者のホーム] \> [ **デバイス アクション**]) の一覧にあるデバイスは、次のいずれかの状態になります。</span><span class="sxs-lookup"><span data-stu-id="2d526-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="2d526-107">**状態**</span><span class="sxs-lookup"><span data-stu-id="2d526-107">**Status**</span></span>|<span data-ttu-id="2d526-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="2d526-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2d526-109">Intune で管理</span><span class="sxs-lookup"><span data-stu-id="2d526-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="2d526-110">Microsoft 365 Business で管理されています。</span><span class="sxs-lookup"><span data-stu-id="2d526-110">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="2d526-111">インベントリからの削除待ち</span><span class="sxs-lookup"><span data-stu-id="2d526-111">Retire pending</span></span>  <br/> |<span data-ttu-id="2d526-112">Microsoft 365 Business はデバイスから会社データを削除する準備をしています。</span><span class="sxs-lookup"><span data-stu-id="2d526-112">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="2d526-113">回収を実行中です</span><span class="sxs-lookup"><span data-stu-id="2d526-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="2d526-114">現在、Microsoft 365 Business はデバイスから会社データを削除しています。</span><span class="sxs-lookup"><span data-stu-id="2d526-114">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="2d526-115">インベントリからの削除失敗</span><span class="sxs-lookup"><span data-stu-id="2d526-115">Retire failed</span></span>  <br/> | <span data-ttu-id="2d526-116">会社データの削除アクションが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="2d526-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="2d526-117">インベントリからの削除がキャンセルされました</span><span class="sxs-lookup"><span data-stu-id="2d526-117">Retire cancelled</span></span>  <br/> |<span data-ttu-id="2d526-118">インベントリからの削除がキャンセルされました。</span><span class="sxs-lookup"><span data-stu-id="2d526-118">Retire action was cancelled.</span></span>  <br/> |
|<span data-ttu-id="2d526-119">ワイプの保留中</span><span class="sxs-lookup"><span data-stu-id="2d526-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="2d526-120">出荷時のリセットを開始するのを待っています。</span><span class="sxs-lookup"><span data-stu-id="2d526-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="2d526-121">ワイプを実行中です</span><span class="sxs-lookup"><span data-stu-id="2d526-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="2d526-122">出荷時のリセットが発行されました。</span><span class="sxs-lookup"><span data-stu-id="2d526-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="2d526-123">ワイプ失敗</span><span class="sxs-lookup"><span data-stu-id="2d526-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="2d526-124">出荷時の設定へのリセットを実行できませんでした。</span><span class="sxs-lookup"><span data-stu-id="2d526-124">Couldn't perform factory reset.</span></span>  <br/> |
|<span data-ttu-id="2d526-125">ワイプがキャンセルされました</span><span class="sxs-lookup"><span data-stu-id="2d526-125">Wipe cancelled</span></span>  <br/> |<span data-ttu-id="2d526-126">出荷時のワイプがキャンセルされました。</span><span class="sxs-lookup"><span data-stu-id="2d526-126">Factory wipe was cancelled.</span></span>  <br/> |
|<span data-ttu-id="2d526-127">異常</span><span class="sxs-lookup"><span data-stu-id="2d526-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="2d526-128">アクションは保留中 (または進行中) ですが、デバイスは 30 日以上チェックインされていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="2d526-128">This means that an action is pending (or in progress) but the device has not checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="2d526-129">削除の保留中</span><span class="sxs-lookup"><span data-stu-id="2d526-129">Delete pending</span></span>  <br/> |<span data-ttu-id="2d526-130">削除アクションが保留中です。</span><span class="sxs-lookup"><span data-stu-id="2d526-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="2d526-131">検出</span><span class="sxs-lookup"><span data-stu-id="2d526-131">Discovered</span></span>  <br/> |<span data-ttu-id="2d526-132">Microsoft 365 Business はデバイスを検出しました。</span><span class="sxs-lookup"><span data-stu-id="2d526-132">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
