---
title: Microsoft Defender for Endpoint アラート キューを表示して整理する
description: Microsoft Defender for Endpoint アラート キューの動作と、アラートの一覧を並べ替えてフィルター処理する方法について説明します。
keywords: アラート、キュー、アラート キュー、並べ替え、順序、フィルター、アラートの管理、新規、進行中、解決済み、最新、キュー内の時間、重大度、期間、Microsoft 脅威専門家のアラート
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
ms.topic: article
ms.date: 03/27/2020
ms.technology: mde
ms.openlocfilehash: 478495601673a92075366d4497ac35f40c84172468b44926546d05c7b3b02edb
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53794467"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-alerts-queue"></a>Microsoft Defender for Endpoint アラート キューを表示して整理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-alertsq-abovefoldlink)

アラート **キューには** 、ネットワーク内のデバイスからフラグが設定されたアラートの一覧が表示されます。 既定では、キューには、グループ化されたビューで過去 30 日間に表示されたアラートが表示されます。 最新のアラートがリストの上部に表示され、最新のアラートを最初に確認できます。

> [!NOTE]
> 自動調査と修復によってアラート キューが大幅に削減され、セキュリティ運用の専門家は、より高度な脅威や他の価値の高いイニシアチブに集中できます。 サポートされているオペレーティング システムを持つデバイスに、自動調査用のサポートされるエンティティ (ファイルなど) がアラートに含まれている場合、自動調査と修復を開始できます。 自動調査の詳細については、「自動調査の [概要」を参照してください](automated-investigations.md)。

アラート キュー ビューをカスタマイズするために選択できるオプションは複数あります。 

上部のナビゲーションでは、次の操作を実行できます。

- グループ化されたビューまたはリスト ビューを選択する
- 列をカスタマイズして列を追加または削除する 
- ページごとに表示するアイテムを選択する
- ページ間の移動
- フィルターの適用

![アラート キューのイメージ](images/alerts-queue-list.png)

## <a name="sort-filter-and-group-the-alerts-queue"></a>アラート キューの並べ替え、フィルター処理、およびグループ化

次のフィルターを適用して、アラートの一覧を制限し、より集中してアラートを表示できます。

### <a name="severity"></a>緊急度

アラートの重大度 | 説明
:---|:---
高 </br>(赤) | 高度な永続的な脅威 (APT) に関連付けられている一般的なアラート。 これらのアラートは、デバイスに与える損害の重大度が高いので、高いリスクを示します。 例として、資格情報の盗難ツールアクティビティ、グループに関連付けされていないランサムウェア アクティビティ、セキュリティ センサーの改ざん、または人間の敵を示す悪意のあるアクティビティがあります。
中 </br>(オレンジ) | 高度な永続的脅威 (APT) の一部である可能性がある侵害後の動作に対するエンドポイント検出と応答からのアラート。 これには、攻撃段階に典型的な観察された動作、異常なレジストリの変更、疑わしいファイルの実行などがあります。 一部は内部セキュリティ テストの一部ですが、高度な攻撃の一部である可能性も考え、調査が必要です。
低 </br>(黄色) | 一般的なマルウェアに関連する脅威に関するアラート。 たとえば、ハッキング ツール、マルウェア以外のハッキング ツール (探索コマンドの実行、ログのクリアなど) は、組織を対象とする高度な脅威を示す場合が多くはありません。 また、組織内のユーザーによる分離されたセキュリティ ツールのテストから行う場合があります。
情報 </br>(灰色) | ネットワークに悪影響を及ぼすとは見なされない可能性があるが、潜在的なセキュリティ問題に関する組織のセキュリティ認識を推進する可能性があるアラート。

#### <a name="understanding-alert-severity"></a>アラートの重大度について

Microsoft Defender ウイルス対策 (Microsoft Defender AV) と Defender for Endpoint アラートの重大度は、スコープが異なっているので異なります。

Microsoft Defender AV の脅威の重大度は、検出された脅威 (マルウェア) の絶対重大度を表し、感染した場合に個々のデバイスに潜在的なリスクに基づいて割り当てられます。

Defender for Endpoint アラートの重大度は、検出された動作の重大度、デバイスに対する実際のリスクを表しますが、さらに重要なのは、組織に対する潜在的なリスクです。

したがって、次に例を示します。

- Microsoft Defender AV に関する Defender for Endpoint アラートの重大度は、完全に防止され、デバイスに感染しなかった脅威を検出しました。実際の被害はなかったため、「Informational」に分類されます。
- 実行中に商用マルウェアに関する警告が検出されましたが、Microsoft Defender AV によってブロックされ、修復されましたが、個々のデバイスに何らかの損害を与えた可能性がありますが、組織上の脅威を与えないので、"低" に分類されます。
- 個々のデバイスだけでなく、組織に脅威を与える可能性がある実行中に検出されたマルウェアに関するアラートは、最終的にブロックされた場合に関係なく、「中」または「高」とランク付けされる可能性があります。
- ブロックまたは修復された疑わしい行動アラートは、同じ組織の脅威に関する考慮事項に従って、"低"、"中"、または "高" にランク付けされます。

#### <a name="understanding-alert-categories"></a>アラート カテゴリについて

アラート カテゴリを再定義し[、MITRE ATT](https://attack.mitre.org/)および CK マトリックスのエンタープライズ攻撃&しました。 [](https://attack.mitre.org/tactics/enterprise/) 新しいカテゴリ名は、すべての新しいアラートに適用されます。 既存のアラートは、以前のカテゴリ名を保持します。

次の表に、現在のカテゴリと、そのカテゴリが以前のカテゴリに一般的にマップされる方法を示します。 

| 新しいカテゴリ       | API カテゴリ名   | 検出された脅威のアクティビティまたはコンポーネント                                                                                                 |
|----------------------|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------|
| コレクション           | コレクション          | エクスフィルトレーション用のデータの検索と収集                                                                                         |
| コマンドとコントロール  | CommandAndControl   | 攻撃者が制御するネットワーク インフラストラクチャに接続してデータを中継したり、コマンドを受信したりする                                          |
| 資格情報へのアクセス    | CredentialAccess    | ネットワーク内のデバイスや他のリソースに対する制御を拡張するための有効な資格情報の取得                                       |
| 防御回避      | DefenseEvasion      | たとえば、セキュリティ アプリのオフ、インプラントの削除、ルートキットの実行によるセキュリティ制御の回避                        |
| 検出            | 検出           | 管理者コンピューター、ドメイン コントローラー、ファイル サーバーなどの重要なデバイスとリソースに関する情報の収集  |
| 実行            | 実行           | 攻撃者ツールと悪意のあるコード (RAT やバックドアを含む) の起動                                                             |
| 流出         | 流出        | ネットワークから外部の攻撃者が制御する場所へのデータの抽出                                                         |
| Exploit              | Exploit             | コードの悪用と悪用の可能性のあるアクティビティ                                                                                       |
| 初期アクセス       | InitialAccess       | ターゲット ネットワークへの最初のエントリを取得する (通常はパスワード推測、悪用、フィッシングメールを含む)                      |
| 横方向の動き     | LateralMovement     | ターゲット ネットワーク内のデバイス間を移動して重要なリソースに到達するか、ネットワークの永続性を得る                                |
| マルウェア              | マルウェア             | バックドア、トロイの木馬、その他の種類の悪意のあるコード                                                                                 |
| 永続性          | 永続性         | 自動起動機能拡張ポイント (ASEPs) を作成してアクティブな状態を維持し、システムの再起動を維持する                                        |
| 特権のエスカレーション | PrivilegeEscalation | 特権プロセスまたはアカウントのコンテキストでコードを実行して、より高いアクセス許可レベルを取得する                         |
| ランサムウェア           | ランサムウェア          | ファイルを暗号化し、支払いを強要してアクセスを復元するマルウェア                                                                     |
| 不審なアクティビティ  | SuspiciousActivity  | マルウェアアクティビティまたは攻撃の一部である可能性のある非一部のアクティビティ                                                                 |
| 望ましくないソフトウェア    | UnwantedSoftware    | 生産性とユーザー エクスペリエンスに影響を与える低評価のアプリとアプリ。望ましくない可能性のあるアプリケーションとして検出された (PUA) |

### <a name="status"></a>状態

アラートの一覧は、その状態に基づいて制限できます。

### <a name="investigation-state"></a>調査の状態

自動調査の状態に対応します。

### <a name="category"></a>カテゴリ

キューをフィルター処理して、特定の種類の悪意のあるアクティビティを表示できます。

### <a name="assigned-to"></a>割り当て先

自分に割り当てられているアラートを表示するか、オートメーションを表示するかを選択できます。

### <a name="detection-source"></a>検出ソース

アラート検出をトリガーしたソースを選択します。 Microsoft 脅威エキスパート参加者は、新しい脅威の専門家が管理する狩猟サービスから検出をフィルター処理して確認できます。

>[!NOTE]
>ウイルス対策フィルターは、デバイスが既定のリアルタイムMicrosoft Defender ウイルス対策マルウェア対策製品として使用している場合にのみ表示されます。

| 検出ソース                  | API 値                  |
|-----------------------------------|----------------------------|
| サードパーティ製センサー                 | ThirdPartySensors          |
| ウイルス対策                         | WindowsDefenderAv          |
| 自動調査           | AutomatedInvestigation     |
| カスタム検出                  | CustomDetection            |
| カスタム TI                         | CustomerTI                 |
| EDR                               | WindowsDefenderAtp         |
| Microsoft 365 Defender            | MTP                        |
| Microsoft Defender for Office 365 | OfficeATP                  |
| Microsoft 脅威エキスパート          | ThreatExperts              |
| SmartScreen                       | WindowsDefenderSmartScreen |

### <a name="os-platform"></a>OS プラットフォーム

調査する OS プラットフォームを選択して、アラート キュー ビューを制限します。

### <a name="device-group"></a>デバイス グループ

確認する特定のデバイス グループがある場合は、グループを選択してアラート キュー ビューを制限できます。 

### <a name="associated-threat"></a>関連する脅威

このフィルターを使用して、注目度の高い脅威に関連するアラートに集中します。 詳細な脅威の一覧については、「Threat [analytics」を参照してください](threat-analytics.md)。

## <a name="related-topics"></a>関連トピック

- [エンドポイント通知の Microsoft Defender の管理](manage-alerts.md)
- [Microsoft Defender for Endpoint アラートの調査](investigate-alerts.md)
- [Microsoft Defender for Endpoint アラートに関連付けられたファイルを調査する](investigate-files.md)
- [Microsoft Defender for Endpoint Devices リストのデバイスを調査する](investigate-machines.md)
- [Microsoft Defender for Endpoint アラートに関連付けられている IP アドレスを調査する](investigate-ip.md)
- [Microsoft Defender for Endpoint アラートに関連付けられているドメインを調査する](investigate-domain.md)
- [Microsoft Defender for Endpoint のユーザー アカウントを調査する](investigate-user.md)
