---
title: 複数のテナントの管理
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
description: テナント スイッチャーとマルチテナント ビューを使用して、単一の場所からテナントを管理する機能を提供する方法について説明します。
ms.openlocfilehash: 0058bdb45b42e2c67b96ff3e30ce1cd04e5658b2
ms.sourcegitcommit: 1c5f9d17a8b095cd88b23f4874539adc3ae021de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2022
ms.locfileid: "64713957"
---
# <a name="multi-tenant-management"></a>マルチテナント管理

マルチテナント管理は、Microsoft 365 パートナー管理者が管理するすべてのテナントを 1 つの場所から管理できる統合された形式の管理を提供します。 代理管理者ロールを持ち、複数のテナントを管理するパートナーの場合は、次のことができます。

- 管理するテナント間をすばやく移動します。
- サービスの正常性、製品、および複数のテナント間の課金を評価します。
- **[すべてのテナント**] ページで、すべてのテナントのサービスの正常性、開いているサービス要求、製品と課金、そのテナント内のユーザー数をすばやく確認できます。

## <a name="move-between-tenants"></a>テナント間の移動

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>で、組織名を選択します。

    :::image type="content" source="../../media/macorgswitcher.png" alt-text="マルチテナント スイッチャー。":::

- **テナント スイッチャー** から、管理するテナント間をすばやく移動できます。

    :::image type="content" source="../../media/yourtenantslist.png" alt-text="検索機能を使用してテナントの一覧を表示します。":::

## <a name="view-all-tenants-page"></a>[すべてのテナントの表示] ページ

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>の左側のナビゲーションで、[**すべてのテナント**] を選択します。
- **[すべてのテナント**] ページで、次の操作を行うことができます。
  - サービスの正常性を評価する
  - ライセンスの使用状況を確認する
  - 管理するテナントを検索または選択する
  - 最も頻繁にアクセスしたテナントを一覧の一番上にピン留めすることもできます。

テナントをお気に入りとしてマークした場合は、状態の詳細をすぐに表示できるように、テナントが自動的に展開されます。

## <a name="view-service-health-for-all-accounts"></a>すべてのアカウントのサービス正常性を表示する

サービス正常性ビューには、インシデントまたはアドバイザリがテナントに影響を与えるかどうかが表示されます。 影響を受けるマネージド テナントの数も示されます。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>のマルチテナント ビューで、[**Service Health**] を選択します。
2. **サービス正常性** ページ集計ビューでは、インシデントの合計数、マネージド テナントに影響を与えるアドバイザリの合計数、アクティブなインシデントを含むサービスの数も確認できます。 また、インシデントやアドバイザリの影響を受けるテナントの数も確認できます。

    - フィルター オプションを使用すると、問題の種類またはサービス別に問題を表示できます

    - [ **すべてのサービス** ] タブまたは [すべての問題] タブで **問題を** 確認できます。

    :::image type="content" source="../../media/multitenant-servicehealth.png" alt-text="マルチテナント サービス正常性 ページ。":::
1. [ **すべてのサービス** ] タブまたは [ **すべての問題** ] タブでインシデントを選択し、[ **概要** ] タブでインシデントの詳細を確認します。[ **テナントの影響を受ける** ] タブを選択して、影響を受けるテナントの一覧を取得します。

    :::image type="content" source="../../media/tenantsaffected.png" alt-text="サービス正常性の問題の影響を受けるテナントの一覧。":::

管理者がサポート チームと共有できるように、影響を受けるテナントの一覧を CSV 形式にエクスポートできます。

## <a name="view-a-single-tenant-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターで 1 つのテナントを表示する

[**すべての** テナント] ページから任意のテナントのMicrosoft 365 管理センターに戻ることができます。

1. [ **すべてのテナント** ] ページで、管理センターを表示するテナント名を選択します。
2. そのテナントの管理センターに移動します。
