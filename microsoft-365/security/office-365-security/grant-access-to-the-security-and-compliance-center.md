---
title: ユーザーにセキュリティ/コンプライアンス センターへのアクセス権を付与する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: ユーザーがセキュリティまたはコンプライアンス機能を管理する前に、Microsoft 365 セキュリティ & コンプライアンスセンターでアクセス許可を割り当てる必要があります。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b51007221257b9adac46c31295e13b20b12342ab
ms.sourcegitcommit: 22dab0f7604cc057a062698005ff901d40771692
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868923"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>ユーザーにセキュリティ/コンプライアンス センターへのアクセス権を付与する

ユーザーがセキュリティまたはコンプライアンス機能を管理する前に、セキュリティ & コンプライアンスセンターでアクセス許可を割り当てる必要があります。 セキュリティ & コンプライアンスセンターでは、組織の全体管理者または組織のメンバーとして、これらのアクセス許可をユーザーに与えることができます。 ユーザーが管理できるのは、アクセス権が付与されたセキュリティまたはコンプライアンスの機能のみです。

セキュリティ & コンプライアンスセンターでユーザーに付与できるさまざまなアクセス許可の詳細については、「 [セキュリティ & コンプライアンスセンターでアクセス許可](permissions-in-the-security-and-compliance-center.md)を確認する」を参照してください。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- この記事に記載されている手順を完了するには、グローバル管理者であるか、またはセキュリティ & コンプライアンスセンターの組織の組織の管理役割グループのメンバーである必要があります。

- セキュリティ & コンプライアンスセンターの役割グループには、Exchange Online の役割グループと同じような名前が付いている場合がありますが、これらは同じではありません。

- 役割グループのメンバーシップは、Exchange Online とセキュリティ & コンプライアンスセンターとの間で共有されません。

- (AOBO) 権限を持つ代理アクセス許可 (DAP) パートナーは、セキュリティ & コンプライアンスセンターにアクセスできません。

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a>セキュリティ & コンプライアンスセンターを使用して、別のユーザーにセキュリティ & コンプライアンスセンターへのアクセス権を付与する

1. [セキュリティ & コンプライアンスセンター] を開き、 <https://protection.office.com> [ **アクセス許可**] に移動します。 [ **アクセス許可** ] タブに直接移動するには、を開き <https://protection.office.com/permissions> ます。

2. 役割グループの一覧から役割グループを選択し、[編集] 編集アイコン **をクリックし** ![ ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) ます。

3. 役割グループのプロパティページの [**メンバー**] で、 **[追加** ![ ] アイコンをクリックし、 ](../../media/ITPro-EAC-AddIcon.gif) 追加するユーザーの名前を選択します。

4. 役割グループに追加するすべてのユーザーを選択したら、[ ** \> 追加**] をクリックし、[ **OK]** をクリックします。

5. 完了したら、**[保存]** をクリックします。

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>セキュリティ & コンプライアンスセンターの PowerShell を使用して、別のユーザーがセキュリティ & コンプライアンスセンターにアクセスできるようにする

1. [セキュリティ/コンプライアンス センター PowerShell に接続します](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。

2. 次の構文を使用してください。

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

構文およびパラメーターの詳細については、「 [add-rolegroupmember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember) 」を参照してください。

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

セキュリティ & コンプライアンスセンターへのアクセスが正常に付与されたことを確認するには、次のいずれかの手順を実行します。

- [セキュリティ & コンプライアンスセンター] で、[ **アクセス許可** ] に移動して役割グループを選択します。 表示される詳細ポップアップで、役割グループのメンバーを確認します。 

- セキュリティ & コンプライアンスセンターの PowerShell で、を \<RoleGroupName\> 役割グループの名前に置き換えて、次のコマンドを実行します。

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  構文およびパラメーターの詳細については、「 [add-rolegroupmember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember)」を参照してください。
