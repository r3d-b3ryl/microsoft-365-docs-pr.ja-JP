---
title: 脅威分析のアナリスト レポート セクションを理解する
ms.reviewer: ''
description: 各脅威分析レポートのアナリスト レポート セクションについて説明します。 脅威、軽減策、検出、高度なハンティング クエリなどの情報を提供する方法について説明します。
keywords: アナリスト レポート, 脅威分析, 検出, 高度な検索クエリ, 軽減策,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 650282e0dce49cc392eeb7501f91b3ffed9f0707
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167559"
---
# <a name="understand-the-analyst-report-in-threat-analytics"></a>脅威分析のアナリスト レポートを理解する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

> Microsoft 365 Defender を体験したい場合 ラボ環境 [で評価したり、](https://aka.ms/mtp-trial-lab) パイロット プロジェクトを実 [稼働環境で実行することができます](https://aka.ms/m365d-pilotplaybook)。
>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

各 [脅威分析レポートには、](threat-analytics.md) 動的セクションと、アナリスト レポートと呼ばれる包括的な記述されたセクション _が含まれます_。 このセクションにアクセスするには、脅威の追跡に関するレポートを開き、[アナリスト] レポート タブ **を選択** します。

![脅威分析レポートのアナリスト レポート セクションの画像](../../media/threat-analytics/ta_analystreport_mtp.png)

_脅威分析レポートのアナリスト レポート セクション_

## <a name="scan-the-analyst-report"></a>アナリスト レポートをスキャンする 
アナリスト レポートの各セクションは、操作可能な情報を提供するように設計されています。 レポートは異なりますが、ほとんどのレポートには次の表で説明するセクションが含まれます。

| [レポート] セクション | 説明 |
|--|--|
| 概要 | 脅威の概要。最初に確認された時、その動機、重要なイベント、主要なターゲット、および個別のツールと手法を含む。 この情報を使用して、業界、地理的な場所、ネットワークのコンテキストで脅威に優先順位を付ける方法をさらに評価できます。 |
| 分析 | 攻撃の詳細や、攻撃者が新しい手法や攻撃面を利用する方法など、脅威に関する技術情報 | 
| MITRE ATT&CK の手法の観察 | 観察された手法が [MITRE ATT と CK 攻撃フレームワーク&マップする方法](https://attack.mitre.org/) | 
| [軽減策](#apply-additional-mitigations) | 脅威の影響を停止または軽減できる推奨事項。 このセクションには、脅威分析レポートの一部として動的に追跡されない軽減策も含まれています。 |
| [検出の詳細](#understand-how-each-threat-can-be-detected) | 脅威に関連するアクティビティやコンポーネントを表面化できる Microsoft セキュリティ ソリューションによって提供される特定の一般的な検出。 | 
| [高度な検出](#find-subtle-threat-artifacts-using-advanced-hunting) | [可能性のある脅威アクティビティを](advanced-hunting-overview.md) 事前に識別するための高度な検索クエリ。 ほとんどのクエリは、特に悪意のある可能性のあるコンポーネントや、悪意のあると動的に評価できなかった動作を見つけ出す場合に、検出を補完するために提供されます。 | 
| 関連情報 | レポートの作成時にアナリストによって参照される Microsoft およびサード パーティの文書。 脅威分析のコンテンツは、Microsoft のリサーチ ツールによって検証されたデータに基づいて作成されます。 公開されているサード パーティソースからの情報は、その情報として明確に識別されます。 | 
| 変更ログ | レポートが発行された時刻と、レポートが大幅に変更された時刻。 |

## <a name="apply-additional-mitigations"></a>追加の軽減策を適用する
脅威分析は、セキュリティ更新プログラム [とセキュリティで保護された構成の状態を動的に追跡します](threat-analytics.md#mitigations-review-list-of-mitigations-and-the-status-of-your-devices)。 この情報は、[軽減策] タブのグラフと表 **として利用** できます。

これらの追跡された軽減策に加えて、アナリスト レポートでは、動的に監視されない軽減 _策も_ 説明します。 動的に追跡されない重要な軽減策の例を次に示します。

- .lnk 添付ファイルまたは _他の疑_ わしいファイルの種類を含むメールをブロックする
- ローカル管理者パスワードをランダム化する
- フィッシング メールや他の脅威ベクトルについてエンド ユーザーに教育する
- 特定の攻撃 [表面の縮小ルールを有効にする](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)

[軽減策]タブを使用して脅威に対するセキュリティの状態を評価することができますが、これらの推奨事項を使用すると、セキュリティの状態を改善するための追加の手順を実行できます。 アナリスト レポートのすべての軽減策ガイダンスを注意深く読み、可能な限り適用してください。

## <a name="understand-how-each-threat-can-be-detected"></a>各脅威を検出する方法を理解する
アナリスト レポートでは、Microsoft Defender for Endpoint ウイルス対策およびエンドポイント検出と応答 (EDR) 機能の検出も提供します。

### <a name="antivirus-detections"></a>ウイルス対策の検出
これらの検出は、Microsoft Defender ウイルス対策が有効 [になっているデバイスで](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) 利用できます。 これらの検出が Microsoft Defender for Endpoint にオンボードされているデバイスで発生すると、レポート内のグラフを明るくするアラートもトリガーされます。

>[!NOTE]
>アナリスト レポートには、追跡された脅威に固有のコンポーネントや動作に加えて、広範な脅威を識別できる一般的な検出も一覧表示されます。 これらの一般的な検出は、グラフには反映されません。

### <a name="endpoint-detection-and-response-edr-alerts"></a>エンドポイントの検出と応答 (EDR) のアラート
EDR アラートは、Microsoft Defender for Endpoint にオンボードされた [デバイスに対して発生します](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)。 これらのアラートは、通常、Microsoft Defender for Endpoint センサーによって収集されたセキュリティ信号と、強力な信号ソースとして機能するウイルス対策、ネットワーク保護、改ざん防止などの他のエンドポイント機能に依存します。

ウイルス検出の一覧と同様に、一部の EDR アラートは、追跡された脅威に関連付けされていない疑わしい動作に汎用的にフラグを設定するように設計されています。 このような場合、レポートはアラートを "汎用" として明確に識別し、レポート内のグラフには影響を与えなくします。

### <a name="email-related-detections-and-mitigations"></a>メール関連の検出と軽減策
Office 365 用 Microsoft Defender からのメール関連の検出と軽減策は、Microsoft Defender for Endpoint から既に利用できるエンドポイント データに加えて、アナリストのレポートに含まれています。 

メール試行の防止情報は、配信前に攻撃が効果的にブロックされた場合や迷惑メール フォルダーに配信された場合でも、組織がアナリスト のレポートに取り組む脅威の対象だったかどうかに関する分析情報を提供します。

## <a name="find-subtle-threat-artifacts-using-advanced-hunting"></a>高度な検索を使用して、微妙な脅威のアーティファクトを見つける
検出によって追跡された脅威を自動的に特定して停止することができますが、多くの攻撃アクティビティでは追加の検査が必要な微妙な追跡が残されています。 一部の攻撃アクティビティでは、通常の動作も示す可能性があります。そのため、動的に検出すると、操作ノイズや誤検知が発生する可能性があります。

[高度な検索](advanced-hunting-overview.md) は、Kusto クエリ言語に基づくクエリ インターフェイスを提供し、脅威アクティビティの微妙なインジケーターの検索を簡素化します。 また、コンテキスト情報を表示し、インジケーターが脅威に接続されているかどうかを確認できます。

アナリスト レポートの高度な検索クエリは、Microsoft アナリストによって確認され、高度な検索クエリ エディターで実行できる [状態です](https://security.microsoft.com/advanced-hunting)。 また、クエリを使用して、今後の一致に [関](custom-detection-rules.md) するアラートをトリガーするカスタム検出ルールを作成することもできます。


>[!NOTE]
> 脅威分析は [、Microsoft Defender for Endpoint でも利用できます](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics)。 ただし、Microsoft 365 Defender Threat 分析が持つ Office 用 Microsoft Defender とエンドポイント用 Microsoft Defender の間のデータ統合はありません。


## <a name="related-topics"></a>関連項目
- [脅威分析の概要](threat-analytics.md)
- [高度な検索を使用して脅威を事前に検出する](advanced-hunting-overview.md) 
- [カスタム検出ルール](custom-detection-rules.md)
