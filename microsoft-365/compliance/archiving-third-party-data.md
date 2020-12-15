---
title: サード パーティのデータをアーカイブする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
ms.custom:
- seo-marvel-apr2020
description: ソーシャル メディア プラットフォーム、インスタント メッセージング プラットフォーム、およびドキュメント コラボレーション プラットフォームから Microsoft 365 メールボックスにサード パーティデータをインポートする方法について説明します。
ms.openlocfilehash: 42835d103e027bd63687151554f811dc0945d46f
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682618"
---
# <a name="archive-third-party-data"></a>サード パーティのデータをアーカイブする

Microsoft 365 を使用すると、管理者はデータ コネクタを使用して、ソーシャル メディア プラットフォーム、インスタント メッセージング プラットフォーム、およびドキュメント コラボレーション プラットフォームから Microsoft 365 組織内のメールボックスにサード パーティデータをインポートおよびアーカイブできます。 Microsoft 365 でデータ コネクタを使用してサード パーティのデータをインポートおよびアーカイブする主な利点の 1 つは、インポート後にさまざまな Microsoft 365 コンプライアンス ソリューションを適用できる点です。 これにより、組織の Microsoft 以外のデータが、組織に影響を与える規制と基準に準拠している必要があります。

## <a name="third-party-data-connectors"></a>サードパーティのデータ コネクタ

次の表に、Microsoft 365 コンプライアンス センターで使用できるサード パーティのデータ コネクタを示します。 この表は、Microsoft 365 でインポートおよびアーカイブした後にサード パーティのデータに適用できるコンプライアンス ソリューションの概要も示しています。 各コンプライアンス [ソリューションの詳細](#overview-of-compliance-solutions-that-support-third-party-data) と、それがサード パーティのデータにメリットをもたらす方法については、次のセクションを参照してください。

> [!TIP]
> [サード パーティ製データ **]** 列のリンクをクリックして、そのデータ型のコネクタを作成するための詳しい手順を実行します。

|サード パーティのデータ  |訴訟ホールド|電子情報開示  |保持設定  |レコード管理  |コミュニケーション コンプライアンス  |インサイダー リスクの管理  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Android <sup>1</sup>](archive-android-archiver-data.md)     |![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[AT&T Network <sup>1</sup>](archive-att-network-archiver-data.md)     |![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[ベル ネットワーク <sup>1</sup>](archive-bell-network-data.md)     |![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Bloomberg メッセージ](archive-bloomberg-message-data.md)     |![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[CellTrust <sup>2</sup>](archive-celltrust-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Cisco Jabber <sup>2</sup>](archive-ciscojabberonmssql-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[EML <sup>2</sup>](archive-eml-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[エンタープライズ番号 <sup>1</sup>](archive-enterprise-number-data.md)     |![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Facebook](archive-facebook-data-with-sample-connector.md)     |![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[FX Connect <sup>2</sup>](archive-fxconnect-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[人事 (HR)](import-hr-data.md) ||||||![チェック マーク](../media/checkmark.png)
|[IceChat](archive-icechat-data.md)     |![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Instant Bloomberg](archive-instant-bloomberg-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Jive <sup>2</sup>](archive-jive-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[LinkedIn](archive-linkedin-data.md)   |![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[MS SQL Database <sup>2</sup>](archive-mssqldatabaseimporter-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[O2 ネットワーク <sup>1</sup>](archive-o2-network-data.md)     |![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[物理的な問題](import-physical-badging-data.md) ||||||![チェック マーク](../media/checkmark.png)|
|[Pivot <sup>2</sup>](archive-pivot-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Reuters Dealing <sup>2</sup>](archive-reutersdealing-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Reuters <sup>E、2</sup>](archive-reuterseikon-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Reuters FX <sup>2</sup>](archive-reutersfx-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Slack 電子情報開示 <sup>2</sup>](archive-slack-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[2 <sup></sup>](archive-symphony-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[TELUS Network <sup>1</sup>](archive-telus-network-data.md)    |![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[テキスト区切り <sup>2</sup>](archive-text-delimited-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[Twitter](archive-twitter-data-with-sample-connector.md)     |![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[Verizon Network <sup>1</sup>](archive-verizon-network-data.md)     |![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Webex Teams <sup>2</sup>](archive-webexteams-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Web ページ <sup>2</sup>](archive-webpagecapture-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[WhatsApp <sup>1</sup>](archive-whatsapp-data.md)     |![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Facebook <sup>2</sup>の Workplace](archive-workplacefromfacebook-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[XIP <sup>2</sup>](archive-xip-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[XSLT/XML <sup>2</sup>](archive-xslt-xml-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[会議<sup>2</sup>のズーム](archive-zoommeetings-data.md)     |![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
||||||||

> [!NOTE]
> <sup>TeleMessage</sup> によって提供される 1 つのデータ コネクタ。 Microsoft 365 でデータをアーカイブするには、TeleMessage を使用して組織のアーカイブ サービスをセットアップする必要があります。 詳細については、このデータ型の詳細な手順の前提条件のセクションを参照してください。<br/><br/><sup>2</sup> データ コネクタは Globanet によって提供されます。 Microsoft 365 でデータをアーカイブする前に、Globanet と一緒に組織のアーカイブ サービスをセットアップする必要があります。 詳細については、このデータ型の詳細な手順の前提条件のセクションを参照してください。

前の表に記載されているサードパーティのデータ (人事データと物理的な不良データを除く) は、ユーザー メールボックスにインポートされます。 サード パーティのデータをサポートする対応するコンプライアンス ソリューションは、データが保存されているユーザー メールボックスに適用されます。

## <a name="overview-of-compliance-solutions-that-support-third-party-data"></a>サード パーティのデータをサポートするコンプライアンス ソリューションの概要

次のセクションでは、Microsoft 365 コンプライアンス ソリューションが前の表に示したサード パーティデータの管理に役立ついくつかの点について説明します。

### <a name="litigation-hold"></a>訴訟ホールド

サードパーティのデータ [を保持するには](create-a-litigation-hold.md) 、ユーザー メールボックスに訴訟ホールドを適用します。 保留リストを作成する場合は、保持期間 (時間ベースの保留とも呼 *ばれる)* を指定して、削除および変更されたサード パーティのデータを指定の期間保持し、メールボックスから完全に削除することができます。 または、コンテンツを無期限に保持する (無限保持と呼 *ばれる)* か、訴訟ホールドが削除されるまで保持できます。

### <a name="ediscovery"></a>電子情報開示

Microsoft 365 の 3 つの主要な電子情報開示ツールは、コンテンツ検索、コア電子情報開示、Advanced eDiscovery です。

- **[コンテンツ検索](content-search.md)。** コンテンツ検索ツールを使用して、インポートしたサード パーティのデータをメールボックスで検索できます。 検索クエリと条件を使用して検索結果を絞り込み、検索結果をエクスポートできます。

- **[コア電子情報開示](get-started-core-ediscovery.md)。** このツールは基本的な検索およびエクスポート機能に基づいて構築され、ケース データにアクセスできるユーザーを制御したり、検索条件に一致するユーザー メールボックスまたはメールボックスのコンテンツを保留にしたりできるケースを作成できます。 つまり、ユーザーのメールボックスにインポートされたサード パーティのデータを電子情報開示の保留にできます。

- **[Advanced eDiscovery](overview-ediscovery-20.md).** この強力なツールを使用すると、ケースにカストディアンを追加し、保管担当者のデータを保留にし、カストディアンのサード パーティデータをレビューに読み込み、テーマや重複検出などの詳細な分析を行って、コア電子情報開示のケース機能を拡張できます。 サード パーティのデータをレビュー セットに読み込むと、クエリを実行して絞り込み結果セットにフィルター処理できます。

   Core 電子情報開示と Advanced eDiscovery の両方を使用すると、組織の法的または内部的な調査に関連する可能性のあるサード パーティのデータを管理できます。

### <a name="retention-settings"></a>保持設定

ユーザーメールボックス [にアイテム保持](retention.md) ポリシーを適用して、保持期間の経過後にサード パーティデータ (および他のメールボックスコンテンツ) を保持してから削除できます。 また、アイテム保持ポリシーを使用して、特定の年齢のサード パーティ データ[](disposition.md)を削除したり、保持ラベルを使用して、サード パーティデータの保持期間が経過した場合に廃棄レビューをトリガーすることもできます。

### <a name="records-management"></a>レコード管理

Microsoft [](records-management.md) 365 のレコード管理機能を使用すると、サードパーティのデータをレコードとして宣言できます。 これは、メールボックス内のサードパーティ データをレコードとしてマークする保持ラベルを適用するユーザーが手動で行うことができます。 また、サードパーティデータ内の機密情報、キーワード、またはコンテンツ タイプを識別することで、保持ラベルを自動適用することもできます。

### <a name="communication-compliance"></a>コミュニケーション コンプライアンス

通信コンプライアンス [を使用すると](communication-compliance.md) 、サード パーティのデータを調べて、それが組織のデータ標準に準拠しているか確認できます。 これを行うには、組織内の不適切なメッセージを検出、キャプチャ、および修復アクションを実行します。 たとえば、攻撃的な言葉、機密情報、規制遵守のためにインポートするサード パーティのデータを監視できます。

### <a name="insider-risk-management"></a>インサイダー リスクの管理

インサイダー リスク管理ソリューションでは、選択的な人事データなどのサード パーティデータ[](insider-risk-management.md)からのシグナルを使用して、組織内のリスクの高いアクティビティを検出、調査、および処理することで内部リスクを最小限に抑えるために使用できます。 たとえば、人事データ コネクタによってインポートされたデータは、従業員データの盗難を検出するのに役立つリスク インジケーターとして使用されます。

## <a name="working-with-a-microsoft-partner-to-archive-third-party-data"></a>Microsoft パートナーと提携してサード パーティのデータをアーカイブする

サード パーティのデータをインポートおよびアーカイブするもう 1 つのオプションは、組織が Microsoft パートナーと一緒に作業する方法です。 Microsoft コンプライアンス センターで利用可能なデータ コネクタでサード パーティのデータ型がサポートされていない場合は、サード パーティのデータ ソースからアイテムを定期的に抽出するように構成されるカスタム コネクタを提供できるパートナーと作業し、サード パーティの API で Microsoft クラウドに接続し、それらのアイテムを Microsoft 365 にインポートできます。 パートナー コネクタは、アイテムのコンテンツをサード パーティのデータ ソースから電子メール メッセージに変換し、Microsoft 365 のメールボックスにインポートします。

使用できるパートナーの一覧と、この方法の手順については、「パートナーと協力して [Microsoft 365](work-with-partner-to-archive-third-party-data.md)のサード パーティデータをアーカイブする」を参照してください。
