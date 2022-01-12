---
title: MRS サービス通知
ms.author: markjjo
author: markjjo
manager: scotv
ms.date: ''
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appveyor:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- NOCSH
description: メールボックス移行サービスの通知を使用して、組織内のメールボックス移行要求の遅延を監視します。
ms.openlocfilehash: 25c569030bd5da914dc6eb7ec0e58ebadfe4d766
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2022
ms.locfileid: "61937893"
---
# <a name="service-alerts-for-mrs-source-delays-in-exchange-online-monitoring"></a>監視の MRS ソース遅延に対するサービスExchange Online通知

メールボックス レプリケーション サービス (MRS) ソース遅延サービスアラートは、Microsoft 365 組織でのメールボックスの移行を遅らせる可能性があるテナント側 (移行ソース) の記憶域の制限やプロセッサ使用率の高い問題を通知します。 これらのサービス通知には、これらの問題の解決に役立つ Microsoft リソースへのリンクも含まれています。

これらのサービス通知は、サービス ウィンドウにMicrosoft 365 管理センター。 これらのサービス通知を表示するには、[**正常性** サービスの正常性] Exchange Online[アクティブな問題]  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842900" target="_blank"></a>  >  **タブをクリック** します。

## <a name="what-do-these-service-alerts-indicate"></a>これらのサービスアラートは何を示していますか?

このサービスアラートは、組織内のメールボックスの移行に遅延が生じ得る可能性を通知します。 これには、フォレスト間の移行、オンボーディング移行、およびオフボード移行が含まれます。 サービスアラートには、組織内の現在の移行に関する情報を含むテーブルが含まれている。 移行の遅延に関する情報を含む表の例を次に示します。

| BatchName | ExchangeGuid | RequestGuid | DelayReason |QueuedHours | DelayInHours | SourceServer | RemoteDatabaseName |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|MRS 移行|246c21f7-ca3c-4bba-ab5d-23456558c52a|3d7fab16-7d8e-4c81-a849-e0795054292a|DiskLatency|35.2|27.3|RD1GBL01EXCH003|GBL01EDAG001-db002|
|MRS テナントの監視|21e9a608-78c3-44ef-a4dd-d5e7222aae82|9974aeb4-2aa4-4a2c-aeb6-d94d78cc25c9|DiskLatency|0.4|0.9|RD1GBL01EXCH010|GBL01EDAG010-db003|

次の一覧では、前の例の各列について説明します。

- **BatchName**: 移行ジョブの一意の名前。

- **ExchangeGuid**: 移行中のユーザー メールボックスのグローバル一意識別子 (GUID) です。

- **RequestGuid**: 移行要求の GUID。

- **DelayReason**: 遅延移行の理由。

- **QueueHours**: 移行がキューに入れ、待機している期間。

- **DelayInHours**: 移行が遅延した期間。

- **SourceServer**: 移行元のオンプレミス サーバー。

- **RemoteDatabaseName**: 移行元のデータベース名。

## <a name="more-information"></a>詳細

MRS とメールボックスの移行の詳細については、次の記事を参照してください。

- [メールボックスの移動は、Exchange](/exchange/recipients/mailbox-moves)

- [Microsoft 365とOffice 365とベスト プラクティス](/exchange/mailbox-migration/office-365-migration-best-practices)

- [メールボックス移行のパフォーマンス分析](https://techcommunity.microsoft.com/t5/exchange-team-blog/mailbox-migration-performance-analysis/ba-p/587134)

- [低速移行のトラブルシューティング](https://techcommunity.microsoft.com/t5/exchange-team-blog/troubleshooting-slow-migrations/ba-p/1795706)

- [複数のメール アカウントを Microsoft 365 に移行する方法](/exchange/mailbox-migration/mailbox-migration)。
