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
description: ソーシャル メディア プラットフォーム、インスタント メッセージング プラットフォーム、ドキュメント コラボレーション プラットフォームからサードパーティ のデータを、ユーザーのメールボックスにインポートするMicrosoft 365します。
ms.openlocfilehash: a51b298b934431a1be8a416dac1f831ddaca5ffe
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861205"
---
# <a name="archive-third-party-data"></a>サード パーティのデータをアーカイブする

Microsoft 365を使用すると、管理者はデータ コネクタを使用して、ソーシャル メディア プラットフォーム、インスタント メッセージング プラットフォーム、ドキュメント コラボレーション プラットフォームから、Microsoft 365 組織内のメールボックスにサードパーティのデータをインポートおよびアーカイブできます。 Microsoft 365 でデータ コネクタを使用してサード パーティ製のデータをインポートおよびアーカイブする主な利点の 1 つは、インポート後にさまざまな Microsoft 365 コンプライアンス ソリューションを適用できる点です。 これにより、組織の Microsoft 以外のデータが、組織に影響を与える規制と標準に準拠しているのを確認できます。

## <a name="third-party-data-connectors"></a>サードパーティのデータ コネクタ

次の表に、コンプライアンス センターで使用できるサード パーティMicrosoft 365示します。 また、この表では、サードパーティのデータをインポートおよびアーカイブした後に、サードパーティのデータに適用できるコンプライアンス ソリューションMicrosoft 365。 各コンプライアンス [ソリューションの詳細](#overview-of-compliance-solutions-that-support-third-party-data) と、サード パーティのデータに対するメリットの詳細については、次のセクションを参照してください。

> [!TIP]
> [サード パーティ製データ] **列** のリンクをクリックして、そのデータ型のコネクタを作成するための手順を実行します。

|サードパーティのデータ  |訴訟ホールド|電子情報開示  |保持設定  |レコード管理  |コミュニケーション コンプライアンス  |インサイダー リスクの管理  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Android <sup>1</sup>](archive-android-archiver-data.md)     |![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[AT&T ネットワーク <sup>1</sup>](archive-att-network-archiver-data.md)     |![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Bell Network <sup>1</sup>](archive-bell-network-data.md)     |![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Bloomberg メッセージ](archive-bloomberg-message-data.md)     |![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[CellTrust <sup>2</sup>](archive-celltrust-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Cisco Jabber on MS SQL <sup>2</sup>](archive-ciscojabberonmssql-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Cisco Jabber on Oracle <sup>2</sup>](archive-ciscojabberonoracle-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[PostgreSQL <sup>2</sup>の Cisco Jabber](archive-ciscojabberonpostgresql-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[EML <sup>2</sup>](archive-eml-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[Enterprise番号<sup>1</sup>](archive-enterprise-number-data.md)     |![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Facebook](archive-facebook-data-with-sample-connector.md)     |![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[FX Connect <sup>2</sup>](archive-fxconnect-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[人事 (HR)](import-hr-data.md) ||||||![チェック マーク](../media/checkmark.png)
|[IceChat](archive-icechat-data.md)     |![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Instant Bloomberg](archive-instant-bloomberg-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Jive <sup>2</sup>](archive-jive-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[LinkedIn](archive-linkedin-data.md)   |![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[MS SQL Database <sup>2</sup>](archive-mssqldatabaseimporter-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[O2 ネットワーク <sup>1</sup>](archive-o2-network-data.md)     |![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[物理バッド](import-physical-badging-data.md) ||||||![チェック マーク](../media/checkmark.png)|
|[ピボット <sup>2</sup>](archive-pivot-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Redtail Speak <sup>2</sup>](archive-redtailspeak-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[ロイターの取引 <sup>2</sup>](archive-reutersdealing-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[ロイター Eikon <sup>2</sup>](archive-reuterseikon-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[ロイター FX <sup>2</sup>](archive-reutersfx-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Salesforce Chatter <sup>2</sup>](archive-salesforcechatter-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[ServiceNow <sup>2</sup>](archive-servicenow-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[Slack 電子情報開示 <sup>2</sup>](archive-slack-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[シンフォ <sup>ニー 2</sup>](archive-symphony-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[TELUS ネットワーク <sup>1</sup>](archive-telus-network-data.md)    |![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[テキストで区切られた <sup>2</sup>](archive-text-delimited-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[Twitter](archive-twitter-data-with-sample-connector.md)     |![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[Verizon Network <sup>1</sup>](archive-verizon-network-data.md)     |![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Webex Teams <sup>2</sup>](archive-webexteams-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Web ページ <sup>2</sup>](archive-webpagecapture-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[WeChat <sup>1</sup>](archive-wechat-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[WhatsApp <sup>1</sup>](archive-whatsapp-data.md)     |![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Facebook <sup>2 からの</sup>Workplace](archive-workplacefromfacebook-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[XIP <sup>2</sup>](archive-xip-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[XSLT/XML <sup>2</sup>](archive-xslt-xml-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[Yieldbroker <sup>2</sup>](archive-yieldbroker-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Zoom Meetings <sup>2</sup>](archive-zoommeetings-data.md)     |![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
||||||||

> [!NOTE]
> <sup>1</sup> TeleMessage によって提供されるデータ コネクタ。 データをアーカイブする前Microsoft 365、組織のアーカイブ サービスをセットアップするには、TeleMessage を使用する必要があります。 詳細については、このデータ型の手順の「前提条件」セクションを参照してください。 TeleMessage データ コネクタは、米国政府機関クラウドGCC環境でもMicrosoft 365利用できます。 詳細については、この記事の「 [米国政府機関クラウドの](#data-connectors-in-the-us-government-cloud) データ コネクタ」セクションを参照してください。 <br/><br/><sup>2</sup> Veritas が提供するデータ コネクタ。 データをアーカイブする前に、Microsoft 365 Veritas を使用して組織のアーカイブ サービスをセットアップする必要があります。 詳細については、このデータ型の手順の「前提条件」セクションを参照してください。

前の表にリストされているサード パーティのデータ (HR データと物理的な不良データを除く) は、ユーザー メールボックスにインポートされます。 サード パーティのデータをサポートする対応するコンプライアンス ソリューションは、データが格納されているユーザー メールボックスに適用されます。

## <a name="overview-of-compliance-solutions-that-support-third-party-data"></a>サードパーティのデータをサポートするコンプライアンス ソリューションの概要

以下のセクションでは、コンプライアンス ソリューションMicrosoft 365前の表に示したサード パーティのデータを管理するのに役立ついくつかの点について説明します。

### <a name="litigation-hold"></a>訴訟ホールド

ユーザー メールボックスに [訴訟ホールドを](create-a-litigation-hold.md) 設定して、サード パーティのデータを保持します。 保留リストを作成する場合は、保持期間 (時間ベースの *保持とも呼* ばれる) を指定して、削除および変更されたサード パーティのデータが指定した期間保持され、メールボックスから完全に削除されます。 または、コンテンツを無期限 (無限保留と呼 *ばれる)* に保持するか、訴訟ホールドが削除されるまで保持できます。

### <a name="ediscovery"></a>電子情報開示

コンテンツ検索、コア電子情報開示、Microsoft 365の 3 つの主要な電子情報開示Advanced eDiscovery。

- **[コンテンツ検索](content-search.md)。** コンテンツ検索ツールを使用して、インポートしたサード パーティデータのメールボックスを検索できます。 検索クエリと条件を使用して検索結果を絞り込み、検索結果をエクスポートできます。

- **[Core eDiscovery](get-started-core-ediscovery.md).** このツールは、ケース データへのアクセス、ユーザー メールボックスの保持、または検索条件に一致するメールボックス コンテンツの保持を制御できるケースを作成することで、基本的な検索およびエクスポート機能に基づいて構築されます。 つまり、ユーザー のメールボックスにインポートされたサード パーティのデータに電子情報開示ホールドを配置できます。

- **[Advanced eDiscovery](overview-ediscovery-20.md).** この強力なツールは、ケースにカストディアンを追加し、保管担当者のデータを保留にし、その後、カストディアンのサードパーティ データをレビューに読み込み、テーマや重複検出などの詳細な分析を行って、Core eDiscovery のケース機能を拡張します。 サード パーティ製のデータをレビュー セットに読み込むと、クエリを実行して絞り込み結果セットにフィルター処理できます。

   Core eDiscovery と Advanced eDiscovery、組織の法的または内部調査に関連する可能性のあるサード パーティのデータを管理できます。

### <a name="retention-settings"></a>保持設定

ユーザー メールボックスに [アイテム保持](retention.md) ポリシーを適用して、保持期間の有効期限が切れた後にサード パーティのデータ (および他のメールボックス コンテンツ) を保持および削除できます。 また、保持ポリシーを使用して、特定の年齢のサード パーティ データを[](disposition.md)削除したり、保持ラベルを使用して、サード パーティ データの保持期間が経過した場合に廃棄レビューをトリガーすることもできます。

### <a name="records-management"></a>レコード管理

この[ページの](records-management.md)レコード管理機能Microsoft 365、サード パーティのデータをレコードとして宣言できます。 これは、メールボックス内のサードパーティ データをレコードとしてマークするアイテム保持ラベルを適用するユーザーが手動で行うことができます。 または、サードパーティ データ内の機密情報、キーワード、またはコンテンツ タイプを識別して、保持ラベルを自動適用することもできます。

### <a name="communication-compliance"></a>コミュニケーション コンプライアンス

コミュニケーション コンプライアンスを [使用して](communication-compliance.md) 、サード パーティのデータを調べて、組織のデータ標準に準拠しているか確認できます。 これを行うには、組織内の不適切なメッセージを検出、キャプチャ、および修復アクションを実行します。 たとえば、インポートするサード パーティのデータを監視して、不快な言語、機密情報、規制遵守を確認できます。

### <a name="insider-risk-management"></a>インサイダー リスクの管理

選択的な人事データなど、サード パーティのデータからのシグナルを Insider リスク[](insider-risk-management.md)管理ソリューションで使用すると、組織内のリスクの高いアクティビティを検出、調査、および操作することで内部リスクを最小限に抑える可能性があります。 たとえば、人事データ コネクタによってインポートされたデータは、従業員のデータ盗難を検出するリスクインジケーターとして使用されます。

## <a name="data-connectors-in-the-us-government-cloud"></a>米国政府機関クラウドのデータ コネクタ

前述したように、TeleMessage によって提供されるデータ コネクタは、米国政府機関のクラウドで利用できます。 次の表は、各 TeleMessage データ コネクタをサポートする特定の政府機関環境を示しています。 米国政府機関のクラウドの詳細については、「米国政府機関Microsoft 365[を参照してください](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/microsoft-365-government-how-to-buy)。

|TeleMessage データ コネクタ  |GCC  |GCC High  |DoD  |
|:---------|:---------|:---------|:---------|
|Android Archiver | はい | いいえ | いいえ |
|AT&T 携帯ショートメール/MMS ネットワーク アーカイブ | はい | いいえ | いいえ |
|Bell 携帯ショートメール/MMS ネットワーク アーカイブ | はい | いいえ | いいえ |
|EnterpriseNumber Archiver | はい | いいえ | いいえ |
|O2 携帯ショートメールおよび音声ネットワーク アーカイブ | はい         | いいえ | いいえ |
|TELUS 携帯ショートメール ネットワーク アーカイブ | はい | いいえ | いいえ |
|Verizon 携帯ショートメール/MMS ネットワーク アーカイブ | はい | いいえ | いいえ |
|WeChat Archiver | はい | いいえ | いいえ |
|WhatsApp Archiver | はい | いいえ | いいえ |
|||||

## <a name="working-with-a-microsoft-partner-to-archive-third-party-data"></a>Microsoft パートナーと作業してサード パーティのデータをアーカイブする

サードパーティのデータをインポートおよびアーカイブするもう 1 つのオプションは、組織が Microsoft パートナーと作業することです。 Microsoft コンプライアンス センターで使用できるデータ コネクタでサード パーティのデータ型がサポートされていない場合は、サードパーティのデータ ソースからアイテムを定期的に抽出し、サード パーティ製 API によって Microsoft クラウドに接続し、それらのアイテムを Microsoft 365 にインポートするように構成されるカスタム コネクタを提供できるパートナーと作業できます。 パートナー コネクタは、アイテムのコンテンツをサード パーティのデータ ソースから電子メール メッセージに変換し、そのアイテムをメール メッセージにMicrosoft 365。

使用できるパートナーの一覧と、このメソッドのステップ バイ ステップ プロセスについては、「パートナーと協力して、Microsoft 365 でサード パーティのデータをアーカイブする」[を参照してください](work-with-partner-to-archive-third-party-data.md)。
