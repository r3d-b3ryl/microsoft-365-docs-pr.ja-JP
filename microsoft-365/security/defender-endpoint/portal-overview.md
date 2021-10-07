---
title: Microsoft Defender for Endpoint ポータルの概要
description: Microsoft 365 Defenderネットワークを監視し、潜在的な高度な永続的脅威 (APT) やデータ侵害への対応を支援できます。
keywords: Microsoft 365 Defender、ポータル、サイバーセキュリティ脅威インテリジェンス、ダッシュボード、アラート キュー、デバイスリスト、設定、デバイス管理、高度な攻撃
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 3450eebd549589f20b074f025d581783acdb23c1
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60168352"
---
# <a name="microsoft-365-defender-portal-overview"></a>Microsoft 365 Defender ポータルの概要

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

Enterpriseチームは、Microsoft 365 Defenderを使用して、潜在的な永続的な脅威アクティビティやデータ侵害の警告を監視および支援できます。

次[のMicrosoft 365 Defender使用](https://security.microsoft.com)できます。

- エンドポイントからのアラートの表示、並べ替え、トリアージ
- ファイルや IP アドレスなどの観測インジケーターの詳細を検索する
- Microsoft Defender for Endpoint の設定 (タイム ゾーンを含む) を変更し、ライセンス情報を確認する

## <a name="microsoft-365-defender"></a>Microsoft 365 Defender

ポータルを開く際に、次の情報が表示されます。

- (1) ナビゲーション ウィンドウ (ナビゲーション ウィンドウの上部にある水平線を選択して表示または非表示にする)
- (2) 検索、Communityセンター、ローカライズ、ヘルプとサポート、フィードバック

 ![Microsoft Defender for Endpoint portal.](images/mdatp-portal-overview.png)

> [!NOTE]
> マルウェア関連の検出は、デバイスが既定のリアルタイム保護マルウェア対策Microsoft Defender ウイルス対策を使用している場合にのみ表示されます。

すべてのセクションで使用できるメニュー オプションを使用して、ポータル内を移動できます。 各セクションの説明については、次の表を参照してください。

分野|説明
:---|:---
**(1) ナビゲーション ウィンドウ**|ナビゲーション ウィンドウを使用して、ダッシュボード、インシデント、デバイス リスト、アラート キュー、自動調査、高度な検索、**レポート**、パートナー **& API、Threat** **&** の脆弱性管理、評価とチュートリアル、サービス正常性、構成管理、**および 設定** の間を移動します。  ナビゲーション ウィンドウの上部にある水平線を選択して、表示または非表示を切り替えます。
**ダッシュボード**|アクティブな自動調査、アクティブなアラート、自動調査統計、危険にさらされているデバイス、危険にさらされているユーザー、センサーの問題を持つデバイス、サービスの正常性、検出ソース、および毎日のデバイスレポートダッシュボードにアクセスします。
**インシデント**|インシデントとして集計されたアラートを表示します。
**デバイスの一覧**|Defender for Endpoint にオンボードされているデバイスの一覧、そのデバイスに関する情報、およびデバイスの露出とリスク レベルが表示されます。
**アラート キュー**|組織のデバイスから生成されたアラートを表示します。
**自動化された調査**|ネットワークで行われた自動調査、アラートのトリガー、各調査の状態、調査の開始時間や調査期間などの詳細を表示します。
**高度な追求**|高度な検索を使用すると、強力な検索およびクエリ ツールを使用して、組織全体で積極的に検索および調査できます。
**レポート**|脅威の保護、デバイスの正常性とコンプライアンス、Web 保護、および脆弱性に関するグラフを表示します。
**パートナーと API**|サポートされているパートナー接続を表示し、プラットフォームの検出、調査、および脅威インテリジェンス機能を強化します。 接続されているアプリケーション、API エクスプローラー、API 使用状況の概要、およびデータエクスポート設定を表示することもできます。
**脅威&の管理**|デバイスの Microsoft Secure Score、露出スコア、露出デバイス、脆弱なソフトウェアを表示し、セキュリティに関する推奨事項の上位に対処します。
**評価とチュートリアル**|テスト デバイス、攻撃シミュレーション、レポートを管理します。 試用版環境でのガイド付きウォークスルーを通じて、Defender for Endpoint の機能を学び、体験してください。
**サービス正常性**|Defender for Endpoint サービスの現在の状態に関する情報を提供します。 サービスの正常性が正常か、現在の問題が発生した場合に確認できます。
**構成管理**|オンボード デバイス、組織のセキュリティ ベースライン、予測分析、Web 保護範囲を表示し、デバイスで攻撃表面管理を実行できます。
**設定**|オンボーディング中に選択した設定を表示し、業界の基本設定と保持ポリシー期間を更新できます。 アクセス許可、API、ルール、デバイス管理、IT サービス管理、ネットワーク評価などの他の構成設定を設定することもできます。
**(2) 検索、Communityセンター、ローカライズ、ヘルプとサポート、フィードバック**|**検索** - デバイス、ファイル、ユーザー、URL、IP、脆弱性、ソフトウェア、推奨事項で検索します。 <p> **Communityセンター** - Communityセンターにアクセスして、製品に関するエクスペリエンスを学び、共同作業し、共有します。 <p> **ローカライズ** - タイム ゾーンを設定します。 <p> **ヘルプとサポート** - Defender for Endpoint ガイド、Microsoft と Microsoft Premier のサポート、ライセンス情報、シミュレーション & チュートリアル、Defender for Endpoint 評価ラボにアクセスし、脅威の専門家に相談してください。 <p> **フィードバック** - 好きな操作や、より良い操作を行う方法に関するコメントを提供します。

> [!NOTE]
> 解像度の高い DPI スケーリングの問題を持つデバイスについては、「Windows [DPI](https://support.microsoft.com/help/3025083/windows-scaling-issues-for-high-dpi-devices)デバイスのスケーリングに関する問題」を参照してください。

## <a name="microsoft-defender-for-endpoint-icons"></a>Microsoft Defender for Endpoint アイコン

次の表に、ポータル全体で使用されるアイコンに関する情報を示します。

アイコン|説明
:---|:---
![ATP ロゴ アイコン。](images/atp-logo-icon.png)|Microsoft Defender for Endpoint ロゴ
![アラート アイコン。](images/alert-icon.png)|アラート: 高度な攻撃と相関するアクティビティを示します。
![検出アイコン。](images/detection-icon.png)|検出: マルウェアの脅威の検出を示します。
![アクティブな脅威アイコン。](images/active-threat-icon.png)|アクティブな脅威: 検出時にアクティブに実行される脅威。
![修復された icon1。](images/remediated-icon.png)|修復: デバイスから削除された脅威。
![修復されていないアイコン。](images/not-remediated-icon.png)|修復されない: デバイスから脅威が削除されません。
![Thunderbolt アイコン。](images/atp-thunderbolt-icon.png)|アラート プロセス ツリーでアラートをトリガーしたイベント **を示します**。
![デバイス アイコン。](images/atp-machine-icon.png)|デバイス アイコン
![Microsoft Defender AV イベント アイコン。](images/atp-windows-defender-av-events-icon.png)|Microsoft Defender ウイルス対策イベント
![Application Guard イベント アイコン。](images/atp-Application-Guard-events-icon.png)|Windows Defender Application Guardイベント
![Device Guard イベント アイコン。](images/atp-Device-Guard-events-icon.png)|Windows Defender Device Guardイベント
![Exploit Guard イベント アイコン。](images/atp-Exploit-Guard-events-icon.png)|Windows DefenderExploit Guard イベント
![SmartScreen イベント アイコン。](images/atp-Smart-Screen-events-icon.png)|Windows DefenderSmartScreen イベント
![ファイアウォール イベント アイコン。](images/atp-Firewall-events-icon.png)|Windowsファイアウォール イベント
![応答アクション アイコン。](images/atp-respond-action-icon.png)|応答アクション
![プロセス イベント アイコン。](images/atp-process-event-icon.png)|プロセス イベント
![ネットワーク通信イベント アイコン。](images/atp-network-communications-icon.png)|ネットワーク イベント
![ファイルの観測イベント アイコン。](images/atp-file-observed-icon.png)|ファイル イベント
![レジストリ イベント アイコン。](images/atp-registry-event-icon.png)|レジストリ イベント
![モジュールの読み込み DLL イベント アイコン。](images/atp-module-load-icon.png)|DLL イベントの読み込み
![その他のイベント アイコン。](images/atp-Other-events-icon.png)|その他のイベント
![アクセス トークンの変更アイコン。](images/atp-access-token-modification-icon.png)|アクセス トークンの変更
![ファイル作成アイコン。](images/atp-file-creation-icon.png)|ファイルの作成
![署名者アイコン。](images/atp-signer-icon.png)|署名者
![ファイル パス アイコン。](images/atp-File-path-icon.png)|ファイル パス
![コマンド ライン アイコン。](images/atp-command-line-icon.png)|コマンド ライン
![署名されていないファイル アイコン。](images/atp-unsigned-file-icon.png)|署名されていないファイル
![プロセス ツリー アイコン。](images/atp-process-tree.png)|プロセス ツリー
![メモリ割り当てアイコン。](images/atp-memory-allocation-icon.png)|メモリ割り当て
![プロセスの挿入アイコン。](images/atp-process-injection.png)|プロセスの挿入
![Powershell コマンドの実行アイコン。](images/atp-powershell-command-run-icon.png)|Powershell コマンドの実行
![Communityアイコンをクリックします。](images/atp-community-center.png)|Communityセンター
![通知アイコン。](images/atp-notifications.png)|通知
![脅威が見つかりません。](images/no-threats-found.png)|自動調査 - 脅威が見つかりません
![失敗したアイコン。](images/failed.png)|自動調査 - 失敗
![部分的に修復されたアイコン。](images/partially-investigated.png)|自動調査 - 部分的に調査
![システムによって終了します。](images/terminated-by-system.png)|自動調査 - システムによって終了
![保留中のアイコン。](images/pending.png)|自動調査 - 保留中
![実行中のアイコン。](images/running.png)|自動調査 - 実行
![修復された icon2。](images/remediated.png)|自動調査 - 修復
![部分的に調査されたアイコン。](images/partially_remediated.png)|自動調査 - 部分的に修復
![脅威の分析情報アイコン。](images/tvm_bug_icon.png)|脅威&の管理 - 脅威の分析情報
![可能なアクティブなアラート アイコン。](images/tvm_alert_icon.png)|脅威&の管理 - アクティブなアラートの可能性
![推奨事項の分析情報アイコン。](images/tvm_insight_icon.png)|脅威&の管理 - 推奨事項の分析情報

## <a name="related-topics"></a>関連トピック

- [概要 Microsoft 365 Defender](use.md)
- [セキュリティ操作ダッシュボードの表示](security-operations-dashboard.md)
- [[脅威の管理] &のダッシュボードを表示する](tvm-dashboard-insights.md)
- [脅威分析ダッシュボードを表示し、推奨される軽減アクションを実行する](threat-analytics.md)
