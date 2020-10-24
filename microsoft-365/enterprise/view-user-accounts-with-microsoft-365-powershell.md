---
title: PowerShell を使用して Microsoft 365 ユーザーアカウントを表示する
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
description: PowerShell を使用して、Microsoft 365 ユーザーアカウントをさまざまな方法で表示、一覧表示、または表示する方法について説明します。
ms.openlocfilehash: 312e9fb983c4d1f4de8bc74586c88f1e669eb90a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754074"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a>PowerShell を使用して Microsoft 365 ユーザーアカウントを表示する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365 管理センターを使用して、Microsoft 365 テナントのアカウントを表示することができます。 Microsoft 365 の PowerShell は、これを可能にしますが、その他の機能も提供します。
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する

最初に、 [Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)します。
  
### <a name="view-all-accounts"></a>すべてのアカウントを表示する

ユーザーアカウントの完全な一覧を表示するには、次のコマンドを実行します。
  
```powershell
Get-AzureADUser
```

次のような情報が表示されるはずです。
  
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

特定のユーザーアカウントを表示するには、次のコマンドを実行します。 ユーザーアカウントのサインインアカウント名を入力します。これは、ユーザープリンシパル名 (UPN) とも呼ばれます。 "<" および ">" 文字を削除します。
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

次に例を示します:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a>特定のアカウントの追加のプロパティ値を表示する

既定では、 **set-azureaduser** コマンドレットでは、アカウントの *ObjectID*、 *DisplayName*、および *UserPrincipalName* のプロパティのみが表示されます。

表示するプロパティをより詳細に選択するには、 **Select** コマンドレットを **set-azureaduser** コマンドレットと組み合わせて使用します。 2つのコマンドレットを組み合わせるには、"pipe" 文字 ("|") を使用します。これは、1つのコマンドの結果を取得して次のコマンドに送信するために、Azure Active Directory PowerShell に対してグラフを表示するように指示します。 次に、すべてのユーザーアカウントの *DisplayName*、 *Department*、および使用 *場所* を表示するコマンドの例を示します。
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

次のコマンドは、PowerShell に次のように指示します。
  
1. ユーザーアカウントのすべての情報を取得し (**set-azureaduser**)、次のコマンドに送信します ( **|** )。
    
1.  ユーザーアカウント名、部署、および使用場所のみを表示します (**DisplayName、department、および使用場所を選択し**ます)。
  
特定のユーザーアカウントのすべてのプロパティを表示するには、 **Select** コマンドレットとワイルドカード文字 (*) を使用します。 次に例を示します:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

別の例として、次のコマンドを実行して、特定のユーザーアカウントの有効な状態を確認します。
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a>アカウントの同期状態を表示する

ユーザーアカウントには2つのソースがあります。 

- Windows Server Active Directory (AD)。これは、オンプレミス AD からクラウドに同期するアカウントです。

- Azure Active Directory (Azure AD) AD アカウント。クラウドに直接作成されます。


次のコマンドは、 *Dirsyncenabled* 属性が *True*に設定されているすべてのユーザーを取得するように PowerShell に指示します。 これを使用して、オンプレミスの AD から同期しているアカウントを検索できます。

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

次のコマンドは、 *Dirsyncenabled* 属性が *False*に設定されているすべてのユーザーを取得するように PowerShell に指示します。 これを使用して、クラウド専用のアカウントを見つけることができます。

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a>共通プロパティに基づいてアカウントを表示する

表示するアカウントの一覧をより詳細に選択できるようにするには、 **set-azureaduser**コマンドレットと組み合わせて**Where**コマンドレットを使用します。 2つのコマンドレットを組み合わせるには、"pipe" 文字 ("|") を使用します。これは、1つのコマンドの結果を取得して次のコマンドに送信するために、Azure Active Directory PowerShell に対してグラフを表示するように指示します。 次に示すのは、指定されていない使用場所を持つユーザーアカウントのみを表示するコマンドの例です。
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

次のコマンドは、Azure Active Directory PowerShell を Graph に対して次のように指示します。
  
1. ユーザーアカウントのすべての情報を取得し (**set-azureaduser**)、次のコマンドに送信します ( **|** )。
    
1. 使用できない場所が指定されているすべてのユーザーアカウントを検索し**ます (Where {$ \_ .の場合は、-eq $Null}**) を指定します。 中かっこの内側では、コマンドは、アクセス先ユーザーアカウントプロパティ (で使用するアカウントのセットのみを検索するように PowerShell に指示し** $ \_ ます。** は、無効な場所) を指定しません (**-eq $Null**)。
    
使用 **場所** プロパティは、ユーザーアカウントに関連付けられている多くのプロパティのうちの1つにすぎません。 特定のユーザーアカウントのすべてのプロパティを表示するには、 **Select** コマンドレットとワイルドカード文字 (*) を使用します。 次に例を示します:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

たとえば、 **City** はユーザーアカウントプロパティの名前です。 London に居住しているユーザーのすべてのアカウントを一覧表示するには、次のコマンドを使用します。
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  これらの例の **where** コマンドレットの構文は、 **{$ \_ .** [ユーザーアカウントのプロパティ名][比較演算子]金額 **}**. > [比較演算子] は、equals、 **-ne** for not equals、 **-lt** (より小さい、-gt (より大きい)、- **gt** (より大きい)、およびその他の場合に- **eq**を指定します。  [value] は通常、文字列 (一連の文字、数字、その他の文字)、数値、または **$Null** 指定なしの場合に使用します。 詳細については、「 [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7)」を参照してください。
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する

最初に、 [Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)します。

### <a name="view-all-accounts"></a>すべてのアカウントを表示する

ユーザーアカウントの完全な一覧を表示するには、次のコマンドを実行します。
  
```powershell
Get-MsolUser
```

>[!Note]
>PowerShell Core は、Windows PowerShell モジュール用 Microsoft Azure Active Directory モジュールと、名前に *Msol* を指定したコマンドレットをサポートしていません。 これらのコマンドレットを Windows PowerShell から実行します。
>

次のような情報が表示されるはずです。
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

**Get-MsolUser** コマンドレットには、表示するユーザー アカウントのセットをフィルターにかけるための一連のパラメーターもあります。 たとえば、ライセンスのないユーザー (Microsoft 365 に追加されていても、サービスのいずれかを使用するライセンスを持っていないユーザー) の一覧については、次のコマンドを実行します。
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

次のような情報が表示されるはずです。
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

表示されるユーザーアカウントのセットをフィルター処理するための追加パラメーターの詳細については、「 [get-msoluser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100))」を参照してください。
  
### <a name="view-a-specific-account"></a>特定のアカウントを表示する

特定のユーザーアカウントを表示するには、次のコマンドを実行します。 ユーザーアカウントのサインイン名を入力します。これは、ユーザープリンシパル名 (UPN) とも呼ばれます。 "<" および ">" 文字を削除します。
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a>共通プロパティに基づいてアカウントを表示する

表示するアカウントの一覧をより詳細に選択できるようにするには、 **get-msoluser**コマンドレットと組み合わせて**Where**コマンドレットを使用します。 2つのコマンドレットを組み合わせるには、"pipe" 文字 ("|") を使用します。これは、1つのコマンドの結果を受け取って次のコマンドに送信するように PowerShell に指示します。 次に示すのは、指定されていない使用場所を持つユーザーアカウントのみを表示する例です。
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

次のコマンドは、PowerShell に次のように指示します。
  
1. ユーザーアカウントのすべての情報を取得し (**get-msoluser**)、次のコマンドに送信します ( **|** )。
    
1. 使用できない場所が指定されているすべてのユーザーアカウントを検索**します (Where {$ \_ .の場合は、-eq $Null}**) を指定します。 中かっこ内では、コマンドによって、アクセス先ユーザーアカウントプロパティ (で使用されるアカウントのセットのみを検索するように PowerShell に指示し** $ \_ ます。** は、無効な場所) を指定しません (**-eq $Null**)。
    
次のような情報が表示されるはずです。
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

使用 *場所* プロパティは、ユーザーアカウントに関連付けられている多くのプロパティのうちの1つにすぎません。 ユーザーアカウントのすべてのプロパティを表示するには、 **Select** コマンドレットとワイルドカード文字 (*) を使用して、特定のユーザーアカウントについてすべてのプロパティを表示します。 次に例を示します:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

たとえば、 *City* はユーザーアカウントプロパティの名前です。 London に居住しているユーザーのすべてのユーザーアカウントを一覧表示するには、次のコマンドを使用します。
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  これらの例の **where** コマンドレットの構文は、 **{$ \_ .** [ユーザーアカウントのプロパティ名][比較演算子]金額 **}**.  [comparison operator] は **-eq** (等しい)、 **-ne** for not equals、 **-lt** (より小さい)、- **gt** (より大きい)、または他のものです。  [value] は通常、文字列 (一連の文字、数字、その他の文字)、数値、または **$Null** 指定なしの場合に使用します。 詳細については、「 [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7)」を参照してください。
  
ユーザーアカウントのブロックされた状態を確認するには、次のコマンドを使用します。
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a>アカウントの追加のプロパティ値を表示する

既定では、 **get-msoluser** コマンドレットでは、ユーザーアカウントの次の3つのプロパティが表示されます。
  
- UserPrincipalName
    
- DisplayName
    
- isLicensed
    
ユーザーが機能する部署や、Microsoft 365 サービスを使用する国/地域など、追加のプロパティが必要な場合は、 **get-msoluser** を **Select** コマンドレットと組み合わせて実行し、ユーザーアカウントのプロパティの一覧を指定できます。 次に例を示します:
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

次のコマンドは、PowerShell に次のように指示します。
  
1. ユーザーアカウントに関するすべての情報を取得し (**get-msoluser**)、次のコマンドに送信し **|** ます ()。
    
1. ユーザーアカウント名、部署、および使用場所のみを表示します (**DisplayName、department、および使用場所を選択し**ます)。
    
次のような情報が表示されるはずです。
  
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

**Select**コマンドレットを使用すると、表示するプロパティを選択できます。 特定のユーザーアカウントのすべてのプロパティを表示するには、ワイルドカード文字 (*) を使用します。 次に例を示します:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

表示するアカウントのリストをより詳細に選択できるようにするには、 **Where** コマンドレットを使用することもできます。 次に示すのは、指定されていない使用場所を持つユーザーアカウントのみを表示するコマンドの例です。
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

次のコマンドは、PowerShell に次のように指示します。
  
1. ユーザーアカウントに関するすべての情報を取得し (**get-msoluser**)、次のコマンドに送信し **|** ます ()。
    
1. 使用できない場所が指定されているすべてのユーザーアカウントを検索**します (Where {$ \_ .[実行場所-eq $Null}**)] を指定して、結果の情報を次のコマンドに送信し **|** ます ()。 中かっこの内側では、コマンドは、アクセス先ユーザーアカウントプロパティ (で使用するアカウントのセットのみを検索するように PowerShell に指示し** $ \_ ます。** は、無効な場所) を指定しません (**-eq $Null**)。
    
1. ユーザーアカウント名、部署、および使用場所のみを表示します (**DisplayName、department、および使用場所を選択し**ます)。
    
次のような情報が表示されるはずです。
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

ディレクトリ同期を使用して Microsoft 365 ユーザーを作成および管理している場合は、Microsoft 365 ユーザーが射影されているローカルアカウントを表示できます。 次の例では、このことを前提としています。

- Azure AD Connect は、ObjectGUID の既定のソースアンカーを使用するように構成されています。 (ソースアンカーの構成の詳細については、「 [AZURE AD Connect: デザインの概念](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)」を参照してください)。
- PowerShell の Active Directory ドメインサービスモジュールがインストールされていること (「 [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)」を参照してください)。

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a>関連項目

[Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)
