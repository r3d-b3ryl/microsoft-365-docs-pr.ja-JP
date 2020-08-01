---
title: Microsoft マネージドデスクトップアプリの要件
description: ''
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: bd775e201f5fec556941ae0e8e7b025744da0419
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529435"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="ce661-103">Microsoft マネージドデスクトップアプリの要件</span><span class="sxs-lookup"><span data-stu-id="ce661-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="ce661-104">Microsoft マネージドデスクトップでは、デバイスのパフォーマンス、信頼性、および保守性を保証するために、特定のアプローチを使用してデバイスを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce661-104">Microsoft Managed Desktop requires that we manage devices using a specific approach to guarantee the performance, reliability, and serviceability of devices.</span></span> <span data-ttu-id="ce661-105">次の領域に対して Microsoft マネージドデスクトップで行われたアプローチが機能しないことがわかっている場合は、[サービスプランに対する例外](customizing.md)を要求できます。</span><span class="sxs-lookup"><span data-stu-id="ce661-105">If you’re sure that the approach taken by Microsoft Managed Desktop for the areas below will not work for you, you can request an [exception to the service plan](customizing.md).</span></span>


|<span data-ttu-id="ce661-106">管理領域</span><span class="sxs-lookup"><span data-stu-id="ce661-106">Management area</span></span>  |<span data-ttu-id="ce661-107">Microsoft マネージドデスクトップアプローチ</span><span class="sxs-lookup"><span data-stu-id="ce661-107">Microsoft Managed Desktop approach</span></span>  |
|---------|---------|
|<span data-ttu-id="ce661-108">デバイス構成またはポリシー管理</span><span class="sxs-lookup"><span data-stu-id="ce661-108">Device configuration or policy management</span></span>     |  <span data-ttu-id="ce661-109">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ce661-109">Microsoft Intune</span></span>       |
|<span data-ttu-id="ce661-110">アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="ce661-110">Application management</span></span>     | <span data-ttu-id="ce661-111">Microsoft Intune およびポータルサイト</span><span class="sxs-lookup"><span data-stu-id="ce661-111">Microsoft Intune and Company Portal</span></span>        |
|<span data-ttu-id="ce661-112">ドライバーの展開</span><span class="sxs-lookup"><span data-stu-id="ce661-112">Driver deployment</span></span>     |  <span data-ttu-id="ce661-113">デバイス、Windows Update、または Intune に含まれるドライバー</span><span class="sxs-lookup"><span data-stu-id="ce661-113">Drivers included with the device, Windows Update, or Intune</span></span>       |
|<span data-ttu-id="ce661-114">デバイスのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="ce661-114">Device security</span></span>     | <span data-ttu-id="ce661-115">「[デバイスのセキュリティ](security.md#device-security)」を参照</span><span class="sxs-lookup"><span data-stu-id="ce661-115">See [Device security](security.md#device-security)</span></span>      |
|<span data-ttu-id="ce661-116">ID およびアクセス管理</span><span class="sxs-lookup"><span data-stu-id="ce661-116">Identity and access management</span></span>     | <span data-ttu-id="ce661-117">[Id およびアクセス管理を](security.md#identity-and-access-management)参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce661-117">See [Identity and access management](security.md#identity-and-access-management)</span></span>        |
|<span data-ttu-id="ce661-118">ネットワーク セキュリティ</span><span class="sxs-lookup"><span data-stu-id="ce661-118">Network security</span></span>     | <span data-ttu-id="ce661-119">「[ネットワークセキュリティ](security.md#network-security)」を参照</span><span class="sxs-lookup"><span data-stu-id="ce661-119">See [Network security](security.md#network-security)</span></span>        |
|<span data-ttu-id="ce661-120">情報セキュリティ</span><span class="sxs-lookup"><span data-stu-id="ce661-120">Information security</span></span>     |  <span data-ttu-id="ce661-121">[情報セキュリティ](security.md#information-security)を参照する</span><span class="sxs-lookup"><span data-stu-id="ce661-121">See [Information security](security.md#information-security)</span></span>       |
|<span data-ttu-id="ce661-122">データの回復</span><span class="sxs-lookup"><span data-stu-id="ce661-122">Data recovery</span></span>     | <span data-ttu-id="ce661-123">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="ce661-123">OneDrive for Business</span></span>        |
|<span data-ttu-id="ce661-124">コア生産性</span><span class="sxs-lookup"><span data-stu-id="ce661-124">Core productivity</span></span>     | <span data-ttu-id="ce661-125">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="ce661-125">Microsoft 365 Apps for enterprise</span></span>    |
|<span data-ttu-id="ce661-126">ブラウザー</span><span class="sxs-lookup"><span data-stu-id="ce661-126">Browser</span></span>     | <span data-ttu-id="ce661-127">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ce661-127">Microsoft Edge</span></span>        |




<span data-ttu-id="ce661-128">Microsoft マネージドデスクトップでは、管理対象デバイス上で実行されている他のソフトウェアを監視できます。</span><span class="sxs-lookup"><span data-stu-id="ce661-128">Microsoft Managed Desktop might monitor other software running on managed devices.</span></span> <span data-ttu-id="ce661-129">システムのセキュリティ、パフォーマンス、または信頼性に悪影響を及ぼす場合は、サービスプランに対する例外を要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce661-129">If it negatively impacts system security, performance, or reliability, you might be required to request an exception to the service plan.</span></span>


