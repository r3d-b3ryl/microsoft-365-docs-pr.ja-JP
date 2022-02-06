---
title: Microsoft Defender for Endpoint
description: Microsoft Defender for Endpoint は、継続的な高度な脅威にからの防御に役立つエンタープライズ エンドポイントセキュリティ プラットフォームです。
keywords: Microsoft Defender for Endpoint の概要、Microsoft Defender for Endpoint の概要、サイバーセキュリティ、継続的な高度な脅威、エンタープライズ セキュリティ、コンピューター動作センサー、クラウド セキュリティ、分析、脅威インテリジェンス、攻撃面の縮小、次世代の保護、調査と修復の自動化、Microsoft 脅威エキスパート、セキュア スコア、高度な捜索、Microsoft 365 Defender、サイバー脅威の捜索
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: high
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.custom: intro-overview
ms.topic: conceptual
ms.technology: mde
---

# <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

EndPoint 向け Microsoft Defender は、エンタープライズネットワークによる高度な脅威の防止、検出、調査、および応答を支援するために設計されたエンタープライズエンドポイントセキュリティプラットフォームです。

> [!TIP]
> まもなく、Microsoft Defender for Endpoint は 2 つのプランで利用できます。 この記事では、Microsoft Defender for Endpoint プラン 2 に含まれる機能について説明します。 [Microsoft Defender for Endpoint プラン 1 とプラン 2 についての詳細](defender-endpoint-plan-1-2.md)。
> 

<p><p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wDob]

EndPoint 向け Defender は、Windows 10 と Microsoft の堅牢なクラウドサービスに組み込まれているテクノロジの次の組み合わせを使用します。

- **エンドポイントの動作センサー**: Windows 10 に組み込まれており、これらのセンサーはオペレーティングシステムからの動作シグナルを収集して処理し、プライベートで分離された EndPoint 向け Microsoft Defender のクラウドインスタンスにこのセンサーデータを送信します。

- **クラウド セキュリティ分析**: ビッグデータ、機械学習、および Microsoft ならではの分析力を Windows のエコシステム、(Office 365 などの) エンタープライズ クラウド製品、およびオンライン アセット全体で活用し、動作シグナルを高度な脅威についての洞察、検出、推奨される対策に結びつけます。　　　　　

- **脅威インテリジェンス**: Microsoft hunters、セキュリティチーム、パートナーによって提供される脅威インテリジェンスによって強化された脅威インテリジェンスでは、EndPoint 向け Defender が攻撃者のツール、手法、および手順を特定し、収集されたセンサーデータで通知されたときにアラートを生成できるようにします。

<center><h2>Microsoft Defender for Endpoint</center></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="Threat & Vulnerability Management"> <br><b>脅威と脆弱性の管理</b></center></a></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="Attack surface reduction"><br><b>攻撃面の減少</b></center></a></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="Next-generation protection"><br> <b>次世代の保護</b></a></center></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="Endpoint detection and response"><br> <b>エンドポイントでの検出と対応</b></a></center></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="Automated investigation and remediation"><br> <b>調査と修復の自動化</b></a></center></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="Microsoft Threat Experts"><br> <b>Microsoft 脅威エキスパート</b></a></center></td>
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

<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vnC4?rel=0]

> [!TIP]
>
> - EndPoint 向け Microsoft Defender の最新機能の詳細については、「[EndPoint 向け Microsoft Defender の新機能](whats-new-in-microsoft-defender-endpoint.md)」を参照してください。
> - 最近の MITRE 評価において、Microsoft Defender for Endpoint の業界をリードする分析力と検出能力が示されました。詳しくは、「[MITRE ATT&CK ベース評価の分析](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)」を参照してください。

<a name="tvm"></a>

**[脅威と脆弱性の管理](next-gen-threat-and-vuln-mgt.md)**

この組み込み機能は、画期的なリスクベースのアプローチを使用してエンドポイントの脆弱性や構成ミスの検出、優先順位付け、および修復を行います。

<a name="asr"></a>

**[攻撃面の減少](overview-attack-surface-reduction.md)**

攻撃面の縮小は、防御の第一線をスタック内で提供する機能のセットです。 構成が正しく設定されていることを確認して悪用に対する修復テクニックを適用することにより、機能は攻撃と悪用に対抗します。 この機能のセットには[ネットワーク保護](network-protection.md)および [Web 保護](web-protection-overview.md)も含まれ、これらの保護により、悪意のある IP アドレス、ドメイン、URL へのアクセスが制御されます。

<a name="ngp"></a>

**[次世代の保護](next-generation-protection.md)**

ネットワークのセキュリティ境界をさらに強化するために、エンドポイント用の Microsoft Defender は、あらゆる種類の新しい脅威をキャッチするために設計された次世代の保護が使用されます。

<a name="edr"></a>

**[エンドポイントでの検出と対応](overview-endpoint-detection-response.md)**

エンドポイントの検出および応答機能は、最初の 2 つのセキュリティの防御を通過した可能性がある高度な脅威の検出、調査、対応を行えるように組み込まれています。 [高度な捜索](advanced-hunting-overview.md) ではクエリベースの脅威捜索ツールが提供され、これにより侵入を予防的に発見し、カスタム検出を作成することができます。

<a name="ai"></a>

**[調査と修復の自動化](automated-investigations.md)**

Microsoft Defender for Endpoint for Endpoint は、高度な攻撃にすぐに対応可能であると共に、スケールの分単位での通知の量を減らすのに役立つ自動調査と修復機能が提供されます。

<a name="ss"></a>

**[デバイスの Microsoft セキュア スコア](tvm-microsoft-secure-score-devices.md)**

EndPoint 向け Microsoft Defender にはエンタープライズ ネットワークのセキュリティ状態を動的に評価し、保護されているシステムを特定し、推奨されたアクションを実行する上で役立つMicrosoft セキュアスコアが含まれているため、これを使用して組織の全体的なセキュリティを改善することができます。

<a name="mte"></a>

**[Microsoft 脅威エキスパート](microsoft-threat-experts.md)**

EndPoint 向け Microsoft Defender のこの新しい管理対象脅威検出サービスでは、予防的な捜索、優先順位付け、および追加のコンテキストと分析が提供され、セキュリティ オペレーション センター (SOC) が脅威を素早く正確に特定し、それに対応できるよう、SOC の能力を強化します。

> [!IMPORTANT]
> 予防的な標的型攻撃通知を受け取ったり、エキスパート オンデマンドとの連携を行ったりするには、EndPoint 向け Microsoft Defender のお客様は Microsoft 脅威エキスパート管理対象脅威捜索サービスに申し込む必要があります。 エキスパート オンデマンドは、アドオン サービスです。 標的型攻撃通知は、Microsoft 脅威エキスパート管理対象脅威捜索サービスへの参加が承認されるともれなく提供されます。
>
> 登録がまだの場合でも、この特典を体験することを希望する場合は、**[設定]** \> **[全般]** \> **[高度な機能]** \> **[Microsoft 脅威エキスパート]** に移動し、お申し込みください。 承認されると、標的型攻撃通知の特典と 90 日間無料のエキスパート オンデマンドの試用版が提供されます。 エキスパート オンデマンドの正規のサブスクリプションを入手するには、お客様の Microsoft 担当者にお問い合わせください。

<a name="apis"></a>

**[一元的な構成と管理、API](management-apis.md)**

Microsoft Defender for Endpoint を既存のワークフローに統合します。

<a name="mtp"></a>

**[Microsoft ソリューションとの統合](threat-protection-integration.md)**

EndPoint 向け Microsoft Defender は、次のようなさまざまな Microsoft ソリューションと直接統合します。

- Microsoft Defender for Cloud
- Microsoft Sentinel
- Intune
- Microsoft Defender for Cloud Apps
- Microsoft Defender for Identity
- Microsoft Defender for Office
- Skype for Business

**[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)**

EndPoint 向け Microsoft Defender および各種の Microsoft セキュリティ ソリューションは、Microsoft 365 Defender とともに侵害前と侵害後の統合されたエンタープライズ防御スイートを形成し、高度な攻撃の検出、防止、調査、およびそれに対する自動対応を、エンドポイント、ID、メール、アプリケーション全体でネイティブに統合します。


## <a name="training-for-security-analysts"></a>セキュリティ アナリスト向けトレーニング

Microsoft Learn のこの学習パスを使用すると、Defender for Endpoint と、組織のエンドポイント (デバイスとシステム) 全体の脅威の防止、検出、調査、および対応にどのように役立つかを理解できます。

|トレーニング: |Microsoft 365 Defender を使用してサイバー攻撃を検出して対応する|
|---|---|
|![Microsoft 365 Defender トレーニング アイコン。](../../media/microsoft-365-defender/m365-defender-secure-organization.svg)|Defender for Endpoint は、脆弱性管理、エンドポイント保護、エンドポイント検出と応答、モバイル脅威防御、およびマネージドサービスを単一の統合プラットフォームで提供するエンドポイント セキュリティ ソリューションです。<p> 2 時間 25 分 - ラーニング パス - 9 モジュール|

> [!div class="nextstepaction"]
> [スタート>](/learn/paths/defender-endpoint-fundamentals/)
