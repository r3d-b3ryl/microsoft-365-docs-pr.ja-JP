---
title: Microsoft Defender for Endpoint
description: Microsoft Defender for Endpoint は、高度な永続的な脅威から防御するのに役立つエンタープライズ エンドポイント セキュリティ プラットフォームです。
keywords: Microsoft Defender for Endpoint の概要、Microsoft Defender for Endpoint の概要、サイバーセキュリティ、高度な永続的脅威、エンタープライズ セキュリティ、マシンの動作センサー、クラウド セキュリティ、分析、脅威インテリジェンス、攻撃表面の縮小、次世代保護、自動調査と修復、Microsoft 脅威の専門家、セキュリティ スコア、高度な検出、Microsoft 365 Defender、サイバー脅威の検出
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
ms.openlocfilehash: 3bab9d0248a2ed8e83807f3c38215e653cba26eb
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843556"
---
# <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> Windows 10 Enterprise エディションの機能の詳細については、「Windows 10 Enterprise[エディション」を参照してください](https://www.microsoft.com/WindowsForBusiness/buy)。

Microsoft Defender for Endpoint は、エンタープライズ ネットワークが高度な脅威を防止、検出、調査、および対応するために設計されたエンタープライズ エンドポイント セキュリティ プラットフォームです。
<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wDob]

Defender for Endpoint では、Microsoft の堅牢なクラウド サービスWindows 10組み込みのテクノロジの組み合わせを使用します。

-   エンドポイント **の** 動作センサー: Windows 10 に埋め込まれたこれらのセンサーは、オペレーティング システムから動作信号を収集および処理し、このセンサー データを Microsoft Defender for Endpoint のプライベートで分離されたクラウド インスタンスに送信します。


-   クラウド セキュリティ **分析:** Windows エコシステム、エンタープライズ クラウド製品 (Office 365 など)、オンライン資産全体で、ビッグ データ、デバイスラーニング、および独自の Microsoft 光ファイバーを活用することで、行動シグナルは高度な脅威に対する洞察、検出、推奨応答に変換されます。

-   **脅威インテリジェンス**: Microsoft のハンター、セキュリティ チームによって生成され、パートナーによって提供される脅威インテリジェンスによって強化された脅威インテリジェンスにより、Defender for Endpoint は攻撃者のツール、テクニック、手順を識別し、収集されたセンサー データで監視されるとアラートを生成できます。

<center><h2>エンドポイント用 Microsoft Defender</center></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="Threat & Vulnerability Management"> <br><b>脅威&の管理</b></center></a></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="Attack surface reduction"><br><b>攻撃表面の縮小</b></center></a></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="Next-generation protection"><br> <b>次世代の保護</b></a></center></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="Endpoint detection and response"><br> <b>エンドポイントの検出と応答</b></a></center></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="Automated investigation and remediation"><br> <b>自動調査と修復</b></a></center></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="Microsoft Threat Experts"><br> <b>Microsoft 脅威エキスパート</b></a></center></td>
</tr>
<tr>
<td colspan="7">
<a href="#apis"><center><b>一元的な構成と管理、API</a></b></center></td>
</tr>
<tr>
<td colspan="7"><a href="#mtp"><center><b>Microsoft 365Defender</a></center></b></td>
</tr>
</table>
<br>

<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vnC4?rel=0] 

> [!TIP]
> - 「Defender for Endpoint: What's new in [Microsoft Defender for Endpoint」の最新の機能強化について説明します](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/)。
> - Microsoft Defender for Endpoint は、最近の MITRE 評価で業界をリードする光学機能と検出機能を実証しました。 読み取り: [MITRE ATT および CK&評価からの分析情報](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)。

<a name="tvm"></a>

**[脅威&の管理](next-gen-threat-and-vuln-mgt.md)**<br>
この組み込み機能では、エンドポイントの脆弱性と誤った構成の検出、事前設定、修復に対して、ゲームを変えるリスクベースのアプローチを使用します。 

<a name="asr"></a>

**[攻撃面の減少](overview-attack-surface-reduction.md)**<br>
攻撃表面の縮小機能のセットは、スタック内の防御の最初の行を提供します。 構成設定が適切に設定され、悪用の軽減手法が適用されていることを確認することで、この機能は攻撃や悪用に抵抗します。 この一連の機能には、[](network-protection.md)悪意のある[](web-protection-overview.md)IP アドレス、ドメイン、URL へのアクセスを規制するネットワーク保護と Web 保護も含まれます。 

<a name="ngp"></a>

**[次世代の保護](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**<br>
Microsoft Defender for Endpoint は、ネットワークのセキュリティ境界をさらに強化するために、すべての種類の新しい脅威をキャッチするように設計された次世代の保護を使用します。

<a name="edr"></a>

**[エンドポイントでの検出と対応](overview-endpoint-detection-response.md)**<br>
エンドポイントの検出および対応機能は、最初の 2 つのセキュリティの柱を越えた高度な脅威を検出、調査、および対応するために用意されています。 [高度な検索](advanced-hunting-overview.md) では、クエリ ベースの脅威検出ツールを使用して、侵害を積極的に検出し、カスタム検出を作成できます。

<a name="ai"></a>

**[自動調査と修復](automated-investigations.md)**<br>
高度な攻撃に迅速に対応できると共に、Microsoft Defender for Endpoint は自動調査と修復機能を提供し、アラートの量を数分で削減できます。 

<a name="ss"></a>

**[デバイス向けの Microsoft セキュア スコア](tvm-microsoft-secure-score-devices.md)**<br>

Defender for Endpoint には、エンタープライズ ネットワークのセキュリティ状態を動的に評価し、保護されていないシステムを特定し、組織の全体的なセキュリティを向上させるために推奨されるアクションを実行するのに役立つ Microsoft Secure Score for Devices が含まれています。

<a name="mte"></a>

**[Microsoft 脅威エキスパート](microsoft-threat-experts.md)**<br>
Microsoft Defender for Endpoint の新しい管理された脅威検出サービスは、予防的な狩猟、事前設定、追加のコンテキストと分析情報を提供し、セキュリティ運用センター (SOC) が脅威を迅速かつ正確に特定して対応する権限をさらに強化します。

>[!IMPORTANT]
>Defender for Endpoint のお客様は、プロアクティブな標的型攻撃通知をMicrosoft 脅威エキスパート専門家とオンデマンドで共同作業を行う場合は、セキュリティ管理された脅威検出サービスに申請する必要があります。 オンデマンドのエキスパートは、アドオン サービスです。 ターゲット攻撃通知は、管理された脅威検出サービスに受け入Microsoft 脅威エキスパート常に含まれます。<p>
><p>まだ登録されていない場合で、その利点を体験する場合は、「一般高度<b></b>> <b></b>> <b></b>設定」Microsoft 脅威エキスパート> <b>を参照</b>してください。 一度受け入れられると、ターゲット攻撃通知のメリットを受け取り、90 日間の Experts on Demand の試用版を開始します。 Microsoft 担当者に問い合わせ、完全な Experts on Demand サブスクリプションを取得してください。

<a name="apis"></a>

**[一元的な構成と管理、API](management-apis.md)**<br>
Microsoft Defender for Endpoint を既存のワークフローに統合します。

<a name="mtp"></a>

**[Microsoft ソリューションとの統合](threat-protection-integration.md)** <br>
Defender for Endpoint は、以下を含むさまざまな Microsoft ソリューションと直接統合します。
- Azure Defender
- Azure Sentinel
- Intune
- Microsoft Cloud App Security
- Microsoft Defender for Identity
- Microsoft Defender for Office
- Skype for Business

**[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-threat-protection)**<br>
Microsoft 365 Defender を使用すると、Defender for Endpoint とさまざまな Microsoft セキュリティ ソリューションが統合された侵害前および侵害後のエンタープライズ防御スイートを形成し、エンドポイント、ID、電子メール、およびアプリケーション間でネイティブに統合され、高度な攻撃を検出、防止、調査、および自動的に対応します。


## <a name="related-topic"></a>関連トピック
[Microsoft Defender for Endpoint は、高度な脅威の検出に役立ちます](https://www.microsoft.com/itshowcase/microsoft-defender-atps-antivirus-capabilities-boost-malware-protection)
