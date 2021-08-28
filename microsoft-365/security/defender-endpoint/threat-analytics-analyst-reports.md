---
title: 脅威分析のアナリスト レポート セクションについて説明します。
ms.reviewer: ''
description: 脅威分析レポートのレポート セクションでは、脅威、軽減、検出、高度な検索クエリなどの情報を提供する方法について説明します。
keywords: アナリスト レポート、脅威分析、検出、高度な検索クエリ、軽減策、
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3de298100e5a66e53bd34e110c35749e15e58044
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58568602"
---
# <a name="the-analyst-report-in-threat-analytics"></a>脅威分析のアナリスト レポート

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

各 [脅威分析レポートには、](threat-analytics.md) 動的セクションと、アナリスト レポートと呼ばれる包括的な記述セクション _が含まれます_。 このセクションにアクセスするには、追跡された脅威に関するレポートを開き、[アナリスト レポート] タブ **を選択** します。

![脅威分析レポートのアナリスト レポート セクションのイメージ。](images/ta-analyst-report-small.png)

_脅威分析レポートのアナリスト レポート セクション_

## <a name="scan-the-analyst-report"></a>アナリスト レポートをスキャンする

アナリスト レポートの各セクションは、アクション可能な情報を提供するように設計されています。 レポートはさまざまですが、ほとんどのレポートには、次の表に示すセクションが含まれます。

<br>

****

|[レポート] セクション|説明|
|---|---|
|エグゼクティブの概要|脅威の概要 (最初に見られた場合を含む)、その動機、重要なイベント、主要なターゲット、および個別のツールとテクニック。 この情報を使用して、業界、地理的位置、ネットワークのコンテキストで脅威に優先順位を付ける方法をさらに評価できます。|
|分析|攻撃の詳細、攻撃者が新しい手法または攻撃表面を利用する方法など、脅威に関する技術情報|
|MITRE ATT&CK 技術の観察|CK 攻撃フレームワークの[MITRE ATT](https://attack.mitre.org/)に&方法|
|[緩和策](#apply-additional-mitigations)|脅威の影響を停止または軽減する可能性がある推奨事項。 このセクションには、脅威分析レポートの一部として動的に追跡されない軽減策も含まれています。|
|[検出の詳細](#understand-how-each-threat-can-be-detected)|脅威に関連付けられたアクティビティやコンポーネントを表面化できる Microsoft セキュリティ ソリューションによって提供される特定の一般的な検出。|
|[高度な追求](#find-subtle-threat-artifacts-using-advanced-hunting)|[脅威の可能性のあるアクティビティ](advanced-hunting-overview.md) を事前に特定するための高度な検索クエリ。 ほとんどのクエリは、特に悪意のある可能性のあるコンポーネントや、悪意のあると動的に評価できなかった動作を見つけ出す場合に、検出を補完するために提供されます。|
|関連情報|レポートの作成中にアナリストが参照する Microsoft およびサードパーティの文書。 脅威分析コンテンツは、Microsoft の研究者によって検証されたデータに基づいて行います。 一般に公開されているサードパーティのソースからの情報は、その情報として明確に識別されます。|
|変更ログ|レポートが発行された時刻と、レポートに大幅な変更が加えた時刻。|
|

## <a name="apply-additional-mitigations"></a>追加の軽減策を適用する

脅威分析は、セキュリティ更新プログラムと [セキュリティで保護された構成の状態を動的に追跡します](threat-analytics.md#mitigations-review-list-of-mitigations-and-the-status-of-your-devices)。 この情報は、[軽減策] タブのグラフと表 **として使用** できます。

これらの追跡された軽減策に加えて、アナリスト レポートでは、動的に監視されない軽減 _策も説明_ します。 動的に追跡されない重要な軽減策の例を次に示します。

- .lnk 添付ファイルまたは _他の疑わしい_ ファイルの種類を含むメールをブロックする
- ローカル管理者パスワードをランダム化する
- フィッシングメールや他の脅威ベクトルについてエンド ユーザーに教育する
- 特定の攻撃表面 [の縮小ルールを有効にする](attack-surface-reduction.md)

[軽減策] タブ **を使用** して脅威に対するセキュリティの態勢を評価することもできますが、これらの推奨事項を使用すると、セキュリティ態勢の改善に向けて追加の手順を実行できます。 アナリスト レポートのすべての軽減ガイダンスを注意深く読み、可能な限り適用します。

## <a name="understand-how-each-threat-can-be-detected"></a>各脅威の検出方法を理解する

アナリスト レポートには、Microsoft Defender for Endpoint ウイルス対策機能とエンドポイント検出および応答 (EDR) 機能も提供されます。

### <a name="antivirus-detections"></a>ウイルス対策の検出

これらの検出は、デバイスで有効になっているデバイス[Microsoft Defender ウイルス対策](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)使用できます。 これらの検出が Microsoft Defender for Endpoint にオンボードされているデバイスで発生すると、レポート内のグラフを点灯するアラートもトリガーされます。

> [!NOTE]
> アナリスト レポートには、 **追跡される** 脅威に固有のコンポーネントや動作に加えて、広範囲の脅威を識別できる一般的な検出も一覧表示されます。 これらの一般的な検出は、グラフには反映されません。

### <a name="endpoint-detection-and-response-edr-alerts"></a>エンドポイントの検出と応答 (EDR) アラート

EDRは、Microsoft Defender for Endpoint にオンボードされている[デバイスに対して発生します](onboard-configure.md)。 これらのアラートは、通常、Microsoft Defender for Endpoint センサーによって収集されるセキュリティ信号と、強力な信号ソースとして機能する他のエンドポイント機能 (ウイルス対策、ネットワーク保護、改ざん防止など) に依存します。

ウイルス対策の検出の一覧と同様EDR一部のアラートは、追跡された脅威に関連付けされない疑わしい動作に一般的にフラグを設定するように設計されています。 このような場合、レポートはアラートを "汎用" として明確に識別し、レポート内のグラフには影響を与えかねない。

## <a name="find-subtle-threat-artifacts-using-advanced-hunting"></a>高度な検索を使用して、微妙な脅威のアーティファクトを検索する

検出では追跡された脅威を自動的に特定して停止することができますが、多くの攻撃アクティビティでは、追加の検査が必要な微妙な痕跡が残っています。 攻撃アクティビティの中には、通常の動作を示すものがあります。そのため、動的に検出すると、運用上のノイズや誤検知が発生する可能性があります。

[高度な検索](advanced-hunting-overview.md) は、Kusto クエリ言語に基づくクエリ インターフェイスを提供し、脅威アクティビティの微妙なインジケーターの検索を簡略化します。 また、コンテキスト情報を表示し、インジケーターが脅威に接続されているかどうかを確認できます。

アナリスト レポートの高度な検索クエリは、Microsoft アナリストによって確認され、高度な検索クエリ エディターで実行 [する準備が整いました](https://securitycenter.windows.com/advanced-hunting)。 クエリを使用して、将来の一致に関するアラート [をトリガー](custom-detection-rules.md) するカスタム検出ルールを作成することもできます。

## <a name="related-topics"></a>関連項目

- [脅威の分析の概要](threat-analytics.md)
- [高度な検索で脅威を事前に検出する](advanced-hunting-overview.md)
- [カスタム検出ルール](custom-detection-rules.md)
- 