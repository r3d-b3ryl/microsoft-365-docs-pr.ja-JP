---
title: Microsoft Defender for Endpoint から SIEM ツールに検出をプルする
description: REST API を使用し、サポートされているセキュリティ情報とイベント管理ツールを構成して検出を受信およびプルする方法について説明します。
keywords: siem、セキュリティ情報とイベント管理ツール、splunk、arcsight、カスタム インジケーター、rest API、アラート定義、侵害の指標を構成する
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0b9ce376736e5f00ee0f6a4f308d783e75052357
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163301"
---
# <a name="pull-detections-to-your-siem-tools"></a><span data-ttu-id="ea7c1-104">SIEM ツールへの検出のプル</span><span class="sxs-lookup"><span data-stu-id="ea7c1-104">Pull detections to your SIEM tools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ea7c1-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ea7c1-105">**Applies to:**</span></span>
- [<span data-ttu-id="ea7c1-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ea7c1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ea7c1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ea7c1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="ea7c1-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="ea7c1-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ea7c1-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="ea7c1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="pull-detections-using-security-information-and-events-management-siem-tools"></a><span data-ttu-id="ea7c1-110">セキュリティ情報とイベント管理 (SIEM) ツールを使用したプル検出</span><span class="sxs-lookup"><span data-stu-id="ea7c1-110">Pull detections using security information and events management (SIEM) tools</span></span>

>[!NOTE]
>- <span data-ttu-id="ea7c1-111">[Microsoft Defender for Endpoint Alert は](alerts.md) 、1 つ以上の検出から構成されます。</span><span class="sxs-lookup"><span data-stu-id="ea7c1-111">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="ea7c1-112">[Microsoft Defender for Endpoint Detection は](api-portal-mapping.md) 、デバイスで発生した疑わしいイベントとその関連するアラートの詳細から構成されます。</span><span class="sxs-lookup"><span data-stu-id="ea7c1-112">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
><span data-ttu-id="ea7c1-113">-Microsoft Defender for Endpoint Alert API は、アラートの使用に関する最新の API であり、各アラートに関連する証拠の詳細な一覧を含む。</span><span class="sxs-lookup"><span data-stu-id="ea7c1-113">-The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="ea7c1-114">詳細については、「Alert メソッドと[プロパティ」および「List alerts」](alerts.md)[を参照してください](get-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="ea7c1-114">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

<span data-ttu-id="ea7c1-115">Defender for Endpoint は、検出をプルするためのセキュリティ情報とイベント管理 (SIEM) ツールをサポートします。</span><span class="sxs-lookup"><span data-stu-id="ea7c1-115">Defender for Endpoint supports security information and event management (SIEM) tools to pull detections.</span></span> <span data-ttu-id="ea7c1-116">Defender for Endpoint は、Azure でホストされている HTTPS エンドポイントを通じてアラートを公開します。</span><span class="sxs-lookup"><span data-stu-id="ea7c1-116">Defender for Endpoint exposes alerts through an HTTPS endpoint hosted in Azure.</span></span> <span data-ttu-id="ea7c1-117">エンドポイントは、環境にインストールされている特定の SIEM コネクタを表す AAD アプリケーションの OAuth 2.0 認証プロトコルを使用して、Azure Active Directory (AAD) のエンタープライズ テナントから検出を取得するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="ea7c1-117">The endpoint can be configured to pull detections from your enterprise tenant in Azure Active Directory (AAD) using the OAuth 2.0 authentication protocol for an AAD application that represents the specific SIEM connector installed in your environment.</span></span>

<span data-ttu-id="ea7c1-118">Defender for Endpoint は現在、専用の SIEM 統合モデルを通じて、次の特定の SIEM ソリューション ツールをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ea7c1-118">Defender for Endpoint currently supports the following specific SIEM solution tools through a dedicated SIEM integration model:</span></span>

- <span data-ttu-id="ea7c1-119">IBM QRadar</span><span class="sxs-lookup"><span data-stu-id="ea7c1-119">IBM QRadar</span></span>
- <span data-ttu-id="ea7c1-120">Micro Focus ArcSight</span><span class="sxs-lookup"><span data-stu-id="ea7c1-120">Micro Focus ArcSight</span></span>

<span data-ttu-id="ea7c1-121">他の SIEM ソリューション (Splunk、RSA NetWitness など) は、新しいアラート API に基づく別の統合モデルを介してサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ea7c1-121">Other SIEM solutions (such as Splunk, RSA NetWitness) are supported through a different integration model based on the new Alert API.</span></span> <span data-ttu-id="ea7c1-122">詳細については、[パートナー アプリケーション] [ページを表示](https://securitycenter.microsoft.com/interoperability/partners) し、[セキュリティ情報と分析] セクションを選択して詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="ea7c1-122">For more information, view the [Partner application](https://securitycenter.microsoft.com/interoperability/partners) page and select the Security Information and Analytics section for full details.</span></span>

<span data-ttu-id="ea7c1-123">サポートされている SIEM ツールのいずれかを使用するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea7c1-123">To use either of these supported SIEM tools, you'll need to:</span></span>

- [<span data-ttu-id="ea7c1-124">Defender for Endpoint で SIEM 統合を有効にする</span><span class="sxs-lookup"><span data-stu-id="ea7c1-124">Enable SIEM integration in Defender for Endpoint</span></span>](enable-siem-integration.md)
- <span data-ttu-id="ea7c1-125">サポートされている SIEM ツールを構成します。</span><span class="sxs-lookup"><span data-stu-id="ea7c1-125">Configure the supported SIEM tool:</span></span>
     - [<span data-ttu-id="ea7c1-126">エンドポイント検出用の Defender をプルする HP ArcSight の構成</span><span class="sxs-lookup"><span data-stu-id="ea7c1-126">Configure HP ArcSight to pull Defender for Endpoint detections</span></span>](configure-arcsight.md)
     - <span data-ttu-id="ea7c1-127">エンドポイント検出用 Defender をプルする IBM QRadar を構成する 詳細については [、「IBM Knowledge Center」を参照してください](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/com.ibm.dsm.doc/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1)。</span><span class="sxs-lookup"><span data-stu-id="ea7c1-127">Configure IBM QRadar to pull Defender for Endpoint detections For more information, see [IBM Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/com.ibm.dsm.doc/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1).</span></span>

<span data-ttu-id="ea7c1-128">検出 API で公開されているフィールドの一覧の詳細については [、「Defender for Endpoint Detection fields」を参照してください](api-portal-mapping.md)。</span><span class="sxs-lookup"><span data-stu-id="ea7c1-128">For more information on the list of fields exposed in the Detection API see, [Defender for Endpoint Detection fields](api-portal-mapping.md).</span></span>
