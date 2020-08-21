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
description: ユーザーが Microsoft 365 セキュリティ/コンプライアンス センターでのアクセス許可を割り &当てないと、そのセキュリティまたはコンプライアンス機能を管理できません。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d21fef9458c02bd09d6d5ce2129b95571e0f8371
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826603"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>ユーザーにセキュリティ/コンプライアンス センターへのアクセス権を付与する

ユーザーは、自分のいずれかのセキュリティまたはコンプライアンス機能を管理&、セキュリティ コンプライアンス センターでアクセス許可を割り当てる必要があります。 グローバル管理者またはセキュリティ コンプライアンス センターの [組織の管理] 役割グループ &のメンバーは、ユーザーにこれらの許可を付与できます。 ユーザーが管理できるのは、アクセス権が付与されたセキュリティまたはコンプライアンスの機能のみです。

ユーザーに付与できるさまざまなアクセス許可の詳細については、セキュリティ/コンプライアンス センター& [&確認してください](permissions-in-the-security-and-compliance-center.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- この記事の手順を実行するには、グローバル管理者か、セキュリティ & コンプライアンス センターの組織の管理役割グループのメンバーである必要があります。

- セキュリティ コンプライアンス センターの役割グループ&、Exchange Online の役割グループと名前が似ていますが、同じです。

- 役割グループのメンバーシップは、Exchange Online とセキュリティ コンプライアンス センターの間&されません。

- 委任アクセス許可 (AOBO) アクセス許可を持つ委任アクセス許可 (DAP) パートナーは、コンプライアンス センターのセキュリティ &にアクセスできません。

## <a name="use-the-admin-center-to-give-another-user-access-to-the-security--compliance-center"></a>管理センターを使用して、セキュリティ センターとコンプライアンス センターへのアクセス&許可する

1. [サインインして管理センターに移動します](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)。

2. Microsoft 365 管理センターで、[管理センター **] を開き、[** セキュリティ]、[ **コンプライアンス&します**。

3. セキュリティ/コンプライアンス センター&アクセス許可に移動 **します**。

4. 一覧から、ユーザーを追加する役割グループを選択し、[編集] アイコン **を** ![ クリックします ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) 。

5. [**メンバー**の追加] の役割グループのプロパティ ページで、[**追加** ![ ] アイコン ](../../media/ITPro-EAC-AddIcon.gif) をクリックし、追加するユーザーの名前を 1 つまたは複数選択します。

6. 役割グループに追加するユーザーをすべて選択したら、[追加] をクリックしてから **[OK] \> **を**クリックします**。

7. **[保存]** をクリックして、役割グループに加えた変更を保存します。

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

1. セキュリティ/コンプライアンス センター&アクセス許可に移動 **します**。

2. 一覧から、メンバーを表示する役割グループを選択します。

3. 右側の役割グループの詳細に、役割グループのメンバーを表示することができます。

## <a name="use-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>PowerShell を使用して、セキュリティ/コンプライアンス センターへのアクセス権を別&付与する

1. [セキュリティ/コンプライアンス センター PowerShell に接続します](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。

2. 次の例で示すように、**Add-RoleGroupMember** コマンドを使用して、ユーザーを Organization Management の役割に追加できます。

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

   **パラメーター**:

   - _Identity_ は、メンバーを追加する役割グループです。

   - _メンバー_ は、役割グループに追加するメールボックス、ユニバーサル セキュリティ グループ (USG)、またはコンピューターです。 一度に 1 メンバーしか指定できません。

構文およびパラメーターの詳細については [、「Add-RoleGroupMember」を参照してください](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember)。

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

ユーザーにセキュリティ & コンプライアンス センターへのアクセス権を付与したことを確認するには、 **次の例のように、Get-RoleGroupMember** コマンドレットを使用して組織管理役割グループのメンバーを表示します。

```PowerShell
Get-RoleGroupMember -Identity "Organization Management"
```

構文およびパラメーターの詳細については [、「Get-RoleGroupMember」を参照してください](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember)。
