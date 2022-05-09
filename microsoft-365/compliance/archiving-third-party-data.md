---
title: データ コネクタを使用して、Microsoft 365でサード パーティのデータをインポートおよびアーカイブする
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
ms.custom:
- seo-marvel-apr2020
description: ソーシャル メディア プラットフォーム、インスタント メッセージング プラットフォーム、ドキュメント コラボレーション プラットフォームからMicrosoft 365メールボックスにサード パーティのデータをインポートしてアーカイブする方法について説明します。
ms.openlocfilehash: 75a1136c38c0b893babd1cd349dbe34aa9bbf8cd
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65093572"
---
# <a name="learn-about-connectors-for-third-party-data"></a>サード パーティ データのコネクタの詳細

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft 365管理者は、データ コネクタを使用して、Microsoft 以外のサード パーティのデータをソーシャル メディア プラットフォーム、インスタント メッセージング プラットフォーム、ドキュメント コラボレーション プラットフォームから、Microsoft 365組織内のメールボックスにインポートおよびアーカイブできます。 データ コネクタを使用してMicrosoft 365でサード パーティのデータをインポートおよびアーカイブする主な利点の 1 つは、インポート後にさまざまな Microsoft Purview ソリューションをデータに適用できる点です。 これにより、組織の Microsoft 以外のデータが、組織に影響を与える規制と標準に準拠していることを確認できます。

サード パーティのデータをインポートおよびアーカイブするためのデータ コネクタを作成する方法と、Microsoft 365にインポートした後にデータにコンプライアンス ソリューションを適用する例を示すこの対話型ガイドをご覧ください。

> [!VIDEO https://mslearn.cloudguides.com/guides/Archive%20data%20from%20non-Microsoft%20sources%20in%20Microsoft%20365]

## <a name="third-party-data-connectors"></a>サードパーティのデータ コネクタ

Microsoft Purview コンプライアンス ポータルでは、Microsoft からネイティブサード パーティのデータ コネクタを提供し、LinkedIn、Instant Bloomberg、Twitter などのさまざまなデータ ソースからデータをインポートし、Insider リスク管理ソリューションをサポートするデータ コネクタを提供します。 これらのデータ コネクタに加えて、Microsoft は次のパートナーと協力して、コンプライアンス ポータルでさらに多くのサード パーツ データ コネクタを提供しています。 組織は、コンプライアンス ポータルで対応するデータ コネクタを作成する前に、これらのパートナーと協力してアーカイブ サービスを設定します。

- [Veritas](#veritas-data-connectors)

- [TeleMessage](#telemessage-data-connectors)

- [17a-4 LLC](#17a-4-data-connectors)

- [CellTrust](#celltrust-data-connectors)

次のセクションに記載されているサード パーティのデータ (Microsoft 365 Insider リスク管理ソリューションに使用される人事データと物理的な不正使用データを除く) は、ユーザー メールボックスにインポートされます。 サード パーティのデータをサポートする Microsoft Purview ソリューションは、データが格納されているユーザー メールボックスに適用されます。

### <a name="microsoft-data-connectors"></a>Microsoft データ コネクタ

次の表に、コンプライアンス ポータルで使用できるネイティブサード パーティのデータ コネクタを示します。 また、Microsoft 365でサード パーティのデータをインポートしてアーカイブした後に適用できるコンプライアンス ソリューションも表にまとめられています。 各コンプライアンス ソリューションの詳細な説明と [、サード パーティのデータをサポートする](#overview-of-compliance-solutions-that-support-third-party-data) 方法については、「サード パーティのデータをサポートするコンプライアンス ソリューションの概要」セクションを参照してください。

**サード パーティのデータ** 列のリンクをクリックして、そのデータ型のコネクタを作成するための詳細な手順に従います。

|サード パーティのデータ  |訴訟ホールド|電子情報開示  |アイテム保持設定  |レコード管理  |コミュニケーション コンプライアンス  |インサイダー リスクの管理  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Bloomberg メッセージ](archive-bloomberg-message-data.md)     |![チェック マーク。](../media/checkmark.png)|![チェック マーク。](../media/checkmark.png)|![チェック マーク。](../media/checkmark.png)|![チェック マーク。](../media/checkmark.png)|![チェック マーク。](../media/checkmark.png)||
|[エピック EHR ヘルスケア](import-epic-data.md) ||||||![チェック マーク](../media/checkmark.png)|
|[Facebook](archive-facebook-data-with-sample-connector.md)     |![チェック マーク。](../media/checkmark.png)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[汎用 EHR 医療](import-healthcare-data.md) ||||||![チェック マーク](../media/checkmark.png)|
|[人事 (HR)](import-hr-data.md) ||||||![チェック マーク](../media/checkmark.png)|
|[IceChat](archive-icechat-data.md)     |![チェック マーク。](../media/checkmark.png)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Instant Bloomberg](archive-instant-bloomberg-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[LinkedIn](archive-linkedin-data.md)   |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[物理的な不正プログラム](import-physical-badging-data.md) ||||||![チェック マーク](../media/checkmark.png)|
|[Slack eDiscovery](archive-slack-data-microsoft.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Twitter](archive-twitter-data-with-sample-connector.md)     |![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
||||||||

### <a name="veritas-data-connectors"></a>Veritas データ コネクタ

このセクションの表は、Veritas と連携して使用できるサード パーティ製のデータ コネクタの一覧です。 この表には、Microsoft 365にインポートしてアーカイブした後にサード パーティのデータに適用できるコンプライアンス ソリューションもまとめられています。 各コンプライアンス ソリューションの詳細な説明と [、サード パーティのデータをサポートする](#overview-of-compliance-solutions-that-support-third-party-data) 方法については、「サード パーティのデータをサポートするコンプライアンス ソリューションの概要」セクションを参照してください。

Microsoft 365でサード パーティのデータをアーカイブするには、Veritas と連携して組織のアーカイブ サービス (*Merge1* と呼ばれる) を設定する必要があります。 詳細については、 **サード パーティのデータ** 列のリンクをクリックして、そのデータ型のコネクタを作成するための詳細な手順に従います。

|サード パーティのデータ  |訴訟ホールド|電子情報開示  |アイテム保持設定  |レコード管理  |コミュニケーション コンプライアンス  |インサイダー リスクの管理  |
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
|[RingCentral](archive-ringcentral-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Salesforce Chatter](archive-salesforcechatter-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[ServiceNow](archive-servicenow-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[Skype for Business](archive-skypeforbusiness-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Slack eDiscovery](archive-slack-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Symphony](archive-symphony-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[区切られたテキスト](archive-text-delimited-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[Twitter](archive-veritas-twitter-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[Webex チーム](archive-webexteams-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Web ページ](archive-webpagecapture-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[Facebookからの職場](archive-workplacefromfacebook-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[XIP](archive-xip-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[XSLT/XML](archive-xslt-xml-data.md)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[Yieldbroker](archive-yieldbroker-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[YouTube](archive-youtube-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|||
|[Zoom会議](archive-zoommeetings-data.md)     |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
||||||||

### <a name="telemessage-data-connectors"></a>TeleMessage データコネクタ

このセクションの表では、TeleMessage と連携して使用できるサード パーティ製のデータ コネクタの一覧を示します。 この表には、Microsoft 365にインポートしてアーカイブした後にサード パーティのデータに適用できるコンプライアンス ソリューションもまとめられています。 各コンプライアンス ソリューションの詳細な説明と [、サード パーティのデータをサポートする](#overview-of-compliance-solutions-that-support-third-party-data) 方法については、「サード パーティのデータをサポートするコンプライアンス ソリューションの概要」セクションを参照してください。

Microsoft 365でサード パーティのデータをアーカイブするには、TeleMessage を使用して組織のアーカイブ サービスを設定する必要があります。 詳細については、 **サード パーティのデータ** 列のリンクをクリックして、そのデータ型のコネクタを作成するための詳細な手順に従います。

TeleMessage データ コネクタは、Microsoft 365米国政府機関クラウドのGCC環境でも使用できます。 詳細については、この記事の [「米国政府機関のクラウド」セクションのデータ コネクタ](#data-connectors-in-the-us-government-cloud) を参照してください。

|サード パーティのデータ  |訴訟ホールド|電子情報開示  |アイテム保持設定  |レコード管理  |コミュニケーション コンプライアンス  |インサイダー リスクの管理  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Android](archive-android-archiver-data.md)     |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[AT&T Network](archive-att-network-archiver-data.md)     |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Bell ネットワーク](archive-bell-network-data.md)     |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[エンタープライズ番号](archive-enterprise-number-data.md)     |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[O2 ネットワーク](archive-o2-network-data.md)     |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Rogers Network](archive-rogers-network-archiver-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[信号](archive-signal-archiver-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[電報](archive-telegram-archiver-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[TELUS ネットワーク](archive-telus-network-data.md)    |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Verizon ネットワーク](archive-verizon-network-data.md)     |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[WeChat](archive-wechat-data.md)|![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[WhatsApp](archive-whatsapp-data.md)     |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
||||||||

### <a name="17a-4-data-connectors"></a>17a-4 データ コネクタ

このセクションの表では、17a-4 LLC と連携して使用できるサード パーティ製データ コネクタの一覧を示します。 この表には、Microsoft 365にインポートしてアーカイブした後にサード パーティのデータに適用できるコンプライアンス ソリューションもまとめられています。 各コンプライアンス ソリューションの詳細な説明と [、サード パーティのデータをサポートする](#overview-of-compliance-solutions-that-support-third-party-data) 方法については、「サード パーティのデータをサポートするコンプライアンス ソリューションの概要」セクションを参照してください。

Microsoft 365でサード パーティのデータをアーカイブする前に、17a-4 LLC を使用して組織のアーカイブ サービス (*DataParser* と呼ばれる) を設定する必要があります。 詳細については、 **サード パーティのデータ** 列のリンクをクリックして、そのデータ型のコネクタを作成するための詳細な手順に従います。

17a-4 データ コネクタは、Microsoft 365米国政府機関クラウドのGCC環境でも使用できます。 詳細については、この記事の [「米国政府機関のクラウド」セクションのデータ コネクタ](#data-connectors-in-the-us-government-cloud) を参照してください。

|サード パーティのデータ  |訴訟ホールド|電子情報開示  |アイテム保持設定  |レコード管理  |コミュニケーション コンプライアンス  |インサイダー リスクの管理  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[BlackBerry](archive-17a-4-blackberry-data.md)     |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[ブルームバーグ](archive-17a-4-bloomberg-data.md)     |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Cisco Jabber](archive-17a-4-cisco-jabber-data.md)   |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Cisco Webex](archive-17a-4-webex-teams-data.md)   |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[FactSet](archive-17a-4-factset-data.md)    |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[信管](archive-17a-4-fuze-data.md)    |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[FX 接続](archive-17a-4-fxconnect-data.md)    |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[IceChat](archive-17a-4-ice-im-data.md)    |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[InvestEdge](archive-17a-4-investedge-data.md)    |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[LivePerson Conversational Cloud](archive-17a-4-liveperson-data.md)    |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[皮肉](archive-17a-4-quip-data.md)    |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Refinitiv Eikon Messenger](archive-17a-4-refinitiv-messenger-data.md)    |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[ServiceNow](archive-17a-4-servicenow-data.md)    |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
[Skype for Business Server](archive-17a-4-skype-for-business-server-data.md)    |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[余裕期間](archive-17a-4-slack-data.md)    |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[SQL](archive-17a-4-sql-database-data.md)    |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[Symphony](archive-17a-4-symphony-data.md)    |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
|[拡大](archive-17a-4-zoom-data.md)    |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
||||||||

### <a name="celltrust-data-connectors"></a>CellTrust データ コネクタ

このセクションの表に、CellTrust と連携して使用できるサード パーティ製データ コネクタの一覧を示します。 この表には、Microsoft 365にインポートしてアーカイブした後にサード パーティのデータに適用できるコンプライアンス ソリューションもまとめられています。 各コンプライアンス ソリューションの詳細な説明と [、サード パーティのデータをサポートする](#overview-of-compliance-solutions-that-support-third-party-data) 方法については、「サード パーティのデータをサポートするコンプライアンス ソリューションの概要」セクションを参照してください。

Microsoft 365でサード パーティのデータをアーカイブする前に、CellTrust と連携して組織のアーカイブ サービス (*CellTrust SL2* と呼ばれる) を設定する必要があります。 詳細については、 **サードパーティのデータ** 列のリンクをクリックして、CellTrust SL2 コネクタを作成するための詳細な手順を参照してください。

|サード パーティのデータ  |訴訟ホールド|電子情報開示  |アイテム保持設定  |レコード管理  |コミュニケーション コンプライアンス  |インサイダー リスクの管理  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[CellTrust SL2](archive-data-from-celltrustsl2.md)     |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
||||||||

CellTrust SL2 データ コネクタは、Microsoft 365米国政府機関クラウドのGCC環境でも使用できます。 詳細については、この記事の [「米国政府機関のクラウド」セクションのデータ コネクタ](#data-connectors-in-the-us-government-cloud) を参照してください。

## <a name="overview-of-compliance-solutions-that-support-third-party-data"></a>サード パーティのデータをサポートするコンプライアンス ソリューションの概要

次のセクションでは、Microsoft Purview ソリューションが前の表に示したサード パーティのデータを管理するのに役立ついくつかの点について説明します。

### <a name="litigation-hold"></a>訴訟ホールド

サード パーティのデータを保持するために、ユーザー メールボックスに [訴訟ホールド](create-a-litigation-hold.md) を置きます。 ホールドを作成するときに、保持期間 ( *時間ベースの保留* とも呼ばれます) を指定して、削除および変更されたサード パーティのデータが指定された期間保持され、メールボックスから完全に削除されるようにすることができます。 または、コンテンツを無期限に保持する ( *無限保留* と呼ばれる) か、訴訟ホールドが削除されるまで保持することもできます。

### <a name="ediscovery"></a>電子情報開示

Microsoft 365の 3 つの主要な電子情報開示ツールは、コンテンツ検索、Microsoft Purview 電子情報開示 (Standard)、および Microsoft Purview 電子情報開示 (プレミアム) です。

- **[コンテンツ検索](content-search.md)。** コンテンツ検索ツールを使用して、インポートしたサード パーティのデータをメールボックスで検索できます。 検索クエリと条件を使用して検索結果を絞り込み、検索結果をエクスポートできます。

- **[電子情報開示 (Standard)](get-started-core-ediscovery.md)。** このツールは、ケース データにアクセスできるユーザーを制御したり、検索条件に一致するユーザー メールボックスやメールボックスのコンテンツを保持したりできるようにするケースを作成できるようにすることで、基本的な検索とエクスポートの機能に基づいています。 つまり、ユーザー メールボックスにインポートされたサード パーティのデータに電子情報開示ホールドを配置できます。

- **[電子情報開示 (プレミアム)](overview-ediscovery-20.md)。** この強力なツールは、ケースにカストディアンを追加し、保管担当者のデータを保留にし、カストディアンのサードパーティデータをレビューに読み込んで、テーマや重複検出などの詳細な分析を行うことにより、電子情報開示 (Standard) のケース機能を拡張します。 サード パーティのデータをレビュー セットに読み込んだ後、絞り込み結果セットに対してクエリを実行してフィルター処理できます。

   電子情報開示 (Standard) と電子情報開示 (プレミアム) の両方を使用すると、組織の法的または内部調査に関連する可能性があるサード パーティのデータを管理できます。

### <a name="retention-settings"></a>アイテム保持設定

保持期間の有効期限が切れた後、ユーザー メールボックスに [アイテム保持ポリシー](retention.md) を適用して、サード パーティのデータ (およびその他のメールボックス コンテンツ) を保持して削除できます。 保持ポリシーを使用して、特定の年齢のサード パーティのデータを削除したり、 [保持ラベルを使用して](disposition.md) サード パーティのデータの保持期間が切れたときに廃棄レビューをトリガーしたりすることもできます。

### <a name="records-management"></a>レコード管理

Microsoft 365の[レコード管理機能](records-management.md)を使用すると、サード パーティのデータをレコードとして宣言できます。 これは、メールボックス内のサード パーティのデータをレコードとしてマークする保持ラベルを適用するユーザーが手動で行うことができます。 または、サードパーティのデータで機密情報、キーワード、またはコンテンツ タイプを識別することで、保持ラベルを自動適用することもできます。

### <a name="communication-compliance"></a>コミュニケーション コンプライアンス

[コミュニケーション コンプライアンス](communication-compliance.md)を使用して、サード パーティのデータを調べて、組織のデータ標準に準拠していることを確認できます。 これを行うには、組織内の不適切なメッセージの検出、キャプチャ、修復アクションを実行します。 たとえば、不適切な言語、機密情報、および規制コンプライアンスのためにインポートするサード パーティのデータを監視できます。

### <a name="insider-risk-management"></a>インサイダー リスクの管理

選択的人事データなどのサード パーティのデータからのシグナルは、 [Insider リスク管理](insider-risk-management.md) ソリューションで使用して、組織内の危険なアクティビティを検出、調査、および行動できるようにすることで内部リスクを最小限に抑えることができます。 たとえば、人事データ コネクタによってインポートされたデータは、従業員データ盗難の検出に役立つリスク インジケーターとして使用されます。

## <a name="using-ediscovery-tools-to-search-for-third-party-data"></a>電子情報開示ツールを使用してサード パーティのデータを検索する

データ コネクタを使用してユーザー メールボックス内のサード パーティのデータをインポートおよびアーカイブした後は、Microsoft 365電子情報開示ツールを使用してサード パーティのデータを検索できます。 また、電子情報開示ツールを使用して、電子情報開示 (Standard) ケースと電子情報開示 (プレミアム) ケースに関連付けられたクエリ ベースの保留を作成して、サード パーティのデータを保持することもできます。 電子情報開示ツールの詳細については、[Microsoft 365の電子情報開示ソリューションに](ediscovery.md)関するページを参照してください。

データ コネクタを使用してユーザー メールボックスにインポートした任意の種類のサード パーティデータを検索 (または保留) するには、次の検索クエリを使用します。 検索の範囲をユーザー メールボックスに設定してください。

```powershell
kind:externaldata
```

このクエリは、コンテンツ検索、電子情報開示 (Standard) ケースに関連付けられた検索、または電子情報開示 (プレミアム) のコレクションの **[キーワード**] ボックスで使用できます。

![サード パーティのデータを検索するクエリ。](..\media\SearchThirdPartyData1.png)

プロパティと値のペアを `kind:externaldata` 使用して、検索範囲をサード パーティのデータに絞り込むこともできます。 たとえば、インポートされたアイテムの **Subject** プロパティに *contoso* という単語を含むサード パーティのデータ ソースからインポートされたアイテムを検索するには、[**キーワード**] ボックスで次のクエリを使用します。

```powershell
subject:contoso AND kind:externaldata
```

または、 **メッセージの種類** 条件を使用して、同じクエリを構成することもできます。

![メッセージの種類の条件を使用して、サード パーティのデータに検索を絞り込みます。](..\media\SearchThirdPartyData2.png)

アーカイブされたサード パーティの特定の種類のデータを検索するには、検索クエリで **itemclass** メールボックス プロパティを使用します。 次のプロパティ:value 形式を使用します。

```powershell
itemclass:ipm.externaldata.<third-party data type>
```

サード パーティのデータ コネクタによってインポートされるすべての項目には、サード パーティのデータ型に対応する値を持つ **itemclass** プロパティが含まれています。 たとえば、 *contoso* という単語を含む Facebook データを検索するには、インポートされたアイテムの **Subject** プロパティで次のクエリを使用します。

```powershell
subject:contoso AND itemclass:ipm.externaldata.facebook*
```

さまざまな種類のサード パーティデータの **アイテムクラス** 値の例をいくつか次に示します。

| **サード パーティのデータ型** | **itemclass プロパティの値**   |
|---------------------------|-------------------------------------|
| Bloomberg メッセージ         | ipm.externaldata.bloombergmessage* |
| CellTrust                 | ipm.externaldata.celltrust*        |
| ピボット                     | ipm.externaldata.pivot*            |
| WhatsApp Archiver         | ipm.externaldata.whatsapparchiver* |
|||

*itemclass* プロパティの値では、大文字と小文字は区別されません。 一般に、サード パーティ製のデータ型の名前 (スペースなし) の後にワイルドカード ( * ) 文字を使用します。

電子情報開示検索クエリの作成の詳細については、「電子情報開示 [のキーワード クエリと検索条件」を参照](keyword-queries-and-search-conditions.md)してください。

## <a name="data-connectors-in-the-us-government-cloud"></a>米国政府機関クラウドのデータ コネクタ

一部のデータ コネクタは、米国政府機関のクラウドで使用できます。 次のセクションでは、サード パーティのデータ コネクタをサポートする特定の政府機関環境を示します。 米国政府機関クラウドの詳細については、「米国政府機関[Microsoft 365](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/microsoft-365-government-how-to-buy)」を参照してください。

### <a name="veritas-data-connectors-in-the-us-government-cloud-preview"></a>米国政府クラウドの Veritas データ コネクタ (プレビュー)

|データ コネクタ  |GCC  |GCC High  |DoD  |
|:---------|:---------|:---------|:---------|
|CellTrust| はい | いいえ | いいえ |
|MS SQL 上の Cisco Jabber| はい | いいえ | いいえ |
|Oracle 上の Cisco Jabber| はい | いいえ | いいえ |
|PostgreSQL 上の Cisco Jabber| はい | いいえ | いいえ |
|EML| はい | いいえ | いいえ |
|FX 接続| はい | いいえ | いいえ |
|Jive| はい | いいえ | いいえ |
|MS SQL Database| はい | いいえ | いいえ |
|ピボット| はい | いいえ | いいえ |
|Redtail Speak| はい | いいえ | いいえ |
|Reuters Dealing| はい | いいえ | いいえ |
|Reuters Eikon| はい | いいえ | いいえ |
|Reuters FX| はい | いいえ | いいえ |
|RingCentral| はい | いいえ | いいえ |
|Salesforce Chatter| はい | いいえ | いいえ |
|ServiceNow| はい | いいえ | いいえ |
|Skype for Business| はい | いいえ | いいえ |
|Slack eDiscovery| はい | いいえ | いいえ |
|Symphony| はい | いいえ | いいえ |
|区切られたテキスト| はい | いいえ | いいえ |
|Twitter| はい | いいえ | いいえ |
|Webex チーム| はい | いいえ | いいえ |
|Web ページ| はい | いいえ | いいえ |
|Facebookからの職場| はい | いいえ | いいえ |
|XIP| はい | いいえ | いいえ |
|XSLT/XML| はい | いいえ | いいえ |
|Yieldbroker| はい | いいえ | いいえ |
|YouTube| いいえ | いいえ | いいえ |
|Zoom会議| はい | いいえ | いいえ |
|||||

### <a name="telemessage-data-connectors-in-the-us-government-cloud"></a>米国政府クラウドの TeleMessage データ コネクタ

|データ コネクタ  |GCC  |GCC High  |DoD  |
|:---------|:---------|:---------|:---------|
|Android Archiver | はい | いいえ | いいえ |
|AT&T SMS/MMS Network Archiver | はい | いいえ | いいえ |
|Bell SMS/MMS Network Archiver | はい | いいえ | いいえ |
|Enterprise Number Archiver | はい | いいえ | いいえ |
|O2 SMS および Voice Network Archiver | はい         | いいえ | いいえ |
|Rogers Network Archiver | はい         | いいえ | いいえ |
|Signal Archiver | はい | いいえ | いいえ |
|Telegram Archiver | はい | いいえ | いいえ |
|TELUS SMS Network Archiver | はい | いいえ | いいえ |
|Verizon SMS/MMS Network Archiver | はい | いいえ | いいえ |
|WeChat Archiver | はい | いいえ | いいえ |
|WhatsApp Archiver | はい | いいえ | いいえ |
|||||

### <a name="17a-4-data-connectors-in-the-us-government-cloud"></a>米国政府機関クラウドの 17a-4 データ コネクタ

|データ コネクタ  |GCC  |GCC High  |DoD  |
|:---------|:---------|:---------|:---------|
|BlackBerry DataParser | はい | いいえ | いいえ |
|Bloomberg DataParser  | はい | いいえ | いいえ |
|Cisco Jabber DataParser  | はい | いいえ | いいえ |
|Cisco Webex DataParser  | はい | いいえ | いいえ |
|FactSet DataParser  | はい | いいえ | いいえ |
|Fuze DataParser  | はい | いいえ | いいえ |
|FX Connect DataParser  | はい | いいえ | いいえ |
|ICE DataParser  | はい | いいえ | いいえ |
|InvestEdge DataParser  | はい | いいえ | いいえ |
|LivePerson Conversational Cloud DataParser  | はい | いいえ | いいえ |
|Quip DataParser  | はい | いいえ | いいえ |
|Refinitiv Eikon Messenger DataParser  | はい | いいえ | いいえ |
|ServiceNow DataParser  | はい | いいえ | いいえ |
|Skype for Business Server DataParser | はい | いいえ | いいえ |
|Slack DataParser | はい | いいえ | いいえ |
|SQL DataParser  | はい | いいえ | いいえ |
|Symphony DataParser | はい | いいえ | いいえ |
|Zoom DataParser | はい | いいえ | いいえ |
|||||

### <a name="celltrust-data-connectors-in-the-us-government-cloud"></a>米国政府クラウドの CellTrust データ コネクタ

|データ コネクタ  |GCC  |GCC High  |DoD  |
|:---------|:---------|:---------|:---------|
|CellTrust SL2 | はい | いいえ | いいえ |
|||||

## <a name="working-with-a-microsoft-partner-to-archive-third-party-data"></a>Microsoft パートナーと協力してサード パーティのデータをアーカイブする

サード パーティのデータをインポートおよびアーカイブするためのもう 1 つのオプションは、組織が Microsoft パートナーと連携することです。 Microsoft コンプライアンス センターで使用できるデータ コネクタでサード パーティのデータ型がサポートされていない場合は、定期的にサード パーティのデータ ソースからアイテムを抽出し、サード パーティの API で Microsoft クラウドに接続し、それらの項目をMicrosoft 365にインポートするように構成されるカスタム コネクタを提供できるパートナーと連携できます。 また、パートナー コネクタは、アイテムのコンテンツをサード パーティのデータ ソースから電子メール メッセージに変換し、Microsoft 365のメールボックスにインポートします。

操作できるパートナーの一覧と、この方法のステップ バイ ステップ プロセスについては、「[パートナーと連携して、Microsoft 365でサード パーティのデータをアーカイブする](work-with-partner-to-archive-third-party-data.md)」を参照してください。
