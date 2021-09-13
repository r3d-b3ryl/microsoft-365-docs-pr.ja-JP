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
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: セキュリティ機能またはコンプライアンス機能を管理するには、Microsoft 365 セキュリティ & コンプライアンス センターでアクセス許可を割り当てる必要があります。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2123cad54bcb1a608447d53a08e61211052e3cca
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59214423"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>ユーザーにセキュリティ/コンプライアンス センターへのアクセス権を付与する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

セキュリティ機能またはコンプライアンス機能を管理するには、&コンプライアンス センターでアクセス許可を割り当てる必要があります。 セキュリティ & コンプライアンス センターの OrganizationManagement 役割グループのグローバル管理者またはメンバーとして、これらのアクセス許可をユーザーに付与できます。 ユーザーが管理できるのは、アクセス権が付与されたセキュリティまたはコンプライアンスの機能のみです。

セキュリティ & コンプライアンス センターでユーザーに付与できるさまざまなアクセス許可の詳細については、「セキュリティ & コンプライアンス センター」 [を参照してください](permissions-in-the-security-and-compliance-center.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- この記事の手順を完了するには、グローバル管理者またはセキュリティ & コンプライアンス センターの OrganizationManagement 役割グループのメンバーである必要があります。

- セキュリティ & コンプライアンス センターの役割グループは、Exchange Online の役割グループと似ていますが、同じではありません。

- 役割グループのメンバーシップは、コンプライアンス センター Exchange Onlineセキュリティ グループ&共有されない。

- 代理アクセス許可 (DAP) パートナーが [代理で管理] (AOBO) アクセス許可を持つ場合、セキュリティ &アクセスできません。

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a>セキュリティ コンプライアンス センター&使用して、別のユーザーにセキュリティ コンプライアンス センター&アクセス権を与える

1. [セキュリティ] コンプライアンス &を開き、[ <https://protection.office.com> アクセス許可] **に移動します**。 [アクセス許可] タブに直接 **移動** するには、 を開きます <https://protection.office.com/permissions> 。

2. 役割グループの一覧から役割グループを選択し、[編集] アイコン **を** ![ クリックします ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) 。

3. [メンバー] の [役割グループのプロパティ] ページ **で**、[アイコンの追加 **] を** ![ クリックします。](../../media/ITPro-EAC-AddIcon.gif) をクリックし、追加するユーザー (またはユーザー) の名前を選択します。

4. 役割グループに追加するすべての **\>** ユーザーを選択したら、[追加] をクリックし **、[OK] をクリックします**。

5. 完了したら、**[保存]** をクリックします。

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>セキュリティ & コンプライアンス センター PowerShell を使用して、別のユーザーにコンプライアンス センターのセキュリティ &アクセス権を与える

1. [セキュリティ/コンプライアンス センター PowerShell に接続します](/powershell/exchange/connect-to-scc-powershell)。

2. 次の構文を使用してください。

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

構文とパラメーターの詳細については [、「Add-RoleGroupMember」を参照してください。](/powershell/module/exchange/add-rolegroupmember)

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

セキュリティ コンプライアンス センターへのアクセスが正常に許可されたことを確認&、次のいずれかの手順を実行します。

- セキュリティ コンプライアンス センターで&アクセス許可に移動 **し** 、役割グループを選択します。 開く詳細フライアウトで、役割グループのメンバーを確認します。

- [セキュリティ & コンプライアンス センター PowerShell] で、役割グループの名前に置き換え、 \<RoleGroupName\> 次のコマンドを実行します。

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  構文とパラメーターの詳細については [、「Get-RoleGroupMember」を参照してください](/powershell/module/exchange/Get-RoleGroupMember)。