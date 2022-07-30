---
title: Microsoft 365 グループのメンバーを追加または削除する
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
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
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
ms.assetid: e186d224-a324-4afa-8300-0e4fc0c3000a
description: グループにメンバーを追加し、グループからメンバーを削除し、Microsoft 365 管理センターでグループ所有者の状態を管理する方法について説明します。
ms.openlocfilehash: 81cf70aca87838bed7060dd75bb6e7cacee66bc1
ms.sourcegitcommit: 2f6a7410e9919f753a759c1ada441141e18f06fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2022
ms.locfileid: "67084369"
---
# <a name="add-or-remove-members-from-microsoft-365-groups-using-the-admin-center"></a>管理センターを使用して Microsoft 365 グループのメンバーを追加または削除する

Microsoft 365 では、通常、グループ メンバーは独自のグループを作成したり、参加するグループに追加したり、グループの所有者から招待されたりします。 グループの所有権が変更された場合、または管理者としてメンバーを追加または削除する必要があると判断した場合は、その変更を行うこともできます。 これらの変更を行うことができるのは、グローバル管理者、Exchange 管理者、グループ管理者、またはユーザー管理者のみです。 [Microsoft 365 グループとは](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

> [!TIP]
> 管理者でない場合は、 [Outlook を使用してメンバーを追加または削除](https://support.microsoft.com/office/3b650f4a-5c9b-4f94-a1bb-0cca4b1091de)できます。
  
## <a name="add-a-member-to-a-group-in-the-admin-center"></a>管理センターのグループにメンバーを追加する

1. 管理センターで、[ [**アクティブ なグループ**](https://admin.microsoft.com/Adminportal/Home?#/groups) ] ページに移動します。  

2. グループ名をクリックします。

3. 詳細ウィンドウの [ **メンバー** ] タブで、[ **すべてのメンバーの表示と管理**] を選択し、[ **メンバーの追加**] を選択します。

4. 追加するメンバーの名前を検索するか選択します。

5. **[保存]** を選択します。

## <a name="add-a-group-to-a-member-in-the-admin-center"></a>管理センターのメンバーにグループを追加する

1. 管理センターで、[ [**アクティブなユーザー**](https://admin.microsoft.com/Adminportal/Home?#/users) ] ページに移動します。  

2. ユーザーをクリックします。

3. 詳細ウィンドウの [ **アカウント** ] タブで、[グループの **管理**] を選択します。

4. 追加するグループの名前を検索または選択します。

5. **[保存]** を選択します。

## <a name="remove-a-member-from-a-group-in-the-admin-center"></a>管理センターのグループからメンバーを削除する

> [!NOTE]
> プライベート グループからメンバーを削除すると、そのユーザーがグループからブロックされるまでに 5 分かかります。

1. 管理センターで、[ [**アクティブ なグループ**](https://admin.microsoft.com/Adminportal/Home?#/groups) ] ページに移動します。  

2. グループ名をクリックします。

3. 詳細ウィンドウの [ **メンバー** ] タブで、[ **すべての表示とメンバーの管理**] を選択します。

4. 削除するメンバーの横にある X を選択します。

5. **[保存] を** 選択してメンバーを削除します。

## <a name="manage-group-owner-status"></a>グループ所有者の状態を管理する

既定では、グループを作成したユーザーが、グループの所有者になります。多くの場合、グループには、バックアップ サポートやその他の理由のために複数の所有者がいます。メンバーを所有者ステータスに昇格させたり、所有者をメンバー ステータスに降格させたりすることができます。
  
### <a name="promote-a-member-to-owner-status-in-the-admin-center"></a>管理センターでメンバーを所有者の状態に昇格させる

1. 管理センターで、[ [**アクティブ なグループ**](https://admin.microsoft.com/Adminportal/Home?#/groups) ] ページに移動します。  

2. グループ名をクリックします。

3. 詳細ウィンドウの [ **メンバー** ] タブで、[ **すべて表示して所有者を管理]** を選択します。

4. [ **所有者の追加]** を選択します。

5. 追加するメンバーの名前の横にあるチェック ボックスをオンにします。

6. **[保存]**、[**閉じる**] の順に選択します。

### <a name="remove-owner-status-in-the-admin-center"></a>管理センターで所有者の状態を削除する

1. 管理センターで、[ [**アクティブ なグループ**](https://admin.microsoft.com/Adminportal/Home?#/groups) ] ページに移動します。  

2. グループ名をクリックします。

3. 詳細ウィンドウの [ **メンバー** ] タブで、[ **すべて表示して所有者を管理]** を選択します。

4. 所有者の名前の横にある X を選択します。

5. **[保存]** を選択します。

## <a name="next-steps"></a>次の手順

- [Azure Active Directory におけるグループの管理](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal): 「グループのメンバーシップを動的に管理する方法」セクションを参照してください。

- グループに数百または数千のユーザーを追加するには、 [Add-UnifiedGroupLinks](/powershell/module/exchange/add-unifiedgrouplinks) を使用します。

- [孤立グループに新しい所有者を割り当てる](https://support.microsoft.com/office/86bb3db6-8857-45d1-95c8-f6d540e45732)

## <a name="related-content"></a>関連コンテンツ

[Outlook で配布リストを Microsoft 365 グループにアップグレードする](../manage/upgrade-distribution-lists.md) (記事)\
[配布リストを Outlook のグループにアップグレードする理由](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188) (記事)\
[Microsoft 365 グループのゲスト アクセスを管理](manage-guest-access-in-groups.md) する (記事)\
[PowerShell を使用して Microsoft 365 グループを管理](../../enterprise/manage-microsoft-365-groups-with-powershell.md)する: この記事では、主要なコマンドレットについて説明し、例 (記事)\ を提供します。
[Microsoft 365 グループの名前付けポリシー](../../solutions/groups-naming-policy.md) (記事)