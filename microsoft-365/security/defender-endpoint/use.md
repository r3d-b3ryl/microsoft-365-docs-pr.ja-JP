---
title: Microsoft Defender セキュリティ センターの概要
description: アラートの動作など、Microsoft Defender セキュリティ センターの機能、および侵害や攻撃の可能性を調査する方法に関する提案について学習します。
keywords: ダッシュボード、アラート キュー、アラートの管理、調査、アラートの調査、デバイスの調査、ファイルの送信、深い分析、高、中、低、重大度、ioc、ioa
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ee6fd4bd8d60f828bb474fc80cb987f4f94edcbe
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581096"
---
# <a name="overview-of-microsoft-defender-security-center"></a><span data-ttu-id="ffe76-104">Microsoft Defender セキュリティ センターの概要</span><span class="sxs-lookup"><span data-stu-id="ffe76-104">Overview of Microsoft Defender Security Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ffe76-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ffe76-105">**Applies to:**</span></span>
- [<span data-ttu-id="ffe76-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ffe76-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="ffe76-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ffe76-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="ffe76-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="ffe76-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ffe76-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="ffe76-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-usewdatp-abovefoldlink)

<span data-ttu-id="ffe76-110">Microsoft Defender セキュリティ センターは、Microsoft Defender for Endpoint の機能にアクセスできるポータルです。</span><span class="sxs-lookup"><span data-stu-id="ffe76-110">Microsoft Defender Security Center is the portal where you can access Microsoft Defender for Endpoint capabilities.</span></span>

<span data-ttu-id="ffe76-111">セキュリティ操作 **ダッシュボードを使用** して、ネットワーク内のデバイスとユーザーに関するさまざまなアラートを把握します。</span><span class="sxs-lookup"><span data-stu-id="ffe76-111">Use the **Security operations** dashboard to gain insight on the various alerts on devices and users in your network.</span></span>

<span data-ttu-id="ffe76-112">[脅威 **の検出&管理** ] ダッシュボードを使用して、組織の全体的なセキュリティ体制の可視性を拡大します。</span><span class="sxs-lookup"><span data-stu-id="ffe76-112">Use the **Threat & Vulnerability Management** dashboard to expand your visibility on the overall security posture of your organization.</span></span> <span data-ttu-id="ffe76-113">組織の攻撃表面を減らすのに役立つ注意と推奨事項が必要なデバイスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ffe76-113">You'll see devices that require attention and recommendations that can help you reduce the attack surface in your organization.</span></span>

<span data-ttu-id="ffe76-114">脅威分析 **ダッシュボードを使用して** 、Spectre と Meltdown へのリスクエクスポージャーを継続的に評価および制御します。</span><span class="sxs-lookup"><span data-stu-id="ffe76-114">Use the **Threat analytics** dashboard to continually assess and control risk exposure to Spectre and Meltdown.</span></span>

## <a name="microsoft-defender-for-endpoint-interactive-guide"></a><span data-ttu-id="ffe76-115">Microsoft Defender for Endpoint 対話型ガイド</span><span class="sxs-lookup"><span data-stu-id="ffe76-115">Microsoft Defender for Endpoint interactive guide</span></span>
<span data-ttu-id="ffe76-116">この対話型ガイドでは、Microsoft Defender for Endpoint を使用して組織に対する脅威を調査する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ffe76-116">In this interactive guide, you'll learn how to investigate threats to your organization with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="ffe76-117">Microsoft Defender for Endpoint が、疑わしいアクティビティの特定、組織のリスクの調査、脅威の修復に役立つ方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ffe76-117">You'll see how Microsoft Defender for Endpoint can help you identify suspicious activities, investigate risks to your organization, and remediate threats.</span></span>

[<span data-ttu-id="ffe76-118">対話型のガイドをチェックしてください</span><span class="sxs-lookup"><span data-stu-id="ffe76-118">Check out the interactive guide</span></span>](https://aka.ms/MSDE-IG)

### <a name="in-this-section"></a><span data-ttu-id="ffe76-119">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ffe76-119">In this section</span></span>

<span data-ttu-id="ffe76-120">トピック</span><span class="sxs-lookup"><span data-stu-id="ffe76-120">Topic</span></span> | <span data-ttu-id="ffe76-121">説明</span><span class="sxs-lookup"><span data-stu-id="ffe76-121">Description</span></span>
:---|:---
[<span data-ttu-id="ffe76-122">ポータルの概要</span><span class="sxs-lookup"><span data-stu-id="ffe76-122">Portal overview</span></span>](portal-overview.md) | <span data-ttu-id="ffe76-123">ポータルのレイアウトとエリアの説明について理解します。</span><span class="sxs-lookup"><span data-stu-id="ffe76-123">Understand the portal layout and area descriptions.</span></span>
[<span data-ttu-id="ffe76-124">セキュリティ操作ダッシュボードの表示</span><span class="sxs-lookup"><span data-stu-id="ffe76-124">View the Security operations dashboard</span></span>](security-operations-dashboard.md) | <span data-ttu-id="ffe76-125">Microsoft Defender for Endpoint  **Security 操作ダッシュボードは** 、ネットワークのスナップショットを提供します。</span><span class="sxs-lookup"><span data-stu-id="ffe76-125">The Microsoft Defender for Endpoint  **Security operations dashboard** provides a snapshot of your network.</span></span> <span data-ttu-id="ffe76-126">アラートの集計、ネットワーク上のデバイスのサービスの全体的な状態を表示し、デバイス、ファイル、URL を調査し、デバイスで見られる脅威のスナップショットを確認できます。</span><span class="sxs-lookup"><span data-stu-id="ffe76-126">You can view aggregates of alerts, the overall status of the service of the devices on your network, investigate devices, files, and URLs, and see snapshots of threats seen on devices.</span></span>
<span data-ttu-id="ffe76-127">[[脅威の管理] &のダッシュボードを表示する](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="ffe76-127">[View the Threat & Vulnerability Management dashboard](tvm-dashboard-insights.md)</span></span> | <span data-ttu-id="ffe76-128">脅威 **&** 脆弱性管理ダッシュボードを使用すると、セキュリティに関する推奨事項、ソフトウェアの脆弱性、修復アクティビティ、公開されたデバイスを使用して、露出と Microsoft Secure Score for Devices を並べて表示できます。</span><span class="sxs-lookup"><span data-stu-id="ffe76-128">The **Threat & Vulnerability Management dashboard** lets you view exposure and Microsoft Secure Score for Devices side-by-side with top security recommendations, software vulnerability, remediation activities, and exposed devices.</span></span>
[<span data-ttu-id="ffe76-129">脅威分析ダッシュボードを表示し、推奨される軽減アクションを実行する</span><span class="sxs-lookup"><span data-stu-id="ffe76-129">View the Threat analytics dashboard and take recommended mitigation actions</span></span>](threat-analytics.md) | <span data-ttu-id="ffe76-130">脅威 **分析ダッシュボードは** 、脅威に対するリスクエクスポージャーを継続的に評価および制御するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ffe76-130">The **Threat analytics** dashboard helps you continually assess and control risk exposure to threats.</span></span> <span data-ttu-id="ffe76-131">グラフを使用して、軽減策の有無に関するデバイスをすばやく特定します。</span><span class="sxs-lookup"><span data-stu-id="ffe76-131">Use the charts to quickly identify devices for the presence or absence of mitigations.</span></span>
