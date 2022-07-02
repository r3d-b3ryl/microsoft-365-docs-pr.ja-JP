---
title: Microsoft Defender for Endpoint アラート キューを表示して整理する
description: Microsoft Defender for Endpointアラート キューのしくみと、アラートの一覧を並べ替えてフィルター処理する方法について説明します。
keywords: アラート, キュー, アラート キュー, 並べ替え, 順序, フィルター, アラートの管理, 新規, 進行中, 解決済み, 最新, キュー内の時間, 重大度, 期間, Microsoft 脅威エキスパート アラート
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
ms.topic: article
ms.date: 03/27/2020
ms.technology: mde
ms.openlocfilehash: 13959666f0c44f83fcb938db010ed30d5e5056b4
ms.sourcegitcommit: bfbe2574f487ced69e711b48ce140120bd99181b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2022
ms.locfileid: "66607534"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-alerts-queue"></a>Microsoft Defender for Endpoint アラート キューを表示して整理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-alertsq-abovefoldlink)

**アラート キュー** には、ネットワーク内のデバイスからフラグが設定されたアラートの一覧が表示されます。 既定では、グループ化されたビューに過去 30 日間に表示されたアラートがキューに表示されます。 一覧の上部に最新のアラートが表示され、最初に最新のアラートが表示されます。

> [!NOTE]
> アラートは、自動調査と修復によって大幅に削減され、セキュリティ運用の専門家は、より高度な脅威やその他の価値の高いイニシアチブに集中できます。 サポートされているオペレーティング システムを持つデバイス内の自動調査用にサポートされているエンティティ (ファイルなど) がアラートに含まれている場合は、自動調査と修復を開始できます。 自動調査の詳細については、「 [自動調査の概要](automated-investigations.md)」を参照してください。

アラート ビューをカスタマイズするには、いくつかのオプションを選択できます。

上部のナビゲーションでは、次の操作を行うことができます。

- 列を追加または削除する列をカスタマイズする
- フィルターの適用
- 1 日、3 日、1 週間、30 日、6 か月などの特定の期間のアラートを表示する
- アラートの一覧を Excel にエクスポートする
- 通知の管理

:::image type="content" source="images/alerts-queue-list.png" alt-text="[アラート キュー] ページ" lightbox="images/alerts-queue-list.png":::

## <a name="sort-and-filter-alerts"></a>アラートの並べ替えとフィルター処理 

次のフィルターを適用して、アラートの一覧を制限し、アラートのより焦点を絞ったビューを取得できます。

### <a name="severity"></a>重要度

アラートの重大度|説明
---|---
高 <br> (赤)|高度な永続的脅威 (APT) に関連する一般的なアラート。 これらのアラートは、デバイスに与える被害の重大度が高いため、リスクが高いことを示します。 たとえば、資格情報盗難ツールアクティビティ、ランサムウェアアクティビティがグループに関連付けられていない、セキュリティ センサーの改ざん、または人間の敵対者を示す悪意のあるアクティビティなどです。
中 <br> (オレンジ)|高度な永続的な脅威 (APT) の一部である可能性があるエンドポイントの検出と違反後の対応の動作からのアラート。 これらの動作には、攻撃ステージに典型的な観察された動作、異常なレジストリの変更、疑わしいファイルの実行などが含まれます。 内部セキュリティ テストの一部である場合もありますが、高度な攻撃の一部でもある可能性があるため、調査が必要です。
低 <br> (黄色)|一般的なマルウェアに関連する脅威に関するアラート。 たとえば、ハッキング ツール、マルウェア以外のハッキング ツール (探索コマンドの実行、ログのクリアなど) は、組織をターゲットとする高度な脅威を示さないことがよくあります。 また、組織内のユーザーによる分離されたセキュリティ ツールのテストからも発生する可能性があります。
情報 <br> (灰色)|ネットワークに有害であるとは考えられませんが、潜在的なセキュリティの問題に対する組織のセキュリティ認識を促進する可能性があるアラート。

#### <a name="understanding-alert-severity"></a>アラートの重大度について

Microsoft Defender ウイルス対策 (Microsoft Defender AV) と Defender for Endpoint アラートの重大度は、スコープが異なるため異なります。

Microsoft Defender ウイルス対策の脅威の重大度は、検出された脅威 (マルウェア) の絶対重大度を表し、感染した場合は個々のデバイスに潜在的なリスクに基づいて割り当てられます。

Defender for Endpoint アラートの重大度は、検出された動作の重大度、デバイスに対する実際のリスクを表しますが、さらに重要なのは、組織に対する潜在的なリスクです。

そのため、次の例を示します。

- Microsoft Defender ウイルス対策によって検出された、デバイスに感染しなかった脅威に関する Defender for Endpoint アラートの重大度は、実際の被害がないため、"Informational" に分類されます。
- 実行中に商用マルウェアに関するアラートが検出されましたが、Microsoft Defender AV によってブロックおよび修復されたアラートは、個々のデバイスに何らかの損害を与えた可能性がありますが、組織の脅威を与えないため、"低" に分類されます。
- 実行中に検出されたマルウェアに関するアラートは、個々のデバイスだけでなく、最終的にブロックされたかどうかに関係なく、組織に脅威をもたらす可能性があります。"中" または "高" にランク付けされる可能性があります。
- ブロックまたは修復されなかった疑わしい動作アラートは、同じ組織の脅威に関する考慮事項に従って、"低"、"中"、または "高" にランク付けされます。

### <a name="status"></a>状態

状態に基づいてアラートの一覧をフィルター処理することもできます。

> [!NOTE]
> *サポートされていないアラートの種類* のアラートの状態が表示される場合は、自動調査機能では、自動調査を実行するためにそのアラートを取得できないことを意味します。 ただし、 [これらのアラートは手動で調査](../defender/investigate-incidents.md#alerts)できます。

### <a name="categories"></a>カテゴリ

[MITRE ATT&CK マトリックス](https://attack.mitre.org/)の[エンタープライズ攻撃戦術](https://attack.mitre.org/tactics/enterprise/)に合わせてアラート カテゴリを再定義しました。 新しいカテゴリ名は、すべての新しいアラートに適用されます。 既存のアラートでは、前のカテゴリ名が保持されます。

### <a name="service-sources"></a>サービス ソース

プレビュー参加者Microsoft 脅威エキスパート、新しい脅威の専門家が管理するハンティング サービスの検出をフィルター処理して表示できるようになりました。

次のサービス ソースに基づいてアラートをフィルター処理します。

- Microsoft Defender for Identity
- Microsoft Defender for Cloud Apps
- Microsoft Defender for Endpoint
- Microsoft 365 Defender
- Microsoft Defender for Office 365
- アプリ ガバナンス
- AAD Identity Protection

> [!NOTE]
> ウイルス対策フィルターは、デバイスが既定のリアルタイム保護マルウェア対策製品として Microsoft Defender ウイルス対策を使用している場合にのみ表示されます。

### <a name="tags"></a>タグ

アラートに割り当てられたタグに基づいてアラートをフィルター処理できます。

### <a name="policy"></a>ポリシー 

アラートは、次のポリシーに基づいてフィルター処理できます。

|検出ソース|API 値|
|---|---|
|サード パーティ製センサー|ThirdPartySensors|
|ウイルス対策|WindowsDefenderAv|
|自動調査|AutomatedInvestigation|
|カスタム検出|CustomDetection|
|カスタム TI|CustomerTI|
|EDR|WindowsDefenderAtp|
|Microsoft 365 Defender|MTP|
|Microsoft Defender for Office 365|OfficeATP|
|Microsoft 脅威エキスパート|ThreatExperts|
|Smartscreen|WindowsDefenderSmartScreen|

### <a name="entities"></a>Entities

エンティティ名または ID に基づいてアラートをフィルター処理できます。 

### <a name="automated-investigation-state"></a>自動調査の状態

自動調査の状態に基づいてアラートをフィルター処理することもできます。



## <a name="related-topics"></a>関連トピック

- [Microsoft Defender for Endpointアラートを管理する](manage-alerts.md)
- [Microsoft Defender for Endpointアラートを調査する](investigate-alerts.md)
- [Microsoft Defender for Endpointアラートに関連付けられているファイルを調査する](investigate-files.md)
- [Microsoft Defender for Endpoint デバイスの一覧のデバイスを調査する](investigate-machines.md)
- [Microsoft Defender for Endpoint アラートに関連付けられている IP アドレスを調査する](investigate-ip.md)
- [Microsoft Defender for Endpoint アラートに関連付けられているドメインを調査する](investigate-domain.md)
- [Microsoft Defender for Endpointでユーザー アカウントを調査する](investigate-user.md)
