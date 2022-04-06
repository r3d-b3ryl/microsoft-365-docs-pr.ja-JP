---
title: '[脅威分析] の [アナリスト レポート] セクションをMicrosoft 365 Defender'
ms.reviewer: ''
description: 各脅威分析レポートのアナリスト レポート セクションについて説明します。 脅威、軽減策、検出、高度な検索クエリなどの情報を提供する方法を理解します。
keywords: アナリスト レポート、脅威分析、検出、高度な検索クエリ、軽減策、
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
ms.openlocfilehash: 68d6c0bed1f9484f4eed45924c57357b1c490e8f
ms.sourcegitcommit: a4729532278de62f80f2160825d446f6ecd36995
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2022
ms.locfileid: "64569380"
---
# <a name="understand-the-analyst-report-in-threat-analytics-in-microsoft-365-defender"></a>脅威分析のアナリスト レポートをMicrosoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

> Microsoft 365 Defender を体験しますか? [ラボ環境で評価](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)、または[運用でパイロット プロジェクトを実行](m365d-pilot.md?ocid=cx-evalpilot)することができます。
>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

各 [脅威分析レポートには、](threat-analytics.md) 動的セクションと、アナリスト レポートと呼ばれる包括的な記述セクション _が含まれます_。 このセクションにアクセスするには、追跡された脅威に関するレポートを開き、[アナリスト レポート] タブ **を選択** します。

:::image type="content" source="../../media/threat-analytics/ta_analystreport_mtp.png" alt-text="脅威分析レポートのアナリスト レポート セクション" lightbox="../../media/threat-analytics/ta_analystreport_mtp.png":::

_脅威分析レポートのアナリスト レポート セクション_

## <a name="scan-the-analyst-report"></a>アナリスト レポートをスキャンする

アナリスト レポートの各セクションは、アクション可能な情報を提供するように設計されています。 レポートはさまざまですが、ほとんどのレポートには、次の表に示すセクションが含まれます。

| [レポート] セクション | 説明 |
|--|--|
| エグゼクティブの概要 | 脅威の概要 (最初に見られた場合を含む)、その動機、重要なイベント、主要なターゲット、および個別のツールとテクニック。 この情報を使用して、業界、地理的位置、ネットワークのコンテキストで脅威に優先順位を付ける方法をさらに評価できます。 |
| 分析 | 攻撃の詳細、攻撃者が新しい手法または攻撃表面を利用する方法など、脅威に関する技術情報 |
| MITRE ATT&CK 技術の観察 | CK 攻撃フレームワークの [MITRE ATT](https://attack.mitre.org/) に&方法 |
| [軽減策](#apply-additional-mitigations) | おすすめの影響を停止または軽減できるデータ。 このセクションには、脅威分析レポートの一部として動的に追跡されない軽減策も含まれています。 |
| [検出の詳細](#understand-how-each-threat-can-be-detected) | 脅威に関連付けられたアクティビティやコンポーネントを表面化できる Microsoft セキュリティ ソリューションによって提供される特定の一般的な検出。 |
| [高度な追求](#find-subtle-threat-artifacts-using-advanced-hunting) | [脅威の可能性のあるアクティビティ](advanced-hunting-overview.md) を事前に特定するための高度な検索クエリ。 ほとんどのクエリは、特に悪意のある可能性のあるコンポーネントや、悪意のあると動的に評価できなかった動作を見つけ出す場合に、検出を補完するために提供されます。 |
| 関連情報 | レポートの作成中にアナリストが参照する Microsoft およびサードパーティの文書。 脅威分析コンテンツは、Microsoft の研究者によって検証されたデータに基づいて行います。 一般に公開されているサードパーティのソースからの情報は、その情報として明確に識別されます。 |
| 変更ログ | レポートが発行された時刻と、レポートに大幅な変更が加えた時刻。 |

## <a name="apply-additional-mitigations"></a>追加の軽減策を適用する

脅威分析は、セキュリティ更新プログラム [とセキュリティで保護された構成の状態を動的に追跡します](threat-analytics.md#exposure-and-mitigations-review-list-of-mitigations-and-the-status-of-your-devices)。 この情報は、[露出の軽減策] タブの& **表として使用** できます。

これらの追跡された軽減策に加えて、アナリスト レポートでは、動的に監視されない軽減 _策も説明_ します。 動的に追跡されない重要な軽減策の例を次に示します。

- _.lnk 添付ファイルまたは他の疑わしい_ ファイルの種類を含むメールをブロックする
- ローカル管理者パスワードをランダム化する
- フィッシングメールや他の脅威ベクトルについてエンド ユーザーに教育する
- 特定の攻撃表面 [の縮小ルールを有効にする](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)

[露出の軽減策] タブ **&** 使用して、脅威に対するセキュリティの態勢を評価することができますが、これらの推奨事項を使用すると、セキュリティ態勢の改善に向けて追加の手順を実行できます。 アナリスト レポートのすべての軽減ガイダンスを注意深く読み、可能な限り適用します。

## <a name="understand-how-each-threat-can-be-detected"></a>各脅威の検出方法を理解する

アナリスト レポートには、分析機能と (_Microsoft Defender ウイルス対策) 機能_ エンドポイントでの検出と対応検出EDR提供されます。

### <a name="antivirus-detections"></a>ウイルス対策の検出

これらの検出は、デバイスで有効になっているデバイス[Microsoft Defender ウイルス対策](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)使用できます。 これらの検出が、Microsoft Defender for Endpointにオンボードされているデバイスで発生すると、レポート内のグラフが点灯するアラートもトリガーされます。

>[!NOTE]
>アナリスト レポートには **、追跡される** 脅威に固有のコンポーネントや動作に加えて、広範囲の脅威を識別できる一般的な検出も一覧表示されます。 これらの一般的な検出は、グラフには反映されません。

### <a name="endpoint-detection-and-response-edr-alerts"></a>エンドポイントの検出と応答 (EDR) アラート

EDRにオンボードされているデバイスに対して[、](/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)Microsoft Defender for Endpoint。 これらのアラートは通常、Microsoft Defender for Endpoint センサーによって収集されたセキュリティ信号と、強力な信号源として機能するウイルス対策、ネットワーク保護、改ざん防止などの他のエンドポイント機能に依存します。

ウイルス対策の検出の一覧と同様EDR一部のアラートは、追跡された脅威に関連付けされない疑わしい動作に一般的にフラグを設定するように設計されています。 このような場合、レポートはアラートを "汎用" として明確に識別し、レポート内のグラフには影響を与えかねない。

### <a name="email-related-detections-and-mitigations"></a>電子メール関連の検出と軽減策

電子メール関連の検出と、Microsoft Defender for Office 365からの軽減策は、アナリスト レポートに含まれています。また、Microsoft Defender for Endpoint から既に使用できるエンドポイント データも含Microsoft Defender for Endpoint。

メールの試行を防止する情報は、配信前に攻撃が効果的にブロックされた場合や迷惑メール フォルダーに配信された場合でも、アナリスト レポートで取り組む脅威の対象として組織が実行されたかどうかに関する分析情報を提供します。

## <a name="find-subtle-threat-artifacts-using-advanced-hunting"></a>高度な検索を使用して、微妙な脅威のアーティファクトを検索する

検出では追跡された脅威を自動的に特定して停止することができますが、多くの攻撃アクティビティでは、追加の検査が必要な微妙な痕跡が残っています。 攻撃アクティビティの中には、通常の動作を示すものがあります。そのため、動的に検出すると、運用上のノイズや誤検知が発生する可能性があります。

[高度な検出](advanced-hunting-overview.md)は、脅威アクティビティの微妙なインジケーター Kusto 照会言語を簡単に見つけ出すクエリ インターフェイスを提供します。 また、コンテキスト情報を表示し、インジケーターが脅威に接続されているかどうかを確認できます。

アナリスト レポートの高度な検索クエリは、Microsoft アナリストによって確認され、高度な検索クエリ エディターで実行 [する準備が整いました](https://security.microsoft.com/advanced-hunting)。 クエリを使用して、将来の一致に関するアラート [をトリガー](custom-detection-rules.md) するカスタム検出ルールを作成することもできます。

>[!NOTE]
> 脅威分析は、Microsoft Defender for Endpoint [でも利用できます](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics)。 ただし、Microsoft Defender 間のデータ統合は行なOfficeとMicrosoft Defender for Endpoint。

## <a name="related-topics"></a>関連項目

- [脅威の分析の概要](threat-analytics.md)
- [高度な検索で脅威を事前に検出する](advanced-hunting-overview.md)
- [カスタム検出ルール](custom-detection-rules.md)
