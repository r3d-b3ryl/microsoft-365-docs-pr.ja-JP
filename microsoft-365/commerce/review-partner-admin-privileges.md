---
title: パートナーの管理特権を確認する
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: jamitche, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_subscriptions
search.appverid: MET150
description: Microsoft 認定ソリューション プロバイダー (パートナー) の一覧を確認して、ユーザーが持つ管理者特権と、それらの特権を削除する方法を確認する方法について説明します。
ms.date: 12/03/2021
ms.openlocfilehash: 067716689bd82e67dda357d675383ef2541b1dc3
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63318425"
---
# <a name="review-partner-administrative-privileges"></a>パートナーの管理特権を確認する

Microsoft 認定のクラウド ソリューション プロバイダー (リセラー パートナー) をお持ちのお客様は、委任された管理特権 (DAP) が割り当てられていることを四半期ごとに確認することをお勧めします。 組織がこのパートナーに組織のデータにアクセスし、ユーザーに代わって購入することを望んでいることを確認します。

> [!IMPORTANT]
> グローバル管理者アクセス許可を含む DAP をパートナーに付与すると、セキュリティ リスクが発生する可能性があります。 グローバル管理者の数が多すぎることも、セキュリティ 上のリスクです。 [委任された特権を対象とする最近のアクティビティの詳細について説明します](https://www.microsoft.com/security/blog/2021/10/25/nobelium-targeting-delegated-administrative-privileges-to-facilitate-broader-attacks/)。

リセラー パートナーから DAP 契約に同意すると、組織のグローバル管理者ロールを従業員に割り当てることができます。 グローバル管理者ロールは、パートナーの従業員が従業員の個人データやその他の機密情報にアクセスできるようにします。 また、次のようなテナント全体のアクションを実行するアクセス許可も付与されます。

- ユーザー パスワードの変更
- 電子メール アカウントを持つユーザーを追加する
- 組織に関連付けられた Web ドメインの追加と管理

DAP が有効になっている場合、パートナーが追加できるグローバル管理者の数を制御することはできません。 アカウントへのパートナー DAP (グローバル管理者) アクセスのみを許可または拒否できます。

## <a name="review-and-remove-roles-from-partners"></a>パートナーのロールを確認して削除する

1. Microsoft 365 管理センターで、**設定** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">Partner リレーションシップ</a> ページに移動します。 DAP のパートナーには、[**ロール**] 列に **グローバル管理者** が表示されます。
2. グローバル管理者ロールをパートナーから削除するには、削除するパートナーの名前を見つけます。
3. **リレーションシップの種類** として **Reseller** を含む行を選択します。
4. パートナーの詳細ページで、[ **ロールの削除**] を選択し、[ **はい**] を選択します。

> [!NOTE]
>
> - パートナーから DAP (グローバル管理者ロール) を削除する場合は、今後のサービス配信について話し合うために、パートナーに連絡することをお勧めします。 たとえば、より低い特権を持つユーザー アカウントを作成し、そのアカウント情報をパートナーと共有できます。 [ユーザーの追加](../admin/add-users/add-users.md)と[管理者ロールの割り当ての](../admin/add-users/assign-admin-roles.md)詳細について説明します。
> - グローバル管理者ロールが削除されても、パートナーは代理で購入を行うことができます。 パートナー センターでその機能を削除するようパートナーに依頼することをお勧めします。

## <a name="related-content"></a>関連コンテンツ

[パートナー関係の管理](manage-partners.md) (記事)\
[管理者ロールについて](../admin/add-users/about-admin-roles.md) (記事)\
[Azure ADの委任された管理者特権](/partner-center/customers-revoke-admin-privileges#delegated-admin-privileges-in-azure-ad) (記事)
