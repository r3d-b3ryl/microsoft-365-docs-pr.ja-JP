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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: テナント スイッチを使用する方法と、マルチテナント ビューについて学習します。
ms.openlocfilehash: 21b51a5e0c79496bf73e60c04aea68def3cf8ad6
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580884"
---
# <a name="multi-tenant-management"></a>マルチテナント管理

マルチテナント管理は、管理の統合形式を提供し、管理者は管理するテナントを 1 つの場所からすべて管理できます。 複数のテナントを管理する場合は、次の処理を実行できます。

- 管理するテナント間をすばやく移動します。
- 複数のテナントでサービスの正常性、製品、請求を評価します。
- [ **すべてのテナント]** ページで、すべてのテナントのサービスの正常性、開いているサービス要求、製品と課金、そのテナント内のユーザー数をすばやく確認できます。


## <a name="move-between-tenants"></a>テナント間の移動

1. Microsoft 365 管理センターで、組織名を選択します。

    :::image type="content" source="../../media/macorgswitcher.png" alt-text="マルチテナント スイッチを使用します。":::

- テナント スイッチ **を使用すると**、管理するテナント間ですばやく移動できます。

    :::image type="content" source="../../media/yourtenantslist.png" alt-text="検索機能を備え、テナントの一覧を表示します。":::

## <a name="view-all-tenants-page"></a>[すべてのテナントの表示] ページ

1. Microsoft 365 管理センターの左側のナビゲーションで、[すべてのテナント] **を選択します**。
- [すべての **テナント] ページ** で、次の方法を実行できます。
  - サービスの正常性を評価する
  - ライセンスの使用状況を確認する
  - 管理するテナントを検索または選択する
  - 最も頻繁にアクセスするテナントをリストの一番上にピン留めできます。


テナントをお気に入りとしてマークした場合は、自動的に展開され、状態の詳細をすぐに表示できます。

## <a name="view-service-health-for-all-accounts"></a>すべてのアカウントのサービス正常性の表示

サービス正常性ビューには、テナントに影響を与えるインシデントやアドバイザリが表示されます。 また、影響を受ける管理テナントの数も示されます。

1. Microsoft 365 管理センターのマルチテナント ビューで、[サービス正常性] **を選択します**。
2. [ **サービス正常性]** ページの集計ビューでは、インシデントの総数、管理テナントに影響を与えるアドバイザリの総数、アクティブなインシデントを持つサービスの数も確認できます。 また、インシデントやアドバイザリの影響を受けるテナントの数も確認できます。
    
    - フィルター オプションを使用して、問題の種類またはサービス別に問題を表示できます。

    - [すべてのサービス] タブまたは [すべての問題] タブ **で****問題を確認** できます。

    :::image type="content" source="../../media/multitenant-servicehealth.png" alt-text="マルチテナント サービスの正常性ページ。":::
1. [すべてのサービス] タブまたは **[すべての** 問題] タブでインシデントを選択し、[概要] タブでインシデントの詳細を **取得** します。[影響 **を受けるテナント] タブ** を選択して、影響を受けるテナントの一覧を取得します。

    :::image type="content" source="../../media/tenantsaffected.png" alt-text="サービス正常性の問題の影響を受けるテナントの一覧。":::

影響を受けるテナントの一覧を CSV 形式にエクスポートして、管理者がサポート チームと共有できます。

## <a name="view-a-single-tenant-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターで 1 つのテナントを表示する

[すべてのテナント] ページから、任意のテナントの Microsoft 365 管理センター **に戻** ります。

1. [すべての **テナント] ページ** で、管理センターを表示するテナント名を選択します。
2. そのテナントの管理センターに移動します。