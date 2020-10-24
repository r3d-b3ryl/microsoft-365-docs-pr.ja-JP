---
title: PowerShell を使用して Microsoft 365 ユーザーアカウントのプロパティを構成する
ms.author: josephd
author: JoeDavies-MSFT
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
description: Microsoft 365 の PowerShell を使用して、Microsoft 365 テナント内の個別のまたは複数のユーザーアカウントのプロパティを構成します。
ms.openlocfilehash: 830cede93a6c14db2dcc5626d41d0dd296b9ac29
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754330"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a>PowerShell を使用して Microsoft 365 ユーザーアカウントのプロパティを構成する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365 管理センターを使用して、Microsoft 365 テナントのユーザーアカウントのプロパティを構成できます。 PowerShell では、これに加えて、管理センターでは実行できないその他のいくつかの操作も実行できます。
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する

Graph モジュールの Azure Active Directory PowerShell でユーザーアカウントのプロパティを構成するには、 [**set-azureaduser**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) コマンドレットを使用して、設定または変更するプロパティを指定します。

最初に、 [Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)します。
   
### <a name="change-properties-for-a-specific-user-account"></a>特定のユーザー アカウントのプロパティを変更する

*-ObjectID*パラメーターを使用してアカウントを識別し、追加のパラメーターを使用して特定のプロパティを設定または変更します。 最も一般的なパラメーターの一覧を次に示します。
  
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
    
- -" \<2-character country or region code> "
    
    これは、ISO 3166-1 alpha-2 (A2) の 2 文字の国/地域コードです。
    
その他のパラメーターについては、「 [set-azureaduser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) 」を参照してください。

>[!Note]
>ユーザーアカウントにライセンスを割り当てるには、その前に、利用状況の場所を割り当てる必要があります。
>

ユーザー アカウントのユーザー プリンシパル名を表示するには、次のコマンドを実行します。
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

次のコマンドは、PowerShell に次のように指示します。
  
1. ユーザーアカウントのすべての情報を取得し (**set-azureaduser**)、次のコマンドに送信します ( **|** )。
    
1. ユーザープリンシパル名のリストをアルファベット順に並べ替え (**UserPrincipalName を並べ替え**)、次のコマンドに送信し **|** ます ()。
    
1. 各アカウントのユーザープリンシパル名プロパティのみを表示します (**UserPrincipalName を選択**します)。

1. 一度に 1 画面ずつ表示する (**More**)。
    
表示名 (姓と名) に基づいてアカウントのユーザープリンシパル名を表示するには、次のコマンドを実行します。 *$UserName*変数を入力し、次の文字を削除し \< and > ます。
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

この例では、表示名が " *Caleb/ls*" であるユーザーアカウントのユーザープリンシパル名を表示します。
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

*$upn* 変数を使用すると、表示名に基づいて個々のアカウントに変更を加えることができます。 次の例では *、ベルギー*の使用場所をフランスに設定します。 しかし、ユーザープリンシパル名ではなく、自分の表示名を指定しています。
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>すべてのユーザー アカウントのプロパティを変更する

すべてのユーザーのプロパティを変更するには、 **set-azureaduser** コマンドレットと **set-azureaduser** コマンドレットの組み合わせを使用できます。 次の例では、すべてのユーザーの使用場所を *フランス*に変更します。
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

次のコマンドは、PowerShell に次のように指示します。
  
1. ユーザーアカウントのすべての情報を取得し (**set-azureaduser**)、次のコマンドに送信し **|** ます ()。
    
1. ユーザーの所在地をフランスに設定します (**set-azureaduser-@ location "FR"**)。
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>特定のユーザー アカウント セットのプロパティを変更する

特定のユーザーアカウントセットのプロパティを変更するには、 **set-azureaduser**、 **Where**、および **set-azureaduser** コマンドレットの組み合わせを使用できます。 次の例では、経理部門のすべてのユーザーの使用場所を *フランス*に変更します。
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

次のコマンドは、PowerShell に次のように指示します。
  
1. ユーザーアカウントのすべての情報を取得し (**set-azureaduser**)、次のコマンドに送信し **|** ます ()。
    
1.  *Department*プロパティが "Accounting" に設定されているすべてのユーザーアカウント (**Where {$ _) を検索します。Department-eq "Accounting"}**) を行い、結果の情報を次のコマンドに送信し **|** ます ()。
    
1. ユーザーの所在地をフランスに設定します (**set-azureaduser-@ location "FR"**)。
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する

Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用して、ユーザーアカウントのプロパティを構成するには、 **get-msoluser** コマンドレットを使用して、設定または変更するプロパティを指定します。

最初に、 [Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)します。
  
>[!Note]
>PowerShell Core は、Windows PowerShell モジュール用 Microsoft Azure Active Directory モジュールと、名前に *Msol* を指定したコマンドレットをサポートしていません。 これらのコマンドレットを Windows PowerShell から実行します。
>

### <a name="change-properties-for-a-specific-user-account"></a>特定のユーザー アカウントのプロパティを変更する

特定のユーザーアカウントのプロパティを構成するには、 [**get-msoluser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) コマンドレットを使用して、設定または変更するプロパティを指定します。 

*-UserPrincipalName*パラメーターを使用してアカウントを識別し、追加のパラメーターを使用して特定のプロパティを設定または変更します。 最も一般的なパラメーターの一覧を次に示します。
  
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
    
- -" \<2-character country or region code> "
    
    これは、ISO 3166-1 alpha-2 (A2) の 2 文字の国/地域コードです。
    
その他のパラメーターについては、「 [get-msoluser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100))」を参照してください。

すべてのユーザーのユーザープリンシパル名を表示するには、次のコマンドを実行します。
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

次のコマンドは、PowerShell に次のように指示します。
  
1. ユーザーアカウントのすべての情報を取得し (**get-msoluser**)、次のコマンドに送信します ( **|** )。
    
1. ユーザープリンシパル名のリストをアルファベット順に並べ替え (**UserPrincipalName を並べ替え**)、次のコマンドに送信し **|** ます ()。
    
1. 各アカウントのユーザープリンシパル名プロパティのみを表示します (**UserPrincipalName を選択**します)。
    
1. 一度に 1 画面ずつ表示する (**More**)。
    
表示名 (姓と名) に基づいてアカウントのユーザープリンシパル名を表示するには、次のコマンドを実行します。 *$UserName*変数に入力し、文字を削除し \< and > ます。
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

この例では、Caleb/Ls という名前のユーザーのユーザープリンシパル名を表示します。
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

*$upn* 変数を使用すると、表示名に基づいて個々のアカウントに変更を加えることができます。 次の例では、 *ベルギー*の使用場所を *フランス*に設定していますが、ユーザープリンシパル名ではなく、表示名を指定しています。
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>すべてのユーザー アカウントのプロパティを変更する

すべてのユーザーのプロパティを変更するには、 **get-msoluser** コマンドレットと **get-msoluser** コマンドレットの組み合わせを使用します。 次の例では、すべてのユーザーの使用場所を *フランス*に変更します。
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

次のコマンドは、PowerShell に次のように指示します。
  
1. ユーザーアカウントのすべての情報を取得し (**get-msoluser**)、次のコマンドに送信します ( **|** )。
    
1. ユーザーの所在地をフランスに設定します (**get-msoluser-@ location "FR"**)。
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>特定のユーザー アカウント セットのプロパティを変更する

特定のユーザーアカウントセットのプロパティを変更するには、 **get-msoluser**、 **Where**、および **get-msoluser** コマンドレットの組み合わせを使用できます。 次の例では、経理部門のすべてのユーザーの使用場所を *フランス*に変更します。
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

次のコマンドは、PowerShell に次のように指示します。
  
1. ユーザーアカウントのすべての情報を取得し (**get-msoluser**)、次のコマンドに送信します ( **|** )。
    
1. *Department*プロパティが "Accounting" に設定されているすべてのユーザーアカウントを検索**します (Where {$ _)。Department-eq "Accounting"}**) を行い、結果の情報を次のコマンドに送信し **|** ます ()。
    
1. ユーザーの所在地をフランスに設定します (**get-msoluser-@ location "FR"**)。

## <a name="see-also"></a>関連項目

[Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)
