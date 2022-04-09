---
title: Microsoft 365 Defenderの脅威分析のアナリスト レポート セクションを理解する
ms.reviewer: ''
description: 各脅威分析レポートのアナリスト レポート セクションについて説明します。 脅威、軽減策、検出、高度な捜索クエリなどの情報を提供する方法について説明します。
keywords: アナリスト レポート, 脅威分析, 検出, 高度な捜索クエリ, 軽減策,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 396be53e4c238a8de21082f025762a1a4243b57c
ms.sourcegitcommit: dd7e5b67ff4ae4e7f74490e437c1795933c74cc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2022
ms.locfileid: "64731144"
---
# <a name="understand-the-analyst-report-in-threat-analytics-in-microsoft-365-defender"></a>Microsoft 365 Defenderの脅威分析のアナリスト レポートを理解する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

[!INCLUDE [Prerelease](../includes/prerelease.md)]

各 [脅威分析レポート](threat-analytics.md) には、動的セクションと _、アナリスト レポート_ と呼ばれる包括的な記述されたセクションが含まれています。 このセクションにアクセスするには、追跡対象の脅威に関するレポートを開き、[ **アナリスト レポート** ] タブを選択します。

:::image type="content" source="../../media/threat-analytics/ta_analystreport_mtp.png" alt-text="脅威分析レポートのアナリスト レポート セクション" lightbox="../../media/threat-analytics/ta_analystreport_mtp.png":::

_脅威分析レポートのアナリスト レポート セクション_

## <a name="scan-the-analyst-report"></a>アナリスト レポートをスキャンする

アナリスト レポートの各セクションは、実用的な情報を提供するように設計されています。 レポートは異なりますが、ほとんどのレポートには、次の表で説明するセクションが含まれています。

| [レポート] セクション | 説明 |
|--|--|
| エグゼクティブサマリー | 脅威の概要 (初めて見たときなど)、その動機、注目すべきイベント、主要なターゲット、個別のツールと手法。 この情報を使用すると、業界、地理的な場所、ネットワークのコンテキストで脅威に優先順位を付ける方法をさらに評価できます。 |
| 分析 | 攻撃の詳細や、攻撃者が新しい手法や攻撃面をどのように利用するかなど、脅威に関する技術情報 |
| MITRE ATT&CK 手法が観察されました | 観察された手法が [MITRE ATT&CK 攻撃フレームワーク](https://attack.mitre.org/)にどのようにマップされるか |
| [軽減策](#apply-additional-mitigations) | 脅威の影響を停止または軽減できるおすすめ。 このセクションには、脅威分析レポートの一部として動的に追跡されない軽減策も含まれています。 |
| [検出の詳細](#understand-how-each-threat-can-be-detected) | 脅威に関連するアクティビティやコンポーネントを表示できる Microsoft セキュリティ ソリューションによって提供される特定の一般的な検出。 |
| [高度な追求](#find-subtle-threat-artifacts-using-advanced-hunting) | 可能性のある脅威アクティビティを事前に特定するための[高度なハンティング クエリ](advanced-hunting-overview.md)。 ほとんどのクエリは、検出を補完するために提供されます。特に、悪意のある可能性のあるコンポーネントや、悪意のあると動的に評価できなかった動作を特定するために提供されます。 |
| 関連情報 | レポートの作成中にアナリストによって参照される Microsoft およびサードパーティのパブリケーション。 脅威分析コンテンツは、Microsoft の研究者によって検証されたデータに基づいています。 公開されているサード パーティのソースからの情報は、そのように明確に識別されます。 |
| 変更ログ | レポートが発行された時刻と、レポートに大きな変更が加えられた時刻。 |

## <a name="apply-additional-mitigations"></a>追加の軽減策を適用する

脅威分析は、 [セキュリティ更新プログラムとセキュリティで保護された構成の状態を](threat-analytics.md#exposure-and-mitigations-review-list-of-mitigations-and-the-status-of-your-devices)動的に追跡します。 この情報は、[ **公開&軽減策** ] タブのグラフとテーブルとして使用できます。

これらの追跡された軽減策に加えて、アナリスト レポートでは、動的に監視 _されない_ 軽減策についても説明します。 動的に追跡されない重要な軽減策の例を次に示します。

- _.lnk_ 添付ファイルまたはその他の疑わしいファイルの種類を含むメールをブロックする
- ローカル管理者パスワードをランダム化する
- フィッシングメールやその他の脅威ベクトルについてエンド ユーザーを教育する
- 特定の[攻撃面の縮小ルール](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)を有効にする

**[公開&軽減策**] タブを使用して脅威に対するセキュリティ体制を評価できますが、これらの推奨事項を使用すると、セキュリティ体制を改善するための追加の手順を実行できます。 アナリスト レポートのすべての軽減策のガイダンスを注意深く読み、可能な限り適用してください。

## <a name="understand-how-each-threat-can-be-detected"></a>各脅威を検出する方法を理解する

アナリスト レポートでは、Microsoft Defender ウイルス対策および _エンドポイントでの検出と対応 (EDR_) 機能からの検出も提供されます。

### <a name="antivirus-detections"></a>ウイルス対策の検出

これらの検出は、[Microsoft Defender ウイルス対策](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)がオンになっているデバイスで使用できます。 これらの検出は、Microsoft Defender for Endpointにオンボードされたデバイスで発生すると、レポート内のグラフを明るくするアラートもトリガーされます。

>[!NOTE]
>アナリスト レポートには、追跡された脅威に固有のコンポーネントや動作に加えて、広範な脅威を識別できる **一般的な検出** も一覧表示されます。 これらの一般的な検出は、グラフには反映されません。

### <a name="endpoint-detection-and-response-edr-alerts"></a>エンドポイントの検出と応答 (EDR) アラート

EDRアラートは、[Microsoft Defender for Endpointにオンボードされたデバイスに対して](/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)発生します。 これらのアラートは、一般に、Microsoft Defender for Endpoint センサーやその他のエンドポイント機能 (ウイルス対策、ネットワーク保護、改ざん防止など) によって収集されたセキュリティ信号に依存し、強力な信号ソースとして機能します。

ウイルス対策の検出の一覧と同様に、一部のEDR アラートは、追跡された脅威に関連付けられていない可能性がある疑わしい動作に汎用的にフラグを設定するように設計されています。 このような場合、レポートはアラートを "汎用" として明確に識別し、レポート内のどのグラフにも影響を与えません。

### <a name="email-related-detections-and-mitigations"></a>電子メール関連の検出と軽減策

Microsoft Defender for Office 365からの電子メール関連の検出と軽減策は、Microsoft Defender for Endpointから既に利用可能なエンドポイント データに加えて、アナリスト レポートに含まれています。

メール試行の防止情報を使用すると、配信前に攻撃が効果的にブロックされたり、迷惑メール フォルダーに配信されたりした場合でも、組織がアナリスト レポートで取り組まれた脅威のターゲットであったかどうかについての分析情報が得られます。

## <a name="find-subtle-threat-artifacts-using-advanced-hunting"></a>高度な捜索を使用して、微妙な脅威アーティファクトを見つける

検出を使用すると、追跡された脅威を自動的に特定して停止できますが、多くの攻撃アクティビティは、追加の検査を必要とするわずかなトレースを残します。 一部の攻撃アクティビティは正常な動作を示すので、動的に検出すると、操作上のノイズや誤検知が発生する可能性があります。

[高度な捜索](advanced-hunting-overview.md)では、脅威アクティビティの微妙なインジケーターを見つけるのを簡単にするKusto 照会言語に基づくクエリ インターフェイスが提供されます。 また、コンテキスト情報を表示し、インジケーターが脅威に接続されているかどうかを確認することもできます。

アナリスト レポートの高度なハンティング クエリは、Microsoft アナリストによって審査され、 [高度なハンティング クエリ エディター](https://security.microsoft.com/advanced-hunting)で実行する準備が整いました。 クエリを使用して、今後の一致に対するアラートをトリガーする [カスタム検出ルール](custom-detection-rules.md) を作成することもできます。

>[!NOTE]
> 脅威分析は[、Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics)でも利用できます。 ただし、Microsoft Defender for OfficeとMicrosoft Defender for Endpointの間にはデータ統合がありません。

## <a name="related-topics"></a>関連項目

- [脅威の分析の概要](threat-analytics.md)
- [高度な捜索で脅威をプロアクティブに見つける](advanced-hunting-overview.md)
- [カスタム検出ルール](custom-detection-rules.md)
