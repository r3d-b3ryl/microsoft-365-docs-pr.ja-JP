---
title: PowerShell を使用Microsoft 365ユーザー アカウントのプロパティを構成する
ms.author: kvice
author: kelleyvice-msft
manager: scotv
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
- Ent_Office_Other
- PowerShell
- admindeeplinkMAC
ms.assetid: 30813f8d-b08d-444b-98c1-53df7c29b4d7
description: Microsoft 365用 PowerShell を使用して、Microsoft 365 テナント内の個々のユーザー アカウントまたは複数のユーザー アカウントのプロパティを構成します。
ms.openlocfilehash: 3a1aa77a6af3995d7cd4d072b6b6c6047bf89942
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65091349"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a>PowerShell を使用Microsoft 365ユーザー アカウントのプロパティを構成する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>を使用して、Microsoft 365 テナントのユーザー アカウントのプロパティを構成できます。 PowerShell では、これを行うこともできます。また、管理センターで実行できないその他の操作も行うことができます。
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する

Azure Active Directory PowerShell for Graph モジュールでユーザー アカウントのプロパティを構成するには、[**Set-AzureADUser**](/powershell/module/azuread/set-azureaduser) コマンドレットを使用して、設定または変更するプロパティを指定します。

まず、[Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。

### <a name="change-properties-for-a-specific-user-account"></a>特定のユーザー アカウントのプロパティを変更する

*-ObjectID* パラメーターを使用してアカウントを識別し、追加のパラメーターを使用して特定のプロパティを設定または変更します。 最も一般的なパラメーターの一覧を次に示します。
  
- -Department "<部署名>"

- -DisplayName "<完全なユーザー名>"

- -FacsimilieTelephoneNumber "<FAX 番号>"

- -GivenName "<ユーザーの名>"

- -Surname "<ユーザーの姓>"

- -Mobile "<携帯電話番号>"

- -JobTitle "<役職>"

- -PreferredLanguage "<言語>"

- -StreetAddress "<番地>"

- -City "<市区町村名>"

- -State "<都道府県名>"

- -PostalCode "<郵便番号>"

- -Country "<国名>"

- -TelephoneNumber "<勤務先電話番号>"

- -UsageLocation "\<2-character country or region code>"

    これは、ISO 3166-1 alpha-2 (A2) の 2 文字の国/地域コードです。

その他のパラメーターについては、「 [Set-AzureADUser](/powershell/module/azuread/set-azureaduser)」を参照してください。

> [!NOTE]
> ユーザー アカウントにライセンスを割り当てる前に、使用場所を割り当てる必要があります。

ユーザー アカウントのユーザー プリンシパル名を表示するには、次のコマンドを実行します。
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

このコマンドによって PowerShell に対して次の処理が命令されます。
  
1. ユーザー アカウントのすべての情報を取得 (**Get-AzureADUser**) して、次のコマンドにそれを送信します (**|**)。

1. ユーザー プリンシパル名の一覧をアルファベット順に並べ **替えて (UserPrincipalName を並べ替え**)、次のコマンド (**|**) に送信します。

1. 各アカウントのユーザー プリンシパル名プロパティのみを表示します (**UserPrincipalName を選択**)。

1. 一度に 1 画面ずつ表示する (**More**)。

表示名 (名と姓) に基づいてアカウントのユーザー プリンシパル名を表示するには、次のコマンドを実行します。 *$userName* 変数を入力し、文字を\< and >削除します。
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

この例では、 *Caleb Sills* という表示名を持つユーザー アカウントのユーザー プリンシパル名を表示します。
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

*$upn* 変数を使用すると、表示名に基づいて個々のアカウントに変更を加えることができます。 *Belinda Newman* の使用場所をフランスに設定する例を次に示します。 ただし、ユーザー プリンシパル名ではなく、表示名を指定します。
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>すべてのユーザー アカウントのプロパティを変更する

すべてのユーザーのプロパティを変更するには、**Get-AzureADUser コマンドレットと Set-AzureADUser** コマンドレットを組み合わせて使用します。 次の例では、すべてのユーザーの使用場所を *フランス* に変更します。
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

このコマンドによって PowerShell に対して次の処理が命令されます。
  
1. ユーザー アカウントに関するすべての情報 (**Get-AzureADUser**) を取得し、次のコマンド (**|**) に送信します。

1. ユーザーの場所をフランスに設定します (**Set-AzureADUser -UsageLocation "FR"**)。

### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>特定のユーザー アカウント セットのプロパティを変更する

特定の一連のユーザー アカウントのプロパティを変更するには、 **Get-AzureADUser** コマンドレット、 **Where** コマンドレット、 **Set-AzureADUser** コマンドレットの組み合わせを使用できます。 次の例では、会計部門のすべてのユーザーの使用場所を *フランス* に変更します。
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

このコマンドによって PowerShell に対して次の処理が命令されます。
  
1. ユーザー アカウント (**Get-AzureADUser**) に関するすべての情報を取得し、次のコマンド (**|**) に送信します。

1.  *Department* プロパティが "Accounting" に設定されているすべてのユーザー アカウントを検索します (**ここで{$_。Department -eq "Accounting"}**)、結果の情報を次のコマンド (**|**) に送信します。

1. ユーザーの場所をフランスに設定します (**Set-AzureADUser -UsageLocation "FR"**)。

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する

Windows PowerShell用の Microsoft Azure Active Directory モジュールを使用してユーザー アカウントのプロパティを構成するには、**Set-MsolUser** コマンドレットを使用し、設定または変更するプロパティを指定します。

まず、[Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。
  
> [!NOTE]
> PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に *Msol* が含まれるコマンドレットをサポートしていません。

### <a name="change-properties-for-a-specific-user-account"></a>特定のユーザー アカウントのプロパティを変更する

特定のユーザー アカウントのプロパティを構成するには、 [**Set-MsolUser**](/previous-versions/azure/dn194136(v=azure.100)) コマンドレットを使用し、設定または変更するプロパティを指定します。 

*ユーザーは、-UserPrincipalName* パラメーターを使用してアカウントを識別し、追加のパラメーターを使用して特定のプロパティを設定または変更します。 最も一般的なパラメーターの一覧を次に示します。
  
- -City "<市区町村名>"

- -Country "<国名>"

- -Department "<部署名>"

- -DisplayName "<完全なユーザー名>"

- -Fax "<fax 番号>"

- -FirstName "<ユーザーの名>"

- -LastName "<ユーザーの姓>"

- -MobilePhone "<モバイル機器の番号>"

- -Office "<事業所の場所>"

- -PhoneNumber "<勤務先電話番号>"

- -PostalCode "<郵便番号>"

- -PreferredLanguage "<言語>"

- -State "<都道府県名>"

- -StreetAddress "<番地>"

- -Title "<役職名>"

- -UsageLocation "\<2-character country or region code>"

    これは、ISO 3166-1 alpha-2 (A2) の 2 文字の国/地域コードです。

その他のパラメーターについては、「 [Set-MsolUser](/previous-versions/azure/dn194136(v=azure.100))」を参照してください。

すべてのユーザーのユーザー プリンシパル名を表示するには、次のコマンドを実行します。
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

このコマンドによって PowerShell に対して次の処理が命令されます。
  
1. ユーザー アカウントのすべての情報 (**Get-MsolUser**) を取得し、次のコマンド (**|**) に送信します。

1. ユーザー プリンシパル名の一覧をアルファベット順に並べ **替えて (UserPrincipalName を並べ替え**)、次のコマンド (**|**) に送信します。

1. 各アカウントのユーザー プリンシパル名プロパティのみを表示します (**UserPrincipalName を選択**)。

1. 一度に 1 画面ずつ表示する (**More**)。

表示名 (名と姓) に基づいてアカウントのユーザー プリンシパル名を表示するには、次のコマンドを実行します。 *$userName* 変数を入力し、文字を削除します\< and >。
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

次の使用例は、Caleb Sills という名前のユーザーのユーザー プリンシパル名を表示します。
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

*$upn* 変数を使用すると、表示名に基づいて個々のアカウントに変更を加えることができます。 *Belinda Newman* の使用場所を *フランス* に設定し、ユーザー プリンシパル名ではなく表示名を指定する例を次に示します。
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>すべてのユーザー アカウントのプロパティを変更する

すべてのユーザーのプロパティを変更するには、 **Get-MsolUser コマンドレットと Set-MsolUser** コマンドレット **の** 組み合わせを使用します。 次の例では、すべてのユーザーの使用場所を *フランス* に変更します。
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

このコマンドによって PowerShell に対して次の処理が命令されます。
  
1. ユーザー アカウントのすべての情報 (**Get-MsolUser**) を取得し、次のコマンド (**|**) に送信します。

1. ユーザーの場所をフランスに設定します (**Set-MsolUser -UsageLocation "FR"**)。

### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>特定のユーザー アカウント セットのプロパティを変更する

特定の一連のユーザー アカウントのプロパティを変更するには、 **Get-MsolUser** コマンドレット、 **Where** コマンドレット、 **Set-MsolUser** コマンドレットの組み合わせを使用できます。 次の例では、会計部門のすべてのユーザーの使用場所を *フランス* に変更します。
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

このコマンドによって PowerShell に対して次の処理が命令されます。
  
1. ユーザー アカウントのすべての情報 (**Get-MsolUser**) を取得し、次のコマンド (**|**) に送信します。

1. *Department* プロパティが "Accounting" に設定されているすべてのユーザー アカウントを検索します (**ここで{$_.Department -eq "Accounting"}**) を選択し、結果の情報を次のコマンド (**|**) に送信します。

1. ユーザーの場所をフランスに設定します (**Set-MsolUser -UsageLocation "FR"**)。

## <a name="see-also"></a>関連項目

[Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)
