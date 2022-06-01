---
title: MRS サービス アラート
ms.author: kvice
author: kelleyvice-msft
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
description: メールボックス移行サービス アドバイザリを使用して、組織内のメールボックス移行要求の遅延を監視します。
ms.openlocfilehash: fe6f60b75fb7d27781d442faf82ff981ac54808a
ms.sourcegitcommit: aff1732dfa21e9283b173d8e5ca5bcbeeaaa26d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2022
ms.locfileid: "65810739"
---
# <a name="service-advisories-for-mrs-source-delays-in-exchange-online-monitoring"></a>Exchange Online監視における MRS ソースの遅延に関するサービス アドバイザリ

メールボックス レプリケーション サービス (MRS) ソース遅延サービス アドバイザリは、Microsoft 365組織内のメールボックスの移行が遅れる可能性があるテナント側 (移行元) の記憶域の制限またはプロセッサ使用率の高い問題を通知します。 これらのサービス アドバイザリには、これらの問題の解決に役立つ Microsoft リソースへのリンクも含まれています。

これらのサービス アドバイザリは、Microsoft 365 管理センターに表示されます。 これらのサービス アドバイザリを表示するには <a href="https://go.microsoft.com/fwlink/p/?linkid=842900" target="_blank">**、[**</a>**正常性** > サービス正常性] に移動 **しExchange Online** > [**アクティブな問題**] タブをクリックします。

## <a name="what-do-these-service-advisories-indicate"></a>これらのサービス アドバイザリは何を示していますか?

このサービス アドバイザリは、組織内のメールボックス移行の遅延の可能性を通知します。 これには、フォレスト間の移行、移行のオンボード、オフボード移行が含まれます。 サービス アドバイザリには、組織内の現在の移行に関する情報を含むテーブルが含まれています。 移行の遅延に関する情報を含むテーブルの例を次に示します。

| BatchGuid | ExchangeGuid | RequestGuid | DelayReason |QueuedHours | DelayInHours | SourceServer | RemoteDatabaseName |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|12345678-1234-1234-1234-1234567891011|246c21f7-ca3c-4bba-ab5d-23456558c52a|3d7fab16-7d8e-4c81-a849-e0795054292a|DiskLatency|35.2|27.3|RD1GBL01EXCH003|GBL01EDAG001-db002|
|87654321-4321-4321-4321-1101987654321|21e9a608-78c3-44ef-a4dd-d5e7222aae82|9974aeb4-2aa4-4a2c-aeb6-d94d78cc25c9|DiskLatency|0.4|0.9|RD1GBL01EXCH010|GBL01EDAG010-db003|

次の一覧では、前の例の各列について説明します。

- **BatchGuid**: 移行ジョブの一意の GUID。

- **ExchangeGuid**: 移行するユーザー メールボックスのグローバル一意識別子 (GUID)。

- **RequestGuid**: 移行要求の GUID。

- **DelayReason**: 移行の遅延の理由。

- **QueueHours**: 移行がキューに登録されて待機している期間。

- **DelayInHours**: 移行が遅延した期間。

- **SourceServer**: 移行元のオンプレミス サーバー。

- **RemoteDatabaseName**: 移行元のデータベース名。

## <a name="more-information"></a>詳細情報

MRS とメールボックスの移行の詳細については、次の記事を参照してください。

- [Exchangeでのメールボックスの移動](/exchange/recipients/mailbox-moves)

- [移行のパフォーマンスとベスト プラクティスのMicrosoft 365とOffice 365](/exchange/mailbox-migration/office-365-migration-best-practices)

- [メールボックス移行のパフォーマンス分析](https://techcommunity.microsoft.com/t5/exchange-team-blog/mailbox-migration-performance-analysis/ba-p/587134)

- [移行速度の低下のトラブルシューティング](https://techcommunity.microsoft.com/t5/exchange-team-blog/troubleshooting-slow-migrations/ba-p/1795706)

- [複数のメール アカウントを Microsoft 365 に移行する方法](/exchange/mailbox-migration/mailbox-migration)。
