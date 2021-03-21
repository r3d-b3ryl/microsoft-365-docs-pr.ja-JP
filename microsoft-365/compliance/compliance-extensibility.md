---
title: Microsoft 365 コンプライアンスの拡張
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
description: サードパーティのデータ コネクタと Microsoft Graph API を使用した Microsoft 365 コンプライアンス ソリューションの拡張について説明します。
ms.openlocfilehash: 676c0ba41e517dd0c3692fec29a1d4034641b634
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919723"
---
# <a name="microsoft-365-compliance-extensibility"></a>Microsoft 365 コンプライアンスの拡張

Microsoft 365 コンプライアンス ソリューションは、組織がコンプライアンス リスクをインテリジェントに評価し、機密データを管理および保護し、規制要件に効果的に対応するのに役立ちます。 Microsoft 365 コンプライアンスは拡張性のシナリオに富み、組織はコンプライアンス ソリューションの適応、拡張、統合、加速、サポートを行えます。

コンプライアンスの機能拡張には、次の 2 つの重要な構成要素があります。

- **データ コネクタ**。 Microsoft 365 以外のデータをインポートおよびアーカイブして、Microsoft 365 の保護とガバナンス機能をサードパーティのデータに適用するために使用します。

- **API**. Microsoft 365 コンプライアンス機能へのプログラムによるアクセスを有効にする。

## <a name="data-connectors"></a>データ コネクタ

Microsoft は、Microsoft 365 コンプライアンス センターで構成できるサード パーティ製のデータ コネクタを提供します。 Microsoft が提供するデータ コネクタの一覧については、「サード パーティ製データ コネクタ」 [の表を参照](archiving-third-party-data.md#third-party-data-connectors) してください。 サード パーティ製のデータ コネクタの表には、Microsoft 365 でデータをインポートおよびアーカイブした後にサード パーティのデータに適用できるコンプライアンス ソリューションと、各コネクタの手順に従った手順へのリンクも示されています。

Microsoft 365 データ コネクタの詳細については、「サードパーティ データのアーカイブ [」を参照してください](archiving-third-party-data.md)。 Microsoft 365 コンプライアンス センターで使用できるデータ コネクタでサード パーティ製のデータ型がサポートされていない場合は、カスタム コネクタを提供できるパートナーと一緒に作業できます。 この方法で作業できるパートナーの一覧と、この方法の手順については、「パートナーと協力してサード パーティのデータをアーカイブする」 [を参照してください](work-with-partner-to-archive-third-party-data.md)。

### <a name="prerequisites-for-data-connectors"></a>データ コネクタの前提条件

サード パーティのデータをインポートおよびアーカイブするために Microsoft 365 コンプライアンス センターで使用できるデータ コネクタの多くは、サードパーティのデータ ソースで構成タスクを準備して実行する必要があります。 これらの前提条件は、サードパーティのデータ コネクタごとに詳細に説明されています。

Microsoft のパートナーの 1 つによって提供される Microsoft 365 コンプライアンス センターのデータ コネクタの場合、コネクタを展開する前に、組織はパートナーとのビジネス関係を必要とします。

サード パーティ製データ コネクタのライセンス要件については [、Microsoft 365 コンプライアンス](/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx) ライセンス比較ドキュメントを参照してください。

## <a name="apis"></a>API

Microsoft 365 コンプライアンス API は、Microsoft Information Protection SDK、Microsoft Graph API、および Office 365 管理アクティビティ API で利用できます。 一部のコンプライアンス API は、Microsoft 365 のお客様、独立したソフトウェア ベンダー、システム インテグレーター、およびマネージド セキュリティ サービス プロバイダーの開発者が価値の高いセキュリティおよびコンプライアンス ソリューションを構築できる新しいセキュリティおよびコンプライアンス API の一部です。

Graph API にアクセスする方法の詳細については、「Overview [of Microsoft Graph」を参照してください](/graph/overview)。

### <a name="microsoft-information-protection-mip-sdk"></a>Microsoft Information Protection (MIP) SDK

MIP SDK は、Microsoft 365 セキュリティ/コンプライアンス センターからのラベル付けおよび保護サービスをサードパーティのアプリケーションとサービスに公開します。 開発者は、SDK を使用して、ファイルにラベルと保護を適用するためのネイティブ サポートを構築できます。 開発者は、特定のラベルが検出された場合に実行するアクションと、MIP で暗号化された情報に対する理由を決定できます。

高レベルの MIP SDK の使用例は次のとおりです。

- エクスポート時に分類ラベルをファイルに適用する業務行アプリケーション。

- MIP ラベル付けのためのネイティブ サポートを提供する CAD/CAM 設計アプリケーション。

- Azure Information Protection を使用してデータを暗号化できるクラウド アクセス セキュリティ ブローカーまたはデータ損失防止ソリューション。

MIP SDK、前提条件、追加シナリオ、およびサンプルの詳細については [、「MIP SDK の概要」を参照してください](/information-protection/develop/overview)。

### <a name="microsoft-graph-api-for-teams-dlp"></a>Microsoft Graph API for Teams DLP

[データ損失防止 (DLP)](dlp-microsoft-teams.md) 機能は、特に組織がリモート作業に移行する中で、Microsoft Teams で広く使用されています。 今年の初めに [、Teams](https://developer.microsoft.com/graph/blogs/announcing-change-notifications-for-microsoft-teams-messages/) のメッセージに関する Microsoft Graph 変更通知 API のパブリック プレビューを発表しました。 この API を使用すると、開発者は Microsoft Teams メッセージをほぼリアルタイムでリッスンし、顧客とパートナーの両方に DLP シナリオを実装できるアプリを構築できます。 さらに、Microsoft Graph Patch API では、Teams メッセージに DLP アクションを適用できます。

これら 2 つの API は、Microsoft Graph API for Teams DLP を形成します。 サンプル アプリを試して開始 [できます](https://github.com/microsoftgraph/csharp-webhook-with-resource-data)。 Microsoft Teams メッセージング Webhook の詳細については、ドキュメントを参照 [してください](/graph/api/subscription-post-subscriptions)。

Teams DLP のライセンス要件については [、「Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-data-loss-prevention-for-teams)ライセンス ガイダンス」を参照して、セキュリティとコンプライアンス&してください。

### <a name="microsoft-graph-api-for-ediscovery-preview"></a>Microsoft Graph API for eDiscovery (プレビュー)

[Advanced eDiscovery](overview-ediscovery-20.md)を使用すると、組織は、データが Microsoft 365 のセキュリティとコンプライアンスの境界内にとどまっている間、データを関連するセットに対して削減するインテリジェントな機械学習機能と分析機能を備え、その場所にあるデータを検出し、より多くのエンドツーエンドの電子情報開示ワークフローを管理できます。

高度な電子情報開示のグラフ API を使用すると、ケースの作成と管理、セットのレビュー、セットクエリのレビューを、スケーラブルで繰り返し可能な方法で行えます。 これにより、顧客とパートナーはアプリとワークフローを作成して、ケースの作成や保管担当者や法的ホールドの管理など、一般的で繰り返しのプロセスを自動化できます。

電子情報開示用のグラフ API の最初のセットは、パブリック プレビューで使用できます。 暦年の終わりまでに、より多くの機能を追加する予定です。 高度な電子情報開示のこれらの API と他の更新プログラムの詳細については、このブログを参照 [してください](https://aka.ms/Ignite2020AeDAA)。

Advanced eDiscovery と API のライセンス要件については、セキュリティとコンプライアンスに関する Microsoft [365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery)ライセンス ガイダンスの「電子情報開示」セクション&してください。

### <a name="microsoft-graph-api-for-teams-export-preview"></a>Microsoft Graph API for Teams エクスポート (プレビュー)

Microsoft Teams のエンタープライズ 情報アーカイブ (EIA) は、規制要件を解決できるお客様の重要なシナリオです。 Microsoft Teams のコンテンツをアーカイブするための組み込みの機能に加えて、顧客とパートナーは Teams エクスポート API を使用して、カスタム アプリケーションと統合のシナリオを解決できます。 Teams エクスポート API は、Teams メッセージとメッセージ添付ファイルの一括エクスポート (アプリごとに 1 秒/テナントあたり最大 200 要求) をサポートします。 削除されたメッセージは、削除後最大 30 日間 API からアクセスすることもできます。 これらの Teams エクスポート API の詳細とアプリケーションでの使用方法については、「Microsoft Teams エクスポート API を使用してコンテンツをエクスポートする」 [を参照してください](/microsoftteams/export-teams-content)。

Teams エクスポート API の使用に関するライセンス要件については [、「Microsoft 36 & 5](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)ライセンス ガイダンス」を参照してください。