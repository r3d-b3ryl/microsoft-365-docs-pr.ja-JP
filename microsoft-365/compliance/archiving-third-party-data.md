---
title: データ コネクタを使用して、Microsoft 365 でサード パーティのデータをインポートおよびアーカイブする
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
description: ソーシャル メディア プラットフォーム、インスタント メッセージング プラットフォーム、ドキュメント コラボレーション プラットフォームから Microsoft 365 メールボックスにサード パーティのデータをインポートしてアーカイブする方法について説明します。
ms.openlocfilehash: b27d45577b98c1eef0f3dab11412f048adff6bcd
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66637551"
---
# <a name="learn-about-connectors-for-third-party-data"></a>サード パーティ データのコネクタの詳細

Microsoft 365 を使用すると、管理者はソーシャル メディア プラットフォーム、インスタント メッセージング プラットフォーム、ドキュメント コラボレーション プラットフォームからのサードパーティ データを、Microsoft 365 組織のメールボックスにインポートしてアーカイブすることができます。 データ コネクタを使用して Microsoft 365 でサード パーティのデータをインポートおよびアーカイブする主な利点の 1 つは、インポート後にさまざまな Microsoft Purview ソリューションをデータに適用できることです。 これにより、組織の Microsoft 以外のデータが、組織に影響を与える規制と標準に準拠していることを確認できます。

この対話型ガイドでは、サード パーティのデータをインポートおよびアーカイブするためのデータ コネクタを作成する方法と、Microsoft 365 にインポートした後にデータにコンプライアンス ソリューションを適用する例について説明します。

> [!VIDEO https://mslearn.cloudguides.com/guides/Archive%20data%20from%20non-Microsoft%20sources%20in%20Microsoft%20365]

## <a name="third-party-data-connectors"></a>サードパーティのデータ コネクタ

このMicrosoft Purview コンプライアンス ポータルは、Microsoft からネイティブサード パーティのデータ コネクタを提供し、LinkedIn、Instant Bloomberg、Twitter、Insider リスク管理ソリューションをサポートするデータ コネクタなど、さまざまなデータ ソースからデータをインポートします。 これらのデータ コネクタに加えて、Microsoft は次のパートナーと協力して、コンプライアンス ポータルでさらに多くのサード パーツ データ コネクタを提供しています。 組織は、コンプライアンス ポータルで対応するデータ コネクタを作成する前に、これらのパートナーと協力してアーカイブ サービスを設定します。

- [Veritas](#veritas-data-connectors)

- [TeleMessage](#telemessage-data-connectors)

- [17a-4 LLC](#17a-4-data-connectors)

- [CellTrust](#celltrust-data-connectors)

次のセクションに記載されているサード パーティのデータ (Microsoft 365 Insider リスク管理ソリューションに使用される人事データと物理的な不適切なデータを除く) は、ユーザー メールボックスにインポートされます。 サード パーティのデータをサポートする Microsoft Purview ソリューションは、データが格納されているユーザー メールボックスに適用されます。

### <a name="microsoft-data-connectors"></a>Microsoft データ コネクタ

次の表に、コンプライアンス ポータルで使用できるネイティブサード パーティのデータ コネクタを示します。 この表には、Microsoft 365 でサード パーティのデータをインポートしてアーカイブした後に適用できるコンプライアンス ソリューションもまとめられています。 各コンプライアンス ソリューションの詳細な説明と [、サード パーティのデータをサポートする](#overview-of-compliance-solutions-that-support-third-party-data) 方法については、「サード パーティのデータをサポートするコンプライアンス ソリューションの概要」セクションを参照してください。

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

このセクションの表は、Veritas と連携して使用できるサード パーティ製のデータ コネクタの一覧です。 この表には、Microsoft 365 でインポートしてアーカイブした後にサード パーティのデータに適用できるコンプライアンス ソリューションもまとめられています。 各コンプライアンス ソリューションの詳細な説明と [、サード パーティのデータをサポートする](#overview-of-compliance-solutions-that-support-third-party-data) 方法については、「サード パーティのデータをサポートするコンプライアンス ソリューションの概要」セクションを参照してください。

Microsoft 365 でサード パーティのデータをアーカイブする前に、Veritas と連携して組織のアーカイブ サービス ( *Merge1* と呼ばれる) を設定する必要があります。 詳細については、 **サード パーティのデータ** 列のリンクをクリックして、そのデータ型のコネクタを作成するための詳細な手順に従います。

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

このセクションの表では、TeleMessage と連携して使用できるサード パーティ製のデータ コネクタの一覧を示します。 この表には、Microsoft 365 でインポートしてアーカイブした後にサード パーティのデータに適用できるコンプライアンス ソリューションもまとめられています。 各コンプライアンス ソリューションの詳細な説明と [、サード パーティのデータをサポートする](#overview-of-compliance-solutions-that-support-third-party-data) 方法については、「サード パーティのデータをサポートするコンプライアンス ソリューションの概要」セクションを参照してください。

Microsoft 365 でサード パーティのデータをアーカイブする前に、TeleMessage を使用して組織のアーカイブ サービスを設定する必要があります。 詳細については、 **サード パーティのデータ** 列のリンクをクリックして、そのデータ型のコネクタを作成するための詳細な手順に従います。

TeleMessage データ コネクタは、Microsoft 365 US Government クラウドの GCC 環境でも使用できます。 詳細については、この記事の [「米国政府機関のクラウド」セクションのデータ コネクタ](#data-connectors-in-the-us-government-cloud) を参照してください。

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

このセクションの表では、17a-4 LLC と連携して使用できるサード パーティ製データ コネクタの一覧を示します。 この表には、Microsoft 365 でインポートしてアーカイブした後にサード パーティのデータに適用できるコンプライアンス ソリューションもまとめられています。 各コンプライアンス ソリューションの詳細な説明と [、サード パーティのデータをサポートする](#overview-of-compliance-solutions-that-support-third-party-data) 方法については、「サード パーティのデータをサポートするコンプライアンス ソリューションの概要」セクションを参照してください。

Microsoft 365 でサード パーティのデータをアーカイブするには、17a-4 LLC を使用して組織のアーカイブ サービス ( *DataParser* と呼ばれる) を設定する必要があります。 詳細については、 **サード パーティのデータ** 列のリンクをクリックして、そのデータ型のコネクタを作成するための詳細な手順に従います。

17a-4 データ コネクタは、Microsoft 365 US Government クラウドの GCC 環境でも使用できます。 詳細については、この記事の [「米国政府機関のクラウド」セクションのデータ コネクタ](#data-connectors-in-the-us-government-cloud) を参照してください。

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

このセクションの表に、CellTrust と連携して使用できるサード パーティ製データ コネクタの一覧を示します。 この表には、Microsoft 365 でインポートしてアーカイブした後にサード パーティのデータに適用できるコンプライアンス ソリューションもまとめられています。 各コンプライアンス ソリューションの詳細な説明と [、サード パーティのデータをサポートする](#overview-of-compliance-solutions-that-support-third-party-data) 方法については、「サード パーティのデータをサポートするコンプライアンス ソリューションの概要」セクションを参照してください。

Microsoft 365 でサード パーティのデータをアーカイブする前に、CellTrust と連携して組織のアーカイブ サービス ( *CellTrust SL2* と呼ばれる) を設定する必要があります。 詳細については、 **サードパーティのデータ** 列のリンクをクリックして、CellTrust SL2 コネクタを作成するための詳細な手順を参照してください。

|サード パーティのデータ  |訴訟ホールド|電子情報開示  |アイテム保持設定  |レコード管理  |コミュニケーション コンプライアンス  |インサイダー リスクの管理  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[CellTrust SL2](archive-data-from-celltrustsl2.md)     |![チェック マーク。](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)|![チェック マーク](../media/checkmark.png)||
||||||||

CellTrust SL2 データ コネクタは、Microsoft 365 US Government クラウドの GCC 環境でも使用できます。 詳細については、この記事の [「米国政府機関のクラウド」セクションのデータ コネクタ](#data-connectors-in-the-us-government-cloud) を参照してください。

## <a name="overview-of-compliance-solutions-that-support-third-party-data"></a>サード パーティのデータをサポートするコンプライアンス ソリューションの概要

次のセクションでは、Microsoft Purview ソリューションが前の表に示したサード パーティのデータを管理するのに役立ついくつかの点について説明します。

### <a name="litigation-hold"></a>訴訟ホールド

サード パーティのデータを保持するために、ユーザー メールボックスに [訴訟ホールド](create-a-litigation-hold.md) を置きます。 ホールドを作成するときに、保持期間 ( *時間ベースの保留* とも呼ばれます) を指定して、削除および変更されたサード パーティのデータが指定された期間保持され、メールボックスから完全に削除されるようにすることができます。 または、コンテンツを無期限に保持する ( *無限保留* と呼ばれる) か、訴訟ホールドが削除されるまで保持することもできます。

### <a name="ediscovery"></a>電子情報開示

Microsoft 365 の 3 つの主要な電子情報開示ツールは、コンテンツ検索、Microsoft Purview eDiscovery (Standard)、Microsoft Purview eDiscovery (Premium) です。

- **[コンテンツ検索](content-search.md)。** コンテンツ検索ツールを使用して、インポートしたサード パーティのデータをメールボックスで検索できます。 検索クエリと条件を使用して検索結果を絞り込み、検索結果をエクスポートできます。

- **[電子情報開示 (Standard)](get-started-core-ediscovery.md)。** このツールは、ケース データにアクセスできるユーザーを制御したり、検索条件に一致するユーザー メールボックスやメールボックスのコンテンツを保持したりできるようにするケースを作成できるようにすることで、基本的な検索とエクスポートの機能に基づいています。 つまり、ユーザー メールボックスにインポートされたサード パーティのデータに電子情報開示ホールドを配置できます。

- **[電子情報開示 (Premium)](overview-ediscovery-20.md)。** この強力なツールは、ケースにカストディアンを追加し、保管担当者のデータを保留にし、カストディアンのサードパーティデータをレビューに読み込んで、テーマや重複検出などの詳細な分析を行うことにより、電子情報開示 (Standard) のケース機能を拡張します。 サード パーティのデータをレビュー セットに読み込んだ後、絞り込み結果セットに対してクエリを実行してフィルター処理できます。

   電子情報開示 (Standard) と電子情報開示 (Premium) の両方を使用すると、組織の法的または内部調査に関連する可能性があるサード パーティのデータを管理できます。

### <a name="retention-settings"></a>アイテム保持設定

保持期間の有効期限が切れた後、ユーザー メールボックスに [アイテム保持ポリシー](retention.md) を適用して、サード パーティのデータ (およびその他のメールボックス コンテンツ) を保持して削除できます。 保持ポリシーを使用して、特定の年齢のサード パーティのデータを削除したり、 [保持ラベルを使用して](disposition.md) サード パーティのデータの保持期間が切れたときに廃棄レビューをトリガーしたりすることもできます。

### <a name="records-management"></a>レコード管理

Microsoft 365 の [レコード管理機能](records-management.md) を使用すると、サード パーティのデータをレコードとして宣言できます。 これは、メールボックス内のサード パーティのデータをレコードとしてマークする保持ラベルを適用するユーザーが手動で行うことができます。 または、サードパーティのデータで機密情報、キーワード、またはコンテンツ タイプを識別することで、保持ラベルを自動適用することもできます。

### <a name="communication-compliance"></a>コミュニケーション コンプライアンス

[コミュニケーション コンプライアンス](communication-compliance.md)を使用して、サード パーティのデータを調べて、組織のデータ標準に準拠していることを確認できます。 これを行うには、組織内の不適切なメッセージの検出、キャプチャ、修復アクションを実行します。 たとえば、不適切な言語、機密情報、および規制コンプライアンスのためにインポートするサード パーティのデータを監視できます。

### <a name="insider-risk-management"></a>インサイダー リスクの管理

選択的人事データなどのサード パーティのデータからのシグナルは、 [Insider リスク管理](insider-risk-management.md) ソリューションで使用して、組織内の危険なアクティビティを検出、調査、および行動できるようにすることで内部リスクを最小限に抑えることができます。 たとえば、人事データ コネクタによってインポートされたデータは、従業員データ盗難の検出に役立つリスク インジケーターとして使用されます。

## <a name="using-ediscovery-tools-to-search-for-third-party-data"></a>電子情報開示ツールを使用してサード パーティのデータを検索する

データ コネクタを使用してユーザー メールボックス内のサード パーティのデータをインポートおよびアーカイブした後、Microsoft 365 電子情報開示ツールを使用してサード パーティのデータを検索できます。 また、電子情報開示ツールを使用して、電子情報開示 (Standard) ケースと電子情報開示 (Premium) ケースに関連付けられたクエリ ベースの保留を作成して、サード パーティのデータを保持することもできます。 電子情報開示ツールの詳細については、 [Microsoft 365 の電子情報開示ソリューションに](ediscovery.md)関するページを参照してください。

データ コネクタを使用してユーザー メールボックスにインポートした任意の種類のサード パーティデータを検索 (または保留) するには、次の検索クエリを使用します。 検索の範囲をユーザー メールボックスに設定してください。

```powershell
kind:externaldata
```

このクエリは、コンテンツ検索、電子情報開示 (Standard) ケースに関連付けられた検索、または電子情報開示 (Premium) のコレクションの **[キーワード** ] ボックスで使用できます。

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

一部のデータ コネクタは、米国政府機関のクラウドで使用できます。 次のセクションでは、サード パーティのデータ コネクタをサポートする特定の政府機関環境を示します。 米国政府機関クラウドの詳細については、「 [Microsoft 365 US Government](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/microsoft-365-government-how-to-buy)」を参照してください。

### <a name="veritas-data-connectors-in-the-us-government-cloud-preview"></a>米国政府クラウドの Veritas データ コネクタ (プレビュー)

|データ コネクタ  |GCC  |GCC High  |DoD  |
|:---------|:---------|:---------|:---------|
|CellTrust| はい | 不要 | 不要 |
|MS SQL 上の Cisco Jabber| はい | 不要 | 不要 |
|Oracle 上の Cisco Jabber| はい | 不要 | 不要 |
|PostgreSQL 上の Cisco Jabber| はい | 不要 | 不要 |
|EML| はい | 不要 | 不要 |
|FX 接続| はい | 不要 | いいえ |
|Jive| はい | 不要 | 不要 |
|MS SQL Database| はい | 不要 | 不要 |
|ピボット| はい | 不要 | 不要 |
|Redtail Speak| はい | 不要 | 不要 |
|Reuters Dealing| はい | 不要 | 不要 |
|Reuters Eikon| はい | 不要 | 不要 |
|Reuters FX| はい | 不要 | 不要 |
|RingCentral| はい | 不要 | いいえ |
|Salesforce Chatter| はい | 不要 | いいえ |
|ServiceNow| はい | 不要 | いいえ |
|Skype for Business| はい | 不要 | いいえ |
|Slack eDiscovery| はい | 不要 | いいえ |
|Symphony| はい | 不要 | いいえ |
|区切られたテキスト| はい | 不要 | いいえ |
|Twitter| はい | 不要 | いいえ |
|Webex チーム| はい | 不要 | いいえ |
|Web ページ| はい | 不要 | いいえ |
|Facebookからの職場| はい | 不要 | いいえ |
|XIP| はい | 不要 | いいえ |
|XSLT/XML| はい | 不要 | 不要 |
|Yieldbroker| はい | 不要 | 不要 |
|YouTube| 不要 | 不要 | 不要 |
|Zoom会議| はい | いいえ | 不要 |
|||||

### <a name="telemessage-data-connectors-in-the-us-government-cloud"></a>米国政府クラウドの TeleMessage データ コネクタ

|データ コネクタ  |GCC  |GCC High  |DoD  |
|:---------|:---------|:---------|:---------|
|Android Archiver | はい | 不要 | 不要 |
|AT&T SMS/MMS Network Archiver | はい | 不要 | 不要 |
|Bell SMS/MMS Network Archiver | はい | 不要 | 不要 |
|Enterprise Number Archiver | はい | 不要 | 不要 |
|O2 SMS および Voice Network Archiver | はい         | 不要 | 不要 |
|Rogers Network Archiver | はい         | 不要 | 不要 |
|Signal Archiver | はい | 不要 | 不要 |
|Telegram Archiver | はい | 不要 | いいえ |
|TELUS SMS Network Archiver | はい | 不要 | いいえ |
|Verizon SMS/MMS Network Archiver | はい | 不要 | いいえ |
|WeChat Archiver | はい | 不要 | いいえ |
|WhatsApp Archiver | はい | 不要 | いいえ |
|||||

### <a name="17a-4-data-connectors-in-the-us-government-cloud"></a>米国政府機関クラウドの 17a-4 データ コネクタ

|データ コネクタ  |GCC  |GCC High  |DoD  |
|:---------|:---------|:---------|:---------|
|BlackBerry DataParser | はい | 不要 | 不要 |
|Bloomberg DataParser  | はい | 不要 | いいえ |
|Cisco Jabber DataParser  | はい | 不要 | いいえ |
|Cisco Webex DataParser  | はい | 不要 | いいえ |
|FactSet DataParser  | はい | 不要 | いいえ |
|Fuze DataParser  | はい | 不要 | いいえ |
|FX Connect DataParser  | はい | 不要 | いいえ |
|ICE DataParser  | はい | 不要 | いいえ |
|InvestEdge DataParser  | はい | いいえ | 不要 |
|LivePerson Conversational Cloud DataParser  | はい | いいえ | 不要 |
|Quip DataParser  | はい | 不要 | 不要 |
|Refinitiv Eikon Messenger DataParser  | はい | 不要 | 不要 |
|ServiceNow DataParser  | はい | いいえ | 不要 |
|Skype for Business Server DataParser | はい | いいえ | 不要 |
|Slack DataParser | はい | いいえ | 不要 |
|SQL DataParser  | はい | いいえ | 不要 |
|Symphony DataParser | はい | 不要 | 不要 |
|Zoom DataParser | はい | 不要 | 不要 |
|||||

### <a name="celltrust-data-connectors-in-the-us-government-cloud"></a>米国政府クラウドの CellTrust データ コネクタ

|データ コネクタ  |GCC  |GCC High  |DoD  |
|:---------|:---------|:---------|:---------|
|CellTrust SL2 | はい | いいえ | いいえ |
|||||

## <a name="working-with-a-microsoft-partner-to-archive-third-party-data"></a>Microsoft パートナーと協力してサード パーティのデータをアーカイブする

サード パーティのデータをインポートおよびアーカイブするためのもう 1 つのオプションは、組織が Microsoft パートナーと連携することです。 Microsoft コンプライアンス センターで使用できるデータ コネクタでサード パーティのデータ型がサポートされていない場合は、定期的にサード パーティのデータ ソースからアイテムを抽出し、サード パーティ API で Microsoft クラウドに接続し、それらの項目を Microsoft 365 にインポートするように構成されるカスタム コネクタを提供できるパートナーと連携できます。 また、パートナー コネクタは、アイテムのコンテンツをサード パーティのデータ ソースから電子メール メッセージに変換し、それを Microsoft 365 のメールボックスにインポートします。

操作できるパートナーの一覧と、この方法のステップ バイ ステップ プロセスについては、「 [パートナーと連携して Microsoft 365 でサード パーティのデータをアーカイブする」を](work-with-partner-to-archive-third-party-data.md)参照してください。
