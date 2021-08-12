---
title: PowerShell Microsoft 365ユーザー アカウントを表示する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
- LIL_Placement
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: bb12f49d-a85d-4f3b-ada2-5c4e33977b10
description: PowerShell を使用して、さまざまな方法でユーザー アカウントMicrosoft 365表示、一覧表示、または表示する方法について説明します。
ms.openlocfilehash: b7a899d7b67b124ffa1db391cd8762cf220d1aa9da01a9e60cb7cb488da1bd34
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53812960"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a>PowerShell Microsoft 365ユーザー アカウントを表示する

*この記事は、Microsoft 365 Enterprise と Office 365 Enterprise の両方に適用されます。*

このサイトを使用Microsoft 365 管理センターテナントのアカウントをMicrosoft 365できます。 PowerShell for Microsoft 365これを有効にし、追加の機能も提供します。
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する

最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
  
### <a name="view-all-accounts"></a>すべてのアカウントを表示する

ユーザー アカウントの完全な一覧を表示するには、次のコマンドを実行します。
  
```powershell
Get-AzureADUser
```

次のような情報を取得する必要があります。
  
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

**既定では、Get-AzureADUser コマンドレット** は、アカウントの *ObjectID、DisplayName、* および *UserPrincipalName* プロパティのみを表示します。 

表示するプロパティの詳細を選択するには **、Select** コマンドレットを **Get-AzureADUser** コマンドレットと組み合わせて使用します。 2 つのコマンドレットを組み合わせるには、"パイプ" 文字 ("|") を使用して、Azure Active Directory PowerShell に Graph のコマンドの結果を取得し、次のコマンドに送信します。 すべてのユーザー アカウントの DisplayName、Department、UsageLocation を表示する *コマンド* の例を次に示します。  
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

このコマンドは、PowerShell に次の指示を行います。
  
1. ユーザー アカウント **(Get-AzureADUser)** のすべての情報を取得し、次のコマンド ( ) に送信します **|** 。
    
1.  ユーザー アカウント名、部署、使用状況の場所のみを表示します **([DisplayName、 Department, UsageLocation] の選択**)。
  
特定のユーザー アカウントのすべてのプロパティを表示するには **、Select** コマンドレットとワイルドカード文字 (*)を使用します。 次に例を示します。
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

別の例として、次のコマンドを実行して、特定のユーザー アカウントの有効な状態を確認します。
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a>アカウントの同期状態の表示

ユーザー アカウントには、次の 2 つのソースがあります。 

- Windows Server Active Directory (AD) は、オンプレミスのユーザーからクラウドに同期ADアカウントです。

- Azure Active Directory (Azure AD) AD、クラウドに直接作成されるアカウントです。


次のコマンドは、属性 *DirSyncEnabled* を True に設定しているすべてのユーザーを取得するように PowerShell に指示 *します*。 この機能を使用して、オンプレミスのアカウントから同期しているアカウントをAD。

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

次のコマンドは、属性 *DirSyncEnabled* を False に設定しているすべてのユーザーを取得するように PowerShell に指示 *します*。 クラウド専用アカウントの検索に使用できます。

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a>共通プロパティに基づいてアカウントを表示する

表示するアカウントの一覧を選択するには **、Get-AzureADUser** コマンドレットと組み合わせて Where コマンドレットを使用できます。 2 つのコマンドレットを組み合わせるには、"パイプ" 文字 ("|") を使用して、Azure Active Directory PowerShell に Graph のコマンドの結果を取得し、次のコマンドに送信します。 使用場所が指定されていないユーザー アカウントのみを表示するコマンドの例を次に示します。
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

このコマンドは、次Azure Active Directory PowerShell にGraph指示します。
  
1. ユーザー アカウント **(Get-AzureADUser)** のすべての情報を取得し、次のコマンド ( ) に送信します **|** 。
    
1. 使用場所が指定されていないすべてのユーザー アカウントを検索します **(Where {$ \_ .UsageLocation -eq $Null}**)。 中かっこ内で、このコマンドは、UsageLocation ユーザー アカウント プロパティ (**$ \_ .UsageLocation**) は指定されていません (**-eq $Null)。**
    
**UsageLocation プロパティ** は、ユーザー アカウントに関連付けられている多数のプロパティの 1 つのみです。 特定のユーザー アカウントのすべてのプロパティを表示するには **、Select** コマンドレットとワイルドカード文字 (*)を使用します。 次に例を示します。
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

たとえば **、City は** ユーザー アカウント プロパティの名前です。 次のコマンドを使用して、ロンドンに住むユーザーのすべてのアカウントを一覧表示できます。
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
> これらの例の **Where コマンドレット** の構文は **、Where {$ です \_ 。** [ユーザー アカウントのプロパティ名][比較演算子][value] **}**.> [比較演算子] は、等号の場合は **-eq、** 等しくない場合は **-ne、** より小さい場合は **-lt、** より大きい場合は **-gt、** その他は -gt です。  [value] は通常、文字列 (一連の文字、数字、その他の文字)、数値、または指定されていない$Null指定します。 詳細については [、「Where」 を参照してください](/powershell/module/microsoft.powershell.core/where-object)。

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する

最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

### <a name="view-all-accounts"></a>すべてのアカウントを表示する

ユーザー アカウントの完全な一覧を表示するには、次のコマンドを実行します。
  
```powershell
Get-MsolUser
```

>[!Note]
>PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に *Msol* が含まれるコマンドレットをサポートしていません。 これらのコマンドレットは、Windows PowerShell から実行します。
>

次のような情報を取得する必要があります。
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

**Get-MsolUser** コマンドレットには、表示するユーザー アカウントのセットをフィルターにかけるための一連のパラメーターもあります。 たとえば、ライセンスのないユーザーの一覧 (Microsoft 365 に追加されたが、まだサービスを使用するライセンスが与えされていないユーザー) の場合は、次のコマンドを実行します。
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

次のような情報を取得する必要があります。
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

表示されるユーザー アカウントのセットをフィルター処理する追加のパラメーターの詳細については [、「Get-MsolUser」を参照してください](/previous-versions/azure/dn194133(v=azure.100))。
  
### <a name="view-a-specific-account"></a>特定のアカウントを表示する

特定のユーザー アカウントを表示するには、次のコマンドを実行します。 ユーザー アカウントのサインイン名 (ユーザー プリンシパル名 (UPN) とも呼ばれる) を入力します。 "<" 文字と ">" 文字を削除します。
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a>共通プロパティに基づいてアカウントを表示する

表示するアカウントの一覧を選択するには **、Get-MsolUser** コマンドレットと組み合わせて **Where** コマンドレットを使用できます。 2 つのコマンドレットを組み合わせるには、"pipe" 文字 ("|") を使用して、PowerShell に 1 つのコマンドの結果を取得し、次のコマンドに送信します。 使用場所が指定されていないユーザー アカウントのみを表示する例を次に示します。
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

このコマンドは、PowerShell に次の指示を行います。
  
1. ユーザー アカウント **(Get-MsolUser)** のすべての情報を取得し、次のコマンド ( ) に送信します **|** 。
    
1. 使用場所が指定されていないすべてのユーザー アカウントを検索します **(Where {$ \_ .UsageLocation -eq $Null}**)。 中かっこ内で、このコマンドは、UsageLocation ユーザー アカウント プロパティ (**$ \_ .UsageLocation**) は指定されていません (**-eq $Null)。**
    
次のような情報を取得する必要があります。
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

*UsageLocation プロパティ* は、ユーザー アカウントに関連付けられている多数のプロパティの 1 つのみです。 ユーザー アカウントのすべてのプロパティを表示するには **、Select** コマンドレットとワイルドカード文字 (*) を使用して、それらをすべて特定のユーザー アカウントに表示します。 次に例を示します。
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

たとえば *、City は* ユーザー アカウント プロパティの名前です。 次のコマンドを使用して、ロンドンに住むユーザーのすべてのユーザー アカウントを一覧表示できます。
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
> これらの例の **Where コマンドレット** の構文は **、Where {$ です \_ 。** [ユーザー アカウントのプロパティ名][比較演算子][value] **}**.  [比較演算子] は、等しい場合は **-eq、** 等しくない場合は **-ne、** より小さい場合は **-lt、** より大きい場合は **-gt、** その他は -gt です。  [value] は通常、文字列 (一連の文字、数字、その他の文字)、数値、または指定されていない$Null指定します。 詳細については [、「Where」 を参照してください](/powershell/module/microsoft.powershell.core/where-object)。
  
ユーザー アカウントのブロックされた状態を確認するには、次のコマンドを使用します。
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a>アカウントの追加のプロパティ値を表示する

既定では **、Get-MsolUser コマンドレットは** 、ユーザー アカウントの次の 3 つのプロパティを表示します。
  
- UserPrincipalName

- DisplayName

- isLicensed

ユーザーが働く部署、Microsoft 365 サービスを使用する国/地域などの追加のプロパティが必要な場合は **、Get-MsolUser** を Select コマンドレットと組み合わせて実行して、ユーザー アカウントのプロパティの一覧を指定できます。 次に例を示します。
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

このコマンドは、PowerShell に次の指示を行います。
  
1. ユーザー アカウント **(Get-MsolUser)** に関する情報を取得し、次のコマンド ( ) に送信します **|** 。
    
1. ユーザー アカウント名、部署、使用状況の場所のみを表示します **([DisplayName、 Department, UsageLocation] の選択**)。
    
次のような情報を取得する必要があります。
  
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

Select **コマンドレットでは** 、表示するプロパティを選択できます。 特定のユーザー アカウントのすべてのプロパティを表示するには、ワイルドカード文字 (*)を使用します。 次に例を示します。
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

表示するアカウントの一覧の詳細を選択するには **、Where** コマンドレットを使用することもできます。 使用場所が指定されていないユーザー アカウントのみを表示するコマンドの例を次に示します。
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

このコマンドは、PowerShell に次の指示を行います。
  
1. ユーザー アカウント **(Get-MsolUser)** に関する情報を取得し、次のコマンド ( ) に送信します **|** 。
    
1. 使用場所が指定されていないすべてのユーザー アカウントを検索します **(Where {$ \_ .UsageLocation -eq $Null} )** をクリックし、結果の情報を次のコマンド ( ) に送信します **|** 。 中かっこ内で、このコマンドは、UsageLocation ユーザー アカウント プロパティ (**$ \_ .UsageLocation**) は指定されていません (**-eq $Null)。**
    
1. ユーザー アカウント名、部署、使用状況の場所のみを表示します **([DisplayName、 Department, UsageLocation] の選択**)。
    
次のような情報を取得する必要があります。
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

ディレクトリ同期を使用して、Microsoft 365 ユーザーを作成および管理する場合は、Microsoft 365 ユーザーが投影されたローカル アカウントを表示できます。 次の例では、以下を前提とします。

- Azure AD Connect ObjectGUID の既定のソース アンカーを使用するように構成されています。 (ソース アンカーの構成の詳細については[、「Azure AD Connect: デザインの概念」を参照してください](/azure/active-directory/hybrid/plan-connect-design-concepts)。
- PowerShell 用の Active Directory ドメイン サービス モジュールがインストールされています [(「RSAT ツール」を参照](https://www.microsoft.com/en-gb/download/details.aspx?id=45520))。

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a>関連項目

[Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)