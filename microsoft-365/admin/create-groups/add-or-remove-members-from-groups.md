---
title: グループにメンバーを追加またはMicrosoft 365する
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
ms.assetid: e186d224-a324-4afa-8300-0e4fc0c3000a
description: グループにメンバーを追加し、グループからメンバーを削除し、グループ所有者の状態を管理する方法については、Microsoft 365 管理センター。
ms.openlocfilehash: 610da28d6282cb45cb43e086fb3f80acaf18bb05
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60165822"
---
# <a name="add-or-remove-members-from-microsoft-365-groups-using-the-admin-center"></a>管理センターを使用して、Microsoft 365グループのメンバーを追加または削除する

このMicrosoft 365、グループ メンバーは通常、独自のグループを作成したり、参加するグループに自分自身を追加したり、グループの所有者から招待されます。 グループの所有権が変更された場合、または管理者としてメンバーを追加または削除する必要がある場合は、その変更を行う必要があります。 これらの変更を行Exchangeできるのは、グローバル管理者、管理者、グループ管理者、またはユーザー管理者のみです。 [グループとはMicrosoft 365ですか?](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

> [!TIP]
> 管理者ではない場合は、管理者を使用してメンバーを追加[または削除Outlook。](https://support.microsoft.com/office/3b650f4a-5c9b-4f94-a1bb-0cca4b1091de)
  
## <a name="add-a-member-to-a-group-in-the-admin-center"></a>管理センターのグループにメンバーを追加する

1. 管理センターで、[アクティブ なグループ] [**ページに移動**](https://admin.microsoft.com/Adminportal/Home?#/groups) します。  

2. グループ名をクリックします。

3. 詳細ウィンドウの [メンバー] タブ **で**、[すべて表示してメンバーを管理する] を選択し、[メンバーの追加]**を選択します**。

4. 追加するメンバーの名前を検索するか選択します。

5. **[保存]** を選択します。

## <a name="add-a-group-to-a-member-in-the-admin-center"></a>管理センターのメンバーにグループを追加する

1. 管理センターで、[アクティブなユーザー] [**ページに移動**](https://admin.microsoft.com/Adminportal/Home?#/users) します。  

2. ユーザーをクリックします。

3. 詳細ウィンドウの [アカウント] **タブで、[** グループの管理] **を選択します**。

4. 追加するグループの名前を検索または選択します。

5. **[保存]** を選択します。

## <a name="remove-a-member-from-a-group-in-the-admin-center"></a>管理センターのグループからメンバーを削除する

> [!NOTE]
> プライベート グループからメンバーを削除すると、そのユーザーがグループからブロックされるのに 5 分かかります。

1. 管理センターで、[アクティブ なグループ] [**ページに移動**](https://admin.microsoft.com/Adminportal/Home?#/groups) します。  

2. グループ名をクリックします。

3. 詳細ウィンドウの [メンバー] タブ **で、[すべて** 表示] を選択し、 **メンバーを管理します**。

4. 削除するメンバーの横にある [X] を選択します。

5. [保存 **] を** 選択してメンバーを削除します。

## <a name="manage-group-owner-status"></a>グループ所有者の状態を管理する

既定では、グループを作成したユーザーが、グループの所有者になります。多くの場合、グループには、バックアップ サポートやその他の理由のために複数の所有者がいます。メンバーを所有者ステータスに昇格させたり、所有者をメンバー ステータスに降格させたりすることができます。
  
### <a name="promote-a-member-to-owner-status-in-the-admin-center"></a>管理センターでメンバーを所有者の状態に昇格する

1. 管理センターで、[アクティブ なグループ] [**ページに移動**](https://admin.microsoft.com/Adminportal/Home?#/groups) します。  

2. グループ名をクリックします。

3. 詳細ウィンドウの [メンバー] タブ **で** 、[すべて表示して所有者を管理 **する] を選択します**。

4. [所有者 **の追加] を選択します**。

5. 追加するメンバーの名前の横にあるチェック ボックスをオンにします。

6. [保存 **] を** 選択し、[閉じる] **を選択します**。

### <a name="remove-owner-status-in-the-admin-center"></a>管理センターで所有者の状態を削除する

1. 管理センターで、[アクティブ なグループ] [**ページに移動**](https://admin.microsoft.com/Adminportal/Home?#/groups) します。  

2. グループ名をクリックします。

3. 詳細ウィンドウの [メンバー] タブ **で** 、[すべて表示して所有者を管理 **する] を選択します**。

4. 所有者の名前の横にある [X] を選択します。

5. **[保存]** を選択します。

## <a name="next-steps"></a>次の手順

- [Azure Active Directory におけるグループの管理](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal): 「グループのメンバーシップを動的に管理する方法」セクションを参照してください。

- グループに数百人または数千人のユーザーを追加するには [、Add-UnifiedGroupLinks を使用します](/powershell/module/exchange/add-unifiedgrouplinks)。

- [孤立グループに新しい所有者を割り当てる](https://support.microsoft.com/office/86bb3db6-8857-45d1-95c8-f6d540e45732)

## <a name="related-content"></a>関連コンテンツ

[配布リストを Microsoft 365グループにOutlook](../manage/upgrade-distribution-lists.md)する (記事)\
[配布リストをサイト内](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)のグループにアップグレードするOutlook (記事)\
[グループ内のゲスト アクセスMicrosoft 365管理](manage-guest-access-in-groups.md)する (記事)\
[PowerShell Microsoft 365グループを](../../enterprise/manage-microsoft-365-groups-with-powershell.md)管理する : この記事では、主要なコマンドレットについて説明し、例 (記事)\ を提供します。
[Microsoft 365グループの名前付けポリシー](../../solutions/groups-naming-policy.md) (記事)