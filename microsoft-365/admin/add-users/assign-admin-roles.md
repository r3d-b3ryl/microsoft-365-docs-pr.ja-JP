---
title: 管理管理センターに管理者ロールMicrosoft 365割り当てる
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
- Adm_TOC
ms.custom:
- MSStore_Link
- okr_smb
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: eac4d046-1afd-4f1a-85fc-8219c79e1504
description: 管理者ロールをビジネスのユーザーまたは複数のユーザーに割り当て、管理センターで特定のタスクを実行できるようにする方法について説明します。
ms.openlocfilehash: f23a30cfd1be53982572d745d476558c3be615e6
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571867"
---
# <a name="assign-admin-roles"></a>管理者ロールを割り当てる

Microsoft ビジネス サブスクリプションを購入したユーザーは、グローバル管理者です。つまり、サブスクリプション内の製品を無制限に制御でき、ほとんどのデータにアクセスできます。

詳細については、「[管理者の役割について](about-admin-roles.md)」を参照してください。

新しいユーザーを追加する場合、管理者ロールを割り当てなければ、その *ユーザーはユーザー ロール* に割り当てられており、Microsoft 管理センターに対する管理者特権がありません。 ただし、作業を完了するために支援が必要な場合は、ユーザーに管理者ロールを割り当てることができます。 たとえば、パスワードのリセットを支援する担当者が必要な場合は、グローバル管理者ロールを割り当てるべきではないので、パスワード管理者ロールを割り当てる必要があります。 データやオンライン ビジネスに無制限にアクセスできるグローバル管理者が多すぎると、セキュリティ リスクが生じます。

## <a name="watch-add-an-adminbrbr"></a>ウォッチ: 管理者を追加します。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

このビデオがお役に立った場合には、「[小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ](../../business-video/index.yml)」をご覧ください。

## <a name="assign-admin-roles"></a>管理者ロールを割り当てる 

::: moniker range="o365-worldwide"

ユーザーをロールに割り当てるには、次の 2 つの方法があります。

- ユーザーの詳細と **ロールの管理** に移動して、ロールをユーザーに割り当てることができます。
- または、[ **ロール]** に移動してロールを選択し、複数のユーザーをロールに追加することもできます。

### <a name="assign-admin-roles-to-users-using-roles"></a>ロールを使用してユーザーに管理者ロールを割り当てる

1. 管理センターで、[ **ロール**] に移動します。 Azure **AD** または **Intune** タブを選択して、組織で使用可能な管理者ロールを表示します。
2. ユーザーを割り当てる管理者ロールを選択します。
3. [ **割り当てられた管理者** > **追加]** を選択します。
4. ユーザーの **表示名** または **ユーザー名** を入力し、候補の一覧からユーザーを選択します。
5. 完了するまで複数のユーザーを追加します。
6. [ **保存 ]** を選択すると、割り当てられた管理者の一覧にユーザーが追加されます。

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a>アクティブ ユーザーから管理者の役割にユーザーを割り当てる

1. 管理センターで、[ **ユーザー** > [アクティブユーザー](https://go.microsoft.com/fwlink/p/?linkid=834822) ] ページに移動します。

2. [ **アクティブなユーザー** ] ページで、管理者ロールを変更するユーザーを選択します。 ポップアップ ウィンドウの [ **ロール]** で、[ **ロールの管理**] を選択します。

3. ユーザーに割り当てる管理者の役割を選択します。 目的のロールが表示されない場合は、一覧の下部にある **[すべて表示** ] を選択します。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、**[ユーザー]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> の順に選択します。

2. [ **アクティブなユーザー** ] ページで、管理者ロールを変更するユーザーを選択します。 フライアウト ペインで、[ **ロール**] の横にある [ **編集**] を選択します。 

    **[編集]** オプションが表示されない場合は、編集権限が与えなくて、他のユーザーに管理者ロールを割り当てることはできません。 担当の役割を割り当ててもらうには、ビジネスのグローバル管理者に依頼してください。 小規模ビジネスでは、ビジネスオーナー (サブスクリプションを購入したユーザー) がグローバル管理者です。大企業では、IT 部門の主要な担当者はグローバル管理者です。

3. **カスタマイズした** ロールの一覧を表示するには、[カスタマイズされた管理者] を選択します。 各ロールの説明については、「[管理者ロールについて](about-admin-roles.md)」を参照してください。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、**[ユーザー]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> の順に選択します。

2. [ **アクティブなユーザー** ] ページで、管理者ロールを変更するユーザーを選択します。 フライアウト ペインで、[ **ロール**] の横にある [ **編集**] を選択します。

    **[編集]** オプションが表示されない場合は、編集権限が与えなくて、他のユーザーに管理者ロールを割り当てることはできません。 担当の役割を割り当ててもらうには、ビジネスのグローバル管理者に依頼してください。 小規模ビジネスでは、ビジネスオーナー (サブスクリプションを購入したユーザー) がグローバル管理者です。大企業では、IT 部門の主要な担当者はグローバル管理者です。

3. **カスタマイズした** ロールの一覧を表示するには、[カスタマイズされた管理者] を選択します。 各ロールの説明については、「[管理者ロールについて](about-admin-roles.md)」を参照してください。

::: moniker-end

## <a name="assign-admin-roles-to-multiple-users"></a>複数のユーザーに管理者ロールを割り当てる

PowerShell がわかっている場合は [、「PowerShell を使用してユーザー アカウントにロールを割り当てる](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md)」を参照してください。 これは多数のユーザーにロールを割り当てるための最適な方法です。
  
次の手順を使用して、多数のユーザーにロールを割り当てます。

::: moniker range="o365-worldwide"

## <a name="check-admin-roles-in-your-organization"></a>組織の管理者の役割を確認する

管理者ロールを他のユーザーに割り当てる適切な権限がない可能性があります。 適切な権限があることを確認するか、別の管理者にロールの割り当てを依頼してください。

管理者の役割のアクセス許可は、次の 2 つの方法で確認できます。

- ユーザーの詳細に移動し、[**アカウント**] ページの **[ロール**] を確認できます。
- または、[ **ロール]** に移動して管理者ロールを選択し、割り当てられた管理者を選択して、割り当てられているユーザーを確認することもできます。

::: moniker-end

## <a name="related-content"></a>関連コンテンツ

[管理者ロールMicrosoft 365について](about-admin-roles.md)(記事)

[Azure Active Directoryの管理者ロールのアクセス許可](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)(記事)

[PowerShell を使用してユーザー アカウントにロールを割り当てる](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md) (記事)

[パートナー関係の承認または削除](../misc/add-partner.md) (記事)