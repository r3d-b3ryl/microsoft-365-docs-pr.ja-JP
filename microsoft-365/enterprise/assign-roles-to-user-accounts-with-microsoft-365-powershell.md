---
title: PowerShell を使用してユーザー Microsoft 365に役割を割り当てる
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
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
description: この記事では、管理者ロールをユーザー アカウントに割り当てるMicrosoft 365 PowerShell を使用する方法について説明します。
ms.openlocfilehash: 0b0fc0a5da1a6b84d4f13f95ace4846e367ae111
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60193137"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a>PowerShell を使用して管理者の役割Microsoft 365ユーザー アカウントに割り当てる

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

PowerShell を使用してユーザー アカウントに役割を簡単に割り当Microsoft 365。

>[!Note]
>管理者ロールを[ユーザー アカウントに割](../admin/add-users/assign-admin-roles.md)り当てる方法については、Microsoft 365 管理センター。
>
>その他のリソースの一覧については、「ユーザーと [グループの管理」を参照してください](/admin)。
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する

最初に **、Azure AD DC 管理者**、**クラウド** アプリケーション管理者、またはグローバル管理者アカウント [を使用](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)して、テナントMicrosoft 365します。
 
詳細については、「[管理者の役割について](/microsoft-365/admin/add-users/about-admin-roles?)」を参照してください。

次に、役割に追加するユーザー アカウントのサインイン名を特定します (例: fredsm \@ contoso.com)。 これは、ユーザー プリンシパル名 (UPN) とも呼ばれています。

次に、ロールの名前を決めます。 「Azure [AD組み込みロール」を参照してください](/azure/active-directory/roles/permissions-reference)。

>[!Note]
>この記事のメモに注意してください。 一部の役割名は、Azure Active Directory (Azure AD) PowerShell で異なります。 たとえば、Azure *SharePoint PowerShell* の Microsoft 365 管理センター管理者SharePoint管理者ADします。
>

次に、サインイン名と役割名を入力し、次のコマンドを実行します。
  
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

次に、サービス管理者の役割を *belindan \@* アカウントに割り当SharePoint完了したコマンド セット contoso.com 示します。
  
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

最初に、グローバル管理者アカウントを使用してテナント[にMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。
  
### <a name="for-a-single-role-change"></a>単一ロールの変更の場合

ユーザー アカウントを指定する最も一般的な方法は、表示名または電子メール名 (サインイン名またはユーザー プリンシパル名 (UPN) とも呼ばれる) を使用します。

#### <a name="display-names-of-user-accounts"></a>ユーザー アカウントの表示名

ユーザー アカウントの表示名の操作に使用する場合は、次の情報を確認します。
  
- 構成するユーザー アカウント
    
    ユーザー アカウントを指定するには、その表示名を判別する必要があります。 アカウントの完全な一覧を取得するには、次のコマンドを使用します。
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    このコマンドにより、ユーザー アカウントの表示名の一覧が、表示名順に並び替えられて、一度に 1 画面ずつ示されます。 **Where** コマンドレットを使用すると、一覧をフィルター処理して、出力するセットを小さくできます。 次の例をご覧ください。

   >[!Note]
   >PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に *Msol* が含まれるコマンドレットをサポートしていません。 これらのコマンドレットは、Windows PowerShell から実行します。
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    このコマンドは、表示名が「John」で始まるユーザー アカウントのみを一覧表示します。
    
- 割り当てる役割
    
    ユーザー アカウントに割り当て可能な管理者ロールの一覧を表示するには、次のコマンドを使用します。
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

アカウントの表示名と役割の名前を確認した後、次のコマンドを使用して役割をアカウントに割り当てる。
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

コマンドを別のメモ帳。 変数と *$dispName* 変数 *$roleName、* 説明テキストを値に置き換える必要があります。 文字を \< and > 削除しますが、二重引用符は保持します。 変更した行を [モジュール] ウィンドウMicrosoft Azure Active Directoryに貼りWindows PowerShellして実行します。 または、統合スクリプト環境 (ISE) Windows PowerShellを使用することもできます。
  
完了したコマンド セットの例を次に示します。
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a>ユーザー アカウントのサインイン名

ユーザー アカウントのサインイン名または UPN の操作に使用する場合は、次の情報を確認します。
  
- ユーザー アカウントの UPN
    
    UPN が分からない場合は、次のコマンドを使用します。
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    このコマンドは、ユーザー アカウントの UPN を UPN で並べ替え、一度に 1 つの画面で一覧表示します。 Where コマンドレットを使用 **して** リストをフィルター処理できます。 次に例を示します:
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    このコマンドは、表示名が「John」で始まるユーザー アカウントのみを一覧表示します。
    
- 割り当てる役割
    
    ユーザー アカウントに割り当てることができるロールの一覧を表示するには、次のコマンドを使用します。
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

アカウントの UPN と役割の名前を確認した後、次のコマンドを使用して役割をアカウントに割り当てします。
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

コマンドをコピーし、コマンドに貼りメモ帳。 変数の **$upnName** 変数 **$roleName** します。 説明テキストを値に置き換える。 文字を \< and > 削除しますが、二重引用符は保持します。 変更した行を [モジュール] ウィンドウMicrosoft Azure Active Directoryに貼りWindows PowerShell実行します。 または、ISE のWindows PowerShell使用できます。
  
完了したコマンド セットの例を次に示します。
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a>複数の役割の変更

複数の役割を変更する場合は、次の情報を確認します。
  
- 構成するユーザー アカウント。 前のセクションのメソッドを使用して、表示名または UPN のセットを収集できます。
    
- 各ユーザー アカウントに割り当てるロール。 ユーザー アカウントに割り当てることができるロールの一覧を表示するには、次のコマンドを使用します。
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

次に、表示名または UPN フィールドと役割名フィールドを持つコンマ区切り値 (CSV) テキスト ファイルを作成します。 この操作は、次の手順で簡単Microsoft Excel。

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
