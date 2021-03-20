---
title: Microsoft Managed Desktop でのセキュリティ操作
description: セキュリティ 運用センターが提供するサービスとプロセス
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 600755c15ce6da94481ef4d84732991e5006cce1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908164"
---
# <a name="security-operations-in-microsoft-managed-desktop"></a><span data-ttu-id="07a87-104">Microsoft Managed Desktop でのセキュリティ操作</span><span class="sxs-lookup"><span data-stu-id="07a87-104">Security operations in Microsoft Managed Desktop</span></span>

<span data-ttu-id="07a87-105">Microsoft Managed Desktop Security Operations Center (SOC) は、デスクトップ環境を安全に保つために、情報セキュリティ スタッフと提携しています。</span><span class="sxs-lookup"><span data-stu-id="07a87-105">The Microsoft Managed Desktop Security Operations Center (SOC) partners with your information security staff to keep your desktop environment secure.</span></span> <span data-ttu-id="07a87-106">弊社のチームは、専門家による分析を行い、管理対象デバイス上のすべてのセキュリティアラートを受信して応答し、必要に応じてセキュリティ インシデント対応活動を推進します。</span><span class="sxs-lookup"><span data-stu-id="07a87-106">Our team receives and responds to all security alerts on managed devices with expert analysis and, when needed, we drive security incident response activities.</span></span> <span data-ttu-id="07a87-107">SOC の操作の詳細については、管理ポータルで運用に関するドキュメントを確認してください。</span><span class="sxs-lookup"><span data-stu-id="07a87-107">For more information about working with the SOC, review operational documentation at your Admin portal.</span></span>

<span data-ttu-id="07a87-108">SOC は、ソフトウェア、ネットワーク、または人間の敵対者による一般的な攻撃方法を含む、現在および新しい脅威の状況に関する専門知識を持つ Microsoft のフルタイム従業員から 24 時間 365 日の範囲を提供します。</span><span class="sxs-lookup"><span data-stu-id="07a87-108">The SOC offers 24/7/365 coverage from Microsoft full-time employees with expertise in the current and emerging threat landscape, including common attack methods through software, network, or human adversaries.</span></span>

<span data-ttu-id="07a87-109">SOC は、次のサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="07a87-109">The SOC provides these services:</span></span>
- <span data-ttu-id="07a87-110">検出されたイベントに迅速かつ正確に対応し、データを分析して影響を特定し、デバイスまたは環境に対する全体的なリスクを評価する</span><span class="sxs-lookup"><span data-stu-id="07a87-110">Quick and accurate response to detected events, with analysis of data to identify the impact and assess the overall risk to a device or your environment</span></span>
- <span data-ttu-id="07a87-111">既知または疑わしい侵害から環境を保護するためのデバイス管理と分離アクション。拡散を防止してリスクを軽減する</span><span class="sxs-lookup"><span data-stu-id="07a87-111">Device management and isolation actions to protect your environment from known or suspected compromises, reducing risk by preventing spread</span></span>
- <span data-ttu-id="07a87-112">セキュリティ インシデント対応プロセスを推進し、セキュリティ チームとの迅速かつ正確なコミュニケーションを確保する</span><span class="sxs-lookup"><span data-stu-id="07a87-112">Driving the security incident response process, ensuring timely and accurate communication with your security team</span></span>
- <span data-ttu-id="07a87-113">脅威および脆弱性データに基づく分析と推奨事項により、リスクが悪用される前にリスクを特定して対処する</span><span class="sxs-lookup"><span data-stu-id="07a87-113">Analysis and recommendations based on threat and vulnerability data to identify and address risks before they're exploited</span></span>
- <span data-ttu-id="07a87-114">既知の脅威と潜在的な脅威の両方に関するインジケーターとエンティティを識別するための、管理対象デバイス全体の高度な検出</span><span class="sxs-lookup"><span data-stu-id="07a87-114">Advanced hunting across the managed devices to identify indicators and entities for both known and potential threats</span></span>

## <a name="processes"></a><span data-ttu-id="07a87-115">プロセス</span><span class="sxs-lookup"><span data-stu-id="07a87-115">Processes</span></span>

- <span data-ttu-id="07a87-116">Microsoft Managed Desktop Security Operations は、Microsoft のサイバー防御オペレーション センターと提携して、Microsoft のフルタイムの従業員 [によってスタッフが管理されています](https://www.microsoft.com/msrc/cdoc)。</span><span class="sxs-lookup"><span data-stu-id="07a87-116">Microsoft Managed Desktop Security Operations is staffed by full-time Microsoft employees in partnership with Microsoft’s [Cyber Defense Operations Center](https://www.microsoft.com/msrc/cdoc).</span></span> 
- <span data-ttu-id="07a87-117">Microsoft SOC は、社内外の両方から送信された一括シグナルを使用して、Microsoft Managed Desktop でまだ見ていないものからデバイスを保護します。</span><span class="sxs-lookup"><span data-stu-id="07a87-117">Our SOC uses collective signals from across our company, both internal and external, to protect your devices--even from things we have not yet seen in Microsoft Managed Desktop.</span></span>
- <span data-ttu-id="07a87-118">Microsoft のセキュリティ ソリューションは、多くのサイバーセキュリティ保護標準に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="07a87-118">Microsoft security solutions align to many cybersecurity protection standards.</span></span> <span data-ttu-id="07a87-119">SOC 操作は、国立標準技術研究所のコンピューター セキュリティ インシデント対応対応ガイド (NIST 800-61 r2) に基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="07a87-119">SOC operations are based on the National Institute of Standards and Technology Computer Security Incident Response Handling Guide (NIST 800-61 r2).</span></span>
- <span data-ttu-id="07a87-120">このプロセスでは、次のフェーズを通じて環境をより適切に防御する方法について、分析とドキュメント、および回復後の分析情報を適切に収集できます。</span><span class="sxs-lookup"><span data-stu-id="07a87-120">The process allows for proper collection of information and evidence, for analysis and documentation and post-recovery insights into ways to better defend your environment through these phases:</span></span>
    - <span data-ttu-id="07a87-121">準備、検出、および分析</span><span class="sxs-lookup"><span data-stu-id="07a87-121">Preparation, detection, and analysis</span></span>
    - <span data-ttu-id="07a87-122">コンテインメント</span><span class="sxs-lookup"><span data-stu-id="07a87-122">Containment</span></span>
    - <span data-ttu-id="07a87-123">根絶</span><span class="sxs-lookup"><span data-stu-id="07a87-123">Eradication</span></span>
    - <span data-ttu-id="07a87-124">回復</span><span class="sxs-lookup"><span data-stu-id="07a87-124">Recovery</span></span>
    - <span data-ttu-id="07a87-125">インシデント後のアクティビティ</span><span class="sxs-lookup"><span data-stu-id="07a87-125">Post-incident activity</span></span>
- <span data-ttu-id="07a87-126">Microsoft Managed Desktop のお客様は、Microsoft Threat Experts サービスに登録できます。</span><span class="sxs-lookup"><span data-stu-id="07a87-126">Microsoft Managed Desktop customers are eligible to enroll in the Microsoft Threat Experts service.</span></span> <span data-ttu-id="07a87-127">SOC は、アラートの問い合わせ、潜在的に侵害されたデバイス、疑わしいネットワーク接続の根本原因、継続的な高度な永続的な脅威キャンペーンに関するその他の脅威インテリジェンスなど、組織に影響を与える複雑な脅威をよりよく理解するために、このサービスと連携しています。</span><span class="sxs-lookup"><span data-stu-id="07a87-127">The SOC liaises with this service to understand better the complex threats affecting your organization, including alert inquiries, potentially compromised devices, root cause of a suspicious network connection, and other threat intelligence regarding ongoing advanced persistent threat campaigns.</span></span> <span data-ttu-id="07a87-128">詳細については [、「Microsoft Threat Experts」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts)。</span><span class="sxs-lookup"><span data-stu-id="07a87-128">For more information, see [Microsoft Threat Experts](/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts).</span></span>
- <span data-ttu-id="07a87-129">SOC の脅威と脆弱性管理プロセスでは、Microsoft のサービスの一部を使用して、組織が脅威から保護するための推奨事項を通知するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="07a87-129">SOC’s Threat and Vulnerability Management process uses some of Microsoft’s services to help inform recommendations for your organization to protect against threats.</span></span> <span data-ttu-id="07a87-130">SOC は、Microsoft Defender for Endpoint Security Center および Microsoft の外部および関連する脆弱性データ ソースからのデータを使用して、脆弱性と誤った構成を検出し、アクション可能なレポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="07a87-130">The SOC consumes data from your Microsoft Defender for Endpoint Security Center and from relevant vulnerability data sources within and outside of Microsoft to discover vulnerabilities and misconfigurations and provide actionable reporting.</span></span>