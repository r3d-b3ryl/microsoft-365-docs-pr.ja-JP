---
title: 管理者ロールに管理者ロールを割り当Microsoft 365 管理センター
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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: eac4d046-1afd-4f1a-85fc-8219c79e1504
description: 管理センターで特定のタスクを実行できるよう、管理者の役割をビジネス内のユーザーまたは複数のユーザーに割り当てる方法について説明します。
ms.openlocfilehash: 0b959dd9349a032d6825d010d103bfd74d080a595b072be950a61e98f3765dbb
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53815865"
---
# <a name="assign-admin-roles"></a>管理者ロールを割り当てる

Microsoft Business サブスクリプションを購入したユーザーは、グローバル管理者です。つまり、サブスクリプション内の製品を無制限に制御し、ほとんどのデータにアクセスできます。

詳細については、「[管理者の役割について](about-admin-roles.md)」を参照してください。

新しいユーザーを追加する場合、管理者ロールを割り当てない場合は、ユーザーロールに含め、Microsoft 管理センターに管理者特権はありません。 ただし、ヘルプが必要な場合は、管理者の役割をユーザーに割り当てできます。 たとえば、パスワードのリセットを支援する必要がある場合は、グローバル管理者の役割を割り当ててはいけない場合は、パスワード管理者の役割を割り当てる必要があります。 データやオンライン ビジネスに無制限にアクセスできるグローバル管理者が多すぎると、セキュリティ リスクが生じます。

## <a name="watch-add-an-adminbrbr"></a>ウォッチ: 管理者を追加する<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

このビデオが役に立った場合には、「[complete training series for small businesses and those new to Microsoft 365 (小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ)](../../business-video/index.yml)」をご覧ください。

## <a name="assign-admin-roles"></a>管理者ロールを割り当てる 

ユーザーを役割に割り当てるには、次の 2 つの方法があります。

- ユーザーの詳細と役割の管理に移動して **、ユーザー** に役割を割り当てることができます。
- または、[ロール] **に移動** して役割を選択し、そのロールに複数のユーザーを追加することもできます。

### <a name="assign-admin-roles-to-users-using-roles"></a>ロールを使用して管理者ロールをユーザーに割り当てる

1. 管理センターで、[ロール] に **移動します**。 組織で **使用できるAD** を表示するには、[Azure の管理者] タブまたは **[Intune]** タブを選択します。
2. ユーザーを割り当てる管理者の役割を選択します。
3. [割 **り当てられた管理者の追加]**  >  **を選択します**。
4. ユーザーの表示 **名またはユーザー** 名を **入力** し、候補の一覧からユーザーを選択します。
5. 完了するまで、複数のユーザーを追加します。
6. [ **保存]** を選択すると、割り当てられた管理者の一覧にユーザーが追加されます。

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a>アクティブ ユーザーから管理者の役割にユーザーを割り当てる

::: moniker range="o365-worldwide"

1. 管理センターで、[ユーザーのアクティブな **ユーザー]** > [ページに移動](https://go.microsoft.com/fwlink/p/?linkid=834822) します。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、[**ユーザー**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[**ユーザー**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。

::: moniker-end

2. [アクティブ **なユーザー] ページ** で、管理者ロールを変更するユーザーを選択します。 [フライアウト] ウィンドウの [役割] **で、[役割** の管理 **] を選択します**。

3. ユーザーに割り当てる管理者の役割を選択します。 探している役割が表示できない場合は、リストの下部にある [すべて表示] を選択します。

## <a name="assign-admin-roles-to-multiple-users"></a>複数のユーザーに管理者ロールを割り当てる

PowerShell を知っている場合は [、「PowerShell を使用して役割をユーザー アカウントに割り当てる」を参照してください](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md)。 これは多数のユーザーにロールを割り当てるための最適な方法です。
  
次の手順を使用して、多数のユーザーにロールを割り当てます。

## <a name="check-admin-roles-in-your-organization"></a>組織内の管理者の役割を確認する

管理者の役割を他のユーザーに割り当てる適切なアクセス許可が付与されていない可能性があります。 正しいアクセス許可を持っているか、別の管理者にロールを割り当てさせるか確認します。

管理者ロールのアクセス許可は、次の 2 つの方法で確認できます。

- ユーザーの詳細に移動し、[アカウント] ページの [ **役割** ] で **確認** できます。
- または、[役割] **に移動** して管理役割を選択し、割り当てられた管理者を選択して、割り当てられているユーザーを確認することもできます。

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 管理者ロールについて](about-admin-roles.md) (記事)\
[管理者ロールのアクセス許可](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)(Azure Active Directory)\
[PowerShell を使用してユーザー アカウントに役割を割り当てる](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md) (記事)\
[パートナー関係の承認または削除](../misc/add-partner.md) (記事)