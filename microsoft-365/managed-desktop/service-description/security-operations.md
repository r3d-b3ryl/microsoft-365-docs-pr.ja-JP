---
title: Microsoft マネージドデスクトップのセキュリティ操作
description: ''
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 5698e2a88adf3d2bae84a82e0e001132293e36be
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847718"
---
# <a name="security-operations-in-microsoft-managed-desktop"></a><span data-ttu-id="60073-103">Microsoft マネージドデスクトップのセキュリティ操作</span><span class="sxs-lookup"><span data-stu-id="60073-103">Security operations in Microsoft Managed Desktop</span></span>

<span data-ttu-id="60073-104">Microsoft Managed デスクトップセキュリティ操作センター (SOC) は、デスクトップ環境のセキュリティを確保するための情報セキュリティ担当者と協力しています。</span><span class="sxs-lookup"><span data-stu-id="60073-104">The Microsoft Managed Desktop Security Operations Center (SOC) partners with your information security staff to keep your desktop environment secure.</span></span> <span data-ttu-id="60073-105">チームは、専門的な分析を使用して管理対象デバイス上のすべてのセキュリティ警告を受信して応答し、必要に応じて、セキュリティインシデント対応アクティビティを推進します。</span><span class="sxs-lookup"><span data-stu-id="60073-105">Our team receives and responds to all security alerts on managed devices with expert analysis and, when needed, we drive security incident response activities.</span></span> <span data-ttu-id="60073-106">SOC を使用した作業の詳細については、管理ポータルで運用に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="60073-106">For more information about working with the SOC, review operational documentation at your Admin portal.</span></span>

<span data-ttu-id="60073-107">SOC は、マイクロソフトのフルタイムの従業員から、ソフトウェア、ネットワーク、またはヒューマン敵対者による一般的な攻撃方法を含む、現在の脅威に関する専門知識を持つ24/7/365 を提供します。</span><span class="sxs-lookup"><span data-stu-id="60073-107">The SOC offers 24/7/365 coverage from Microsoft full-time employees with expertise in the current and emerging threat landscape, including common attack methods through software, network, or human adversaries.</span></span>

<span data-ttu-id="60073-108">SOC は、次のサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="60073-108">The SOC provides these services:</span></span>
- <span data-ttu-id="60073-109">検出されたイベントに対する迅速かつ正確な応答。データの分析による影響を特定し、デバイスまたは環境に対する全体的なリスクを評価します。</span><span class="sxs-lookup"><span data-stu-id="60073-109">Quick and accurate response to detected events, with analysis of data to identify the impact and assess the overall risk to a device or your environment</span></span>
- <span data-ttu-id="60073-110">既知または問題のある危険から環境を保護するためのデバイス管理および分離のアクションによって、蔓延を防止してリスクを軽減する</span><span class="sxs-lookup"><span data-stu-id="60073-110">Device management and isolation actions to protect your environment from known or suspected compromises, reducing risk by preventing spread</span></span>
- <span data-ttu-id="60073-111">セキュリティインシデント対応プロセスを推進し、セキュリティチームとタイムリーかつ正確にコミュニケーションを確保する</span><span class="sxs-lookup"><span data-stu-id="60073-111">Driving the security incident response process, ensuring timely and accurate communication with your security team</span></span>
- <span data-ttu-id="60073-112">脅威と脆弱性のデータに基づいて分析と推奨事項を確認し、リスクを悪用する前に対処する</span><span class="sxs-lookup"><span data-stu-id="60073-112">Analysis and recommendations based on threat and vulnerability data to identify and address risks before they're exploited</span></span>
- <span data-ttu-id="60073-113">既知の脅威と潜在的な脅威の両方の指標とエンティティを識別するための、管理対象デバイス間の高度な検索</span><span class="sxs-lookup"><span data-stu-id="60073-113">Advanced hunting across the managed devices to identify indicators and entities for both known and potential threats</span></span>

## <a name="processes"></a><span data-ttu-id="60073-114">工程</span><span class="sxs-lookup"><span data-stu-id="60073-114">Processes</span></span>

- <span data-ttu-id="60073-115">Microsoft の管理されたデスクトップのセキュリティ操作は、microsoft の [サイバー防衛運用センター](https://www.microsoft.com/msrc/cdoc)と連携して、microsoft のフルタイムの従業員が担当します。</span><span class="sxs-lookup"><span data-stu-id="60073-115">Microsoft Managed Desktop Security Operations is staffed by full-time Microsoft employees in partnership with  Microsoft’s [Cyber Defense Operations Center](https://www.microsoft.com/msrc/cdoc).</span></span> 
- <span data-ttu-id="60073-116">この SOC では、内部と外部の両方の会社全体の集合信号を使用して、お客様のデバイスを保護します。ただし、Microsoft の管理されたデスクトップにまだ何も表示されていません。</span><span class="sxs-lookup"><span data-stu-id="60073-116">Our SOC uses collective signals from across our company, both internal and external, to protect your devices--even from things we have not yet seen in Microsoft Managed Desktop.</span></span>
- <span data-ttu-id="60073-117">Microsoft セキュリティソリューションは、多くの cybersecurity 保護標準に適合しています。</span><span class="sxs-lookup"><span data-stu-id="60073-117">Microsoft security solutions align to many cybersecurity protection standards.</span></span> <span data-ttu-id="60073-118">SOC 操作は、米国標準規格およびテクノロジコンピューターセキュリティインシデント対応ガイド (NIST 800-61 r2) に基づいています。</span><span class="sxs-lookup"><span data-stu-id="60073-118">SOC operations are based on the National Institute of Standards and Technology Computer Security Incident Response Handling Guide (NIST 800-61 r2).</span></span>
- <span data-ttu-id="60073-119">このプロセスでは、次のフェーズを通じて環境をより適切に保護する方法について、分析および文書化および復旧後の洞察のための適切な情報と証拠を収集できます。</span><span class="sxs-lookup"><span data-stu-id="60073-119">The process allows for proper collection of information and evidence, for analysis and documentation and post-recovery insights into ways to better defend your environment through these phases:</span></span>
    - <span data-ttu-id="60073-120">準備、検出、および分析</span><span class="sxs-lookup"><span data-stu-id="60073-120">Preparation, detection, and analysis</span></span>
    - <span data-ttu-id="60073-121">コンテインメント</span><span class="sxs-lookup"><span data-stu-id="60073-121">Containment</span></span>
    - <span data-ttu-id="60073-122">根絶</span><span class="sxs-lookup"><span data-stu-id="60073-122">Eradication</span></span>
    - <span data-ttu-id="60073-123">回復</span><span class="sxs-lookup"><span data-stu-id="60073-123">Recovery</span></span>
    - <span data-ttu-id="60073-124">インシデント後のアクティビティ</span><span class="sxs-lookup"><span data-stu-id="60073-124">Post-incident activity</span></span>
- <span data-ttu-id="60073-125">Microsoft マネージドデスクトップのお客様は、Microsoft の脅威の専門家サービスに登録する資格があります。</span><span class="sxs-lookup"><span data-stu-id="60073-125">Microsoft Managed Desktop customers are eligible to enroll in the Microsoft Threat Experts service.</span></span> <span data-ttu-id="60073-126">SOC スポンサーは、このサービスを使用して、組織に影響を与える複雑な脅威 (アラートの照会、侵害される可能性のあるデバイス、疑わしいネットワーク接続の根本的な原因、および継続的な高度な脅威のキャンペーンに関する追加の脅威インテリジェンス) を理解します。</span><span class="sxs-lookup"><span data-stu-id="60073-126">The SOC liaises with this service to understand better the complex threats affecting your organization, including alert inquiries, potentially compromised devices, root cause of a suspicious network connection, and additional threat intelligence regarding ongoing advanced persistent threat campaigns.</span></span> <span data-ttu-id="60073-127">詳細については、「 [マイクロソフトの脅威の専門家](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60073-127">For more information, see [Microsoft Threat Experts](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts).</span></span>
- <span data-ttu-id="60073-128">SOC の脅威と脆弱性管理プロセスは、Microsoft のいくつかのサービスを使用して、組織が脅威から保護するための推奨事項について通知します。</span><span class="sxs-lookup"><span data-stu-id="60073-128">SOC’s Threat and Vulnerability Management process uses some of Microsoft’s services to help inform recommendations for your organization to protect against threats.</span></span> <span data-ttu-id="60073-129">SOC は、エンドポイントセキュリティセンターと、Microsoft の内外にある関連する脆弱性データソースからのデータを使用して、脆弱性と誤りを発見し、操作可能なレポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="60073-129">The SOC consumes data from your Microsoft Defender for Endpoint Security Center and from relevant vulnerability data sources within and outside of Microsoft to discover vulnerabilities and misconfigurations and provide actionable reporting.</span></span>
