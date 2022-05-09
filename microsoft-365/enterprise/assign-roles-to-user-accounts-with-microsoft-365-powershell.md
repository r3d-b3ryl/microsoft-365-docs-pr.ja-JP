---
title: PowerShell を使用して Microsoft 365 ユーザー アカウントに役割を割り当てます
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
description: この記事では、PowerShell を使用してユーザー アカウントに管理者ロールを割り当てるMicrosoft 365を迅速かつ簡単に行う方法について説明します。
ms.openlocfilehash: 8ac98920dd3d2d0487905b001434d73274463f9a
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65097450"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a>PowerShell を使用してMicrosoft 365ユーザー アカウントに管理者ロールを割り当てる

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365用 PowerShell を使用して、ユーザー アカウントにロールを簡単に割り当てることができます。

>[!Note]
>Microsoft 365 管理センターを使用して管理者ロールをユーザー アカウントに[割り当てる](../admin/add-users/assign-admin-roles.md)方法について説明します。
>
>その他のリソースの一覧については、「 [ユーザーとグループの管理](/admin)」を参照してください。
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する

まず、**Azure AD DC 管理者**、**クラウド アプリケーション管理者**、または **グローバル管理者** アカウントを使用して [、Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
 
詳細については、「[管理者の役割について](/microsoft-365/admin/add-users/about-admin-roles?)」を参照してください。

次に、ロールに追加するユーザー アカウントのサインイン名を特定します (例: fredsm\@ contoso.com)。 これは、ユーザー プリンシパル名 (UPN) とも呼ばれます。

次に、ロールの名前を決めます。 [組み込みロールAzure AD](/azure/active-directory/roles/permissions-reference)参照してください。

>[!Note]
>この記事のメモに注意してください。 一部のロール名は、Azure Active Directory (Azure AD) PowerShell では異なります。 たとえば、Microsoft 365 管理センターの *SharePoint管理者* ロールは *、powerShell のサービス管理者* SharePoint Azure AD。
>

次に、サインイン名とロール名を入力し、次のコマンドを実行します。
  
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

SharePointサービス管理者ロールを *belindan\@ contoso.com* アカウントに割り当てる完了したコマンド セットの例を次に示します。
  
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

特定の管理者ロールのユーザー名の一覧を表示するには、次のコマンドを使用します。

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する

まず、グローバル管理者アカウントを使用して[、Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。
  
### <a name="for-a-single-role-change"></a>単一ロールの変更の場合

ユーザー アカウントを指定する最も一般的な方法は、表示名またはその電子メール名 (サインイン名またはユーザー プリンシパル名 (UPN) とも呼ばれます) を使用することです。

#### <a name="display-names-of-user-accounts"></a>ユーザー アカウントの表示名

ユーザー アカウントの表示名の操作に慣れている場合は、次の情報を確認します。
  
- 構成するユーザー アカウント
    
    ユーザー アカウントを指定するには、その表示名を判別する必要があります。 アカウントの完全な一覧を取得するには、次のコマンドを使用します。
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    このコマンドにより、ユーザー アカウントの表示名の一覧が、表示名順に並び替えられて、一度に 1 画面ずつ示されます。 **Where** コマンドレットを使用すると、一覧をフィルター処理して、出力するセットを小さくできます。 次の例をご覧ください。

   >[!Note]
   >PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に *Msol* が含まれるコマンドレットをサポートしていません。
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    このコマンドは、表示名が「John」で始まるユーザー アカウントのみを一覧表示します。
    
- 割り当てるロール
    
    ユーザー アカウントに割り当てることができる管理者ロールの一覧を表示するには、次のコマンドを使用します。
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

アカウントの表示名とロールの名前を確認したら、次のコマンドを使用してロールをアカウントに割り当てます。
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

コマンドをメモ帳に貼り付けます。 *$dispName* 変数と *$roleName* 変数の場合は、説明テキストをそれらの値に置き換えます。 文字を削除します \< and > が、引用符は保持します。 変更した行を Microsoft Azure Active Directory モジュールの Windows PowerShell ウィンドウに貼り付けて実行します。 または、Windows PowerShell統合スクリプト環境 (ISE) を使用することもできます。
  
完了したコマンド セットの例を次に示します。
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a>ユーザー アカウントのサインイン名

ユーザー アカウントのサインイン名または UPN の操作に慣れている場合は、次の情報を決定します。
  
- ユーザー アカウントの UPN
    
    UPN がわからない場合は、次のコマンドを使用します。
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    このコマンドは、UPN で並べ替えられたユーザー アカウントの UPN を一度に 1 画面ずつ一覧表示します。 **Where** コマンドレットを使用して、リストをフィルター処理できます。 次に例を示します。
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    このコマンドは、表示名が「John」で始まるユーザー アカウントのみを一覧表示します。
    
- 割り当てるロール
    
    ユーザー アカウントに割り当てることができるロールの一覧を表示するには、次のコマンドを使用します。
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

アカウントの UPN とロールの名前を取得したら、次のコマンドを使用してロールをアカウントに割り当てます。
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

コマンドをコピーし、メモ帳に貼り付けます。 **$upnName** 変数と **$roleName** 変数の場合。 説明テキストをそれらの値に置き換えます。 文字を削除します \< and > が、引用符は保持します。 変更した行を Microsoft Azure Active Directory モジュールに貼り付けてWindows PowerShellウィンドウに貼り付けて実行します。 または、WINDOWS POWERSHELL ISE を使用することもできます。
  
完了したコマンド セットの例を次に示します。
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a>複数のロール変更

複数のロール変更の場合は、次の情報を決定します。
  
- 構成するユーザー アカウント。 前のセクションのメソッドを使用して、表示名または UPN のセットを収集できます。
    
- 各ユーザー アカウントに割り当てるロール。 ユーザー アカウントに割り当てることができるロールの一覧を表示するには、次のコマンドを使用します。
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

次に、表示名または UPN フィールドとロール名フィールドを含むコンマ区切り値 (CSV) テキスト ファイルを作成します。 これはMicrosoft Excelで簡単に行うことができます。

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

UPN の例を次に示します。
  
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
