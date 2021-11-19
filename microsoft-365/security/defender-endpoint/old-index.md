---
title: 脅威保護 (Windows 10)
description: Microsoft Defender for Endpoint は、予防的な保護、侵害後の検出、自動調査、対応のための統一されたプラットフォームです。
keywords: 脅威保護、Microsoft Defender for Endpoint、攻撃表面の縮小、次世代保護、エンドポイントの検出と対応、自動調査と対応、Microsoft Threat Experts、Microsoft Secure Score for Devices、Advanced Hunting、Cyber Threat Hunting、Web Threat Protection
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: c19189ab33fca3c537347c0d20d14d602fe99da3
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2021
ms.locfileid: "61109037"
---
# <a name="threat-protection"></a>脅威保護

[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection) は、予防的な保護、侵害後の検出、自動調査、対応のための統一されたプラットフォームです。 Defender for Endpoint は、エンドポイントをサイバー脅威から保護し、高度な攻撃とデータ侵害を検出し、セキュリティ インシデントを自動化し、セキュリティの態勢を改善します。

> [!TIP]
> ユーザーがクラウド サービスとオンプレミス アプリケーションに簡単にアクセスし、すべてのデバイスで最新の管理機能を有効にできます。 詳細については、「リモートワークフォース [のセキュリティ保護」を参照してください](/enterprise-mobility-security/remote-work/)。 

<center><h2>Microsoft Defender for Endpoint</center></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="threat and vulnerability icon"> <br><b>脅威& 脆弱性の管理</b></center></a></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="attack surface reduction icon"> <br><b>攻撃面の減少</b></center></a></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="next generation protection icon"><br> <b>次世代の保護</b></a></center></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="endpoint detection and response icon"><br> <b>エンドポイントでの検出と対応</b></a></center></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="automated investigation and remediation icon"><br> <b>調査と修復の自動化</b></a></center></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="microsoft threat experts icon"><br> <b>Microsoft 脅威エキスパート</b></a></center></td>
</tr>
<tr>
<td colspan="7">
<a href="#apis"><center><b>一元的な構成と管理、API</a></b></center></td>
</tr>
<tr>
<td colspan="7"><a href="#mtp"><center><b>Microsoft 365 Defender</a></center></b></td>
</tr>
</table>
<br>

<a name="tvm"></a>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4obJq]

**[脅威& 脆弱性の管理](next-gen-threat-and-vuln-mgt.md)**<br>
この組み込み機能は、画期的なリスクベースのアプローチを使用してエンドポイントの脆弱性や構成ミスの検出、優先順位付け、および修復を行います。

- [脅威& 脆弱性の管理概要](next-gen-threat-and-vuln-mgt.md)
- [概要](tvm-prerequisites.md)
- [セキュリティの姿勢にアクセスする](tvm-dashboard-insights.md)
- [セキュリティの状態の改善とリスクの軽減](tvm-security-recommendation.md)
- [デバイスの脆弱性を理解する](tvm-software-inventory.md)

<a name="asr"></a>

**[攻撃面の減少](overview-attack-surface-reduction.md)**<br>
攻撃表面の縮小機能のセットは、スタック内の防御の最初の行を提供します。 構成設定が適切に設定され、悪用の軽減手法が適用されていることを確認することで、これらの一連の機能は攻撃と悪用に抵抗します。

- [ハードウェア ベースの分離](overview-hardware-based-isolation.md)
- [アプリケーション制御](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)
- [デバイス コントロール](/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)
- [エクスプロイト保護](exploit-protection.md)
- [ネットワーク保護](network-protection.md) [、Web 保護](web-protection-overview.md)
- [制御されたフォルダー アクセス](controlled-folders.md)
- [ネットワーク ファイアウォール](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
- [攻撃面の減少ルール](attack-surface-reduction.md)

<a name="ngp"></a>

**[次世代の保護](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**<br>
ネットワークのセキュリティ境界をさらに強化するために、エンドポイント用の Microsoft Defender は、あらゆる種類の新しい脅威をキャッチするために設計された次世代の保護が使用されます。

- [動作の監視](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)
- [クラウドベースの保護](/windows/security/threat-protection/microsoft-defender-antivirus/configure-protection-features-microsoft-defender-antivirus)
- [機械学習](/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [URL 保護](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)
- [自動サンドボックス サービス](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

<a name="edr"></a>

**[エンドポイントでの検出と対応](overview-endpoint-detection-response.md)**<br>
エンドポイントの検出および応答機能は、侵入の試みとアクティブな侵害を検出、調査、および対応するために配置されます。 高度な検出機能を使用すると、クエリベースの脅威検出ツールを使用して、侵害を積極的に検出し、カスタム検出を作成できます。

- [アラート](alerts-queue.md)
- [エンドポイント データの履歴](investigate-machines.md#timeline)
- [応答オーケストレーション](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)
- [Forensic コレクション](respond-machine-alerts.md#collect-investigation-package-from-devices)
- [脅威インテリジェンス](threat-indicator-concepts.md)
- [高度なデトレーションと分析サービス](respond-file-alerts.md#deep-analysis)
- [高度な追求](advanced-hunting-overview.md)
    - [カスタム検出](overview-custom-detections.md)

<a name="ai"></a>

**[調査と修復の自動化](automated-investigations.md)**<br>
高度な攻撃への迅速な対応に加えて、Microsoft Defender for Endpoint は自動調査と修復機能を提供し、アラートの量を数分で削減できます。

- [調査と修復の自動化](automated-investigations.md)
- [自動調査の詳細と結果を表示する](auto-investigation-action-center.md)
- [修復アクションを表示および承認する](manage-auto-investigation.md)

<a name="mte"></a>

**[Microsoft 脅威エキスパート](microsoft-threat-experts.md)**<br>
Microsoft Defender for Endpoint の新しい管理された脅威検出サービスは、プロアクティブな狩猟、事前承認、追加のコンテキストと分析情報を提供します。 Microsoft 脅威エキスパートオペレーション センター (SOC) が脅威を迅速かつ正確に特定して対応する権限をさらに強化します。

- [標的型攻撃の通知](microsoft-threat-experts.md)
- [エキスパートオンデマンド](microsoft-threat-experts.md)
- [管理されたMicrosoft 365 Defenderサービスを構成する](configure-microsoft-threat-experts.md)

<a name="apis"></a>

**[一元的な構成と管理、API](management-apis.md)**<br>
Microsoft Defender for Endpoint を既存のワークフローに統合します。
- [オンボーディング](onboard-configure.md)
- [API と SIEM の統合](configure-siem.md)
- [公開された API](apis-intro.md)
- [役割ベースのアクセス制御 (RBAC)](rbac.md)
- [レポートと傾向](threat-protection-reports.md)

<a name="integration"></a>
**[Microsoft ソリューションとの統合](threat-protection-integration.md)** <br>
 Microsoft Defender for Endpoint は、以下を含むさまざまな Microsoft ソリューションと直接統合します。
- Intune
- Microsoft Defender for Office 365
- Microsoft Defender for Identity
- Microsoft Defender for Cloud
- Skype for Business
- Microsoft Defender for Cloud Apps

<a name="mtp"></a>
**[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-threat-protection)**<br>
 Microsoft 365 Defender では、Microsoft Defender for Endpoint とさまざまな Microsoft セキュリティ ソリューションが統合された侵害前および侵害後のエンタープライズ防御スイートを形成し、エンドポイント、ID、電子メール、アプリケーション間でネイティブに統合され、高度な攻撃を検出、防止、調査、および自動的に対応できます。
