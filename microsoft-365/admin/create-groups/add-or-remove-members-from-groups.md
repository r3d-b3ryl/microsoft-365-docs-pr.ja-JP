---
title: Microsoft 365 グループのメンバーを追加または削除する
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
ms.assetid: e186d224-a324-4afa-8300-0e4fc0c3000a
description: Microsoft 365 管理センターで、グループにメンバーを追加する方法、グループからメンバーを削除する方法、およびグループ所有者の状態を管理する方法について説明します。
ms.openlocfilehash: 34c026bced5563e07a1ae0d13f4c691cfaf3f624
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663245"
---
# <a name="add-or-remove-members-from-microsoft-365-groups-using-the-admin-center"></a>管理センターを使用して Microsoft 365 グループのメンバーを追加または削除する

Microsoft 365 では、グループ メンバーは通常、独自のグループを作成したり、参加するグループに自分自身を追加したり、グループの所有者によって招待されます。 グループの所有権が変更された場合、または管理者としてメンバーを追加または削除する必要がある場合は、その変更を行う必要があります。 これらの変更を行えるのは、グローバル管理者、Exchange 管理者、グループ管理者、またはユーザー管理者のみです。 [Microsoft 365 グループとは](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

> [!TIP]
> 管理者ではない場合は、Outlook を使用してメンバーを追加 [または削除できます](https://support.microsoft.com/office/3b650f4a-5c9b-4f94-a1bb-0cca4b1091de)。
  
## <a name="add-a-member-to-a-group-in-the-admin-center"></a>管理センターでグループにメンバーを追加する

1. 管理センターで、[アクティブなグループ] [**ページに移動**](https://admin.microsoft.com/Adminportal/Home?#/groups) します。  

2. グループ名をクリックします。

3. 詳細ウィンドウの [メンバー]タブで、[すべてのメンバーの表示と管理] を選択し、[メンバーの追加]**を選択します**。

4. 追加するメンバーの名前を検索するか選択します。

5. **[保存]** を選択します。

## <a name="add-a-group-to-a-member-in-the-admin-center"></a>管理センターでメンバーにグループを追加する

1. 管理センターで、[アクティブなユーザー] [**ページに移動**](https://admin.microsoft.com/Adminportal/Home?#/users) します。  

2. ユーザーをクリックします。

3. 詳細ウィンドウの [アカウント]タブで、[グループの管理]**を選択します**。

4. 追加するグループの名前を検索または選択します。

5. **[保存]** を選択します。

## <a name="remove-a-member-from-a-group-in-the-admin-center"></a>管理センターでグループからメンバーを削除する

> [!NOTE]
> プライベート グループからメンバーを削除すると、そのユーザーがグループからブロックされるのに 5 分かかります。

1. 管理センターで、[アクティブなグループ] [**ページに移動**](https://admin.microsoft.com/Adminportal/Home?#/groups) します。  

2. グループ名をクリックします。

3. 詳細ウィンドウの [メンバー]タブで、[すべてのメンバーの表示と管理 **] を選択します**。

4. 削除するメンバーの横にある [X] を選択します。

5. [保存 **] を** 選択してメンバーを削除します。

## <a name="manage-group-owner-status"></a>グループ所有者の状態を管理する

既定では、グループを作成したユーザーが、グループの所有者になります。多くの場合、グループには、バックアップ サポートやその他の理由のために複数の所有者がいます。メンバーを所有者ステータスに昇格させたり、所有者をメンバー ステータスに降格させたりすることができます。
  
### <a name="promote-a-member-to-owner-status-in-the-admin-center"></a>管理センターでメンバーを所有者の状態に昇格する

1. 管理センターで、[アクティブなグループ] [**ページに移動**](https://admin.microsoft.com/Adminportal/Home?#/groups) します。  

2. グループ名をクリックします。

3. 詳細ウィンドウの [メンバー]タブで、[すべて表示] を選択し、所有者 **を管理します**。

4. [所有者 **の追加] を選択します**。

5. 追加するメンバーの名前の横にあるチェック ボックスをオンにします。

6. [保存 **] を** 選択し、[閉じる] **を選択します**。

### <a name="remove-owner-status-in-the-admin-center"></a>管理センターで所有者の状態を削除する

1. 管理センターで、[アクティブなグループ] [**ページに移動**](https://admin.microsoft.com/Adminportal/Home?#/groups) します。  

2. グループ名をクリックします。

3. 詳細ウィンドウの [メンバー]タブで、[すべての表示と所有者の管理 **] を選択します**。

4. 所有者の名前の横にある [X] を選択します。

5. **[保存]** を選択します。

## <a name="more-on-managing-membership"></a>メンバーシップの管理に関する詳細

- [Azure Active Directory におけるグループの管理](https://go.microsoft.com/fwlink/?linkid=847632): 「グループのメンバーシップを動的に管理する方法」セクションを参照してください。

- グループに数百または数千のユーザーを追加するには [、Add-UnifiedGroupLinks を使用します](https://docs.microsoft.com/powershell/module/exchange/add-unifiedgrouplinks)。

- [孤立グループに新しい所有者を割り当てる](https://support.microsoft.com/office/86bb3db6-8857-45d1-95c8-f6d540e45732)

## <a name="articles-about-managing-groups"></a>グループの管理に関する記事

- [Outlook で配布リストを Microsoft 365 グループにアップグレードする](../manage/upgrade-distribution-lists.md)

- [Outlook で配布リストをグループにアップグレードする理由](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

- [Microsoft 365 グループのゲスト アクセスを管理する](manage-guest-access-in-groups.md)

- [PowerShell を使用して Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)グループを管理する : この記事では、主要なコマンドレットについて説明し、例を示します。

- [Microsoft 365 グループの名前付けポリシー](groups-naming-policy.md)
