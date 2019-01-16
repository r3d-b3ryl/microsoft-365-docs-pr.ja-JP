---
title: Microsoft 管理されたデスクトップ アプリケーションの要件
description: ''
keywords: 管理されたデスクトップの Microsoft、Microsoft 365 サービス マニュアル
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/08/2019
ms.openlocfilehash: 6b6c6f6a2e719496578ac1d15c9b94a92a2ab492
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868983"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="b7dda-103">Microsoft 管理されたデスクトップ アプリケーションの要件</span><span class="sxs-lookup"><span data-stu-id="b7dda-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="b7dda-104">Microsoft 管理デスクトップ デバイスに配備する基幹業務アプリケーションでは、このトピックの要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7dda-104">Line-of-business applications that you want to deploy to Microsoft Managed Desktop devices must meet the requirements in this topic.</span></span> 

## <a name="application-condition"></a><span data-ttu-id="b7dda-105">アプリケーションの条件</span><span class="sxs-lookup"><span data-stu-id="b7dda-105">Application condition</span></span>

<span data-ttu-id="b7dda-p101">アプリケーションは、Microsoft の管理されたデスクトップ環境に悪影響を及ぼすしない必要があります。アプリケーションは、マイクロソフトが展開するために満たす必要がある要件を次に示します。任意の特定のアプリケーションまたはドライバーを使用して、マイクロソフトは、ここに示すすべての要件を免除可能性があります。マイクロソフトは、アプリケーションまたはドライバーがマイクロソフトの管理されたデスクトップのデバイスのパフォーマンスと信頼性に悪影響を削除する場合があります。</span><span class="sxs-lookup"><span data-stu-id="b7dda-p101">It’s important that applications don’t adversely impact the Microsoft Managed Desktop environment. The following are the requirements that an application must meet in order for Microsoft to deploy it. For any given application or driver, Microsoft may waive any requirement provided herein. Microsoft may decide to remove any application or driver that negatively impacts performance and reliability of Microsoft Managed Desktop devices.</span></span>

## <a name="deployable-using-microsoft-technologies"></a><span data-ttu-id="b7dda-110">マイクロソフトのテクノロジを使用して配置可能です</span><span class="sxs-lookup"><span data-stu-id="b7dda-110">Deployable using Microsoft technologies</span></span>

<span data-ttu-id="b7dda-p102">Microsoft 管理されたデスクトップは、アプリケーションを配置するのに Intune、マイクロソフトのストア、およびビジネスのためのマイクロソフト ストアを使用します。したがって、これらのサービスで最新のバージョンで展開することの方法でアプリケーションをパッケージ化しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="b7dda-p102">Microsoft Managed Desktop uses Intune,  Microsoft Store, and  Microsoft Store for Business to deploy applications. Consequently, applications must be packaged in a manner able to be deployed by the then-current version of those services.</span></span>

## <a name="prohibited-app-classes"></a><span data-ttu-id="b7dda-113">禁止されているアプリケーション クラス</span><span class="sxs-lookup"><span data-stu-id="b7dda-113">Prohibited app classes</span></span>

<span data-ttu-id="b7dda-114">Microsoft 管理デスクトップ デバイスでは、特定の種類のアプリケーションは使用できません。</span><span class="sxs-lookup"><span data-stu-id="b7dda-114">Certain application types are not permitted on Microsoft Managed Desktop devices:</span></span>
- <span data-ttu-id="b7dda-115">サード パーティ製ウイルス対策、セキュリティ、または監査ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="b7dda-115">3rd party anti-virus, security, or audit software</span></span>
- <span data-ttu-id="b7dda-116">サード パーティ製の web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="b7dda-116">3rd party web browsers</span></span>
- <span data-ttu-id="b7dda-117">Office 365 Pro Plus より前の Microsoft Office のバージョン</span><span class="sxs-lookup"><span data-stu-id="b7dda-117">Versions of Microsoft Office prior to Office 365 Pro Plus</span></span>
- <span data-ttu-id="b7dda-118">アプリケーションをインストールするか、他のサード ・ パーティ製ソフトウェアをバンドル</span><span class="sxs-lookup"><span data-stu-id="b7dda-118">Applications that install or bundle other 3rd party software</span></span>

## <a name="restricted-app-behaviors"></a><span data-ttu-id="b7dda-119">制限されたアプリケーションの動作</span><span class="sxs-lookup"><span data-stu-id="b7dda-119">Restricted app behaviors</span></span>

<span data-ttu-id="b7dda-p103">特定のアプリケーションの動作するユーザー エクスペリエンスに悪影響を及ぼすか、Microsoft 管理デスクトップ デバイスにセキュリティ リスクが存在します。アプリケーションは、次の動作または特性は発生しません。</span><span class="sxs-lookup"><span data-stu-id="b7dda-p103">Certain application behaviors can either be detrimental to user experience or present a security risk to Microsoft Managed Desktop devices. Applications shall not exhibit the following behaviors or characteristics:</span></span> 

<span data-ttu-id="b7dda-122">ユーザー エクスペリエンス。</span><span class="sxs-lookup"><span data-stu-id="b7dda-122">User Experience:</span></span>
- <span data-ttu-id="b7dda-123">バック グラウンド サービスをインストールするか、長時間実行されるバック グラウンド プロセスの生成</span><span class="sxs-lookup"><span data-stu-id="b7dda-123">Install background services or spawn long-running background processes</span></span>
- <span data-ttu-id="b7dda-124">自分自身を Windows のスタートアップ パスに追加します。</span><span class="sxs-lookup"><span data-stu-id="b7dda-124">Add itself to the Windows startup path</span></span>

<span data-ttu-id="b7dda-125">セキュリティ:</span><span class="sxs-lookup"><span data-stu-id="b7dda-125">Security:</span></span>
- <span data-ttu-id="b7dda-126">Windows または Office の内部データ構造を文書化されていない、Windows または Office Api を呼び出すまたは依存関係</span><span class="sxs-lookup"><span data-stu-id="b7dda-126">Call undocumented Windows or Office APIs or take dependencies on internal Windows or Office data structures</span></span>
- <span data-ttu-id="b7dda-127">アプリケーション ストアとして機能または拡張機能マネージャー</span><span class="sxs-lookup"><span data-stu-id="b7dda-127">Act as an app store or have built-in extension manager</span></span>
- <span data-ttu-id="b7dda-128">エンド ・ ユーザーの権限を昇格させる</span><span class="sxs-lookup"><span data-stu-id="b7dda-128">Elevate the end user’s privileges</span></span>
- <span data-ttu-id="b7dda-129">既知のセキュリティの脆弱性を持つ</span><span class="sxs-lookup"><span data-stu-id="b7dda-129">Have known security vulnerabilities</span></span>
- <span data-ttu-id="b7dda-130">重ね合わせ不可に信頼されたルート証明書を使用して署名</span><span class="sxs-lookup"><span data-stu-id="b7dda-130">Signed using a certificate which doesn’t roll up to a trusted root</span></span>
- <span data-ttu-id="b7dda-131">暗号化またはエンド ・ ユーザーのデータへのアクセスを制限</span><span class="sxs-lookup"><span data-stu-id="b7dda-131">Encrypt or restrict access to end-user data</span></span>
- <span data-ttu-id="b7dda-132">実行時にオペレーティング システムのコードを変更します。</span><span class="sxs-lookup"><span data-stu-id="b7dda-132">Modify operating system code at run time</span></span>

## <a name="driver-deployment"></a><span data-ttu-id="b7dda-133">ドライバーの配備</span><span class="sxs-lookup"><span data-stu-id="b7dda-133">Driver deployment</span></span>

<span data-ttu-id="b7dda-134">場合を除き、ドライバーが Windows Update で利用可能な Windows ハードウェア品質ラボ (WHQL) によって署名とは別に、マイクロソフトは、マイクロソフトはマイクロソフトの管理されたデスクトップ デバイスにドライバーを配置する前にドライバーを承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7dda-134">Unless a driver is available in Windows Update or is separately signed by Windows Hardware Quality Lab (WHQL), Microsoft must approve a driver before Microsoft will deploy the driver to Microsoft Managed Desktop devices.</span></span>
