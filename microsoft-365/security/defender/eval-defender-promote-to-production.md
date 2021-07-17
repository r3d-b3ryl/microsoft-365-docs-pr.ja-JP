---
title: 評価環境をMicrosoft 365 Defender、評価Microsoft 365 Defender、評価を試す、評価を維持する、生産評価を行う
description: この記事を使用して、MDI、MDO、MDE、MCAS のエバルを、Microsoft 365 Defender または M365D のライブ環境に昇格します。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: b67f0f493c97b900fa08b10e3eb7a5967560dcfd
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458344"
---
# <a name="promote-your-microsoft-365-defender-evaluation-environment-to-production"></a><span data-ttu-id="1bdab-103">評価環境Microsoft 365 Defenderを実稼働環境に昇格する</span><span class="sxs-lookup"><span data-stu-id="1bdab-103">Promote your Microsoft 365 Defender evaluation environment to production</span></span>

<span data-ttu-id="1bdab-104">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="1bdab-104">**Applies to:**</span></span>
- <span data-ttu-id="1bdab-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1bdab-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="1bdab-106">評価環境をMicrosoft 365 Defenderするには、まず必要なライセンスを購入します。</span><span class="sxs-lookup"><span data-stu-id="1bdab-106">To promote your Microsoft 365 Defender evaluation environment to production, first purchase the necessary license.</span></span> <span data-ttu-id="1bdab-107">「eval[環境の作成」](eval-create-eval-environment.md)の手順に従って、ライセンスOffice 365 E5購入します ([無料試用版の開始] を選択する代わりに)。</span><span class="sxs-lookup"><span data-stu-id="1bdab-107">Follow the steps in [Create the eval environment](eval-create-eval-environment.md) and purchase the Office 365 E5 license (instead of selecting Start free trial).</span></span>

<span data-ttu-id="1bdab-108">次に、追加の構成を完了し、パイロット グループが完全に稼働するまで展開します。</span><span class="sxs-lookup"><span data-stu-id="1bdab-108">Next, complete any additional configuration and expand your pilot groups until these have reached full production.</span></span> 

## <a name="microsoft-defender-for-identity"></a><span data-ttu-id="1bdab-109">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="1bdab-109">Microsoft Defender for Identity</span></span>
<span data-ttu-id="1bdab-110">Id の Defender は、追加の構成を必要とします。</span><span class="sxs-lookup"><span data-stu-id="1bdab-110">Defender for Identity doesn't require any additional configuration.</span></span> <span data-ttu-id="1bdab-111">必要なライセンスを購入し、すべての Active Directory ドメイン コントローラーと Active Directory フェデレーション サービス (AD FS) サーバーにセンサーをインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="1bdab-111">Just make sure you've purchased the necessary licenses and installed the sensor on all of your Active Directory domain controllers and Active Directory Federation Services (AD FS) servers.</span></span> 

## <a name="microsoft-defender-for-office-365"></a><span data-ttu-id="1bdab-112">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="1bdab-112">Microsoft Defender for Office 365</span></span>
<span data-ttu-id="1bdab-113">MDO を正常に評価またはパイロットした後、その MDO を実稼働環境全体に昇格できます。</span><span class="sxs-lookup"><span data-stu-id="1bdab-113">After successfully evaluating or piloting MDO, it can be promoted to your entire production environment.</span></span>
1. <span data-ttu-id="1bdab-114">必要なライセンスを購入してプロビジョニングし、実稼働ユーザーに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="1bdab-114">Purchase and provision the necessary licenses and assign them to your production users.</span></span>
2. <span data-ttu-id="1bdab-115">推奨されるベースライン ポリシー構成 (Standard または Strict) を、実稼働メール ドメインまたは特定のユーザー グループに対して再実行します。</span><span class="sxs-lookup"><span data-stu-id="1bdab-115">Re-run recommended baseline policy configurations (either Standard or Strict) against your production email domain or specific groups of users.</span></span>
3. <span data-ttu-id="1bdab-116">必要に応じて、実稼働メール ドメインまたはユーザー グループに対してカスタム MDO ポリシーを作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="1bdab-116">Optionally create and configure any custom MDO policies against your production email domain or groups of users.</span></span>  <span data-ttu-id="1bdab-117">ただし、割り当てられた基準ポリシーは常にカスタム ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="1bdab-117">However, remember that any assigned baseline policies will always take precedence over custom policies.</span></span>
4. <span data-ttu-id="1bdab-118">運用メール ドメインのパブリック MX レコードを更新して、EOP に直接解決します。</span><span class="sxs-lookup"><span data-stu-id="1bdab-118">Update the public MX record for your production email domain to resolve directly to EOP.</span></span>
5. <span data-ttu-id="1bdab-119">サードパーティの SMTP ゲートウェイを使用停止し、このリレーに関連付けられている EXO コネクタを無効または削除します。</span><span class="sxs-lookup"><span data-stu-id="1bdab-119">Decommission any third-party SMTP gateways and disable or delete any EXO connectors associated with this relay.</span></span>

## <a name="microsoft-defender-for-endpoint"></a><span data-ttu-id="1bdab-120">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1bdab-120">Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="1bdab-121">Microsoft Defender for Endpoint 評価環境をパイロットから実稼働環境に昇格するには、サポートされているツールと方法を使用して、より多くのエンドポイントをサービスに [オンボードします](/defender-endpoint/onboard-configure)。</span><span class="sxs-lookup"><span data-stu-id="1bdab-121">To promote Microsoft Defender for Endpoint evaluation environment from a pilot to production, simply onboard more endpoints to the service using any of the [supported tools and methods](/defender-endpoint/onboard-configure).</span></span>

<span data-ttu-id="1bdab-122">Microsoft Defender for Endpoint に追加のデバイスをオンボードするには、次の一般的なガイドラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="1bdab-122">Use the following general guidelines to onboard more devices to Microsoft Defender for Endpoint.</span></span> 

1. <span data-ttu-id="1bdab-123">デバイスが最小要件を満 [たしていることを確認します](/defender-endpoint/minimum-requirements)。</span><span class="sxs-lookup"><span data-stu-id="1bdab-123">Verify that the device fulfills the [minimum requirements](/defender-endpoint/minimum-requirements).</span></span>
2. <span data-ttu-id="1bdab-124">デバイスに応じて、Defender for Endpoint ポータルのオンボーディング セクションに示されている構成手順に従います。</span><span class="sxs-lookup"><span data-stu-id="1bdab-124">Depending on the device, follow the configuration steps provided in the onboarding section of the Defender for Endpoint portal.</span></span>
3. <span data-ttu-id="1bdab-125">デバイスに適切な管理ツールと展開方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="1bdab-125">Use the appropriate management tool and deployment method for your devices.</span></span>
4.  <span data-ttu-id="1bdab-126">検出テストを実行して、デバイスが適切にオンボードされ、サービスに報告されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1bdab-126">Run a detection test to verify that the devices are properly onboarded and reporting to the service.</span></span>

## <a name="microsoft-cloud-app-security"></a><span data-ttu-id="1bdab-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1bdab-127">Microsoft Cloud App Security</span></span>
<span data-ttu-id="1bdab-128">Microsoft Cloud App Security構成は不要です。</span><span class="sxs-lookup"><span data-stu-id="1bdab-128">Microsoft Cloud App Security doesn't require any additional configuration.</span></span> <span data-ttu-id="1bdab-129">必要なライセンスを購入しただけ。</span><span class="sxs-lookup"><span data-stu-id="1bdab-129">Just make sure you've purchased the necessary licenses.</span></span> <span data-ttu-id="1bdab-130">展開の範囲を特定のユーザー グループに設定した場合は、実稼働規模に達するまで、これらのグループの範囲を広くします。</span><span class="sxs-lookup"><span data-stu-id="1bdab-130">If you've scoped the deployment to certain user groups, increase the scope of these groups until you reach production scale.</span></span> 

