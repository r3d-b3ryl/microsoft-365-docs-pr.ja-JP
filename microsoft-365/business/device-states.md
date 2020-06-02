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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Microsoft 365 for business の管理者ホームの [デバイスの操作] リストに表示されるさまざまなデバイスの状態について説明します。
ms.openlocfilehash: 64138e2b6ae73c067709cde1912a96615d08ebf1
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2020
ms.locfileid: "44471181"
---
# <a name="device-states"></a><span data-ttu-id="c8ced-103">デバイス状態</span><span class="sxs-lookup"><span data-stu-id="c8ced-103">Device states</span></span>

<span data-ttu-id="c8ced-104">この記事は、Microsoft 365 Business Premium に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c8ced-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="c8ced-105">[ **デバイス アクション**] ([管理者のホーム] \> [ **デバイス アクション**]) の一覧にあるデバイスは、次のいずれかの状態になります。</span><span class="sxs-lookup"><span data-stu-id="c8ced-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="c8ced-107">**状態**</span><span class="sxs-lookup"><span data-stu-id="c8ced-107">**Status**</span></span>|<span data-ttu-id="c8ced-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="c8ced-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c8ced-109">Intune で管理</span><span class="sxs-lookup"><span data-stu-id="c8ced-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="c8ced-110">Microsoft 365 Business Premium によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="c8ced-110">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="c8ced-111">インベントリからの削除待ち</span><span class="sxs-lookup"><span data-stu-id="c8ced-111">Retire pending</span></span>  <br/> |<span data-ttu-id="c8ced-112">Microsoft 365 Business Premium は、デバイスから会社のデータを削除する準備をしています。</span><span class="sxs-lookup"><span data-stu-id="c8ced-112">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="c8ced-113">回収を実行中です</span><span class="sxs-lookup"><span data-stu-id="c8ced-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="c8ced-114">Microsoft 365 Business Premium は現在、デバイスから会社データを削除しています。</span><span class="sxs-lookup"><span data-stu-id="c8ced-114">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="c8ced-115">インベントリからの削除失敗</span><span class="sxs-lookup"><span data-stu-id="c8ced-115">Retire failed</span></span>  <br/> | <span data-ttu-id="c8ced-116">会社データの削除アクションが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="c8ced-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="c8ced-117">削除の取り消し</span><span class="sxs-lookup"><span data-stu-id="c8ced-117">Retire canceled</span></span>  <br/> |<span data-ttu-id="c8ced-118">"削除" アクションが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="c8ced-118">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="c8ced-119">ワイプの保留中</span><span class="sxs-lookup"><span data-stu-id="c8ced-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="c8ced-120">出荷時のリセットを開始するのを待っています。</span><span class="sxs-lookup"><span data-stu-id="c8ced-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="c8ced-121">ワイプを実行中です</span><span class="sxs-lookup"><span data-stu-id="c8ced-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="c8ced-122">出荷時のリセットが発行されました。</span><span class="sxs-lookup"><span data-stu-id="c8ced-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="c8ced-123">ワイプ失敗</span><span class="sxs-lookup"><span data-stu-id="c8ced-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="c8ced-124">出荷時の設定に戻すことができませんでした。</span><span class="sxs-lookup"><span data-stu-id="c8ced-124">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="c8ced-125">ワイプの取り消し</span><span class="sxs-lookup"><span data-stu-id="c8ced-125">Wipe canceled</span></span>  <br/> |<span data-ttu-id="c8ced-126">ファクトリワイプがキャンセルされました。</span><span class="sxs-lookup"><span data-stu-id="c8ced-126">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="c8ced-127">異常</span><span class="sxs-lookup"><span data-stu-id="c8ced-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="c8ced-128">アクションが保留中 (または進行中) ですが、デバイスは30日以上チェックインされていません。</span><span class="sxs-lookup"><span data-stu-id="c8ced-128">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="c8ced-129">削除の保留中</span><span class="sxs-lookup"><span data-stu-id="c8ced-129">Delete pending</span></span>  <br/> |<span data-ttu-id="c8ced-130">削除アクションが保留中です。</span><span class="sxs-lookup"><span data-stu-id="c8ced-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="c8ced-131">検出</span><span class="sxs-lookup"><span data-stu-id="c8ced-131">Discovered</span></span>  <br/> |<span data-ttu-id="c8ced-132">Microsoft 365 Business Premium はデバイスを検出しました。</span><span class="sxs-lookup"><span data-stu-id="c8ced-132">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
