---
title: Microsoft 365 コンプライアンス拡張機能
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: サードパーティのデータコネクタと Microsoft Graph Api を使用して、Microsoft 365 コンプライアンスソリューションを拡張する方法について説明します。
ms.openlocfilehash: 8eeb83013ec412ed82973b37c4c10e2250f5eaf8
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285743"
---
# <a name="microsoft-365-compliance-extensibility"></a>Microsoft 365 コンプライアンス拡張機能

Microsoft 365 コンプライアンスソリューションは、組織がコンプライアンスリスクをインテリジェントに評価し、機密データを管理および保護し、規制要件に効果的に対応するのに役立ちます。 Microsoft 365 コンプライアンスは、拡張性のシナリオにおいて豊富で、組織がコンプライアンスソリューションを適応、拡張、統合、促進、サポートすることができます。

コンプライアンスの拡張性には、次の2つの主要な構成要素があります。

- **データコネクタ**。 マイクロソフト以外のデータをインポートおよびアーカイブするために使用します。これにより、Microsoft 365 の保護およびガバナンス機能をサードパーティのデータに適用できるようになります。

- **Api**。 Microsoft 365 コンプライアンス機能へのプログラムによるアクセスを可能にします。

## <a name="data-connectors"></a>データコネクタ

Microsoft は、Microsoft 365 コンプライアンスセンターで構成できるサードパーティのデータコネクタを提供しています。 Microsoft によって提供されるデータコネクタの一覧については、 [サードパーティのデータコネクタ](archiving-third-party-data.md#third-party-data-connectors) の表を参照してください。 サードパーティのデータコネクタの表には、Microsoft 365 でデータをインポートおよびアーカイブした後にサードパーティのデータに適用できるコンプライアンスソリューションの概要と、各コネクタのステップごとの手順へのリンクも含まれています。

Microsoft 365 データコネクタの詳細については、「 [サードパーティのデータをアーカイブ](archiving-third-party-data.md)する」を参照してください。 Microsoft 365 コンプライアンスセンターで利用可能なデータコネクタでサードパーティのデータ型がサポートされていない場合は、カスタムコネクタを提供できるパートナーと連携することができます。 この方法で操作できるパートナーの一覧と、この方法のステップバイステップのプロセスについては、「 [パートナーと連携してサードパーティのデータをアーカイブする](work-with-partner-to-archive-third-party-data.md)」を参照してください。

### <a name="prerequisites-for-data-connectors"></a>データコネクタの前提条件

Microsoft 365 コンプライアンスセンターで使用可能なデータコネクタの多くは、サードパーティのデータをインポートしてアーカイブするために、サードパーティのデータソースの構成タスクを準備して実行する必要があります。 これらの前提条件は、サードパーティのデータコネクタごとに詳細に説明されています。

Microsoft のパートナーの1つによって提供される Microsoft 365 コンプライアンスセンターのデータコネクタでは、コネクタを展開する前に、組織にパートナーとのビジネス関係を持たせる必要があります。

サードパーティのデータコネクタのライセンス要件については、 [Microsoft 365 コンプライアンスライセンスの比較](https://docs.microsoft.com/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx) に関するドキュメントを参照してください。

## <a name="apis"></a>API

Microsoft 365 コンプライアンス Api は、Microsoft Information Protection SDK、Microsoft Graph API、および Office 365 Management Activity API で利用できます。 一部のコンプライアンス Api は、新しいセキュリティおよびコンプライアンス Api の一部であり、Microsoft 365 のお客様、独立系ソフトウェアベンダー、システムインテグレーター、および管理セキュリティサービスプロバイダーの開発者が、高価値のセキュリティおよびコンプライアンスソリューションを構築できるようにします。

Graph Api へのアクセス方法の詳細については、「 [Microsoft graph の概要](https://docs.microsoft.com/graph/overview)」を参照してください。

### <a name="microsoft-information-protection-mip-sdk"></a>Microsoft Information Protection (MIP) SDK

MIP SDK は、Microsoft 365 セキュリティ/コンプライアンスセンターからサードパーティのアプリケーションおよびサービスへのラベル付けおよび保護サービスを公開します。 開発者は SDK を使用して、ラベルを適用し、ファイルに保護するためのネイティブサポートを構築できます。 開発者は、特定のラベルが検出されたときに実行するアクションと、MIP で暗号化された情報を確認できます。

高レベルの MIP SDK ユースケースは次のとおりです。

- エクスポート時に分類ラベルをファイルに適用する基幹業務アプリケーション。

- MIP ラベルのネイティブサポートを提供する CAD/CAM 設計アプリケーション。

- Azure Information Protection を使用してデータを暗号化できる、クラウドアクセスセキュリティブローカーまたはデータ損失防止ソリューション。

MIP SDK、前提条件、その他のシナリオ、およびサンプルの詳細については、「 [MIP sdk の概要](https://docs.microsoft.com/information-protection/develop/overview)」を参照してください。

### <a name="microsoft-graph-api-for-teams-dlp"></a>Microsoft Graph API for Teams DLP

Microsoft Teams では、[データ損失防止 (DLP)](dlp-microsoft-teams.md)機能がよく使用されています。これは、組織がリモート作業に移行したためです。 今年前半に、Teams のメッセージに関する Microsoft Graph 変更通知 API の [パブリックプレビューを発表しました](https://developer.microsoft.com/graph/blogs/announcing-change-notifications-for-microsoft-teams-messages/) 。 この API を使用すると、開発者は、Microsoft Teams のメッセージをほぼリアルタイムで聞いて、顧客とパートナーの両方に DLP シナリオを実装できるアプリを構築できます。 さらに、Microsoft Graph Patch API を使用すると、Teams メッセージに DLP アクションを適用することができます。

これら2つの Api は、Teams DLP 用の Microsoft Graph API を形成しています。 最初に、 [サンプルアプリ](https://github.com/microsoftgraph/csharp-webhook-with-resource-data)を試してみることができます。 Microsoft Teams メッセージングの webhooks の詳細については、 [ドキュメント](https://docs.microsoft.com/graph/api/subscription-post-subscriptions)を参照してください。

Teams DLP のライセンス要件については、「 [Microsoft 365 licensing ガイダンス for security & 法令遵守](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-data-loss-prevention-for-teams)」を参照してください。

### <a name="microsoft-graph-api-for-ediscovery-preview"></a>電子情報開示のための Microsoft Graph API (プレビュー)

[高度な電子情報開示](overview-ediscovery-20.md)を使用すると、組織はそれが存在するデータを検出し、インテリジェントな機械学習および分析機能を使用してより多くのエンドツーエンドの電子情報開示ワークフローを管理することにより、データが Microsoft 365 のセキュリティおよびコンプライアンスの境界内にある間、関連するセットにデータを削減することができます。

高度な電子情報開示のための Graph Api を使用して、ケースの作成と管理、およびセットクエリの、拡張性のある反復可能な方法での確認を行うことができます。 これにより、顧客やパートナーは、アプリやワークフローを作成して、ケースの作成や保管担当者および法的保持の管理などの一般的で反復的なプロセスを自動化することができます。

電子情報開示用の Graph Api の最初のセットは、パブリックプレビューで入手できます。 カレンダー年の終わりまでに、さらに多くの機能を追加することを計画しています。 詳細な電子情報開示のためのこれらの Api とその他の更新プログラムの詳細については、この [ブログ](https://aka.ms/Ignite2020AeDAA)を参照してください。

高度な電子情報開示と API のライセンス要件については、「 [Microsoft 365 のライセンスガイダンス」の「セキュリティ & のコンプライアンス](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery)」の「電子情報開示」セクションを参照してください。

### <a name="microsoft-graph-api-for-teams-export-preview"></a>Microsoft Graph API for Teams エクスポート (プレビュー)

Microsoft Teams のエンタープライズ情報アーカイブ (EIA) は、お客様が規制要件を解決できるようにするための主要なシナリオです。 Microsoft Teams のコンテンツをアーカイブするための組み込み機能に加えて、お客様とパートナーは Teams エクスポート Api を使用して、カスタムのアプリケーションと統合のシナリオを解決できるようになりました。 Teams のエクスポート Api は、Teams メッセージおよびメッセージの添付ファイルの一括エクスポート (最大200の要求数/アプリ/テナントごと) をサポートしています。 削除されたメッセージは、削除後30日以内、API によってもアクセスできます。 これらの Teams の詳細については、「 [Microsoft Teams エクスポート api](https://docs.microsoft.com/microsoftteams/export-teams-content)を使用してコンテンツをエクスポートする」を参照してください。

Teams エクスポート Api を使用するためのライセンス要件については、「 [Microsoft 365 licensing ガイダンス for security & 法令遵守](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)」を参照してください。
