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
ms.collection: M365-security-compliance
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: ユーザーは、Microsoft 365 セキュリティ & コンプライアンス センターでアクセス許可を割り当てる必要があります。その前に、セキュリティ機能またはコンプライアンス機能を管理する必要があります。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4e0ca3874f03d9f0c386a84c9e8b56ea58bbfe72
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2022
ms.locfileid: "66018010"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>ユーザーにセキュリティ/コンプライアンス センターへのアクセス権を付与する

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

ユーザーは、セキュリティまたはコンプライアンス機能を管理するには、セキュリティ & コンプライアンス センターでアクセス許可を割り当てる必要があります。 セキュリティ & コンプライアンス センターの OrganizationManagement ロール グループのグローバル管理者またはメンバーとして、これらのアクセス許可をユーザーに付与できます。 ユーザーが管理できるのは、アクセス権が付与されたセキュリティまたはコンプライアンスの機能のみです。

セキュリティ & コンプライアンス センターのユーザーに付与できるさまざまなアクセス許可の詳細については、セキュリティ [& コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)に関するページを参照してください。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- この記事の手順を完了するには、グローバル管理者、またはセキュリティ & コンプライアンス センターの OrganizationManagement ロール グループのメンバーである必要があります。

- セキュリティ & コンプライアンス センターの役割グループの名前は、Exchange Onlineの役割グループと似ていますが、同じではありません。

- 役割グループのメンバーシップは、Exchange Onlineとセキュリティ & コンプライアンス センターの間では共有されません。

- 代理アクセス許可 (DAP) の代理管理 (AOBO) アクセス許可を持つパートナーは、セキュリティ & コンプライアンス センターにアクセスできません。

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a>セキュリティ & コンプライアンス センターを使用して、別のユーザーにセキュリティ & コンプライアンス センターへのアクセス権を付与する

1. セキュリティ & コンプライアンス センターを <https://protection.office.com> 開き、 **アクセス許可** に移動します。 **[アクセス許可]** タブに直接移動するには、を開きます<https://protection.office.com/permissions>。

2. 役割グループの一覧から役割グループを選択し、[ **編集]** ![アイコンをクリックします](../../media/O365-MDM-CreatePolicy-EditIcon.gif)。

3. [ **メンバー**] の [役割グループのプロパティ] ページで、[ **追加**![アイコン] をクリックします。](../../media/ITPro-EAC-AddIcon.gif) をクリックし、追加するユーザー (またはユーザー) の名前を選択します。

4. 役割グループに追加するすべてのユーザーを選択したら、[ **追加\>** ] をクリックし、[ **OK] をクリックします**。

5. 完了したら、**[保存]** をクリックします。

## <a name="use-security--compliance-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>セキュリティ & コンプライアンス PowerShell を使用して、別のユーザーにセキュリティ & コンプライアンス センターへのアクセス権を付与する

1. [セキュリティ & コンプライアンス PowerShell にConnect](/powershell/exchange/connect-to-scc-powershell)します。

2. 次の構文を使用してください。

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

構文とパラメーターの問題の詳細については、「[Add-RoleGroupMember](/powershell/module/exchange/add-rolegroupmember)」を参照してください。

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

セキュリティ & コンプライアンス センターへのアクセス権が正常に付与されたことを確認するには、次のいずれかの手順を実行します。

- セキュリティ & コンプライアンス センターで、[ **アクセス許可]** に移動し、役割グループを選択します。 開いた詳細ポップアップで、役割グループのメンバーを確認します。

- セキュリティ & コンプライアンス PowerShell で、役割グループの名前に置き換えて \<RoleGroupName\> 、次のコマンドを実行します。

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  構文とパラメーターの詳細については、「 [Get-RoleGroupMember」を](/powershell/module/exchange/Get-RoleGroupMember)参照してください。
