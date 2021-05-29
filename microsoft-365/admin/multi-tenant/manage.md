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
description: 1 つの場所からテナントを管理する機能を提供するテナント スイッチアビューとマルチテナント ビューを使用する方法について学習します。
ms.openlocfilehash: e0bf6c872d4998c0cd0263fd8474ac5e9c99ef14
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706156"
---
# <a name="multi-tenant-management"></a>マルチテナント管理

マルチテナント管理は、パートナー管理者が管理しているすべてのテナントを 1 つの場所から管理Microsoft 365できる、統合された形式の管理を提供します。 複数のテナントを管理するパートナーの場合は、次の処理を実行できます。

- 管理するテナント間をすばやく移動します。
- 複数のテナントでサービスの正常性、製品、請求を評価します。
- [ **すべてのテナント]** ページで、すべてのテナントのサービスの正常性、開いているサービス要求、製品と課金、そのテナント内のユーザー数をすばやく確認できます。

## <a name="move-between-tenants"></a>テナント間の移動

1. 管理センター Microsoft 365組織名を選択します。

    :::image type="content" source="../../media/macorgswitcher.png" alt-text="マルチテナント スイッチを使用します。":::

- テナント スイッチ **を使用すると**、管理するテナント間ですばやく移動できます。

    :::image type="content" source="../../media/yourtenantslist.png" alt-text="検索機能を備え、テナントの一覧を表示します。":::

## <a name="view-all-tenants-page"></a>[すべてのテナントの表示] ページ

1. 管理センター Microsoft 365左側のナビゲーションで、[すべてのテナント]**を選択します**。
- [すべての **テナント] ページ** で、次の方法を実行できます。
  - サービスの正常性を評価する
  - ライセンスの使用状況を確認する
  - 管理するテナントを検索または選択する
  - 最も頻繁にアクセスするテナントをリストの一番上にピン留めできます。

テナントをお気に入りとしてマークした場合は、自動的に展開され、状態の詳細をすぐに表示できます。

## <a name="view-service-health-for-all-accounts"></a>すべてのアカウントのサービス正常性の表示

サービス正常性ビューには、テナントに影響を与えるインシデントやアドバイザリが表示されます。 また、影響を受ける管理テナントの数も示されます。

1. 管理センター Microsoft 365マルチテナント ビューで、[サービス正常性]**を選択します**。
2. [ **サービス正常性]** ページの集計ビューでは、インシデントの総数、管理テナントに影響を与えるアドバイザリの総数、アクティブなインシデントを持つサービスの数も確認できます。 また、インシデントやアドバイザリの影響を受けるテナントの数も確認できます。

    - フィルター オプションを使用して、問題の種類またはサービス別に問題を表示できます。

    - [すべてのサービス] タブまたは [すべての問題] タブ **で****問題を確認** できます。

    :::image type="content" source="../../media/multitenant-servicehealth.png" alt-text="マルチテナント サービスの正常性ページ。":::
1. [すべてのサービス] タブまたは **[すべての** 問題] タブでインシデントを選択し、[概要] タブでインシデントの詳細を **取得** します。[影響 **を受けるテナント] タブ** を選択して、影響を受けるテナントの一覧を取得します。

    :::image type="content" source="../../media/tenantsaffected.png" alt-text="サービス正常性の問題の影響を受けるテナントの一覧。":::

影響を受けるテナントの一覧を CSV 形式にエクスポートして、管理者がサポート チームと共有できます。

## <a name="view-a-single-tenant-in-the-microsoft-365-admin-center"></a>管理センターで 1 つのテナントMicrosoft 365表示する

[すべてのテナント] ページMicrosoft 365任意のテナントの管理センター **に戻** ります。

1. [すべての **テナント] ページ** で、管理センターを表示するテナント名を選択します。
2. そのテナントの管理センターに移動します。