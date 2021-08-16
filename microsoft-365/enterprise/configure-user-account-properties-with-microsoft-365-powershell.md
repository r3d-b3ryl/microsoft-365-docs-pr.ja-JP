---
title: PowerShell Microsoft 365ユーザー アカウントのプロパティを構成する
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
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
- Ent_Office_Other
- PowerShell
ms.assetid: 30813f8d-b08d-444b-98c1-53df7c29b4d7
description: PowerShell を使用して、Microsoft 365テナント内の個々または複数のユーザー アカウントのプロパティMicrosoft 365します。
ms.openlocfilehash: 23d89448eb9f34d67ada8711b8ca6463a0f6acd7
ms.sourcegitcommit: e269371de759a1a747c9f292775463aa11415f25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2021
ms.locfileid: "58356626"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a>PowerShell Microsoft 365ユーザー アカウントのプロパティを構成する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

このプロパティを使用Microsoft 365 管理センターテナントのユーザー アカウントのプロパティをMicrosoft 365できます。 PowerShell では、管理センターで実行できないその他の操作も実行できます。
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する

Graph モジュールの Azure Active Directory PowerShell でユーザー アカウントのプロパティを構成するには [**、Set-AzureADUser**](/powershell/module/azuread/set-azureaduser)コマンドレットを使用して、設定または変更するプロパティを指定します。

最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。

### <a name="change-properties-for-a-specific-user-account"></a>特定のユーザー アカウントのプロパティを変更する

-ObjectID パラメーターを使用してアカウント *を識別* し、追加のパラメーターを使用して特定のプロパティを設定または変更します。 最も一般的なパラメーターの一覧を次に示します。
  
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

- -UsageLocation \<2-character country or region code> "

    これは、ISO 3166-1 alpha-2 (A2) の 2 文字の国/地域コードです。

その他のパラメーターについては [、「Set-AzureADUser」を参照してください](/powershell/module/azuread/set-azureaduser)。

> [!NOTE]
> ユーザー アカウントにライセンスを割り当てる前に、使用場所を割り当てる必要があります。

ユーザー アカウントのユーザー プリンシパル名を表示するには、次のコマンドを実行します。
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

このコマンドは、PowerShell に次の指示を行います。
  
1. ユーザー アカウント **(Get-AzureADUser)** のすべての情報を取得し、次のコマンド ( ) に送信します **|** 。

1. ユーザー プリンシパル名の一覧をアルファベット順に並べ替え (**Sort UserPrincipalName**) し、次のコマンド ( ) に送信します **|** 。

1. 各アカウントの [ユーザー プリンシパル名] プロパティ **([UserPrincipalName** の選択]) を表示します。

1. 一度に 1 画面ずつ表示する (**More**)。

表示名 (名と名) に基づいてアカウントのユーザー プリンシパル名を表示するには、次のコマンドを実行します。 変数を入力 *$userName、* 次の文字を削除 \< and > します。
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

次の使用例は、表示名 *Caleb Sills* を持つユーザー アカウントのユーザー プリンシパル名を表示します。
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

*$upn* 変数を使用すると、表示名に基づいて個々のアカウントに変更を加えることができます。 Belinda *Newman* の使用場所をフランスに設定する例を次に示します。 ただし、ユーザー プリンシパル名ではなく、表示名を指定します。
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>すべてのユーザー アカウントのプロパティを変更する

すべてのユーザーのプロパティを変更するには **、Get-AzureADUser** コマンドレットと **Set-AzureADUser** コマンドレットを組み合わせて使用できます。 次の使用例は、すべてのユーザーの使用場所をフランスに変更 *します*。
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

このコマンドは、PowerShell に次の指示を行います。
  
1. ユーザー アカウント **(Get-AzureADUser)** のすべての情報を取得し、次のコマンド ( ) に送信します **|** 。

1. ユーザーの場所をフランス **(Set-AzureADUser -UsageLocation "FR") に設定します**。

### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>特定のユーザー アカウント セットのプロパティを変更する

ユーザー アカウントの特定のセットのプロパティを変更するには **、Get-AzureADUser** コマンドレット **、Where** コマンドレット **、Set-AzureADUser** コマンドレットを組み合わせて使用できます。 次の使用例は、経理部門のすべてのユーザーの使用場所をフランスに変更 *します*。
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

このコマンドは、PowerShell に次の指示を行います。
  
1. ユーザー アカウント **(Get-AzureADUser)** のすべての情報を取得し、次のコマンド ( ) に送信します **|** 。

1.  Department プロパティが "Accounting"  **(Where {$_) に設定されているすべてのユーザー アカウントを検索します。Department -eq "Accounting"} )** をクリックし、結果の情報を次のコマンド ( ) に送信します **|** 。

1. ユーザーの場所をフランス **(Set-AzureADUser -UsageLocation "FR") に設定します**。

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する

Windows PowerShell 用の Microsoft Azure Active Directory モジュールを使用してユーザー アカウントのプロパティを構成するには **、Set-MsolUser** コマンドレットを使用して、設定または変更するプロパティを指定します。

最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。
  
> [!NOTE]
> PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に *Msol* が含まれるコマンドレットをサポートしていません。 これらのコマンドレットは、Windows PowerShell から実行します。

### <a name="change-properties-for-a-specific-user-account"></a>特定のユーザー アカウントのプロパティを変更する

特定のユーザー アカウントのプロパティを構成するには [**、Set-MsolUser**](/previous-versions/azure/dn194136(v=azure.100)) コマンドレットを使用し、設定または変更するプロパティを指定します。 

*-UserPrincipalName* パラメーターを使用してアカウントを識別し、追加のパラメーターを使用して特定のプロパティを設定または変更します。 最も一般的なパラメーターの一覧を次に示します。
  
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

- -UsageLocation \<2-character country or region code> "

    これは、ISO 3166-1 alpha-2 (A2) の 2 文字の国/地域コードです。

その他のパラメーターについては [、「Set-MsolUser」を参照してください](/previous-versions/azure/dn194136(v=azure.100))。

すべてのユーザーのユーザー プリンシパル名を表示するには、次のコマンドを実行します。
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

このコマンドは、PowerShell に次の指示を行います。
  
1. ユーザー アカウント **(Get-MsolUser)** のすべての情報を取得し、次のコマンド ( ) に送信します **|** 。

1. ユーザー プリンシパル名の一覧をアルファベット順に並べ替え (**Sort UserPrincipalName**) し、次のコマンド ( ) に送信します **|** 。

1. 各アカウントの [ユーザー プリンシパル名] プロパティ **([UserPrincipalName** の選択]) を表示します。

1. 一度に 1 画面ずつ表示する (**More**)。

表示名 (名と名) に基づいてアカウントのユーザー プリンシパル名を表示するには、次のコマンドを実行します。 変数 *に$userNameし* 、文字を削除 \< and > します。
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

次の使用例は、Caleb Sills という名前のユーザーのユーザー プリンシパル名を表示します。
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

*$upn* 変数を使用すると、表示名に基づいて個々のアカウントに変更を加えることができます。 Belinda *Newman* の使用場所をフランスに設定し、ユーザープリンシパル名ではなく表示名を指定する例を次に示します。
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>すべてのユーザー アカウントのプロパティを変更する

すべてのユーザーのプロパティを変更するには **、Get-MsolUser** コマンドレットと **Set-MsolUser** コマンドレットを組み合わせて使用します。 次の使用例は、すべてのユーザーの使用場所をフランスに変更 *します*。
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

このコマンドは、PowerShell に次の指示を行います。
  
1. ユーザー アカウント **(Get-MsolUser)** のすべての情報を取得し、次のコマンド ( ) に送信します **|** 。

1. ユーザーの場所をフランス **(Set-MsolUser -UsageLocation "FR") に設定します**。

### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>特定のユーザー アカウント セットのプロパティを変更する

特定の一連のユーザー アカウントのプロパティを変更するには **、Get-MsolUser** コマンドレット **、Where** コマンドレット **、Set-MsolUser** コマンドレットを組み合わせて使用できます。 次の使用例は、経理部門のすべてのユーザーの使用場所をフランスに変更 *します*。
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

このコマンドは、PowerShell に次の指示を行います。
  
1. ユーザー アカウント **(Get-MsolUser)** のすべての情報を取得し、次のコマンド ( ) に送信します **|** 。

1. Department プロパティが *"Accounting"* **(Where {$_) に設定されているすべてのユーザー アカウントを検索します。Department -eq "Accounting"}**) をクリックし、結果の情報を次のコマンド ( ) に送信します **|** 。

1. ユーザーの場所をフランス **(Set-MsolUser -UsageLocation "FR") に設定します**。

## <a name="see-also"></a>関連項目

[Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)
