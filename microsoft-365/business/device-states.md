---
title: デバイス状態
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
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
description: Microsoft 365 のビジネスでのデバイスの状態について説明します。
ms.openlocfilehash: bd6f1ad7f7671d9616fd14d477dfcfb164ff6bd0
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869227"
---
# <a name="device-states"></a><span data-ttu-id="3d15c-103">デバイス状態</span><span class="sxs-lookup"><span data-stu-id="3d15c-103">Device states</span></span>

## <a name="device-states"></a><span data-ttu-id="3d15c-104">デバイス状態</span><span class="sxs-lookup"><span data-stu-id="3d15c-104">Device states</span></span>

<span data-ttu-id="3d15c-105">[ **デバイス アクション**] ([管理者のホーム] \> [ **デバイス アクション**]) の一覧にあるデバイスは、次のいずれかの状態になります。</span><span class="sxs-lookup"><span data-stu-id="3d15c-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="3d15c-107">**状態**</span><span class="sxs-lookup"><span data-stu-id="3d15c-107">**Status**</span></span>|<span data-ttu-id="3d15c-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="3d15c-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3d15c-109">Intune で管理</span><span class="sxs-lookup"><span data-stu-id="3d15c-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="3d15c-110">Microsoft 365 Business で管理されています。</span><span class="sxs-lookup"><span data-stu-id="3d15c-110">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="3d15c-111">インベントリからの削除待ち</span><span class="sxs-lookup"><span data-stu-id="3d15c-111">Retire pending</span></span>  <br/> |<span data-ttu-id="3d15c-112">Microsoft 365 Business はデバイスから会社データを削除する準備をしています。</span><span class="sxs-lookup"><span data-stu-id="3d15c-112">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="3d15c-113">回収を実行中です</span><span class="sxs-lookup"><span data-stu-id="3d15c-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="3d15c-114">現在、Microsoft 365 Business はデバイスから会社データを削除しています。</span><span class="sxs-lookup"><span data-stu-id="3d15c-114">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="3d15c-115">インベントリからの削除失敗</span><span class="sxs-lookup"><span data-stu-id="3d15c-115">Retire failed</span></span>  <br/> | <span data-ttu-id="3d15c-116">会社データの削除アクションが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="3d15c-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="3d15c-117">インベントリからの削除がキャンセルされました</span><span class="sxs-lookup"><span data-stu-id="3d15c-117">Retire cancelled</span></span>  <br/> |<span data-ttu-id="3d15c-118">インベントリからの削除がキャンセルされました。</span><span class="sxs-lookup"><span data-stu-id="3d15c-118">Retire action was cancelled.</span></span>  <br/> |
|<span data-ttu-id="3d15c-119">ワイプの保留中</span><span class="sxs-lookup"><span data-stu-id="3d15c-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="3d15c-120">出荷時のリセットを開始するのを待っています。</span><span class="sxs-lookup"><span data-stu-id="3d15c-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="3d15c-121">ワイプを実行中です</span><span class="sxs-lookup"><span data-stu-id="3d15c-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="3d15c-122">出荷時のリセットが発行されました。</span><span class="sxs-lookup"><span data-stu-id="3d15c-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="3d15c-123">ワイプ失敗</span><span class="sxs-lookup"><span data-stu-id="3d15c-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="3d15c-124">出荷時の設定へのリセットを実行できませんでした。</span><span class="sxs-lookup"><span data-stu-id="3d15c-124">Couldn't perform factory reset.</span></span>  <br/> |
|<span data-ttu-id="3d15c-125">ワイプがキャンセルされました</span><span class="sxs-lookup"><span data-stu-id="3d15c-125">Wipe cancelled</span></span>  <br/> |<span data-ttu-id="3d15c-126">出荷時のワイプがキャンセルされました。</span><span class="sxs-lookup"><span data-stu-id="3d15c-126">Factory wipe was cancelled.</span></span>  <br/> |
|<span data-ttu-id="3d15c-127">異常</span><span class="sxs-lookup"><span data-stu-id="3d15c-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="3d15c-128">アクションは保留中 (または進行中) ですが、デバイスは 30 日以上チェックインされていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="3d15c-128">This means that an action is pending (or in progress) but the device has not checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="3d15c-129">削除の保留中</span><span class="sxs-lookup"><span data-stu-id="3d15c-129">Delete pending</span></span>  <br/> |<span data-ttu-id="3d15c-130">削除アクションが保留中です。</span><span class="sxs-lookup"><span data-stu-id="3d15c-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="3d15c-131">検出</span><span class="sxs-lookup"><span data-stu-id="3d15c-131">Discovered</span></span>  <br/> |<span data-ttu-id="3d15c-132">Microsoft 365 Business はデバイスを検出しました。</span><span class="sxs-lookup"><span data-stu-id="3d15c-132">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
