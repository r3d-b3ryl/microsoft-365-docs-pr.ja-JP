---
title: パートナーの管理特権を確認する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
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
description: Microsoft 認定ソリューション プロバイダー (パートナー) の一覧を確認して、持っている管理者特権と、それらの特権を削除する方法を確認する方法について説明します。
ms.date: 12/03/2021
ms.openlocfilehash: 7dc0a52526da1f0da9cd85b438b6f30b798c2dfa
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2021
ms.locfileid: "61302509"
---
# <a name="review-partner-administrative-privileges"></a>パートナーの管理特権を確認する

Microsoft 認定クラウド ソリューション プロバイダー (リセラー パートナー) をお持ちの場合は、委任された管理特権 (DAP) が割り当てられているか四半期ごとに確認することをお勧めします。 組織は、このパートナーが組織のデータにアクセスし、代わりに購入を行う必要があります。

> [!IMPORTANT]
> グローバル管理者のアクセス許可を含む DAP を任意のパートナーに付与すると、セキュリティ リスクが生じ得る可能性があります。 グローバル管理者が多すぎると、セキュリティリスクも伴います。 [委任された特権を対象とした最近のアクティビティの詳細については、次のリンクを参照してください](https://www.microsoft.com/security/blog/2021/10/25/nobelium-targeting-delegated-administrative-privileges-to-facilitate-broader-attacks/)。

リセラー パートナーから DAP 契約に同意すると、組織のグローバル管理者の役割を従業員に割り当てできます。 グローバル管理者ロールを使用すると、パートナーの従業員は従業員の個人データや他の機密情報にアクセスできます。 また、次のようなテナント全体のアクションを実行するためのアクセス許可も付与されます。

- ユーザー パスワードの変更
- メール アカウントを使用したユーザーの追加
- 組織に関連付けられた Web ドメインの追加と管理

DAP を有効にすると、パートナーが追加できるグローバル管理者の数を制御できません。 アカウントへのパートナー DAP (グローバル管理者) アクセスのみを許可または拒否できます。

## <a name="review-and-remove-roles-from-partners"></a>パートナーからのロールの確認と削除

1. [パートナー Microsoft 365 管理センター]**ページ設定**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">移動</a>します。 DAP を持つパートナーには **、[役割]** 列にグローバル管理者が **表示** されます。
2. グローバル管理者の役割をパートナーから削除するには、削除するパートナーの名前を見つける必要があります。
3. リセラーをリレーションシップの **種類として** 含む行 **を選択します**。
4. パートナーの詳細ページで、[役割の削除] **を選択し**、[はい] を **選択します**。

> [!NOTE]
>
> - パートナーから DAP (グローバル管理者の役割) を削除する場合は、今後のサービス配信について説明するために、パートナーに問い合わせすることをお勧めします。 たとえば、低い権限を持つユーザー アカウントを作成し、そのアカウント情報をパートナーと共有できます。 ユーザーの追加と [管理者ロールの](../admin/add-users/add-users.md) 割り当 [てについて詳しくは、を参照してください](../admin/add-users/assign-admin-roles.md)。
> - グローバル管理者ロールが削除された場合でも、パートナーは代理で購入できます。 パートナー センターで、その機能を削除する必要がある場合は、パートナーに問い合わせすることをお勧めします。

## <a name="related-content"></a>関連コンテンツ

[パートナー関係の管理](manage-partners.md) (記事)\
[管理者の役割について](../admin/add-users/about-admin-roles.md) (記事)\
[管理者特権の委任 (Azure AD)](/partner-center/customers-revoke-admin-privileges#delegated-admin-privileges-in-azure-ad)
