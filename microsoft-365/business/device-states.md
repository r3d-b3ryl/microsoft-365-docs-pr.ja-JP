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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Microsoft 365 Business のデバイスの状態について説明します。
ms.openlocfilehash: 26b218cb7b6a14f17e33d34a2e712b06ac814c0c
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42065770"
---
# <a name="device-states"></a><span data-ttu-id="71b8a-103">デバイス状態</span><span class="sxs-lookup"><span data-stu-id="71b8a-103">Device states</span></span>

<span data-ttu-id="71b8a-104">[ **デバイス アクション**] ([管理者のホーム] \> [ **デバイス アクション**]) の一覧にあるデバイスは、次のいずれかの状態になります。</span><span class="sxs-lookup"><span data-stu-id="71b8a-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="71b8a-106">**状態**</span><span class="sxs-lookup"><span data-stu-id="71b8a-106">**Status**</span></span>|<span data-ttu-id="71b8a-107">**説明**</span><span class="sxs-lookup"><span data-stu-id="71b8a-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="71b8a-108">Intune で管理</span><span class="sxs-lookup"><span data-stu-id="71b8a-108">Managed by Intune</span></span>  <br/> |<span data-ttu-id="71b8a-109">Microsoft 365 Business で管理されています。</span><span class="sxs-lookup"><span data-stu-id="71b8a-109">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="71b8a-110">インベントリからの削除待ち</span><span class="sxs-lookup"><span data-stu-id="71b8a-110">Retire pending</span></span>  <br/> |<span data-ttu-id="71b8a-111">Microsoft 365 Business はデバイスから会社データを削除する準備をしています。</span><span class="sxs-lookup"><span data-stu-id="71b8a-111">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="71b8a-112">回収を実行中です</span><span class="sxs-lookup"><span data-stu-id="71b8a-112">Retire in progress</span></span>  <br/> |<span data-ttu-id="71b8a-113">現在、Microsoft 365 Business はデバイスから会社データを削除しています。</span><span class="sxs-lookup"><span data-stu-id="71b8a-113">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="71b8a-114">インベントリからの削除失敗</span><span class="sxs-lookup"><span data-stu-id="71b8a-114">Retire failed</span></span>  <br/> | <span data-ttu-id="71b8a-115">会社データの削除アクションが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="71b8a-115">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="71b8a-116">削除の取り消し</span><span class="sxs-lookup"><span data-stu-id="71b8a-116">Retire canceled</span></span>  <br/> |<span data-ttu-id="71b8a-117">"削除" アクションが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="71b8a-117">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="71b8a-118">ワイプの保留中</span><span class="sxs-lookup"><span data-stu-id="71b8a-118">Wipe pending</span></span>  <br/> |<span data-ttu-id="71b8a-119">出荷時のリセットを開始するのを待っています。</span><span class="sxs-lookup"><span data-stu-id="71b8a-119">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="71b8a-120">ワイプを実行中です</span><span class="sxs-lookup"><span data-stu-id="71b8a-120">Wipe in progress</span></span>  <br/> |<span data-ttu-id="71b8a-121">出荷時のリセットが発行されました。</span><span class="sxs-lookup"><span data-stu-id="71b8a-121">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="71b8a-122">ワイプ失敗</span><span class="sxs-lookup"><span data-stu-id="71b8a-122">Wipe failed</span></span>  <br/> |<span data-ttu-id="71b8a-123">出荷時の設定に戻すことができませんでした。</span><span class="sxs-lookup"><span data-stu-id="71b8a-123">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="71b8a-124">ワイプの取り消し</span><span class="sxs-lookup"><span data-stu-id="71b8a-124">Wipe canceled</span></span>  <br/> |<span data-ttu-id="71b8a-125">ファクトリワイプがキャンセルされました。</span><span class="sxs-lookup"><span data-stu-id="71b8a-125">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="71b8a-126">異常</span><span class="sxs-lookup"><span data-stu-id="71b8a-126">Unhealthy</span></span>  <br/> |<span data-ttu-id="71b8a-127">アクションが保留中 (または進行中) ですが、デバイスは30日以上チェックインされていません。</span><span class="sxs-lookup"><span data-stu-id="71b8a-127">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="71b8a-128">削除の保留中</span><span class="sxs-lookup"><span data-stu-id="71b8a-128">Delete pending</span></span>  <br/> |<span data-ttu-id="71b8a-129">削除アクションが保留中です。</span><span class="sxs-lookup"><span data-stu-id="71b8a-129">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="71b8a-130">検出</span><span class="sxs-lookup"><span data-stu-id="71b8a-130">Discovered</span></span>  <br/> |<span data-ttu-id="71b8a-131">Microsoft 365 Business はデバイスを検出しました。</span><span class="sxs-lookup"><span data-stu-id="71b8a-131">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
