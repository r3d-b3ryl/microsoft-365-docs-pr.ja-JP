---
title: Microsoft Managed Desktop アプリの要件
description: ''
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 322a46ce48cce4d080e51f482178462934d5c8f2
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659716"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="1eacd-103">Microsoft Managed Desktop アプリの要件</span><span class="sxs-lookup"><span data-stu-id="1eacd-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="1eacd-104">Microsoft Managed Desktop では、デバイスのパフォーマンス、信頼性、およびサービス性を保証するために、特定の方法を使用してデバイスを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1eacd-104">Microsoft Managed Desktop requires that we manage devices using a specific approach to guarantee the performance, reliability, and serviceability of devices.</span></span>


|<span data-ttu-id="1eacd-105">管理領域</span><span class="sxs-lookup"><span data-stu-id="1eacd-105">Management area</span></span>  |<span data-ttu-id="1eacd-106">Microsoft Managed Desktop のアプローチ</span><span class="sxs-lookup"><span data-stu-id="1eacd-106">Microsoft Managed Desktop approach</span></span>  |
|---------|---------|
|<span data-ttu-id="1eacd-107">デバイスの構成またはポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="1eacd-107">Device configuration or policy management</span></span>     |  <span data-ttu-id="1eacd-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="1eacd-108">Microsoft Intune</span></span>       |
|<span data-ttu-id="1eacd-109">アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="1eacd-109">Application management</span></span>     | <span data-ttu-id="1eacd-110">Microsoft Intune とポータル サイト</span><span class="sxs-lookup"><span data-stu-id="1eacd-110">Microsoft Intune and Company Portal</span></span>        |
|<span data-ttu-id="1eacd-111">ドライバーの展開</span><span class="sxs-lookup"><span data-stu-id="1eacd-111">Driver deployment</span></span>     |  <span data-ttu-id="1eacd-112">デバイス、Windows Update、Intune に含まれるドライバー</span><span class="sxs-lookup"><span data-stu-id="1eacd-112">Drivers included with the device, Windows Update, or Intune</span></span>       |
|<span data-ttu-id="1eacd-113">デバイスのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="1eacd-113">Device security</span></span>     | <span data-ttu-id="1eacd-114">「デバイス [のセキュリティ」を参照してください。](security.md#device-security)</span><span class="sxs-lookup"><span data-stu-id="1eacd-114">See [Device security](security.md#device-security)</span></span>      |
|<span data-ttu-id="1eacd-115">ID およびアクセス管理</span><span class="sxs-lookup"><span data-stu-id="1eacd-115">Identity and access management</span></span>     | <span data-ttu-id="1eacd-116">「Identity [and access management」を参照してください。](security.md#identity-and-access-management)</span><span class="sxs-lookup"><span data-stu-id="1eacd-116">See [Identity and access management](security.md#identity-and-access-management)</span></span>        |
|<span data-ttu-id="1eacd-117">ネットワーク セキュリティ</span><span class="sxs-lookup"><span data-stu-id="1eacd-117">Network security</span></span>     | <span data-ttu-id="1eacd-118">「 [ネットワーク セキュリティ」を参照してください。](security.md#network-security)</span><span class="sxs-lookup"><span data-stu-id="1eacd-118">See [Network security](security.md#network-security)</span></span>        |
|<span data-ttu-id="1eacd-119">情報セキュリティ</span><span class="sxs-lookup"><span data-stu-id="1eacd-119">Information security</span></span>     |  <span data-ttu-id="1eacd-120">「 [情報セキュリティ」を参照してください。](security.md#information-security)</span><span class="sxs-lookup"><span data-stu-id="1eacd-120">See [Information security](security.md#information-security)</span></span>       |
|<span data-ttu-id="1eacd-121">データ復旧</span><span class="sxs-lookup"><span data-stu-id="1eacd-121">Data recovery</span></span>     | <span data-ttu-id="1eacd-122">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="1eacd-122">OneDrive for Business</span></span>        |
|<span data-ttu-id="1eacd-123">コア生産性</span><span class="sxs-lookup"><span data-stu-id="1eacd-123">Core productivity</span></span>     | <span data-ttu-id="1eacd-124">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="1eacd-124">Microsoft 365 Apps for enterprise</span></span>    |
|<span data-ttu-id="1eacd-125">ブラウザー</span><span class="sxs-lookup"><span data-stu-id="1eacd-125">Browser</span></span>     | <span data-ttu-id="1eacd-126">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1eacd-126">Microsoft Edge</span></span>        |




<span data-ttu-id="1eacd-127">Microsoft Managed Desktop は、管理対象デバイスで実行されている他のソフトウェアを監視する場合があります。</span><span class="sxs-lookup"><span data-stu-id="1eacd-127">Microsoft Managed Desktop might monitor other software running on managed devices.</span></span> <span data-ttu-id="1eacd-128">デバイスの管理、デバイスのセキュリティ、パフォーマンス、または信頼性に悪影響を及ぼす場合は、サービス プランに例外を要求 [する必要があります](customizing.md)。</span><span class="sxs-lookup"><span data-stu-id="1eacd-128">If it negatively impacts device management, device security, performance, or reliability, you might be required to request an [exception to the service plan](customizing.md).</span></span>
