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
ms.openlocfilehash: 90c11caa03249408ba2916d303bcb4a59fbcca8c
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400956"
---
# <a name="device-states"></a><span data-ttu-id="65893-103">デバイス状態</span><span class="sxs-lookup"><span data-stu-id="65893-103">Device states</span></span>

<span data-ttu-id="65893-104">[ **デバイス アクション**] ([管理者のホーム] \> [ **デバイス アクション**]) の一覧にあるデバイスは、次のいずれかの状態になります。</span><span class="sxs-lookup"><span data-stu-id="65893-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="65893-106">**状態**</span><span class="sxs-lookup"><span data-stu-id="65893-106">**Status**</span></span>|<span data-ttu-id="65893-107">**説明**</span><span class="sxs-lookup"><span data-stu-id="65893-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="65893-108">Intune で管理</span><span class="sxs-lookup"><span data-stu-id="65893-108">Managed by Intune</span></span>  <br/> |<span data-ttu-id="65893-109">Microsoft 365 Business Premium によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="65893-109">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="65893-110">インベントリからの削除待ち</span><span class="sxs-lookup"><span data-stu-id="65893-110">Retire pending</span></span>  <br/> |<span data-ttu-id="65893-111">Microsoft 365 Business Premium は、デバイスから会社のデータを削除する準備をしています。</span><span class="sxs-lookup"><span data-stu-id="65893-111">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="65893-112">回収を実行中です</span><span class="sxs-lookup"><span data-stu-id="65893-112">Retire in progress</span></span>  <br/> |<span data-ttu-id="65893-113">Microsoft 365 Business Premium は現在、デバイスから会社データを削除しています。</span><span class="sxs-lookup"><span data-stu-id="65893-113">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="65893-114">インベントリからの削除失敗</span><span class="sxs-lookup"><span data-stu-id="65893-114">Retire failed</span></span>  <br/> | <span data-ttu-id="65893-115">会社データの削除アクションが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="65893-115">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="65893-116">削除の取り消し</span><span class="sxs-lookup"><span data-stu-id="65893-116">Retire canceled</span></span>  <br/> |<span data-ttu-id="65893-117">"削除" アクションが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="65893-117">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="65893-118">ワイプの保留中</span><span class="sxs-lookup"><span data-stu-id="65893-118">Wipe pending</span></span>  <br/> |<span data-ttu-id="65893-119">出荷時のリセットを開始するのを待っています。</span><span class="sxs-lookup"><span data-stu-id="65893-119">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="65893-120">ワイプを実行中です</span><span class="sxs-lookup"><span data-stu-id="65893-120">Wipe in progress</span></span>  <br/> |<span data-ttu-id="65893-121">出荷時のリセットが発行されました。</span><span class="sxs-lookup"><span data-stu-id="65893-121">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="65893-122">ワイプ失敗</span><span class="sxs-lookup"><span data-stu-id="65893-122">Wipe failed</span></span>  <br/> |<span data-ttu-id="65893-123">出荷時の設定に戻すことができませんでした。</span><span class="sxs-lookup"><span data-stu-id="65893-123">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="65893-124">ワイプの取り消し</span><span class="sxs-lookup"><span data-stu-id="65893-124">Wipe canceled</span></span>  <br/> |<span data-ttu-id="65893-125">ファクトリワイプがキャンセルされました。</span><span class="sxs-lookup"><span data-stu-id="65893-125">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="65893-126">異常</span><span class="sxs-lookup"><span data-stu-id="65893-126">Unhealthy</span></span>  <br/> |<span data-ttu-id="65893-127">アクションが保留中 (または進行中) ですが、デバイスは30日以上チェックインされていません。</span><span class="sxs-lookup"><span data-stu-id="65893-127">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="65893-128">削除の保留中</span><span class="sxs-lookup"><span data-stu-id="65893-128">Delete pending</span></span>  <br/> |<span data-ttu-id="65893-129">削除アクションが保留中です。</span><span class="sxs-lookup"><span data-stu-id="65893-129">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="65893-130">検出</span><span class="sxs-lookup"><span data-stu-id="65893-130">Discovered</span></span>  <br/> |<span data-ttu-id="65893-131">Microsoft 365 Business Premium はデバイスを検出しました。</span><span class="sxs-lookup"><span data-stu-id="65893-131">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
