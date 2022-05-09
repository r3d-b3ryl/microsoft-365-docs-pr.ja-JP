---
title: Microsoft 365 管理センターに管理者ロールを割り当てる
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
- Adm_TOC
ms.custom:
- MSStore_Link
- okr_smb
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- AdminTemplateSet
- adminvideo
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: eac4d046-1afd-4f1a-85fc-8219c79e1504
description: 管理者センターで特定のタスクを実行できるように、管理者ロールをユーザーまたはビジネス内の複数のユーザーに割り当てる方法について説明します。
ms.openlocfilehash: fd38bb9ed378e6b3ffc20a79ca71eb2943599dcc
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2021
ms.locfileid: "61370622"
---
# <a name="assign-admin-roles"></a>管理者ロールを割り当てる

Microsoft ビジネス サブスクリプションを購入したユーザーは、グローバル管理者です。つまり、サブスクリプション内の製品を無制限に制御でき、ほとんどのデータにアクセスできます。

詳細については、「[管理者の役割について](about-admin-roles.md)」を参照してください。

新しいユーザーを追加するときに、管理者ロールを割り当てない場合、その *ユーザーはユーザー ロール* に含まれ、Microsoft 管理センターに対する管理者特権を持っていません。 ただし、作業の完了に関するヘルプが必要な場合は、管理者ロールをユーザーに割り当てることができます。 たとえば、パスワードのリセットに役立つユーザーが必要な場合は、グローバル管理者ロールを割り当てず、パスワード管理者ロールを割り当てる必要があります。 データやオンライン ビジネスに無制限にアクセスできるグローバル管理者が多すぎると、セキュリティ リスクが生じます。

## <a name="watch-add-an-admin"></a>ウォッチ: 管理者を追加する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

1. Microsoft 365 Business にサインアップすると、自動的にグローバル管理者になります。ビジネスを管理しやすくするために、他のユーザーを管理者にすることもできます。 
1. Microsoft 365 管理センターで、**[ユーザー]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**[アクティブなユーザー]**</a> の順に選択します。
1. 管理者にするユーザーを選択し、**[役割の管理]** を選択します。

このビデオが役に立った場合には、「[complete training series for small businesses and those new to Microsoft 365 (小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ)](../../business-video/index.yml)」をご覧ください。

## <a name="assign-admin-roles"></a>管理者ロールを割り当てる 

ユーザーをロールに割り当てるには、次の 2 つの方法があります。

- ユーザーの詳細と **ロールの管理** に移動して、ユーザーにロールを割り当てることができます。
- または、[ **ロール]** に移動してロールを選択し、そのロールに複数のユーザーを追加することもできます。

### <a name="assign-admin-roles-to-users-using-roles"></a>ロールを使用して管理者ロールをユーザーに割り当てる

1. 管理センターで、[ <a href="https://go.microsoft.com/fwlink/p/?linkid=2097861" target="_blank">**ロールの割り当て]**</a> に移動します。 **Azure AD** タブまたは **Intune** タブを選択すると、組織で使用できる管理者ロールが表示されます。
2. ユーザーを割り当てる管理者ロールを選択します。
3. [**割り当てられた adminsAdd** > ] を選択 **します**。
4. ユーザーの **表示名** または **ユーザー名** を入力し、候補の一覧からユーザーを選択します。
5. 完了するまで、複数のユーザーを追加します。
6. **[保存] を** 選択すると、ユーザーが割り当てられた管理者の一覧に追加されます。

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a>アクティブ ユーザーから管理者の役割にユーザーを割り当てる

::: moniker range="o365-worldwide"

1. 管理センターで、[ **ユーザー** > [アクティブ ユーザー](https://go.microsoft.com/fwlink/p/?linkid=834822) ] ページに移動します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、**[ユーザー]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> の順に選択します。

::: moniker-end

2. **[アクティブ ユーザー]** ページで、どのユーザーの管理者ロールを変更するかを選択します。 ポップアップ ウィンドウの **[役割]** で、**[役割の管理]** を選択します。

3. ユーザーに割り当てる管理者の役割を選択します。 探しているロールが表示されない場合は、リストの下部にある **[すべて表示]** を選択します。

## <a name="assign-admin-roles-to-multiple-users"></a>複数のユーザーに管理者ロールを割り当てる

PowerShell がわかっている場合は、「 [PowerShell を使用してユーザー アカウントにロールを割り当てる](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md)」を参照してください。 これは多数のユーザーにロールを割り当てるための最適な方法です。
  
次の手順を使用して、多数のユーザーにロールを割り当てます。

## <a name="check-admin-roles-in-your-organization"></a>組織内の管理者ロールを確認する

管理者ロールを他のユーザーに割り当てる適切なアクセス許可がない可能性があります。 適切なアクセス許可があることを確認するか、別の管理者にロールを割り当ててもらうように依頼します。

管理者ロールのアクセス許可は、次の 2 つの方法で確認できます。

- ユーザーの詳細に移動し、[**アカウント**] ページの [**ロール]** で確認できます。
- または、[ **ロール]** に移動して管理者ロールを選択し、割り当てられている管理者を選択して、割り当てられているユーザーを確認することもできます。

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 管理者ロールについて](about-admin-roles.md) (記事)\
[Azure AD組み込みのロール](/azure/active-directory/roles/permissions-reference) (記事)\
[PowerShell を使用してユーザー アカウントにロールを割り当てる](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md) (記事)\
[パートナー関係を承認または削除する](../misc/add-partner.md) (記事)