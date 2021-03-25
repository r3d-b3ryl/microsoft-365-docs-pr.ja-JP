---
title: 脅威保護 (Windows 10)
description: Microsoft Defender for Endpoint は、予防的な保護、侵害後の検出、自動調査、対応のための統一されたプラットフォームです。
keywords: 脅威保護、Microsoft Defender Advanced Threat Protection、攻撃表面の縮小、次世代保護、エンドポイントの検出と対応、自動調査と対応、Microsoft Threat Experts、Microsoft Secure Score for Devices、Advanced Hunting、Cyber Threat Hunting、Web Threat Protection
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 4206519d62feb82bbc297659e01b0cc3902b83dc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51061162"
---
# <a name="threat-protection"></a><span data-ttu-id="3bd20-104">脅威の防止</span><span class="sxs-lookup"><span data-stu-id="3bd20-104">Threat Protection</span></span>
<span data-ttu-id="3bd20-105">[Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection) は、予防的な保護、侵害後の検出、自動調査、対応のための統一されたプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="3bd20-105">[Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection) is a unified platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> <span data-ttu-id="3bd20-106">Defender for Endpoint は、エンドポイントをサイバー脅威から保護し、高度な攻撃とデータ侵害を検出し、セキュリティ インシデントを自動化し、セキュリティの態勢を改善します。</span><span class="sxs-lookup"><span data-stu-id="3bd20-106">Defender for Endpoint protects endpoints from cyber threats, detects advanced attacks and data breaches, automates security incidents, and improves security posture.</span></span>

> [!TIP]
> <span data-ttu-id="3bd20-107">ユーザーがクラウド サービスとオンプレミス アプリケーションに簡単にアクセスし、すべてのデバイスで最新の管理機能を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="3bd20-107">Enable your users to access cloud services and on-premises applications with ease and enable modern management capabilities for all devices.</span></span> <span data-ttu-id="3bd20-108">詳細については、「リモートワークフォース [のセキュリティ保護」を参照してください](https://docs.microsoft.com/enterprise-mobility-security/remote-work/)。</span><span class="sxs-lookup"><span data-stu-id="3bd20-108">For more information, see [Secure your remote workforce](https://docs.microsoft.com/enterprise-mobility-security/remote-work/).</span></span> 

<center><h2><span data-ttu-id="3bd20-109">エンドポイント用 Microsoft Defender</center></span><span class="sxs-lookup"><span data-stu-id="3bd20-109">Microsoft Defender for Endpoint</center></span></span></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="threat and vulnerability icon"> <br><span data-ttu-id="3bd20-110"><b>脅威&の管理</b></center></a></span><span class="sxs-lookup"><span data-stu-id="3bd20-110"><b>Threat & vulnerability management</b></center></a></span></span></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="attack surface reduction icon"> <br><span data-ttu-id="3bd20-111"><b>攻撃表面の縮小</b></center></a></span><span class="sxs-lookup"><span data-stu-id="3bd20-111"><b>Attack surface reduction</b></center></a></span></span></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="next generation protection icon"><br> <span data-ttu-id="3bd20-112"><b>次世代の保護</b></a></center></span><span class="sxs-lookup"><span data-stu-id="3bd20-112"><b>Next-generation protection</b></a></center></span></span></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="endpoint detection and response icon"><br> <span data-ttu-id="3bd20-113"><b>エンドポイントの検出と応答</b></a></center></span><span class="sxs-lookup"><span data-stu-id="3bd20-113"><b>Endpoint detection and response</b></a></center></span></span></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="automated investigation and remediation icon"><br> <span data-ttu-id="3bd20-114"><b>自動調査と修復</b></a></center></span><span class="sxs-lookup"><span data-stu-id="3bd20-114"><b>Automated investigation and remediation</b></a></center></span></span></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="microsoft threat experts icon"><br> <span data-ttu-id="3bd20-115"><b>Microsoft Threat Experts</b></a></center></span><span class="sxs-lookup"><span data-stu-id="3bd20-115"><b>Microsoft Threat Experts</b></a></center></span></span></td>
</tr>
<tr>
<td colspan="7"><span data-ttu-id="3bd20-116">
<a href="#apis"><center><b>一元的な構成と管理、API</a></span><span class="sxs-lookup"><span data-stu-id="3bd20-116">
<a href="#apis"><center><b>Centralized configuration and administration, APIs</a></span></span></b></center></td>
</tr>
<tr>
<td colspan="7"><span data-ttu-id="3bd20-117"><a href="#mtp"><center><b>Microsoft 365 Defender</a></span><span class="sxs-lookup"><span data-stu-id="3bd20-117"><a href="#mtp"><center><b>Microsoft 365 Defender</a></span></span></center></b></td>
</tr>
</table>
<br>

<a name="tvm"></a>


>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4obJq]

<span data-ttu-id="3bd20-118">**[脅威&の管理](next-gen-threat-and-vuln-mgt.md)**</span><span class="sxs-lookup"><span data-stu-id="3bd20-118">**[Threat & vulnerability management](next-gen-threat-and-vuln-mgt.md)**</span></span><br>
<span data-ttu-id="3bd20-119">この組み込み機能では、エンドポイントの脆弱性と誤った構成の検出、事前設定、修復に対して、ゲームを変えるリスクベースのアプローチを使用します。</span><span class="sxs-lookup"><span data-stu-id="3bd20-119">This built-in capability uses a game-changing risk-based approach to the discovery, prioritization, and remediation of endpoint vulnerabilities and misconfigurations.</span></span>

- [<span data-ttu-id="3bd20-120">脅威&の管理の概要</span><span class="sxs-lookup"><span data-stu-id="3bd20-120">Threat & vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="3bd20-121">概要</span><span class="sxs-lookup"><span data-stu-id="3bd20-121">Get started</span></span>](tvm-prerequisites.md)
- [<span data-ttu-id="3bd20-122">セキュリティの姿勢にアクセスする</span><span class="sxs-lookup"><span data-stu-id="3bd20-122">Access your security posture</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="3bd20-123">セキュリティの態勢を改善し、リスクを軽減する</span><span class="sxs-lookup"><span data-stu-id="3bd20-123">Improve your security posture and reduce risk</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="3bd20-124">デバイスの脆弱性を理解する</span><span class="sxs-lookup"><span data-stu-id="3bd20-124">Understand vulnerabilities on your devices</span></span>](tvm-software-inventory.md)

<a name="asr"></a>

<span data-ttu-id="3bd20-125">**[攻撃面の縮小](overview-attack-surface-reduction.md)**</span><span class="sxs-lookup"><span data-stu-id="3bd20-125">**[Attack surface reduction](overview-attack-surface-reduction.md)**</span></span><br>
<span data-ttu-id="3bd20-126">攻撃表面の縮小機能のセットは、スタック内の防御の最初の行を提供します。</span><span class="sxs-lookup"><span data-stu-id="3bd20-126">The attack surface reduction set of capabilities provide the first line of defense in the stack.</span></span> <span data-ttu-id="3bd20-127">構成設定が適切に設定され、悪用の軽減手法が適用されていることを確認することで、これらの一連の機能は攻撃と悪用に抵抗します。</span><span class="sxs-lookup"><span data-stu-id="3bd20-127">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span>

- [<span data-ttu-id="3bd20-128">ハードウェア ベースの分離</span><span class="sxs-lookup"><span data-stu-id="3bd20-128">Hardware based isolation</span></span>](overview-hardware-based-isolation.md)
- [<span data-ttu-id="3bd20-129">アプリケーション制御</span><span class="sxs-lookup"><span data-stu-id="3bd20-129">Application control</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)
- [<span data-ttu-id="3bd20-130">デバイス制御</span><span class="sxs-lookup"><span data-stu-id="3bd20-130">Device control</span></span>](https://docs.microsoft.com/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)
- [<span data-ttu-id="3bd20-131">エクスプロイト保護</span><span class="sxs-lookup"><span data-stu-id="3bd20-131">Exploit protection</span></span>](exploit-protection.md)
- <span data-ttu-id="3bd20-132">[ネットワーク保護](network-protection.md) [、Web 保護](web-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="3bd20-132">[Network protection](network-protection.md), [web protection](web-protection-overview.md)</span></span>
- [<span data-ttu-id="3bd20-133">フォルダー アクセスの制御</span><span class="sxs-lookup"><span data-stu-id="3bd20-133">Controlled folder access</span></span>](controlled-folders.md)
- [<span data-ttu-id="3bd20-134">ネットワーク ファイアウォール</span><span class="sxs-lookup"><span data-stu-id="3bd20-134">Network firewall</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
- [<span data-ttu-id="3bd20-135">攻撃面の減少ルール</span><span class="sxs-lookup"><span data-stu-id="3bd20-135">Attack surface reduction rules</span></span>](attack-surface-reduction.md)

<a name="ngp"></a>

<span data-ttu-id="3bd20-136">**[次世代の保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**</span><span class="sxs-lookup"><span data-stu-id="3bd20-136">**[Next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**</span></span><br>
<span data-ttu-id="3bd20-137">Microsoft Defender for Endpoint は、ネットワークのセキュリティ境界をさらに強化するために、すべての種類の新しい脅威をキャッチするように設計された次世代の保護を使用します。</span><span class="sxs-lookup"><span data-stu-id="3bd20-137">To further reinforce the security perimeter of your network, Microsoft Defender for Endpoint uses next-generation protection designed to catch all types of emerging threats.</span></span>

- [<span data-ttu-id="3bd20-138">動作の監視</span><span class="sxs-lookup"><span data-stu-id="3bd20-138">Behavior monitoring</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)
- [<span data-ttu-id="3bd20-139">クラウドベースの保護</span><span class="sxs-lookup"><span data-stu-id="3bd20-139">Cloud-based protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-protection-features-microsoft-defender-antivirus)
- [<span data-ttu-id="3bd20-140">機械学習</span><span class="sxs-lookup"><span data-stu-id="3bd20-140">Machine learning</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [<span data-ttu-id="3bd20-141">URL 保護</span><span class="sxs-lookup"><span data-stu-id="3bd20-141">URL Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)
- [<span data-ttu-id="3bd20-142">自動サンドボックス サービス</span><span class="sxs-lookup"><span data-stu-id="3bd20-142">Automated sandbox service</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

<a name="edr"></a>

<span data-ttu-id="3bd20-143">**[エンドポイントの検出および応答](overview-endpoint-detection-response.md)**</span><span class="sxs-lookup"><span data-stu-id="3bd20-143">**[Endpoint detection and response](overview-endpoint-detection-response.md)**</span></span><br>
<span data-ttu-id="3bd20-144">エンドポイントの検出および応答機能は、侵入の試みとアクティブな侵害を検出、調査、および対応するために配置されます。</span><span class="sxs-lookup"><span data-stu-id="3bd20-144">Endpoint detection and response capabilities are put in place to detect, investigate, and respond to intrusion attempts and active breaches.</span></span> <span data-ttu-id="3bd20-145">高度な検出機能を使用すると、クエリベースの脅威検出ツールを使用して、侵害を積極的に検出し、カスタム検出を作成できます。</span><span class="sxs-lookup"><span data-stu-id="3bd20-145">With Advanced hunting, you have a query-based threat-hunting tool that lets your proactively find breaches and create custom detections.</span></span>

- [<span data-ttu-id="3bd20-146">Alerts</span><span class="sxs-lookup"><span data-stu-id="3bd20-146">Alerts</span></span>](alerts-queue.md)
- [<span data-ttu-id="3bd20-147">エンドポイント データの履歴</span><span class="sxs-lookup"><span data-stu-id="3bd20-147">Historical endpoint data</span></span>](investigate-machines.md#timeline)
- [<span data-ttu-id="3bd20-148">応答オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="3bd20-148">Response orchestration</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)
- [<span data-ttu-id="3bd20-149">Forensic コレクション</span><span class="sxs-lookup"><span data-stu-id="3bd20-149">Forensic collection</span></span>](respond-machine-alerts.md#collect-investigation-package-from-devices)
- [<span data-ttu-id="3bd20-150">脅威インテリジェンス</span><span class="sxs-lookup"><span data-stu-id="3bd20-150">Threat intelligence</span></span>](threat-indicator-concepts.md)
- [<span data-ttu-id="3bd20-151">高度なデトレーションと分析サービス</span><span class="sxs-lookup"><span data-stu-id="3bd20-151">Advanced detonation and analysis service</span></span>](respond-file-alerts.md#deep-analysis)
- [<span data-ttu-id="3bd20-152">高度な検出</span><span class="sxs-lookup"><span data-stu-id="3bd20-152">Advanced hunting</span></span>](advanced-hunting-overview.md)
    - [<span data-ttu-id="3bd20-153">カスタム検出</span><span class="sxs-lookup"><span data-stu-id="3bd20-153">Custom detections</span></span>](overview-custom-detections.md)

<a name="ai"></a>

<span data-ttu-id="3bd20-154">**[調査と修復の自動化](automated-investigations.md)**</span><span class="sxs-lookup"><span data-stu-id="3bd20-154">**[Automated investigation and remediation](automated-investigations.md)**</span></span><br>
<span data-ttu-id="3bd20-155">高度な攻撃への迅速な対応に加えて、Microsoft Defender for Endpoint は自動調査と修復機能を提供し、アラートの量を数分で削減できます。</span><span class="sxs-lookup"><span data-stu-id="3bd20-155">In addition to quickly responding to advanced attacks, Microsoft Defender for Endpoint offers automatic investigation and remediation capabilities that help reduce the volume of alerts in minutes at scale.</span></span>

- [<span data-ttu-id="3bd20-156">調査と修復の自動化</span><span class="sxs-lookup"><span data-stu-id="3bd20-156">Automated investigation and remediation</span></span>](automated-investigations.md)
- [<span data-ttu-id="3bd20-157">自動調査の詳細と結果を表示する</span><span class="sxs-lookup"><span data-stu-id="3bd20-157">View details and results of automated investigations</span></span>](auto-investigation-action-center.md)
- [<span data-ttu-id="3bd20-158">修復アクションの表示と承認</span><span class="sxs-lookup"><span data-stu-id="3bd20-158">View and approve remediation actions</span></span>](manage-auto-investigation.md)

<a name="mte"></a>

<span data-ttu-id="3bd20-159">**[Microsoft 脅威エキスパート](microsoft-threat-experts.md)**</span><span class="sxs-lookup"><span data-stu-id="3bd20-159">**[Microsoft Threat Experts](microsoft-threat-experts.md)**</span></span><br>
<span data-ttu-id="3bd20-160">Microsoft Defender for Endpoint の新しい管理された脅威検出サービスは、プロアクティブな狩猟、事前承認、追加のコンテキストと分析情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="3bd20-160">Microsoft Defender for Endpoint's new managed threat hunting service provides proactive hunting, prioritization, and additional context and insights.</span></span> <span data-ttu-id="3bd20-161">Microsoft Threat Experts は、セキュリティ オペレーション センター (SOC) が脅威を迅速かつ正確に特定して対応する権限をさらに強化します。</span><span class="sxs-lookup"><span data-stu-id="3bd20-161">Microsoft Threat Experts further empowers Security Operation Centers (SOCs) to identify and respond to threats quickly and accurately.</span></span>

- [<span data-ttu-id="3bd20-162">標的型攻撃の通知</span><span class="sxs-lookup"><span data-stu-id="3bd20-162">Targeted attack notification</span></span>](microsoft-threat-experts.md)
- [<span data-ttu-id="3bd20-163">エキスパートオンデマンド</span><span class="sxs-lookup"><span data-stu-id="3bd20-163">Experts-on-demand</span></span>](microsoft-threat-experts.md)
- [<span data-ttu-id="3bd20-164">Microsoft 365 Defender マネージ ハンティング サービスを構成する</span><span class="sxs-lookup"><span data-stu-id="3bd20-164">Configure your Microsoft 365 Defender managed hunting service</span></span>](configure-microsoft-threat-experts.md)

<a name="apis"></a>

<span data-ttu-id="3bd20-165">**[一元的な構成と管理、API](management-apis.md)**</span><span class="sxs-lookup"><span data-stu-id="3bd20-165">**[Centralized configuration and administration, APIs](management-apis.md)**</span></span><br>
<span data-ttu-id="3bd20-166">Microsoft Defender for Endpoint を既存のワークフローに統合します。</span><span class="sxs-lookup"><span data-stu-id="3bd20-166">Integrate Microsoft Defender for Endpoint into your existing workflows.</span></span>
- [<span data-ttu-id="3bd20-167">オンボード</span><span class="sxs-lookup"><span data-stu-id="3bd20-167">Onboarding</span></span>](onboard-configure.md)
- [<span data-ttu-id="3bd20-168">API と SIEM の統合</span><span class="sxs-lookup"><span data-stu-id="3bd20-168">API and SIEM integration</span></span>](configure-siem.md)
- [<span data-ttu-id="3bd20-169">公開された API</span><span class="sxs-lookup"><span data-stu-id="3bd20-169">Exposed APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="3bd20-170">役割ベースのアクセス制御 (RBAC)</span><span class="sxs-lookup"><span data-stu-id="3bd20-170">Role-based access control (RBAC)</span></span>](rbac.md)
- [<span data-ttu-id="3bd20-171">レポートと傾向</span><span class="sxs-lookup"><span data-stu-id="3bd20-171">Reporting and trends</span></span>](threat-protection-reports.md)

<a name="integration"></a>
<span data-ttu-id="3bd20-172">**[Microsoft ソリューションとの統合](threat-protection-integration.md)**</span><span class="sxs-lookup"><span data-stu-id="3bd20-172">**[Integration with Microsoft solutions](threat-protection-integration.md)**</span></span> <br>
 <span data-ttu-id="3bd20-173">Microsoft Defender for Endpoint は、以下を含むさまざまな Microsoft ソリューションと直接統合します。</span><span class="sxs-lookup"><span data-stu-id="3bd20-173">Microsoft Defender for Endpoint directly integrates with various Microsoft solutions, including:</span></span>
- <span data-ttu-id="3bd20-174">Intune</span><span class="sxs-lookup"><span data-stu-id="3bd20-174">Intune</span></span>
- <span data-ttu-id="3bd20-175">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="3bd20-175">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="3bd20-176">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="3bd20-176">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="3bd20-177">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="3bd20-177">Azure Defender</span></span>
- <span data-ttu-id="3bd20-178">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3bd20-178">Skype for Business</span></span>
- <span data-ttu-id="3bd20-179">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="3bd20-179">Microsoft Cloud App Security</span></span>

<a name="mtp"></a>
<span data-ttu-id="3bd20-180">**[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)**</span><span class="sxs-lookup"><span data-stu-id="3bd20-180">**[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)**</span></span><br>
 <span data-ttu-id="3bd20-181">Microsoft 365 Defender を使用すると、Microsoft Defender for Endpoint およびさまざまな Microsoft セキュリティ ソリューションが統合された侵害前および侵害後のエンタープライズ防御スイートを形成し、エンドポイント、ID、電子メール、アプリケーション間でネイティブに統合され、高度な攻撃を検出、防止、調査、および自動的に対応します。</span><span class="sxs-lookup"><span data-stu-id="3bd20-181">With Microsoft 365 Defender, Microsoft Defender for Endpoint and various Microsoft security solutions form a unified pre- and post-breach enterprise defense suite that natively integrates across endpoint, identity, email, and applications to detect, prevent, investigate, and automatically respond to sophisticated attacks.</span></span>