---
title: Microsoft マネージドデスクトップアプリの要件
description: ''
keywords: microsoft マネージドデスクトップ、microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/08/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: de6cc7d77e023a9d41961e5fbcce060f1bb659ae
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278337"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="dadc0-103">Microsoft マネージドデスクトップアプリの要件</span><span class="sxs-lookup"><span data-stu-id="dadc0-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="dadc0-104">Microsoft マネージドデスクトップデバイスに展開する基幹業務アプリケーションは、このトピックの要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dadc0-104">Line-of-business applications that you want to deploy to Microsoft Managed Desktop devices must meet the requirements in this topic.</span></span> 

## <a name="application-condition"></a><span data-ttu-id="dadc0-105">アプリケーションの条件</span><span class="sxs-lookup"><span data-stu-id="dadc0-105">Application condition</span></span>

<span data-ttu-id="dadc0-106">アプリケーションが Microsoft マネージドデスクトップ環境に悪影響を与えることは重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="dadc0-106">It’s important that applications don’t adversely impact the Microsoft Managed Desktop environment.</span></span> <span data-ttu-id="dadc0-107">以下に、Microsoft が展開するためにアプリケーションが満たす必要がある要件を示します。</span><span class="sxs-lookup"><span data-stu-id="dadc0-107">The following are the requirements that an application must meet in order for Microsoft to deploy it.</span></span> <span data-ttu-id="dadc0-108">特定のアプリケーションまたはドライバーについては、ここに記載されているすべての要件を Microsoft が免除することがあります。</span><span class="sxs-lookup"><span data-stu-id="dadc0-108">For any given application or driver, Microsoft may waive any requirement provided herein.</span></span> <span data-ttu-id="dadc0-109">microsoft は、microsoft マネージドデスクトップデバイスのパフォーマンスと信頼性に悪影響を及ぼすアプリケーションまたはドライバーを削除することを決定する場合があります。</span><span class="sxs-lookup"><span data-stu-id="dadc0-109">Microsoft may decide to remove any application or driver that negatively impacts performance and reliability of Microsoft Managed Desktop devices.</span></span>

## <a name="deployable-using-microsoft-technologies"></a><span data-ttu-id="dadc0-110">Microsoft テクノロジを使用した展開</span><span class="sxs-lookup"><span data-stu-id="dadc0-110">Deployable using Microsoft technologies</span></span>

<span data-ttu-id="dadc0-111">microsoft マネージドデスクトップでは、アプリケーションを展開するために Intune、microsoft store、および microsoft store を使用しています。</span><span class="sxs-lookup"><span data-stu-id="dadc0-111">Microsoft Managed Desktop uses Intune,  Microsoft Store, and  Microsoft Store for Business to deploy applications.</span></span> <span data-ttu-id="dadc0-112">そのため、アプリケーションは、これらのサービスの最新バージョンによって展開可能な方法でパッケージ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dadc0-112">Consequently, applications must be packaged in a manner able to be deployed by the then-current version of those services.</span></span>

## <a name="prohibited-app-classes"></a><span data-ttu-id="dadc0-113">禁止されたアプリクラス</span><span class="sxs-lookup"><span data-stu-id="dadc0-113">Prohibited app classes</span></span>

<span data-ttu-id="dadc0-114">Microsoft マネージドデスクトップデバイスでは、特定の種類のアプリケーションが許可されていません。</span><span class="sxs-lookup"><span data-stu-id="dadc0-114">Certain application types are not permitted on Microsoft Managed Desktop devices:</span></span>
- <span data-ttu-id="dadc0-115">サードパーティ製のウイルス対策、セキュリティ、または監査ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="dadc0-115">3rd party anti-virus, security, or audit software</span></span>
- <span data-ttu-id="dadc0-116">サードパーティの web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="dadc0-116">3rd party web browsers</span></span>
- <span data-ttu-id="dadc0-117">office 365 Pro Plus より前のバージョンの Microsoft office</span><span class="sxs-lookup"><span data-stu-id="dadc0-117">Versions of Microsoft Office prior to Office 365 Pro Plus</span></span>
- <span data-ttu-id="dadc0-118">他のサードパーティ製ソフトウェアをインストールまたはバンドルするアプリケーション</span><span class="sxs-lookup"><span data-stu-id="dadc0-118">Applications that install or bundle other 3rd party software</span></span>

## <a name="restricted-app-behaviors"></a><span data-ttu-id="dadc0-119">制限されたアプリの動作</span><span class="sxs-lookup"><span data-stu-id="dadc0-119">Restricted app behaviors</span></span>

<span data-ttu-id="dadc0-120">アプリケーションの動作によっては、ユーザーの作業に悪影響を及ぼすことがあります。また、Microsoft マネージドデスクトップデバイスに対するセキュリティリスクを提示することもできます。</span><span class="sxs-lookup"><span data-stu-id="dadc0-120">Certain application behaviors can either be detrimental to user experience or present a security risk to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="dadc0-121">アプリケーションは、次の動作や特性を示しません。</span><span class="sxs-lookup"><span data-stu-id="dadc0-121">Applications shall not exhibit the following behaviors or characteristics:</span></span> 

<span data-ttu-id="dadc0-122">ユーザーの作業状況:</span><span class="sxs-lookup"><span data-stu-id="dadc0-122">User Experience:</span></span>
- <span data-ttu-id="dadc0-123">バックグラウンドサービスをインストールする、または長時間実行するバックグラウンドプロセスを生成する</span><span class="sxs-lookup"><span data-stu-id="dadc0-123">Install background services or spawn long-running background processes</span></span>
- <span data-ttu-id="dadc0-124">Windows スタートアップパスに自分自身を追加する</span><span class="sxs-lookup"><span data-stu-id="dadc0-124">Add itself to the Windows startup path</span></span>

<span data-ttu-id="dadc0-125">セキュリティ:</span><span class="sxs-lookup"><span data-stu-id="dadc0-125">Security:</span></span>
- <span data-ttu-id="dadc0-126">文書化される windows または office api を呼び出したり、内部の windows または office データ構造に依存関係を取得したりする</span><span class="sxs-lookup"><span data-stu-id="dadc0-126">Call undocumented Windows or Office APIs or take dependencies on internal Windows or Office data structures</span></span>
- <span data-ttu-id="dadc0-127">アプリストアとして機能するか、または組み込みの拡張機能マネージャーを備えている</span><span class="sxs-lookup"><span data-stu-id="dadc0-127">Act as an app store or have built-in extension manager</span></span>
- <span data-ttu-id="dadc0-128">エンドユーザーの権限を昇格させる</span><span class="sxs-lookup"><span data-stu-id="dadc0-128">Elevate the end user’s privileges</span></span>
- <span data-ttu-id="dadc0-129">既知のセキュリティの脆弱性</span><span class="sxs-lookup"><span data-stu-id="dadc0-129">Have known security vulnerabilities</span></span>
- <span data-ttu-id="dadc0-130">信頼できるルートにロールアップしない証明書を使用した署名</span><span class="sxs-lookup"><span data-stu-id="dadc0-130">Signed using a certificate which doesn’t roll up to a trusted root</span></span>
- <span data-ttu-id="dadc0-131">エンドユーザーデータへのアクセスを暗号化または制限する</span><span class="sxs-lookup"><span data-stu-id="dadc0-131">Encrypt or restrict access to end-user data</span></span>
- <span data-ttu-id="dadc0-132">実行時にオペレーティングシステムのコードを変更する</span><span class="sxs-lookup"><span data-stu-id="dadc0-132">Modify operating system code at run time</span></span>

## <a name="driver-deployment"></a><span data-ttu-id="dadc0-133">ドライバーの展開</span><span class="sxs-lookup"><span data-stu-id="dadc0-133">Driver deployment</span></span>

<span data-ttu-id="dadc0-134">ドライバーが windows Update で利用できない場合、または windows ハードウェア品質ラボ (WHQL) によって個別に署名されていない場合、microsoft がドライバーを microsoft マネージドデスクトップデバイスに展開する前に、microsoft がドライバーを承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dadc0-134">Unless a driver is available in Windows Update or is separately signed by Windows Hardware Quality Lab (WHQL), Microsoft must approve a driver before Microsoft will deploy the driver to Microsoft Managed Desktop devices.</span></span>
