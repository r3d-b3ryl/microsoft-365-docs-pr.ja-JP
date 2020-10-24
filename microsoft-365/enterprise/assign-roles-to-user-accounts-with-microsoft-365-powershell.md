---
title: PowerShell を使用して Microsoft 365 ユーザーアカウントに役割を割り当てる
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- O365ITProTrain
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: ede7598c-b5d5-4e3e-a488-195f02f26d93
description: この記事では、Microsoft 365 の PowerShell を使用して、ユーザーアカウントに管理者の役割を割り当てる方法について説明します。
ms.openlocfilehash: 7e3292ab26924384beb8d0c7450b7665dccd48fa
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754200"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a>PowerShell を使用して Microsoft 365 ユーザーアカウントに管理者ロールを割り当てる

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365 の PowerShell を使用して、ユーザーアカウントに役割を簡単に割り当てることができます。

>[!Note]
>Microsoft 365 管理センターで  [管理者の役割](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) をユーザーアカウントに割り当てる方法について説明します。
>
>その他のリソースの一覧については、「 [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/)」を参照してください。
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する

最初に、全体管理者アカウントを使用し [て、Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)します。
  
次に、役割に追加するユーザーアカウントのサインイン名を指定します (例: fredsm \@ contoso.com)。 これは、ユーザープリンシパル名 (UPN) とも呼ばれます。

次に、ロールの名前を決めます。 「 [Azure Active Directory の管理者役割のアクセス許可」を](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)参照してください。

>[!Note]
>この記事のメモに注意してください。 Azure Active Directory (Azure AD) PowerShell では、一部の役割名が異なる場合があります。 たとえば、Microsoft 365 管理センターの *Sharepoint 管理者* の役割は、Azure AD PowerShell の *Sharepoint サービス管理者* です。
>

次に、サインイン名とロール名を入力して、次のコマンドを実行します。
  
```powershell
$userName="<sign-in name of the account>"
$roleName="<admin role name>"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

次に、SharePoint サービス管理者の役割を *ベルギーの \@ contoso.com* アカウントに割り当てる、完成したコマンドセットの例を示します。
  
```powershell
$userName="belindan@contoso.com"
$roleName="SharePoint Service Administrator"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

特定の管理者の役割についてユーザー名の一覧を表示するには、次のコマンドを使用します。

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する

最初に、全体管理者アカウントを使用し [て、Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)します。
  
### <a name="for-a-single-role-change"></a>単一ロールの変更の場合

ユーザーアカウントを指定する最も一般的な方法は、表示名または電子メール名 (サインイン名またはユーザープリンシパル名 (UPN) とも呼ばれる) を使用することです。

#### <a name="display-names-of-user-accounts"></a>ユーザーアカウントの表示名

ユーザーアカウントの表示名を使用して作業している場合は、次の情報を確認してください。
  
- 構成するユーザーアカウント
    
    ユーザー アカウントを指定するには、その表示名を判別する必要があります。 アカウントの完全な一覧を取得するには、次のコマンドを使用します。
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    このコマンドにより、ユーザー アカウントの表示名の一覧が、表示名順に並び替えられて、一度に 1 画面ずつ示されます。 **Where** コマンドレットを使用すると、一覧をフィルター処理して、出力するセットを小さくできます。 次の例をご覧ください。

   >[!Note]
   >PowerShell Core は、Windows PowerShell モジュール用 Microsoft Azure Active Directory モジュールと、名前に *Msol* を指定したコマンドレットをサポートしていません。 これらのコマンドレットを Windows PowerShell から実行します。
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    このコマンドは、表示名が「John」で始まるユーザー アカウントのみを一覧表示します。
    
- 割り当てる役割
    
    ユーザーアカウントに割り当てることができる利用可能な管理者の役割の一覧を表示するには、次のコマンドを使用します。
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

アカウントの表示名と役割の名前を特定したら、次のコマンドを使用してアカウントに役割を割り当てます。
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

コマンドをメモ帳に貼り付けます。 *$DispName*変数と *$roleName*変数については、説明テキストをその値に置き換えます。 文字を削除 \< and > しますが、引用符はそのままにします。 変更した行を Windows PowerShell 用 Microsoft Azure Active Directory モジュールウィンドウに貼り付けて、それらを実行します。 または、Windows PowerShell 統合スクリプト環境 (ISE) を使用することもできます。
  
次に、完了したコマンドセットの例を示します。
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a>ユーザーアカウントのサインイン名

ユーザーアカウントのサインイン名または Upn を使用して作業している場合は、次の情報を確認してください。
  
- ユーザーアカウントの UPN
    
    UPN がわからない場合は、次のコマンドを使用します。
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    このコマンドは、UPN で並べ替えて、一度に1画面ずつ、ユーザーアカウントの UPN を一覧表示します。 **Where**コマンドレットを使用して、リストにフィルターを適用できます。 次に例を示します:
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    このコマンドは、表示名が「John」で始まるユーザー アカウントのみを一覧表示します。
    
- 割り当てる役割
    
    ユーザー アカウントに割り当てることができるロールの一覧を表示するには、次のコマンドを使用します。
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

アカウントの UPN と役割の名前を取得したら、次のコマンドを使用してアカウントに役割を割り当てます。
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

コマンドをコピーしてメモ帳に貼り付けます。 **$UpnName**と **$roleName**変数の場合。 説明テキストをその値に置き換えます。 文字を削除 \< and > しますが、引用符はそのままにします。 変更した行を Windows PowerShell 用 Microsoft Azure Active Directory モジュールウィンドウに貼り付けて、それらを実行します。 または、Windows PowerShell ISE を使用することもできます。
  
次に、完了したコマンドセットの例を示します。
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a>複数の役割の変更

複数の役割の変更については、次の情報を確認してください。
  
- 構成するユーザーアカウント。 前のセクションの方法を使用して、表示名または Upn のセットを収集できます。
    
- 各ユーザー アカウントに割り当てるロール。 ユーザー アカウントに割り当てることができるロールの一覧を表示するには、次のコマンドを使用します。
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

次に、[表示名] または [UPN] および [役割名] フィールドを含むコンマ区切り値 (CSV) テキストファイルを作成します。 この操作は、Microsoft Excel で簡単に実行できます。

表示名の例を次に示します。
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

その後、PowerShell コマンド プロンプトで CSV ファイルの場所を入力し、完成したコマンドを実行します。
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

次に、Upn の例を示します。
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

その後、PowerShell コマンド プロンプトで CSV ファイルの場所を入力し、完成したコマンドを実行します。
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a>関連項目

- [Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)
- [Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)
