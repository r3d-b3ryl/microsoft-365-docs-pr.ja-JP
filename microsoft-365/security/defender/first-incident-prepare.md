---
title: 最初のインシデントのセキュリティ態勢を準備する
description: Defender でMicrosoft 365インシデントに対して、テナントのセキュリティ態勢をMicrosoft 365します。
keywords: インシデント、アラート、調査、相関、攻撃、マシン、デバイス、ユーザー、複数の ID、ID、メールボックス、メール、365、Microsoft、M365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 76bead8fd855e4119db6297d2ab1a3d08d64a48c
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297166"
---
# <a name="prepare-your-security-posture-for-your-first-incident"></a><span data-ttu-id="a49cc-104">最初のインシデントのセキュリティ態勢を準備する</span><span class="sxs-lookup"><span data-stu-id="a49cc-104">Prepare your security posture for your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="a49cc-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a49cc-105">**Applies to:**</span></span>
- <span data-ttu-id="a49cc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a49cc-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="a49cc-107">インシデント処理の準備には、さまざまな種類のセキュリティ インシデントから組織のネットワークを十分に保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a49cc-107">Preparing for incident handling involves setting up sufficient protection of an organization's network from different kinds of security incidents.</span></span> <span data-ttu-id="a49cc-108">セキュリティ インシデントのリスクを軽減するために、国立標準技術研究所 (NIST) では、リスク評価、ホスト セキュリティの強化、ネットワークの安全な構成、マルウェアの防止など、いくつかのセキュリティプラクティスを推奨しています。</span><span class="sxs-lookup"><span data-stu-id="a49cc-108">To reduce the risk of security incidents, National Institute of Standards and Technology (NIST) recommends several security practices including risk assessments, hardening host security, configuring networks securely, and preventing malware.</span></span> 

<span data-ttu-id="a49cc-109">Microsoft 365Defender は、インシデント防止のいくつかの側面に対処するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a49cc-109">Microsoft 365 Defender can help address several aspects of incident prevention:</span></span> 

- <span data-ttu-id="a49cc-110">ゼロトラスト フレームワーク [の](https://docs.microsoft.com/security/zero-trust/) 実装</span><span class="sxs-lookup"><span data-stu-id="a49cc-110">Implementing a [Zero Trust](https://docs.microsoft.com/security/zero-trust/) framework</span></span>
- <span data-ttu-id="a49cc-111">Microsoft Secure Score でスコアを割り当て、セキュリティの態勢 [を決定する](microsoft-secure-score.md)</span><span class="sxs-lookup"><span data-stu-id="a49cc-111">Determining your security posture by assigning a score with [Microsoft Secure Score](microsoft-secure-score.md)</span></span>
- <span data-ttu-id="a49cc-112">脅威と脆弱性管理の脆弱性評価による [脅威の防止](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="a49cc-112">Preventing threats through vulnerability assessments in [Threat and Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span></span>
- <span data-ttu-id="a49cc-113">最新のセキュリティ脅威を理解して、セキュリティ脅威に備える</span><span class="sxs-lookup"><span data-stu-id="a49cc-113">Understanding the latest security threats so you can prepare for them</span></span>

## <a name="step-1-implement-zero-trust"></a><span data-ttu-id="a49cc-114">手順 1.</span><span class="sxs-lookup"><span data-stu-id="a49cc-114">Step 1.</span></span> <span data-ttu-id="a49cc-115">ゼロ信頼の実装</span><span class="sxs-lookup"><span data-stu-id="a49cc-115">Implement Zero Trust</span></span>

<span data-ttu-id="a49cc-116">[ゼロトラスト](https://docs.microsoft.com/security/zero-trust/) は、モバイルワークフォース、ユーザー、デバイス、アプリケーション、データなど、モダンな環境の複雑な性質を考慮した統合セキュリティ哲学とエンドツーエンド戦略です。</span><span class="sxs-lookup"><span data-stu-id="a49cc-116">[Zero Trust](https://docs.microsoft.com/security/zero-trust/) is an integrated security philosophy and end-to-end strategy that considers the complex nature of any modern environment, including the mobile workforce and the users, devices, applications and data, wherever they may be located.</span></span> <span data-ttu-id="a49cc-117">Microsoft 365 Defender は、すべてのエンドポイント検出を一貫した方法で管理するための単一のウィンドウを提供することで、セキュリティ運用チームがゼロトラストの指針を実装[](https://docs.microsoft.com/security/zero-trust/#guiding-principles-of-zero-trust)しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="a49cc-117">By providing a single pane of glass to manage all endpoint detections in a consistent way, Microsoft 365 Defender can make it easier for your security operations team to implement the [guiding principles](https://docs.microsoft.com/security/zero-trust/#guiding-principles-of-zero-trust) of Zero Trust.</span></span> 

<span data-ttu-id="a49cc-118">Microsoft 365 Defender のコンポーネントは、デバイス コンプライアンス ポリシーの情報ソースとして Microsoft Defender for Endpoint (MDE) または他のモバイル セキュリティ ベンダーからのデータを統合し、デバイス ベースの条件付きアクセス ポリシーを実装することで、ゼロトラストの条件付きアクセス ポリシーを確立するために実装されているルールの違反を表示できます。</span><span class="sxs-lookup"><span data-stu-id="a49cc-118">Components of Microsoft 365 Defender can display violations of rules that have been implemented to establish Conditional Access policies for Zero Trust by integrating data from Microsoft Defender for Endpoint (MDE) or other mobile security vendors as an information source for device compliance policies and implementation of device-based Conditional Access policies.</span></span> 

<span data-ttu-id="a49cc-119">デバイスリスクは、そのデバイスのユーザーがアクセスできるリソースに直接影響します。</span><span class="sxs-lookup"><span data-stu-id="a49cc-119">Device risk directly influences what resources will be accessible by the user of that device.</span></span> <span data-ttu-id="a49cc-120">特定の条件に基づくリソースへのアクセス拒否は、ゼロ信頼の主なテーマであり、信頼レベルの基準を決定するためにMicrosoft 365 Defender が必要な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="a49cc-120">The denial of access to resources based on certain criteria is the main theme of Zero Trust and Microsoft 365 Defender provides information needed to determine the trust level criteria.</span></span> <span data-ttu-id="a49cc-121">たとえば、Microsoft 365 Defender は[脅威と脆弱性の管理] ページを通じてデバイスのソフトウェア バージョン レベルを提供し、条件付きアクセス ポリシーでは古いバージョンまたは脆弱なバージョンのデバイスを制限します。</span><span class="sxs-lookup"><span data-stu-id="a49cc-121">For example, Microsoft 365 Defender can provide the software version level of a device through the Threat and Vulnerability Management page while Conditional Access policies restrict devices that have outdated or vulnerable versions.</span></span>

<span data-ttu-id="a49cc-122">自動化は、ゼロトラスト環境を実装して維持する上で重要な部分であり、インシデント対応 (IR) イベントにつながる可能性のあるアラートの数も減らします。</span><span class="sxs-lookup"><span data-stu-id="a49cc-122">Automation is a crucial part of implementing and maintaining a Zero Trust environment while also reducing the number of alerts that would potentially lead to incident response (IR) events.</span></span> <span data-ttu-id="a49cc-123">Microsoft 365 Defender のコンポーネントは、修復アクション[(Microsoft 365](m365d-autoir.md)セキュリティ センターでのインシデントの調査と呼ばれる)、通知アクション[、ServiceNow](https://microsoft.service-now.com/sp/)などのサポート チケットの作成など、自動化できます。</span><span class="sxs-lookup"><span data-stu-id="a49cc-123">Components of Microsoft 365 Defender can be automated such as [remediation actions](m365d-autoir.md) (known as investigations for an incident in the Microsoft 365 security center), notification actions, and even the creation of support tickets such as in [ServiceNow](https://microsoft.service-now.com/sp/).</span></span>

## <a name="step-2-determine-your-organizations-security-posture"></a><span data-ttu-id="a49cc-124">手順 2.</span><span class="sxs-lookup"><span data-stu-id="a49cc-124">Step 2.</span></span> <span data-ttu-id="a49cc-125">組織のセキュリティ体制を決定する</span><span class="sxs-lookup"><span data-stu-id="a49cc-125">Determine your organization’s security posture</span></span>

<span data-ttu-id="a49cc-126">次に、組織は[Defender](microsoft-secure-score.md)の Microsoft Secure Score をMicrosoft 365して、現在のセキュリティの状態を判断し、その改善方法に関する推奨事項を検討できます。</span><span class="sxs-lookup"><span data-stu-id="a49cc-126">Next, organizations can use the [Microsoft Secure Score](microsoft-secure-score.md) in Microsoft 365 Defender to determine your current security posture and consider recommendations on how to improve it.</span></span> <span data-ttu-id="a49cc-127">スコアが高いほど、組織によってセキュリティに関する推奨事項と改善のアクションが多くなります。</span><span class="sxs-lookup"><span data-stu-id="a49cc-127">The higher the score is, the more security recommendations and improvement actions have been taken by the organization.</span></span> <span data-ttu-id="a49cc-128">セキュリティで保護されたスコアの推奨事項は、さまざまな製品間で取り上げ、組織がスコアを上げるのをさらに高くすることができます。</span><span class="sxs-lookup"><span data-stu-id="a49cc-128">Secure Score recommendations can be taken across different products and allow organizations to raise their scores even higher.</span></span> 

:::image type="content" source="../../media/first-incident-prepare/first-incident-secure-score.png" alt-text="Microsoft セキュリティ センターの Microsoft Secure Score の例":::
 
## <a name="step-3-assess-your-organizations-vulnerability-exposure"></a><span data-ttu-id="a49cc-130">手順 3.</span><span class="sxs-lookup"><span data-stu-id="a49cc-130">Step 3.</span></span> <span data-ttu-id="a49cc-131">組織の脆弱性の暴露を評価する</span><span class="sxs-lookup"><span data-stu-id="a49cc-131">Assess your organization’s vulnerability exposure</span></span>

<span data-ttu-id="a49cc-132">インシデントを防止すると、セキュリティ運用の取り組みを合理化し、重要で重要なセキュリティ インシデントに集中できます。</span><span class="sxs-lookup"><span data-stu-id="a49cc-132">Preventing incidents can help streamline security operations efforts to focus on on-going critical and important security incidents.</span></span> <span data-ttu-id="a49cc-133">ソフトウェアの脆弱性は、多くの場合、データの盗難、データの損失、またはビジネス操作の中断につながる可能性のある攻撃の予防可能なエントリ ポイントです。</span><span class="sxs-lookup"><span data-stu-id="a49cc-133">Software vulnerabilities are often a preventable entry point for attacks that can lead to data theft, data loss, or disruption of business operations.</span></span> <span data-ttu-id="a49cc-134">攻撃が継続的に行なえない場合、セキュリティ運用は、組織内で許容できるレベルの脆弱性の暴露を達成し、維持するために [努力する必要](../defender-endpoint/tvm-exposure-score.md) があります。</span><span class="sxs-lookup"><span data-stu-id="a49cc-134">If no attacks are on-going, security operations must strive to achieve and maintain an acceptable level of [vulnerability exposure](../defender-endpoint/tvm-exposure-score.md) in their organization.</span></span>

<span data-ttu-id="a49cc-135">ソフトウェアの修正プログラムの進行状況を確認するには、Defender for Endpoint の [脅威と脆弱性の管理] ページを参照し、Microsoft 365 Defender から [その他のリソース] タブに **アクセス** できます。 [](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="a49cc-135">To check your software patching progress, visit the [Threat and Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md) page in Defender for Endpoint, which you can access from Microsoft 365 Defender through the **More resources** tab.</span></span>

:::image type="content" source="../../media/first-incident-prepare/first-incident-vulnerability.png" alt-text="Microsoft セキュリティ センターの [脅威と脆弱性] ページの例"::: 
 
## <a name="4-understand-emerging-threats"></a><span data-ttu-id="a49cc-137">4. 新たな脅威を理解する</span><span class="sxs-lookup"><span data-stu-id="a49cc-137">4. Understand emerging threats</span></span>

<span data-ttu-id="a49cc-138">セキュリティ[センターで脅威](threat-analytics.md)Microsoft 365分析を使用して、現在のセキュリティ脅威の状況を最新の状態に保つ。</span><span class="sxs-lookup"><span data-stu-id="a49cc-138">Use [threat analytics](threat-analytics.md) in the Microsoft 365 security center to keep up-to-date with the current security threat landscape.</span></span> <span data-ttu-id="a49cc-139">Microsoft のセキュリティ専門家は、最新のサイバー脅威を詳細に説明するレポートを作成し、Microsoft 365 サブスクリプション、デバイス、およびユーザーにどのような影響を与えるのか理解できます。</span><span class="sxs-lookup"><span data-stu-id="a49cc-139">Expert Microsoft security researchers create reports that describe the latest cyber-threats in detail so you can understand how they might affect your Microsoft 365 subscription, devices, and users.</span></span> <span data-ttu-id="a49cc-140">これらのレポートには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a49cc-140">These reports can include:</span></span>

- <span data-ttu-id="a49cc-141">アクティブな脅威アクターとそのキャンペーン</span><span class="sxs-lookup"><span data-stu-id="a49cc-141">Active threat actors and their campaigns</span></span>
- <span data-ttu-id="a49cc-142">人気のある新しい攻撃手法</span><span class="sxs-lookup"><span data-stu-id="a49cc-142">Popular and new attack techniques</span></span>
- <span data-ttu-id="a49cc-143">重大な脆弱性</span><span class="sxs-lookup"><span data-stu-id="a49cc-143">Critical vulnerabilities</span></span>
- <span data-ttu-id="a49cc-144">一般的な攻撃の表面</span><span class="sxs-lookup"><span data-stu-id="a49cc-144">Common attack surfaces</span></span>
- <span data-ttu-id="a49cc-145">一般的なマルウェア</span><span class="sxs-lookup"><span data-stu-id="a49cc-145">Prevalent malware</span></span>

<span data-ttu-id="a49cc-146">新たな脅威の推奨事項を実装して、セキュリティ体制を強化し、攻撃の表面領域を最小限に抑える。</span><span class="sxs-lookup"><span data-stu-id="a49cc-146">You can implement the recommendations of an emerging threat to strengthen your security posture and minimize your attack surface area.</span></span>

<span data-ttu-id="a49cc-147">スケジュール内で、セキュリティ センターの[[Threat Analytics]](threat-analytics.md)セクションを定期的に確認Microsoft 365してください。</span><span class="sxs-lookup"><span data-stu-id="a49cc-147">Make time in your schedule to regularly check the [Threat Analytics](threat-analytics.md) section of the Microsoft 365 security center.</span></span>

## <a name="next-step"></a><span data-ttu-id="a49cc-148">次の手順</span><span class="sxs-lookup"><span data-stu-id="a49cc-148">Next step</span></span>

<span data-ttu-id="a49cc-149">[![手順 1: インシデントをトリアージして分析する方法について学習する](../../media/first-incident-overview/first-incident-path-step1.png)](first-incident-analyze.md)</span><span class="sxs-lookup"><span data-stu-id="a49cc-149">[![Step 1: Learn how to triage and analyze incidents](../../media/first-incident-overview/first-incident-path-step1.png)](first-incident-analyze.md)</span></span>

<span data-ttu-id="a49cc-150">インシデントをトリアー [ジして分析する方法について学習します](first-incident-analyze.md)。</span><span class="sxs-lookup"><span data-stu-id="a49cc-150">Learn how to [triage and analyze incidents](first-incident-analyze.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a49cc-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="a49cc-151">See also</span></span>

- [<span data-ttu-id="a49cc-152">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="a49cc-152">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="a49cc-153">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="a49cc-153">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="a49cc-154">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="a49cc-154">Manage incidents</span></span>](manage-incidents.md)
