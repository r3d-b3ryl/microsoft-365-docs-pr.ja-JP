---
title: Microsoft Purview の拡張性
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
description: サード パーティのデータ コネクタと Microsoft Graph API を使用して Microsoft Purview ソリューションを拡張する方法について説明します。
ms.openlocfilehash: 9d2c3235a29e2d25e24656a4ff94216cde925b6c
ms.sourcegitcommit: caedcf7f16eed23596487d97c375d4bc4c8f3566
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64992262"
---
# <a name="microsoft-purview-and-microsoft-priva-extensibility"></a>Microsoft Purview と Microsoft Priva の拡張性

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft Purview ソリューションは、組織がコンプライアンス リスクをインテリジェントに評価し、機密データを管理および保護し、規制要件に効果的に対応するのに役立ちます。 Microsoft Purview は拡張性の高いシナリオが豊富で、組織はコンプライアンス ソリューションの適応、拡張、統合、高速化、サポートを行うことができます。

コンプライアンス機能拡張には、次の 2 つの重要な構成要素があります。

- **データ コネクタ**。 Microsoft 以外のデータをインポートしてアーカイブするために使用し、Microsoft 365保護とガバナンス機能をサード パーティのデータに適用できるようにします。

- **API**。 Microsoft Purview 機能へのプログラムによるアクセスを有効にします。

## <a name="data-connectors"></a>データ コネクタ

Microsoft は、Microsoft Purview コンプライアンス ポータルで構成できるサードパーティのデータ コネクタを提供します。 Microsoft から提供されるデータ コネクタの一覧については、 [サード パーティのデータ コネクタ](archiving-third-party-data.md#third-party-data-connectors) の表を参照してください。 サード パーティのデータ コネクタの表には、Microsoft 365でデータをインポートおよびアーカイブした後にサード パーティのデータに適用できるコンプライアンス ソリューションと、各コネクタの詳細な手順へのリンクもまとめられています。

Microsoft 365 データ コネクタの詳細については、「[サード パーティのデータのアーカイブ](archiving-third-party-data.md)」を参照してください。 コンプライアンス ポータルで使用できるデータ コネクタでサード パーティのデータ型がサポートされていない場合は、カスタム コネクタを提供できるパートナーと連携できます。 操作できるパートナーの一覧と、この方法のステップ バイ ステップ プロセスについては、「 [パートナーと連携してサード パーティのデータをアーカイブする](work-with-partner-to-archive-third-party-data.md)」を参照してください。

### <a name="prerequisites-for-data-connectors"></a>データ コネクタの前提条件

コンプライアンス ポータルでサード パーティのデータをインポートおよびアーカイブするために使用できるデータ コネクタの多くは、サード パーティのデータ ソースで構成タスクを準備して実行する必要があります。 これらの前提条件については、サード パーティの各データ コネクタについて詳しく説明します。

Microsoft のいずれかのパートナーによって提供されるコンプライアンス ポータルのデータ コネクタの場合、コネクタをデプロイする前に、組織はパートナーとのビジネス関係を必要とします。

サード パーティのデータ コネクタのガイダンスと要件については、「[セキュリティ&コンプライアンスに関するMicrosoft 365ガイダンス - サービスの説明|」の「データ コネクタ」セクションを参照してください。Microsoft Docs](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。

## <a name="apis"></a>API

Microsoft Purview API と Microsoft Priva API は、Microsoft Information Protection SDK、Microsoft Graph API、および Office 365 Management アクティビティ API で入手できます。 一部のコンプライアンス API は、Microsoft 365顧客、独立系ソフトウェア ベンダー、システム インテグレーター、マネージド セキュリティ サービス プロバイダーの開発者が価値の高いセキュリティとコンプライアンス ソリューションを構築できるようにする新しいセキュリティおよびコンプライアンス API のセットの一部です。

Graph API にアクセスする方法の詳細については、「[Microsoft Graphの概要](/graph/overview)」を参照してください。

### <a name="microsoft-graph-apis-for-subject-rights-requests"></a>サブジェクト権利要求に対する Microsoft Graph API

個人は、世界中の特定のプライバシー規制に従って、企業が収集した個人データの確認または管理を要求できます。 これらの要求は、Microsoft Priva Subject *Rights Requests* ソリューション内のサブジェクト権利要求と呼ばれます。 サブジェクト権利要求は、 *データ主体要求* (DSR) または *データ主体アクセス要求* (DSAR) とも呼ばれます。 Microsoft Graphサブジェクト権利要求用 API を使用すると、開発者は、Microsoft 365関連のサブジェクト権利要求をより広範なプライバシー エコシステムと統合できます。 この API ベースの機能拡張により、組織は、Microsoft 環境と Microsoft 以外の両方の環境をカバーするデータ資産全体で、サブジェクトの権利要求に一元的に対応できます。 この機能は、大規模な自動化にも役立ち、組織は手動プロセスに依存することなく、業界の規制をより効率的に満たすのに役立ちます。

詳細については、[サブジェクト権限要求に関する Microsoft Graph API に関するページを](/graph/api/resources/subjectrightsrequest-subjectrightsrequestapioverview)参照してください。

### <a name="microsoft-information-protection-mip-sdk"></a>Microsoft Information Protection (MIP) SDK

MIP SDK は、Microsoft 365セキュリティおよびコンプライアンス センターからサード パーティのアプリケーションやサービスにラベル付けサービスと保護サービスを公開します。 開発者は SDK を使用して、ファイルにラベルと保護を適用するためのネイティブ サポートを構築できます。 開発者は、特定のラベルが検出されたときに実行するアクションと、MIP で暗号化された情報に対する理由を判断できます。

MIP SDK の上位レベルのユース ケースは次のとおりです。

- エクスポート時にファイルに分類ラベルを適用する基幹業務アプリケーション。

- 秘密度ラベルのネイティブ サポートを提供する CAD/CAM 設計アプリケーション。

- Azure Information Protectionを使用してデータを暗号化できるクラウド アクセス セキュリティ ブローカーまたはデータ損失防止ソリューション。

MIP SDK、前提条件、その他のシナリオ、サンプルの詳細については、「 [MIP SDK の概要](/information-protection/develop/overview)」を参照してください。

### <a name="microsoft-graph-api-for-teams-dlp"></a>Teams DLP の Microsoft Graph API

[データ損失防止 (DLP)](dlp-microsoft-teams.md) 機能は、特に組織がリモート作業に移行するにつれて、Microsoft Teamsで広く使用されています。 最近、Teamsのメッセージに対する Microsoft Graph変更通知 API の[一般公開が発表されました](https://devblogs.microsoft.com/microsoft365dev/change-notifications-for-microsoft-teams-messages-now-generally-available/)。 この API を使用すると、開発者は、ほぼリアルタイムでMicrosoft Teamsメッセージをリッスンし、顧客とパートナーの両方に DLP シナリオを実装できるアプリを構築できます。 さらに、Microsoft Graph Patch API を使用すると、Teams メッセージに DLP アクションを適用できます。

これら 2 つの API は、Teams DLP の Microsoft Graph APIを形成します。 [サンプル アプリ](https://github.com/microsoftgraph/aspnetcore-webhooks-sample)を試してみると、作業を開始できます。 メッセージング webhook のMicrosoft Teamsの詳細については、[ドキュメントを参照してください](/graph/api/subscription-post-subscriptions)。

Teams DLP のライセンス要件については、[セキュリティ&コンプライアンスに関するライセンスガイダンスMicrosoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)参照してください。

### <a name="microsoft-graph-api-for-ediscovery-preview"></a>Microsoft Graph API for eDiscovery (プレビュー)

[電子情報開示 (プレミアム)](overview-ediscovery-20.md) を使用すると、組織は、それが存在するデータを検出し、インテリジェントな機械学習と分析機能を備えたより多くのエンド ツー エンドの電子情報開示ワークフローを管理して、データを関連するセットに削減できます。データはMicrosoft 365セキュリティとコンプライアンスの境界内に留まります。

電子情報開示 (プレミアム) 用のGraph API を使用すると、ケースの作成と管理、セットのレビュー、およびセット クエリのレビューをスケーラブルで繰り返し可能な方法で行うことができます。 これにより、顧客とパートナーは、ケースの作成やカストディアンや訴訟ホールドの管理など、一般的で反復的なプロセスを自動化するアプリやワークフローを作成できます。

電子情報開示用のGraph API の最初のセットは、パブリック プレビューで利用できます。 暦年の終わりまでにさらに機能を追加する予定です。 これらの API と電子情報開示 (プレミアム) のその他の更新プログラムの詳細については、この[ブログ](https://aka.ms/Ignite2020AeDAA)を参照してください。

電子情報開示 (プレミアム) と API のライセンス要件については、[セキュリティ&コンプライアンスに関するMicrosoft 365ライセンスガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery)の「電子情報開示」セクションを参照してください。

### <a name="microsoft-graph-api-for-teams-export"></a>Teamsエクスポート用の Microsoft Graph API

Microsoft TeamsのEnterprise情報アーカイブ (EIA) は、規制要件を解決できるため、お客様にとって重要なシナリオです。 Microsoft Teamsのコンテンツをアーカイブするための組み込みの機能に加えて、顧客とパートナーはTeamsエクスポート API を使用して、カスタム アプリケーションと統合のシナリオを解決できるようになりました。 Teams エクスポート API では、Teams メッセージとメッセージ添付ファイルの一括エクスポート (1 秒あたり最大 200 要求/アプリ/テナントあたり) がサポートされます。 削除されたメッセージには、削除後最大 30 日間 API からアクセスできます。 これらのTeamsエクスポート API とアプリケーションで使用する方法の詳細については、「[Microsoft Teams Export API を使用してコンテンツをエクスポートする」を](/microsoftteams/export-teams-content)参照してください。

Teamsエクスポート API の使用に関するライセンス要件については、[セキュリティ&コンプライアンスに関するMicrosoft 365ライセンスガイダンスを](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)参照してください。

### <a name="microsoft-graph-connector-apis-preview"></a>Microsoft Graph コネクタ API (プレビュー)

[Microsoft Graph コネクタ](/microsoftsearch/connectors-overview)を使用すると、組織はサード パーティのデータにインデックスを付けて、結果Microsoft Search表示できます。 この機能は、Microsoft 365 の生産性向上アプリと Microsoft の広範なエコシステムで検索可能な、コンテンツ ソースの種類を拡大しています。 サード パーティのデータは、オンプレミスまたはパブリッククラウドまたはプライベート クラウドでホストできます。 電子情報開示 (プレミアム) 以降では、Microsoft 365接続されたアプリの組み込みのコンプライアンス値の開発者プレビューが有効になります。 これにより、アプリのコンプライアンスがMicrosoft 365 エコシステムに統合され、シームレスなコンプライアンス エクスペリエンスをユーザーに提供できるようになります。 Microsoft Graph Connector API をアプリ ビューに組み込む方法の詳細については、[Microsoft Graphの接続の作成、更新、削除に関するページを](/graph/connecting-external-content-connectors-api-overview)参照してください。
