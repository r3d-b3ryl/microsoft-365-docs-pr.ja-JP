---
title: Microsoft Defender for Endpoint脅威分析を使用して、新たな脅威を追跡して対応する
ms.reviewer: ''
description: 新たに発生する脅威と攻撃の手法と、それらを阻止する方法について理解します。 組織への影響を評価し、組織の回復性を評価します。
keywords: 脅威分析、リスク評価、OS 軽減策、マイクロコード軽減策、軽減状態
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 455b80f590edf255362c7bb047c7aa1b23916666
ms.sourcegitcommit: fdd0294e6cda916392ee66f5a1d2a235fb7272f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2022
ms.locfileid: "65128568"
---
# <a name="track-and-respond-to-emerging-threats-through-threat-analytics"></a>脅威分析を通じて、新たな脅威を追跡し、対応する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

より高度な敵対者と新しい脅威が頻繁かつ一般的に出現する中で、次のことが迅速に可能になることが重要です。

- 新しい脅威の影響を評価する
- 脅威に対する回復性または脅威にさらされる回復性を確認する
- 脅威を停止または含めるために実行できるアクションを特定する

脅威分析は、次のような最も関連性の高い脅威をカバーする、Microsoft の専門家のセキュリティ研究者からの一連のレポートです。

- アクティブな脅威アクターとそのキャンペーン
- 一般的な攻撃手法と新しい攻撃手法
- 重大な脆弱性
- 一般的な攻撃対象領域
- 流行しているマルウェア

各レポートには、脅威の詳細な分析と、その脅威から防御する方法に関する広範なガイダンスが提供されます。 また、ネットワークからのデータも組み込まれており、脅威がアクティブかどうか、および適切な保護が適用されているかどうかを示します。

脅威分析が最新の脅威を追跡して停止する方法の詳細については、この短いビデオをご覧ください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bw1f]

## <a name="required-roles-and-permissions"></a>必要な役割と権限
次の表に、Threat Analytics にアクセスするために必要なロールとアクセス許可の概要を示します。 次の表で定義されているロールは、個々のポータルのカスタム ロールを参照し、同様に名前が付けられている場合でも、Azure ADのグローバル ロールには接続されません。

| **Microsoft 365 Defenderには、次のいずれかのロールが必要です。**  | **Defender for Endpoint には、次のいずれかのロールが必要です**  | **Defender for Office 365には、次のいずれかのロールが必要です。** | **Defender for Cloud アプリには、次のいずれかのロールが必要です** | 
|---------|---------|---------|---------|
| 脅威の分析 | アラートとインシデント データ: <ul><li>データの表示 - セキュリティ操作</li></ul>TVM の軽減策:<ul><li>データの表示 - 脅威と脆弱性の管理</li></ul> | アラートとインシデント データ:<ul> <li>アラートを表示専用で管理する</li> <li>アラートの管理</li> <li>組織の構成</li><li>監査ログ</li> <li>表示専用の監査ログ</li><li>セキュリティ閲覧者</li> <li>セキュリティ管理者</li><li>表示専用の受信者</li> </ul> 禁止された電子メールの試行: <ul><li>セキュリティ閲覧者</li> <li>セキュリティ管理者</li><li>表示専用の受信者</li> | Defender for Cloud アプリまたは MDI ユーザーには使用できません |

## <a name="view-the-threat-analytics-dashboard"></a>脅威分析ダッシュボードを表示する

脅威分析ダッシュボードは、組織に最も関連するレポートにアクセスするための優れた出発点です。 次のセクションの脅威の概要を示します。

- **最新の脅威**: 最近公開された脅威レポートと、アクティブなアラートと解決済みのアラートを含むデバイスの数を一覧表示します。
- **影響の大きい脅威**: 組織に最も大きな影響を与えた脅威を一覧表示します。 このセクションでは、アクティブなアラートを持つデバイスの数によって脅威をランク付けします。
- **脅威の概要**: アクティブなアラートと解決されたアラートで脅威の数を表示することで、追跡された脅威の全体的な影響を示します。

ダッシュボードから脅威を選択して、その脅威のレポートを表示します。

:::image type="content" source="images/ta_dashboard.png" alt-text="脅威分析ダッシュボード" lightbox="images/ta_dashboard.png":::

## <a name="view-a-threat-analytics-report"></a>脅威分析レポートを表示する

各脅威分析レポートには、 **概要**、 **アナリスト レポート**、 **軽減策** の 3 つのセクションに関する情報が用意されています。

### <a name="overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses"></a>概要: 脅威をすばやく理解し、その影響を評価し、防御を確認する

[ **概要]** セクションには、詳細なアナリスト レポートのプレビューが表示されます。 また、組織に対する脅威の影響と、不適切な構成とパッチが適用されていないデバイスによる露出を強調するグラフも提供されます。

:::image type="content" source="images/ta-overview.png" alt-text="脅威分析レポートの [概要] セクション" lightbox="images/ta-overview.png":::
_脅威分析レポートの [概要] セクション_

#### <a name="assess-the-impact-to-your-organization"></a>組織への影響を評価する

各レポートには、脅威の組織の影響に関する情報を提供するように設計されたグラフが含まれています。

- **アラートを含むデバイス**: 脅威の影響を受けた個別のデバイスの現在の数を示します。 その脅威に関連付けられているアラートが少なくとも 1 つある場合、デバイスは **アクティブ** として分類され、デバイス上 *の* 脅威に関連付けられているすべてのアラートが解決 **された場合は** 解決されます。
- **時間の経過に伴うアラートを含む** デバイス: 時間の経過と共に **アクティブ** なアラートと **解決済みの** アラートを持つ個別のデバイスの数を示します。 解決されたアラートの数は、組織が脅威に関連付けられたアラートにどれだけ迅速に対応するかを示します。 理想的には、グラフに数日以内に解決されたアラートが表示されている必要があります。

#### <a name="review-security-resilience-and-posture"></a>セキュリティの回復性と体制を確認する

各レポートには、特定の脅威に対する組織の回復性の概要を示すグラフが含まれています。

- **セキュリティ構成の状態**: 脅威の軽減に役立つ推奨されるセキュリティ設定を適用したデバイスの数を示します。 デバイスは、追跡 _されたすべての_ 設定を適用した場合、**セキュリティで保護** されたと見なされます。
- **脆弱性の修正プログラムの状態**: 脅威によって悪用された脆弱性に対処するセキュリティ更新プログラムまたは修正プログラムを適用したデバイスの数を示します。

### <a name="analyst-report-get-expert-insight-from-microsoft-security-researchers"></a>アナリスト レポート: Microsoft セキュリティ研究者から専門家の分析情報を取得する

**アナリスト レポート** セクションに移動して、詳細なエキスパートの書き込みを確認します。 ほとんどのレポートでは、MITRE ATT&CK フレームワークにマップされた戦術と手法、推奨事項の網羅リスト、強力な [脅威ハンティング](advanced-hunting-overview.md) ガイダンスなど、攻撃チェーンの詳細な説明が提供されます。

[アナリスト レポートの詳細を確認する](threat-analytics-analyst-reports.md)

### <a name="mitigations-review-list-of-mitigations-and-the-status-of-your-devices"></a>軽減策: 軽減策の一覧とデバイスの状態を確認する

[ **軽減策** ] セクションで、脅威に対する組織の回復性を高めるのに役立つ具体的な実用的な推奨事項の一覧を確認します。 追跡対象の軽減策の一覧には、次のものが含まれます。

- **セキュリティ更新プログラム**: セキュリティ更新プログラムまたは脆弱性の修正プログラムの展開
- **Microsoft Defender ウイルス対策設定**
  - セキュリティ インテリジェンスのバージョン
  - クラウドによる保護
  - 望ましくない可能性があるアプリケーション (PUA) 保護
  - リアルタイム保護

このセクションの軽減策情報には[、脅威と脆弱性の管理](next-gen-threat-and-vuln-mgt.md)からのデータが組み込まれています。また、レポートのさまざまなリンクから詳細なドリルダウン情報も提供されます。

:::image type="content" source="images/ta-mitigations.png" alt-text="脅威分析レポートの [軽減策] セクション" lightbox="images/ta-mitigations.png":::


_脅威分析レポートの [軽減策] セクション_

## <a name="additional-report-details-and-limitations"></a>その他のレポートの詳細と制限事項

レポートを使用する場合は、次の点に注意してください。

- データのスコープは、ロールベースのアクセス制御 (RBAC) スコープに基づいています。 [アクセスできるグループ](machine-groups.md)内のデバイスの状態が表示されます。
- グラフには、追跡される軽減策のみが反映されます。 グラフに表示されないその他の軽減策については、レポートの概要を確認してください。
- 軽減策では、完全な回復性は保証されません。 提供される軽減策は、回復性を向上させるために必要な最善のアクションを反映しています。
- デバイスがサービスにデータを送信していない場合、デバイスは "利用不可" としてカウントされます。
- ウイルス対策関連の統計情報は、Microsoft Defender ウイルス対策設定に基づいています。 サードパーティのウイルス対策ソリューションを備えたデバイスは、"公開済み" として表示される可能性があります。

## <a name="related-topics"></a>関連項目

- [高度な捜索で脅威をプロアクティブに見つける](advanced-hunting-overview.md)
- [アナリスト レポート セクションについて理解する](threat-analytics-analyst-reports.md)
- [セキュリティの弱点と露出を評価して解決する](next-gen-threat-and-vuln-mgt.md)
