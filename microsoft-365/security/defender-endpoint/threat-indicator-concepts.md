---
title: Microsoft Defender for Endpoint の脅威インテリジェンスの概念を理解する
description: 組織のカスタム脅威アラートを作成し、Microsoft Defender for Endpoint の脅威インテリジェンスに関する概念を学ぶ
keywords: 脅威インテリジェンス、アラート定義、侵害の指標、ioc
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
ms.openlocfilehash: bb82634c8c2ef11131a43e8e479bf88d5626ed03
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066083"
---
# <a name="understand-threat-intelligence-concepts"></a><span data-ttu-id="4830f-104">脅威インテリジェンスの概念を理解する</span><span class="sxs-lookup"><span data-stu-id="4830f-104">Understand threat intelligence concepts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4830f-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="4830f-105">**Applies to:**</span></span>
- [<span data-ttu-id="4830f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4830f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="4830f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4830f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



><span data-ttu-id="4830f-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="4830f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4830f-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="4830f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-threatindicator-abovefoldlink) 

<span data-ttu-id="4830f-110">高度なサイバーセキュリティ攻撃は、複数の複雑な悪意のあるイベント、属性、コンテキスト情報で構成されます。</span><span class="sxs-lookup"><span data-stu-id="4830f-110">Advanced cybersecurity attacks comprise of multiple complex malicious events, attributes, and contextual information.</span></span> <span data-ttu-id="4830f-111">これらのアクティビティの中で疑わしいと見なされるアクティビティを特定して決定すると、困難な作業になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4830f-111">Identifying and deciding which of these activities qualify as suspicious can be a challenging task.</span></span> <span data-ttu-id="4830f-112">業界固有の既知の属性と異常なアクティビティに関する知識は、観測された動作を疑わしいと呼ぶ場合を知る上で基本的です。</span><span class="sxs-lookup"><span data-stu-id="4830f-112">Your knowledge of known attributes and abnormal activities specific to your industry is fundamental in knowing when to call an observed behavior as suspicious.</span></span>

<span data-ttu-id="4830f-113">Microsoft Defender for Endpoint を使用すると、組織内で発生する可能性のある攻撃アクティビティを追跡するのに役立つカスタム脅威アラートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4830f-113">With Microsoft Defender for Endpoint, you can create custom threat alerts that can help you keep track of possible attack activities in your organization.</span></span> <span data-ttu-id="4830f-114">疑わしいイベントにフラグを立て、手がかりをまとめ、攻撃チェーンを停止できます。</span><span class="sxs-lookup"><span data-stu-id="4830f-114">You can flag suspicious events to piece together clues and possibly stop an attack chain.</span></span> <span data-ttu-id="4830f-115">これらのカスタム脅威アラートは組織にのみ表示され、追跡に設定したイベントにフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="4830f-115">These custom threat alerts will only appear in your organization and will flag events that you set it to track.</span></span>

<span data-ttu-id="4830f-116">カスタム脅威アラートを作成する前に、アラート定義と侵害の指標 (IOC) の背後にある概念と、その間の関係を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="4830f-116">Before creating custom threat alerts, it's important to know the concepts behind alert definitions and indicators of compromise (IOCs) and the relationship between them.</span></span>

## <a name="alert-definitions"></a><span data-ttu-id="4830f-117">アラートの定義</span><span class="sxs-lookup"><span data-stu-id="4830f-117">Alert definitions</span></span>
<span data-ttu-id="4830f-118">アラート定義はコンテキスト属性で、サイバーセキュリティ攻撃の可能性に関する早期の手がかりを特定するためにまとめて使用できます。</span><span class="sxs-lookup"><span data-stu-id="4830f-118">Alert definitions are contextual attributes that can be used collectively to identify early clues on a possible cybersecurity attack.</span></span> <span data-ttu-id="4830f-119">通常、これらのインジケーターは、攻撃の目的を達成するために攻撃者が実行したアクティビティ、特性、およびアクションの組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="4830f-119">These indicators are typically a combination of activities, characteristics, and actions taken by an attacker to successfully achieve the objective of an attack.</span></span> <span data-ttu-id="4830f-120">これらの属性の組み合わせを監視すると、攻撃に対する視点を得て、攻撃者の目標に達する前に一部のイベントに干渉する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4830f-120">Monitoring these combinations of attributes is critical in gaining a vantage point against attacks and possibly interfering with the chain of events before an attacker's objective is reached.</span></span>

## <a name="indicators-of-compromise-ioc"></a><span data-ttu-id="4830f-121">侵害の指標 (IOC)</span><span class="sxs-lookup"><span data-stu-id="4830f-121">Indicators of compromise (IOC)</span></span>
<span data-ttu-id="4830f-122">IOC は、ネットワークまたはデバイスが既に侵害されているという個別の既知の悪意のあるイベントです。</span><span class="sxs-lookup"><span data-stu-id="4830f-122">IOCs are individually-known malicious events that indicate that a network or device has already been breached.</span></span> <span data-ttu-id="4830f-123">アラート定義とは異なり、これらのインジケーターは侵害の証拠と見なされます。</span><span class="sxs-lookup"><span data-stu-id="4830f-123">Unlike alert definitions, these indicators are considered as evidence of a breach.</span></span> <span data-ttu-id="4830f-124">多くの場合、攻撃が既に実行され、その目的に達した後 (例: exfiltration など) 見られます。</span><span class="sxs-lookup"><span data-stu-id="4830f-124">They are often seen after an attack has already been carried out and the objective has been reached, such as exfiltration.</span></span> <span data-ttu-id="4830f-125">IOC の追跡は、捜査の際にも重要です。</span><span class="sxs-lookup"><span data-stu-id="4830f-125">Keeping track of IOCs is also important during forensic investigations.</span></span> <span data-ttu-id="4830f-126">攻撃チェーンに介入する機能を提供しない場合でも、これらのインジケーターを収集すると、将来の攻撃に対する防御の向上に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4830f-126">Although it might not provide the ability to intervene with an attack chain, gathering these indicators can be useful in creating better defenses for possible future attacks.</span></span>

## <a name="relationship-between-alert-definitions-and-iocs"></a><span data-ttu-id="4830f-127">アラート定義と IOC の関係</span><span class="sxs-lookup"><span data-stu-id="4830f-127">Relationship between alert definitions and IOCs</span></span>
<span data-ttu-id="4830f-128">Microsoft Defender for Endpoint のコンテキストでは、アラート定義は IOC のコンテナーであり、特定の IOC が一致した場合に発生するメタデータを含むアラートを定義します。</span><span class="sxs-lookup"><span data-stu-id="4830f-128">In the context of Microsoft Defender for Endpoint, alert definitions are containers for IOCs and defines the alert, including the metadata that is raised in case of a specific IOC match.</span></span> <span data-ttu-id="4830f-129">アラート定義の一部として、さまざまなメタデータが提供されます。</span><span class="sxs-lookup"><span data-stu-id="4830f-129">Various metadata is provided as part of the alert definitions.</span></span> <span data-ttu-id="4830f-130">攻撃のアラート定義名、重大度、説明などのメタデータは、他のオプションと共に提供されます。</span><span class="sxs-lookup"><span data-stu-id="4830f-130">Metadata such as alert definition name of attack, severity, and description is provided along with other options.</span></span>

<span data-ttu-id="4830f-131">各 IOC は、その種類と値、およびアクションに基づいて具体的な検出ロジックを定義し、その一致方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="4830f-131">Each IOC defines the concrete detection logic based on its type and value as well as its action, which determines how it is matched.</span></span> <span data-ttu-id="4830f-132">これは、検出が Microsoft Defender for Endpoint コンソールでアラートとして表示される方法を定義する特定のアラート定義にバインドされます。</span><span class="sxs-lookup"><span data-stu-id="4830f-132">It is bound to a specific alert definition that defines how a detection is displayed as an alert on the Microsoft Defender for Endpoint console.</span></span>

<span data-ttu-id="4830f-133">IOC の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4830f-133">Here is an example of an IOC:</span></span>
- <span data-ttu-id="4830f-134">種類: Sha1</span><span class="sxs-lookup"><span data-stu-id="4830f-134">Type: Sha1</span></span>
- <span data-ttu-id="4830f-135">値: 92cfceb39d57d914ed8b14d0e37643de0797ae56</span><span class="sxs-lookup"><span data-stu-id="4830f-135">Value:  92cfceb39d57d914ed8b14d0e37643de0797ae56</span></span>
- <span data-ttu-id="4830f-136">Action: Equals</span><span class="sxs-lookup"><span data-stu-id="4830f-136">Action: Equals</span></span>

<span data-ttu-id="4830f-137">IOC は、アラート定義と多対 1 の関係を持ち、アラート定義に対応する IOC を多数持つ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4830f-137">IOCs have a many-to-one relationship with alert definitions such that an alert definition can have many IOCs that correspond to it.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="4830f-138">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4830f-138">In this section</span></span>

<span data-ttu-id="4830f-139">トピック</span><span class="sxs-lookup"><span data-stu-id="4830f-139">Topic</span></span> | <span data-ttu-id="4830f-140">説明</span><span class="sxs-lookup"><span data-stu-id="4830f-140">Description</span></span>
:---|:---
[<span data-ttu-id="4830f-141">SIEM ツールへの検出のプル</span><span class="sxs-lookup"><span data-stu-id="4830f-141">Pull detections to your SIEM tools</span></span>](configure-siem.md)| <span data-ttu-id="4830f-142">検出をプルするさまざまな方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="4830f-142">Learn about different ways to pull detections.</span></span>
[<span data-ttu-id="4830f-143">エンドポイント向け Microsoft Defender で SIEM 統合を有効にする</span><span class="sxs-lookup"><span data-stu-id="4830f-143">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>](enable-siem-integration.md)| <span data-ttu-id="4830f-144">サポートされている SIEM ツールを構成するために必要な情報を使用して生成できるよう、ポータルの [設定] ページで SIEM 統合機能を有効にする方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="4830f-144">Learn about enabling the SIEM integration feature in the **Settings** page in the portal so that you can use and generate the required information to configure supported SIEM tools.</span></span>
[<span data-ttu-id="4830f-145">エンドポイント検出用の Microsoft Defender をプルする Splunk の構成</span><span class="sxs-lookup"><span data-stu-id="4830f-145">Configure Splunk to pull Microsoft Defender for Endpoint detections</span></span>](configure-siem.md)| <span data-ttu-id="4830f-146">REST API モジュラ入力アプリなどの構成設定をインストールして、Splunk が Microsoft Defender for Endpoint の検出を取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4830f-146">Learn about installing the REST API Modular Input App and other configuration settings to enable Splunk to pull Microsoft Defender for Endpoint detections.</span></span>
[<span data-ttu-id="4830f-147">エンドポイント検出用の Microsoft Defender をプルする HP ArcSight の構成</span><span class="sxs-lookup"><span data-stu-id="4830f-147">Configure HP ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)| <span data-ttu-id="4830f-148">HP ArcSight REST FlexConnector パッケージのインストールと、Microsoft Defender for Endpoint 検出を取得するために ArcSight を構成するために必要なファイルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4830f-148">Learn about installing the HP ArcSight REST FlexConnector package and the files you need to configure ArcSight to pull Microsoft Defender for Endpoint detections.</span></span>
[<span data-ttu-id="4830f-149">Microsoft Defender for Endpoint Detection フィールド</span><span class="sxs-lookup"><span data-stu-id="4830f-149">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md) | <span data-ttu-id="4830f-150">アラート API の一部として公開されるデータ フィールドと、Microsoft Defender セキュリティ センターへのマップ方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4830f-150">Understand what data fields are exposed as part of the alerts API and how they map to Microsoft Defender Security Center.</span></span>
[<span data-ttu-id="4830f-151">REST API を使用したエンドポイント検出用の Microsoft Defender のプル</span><span class="sxs-lookup"><span data-stu-id="4830f-151">Pull Microsoft Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md) | <span data-ttu-id="4830f-152">REST API を使用して Microsoft Defender for Endpoint から検出を取得するには、クライアント資格情報 OAuth 2.0 フローを使用します。</span><span class="sxs-lookup"><span data-stu-id="4830f-152">Use the Client credentials OAuth 2.0 flow to pull detections from Microsoft Defender for Endpoint using REST API.</span></span>
[<span data-ttu-id="4830f-153">SIEM ツールの統合に関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="4830f-153">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md) | <span data-ttu-id="4830f-154">SIEM 統合機能を使用するときに発生する可能性がある問題に対処します。</span><span class="sxs-lookup"><span data-stu-id="4830f-154">Address issues you might encounter when using the SIEM integration feature.</span></span>



## <a name="related-topics"></a><span data-ttu-id="4830f-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="4830f-155">Related topics</span></span>
- [<span data-ttu-id="4830f-156">インジケーターの管理</span><span class="sxs-lookup"><span data-stu-id="4830f-156">Manage indicators</span></span>](manage-indicators.md)
