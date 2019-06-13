---
title: Microsoft マネージドデスクトップアプリの要件
description: ''
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: ded8bcfd87a6b430dfc4be055a582b482872b104
ms.sourcegitcommit: 498340389e1c34f49f0b2da382c23c8d5334ae47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2019
ms.locfileid: "34913018"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="f15e5-103">Microsoft マネージドデスクトップアプリの要件</span><span class="sxs-lookup"><span data-stu-id="f15e5-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="f15e5-104">Microsoft マネージドデスクトップデバイスのパフォーマンス、信頼性、および保守性を保証するために、お客様の基幹業務アプリはエンドユーザーの環境に重大な影響を与えたり、セキュリティの態勢を変更したりする必要がありません。</span><span class="sxs-lookup"><span data-stu-id="f15e5-104">In order to guarantee the performance, reliability, and serviceability of Microsoft Managed Desktop devices a customer’s line of business apps must not seriously impact end user experience or modify the security stance.</span></span> <span data-ttu-id="f15e5-105">そのため、Microsoft マネージドデスクトップデバイスに展開する基幹業務アプリケーションは、このトピックの要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f15e5-105">Consequently, line of business applications that you want to deploy to Microsoft Managed Desktop devices must meet the requirements in this topic.</span></span>

## <a name="application-condition"></a><span data-ttu-id="f15e5-106">アプリケーションの条件</span><span class="sxs-lookup"><span data-stu-id="f15e5-106">Application condition</span></span>

<span data-ttu-id="f15e5-107">アプリケーションが Microsoft マネージドデスクトップ環境に悪影響を与えることは重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="f15e5-107">It’s important that applications don’t adversely impact the Microsoft Managed Desktop environment.</span></span> <span data-ttu-id="f15e5-108">アプリケーションを展開するためにアプリケーションが満たす必要がある要件を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f15e5-108">The following are the requirements that an application must meet for an application to be deployed.</span></span> <span data-ttu-id="f15e5-109">特定のアプリケーションまたはドライバーについては、ここに記載されているすべての要件を Microsoft が免除することがあります。</span><span class="sxs-lookup"><span data-stu-id="f15e5-109">For any given application or driver, Microsoft may waive any requirement provided herein.</span></span> <span data-ttu-id="f15e5-110">Microsoft は、Microsoft マネージドデスクトップデバイスのパフォーマンスと信頼性に悪影響を及ぼすアプリケーションまたはドライバーを削除することを決定する場合があります。</span><span class="sxs-lookup"><span data-stu-id="f15e5-110">Microsoft may decide to remove any application or driver that negatively impacts performance and reliability of Microsoft Managed Desktop devices.</span></span>

## <a name="centrally-managed-apps"></a><span data-ttu-id="f15e5-111">一元管理されたアプリ</span><span class="sxs-lookup"><span data-stu-id="f15e5-111">Centrally managed apps</span></span>

<span data-ttu-id="f15e5-112">Microsoft 管理デバイスにインストールされているすべてのアプリケーションとドライバーは、Microsoft Intune、Microsoft Store、または Microsoft Store for Business を使用して展開する必要があります。可能であれば、Windows Update サービスを使用してドライバーを展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="f15e5-112">All applications and drivers installed on Microsoft Managed Devices must be deployed through Microsoft Intune, the Microsoft Store, or the Microsoft Store for Business; if available, drivers will also be deployed through the Windows Update service.</span></span> 

## <a name="prohibited-app-classes"></a><span data-ttu-id="f15e5-113">禁止されたアプリクラス</span><span class="sxs-lookup"><span data-stu-id="f15e5-113">Prohibited app classes</span></span>

<span data-ttu-id="f15e5-114">Microsoft マネージドデスクトップデバイスでは、特定の種類のアプリケーションが許可されていません。</span><span class="sxs-lookup"><span data-stu-id="f15e5-114">Certain application types are not permitted on Microsoft Managed Desktop devices:</span></span>
- <span data-ttu-id="f15e5-115">サードパーティ製のウイルス対策、セキュリティ、または監査ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="f15e5-115">3rd party anti-virus, security, or audit software</span></span>
- <span data-ttu-id="f15e5-116">Office 365 Pro Plus より前のバージョンの Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="f15e5-116">Versions of Microsoft Office prior to Office 365 Pro Plus</span></span>
- <span data-ttu-id="f15e5-117">他のサードパーティ製ソフトウェアをインストールまたはバンドルするアプリケーション</span><span class="sxs-lookup"><span data-stu-id="f15e5-117">Applications that install or bundle other 3rd party software</span></span>

## <a name="restricted-app-behaviors"></a><span data-ttu-id="f15e5-118">制限されたアプリの動作</span><span class="sxs-lookup"><span data-stu-id="f15e5-118">Restricted app behaviors</span></span>

<span data-ttu-id="f15e5-119">アプリの動作によっては、ユーザーの環境に悪影響を及ぼす場合や、Microsoft マネージドデスクトップデバイスにセキュリティリスクをもたらす場合があります。</span><span class="sxs-lookup"><span data-stu-id="f15e5-119">Certain app behaviors can negatively impact the user experience or may present a security risk to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f15e5-120">次の動作を持つアプリは、Microsoft の特定の除外を使用せずに Microsoft マネージドデスクトップ環境で実行することを許可されていません。</span><span class="sxs-lookup"><span data-stu-id="f15e5-120">Apps with the following behaviors are not permitted to run in the Microsoft Managed Desktop environment without a specific exemption from Microsoft.</span></span>

<span data-ttu-id="f15e5-121">ユーザーの作業状況:</span><span class="sxs-lookup"><span data-stu-id="f15e5-121">User Experience:</span></span>
- <span data-ttu-id="f15e5-122">バックグラウンドサービスをインストールする</span><span class="sxs-lookup"><span data-stu-id="f15e5-122">Install background services</span></span>
- <span data-ttu-id="f15e5-123">Windows スタートアップパスに自分自身を追加する</span><span class="sxs-lookup"><span data-stu-id="f15e5-123">Add itself to the Windows startup path</span></span>
- <span data-ttu-id="f15e5-124">ドライバーに依存するアプリケーション</span><span class="sxs-lookup"><span data-stu-id="f15e5-124">Applications dependent on drivers</span></span>
- <span data-ttu-id="f15e5-125">サードパーティの web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="f15e5-125">3rd party web browsers</span></span>

<span data-ttu-id="f15e5-126">セキュリティ:</span><span class="sxs-lookup"><span data-stu-id="f15e5-126">Security:</span></span>
- <span data-ttu-id="f15e5-127">エンドユーザーの権限を昇格させる</span><span class="sxs-lookup"><span data-stu-id="f15e5-127">Elevate the end user’s privileges</span></span>
- <span data-ttu-id="f15e5-128">アプリストアとして機能するか、組み込みの拡張マネージャーを備えている</span><span class="sxs-lookup"><span data-stu-id="f15e5-128">Act as an app store or have a built-in extension manager</span></span>
- <span data-ttu-id="f15e5-129">既知のセキュリティの脆弱性</span><span class="sxs-lookup"><span data-stu-id="f15e5-129">Have known security vulnerabilities</span></span>
- <span data-ttu-id="f15e5-130">エンドユーザーデータへのアクセスを暗号化または制限する</span><span class="sxs-lookup"><span data-stu-id="f15e5-130">Encrypt or restrict access to end-user data</span></span>
- <span data-ttu-id="f15e5-131">署名されていないか、信頼できるルートにロールアップしない証明書を使用して署名されている</span><span class="sxs-lookup"><span data-stu-id="f15e5-131">Is unsigned or is signed using a certificate which doesn’t roll up to a trusted root</span></span>


## <a name="driver-deployment"></a><span data-ttu-id="f15e5-132">ドライバーの展開</span><span class="sxs-lookup"><span data-stu-id="f15e5-132">Driver deployment</span></span>

<span data-ttu-id="f15e5-133">Microsoft マネージドデスクトップは、Microsoft の管理されたデバイスを使用して Windows Update または受信トレイで利用可能なデバイスドライバーのみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f15e5-133">Microsoft Managed Desktop only supports device drivers that are available through Windows Update or installed inbox with the Microsoft Managed Device.</span></span> 

<span data-ttu-id="f15e5-134">アプリケーションで特定のドライバーを実行する必要がある場合は、制限付きアプリケーションと見なされ、Microsoft マネージドデスクトップに展開するための除外が必要になります。</span><span class="sxs-lookup"><span data-stu-id="f15e5-134">If an application requires a specific driver(s) to run it is considered a Restricted Application and requires an exemption to be deployed to Microsoft Managed Desktop.</span></span> 

