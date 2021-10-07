---
title: Microsoft 365の拡張性
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
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
description: サード パーティ製のデータ Microsoft 365 API を使用してコンプライアンス ソリューションを拡張する方法Graph説明します。
ms.openlocfilehash: bc812a6cdc051daf64b14f60db32f360ceee7bd4
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60204409"
---
# <a name="microsoft-365-compliance-extensibility"></a>Microsoft 365の拡張性

Microsoft 365ソリューションは、組織がコンプライアンス リスクをインテリジェントに評価し、機密データを管理および保護し、規制要件に効果的に対応するのに役立ちます。 Microsoft 365は拡張性のシナリオに富み、組織はコンプライアンス ソリューションの適応、拡張、統合、加速、サポートを行えます。

コンプライアンスの機能拡張には、次の 2 つの重要な構成要素があります。

- **データ コネクタ**。 Microsoft 以外のデータをインポートおよびアーカイブするために使用し、保護とガバナンスMicrosoft 365をサード パーティのデータに適用できます。

- **API**. コンプライアンス機能にプログラムMicrosoft 365アクセスできます。

## <a name="data-connectors"></a>データ コネクタ

Microsoft は、サード パーティ製のデータ コネクタを提供し、このコネクタで構成Microsoft 365 コンプライアンス センター。 Microsoft が提供するデータ コネクタの一覧については、「サード パーティ製データ コネクタ」 [の表を参照](archiving-third-party-data.md#third-party-data-connectors) してください。 また、サード パーティ製データ コネクタの表には、Microsoft 365 でデータをインポートおよびアーカイブした後にサード パーティデータに適用できるコンプライアンス ソリューションと、各コネクタの詳細な手順へのリンクも示されています。

データ コネクタの詳細Microsoft 365については、「サードパーティ データのアーカイブ[」を参照してください](archiving-third-party-data.md)。 Microsoft 365 コンプライアンス センター で使用できるデータ コネクタでサード パーティ製のデータ型がサポートされていない場合は、カスタム コネクタを提供できるパートナーと作業できます。 この方法で作業できるパートナーの一覧と、この方法の手順については、「パートナーと協力してサード パーティのデータをアーカイブする」 [を参照してください](work-with-partner-to-archive-third-party-data.md)。

### <a name="prerequisites-for-data-connectors"></a>データ コネクタの前提条件

サード パーティのデータをインポートおよびアーカイブするために、Microsoft 365 コンプライアンス センターで使用できるデータ コネクタの多くは、サード パーティのデータ ソースで構成タスクを準備して実行する必要があります。 これらの前提条件は、サードパーティのデータ コネクタごとに詳細に説明されています。

Microsoft のパートナー Microsoft 365 コンプライアンス センター提供されるデータ コネクタの場合、コネクタを展開する前に、組織はパートナーとのビジネス関係を必要とします。

サード パーティ製データ コネクタのライセンス要件については、「コンプライアンス ライセンス[Microsoft 365」を参照](/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx)してください。

## <a name="apis"></a>API

Microsoft 365 API は、Microsoft Information Protection SDK、Microsoft Graph API、および Office 365管理アクティビティ API で利用できます。 一部のコンプライアンス API は、Microsoft 365 のお客様、独立したソフトウェア ベンダー、システム インテグレーター、およびマネージド セキュリティ サービス プロバイダーの開発者が価値の高いセキュリティおよびコンプライアンス ソリューションを構築できる新しいセキュリティおよびコンプライアンス API の一部です。

API にアクセスする方法の詳細については、「Graphの[概要」を参照Graph。](/graph/overview)

### <a name="microsoft-information-protection-mip-sdk"></a>Microsoft Information Protection (MIP) SDK

MIP SDK は、ラベル付けおよび保護サービスを、Microsoft 365およびコンプライアンス センターからサード パーティのアプリケーションとサービスに公開します。 開発者は、SDK を使用して、ファイルにラベルと保護を適用するためのネイティブ サポートを構築できます。 開発者は、特定のラベルが検出された場合に実行するアクションと、MIP で暗号化された情報に対する理由を決定できます。

高レベルの MIP SDK の使用例は次のとおりです。

- エクスポート時に分類ラベルをファイルに適用する業務行アプリケーション。

- MIP ラベル付けのためのネイティブ サポートを提供する CAD/CAM 設計アプリケーション。

- Azure Information Protection を使用してデータを暗号化できるクラウド アクセス セキュリティ ブローカーまたはデータ損失防止ソリューション。

MIP SDK、前提条件、追加シナリオ、およびサンプルの詳細については [、「MIP SDK の概要」を参照してください](/information-protection/develop/overview)。

### <a name="microsoft-graph-api-for-teams-dlp"></a>Microsoft Graph DLP Teams API

[データ損失防止 (DLP)](dlp-microsoft-teams.md)機能は、特に組織がリモート作業に移行Microsoft Teamsに広く使用されています。 今年の初めに[、Microsoft](https://developer.microsoft.com/graph/blogs/announcing-change-notifications-for-microsoft-teams-messages/) Graph変更通知 API のパブリック プレビューをTeams。 この API を使用すると、開発者は、ほぼリアルタイムでMicrosoft Teamsメッセージをリッスンし、顧客とパートナーの両方に DLP シナリオを実装できるアプリを構築できます。 さらに、Microsoft Graph Patch API では、メッセージに DLP アクションTeamsできます。

これら 2 つの API は、DLP 用の Microsoft Graph API をTeamsします。 サンプル アプリを試して開始 [できます](https://github.com/microsoftgraph/csharp-webhook-with-resource-data)。 メッセージング Webhook のMicrosoft Teams詳細については、ドキュメントを参照[してください](/graph/api/subscription-post-subscriptions)。

DLP のライセンス要件については、「セキュリティTeamsコンプライアンスMicrosoft 365ライセンス ガイダンス[」を&してください](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-data-loss-prevention-for-teams)。

### <a name="microsoft-graph-api-for-ediscovery-preview"></a>Microsoft Graph API for eDiscovery (プレビュー)

[Advanced eDiscovery](overview-ediscovery-20.md)を使用すると、組織は、データが Microsoft 365 のセキュリティとコンプライアンスの境界内にとどまっている間、関連するセットに対するデータを削減するために、インテリジェントな機械学習と分析機能を使用して、データが保存されているデータを検出し、より多くのエンドツーエンドの電子情報開示ワークフローを管理できます。

Graphカスタム クエリAdvanced eDiscovery API を使用して、ケースの作成と管理、セットの確認、およびセット クエリのレビューを、スケーラブルで繰り返し可能な方法で行えます。 これにより、顧客とパートナーはアプリとワークフローを作成して、ケースの作成や保管担当者や法的ホールドの管理など、一般的で繰り返しのプロセスを自動化できます。

電子情報開示用のGraph API の最初のセットは、パブリック プレビューで使用できます。 暦年の終わりまでに、より多くの機能を追加する予定です。 これらの API と他の更新プログラムの詳細については、Advanced eDiscoveryブログを参照[してください](https://aka.ms/Ignite2020AeDAA)。

Advanced eDiscovery および API のライセンス要件については、「Microsoft 365 ライセンス ガイダンス」の「電子情報開示」セクションを参照&[してください](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery)。

### <a name="microsoft-graph-api-for-teams-export-preview"></a>Microsoft Graph API for Teams エクスポート (プレビュー)

Enterprise情報アーカイブ (EIA) Microsoft Teamsは、規制要件を解決できる重要なシナリオです。 Microsoft Teams のコンテンツをアーカイブするための組み込みの機能に加えて、顧客とパートナーは Teams Export API を使用してカスタム アプリケーションと統合のシナリオを解決できます。 この Teams エクスポート API は、メッセージとメッセージの添付ファイルの一括エクスポート (アプリごとに 1 秒/1 テナントあたり最大 200 要求) をサポートTeamsします。 削除されたメッセージは、削除後最大 30 日間 API からアクセスすることもできます。 これらのエクスポート API の詳細Teamsアプリケーションで使用する方法については、「Export content with the Microsoft Teams [API」を参照してください](/microsoftteams/export-teams-content)。

エクスポート API の使用に関するライセンス要件については、「Teamsコンプライアンスに関するMicrosoft 365ライセンス[ガイダンス」を&してください](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。

### <a name="microsoft-graph-connector-apis-preview"></a>Microsoft Graph コネクタ API (プレビュー)

[Microsoft Graphコネクタを使用](/microsoftsearch/connectors-overview)すると、組織はサードパーティのデータをインデックス化して、そのデータが結果にMicrosoft Searchできます。 この機能は、Microsoft 365 の生産性向上アプリと Microsoft の広範なエコシステムで検索可能な、コンテンツ ソースの種類を拡大しています。 サード パーティのデータは、オンプレミスまたはパブリック クラウドまたはプライベート クラウドでホストできます。 このAdvanced eDiscovery、接続されたアプリに組み込みのコンプライアンス値を開発者Microsoft 365しています。 これにより、シームレスなコンプライアンス エクスペリエンスをユーザーに提供Microsoft 365エコシステムに統合するアプリのコンプライアンスが可能となります。 Microsoft Graph コネクタ API をアプリ ビューに組み込む方法の詳細については、「Microsoft Graph で接続を作成、更新、および削除する」[を参照してください](/graph/search-index-manage-connections)。

