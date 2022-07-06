---
title: Microsoft Purview の拡張性
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: サード パーティのデータ コネクタと Microsoft Graph API を使用して Microsoft Purview ソリューションを拡張する方法について説明します。
ms.openlocfilehash: 8cda9ea3a5ef69af69ab802ca21aa8c4c0e716b9
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66621185"
---
# <a name="microsoft-purview-and-microsoft-priva-extensibility"></a>Microsoft Purview とMicrosoft Priva機能拡張

Microsoft Purview ソリューションは、組織がコンプライアンス リスクをインテリジェントに評価し、機密データを管理および保護し、規制要件に効果的に対応するのに役立ちます。 Microsoft Purview は拡張性の高いシナリオが豊富で、組織はコンプライアンス ソリューションの適応、拡張、統合、高速化、サポートを行うことができます。

コンプライアンス機能拡張には、次の 2 つの重要な構成要素があります。

- **データ コネクタ**。 Microsoft 365 の保護機能とガバナンス機能をサード パーティのデータに適用できるように、Microsoft 以外のデータをインポートおよびアーカイブするために使用します。

- **API**。 Microsoft Purview 機能へのプログラムによるアクセスを有効にします。

## <a name="data-connectors"></a>データ コネクタ

Microsoft は、Microsoft Purview コンプライアンス ポータルで構成できるサード パーティのデータ コネクタを提供します。 Microsoft が提供するデータ コネクタの一覧については、「[サードパーティのデータ コネクタ](archiving-third-party-data.md#third-party-data-connectors)」の表を参照してください。 サード パーティのデータ コネクタの表には、Microsoft 365 でデータをインポートおよびアーカイブした後にサード パーティのデータに適用できるコンプライアンス ソリューションと、各コネクタの詳細な手順へのリンクもまとめられています。

Microsoft 365 データ コネクタの詳細については、「 [サード パーティのデータのアーカイブ](archiving-third-party-data.md)」を参照してください。 コンプライアンス ポータルで使用できるデータ コネクタでサード パーティのデータ型がサポートされていない場合は、カスタム コネクタを提供できるパートナーと連携できます。 操作できるパートナーの一覧と、この方法のステップ バイ ステップ プロセスについては、「 [パートナーと連携してサード パーティのデータをアーカイブする](work-with-partner-to-archive-third-party-data.md)」を参照してください。

### <a name="prerequisites-for-data-connectors"></a>データ コネクタの前提条件

コンプライアンス ポータルでサード パーティのデータをインポートおよびアーカイブするために使用できるデータ コネクタの多くは、サード パーティのデータ ソースで構成タスクを準備して実行する必要があります。 これらの前提条件については、サード パーティの各データ コネクタについて詳しく説明します。

Microsoft のいずれかのパートナーによって提供されるコンプライアンス ポータルのデータ コネクタの場合、コネクタをデプロイする前に、組織はパートナーとのビジネス関係を必要とします。

サード パーティのデータ コネクタのガイダンスと要件については、セキュリティ & コンプライアンスに関する Microsoft 365 ガイダンスの「データ コネクタ」セクションを参照[してください - サービスの説明 |Microsoft Docs](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。

## <a name="apis"></a>API

Microsoft Purview API とMicrosoft Priva API は、Microsoft Information Protection SDK、Microsoft Graph API、Office 365 Management アクティビティ API で入手できます。 一部のコンプライアンス API は、Microsoft 365 のお客様、独立系ソフトウェア ベンダー、システム インテグレーター、マネージド セキュリティ サービス プロバイダーの開発者が価値の高いセキュリティとコンプライアンス ソリューションを構築できるようにする、セキュリティとコンプライアンス API の新しいセットの一部です。

Graph API にアクセスする方法の詳細については、「 [Microsoft Graph の概要](/graph/overview)」を参照してください。

### <a name="microsoft-graph-apis-for-subject-rights-requests"></a>サブジェクト権利要求用の Microsoft Graph API

個人は、世界中の特定のプライバシー規制に従って、企業が収集した個人データの確認または管理を要求できます。 これらの要求は、Microsoft Priva 主体の権利要求 ソリューション内 *のサブジェクト権限要求* と呼ばれます。 サブジェクト権利要求は、 *データ主体要求* (DSR) または *データ主体アクセス要求* (DSAR) とも呼ばれます。 サブジェクト権利要求用の Microsoft Graph API を使用すると、開発者は Microsoft 365 関連のサブジェクト権利要求をより広範なプライバシー エコシステムと統合できます。 この API ベースの機能拡張により、組織は、Microsoft 環境と Microsoft 以外の両方の環境をカバーするデータ資産全体で、サブジェクトの権利要求に一元的に対応できます。 この機能は、大規模な自動化にも役立ち、組織は手動プロセスに依存することなく、業界の規制をより効率的に満たすのに役立ちます。

詳細については、 [サブジェクト権限要求に関する Microsoft Graph API を](/graph/api/resources/subjectrightsrequest-subjectrightsrequestapioverview)参照してください。

### <a name="microsoft-information-protection-mip-sdk"></a>Microsoft Information Protection (MIP) SDK

MIP SDK では、Microsoft 365 セキュリティおよびコンプライアンス センターからサード パーティのアプリケーションとサービスにラベル付けサービスと保護サービスが公開されます。 開発者は SDK を使用して、ファイルにラベルと保護を適用するためのネイティブ サポートを構築できます。 開発者は、特定のラベルが検出されたときに実行するアクションと、MIP で暗号化された情報に対する理由を判断できます。

MIP SDK の上位レベルのユース ケースは次のとおりです。

- エクスポート時にファイルに分類ラベルを適用する基幹業務アプリケーション。

- 秘密度ラベルのネイティブ サポートを提供する CAD/CAM 設計アプリケーション。

- Azure Information Protectionを使用してデータを暗号化できるクラウド アクセス セキュリティ ブローカーまたはデータ損失防止ソリューション。

MIP SDK、前提条件、その他のシナリオ、サンプルの詳細については、「 [MIP SDK の概要](/information-protection/develop/overview)」を参照してください。

### <a name="microsoft-graph-api-for-teams-dlp"></a>Teams DLP の Microsoft Graph API

[データ損失防止 (DLP)](dlp-microsoft-teams.md) 機能は、特に組織がリモート作業に移行するにつれて、Microsoft Teams で広く使用されています。 最近、Teams のメッセージに対する Microsoft Graph 変更通知 API の [一般公開が発表されました](https://devblogs.microsoft.com/microsoft365dev/change-notifications-for-microsoft-teams-messages-now-generally-available/) 。 この API を使用すると、開発者は Microsoft Teams メッセージをほぼリアルタイムでリッスンできるアプリを構築し、顧客とパートナーの両方に DLP シナリオを実装できます。 さらに、Microsoft Graph Patch API を使用すると、Teams メッセージに DLP アクションを適用できます。

これら 2 つの API は、Teams DLP の Microsoft Graph APIを形成します。 [サンプル アプリ](https://github.com/microsoftgraph/aspnetcore-webhooks-sample)を試してみると、作業を開始できます。 Microsoft Teams メッセージング Webhook の詳細については、 [ドキュメントを参照してください](/graph/api/subscription-post-subscriptions)。

Teams DLP のライセンス要件については、 [セキュリティ&コンプライアンスに関する Microsoft 365 ライセンス ガイダンスを](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)参照してください。

### <a name="microsoft-graph-api-for-ediscovery-preview"></a>Microsoft Graph API for eDiscovery (プレビュー)

[電子情報開示 (Premium) を](overview-ediscovery-20.md)使用すると、組織は、それが存在するデータを検出し、インテリジェントな機械学習と分析機能を備えたより多くのエンドツーエンドの電子情報開示ワークフローを管理して、データを関連するセットに削減できます。データは Microsoft 365 のセキュリティとコンプライアンスの境界内にとどまります。

電子情報開示 (Premium) 用の Graph API を使用すると、ケースの作成と管理、セットの確認、セット クエリのレビューをスケーラブルで繰り返し可能な方法で行うことができます。 これにより、顧客とパートナーは、ケースの作成やカストディアンや訴訟ホールドの管理など、一般的で反復的なプロセスを自動化するアプリやワークフローを作成できます。

電子情報開示用の Graph API の最初のセットは、パブリック プレビューで使用できます。 暦年の終わりまでにさらに機能を追加する予定です。 これらの API と電子情報開示 (Premium) のその他の更新プログラムの詳細については、この [ブログ](https://aka.ms/Ignite2020AeDAA)を参照してください。

電子情報開示 (Premium) と API のライセンス要件については、 [セキュリティ&コンプライアンスに関する Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery)の「電子情報開示」セクションを参照してください。

### <a name="microsoft-graph-api-for-teams-export"></a>Microsoft Graph API for Teams Export

Microsoft Teams のエンタープライズ情報アーカイブ (EIA) は、規制要件を解決できるため、お客様にとって重要なシナリオです。 Microsoft Teams のコンテンツをアーカイブするための組み込みの機能に加えて、お客様とパートナーは Teams Export API を使用して、カスタム アプリケーションと統合のシナリオを解決できるようになりました。 Teams Export API では、Teams メッセージとメッセージ添付ファイルの一括エクスポート (1 秒あたり最大 200 要求/アプリ/テナントあたり) がサポートされます。 削除されたメッセージには、削除後最大 30 日間 API からアクセスできます。 これらの Teams Export API とアプリケーションで使用する方法の詳細については、「 [Microsoft Teams Export API を使用してコンテンツをエクスポートする」を](/microsoftteams/export-teams-content)参照してください。

Teams Export API の使用に関するライセンス要件については、 [セキュリティ&コンプライアンスに関する Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)を参照してください。

### <a name="microsoft-graph-connector-apis-preview"></a>Microsoft Graph Connector API (プレビュー)

[Microsoft Graph コネクタ](/microsoftsearch/connectors-overview)を使用すると、組織はサード パーティのデータにインデックスを付けて、Microsoft Search の結果に表示されるようにすることができます。 この機能は、Microsoft 365 の生産性向上アプリと Microsoft の広範なエコシステムで検索可能な、コンテンツ ソースの種類を拡大しています。 サード パーティのデータは、オンプレミスまたはパブリッククラウドまたはプライベート クラウドでホストできます。 電子情報開示 (Premium) 以降、Microsoft 365 接続アプリの組み込みのコンプライアンス値の開発者プレビューが有効になります。 これにより、Microsoft 365 エコシステムに統合されたアプリのコンプライアンスが可能になり、シームレスなコンプライアンス エクスペリエンスをユーザーに提供できるようになります。 アプリ ビューに Microsoft Graph Connector API を組み込む方法の詳細については、 [Microsoft Graph での接続の作成、更新、および削除に関するページを](/graph/connecting-external-content-connectors-api-overview)参照してください。

### <a name="microsoft-graph-api-for-records-management-preview"></a>Microsoft Graph API for records management (プレビュー)

あらゆる種類の組織では、データ全体で重要なレコードを管理するためのレコード管理ソリューションが必要です。 [Microsoft Purview レコード管理](records-management.md)は、組織が法的義務を管理し、規制への準拠を示す機能を提供し、不要になったアイテムを定期的に処理することで効率を向上させます。

レコード管理ソリューションは、大量の組織がデータの保護、ラベル付け、保持、または削除に関するさまざまな機能を利用するために使用されます。 レコード管理用の Microsoft Graph API を使用すると、組織は保持ラベルとそれに関連するアクションをより効率的に管理し、繰り返しタスクを自動化し、オプションの柔軟性を顧客に提供できます。

今度は、レコード管理用の Graph API の最初のリリースで、保持ラベルとイベント ベースのリテンション期間の管理がサポートされます。 サンプル シナリオ:

- **保持ラベルの管理**
    
    レコード管理管理者と開発者は、定期的に作成、更新、削除されるラベルを使用してレコード管理システムを維持する必要があります。
    
    開発者とコンプライアンス管理者は、レコード管理に Graph API を使用して、ラベル エンティティで CRUD 操作を実行してシステムを維持します。

- **既存のラベルのイベントをトリガーする**
    
    従業員が組織を離れると、人事管理システムで情報が更新されます。 退出日から、機密文書を 7 年間保持する必要があります。 これらのドキュメントには、保持ラベル "Employee_departure" が既に適用されています。
    
    開発者とコンプライアンス管理者は、レコード管理に Graph API を使用してラベル "Employee_departure" を読み取り、関連するイベントの種類 "Event-employee_departure" を検索します。
    
    次に、レコード管理に Graph API を使用して、関連するイベントの種類のイベントを作成します。 機密ドキュメントの保持期間は、このイベントが作成された後に開始されます。

レコード管理用の Graph API の詳細については、「 [Microsoft Graph Records Management API の使用」を](/graph/api/resources/security-recordsmanagement-overview?view=graph-rest-beta&preserve-view=true)参照してください。

これらの API を使用するためのライセンス要件については、 [セキュリティ&コンプライアンスに関する Microsoft 365 ライセンス ガイダンスの](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)レコード管理セクションを参照してください。
