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
ms.openlocfilehash: 70e01994c69d838693eaf453005a829d99f2cc4e
ms.sourcegitcommit: 8db88004f4c015138b20c55095ada2c0c79e5910
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2021
ms.locfileid: "58928730"
---
# <a name="archive-third-party-data-in-microsoft-365"></a>サードパーティのデータをアーカイブMicrosoft 365

Microsoft 365を使用すると、管理者はデータ コネクタを使用して、ソーシャル メディア プラットフォーム、インスタント メッセージング プラットフォーム、ドキュメント コラボレーション プラットフォームから、Microsoft 365 組織内のメールボックスにサードパーティのデータをインポートおよびアーカイブできます。 Microsoft 365 でデータ コネクタを使用してサード パーティ製のデータをインポートおよびアーカイブする主な利点の 1 つは、インポート後にさまざまな Microsoft 365 コンプライアンス ソリューションを適用できる点です。 これにより、組織の Microsoft 以外のデータが、組織に影響を与える規制と標準に準拠しているのを確認できます。

## <a name="third-party-data-connectors"></a>サードパーティのデータ コネクタ

このMicrosoft 365 コンプライアンス センターは、Microsoft からネイティブのサード パーティ 製データ コネクタを提供し、LinkedIn、Instant Bloomberg、Insider リスク管理ソリューションをサポートする Twitter やデータ コネクタなど、さまざまなデータ ソースからデータをインポートします。 Microsoft は、これらのデータ コネクタに加えて、次のパートナーと連携して、データ コネクタにさらに多くのサード パーツ データ コネクタを提供Microsoft 365 コンプライアンス センター。 組織は、これらのパートナーと連携してアーカイブ サービスをセットアップしてから、対応するデータ コネクタを作成Microsoft 365 コンプライアンス センター。

- [Veritas](#veritas-data-connectors)

- [TeleMessage](#telemessage-data-connectors)

- [17a-4 LLC](#17a-4-data-connectors)

- [CellTrust](#celltrust-data-connectors)

次のセクションに記載されているサード パーティのデータ (Microsoft 365 Insider リスク管理ソリューションに使用される人事データと物理的な不良データを除く) は、ユーザー メールボックスにインポートされます。 サード Microsoft 365をサポートするコンプライアンス ソリューションは、データが格納されているユーザー メールボックスに適用されます。

### <a name="microsoft-data-connectors"></a>Microsoft データ コネクタ

次の表に、アプリケーションで使用できるネイティブのサード パーティ製データ コネクタMicrosoft 365 コンプライアンス センター。 また、この表では、サードパーティのデータをインポートおよびアーカイブした後に適用できるコンプライアンス ソリューションMicrosoft 365。 各コンプライアンス [ソリューションの](#overview-of-compliance-solutions-that-support-third-party-data) 詳細と、サード パーティデータのサポート方法の詳細については、「サードパーティ データをサポートするコンプライアンス ソリューションの概要」セクションを参照してください。

[サード パーティ製データ] **列** のリンクをクリックして、そのデータ型のコネクタを作成するための手順を実行します。

|サードパーティのデータ  |訴訟ホールド|電子情報開示  |保持設定  |レコード管理  |コミュニケーション コンプライアンス  |インサイダー リスクの管理  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Bloomberg メッセージ](archive-bloomberg-message-data.md)     |![チェック マーク。](../media/checkmark.png)|![チェック マーク。](../media/checkmark.png)|![チェック マーク。](../media/checkmark.png)|![チェック マーク。](../media/checkmark.png)|![チェック マーク。](../media/checkmark.png)||
|[Facebook](archive-facebook-data-with-sample-connector.md)     |![チェック マーク。](../media/checkmark.png)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[人事 (HR)](import-hr-data.md) ||||||![チェック マーク](../media/checkmark.png)
|[IceChat](archive-icechat-data.md)     |![チェック マーク。](../media/checkmark.png)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Instant Bloomberg](archive-instant-bloomberg-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[LinkedIn](archive-linkedin-data.md)   |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[物理バッド](import-physical-badging-data.md) ||||||![チェック マーク](../media/checkmark.png)|
|[Twitter](archive-twitter-data-with-sample-connector.md)     |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
||||||||

### <a name="veritas-data-connectors"></a>Veritas データ コネクタ

このセクションの表は、Veritas と提携して利用できるサードパーティのデータ コネクタの一覧です。 また、この表では、サードパーティのデータをインポートしてアーカイブした後に、サードパーティのデータに適用できるコンプライアンス ソリューションMicrosoft 365。 各コンプライアンス [ソリューションの](#overview-of-compliance-solutions-that-support-third-party-data) 詳細と、サード パーティデータのサポート方法の詳細については、「サードパーティ データをサポートするコンプライアンス ソリューションの概要」セクションを参照してください。

Microsoft 365 でサード パーティ製のデータをアーカイブする前に、Veritas と一緒に組織のアーカイブ サービス *(Merge1)* をセットアップする必要があります。 詳細については、[サード パーティ製データ]列のリンクをクリックして、そのデータ型のコネクタを作成するための手順を実行します。

|サードパーティのデータ  |訴訟ホールド|電子情報開示  |保持設定  |レコード管理  |コミュニケーション コンプライアンス  |インサイダー リスクの管理  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[CellTrust](archive-celltrust-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[MS SQL 上の Cisco Jabber](archive-ciscojabberonmssql-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Oracle 上の Cisco Jabber](archive-ciscojabberonoracle-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[PostgreSQL 上の Cisco Jabber](archive-ciscojabberonpostgresql-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[EML](archive-eml-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[FX 接続](archive-fxconnect-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Jive](archive-jive-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[MS SQL Database](archive-mssqldatabaseimporter-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[Pivot](archive-pivot-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Redtail Speak](archive-redtailspeak-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Reuters Dealing](archive-reutersdealing-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Reuters Eikon](archive-reuterseikon-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Reuters FX](archive-reutersfx-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[RingCentral](archive-ringcentral-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[Salesforce Chatter](archive-salesforcechatter-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[ServiceNow](archive-servicenow-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[Skype for Business](archive-skypeforbusiness-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[Slack eDiscovery](archive-slack-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Symphony](archive-symphony-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[区切られたテキスト](archive-text-delimited-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[Webex チーム](archive-webexteams-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Web ページ](archive-webpagecapture-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[Facebookからの職場](archive-workplacefromfacebook-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[XIP](archive-xip-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[XSLT/XML](archive-xslt-xml-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[Yieldbroker](archive-yieldbroker-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Zoom会議](archive-zoommeetings-data.md)     |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
||||||||

### <a name="telemessage-data-connectors"></a>TeleMessage データコネクタ

このセクションの表は、TeleMessage と提携して利用できるサードパーティのデータ コネクタの一覧です。 また、この表では、サードパーティのデータをインポートしてアーカイブした後に、サードパーティのデータに適用できるコンプライアンス ソリューションMicrosoft 365。 各コンプライアンス [ソリューションの](#overview-of-compliance-solutions-that-support-third-party-data) 詳細と、サード パーティデータのサポート方法の詳細については、「サードパーティ データをサポートするコンプライアンス ソリューションの概要」セクションを参照してください。

サード パーティのデータを Microsoft 365にアーカイブするには、その前に TeleMessage を使用して組織のアーカイブ サービスをセットアップする必要があります。 詳細については、[サード パーティ製データ]列のリンクをクリックして、そのデータ型のコネクタを作成するための手順を実行します。

TeleMessage データ コネクタは、米国政府機関クラウドGCC環境でもMicrosoft 365利用できます。 詳細については、この記事の「 [米国政府機関クラウドの](#data-connectors-in-the-us-government-cloud) データ コネクタ」セクションを参照してください。

|サードパーティのデータ  |訴訟ホールド|電子情報開示  |保持設定  |レコード管理  |コミュニケーション コンプライアンス  |インサイダー リスクの管理  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Android](archive-android-archiver-data.md)     |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[AT&T ネットワーク](archive-att-network-archiver-data.md)     |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Bell ネットワーク](archive-bell-network-data.md)     |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[エンタープライズ番号](archive-enterprise-number-data.md)     |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[O2 ネットワーク](archive-o2-network-data.md)     |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[ロジャーズ ネットワーク](archive-rogers-network-archiver-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Signal](archive-signal-archiver-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[テレグラム](archive-telegram-archiver-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[TELUS ネットワーク](archive-telus-network-data.md)    |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Verizon ネットワーク](archive-verizon-network-data.md)     |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[WeChat](archive-wechat-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[WhatsApp](archive-whatsapp-data.md)     |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
||||||||

### <a name="17a-4-data-connectors"></a>17a-4 データ コネクタ

このセクションの表に、17a-4 LLC と提携して利用できるサードパーティのデータ コネクタを示します。 また、この表では、サードパーティのデータをインポートしてアーカイブした後に、サードパーティのデータに適用できるコンプライアンス ソリューションMicrosoft 365。 各コンプライアンス [ソリューションの](#overview-of-compliance-solutions-that-support-third-party-data) 詳細と、サード パーティデータのサポート方法の詳細については、「サードパーティ データをサポートするコンプライアンス ソリューションの概要」セクションを参照してください。

Microsoft 365 でサード パーティのデータをアーカイブするには、17a-4 LLC を使用して組織のアーカイブ サービス *(DataParser* と呼ばれる) をセットアップする必要があります。 詳細については、[サード パーティ製データ]列のリンクをクリックして、そのデータ型のコネクタを作成するための手順を実行します。

|サードパーティのデータ  |訴訟ホールド|電子情報開示  |保持設定  |レコード管理  |コミュニケーション コンプライアンス  |インサイダー リスクの管理  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[BlackBerry](archive-17a-4-blackberry-data.md)     |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[ブルームバーグ](archive-17a-4-bloomberg-data.md)     |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Cisco Jabber](archive-17a-4-cisco-jabber-data.md)   |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Cisco Webex](archive-17a-4-webex-teams-data.md)   |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[FactSet](archive-17a-4-factset-data.md)    |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Fuze](archive-17a-4-fuze-data.md)    |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[FX 接続](archive-17a-4-fxconnect-data.md)    |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[IceChat](archive-17a-4-ice-im-data.md)    |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[InvestEdge](archive-17a-4-investedge-data.md)    |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[LivePerson Conversational Cloud](archive-17a-4-liveperson-data.md)    |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Quip](archive-17a-4-quip-data.md)    |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Refinitiv Eikon Messenger](archive-17a-4-refinitiv-messenger-data.md)    |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[ServiceNow](archive-17a-4-servicenow-data.md)    |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
[Skype for Business Server](archive-17a-4-skype-for-business-server-data.md)    |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[余裕期間](archive-17a-4-slack-data.md)    |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[SQL](archive-17a-4-sql-database-data.md)    |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Symphony](archive-17a-4-symphony-data.md)    |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Zoom](archive-17a-4-zoom-data.md)    |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
||||||||

### <a name="celltrust-data-connectors"></a>CellTrust データ コネクタ

このセクションの表に、CellTrust と提携して利用できるサード パーティ製データ コネクタの一覧を示します。 また、この表では、サードパーティのデータをインポートしてアーカイブした後に、サードパーティのデータに適用できるコンプライアンス ソリューションMicrosoft 365。 各コンプライアンス [ソリューションの](#overview-of-compliance-solutions-that-support-third-party-data) 詳細と、サード パーティデータのサポート方法の詳細については、「サードパーティ データをサポートするコンプライアンス ソリューションの概要」セクションを参照してください。

Microsoft 365 でサード パーティのデータをアーカイブする前に、CellTrust を使用して組織のアーカイブ サービス *(CellTrust SL2* と呼ばれる) をセットアップする必要があります。 詳細については、[サード パーティ製データ]列のリンクをクリックして、CellTrust SL2 コネクタを作成するための手順を実行します。

|サードパーティのデータ  |訴訟ホールド|電子情報開示  |保持設定  |レコード管理  |コミュニケーション コンプライアンス  |インサイダー リスクの管理  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[CellTrust SL2](archive-data-from-celltrustsl2.md)     |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
||||||||

CellTrust SL2 データ コネクタは、米国政府機関クラウドGCC環境Microsoft 365でも利用できます。 詳細については、この記事の「 [米国政府機関クラウドの](#data-connectors-in-the-us-government-cloud) データ コネクタ」セクションを参照してください。

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

## <a name="using-ediscovery-tools-to-search-for-third-party-data"></a>電子情報開示ツールを使用してサードパーティのデータを検索する

データ コネクタを使用してユーザー メールボックス内のサード パーティ 製データをインポートおよびアーカイブした後、Microsoft 365 電子情報開示ツールを使用してサード パーティのデータを検索できます。 また、電子情報開示ツールを使用して、Core eDiscovery に関連付けられたクエリ ベースの保持を作成し、Advanced eDiscoveryのケースに関連付け、サード パーティのデータを保持することもできます。 電子情報開示ツールの詳細については、「電子情報開示ソリューション」を参照[Microsoft 365。](ediscovery.md)

データ コネクタを使用してユーザー メールボックスにインポートした任意の種類のサードパーティ データを検索 (または保留) するには、次の検索クエリを使用できます。 検索の範囲をユーザー メールボックスに設定してください。

```powershell
kind:externaldata
```

このクエリは、コンテンツ検索、Core 電子情報開示ケースに関連付けられた検索、またはコンテンツ 内のコレクションの [キーワード] ボックスでAdvanced eDiscovery。 

![サードパーティのデータを検索するクエリ。](..\media\SearchThirdPartyData1.png)

また、property:value ペアを使用して、検索範囲をサードパーティのデータ `kind:externaldata` に絞り込む場合にも使用できます。 たとえば、インポートしたアイテムの **Subject** プロパティに *contoso* という単語を含むサードパーティのデータ ソースからインポートされたアイテムを検索するには、[キーワード] ボックスで次のクエリ **を使用** します。

```powershell
subject:contoso AND kind:externaldata
```

または、[メッセージの種類] 条件 **を使用して** 同じクエリを構成することもできます。

![[メッセージの種類] 条件を使用して、サード パーティのデータに検索を絞り込む。](..\media\SearchThirdPartyData2.png)

アーカイブされたサード パーティの特定の種類のデータを検索するには、検索クエリで **itemclass** メールボックス プロパティを使用します。 次のプロパティ:値の形式を使用します。

```powershell
itemclass:ipm.externaldata.<third-party data type>
```

サード パーティのデータ コネクタによってインポートされたアイテムには、サード パーティのデータ型に対応する値を持つ **itemclass** プロパティが含まれます。 たとえば、インポートしたアイテムの Subject プロパティで *contoso* という単語を含む Facebook データを検索するには、次のクエリを使用します。

```powershell
subject:contoso AND itemclass:ipm.externaldata.facebook*
```

さまざまな種類のサード パーティ製データ **のアイテム** クラス値の例を次に示します。

| **サード パーティ製のデータ型** | **itemclass プロパティの値**   |
|---------------------------|-------------------------------------|
| Bloomberg メッセージ         | ipm.externaldata.bloombergmessage* |
| CellTrust                 | ipm.externaldata.celltrust*        |
| ピボット                     | ipm.externaldata.pivot*            |
| WhatsApp Archiver         | ipm.externaldata.whatsapparchiver* |
|||

*itemclass プロパティの値* では、大文字と小文字は区別されません。 一般に、サード パーティのデータ型の名前 (スペースなし) の後にワイルドカード ( * ) 文字を使用します。

電子情報開示検索クエリの作成の詳細については、「電子情報開示のキーワード クエリと [検索条件」を参照してください](keyword-queries-and-search-conditions.md)。

## <a name="data-connectors-in-the-us-government-cloud"></a>米国政府機関クラウドのデータ コネクタ

一部のデータ コネクタは、米国政府機関クラウドで利用できます。 次のセクションでは、サードパーティのデータ コネクタをサポートする特定の政府機関環境を示します。 米国政府機関のクラウドの詳細については、「米国政府機関Microsoft 365[を参照してください](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/microsoft-365-government-how-to-buy)。

### <a name="telemessage-data-connectors"></a>Telemessage データ コネクタ

|データ コネクタ  |GCC  |GCC High  |DoD  |
|:---------|:---------|:---------|:---------|
|Android Archiver | はい | いいえ | いいえ |
|AT&T SMS/MMS Network Archiver | はい | いいえ | いいえ |
|Bell SMS/MMS Network Archiver | はい | いいえ | いいえ |
|Enterprise Number Archiver | はい | いいえ | いいえ |
|O2 SMS と Voice Network Archiver | はい         | いいえ | いいえ |
|Signal Archiver | はい | いいえ | いいえ |
|Telegram Archiver | はい | いいえ | いいえ |
|TELUS SMS ネットワーク アーカイブ | はい | いいえ | いいえ |
|Verizon SMS/MMS Network Archiver | はい | いいえ | いいえ |
|WeChat Archiver | はい | いいえ | いいえ |
|WhatsApp Archiver | はい | いいえ | いいえ |
|||||

### <a name="celltrust-data-connectors"></a>CellTrust データ コネクタ

|データ コネクタ  |GCC  |GCC High  |DoD  |
|:---------|:---------|:---------|:---------|
|CellTrust SL2 | はい | いいえ | いいえ |
|||||

## <a name="working-with-a-microsoft-partner-to-archive-third-party-data"></a>Microsoft パートナーと作業してサード パーティのデータをアーカイブする

サードパーティのデータをインポートおよびアーカイブするもう 1 つのオプションは、組織が Microsoft パートナーと作業することです。 Microsoft コンプライアンス センターで使用できるデータ コネクタでサード パーティのデータ型がサポートされていない場合は、サードパーティのデータ ソースからアイテムを定期的に抽出し、サード パーティ製 API によって Microsoft クラウドに接続し、それらのアイテムを Microsoft 365 にインポートするように構成されるカスタム コネクタを提供できるパートナーと作業できます。 パートナー コネクタは、アイテムのコンテンツをサード パーティのデータ ソースから電子メール メッセージに変換し、そのアイテムをメール メッセージにMicrosoft 365。

使用できるパートナーの一覧と、このメソッドのステップ バイ ステップ プロセスについては、「パートナーと協力して、Microsoft 365 でサード パーティのデータをアーカイブする」[を参照してください](work-with-partner-to-archive-third-party-data.md)。
