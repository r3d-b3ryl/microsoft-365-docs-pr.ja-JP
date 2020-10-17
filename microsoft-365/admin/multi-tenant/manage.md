---
title: 複数のテナントを管理する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: テナントスイッチャーおよびマルチテナントビューの使用方法について説明します。
ms.openlocfilehash: 2c96a80a0095e909eff19c9172eb0709ecece942
ms.sourcegitcommit: 705915f8bf9b7c082d12a009523d8aa0670a74a1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48495881"
---
# <a name="multi-tenant-management"></a>マルチテナント管理

マルチテナント管理では、管理者が管理するすべてのテナントを1つの場所から管理できる統合された形式の管理が提供されます。 複数のテナントを管理する場合は、次のことを行うことができます。

- 管理するテナント間をすばやく移動できます。
- 複数のテナントにわたるサービスの正常性、製品、および請求を評価します。
- [ **すべてのテナント** ] ページでは、すべてのテナントのサービスの正常性、開いているサービス要求、製品と請求書、およびそのテナント内のユーザー数をすばやく確認できます。


## <a name="move-between-tenants"></a>テナント間の移動

1. Microsoft 365 管理センターで、組織名を選択します。

    :::image type="content" source="../../media/macorgswitcher.png" alt-text="マルチテナントスイッチャー。":::

- **テナントスイッチャー**から、管理するテナント間をすばやく移動できます。

    :::image type="content" source="../../media/yourtenantslist.png" alt-text="マルチテナントスイッチャー。":::

## <a name="view-all-tenants-page"></a>すべてのテナントページの表示

1. Microsoft 365 管理センターの左側のナビゲーションで、[すべての **テナント**] を選択します。
- [ **すべてのテナント** ] ページでは、
  - サービス正常性の評価
  - ライセンス使用状況を確認する
  - 管理するテナントを検索するか、選択します。
  - 最も頻繁に訪れたテナントを一覧の一番上にピン留めすることもできます。


テナントがお気に入りとしてマークされている場合は、自動的に展開され、状態の詳細をすぐに表示できるようになります。

## <a name="view-service-health-for-all-accounts"></a>すべてのアカウントのサービス正常性を表示する

サービス正常性ビューには、インシデントまたはアドバイザリがテナントに影響しているかどうかが表示されます。 また、管理されているテナントの数がどの程度影響を受けるかを知ることもできます。

1. Microsoft 365 管理センターのマルチテナントビューで、[ **サービス正常性**] を選択します。
2. [ **サービス正常性** ] ページで、[すべての **サービス** ] タブまたは [ **すべての問題** ] タブの問題を確認できます。
3. [ **すべてのサービス** ] タブまたは [ **すべての問題** ] タブでインシデントを選択し、[ **概要** ] タブでインシデントに関する詳細情報を取得します。影響を受けるテナントの一覧を取得するには、[ **影響を受けるテナント** ] タブを選択します。

    :::image type="content" source="../../media/tenantsaffected.png" alt-text="マルチテナントスイッチャー。":::

## <a name="view-a-single-tenant-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターで1つのテナントを表示する

[ **すべてのテナント** ] ページから、いずれかのテナントの Microsoft 365 管理センターに戻ることができます。

1. [ **すべてのテナント** ] ページで、管理センターを表示するテナント名をクリックします。
2. そのテナントの管理センターに転送されます。