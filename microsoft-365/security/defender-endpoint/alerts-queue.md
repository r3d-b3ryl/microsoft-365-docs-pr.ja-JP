---
title: Microsoft Defender for Endpoint アラート キューを表示して整理する
description: Microsoft Defender for Endpoint アラート キューの動作と、アラートの一覧を並べ替えてフィルター処理する方法について説明します。
keywords: アラート、キュー、アラート キュー、並べ替え、順序、フィルター、アラートの管理、新規、進行中、解決済み、最新、キュー内の時間、重大度、期間、Microsoft 脅威専門家のアラート
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
ms.openlocfilehash: 0d6b012d2e3dbe6778c8d9c70552cf24427f8a3d
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64472047"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-alerts-queue"></a>Microsoft Defender for Endpoint アラート キューを表示して整理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-alertsq-abovefoldlink)

アラート **キューには** 、ネットワーク内のデバイスからフラグが設定されたアラートの一覧が表示されます。 既定では、キューには、グループ化されたビューで過去 30 日間に表示されたアラートが表示されます。 リストの上部に最新のアラートが表示され、最初に最新のアラートが表示されます。

> [!NOTE]
> 自動調査と修復によってアラートが大幅に削減され、セキュリティ運用の専門家は、より高度な脅威や他の価値の高いイニシアチブに集中できます。 サポートされているオペレーティング システムを持つデバイスに、自動調査用のサポートされるエンティティ (ファイルなど) がアラートに含まれている場合、自動調査と修復を開始できます。 自動調査の詳細については、「自動調査の [概要」を参照してください](automated-investigations.md)。

アラート ビューをカスタマイズするために選択できるオプションは複数あります。

上部のナビゲーションでは、次の操作を実行できます。

- 列をカスタマイズして列を追加または削除する
- フィルターの適用
- 1 日、3 日、1 週間、30 日、6 か月など、特定の期間のアラートを表示する
- アラート リストを excel にエクスポートする
- 通知の管理

:::image type="content" source="images/alerts-queue-list.png" alt-text="[アラート キュー] ページ" lightbox="images/alerts-queue-list.png":::

## <a name="sort-and-filter-alerts"></a>アラートの並べ替えとフィルター処理 

次のフィルターを適用して、アラートの一覧を制限し、アラートのより重点的なビューを取得できます。

### <a name="severity"></a>重要度

アラートの重大度|説明
---|---
高 <br> (赤)|高度な永続的な脅威 (APT) に関連付けられている一般的なアラート。 これらのアラートは、デバイスに与える損害の重大度が高いので、高いリスクを示します。 例として、資格情報の盗難ツールアクティビティ、グループに関連付けされていないランサムウェア アクティビティ、セキュリティ センサーの改ざん、または人間の敵を示す悪意のあるアクティビティがあります。
中 <br> (オレンジ)|高度な永続的脅威 (APT) の一部である可能性がある侵害後の動作に対するエンドポイント検出と応答からのアラート。 これらの動作には、攻撃段階に典型的な観察された動作、異常なレジストリの変更、疑わしいファイルの実行などがあります。 一部は内部セキュリティ テストの一部ですが、高度な攻撃の一部である可能性も考え、調査が必要です。
低 <br> (黄色)|一般的なマルウェアに関連する脅威に関するアラート。 たとえば、ハッキング ツール、マルウェア以外のハッキング ツール (探索コマンドの実行、ログのクリアなど) は、組織を対象とする高度な脅威を示す場合が多くはありません。 また、組織内のユーザーによる分離されたセキュリティ ツールのテストから行う場合があります。
情報 <br> (灰色)|ネットワークに悪影響を及ぼすとは見なされない可能性があるが、潜在的なセキュリティ問題に関する組織のセキュリティ認識を推進する可能性があるアラート。

#### <a name="understanding-alert-severity"></a>アラートの重大度について

Microsoft Defender ウイルス対策 (Microsoft Defender AV) と Defender for Endpoint アラートの重大度は、異なるスコープを表すので異なります。

脅威Microsoft Defender ウイルス対策重大度は、検出された脅威 (マルウェア) の絶対重大度を表し、感染した場合に個々のデバイスに潜在的なリスクに基づいて割り当てられます。

Defender for Endpoint アラートの重大度は、検出された動作の重大度、デバイスに対する実際のリスクを表しますが、さらに重要なのは、組織に対する潜在的なリスクです。

したがって、次に例を示します。

- Microsoft Defender ウイルス対策 が検出した脅威がデバイスに感染しなかった場合の Defender for Endpoint アラートの重大度は、実際の損害が発生しなかったため、「Informational」に分類されます。
- 実行中に商用マルウェアに関する警告が検出されましたが、Microsoft Defender AV によってブロックされ、修復されましたが、個々のデバイスに何らかの損害を与えた可能性がありますが、組織上の脅威を与えないので、"低" に分類されます。
- 個々のデバイスだけでなく、組織に脅威を与える可能性がある実行中に検出されたマルウェアに関するアラートは、最終的にブロックされた場合に関係なく、「中」または「高」とランク付けされる可能性があります。
- ブロックまたは修復された疑わしい行動アラートは、同じ組織の脅威に関する考慮事項に従って、"低"、"中"、または "高" にランク付けされます。

### <a name="status"></a>状態

[状態] に基づいてアラートの一覧をフィルター処理できます。

### <a name="categories"></a>カテゴリ

アラート カテゴリを再定義し、[MITRE ATT](https://attack.mitre.org/) と [](https://attack.mitre.org/tactics/enterprise/) CK マトリックスのエンタープライズ攻撃&しました。 新しいカテゴリ名は、すべての新しいアラートに適用されます。 既存のアラートは、以前のカテゴリ名を保持します。

### <a name="service-sources"></a>サービス ソース

Microsoft 脅威エキスパート参加者は、新しい脅威の専門家が管理する狩猟サービスから検出をフィルター処理して確認できます。

次のサービス ソースに基づいてアラートをフィルター処理します。

- Microsoft Defender for Identity
- Microsoft Defender for Cloud Apps
- Microsoft Defender for Endpoint
- Microsoft 365 Defender
- Microsoft Defender for Office 365
- アプリガバナンス
- AAD ID 保護

> [!NOTE]
> ウイルス対策フィルターは、デバイスが既定のリアルタイムMicrosoft Defender ウイルス対策マルウェア対策製品として使用している場合にのみ表示されます。

### <a name="tags"></a>タグ

アラートに割り当てられたタグに基づいてアラートをフィルター処理できます。

### <a name="policy"></a>ポリシー 

次のポリシーに基づいてアラートをフィルター処理できます。

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
|SmartScreen|WindowsDefenderSmartScreen|

### <a name="entities"></a>Entities

エンティティ名または ID に基づいてアラートをフィルター処理できます。 

### <a name="automated-investigation-state"></a>自動調査の状態

自動調査の状態に基づいてアラートをフィルター処理できます。



## <a name="related-topics"></a>関連項目

- [エンドポイント通知の Microsoft Defender の管理](manage-alerts.md)
- [Microsoft Defender for Endpoint アラートの調査](investigate-alerts.md)
- [Microsoft Defender for Endpoint アラートに関連付けられたファイルを調査する](investigate-files.md)
- [Microsoft Defender for Endpoint Devices リストのデバイスを調査する](investigate-machines.md)
- [Microsoft Defender for Endpoint アラートに関連付けられている IP アドレスを調査する](investigate-ip.md)
- [Microsoft Defender for Endpoint アラートに関連付けられているドメインを調査する](investigate-domain.md)
- [Microsoft Defender for Endpoint のユーザー アカウントを調査する](investigate-user.md)
