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
description: ユーザーは、Microsoft 365 セキュリティ/コンプライアンス センターでアクセス許可を割り当て&、セキュリティまたはコンプライアンス機能を管理する必要があります。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e1a619b184c575e3750b2499adc661627b4d27d6
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289879"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>ユーザーにセキュリティ/コンプライアンス センターへのアクセス権を付与する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

ユーザーは、セキュリティまたはコンプライアンス機能を管理する前&セキュリティ/コンプライアンス センターでアクセス許可を割り当てる必要があります。 セキュリティ & コンプライアンス センターのグローバル管理者または OrganizationManagement 役割グループのメンバーは、これらのアクセス許可をユーザーに付与できます。 ユーザーが管理できるのは、アクセス権が付与されたセキュリティまたはコンプライアンスの機能のみです。

セキュリティ & コンプライアンス センターでユーザーに付与できるさまざまなアクセス許可の詳細については、セキュリティ/コンプライアンス センターでアクセス許可 [&確認してください](permissions-in-the-security-and-compliance-center.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- この記事の手順を完了するには、グローバル管理者、またはセキュリティ & コンプライアンス センターの OrganizationManagement 役割グループのメンバーである必要があります。

- セキュリティ/コンプライアンス センター&グループの名前は Exchange Online の役割グループと似ていますが、同じではありません。

- 役割グループのメンバーシップは、Exchange Online とセキュリティ/コンプライアンス センター&共有されます。

- 代理アクセス許可 (DAP) パートナーが代理管理 (AOBO) アクセス許可を持つ場合、セキュリティ/コンプライアンス センター&できません。

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a>セキュリティ/コンプライアンス センター&使用して、別のユーザーにセキュリティ/コンプライアンス センターへのアクセス&与える

1. セキュリティ/コンプライアンス センター&開き、[ <https://protection.office.com> アクセス許可] に **移動します**。 [アクセス許可] タブに **直接移動するには** 、開きます <https://protection.office.com/permissions> 。

2. 役割グループの一覧から役割グループを選択し、[編集] アイコン **を** ![ クリックします ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) 。

3. 役割グループのプロパティ ページの **[メンバー**]で、[追加] アイコンをクリックし、追加するユーザー ![ の名前 ](../../media/ITPro-EAC-AddIcon.gif) を選択します。

4. 役割グループに追加するユーザー **\>** を選択したら、[追加] をクリックし **、[OK]** をクリックします。

5. 完了したら、**[保存]** をクリックします。

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>セキュリティ/コンプライアンス & PowerShell を使用して、別のユーザーにセキュリティ/コンプライアンス センターへのアクセス&与える

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

構文およびパラメーターの詳細については[、「Add-RoleGroupMember」を参照してください](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)。

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

セキュリティ センター コンプライアンス センターへのアクセスが正常に許可されたことを確認&、次のいずれかの手順を実行します。

- セキュリティ/コンプライアンス センター&アクセス **許可に移動** し、役割グループを選択します。 開く詳細フライアウトで、役割グループのメンバーを確認します。

- Security & Compliance Center PowerShell で、役割グループの名前に置き換え、次 \<RoleGroupName\> のコマンドを実行します。

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  構文およびパラメーターの詳細については [、「Get-RoleGroupMember」を参照してください](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember)。
