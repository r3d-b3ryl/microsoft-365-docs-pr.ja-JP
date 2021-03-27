---
title: Microsoft Defender ATP でカスタム検出ルールを作成する
ms.reviewer: ''
description: 高度な検索クエリに基づいてカスタム検出ルールを作成する方法について説明します。
keywords: カスタム検出、作成、管理、アラート、編集、オンデマンドでの実行、頻度、間隔、検出ルール、高度な狩猟、ハント、クエリ、応答アクション、mdatp、microsoft Defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 48b1f1bf9506acc8491887fca49295d5e4ccbd69
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382711"
---
# <a name="create-custom-detection-rules"></a>検出ルールの作成

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

高度な検索クエリから[](advanced-hunting-overview.md)構築されたカスタム検出ルールを使用すると、侵害アクティビティの疑いやデバイスの構成ミスなど、さまざまなイベントやシステム状態を積極的に監視できます。 一定の間隔で実行し、アラートを生成し、一致するたびに応答アクションを実行する設定できます。

新しいカスタム検出ルールを作成する方法については、この記事を参照してください。 または [、既存のルールの表示と管理を参照してください](custom-detections-manage.md)。

> [!NOTE]
> カスタム検出を作成または管理するには、 [役割に](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) セキュリティ設定の管理権限 **が必要** です。

## <a name="1-prepare-the-query"></a>1. クエリを準備します。

Microsoft Defender セキュリティ センターで、[高度な検索] **に** 移動し、既存のクエリを選択するか、新しいクエリを作成します。 新しいクエリを使用する場合は、クエリを実行してエラーを特定し、考えられる結果を理解します。

>[!IMPORTANT]
>サービスがあまりにも多くのアラートを返さなすぎ防止するために、各ルールは、実行されるたびに 100 件のアラートのみを生成するに制限されます。 ルールを作成する前に、クエリを調整して、通常の毎日のアクティビティに対する警告を回避してください。

### <a name="required-columns-in-the-query-results"></a>クエリ結果に必要な列

カスタム検出ルールにクエリを使用するには、次の列を返す必要があります。

- `Timestamp`
- `DeviceId`
- `ReportId`

単純なクエリ (結果をカスタマイズまたは集計するために or 演算子を使用しないクエリなど) は、通常、これらの一般的な `project` `summarize` 列を返します。

より複雑なクエリがこれらの列を返すには、さまざまな方法があります。 たとえば、集計とカウントを行う場合は、各デバイスに関連する最新のイベントから取得して取得 `DeviceId` `Timestamp` `ReportId` できます。

以下のサンプル クエリは、ウイルス対策検出を含む一意のデバイス ( ) の数をカウントし、これを使用して 5 つを超える検出を持つデバイス `DeviceId` のみを検索します。 最新の値と `Timestamp` 対応する値を取得 `ReportId` するには、関数と `summarize` 一緒に演算子を使用 `arg_max` します。

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> クエリのパフォーマンスを向上するには、ルールの目的の実行頻度に一致する時間フィルターを設定します。 実行頻度が最も少ないのは 24 時間ごとに行われるので、過去 1 日のフィルター処理では、すべての新しいデータがカバーされます。

## <a name="2-create-a-new-rule-and-provide-alert-details"></a>2. 新しいルールを作成し、アラートの詳細を指定します。

クエリ エディターでクエリを使用して、[検出ルールの作成] **を選択し** 、次のアラートの詳細を指定します。

- **検出名**—検出ルールの名前
- **頻度**—クエリを実行してアクションを実行する間隔。 [以下のその他のガイダンスを参照してください。](#rule-frequency)
- **アラート タイトル**- ルールによってトリガーされたアラートで表示されるタイトル
- **重大度 —** ルールによって識別されるコンポーネントまたはアクティビティの潜在的なリスク。 [アラートの重大度について読む](alerts-queue.md#severity)
- **Category**—脅威コンポーネントまたはアクティビティの種類 (その場合)。 [アラート カテゴリについて読む](alerts-queue.md#understanding-alert-categories)
- **MITRE ATT&CK** の手法 (CK フレームワークの MITRE ATT に記載されているルールで識別される 1 つ以上の攻撃&です。 このセクションは、マルウェア、ランサムウェア、疑わしいアクティビティ、望ましくないソフトウェアなど、特定のアラート カテゴリでは使用できません。
- **Description**—ルールによって識別されるコンポーネントまたはアクティビティの詳細 
- **推奨されるアクション**—応答者がアラートに応答して実行する可能性がある追加のアクション

アラートの詳細の表示方法の詳細については、「アラート キュー [」を参照してください](alerts-queue.md)。

### <a name="rule-frequency"></a>ルールの頻度

保存すると、新しいカスタム検出ルールが直ちに実行され、過去 30 日間のデータからの一致がチェックされます。 次に、ルールは、選択した頻度に基づいて、固定間隔とルックバック期間で再度実行されます。

- **24 時間ごとに** 実行され、過去 30 日間のデータを確認します。
- **12 時間ごとに** 実行され、過去 24 時間のデータを確認します。
- **3 時間ごとに** 実行され、過去 6 時間のデータを確認します。
- **1 時間** ごとに 1 時間ごとに実行され、過去 2 時間のデータを確認します。

ルールを編集すると、設定した頻度に従ってスケジュールされた次の実行時に適用された変更と一緒に実行されます。


> [!TIP]
> クエリのタイム フィルターとルックバック期間を一致します。 ルックバック期間外の結果は無視されます。

検出を監視する頻度に一致する頻度を選択し、通知に応答する組織の容量を検討します。

## <a name="3-choose-the-impacted-entities"></a>3. 影響を受け取ったエンティティを選択します。

影響を受ける主なエンティティまたは影響を受けるエンティティを検索するクエリ結果の列を特定します。 たとえば、クエリはデバイス ID とユーザー ID の両方を返す場合があります。 これらの列の中で、影響を受ける主なエンティティを表す列を特定すると、サービスは関連するアラートの集計、インシデントの関連付け、およびターゲット応答アクションの集計に役立ちます。

エンティティの種類ごとに 1 つの列のみを選択できます。 クエリによって返されない列は選択できません。

## <a name="4-specify-actions"></a>4. アクションを指定します。

カスタム検出ルールは、クエリによって返されるファイルまたはデバイスに対して自動的にアクションを実行できます。

### <a name="actions-on-devices"></a>デバイスでのアクション

これらのアクションは、クエリ結果の列 `DeviceId` のデバイスに適用されます。

- **デバイスの分離**—完全なネットワーク分離を適用し、Defender for Endpoint サービスを除くすべてのアプリケーションまたはサービスにデバイスが接続できません。 [デバイスの分離の詳細](respond-machine-alerts.md#isolate-devices-from-the-network)
- **調査パッケージの収集**— ZIP ファイル内のデバイス情報を収集します。 [調査パッケージの詳細](respond-machine-alerts.md#collect-investigation-package-from-devices)
- **ウイルス対策スキャンの実行**-デバイスで Microsoft Defender ウイルス対策スキャン全体を実行する
- **調査の開始**- デバイスで [自動調査](automated-investigations.md) を開始する
- **アプリの実行を制限** する :Microsoft 発行の証明書で署名されたファイルのみを実行できるデバイスの制限を設定します。 [アプリの実行を制限する方法の詳細](respond-machine-alerts.md#restrict-app-execution)

### <a name="actions-on-files"></a>ファイルに対するアクション

これらのアクションは、クエリ結果の列または列内 `SHA1` `InitiatingProcessSHA1` のファイルに適用されます。

- **Allow/Block**—ファイルをカスタム インジケーター [](manage-indicators.md)リストに自動的に追加して、常に実行を許可またはブロックします。 このアクションの範囲を設定して、選択したデバイス グループでのみ実行できます。 このスコープは、ルールのスコープとは独立しています。
- **検疫ファイル**— ファイルを現在の場所から削除し、コピーを検疫に入れる

### <a name="actions-on-users"></a>ユーザーに対するアクション

- **ユーザーを侵害済み** としてマークする —Azure Active Directory でユーザーのリスク レベルを "高" に設定し、対応する ID 保護ポリシーを [トリガーします](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection#risk-levels)。

## <a name="5-set-the-rule-scope"></a>5. ルールスコープを設定します。

ルールの対象となるデバイスを指定するスコープを設定します。

- すべてのデバイス
- 特定のデバイス グループ

スコープ内のデバイスからのデータだけがクエリされます。 また、これらのデバイスでのみアクションが実行されます。

## <a name="6-review-and-turn-on-the-rule"></a>6. ルールを確認して有効にする。

ルールを確認した後、[作成] **を選択して** 保存します。 カスタム検出ルールが直ちに実行されます。 構成された頻度に基づいて再び実行され、一致を確認し、アラートを生成し、応答アクションを実行します。

カスタム検出 [ルールを表示および管理し、](custom-detections-manage.md)以前の実行を確認し、トリガーしたアラートを確認できます。 必要に応じてルールを実行して変更できます。

## <a name="related-topics"></a>関連項目

- [検出ルールの表示と管理](custom-detections-manage.md)
- [カスタム検出の概要](overview-custom-detections.md)
- [高度な検出の概要](advanced-hunting-overview.md)
- [高度な捜索のクエリ言語について学習する](advanced-hunting-query-language.md)
- [アラートの表示と整理](alerts-queue.md)
