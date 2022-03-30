---
title: PowerShell で Microsoft 365 ユーザー アカウントを表示する
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/17/2020
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
- LIL_Placement
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: bb12f49d-a85d-4f3b-ada2-5c4e33977b10
description: PowerShell を使用して、さまざまな方法で Microsoft 365 ユーザー アカウントを閲覧、一覧表示、表示する方法について説明します。
ms.openlocfilehash: 5c434825da95fd7d90594b2424cab287305f7d26
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2021
ms.locfileid: "60667508"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a>PowerShell で Microsoft 365 ユーザー アカウントを表示する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365 管理センターを使用して、Microsoft 365 テナントのアカウントを表示できます。 PowerShell for Microsoft 365 では、これが可能なだけでなく、追加の機能も用意されています。
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する

まず、[Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
  
### <a name="view-all-accounts"></a>すべてのアカウントを表示する

ユーザー アカウントの完全な一覧を表示するには、次のコマンドを実行します。
  
```powershell
Get-AzureADUser
```

次のような情報が表示されます。
  
```powershell
ObjectId                             DisplayName                                           UserPrincipalName
--------                             -----------                                           -----------------
032fc1fc-b5a2-46f1-8635-3d7dcb52c48d Adele Vance                                           AdeleV@litwareinc.OnMicr...
bd1e6af1-41e7-4f77-a2ac-5b209950135c Global Administrator                                  admin@litwareinc.onmicro...
ec37a4d6-232e-4eb7-82a5-1613490642a5 Alex Wilber                                           AlexW@litwareinc.OnMicro...
be4bdddd-c790-424c-9f96-a0cf609b7815 Allan Deyoung                                         AllanD@litwareinc.OnMicr...
598ab87b-76f0-4bf9-9538-bd46b10f4438 Christie Cline                                        ChristieC@litwareinc.OnM...
40722671-e520-4a5f-97d4-0bc9e9b2dc0f Debra Berger                                          DebraB@litwareinc.OnMicr...
```

### <a name="view-a-specific-account"></a>特定のアカウントを表示する

特定のユーザー アカウントを表示するには、次のコマンドを実行します。 ユーザー アカウントのサインイン アカウント名 (ユーザー プリンシパル名 (UPN) とも呼ばれる) を入力します。 "<" 文字と ">" 文字を削除します。
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

次に例を示します。
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a>特定のアカウントの追加のプロパティ値を表示する

既定では、**Get-AzureADUser** コマンドレットは、アカウントの *ObjectID*、*DisplayName*、*UserPrincipalName* の各プロパティを表示します。

表示するプロパティをより詳細に選択するには、**Select** コマンドレットを **Get-AzureADUser** コマンドレットと組み合わせて使用します。 この 2 つのコマンドレットを組み合わせるには、"パイプ" 文字 ("|") を使用します。この文字は、1 つのコマンドの結果を次のコマンドに送るよう Azure Active Directory PowerShell for Graph に指示します。 すべてのユーザー アカウントの *DisplayName*、*Department*、*UsageLocation* を表示するコマンドの例を次に示します。
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

このコマンドによって PowerShell に対して次の処理が命令されます。
  
1. ユーザー アカウントのすべての情報を取得 (**Get-AzureADUser**) して、次のコマンドにそれを送信します (**|**)。
    
1.  ユーザー アカウント名、部署、使用場所 (**Select DisplayName、Department、UsageLocation**) だけを表示する。
  
特定のユーザー アカウントのすべてのプロパティを表示するには、**Select** コマンドレットとワイルドカード文字 (*) を使用します。 次に例を示します。
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

別の例として、次のコマンドを実行して、特定のユーザー アカウントの有効な状態を確認します。
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a>アカウントの同期状態を表示する

ユーザー アカウントには、次の 2 つのソースがあります。 

- オンプレミス AD からクラウドに同期するアカウントである Windows Server Active Directory (AD)。

- クラウドに直接作成される Azure Active Directory (Azure AD) アカウント。

次のコマンドを使用して、**オンプレミス** AD のアカウントから同期しているアカウントを検索できます。 属性 *DirSyncEnabled* が *True* に設定されているすべてのユーザーを取得するように PowerShell に指示します。 

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

次のコマンドを使用して、**クラウド専用** アカウントを検索できます。 属性 *DirSyncEnabled* が *False* に設定されているか、設定されていない (*Null* である) すべてのユーザーを取得するように PowerShell に指示します。
オンプレミス AD から同期されたことがないアカウントでは、*DirSyncEnabled* が *Null* に設定されています。 最初にオンプレミス AD から同期されたものの、同期されなくなったアカウントでは、*DirSyncEnabled* が *False* に設定されています。 

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $true}
```

### <a name="view-accounts-based-on-a-common-property"></a>共通プロパティに基づいてアカウントを表示する

表示するアカウント一覧をより詳細に選択するには、**Where** コマンドレットを **Get-AzureADUser** コマンドレットと組み合わせて使用できます。 この 2 つのコマンドレットを組み合わせるには、"パイプ" 文字 ("|") を使用します。この文字は、1 つのコマンドの結果を次のコマンドに送るよう Azure Active Directory PowerShell for Graph に指示します。 次に、使用場所が指定されていないユーザー アカウントのみを表示するコマンドの例を示します。
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

このコマンドにより、Azure Active Directory PowerShell for Graph に対して次の処理が命令されます。
  
1. ユーザー アカウントのすべての情報を取得 (**Get-AzureADUser**) して、次のコマンドにそれを送信します (**|**)。
    
1. 使用場所が指定されていないすべてのユーザー アカウントを検索します (**Where {$\_.UsageLocation -eq $Null}**)。 中かっこの中で、コマンドは PowerShell に対して、UsageLocation ユーザー アカウント プロパティ (**$\_.UsageLocation**) が指定されていない (**-eq $Null**) アカウントのセットだけを検索するように指示しています。
    
**UsageLocation** プロパティは、ユーザー アカウントに関連付けられている多数のプロパティのうちの 1 つに過ぎません。 特定のユーザー アカウントのすべてのプロパティを表示するには、**Select** コマンドレットとワイルドカード文字 (*)を使用します。 次に例を示します。
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

たとえば、**City** がユーザー アカウント プロパティの名前であるとします。 つまり、以下のコマンドを使用すると、ロンドン在住のユーザーのすべてのアカウントの一覧を表示できます。
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
> この例に示されている **Where** コマンドレットの構文は、**Where {$\_.** [user account property name] [comparison operator] [value] **}** です。> [comparison operator] は **-eq** (等しい)、**-ne** (等しくない)、**-lt** (より小さい)、**-gt** (より大きい) などです。  [value] は通常、文字列 (文字、数字などのシーケンス)、数値、**$Null** (未指定の場合) のいずれかです。 詳細については、「[Where](/powershell/module/microsoft.powershell.core/where-object)」を参照してください。

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する

まず、[Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

### <a name="view-all-accounts"></a>すべてのアカウントを表示する

ユーザー アカウントの完全な一覧を表示するには、次のコマンドを実行します。
  
```powershell
Get-MsolUser
```

>[!Note]
>PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に *Msol* が含まれるコマンドレットをサポートしていません。
>

次のような情報が表示されます。
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

**Get-MsolUser** コマンドレットには、表示するユーザー アカウントのセットをフィルターにかけるための一連のパラメーターもあります。たとえば、ライセンス未付与のユーザーの一覧 (Microsoft 365 に追加されたものの、どのサービスを使用するライセンスもまだ与えられていないユーザー) を表示するには、次のコマンドを実行します。
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

次のような情報が表示されます。
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

表示されるユーザー アカウントのセットをフィルター処理するための追加のパラメーターの詳細については、「[Get-MsolUser](/previous-versions/azure/dn194133(v=azure.100))」を参照してください。
  
### <a name="view-a-specific-account"></a>特定のアカウントを表示する

特定のユーザー アカウントを表示するには、次のコマンドを実行します。 ユーザー アカウントのサインイン名 (ユーザー プリンシパル名 (UPN) とも呼ばれる) を入力します。 "<" 文字と ">" 文字を削除します。
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a>共通プロパティに基づいてアカウントを表示する

表示するアカウント一覧をより詳細に選択するには、**Where** コマンドレットを **Get-MsolUser** コマンドレットと組み合わせて使用できます。 この 2 つのコマンドレットを組み合わせるには、"パイプ" 文字 ("|") を使用します。この文字は、1 つのコマンドの結果を次のコマンドに送るよう PowerShell に指示します。 次に、使用場所が指定されていないユーザー アカウントのみを表示する例を示します。
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

このコマンドによって PowerShell に対して次の処理が命令されます。
  
1. ユーザー アカウントのすべての情報を取得 (**Get-MsolUser**) して、次のコマンドにそれを送信する (**|**)。
    
1. 使用場所が指定されていないすべてのユーザー アカウントを検索します (**Where {$\_.UsageLocation -eq $Null}**)。 中かっこの中で、コマンドは PowerShell に対して、UsageLocation ユーザー アカウント プロパティ (**$\_.UsageLocation**) が指定されていない (**-eq $Null**) アカウントのセットだけを検索するように指示しています。
    
次のような情報が表示されます。
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

*UsageLocation* プロパティは、ユーザー アカウントに関連付けられている多数のプロパティのうちの 1 つに過ぎません。 ユーザー アカウントのすべてのプロパティを表示するには、**Select** コマンドレットとワイルドカード文字 (*) を使用して、特定のユーザー アカウントのすべてのプロパティを表示します。 次に例を示します。
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

たとえば、*City* がユーザー アカウント プロパティの名前であるとします。 つまり、以下のコマンドを使用すると、ロンドン在住のユーザーのすべてのユーザー アカウントの一覧を表示できます。
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
> この例に示されている **Where** コマンドレットの構文は、**Where {$\_.** [user account property name] [comparison operator] [value] **}** です。  [comparison operator] は **-eq** (等しい)、**-ne** (等しくない)、**-lt** (より小さい)、**-gt** (より大きい) などです。  [value] は通常、文字列 (文字、数字などのシーケンス)、数値、**$Null** (未指定の場合) のいずれかです。 詳細については、「[Where](/powershell/module/microsoft.powershell.core/where-object)」を参照してください。
  
ユーザー アカウントのブロック状態を確認するには、次のコマンドを使用します。
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a>アカウントの追加のプロパティ値を表示する

既定では、**Get-MsolUser** コマンドレットは、ユーザー アカウントの次の 3 つのプロパティを表示します。
  
- UserPrincipalName

- DisplayName

- isLicensed

ユーザーの勤務先の部署やユーザーが Microsoft 365 サービスを使用する国/地域などの追加プロパティが必要な場合、**Get-MsolUser** を **Select** コマンドレットを組み合わせて実行し、ユーザー アカウント プロパティの一覧を指定できます。 次に例を示します。
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

このコマンドによって PowerShell に対して次の処理が命令されます。
  
1. ユーザー アカウントのすべての情報を取得 (**Get-MsolUser**) して、次のコマンドにそれを送信する (**|**)。
    
1. ユーザー アカウント名、部署、使用場所 (**Select DisplayName、Department、UsageLocation**) だけを表示する。
    
次のような情報が表示されます。
  
```powershell
DisplayName             Department                       UsageLocation
-----------             ----------                       -------------
Bonnie Kearney          Sales & Marketing                    US
Fabrice Canel           Legal                                US
Brian Johnson
Anne Wallace            Executive Management                 US
Alex Darrow             Sales & Marketing                    US
Scott Wallace           Operations
```

**Select** コマンドレットでは、表示するプロパティを選択できます。 特定のユーザー アカウントのすべてのプロパティを表示するには、ワイルドカード文字 (*)を使用します。 次に例を示します。
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

アカウントの一覧をより選択的に表示する場合には、**Where** コマンドレットも使用できます。次に、使用場所が指定されていないユーザー アカウントのみを表示するコマンドの例を示します。
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

このコマンドによって PowerShell に対して次の処理が命令されます。
  
1. ユーザー アカウントのすべての情報を取得 (**Get-MsolUser**) して、次のコマンドにそれを送信する (**|**)。
    
1. 使用場所が指定されていないすべてのユーザー アカウントを検索して (**Where {$\_.UsageLocation -eq $Null}**)、結果の情報を次のコマンドに送る (**|**)。中かっこの中で、コマンドは PowerShell に対して、UsageLocation ユーザー アカウント プロパティ (**$\_.UsageLocation**) が指定されていない (**-eq $Null**) アカウントのセットだけを検索するように指示しています。
    
1. ユーザー アカウント名、部署、使用場所 (**Select DisplayName、Department、UsageLocation**) だけを表示する。
    
次のような情報が表示されます。
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

Microsoft 365 ユーザーの作成と管理にディレクトリ同期を使用している場合、Microsoft 365 ユーザーが投影されたローカル アカウントを表示できます。 次の例では、次のことを前提としています。

- Azure AD Connect は、ObjectGUID の既定のソース アンカーを使用するように構成されています。 (ソース アンカーの構成の詳細については、「[Azure AD Connect: デザインの概念](/azure/active-directory/hybrid/plan-connect-design-concepts)」を参照してください)。
- PowerShell の Active Directory Domain Services モジュールがインストールされています (「[RSAT ツール](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)」を参照してください)。

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a>関連項目

[Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)
