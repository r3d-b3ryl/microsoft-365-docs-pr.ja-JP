---
title: PowerShell を使用してMicrosoft 365ユーザー アカウントを作成する
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
- PowerShell
- Ent_Office_Other
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: PowerShell を使用して個々のユーザー アカウントまたは複数のMicrosoft 365 ユーザー アカウントを作成する方法。
ms.openlocfilehash: 2b0ef749dc0a0d38d84d1086dee50ce416d93e9b
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65101053"
---
# <a name="create-microsoft-365-user-accounts-with-powershell"></a>PowerShell を使用してMicrosoft 365ユーザー アカウントを作成する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

PowerShell を使用して、複数のアカウントを含むユーザー アカウントを効率的に作成Microsoft 365。

PowerShell でユーザー アカウントを作成する場合、特定のアカウント プロパティが常に必要です。 その他のプロパティは必須ではありませんが、重要です。 次の表を参照してください。
  
|**プロパティ名**|**必須**|**説明**|
|:-----|:-----|:-----|
|**DisplayName** <br/> |はい  <br/> |これは、Microsoft 365 サービスで使用される表示名です。 たとえば、 *Caleb Sills* です。 <br/> |
|**UserPrincipalName** <br/> |はい  <br/> |これは、Microsoft 365 サービスへのサインインに使用されるアカウント名です。 たとえば、 *CalebS\@ contoso.onmicrosoft.com*。  <br/> |
|**FirstName** <br/> |いいえ  <br/> ||
|**LastName** <br/> |いいえ  <br/> ||
|**LicenseAssignment** <br/> |いいえ  <br/> |これは、使用可能なライセンスがユーザー アカウントに割り当てられるライセンス プラン (ライセンス プランまたは SKU とも呼ばれます) です。 ライセンスは、アカウントで使用できるMicrosoft 365 サービスを定義します。 アカウントを作成するときにユーザーにライセンスを割り当てる必要はありませんが、そのアカウントには、Microsoft 365 サービスにアクセスするためのライセンスが必要です。 ユーザー アカウントにライセンスを割り当てる期間は作成後 30 日です。 |
|**Password** <br/> |いいえ  <br/> | パスワードを指定しない場合、ランダムなパスワードがユーザー アカウントに割り当てられ、パスワードはコマンドの結果に表示されます。 パスワードを指定する場合は、小文字、大文字、数字、記号の 8 から 16 の ASCII テキスト文字が必要です。<br/> |
|**UsageLocation** <br/> |いいえ  <br/> |これは有効な ISO 3166-1 alpha-2 国コードです。 たとえば、*米国の場合は米国*、フランスの場合 *は FR* です。 一部のMicrosoft 365 サービスは特定の国では利用できないため、この値を指定することが重要です。 アカウントにこの値が構成されていない限り、ユーザー アカウントにライセンスを割り当てることはできません。 詳細については、「 [ライセンス制限について](https://go.microsoft.com/fwlink/p/?LinkId=691730)」を参照してください。<br/> |

>[!Note]
>Microsoft 365 管理センターを使用して[ユーザー アカウントを作成する方法について説明](../admin/add-users/add-users.md)します。
> 
> その他のリソースの一覧については、「 [ユーザーとグループの管理](/admin)」を参照してください。
>   

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する

まず、[Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。

接続後、次の構文を使用して個々のアカウントを作成します。
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="<user account password>"
New-AzureADUser -DisplayName "<display name>" -GivenName "<first name>" -SurName "<last name>" -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -MailNickName <mailbox name> -PasswordProfile $PasswordProfile -AccountEnabled $true
```

この例では、米国ユーザー *Caleb Sills* のアカウントを作成します。
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="3Rv0y1q39/chsy"
New-AzureADUser -DisplayName "Caleb Sills" -GivenName "Caleb" -SurName "Sills" -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -MailNickName calebs -PasswordProfile $PasswordProfile -AccountEnabled $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する

まず、[Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

### <a name="create-an-individual-user-account"></a>個別のユーザー アカウントの作成

個別のアカウントを作成するには、次の構文を使用します。
  
```powershell
New-MsolUser -DisplayName <display name> -FirstName <first name> -LastName <last name> -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -LicenseAssignment <licensing plan name> [-Password <Password>]
```

>[!Note]
>PowerShell Core では、名前に *Msol* が含まれるWindows PowerShell モジュールとコマンドレットのMicrosoft Azure Active Directory モジュールはサポートされていません。 これらのコマンドレットは、Windows PowerShell から実行します。
>

使用可能なライセンスのプラン名を一覧表示するには、次のコマンドを使用します。

````powershell
Get-MsolAccountSku
````

この例では、米国ユーザー *Caleb Sills* のアカウントを作成し、(Office 365 Enterprise E3) ライセンス プランから`contoso:ENTERPRISEPACK`ライセンスを割り当てます。
  
```powershell
New-MsolUser -DisplayName "Caleb Sills" -FirstName Caleb -LastName Sills -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -LicenseAssignment contoso:ENTERPRISEPACK
```

### <a name="create-multiple-user-accounts"></a>複数のユーザー アカウントを作成する

1. 必要なユーザー アカウント情報を含むコンマ区切り (CSV) ファイルを作成します。例:

     ```powershell
     UserPrincipalName,FirstName,LastName,DisplayName,UsageLocation,AccountSkuId
     ClaudeL@contoso.onmicrosoft.com,Claude,Loiselle,Claude Loiselle,US,contoso:ENTERPRISEPACK
     LynneB@contoso.onmicrosoft.com,Lynne,Baxter,Lynne Baxter,US,contoso:ENTERPRISEPACK
     ShawnM@contoso.onmicrosoft.com,Shawn,Melendez,Shawn Melendez,US,contoso:ENTERPRISEPACK
     ```

   >[!NOTE]
   >CSV ファイルの最初の行の列名とその順序は任意です。 ただし、ファイルの残りの部分のデータの順序が列名の順序と一致することを確認してください。 PowerShell for Microsoft 365 コマンドのパラメーター値の列名を使用します。
    
2. 次の構文を使用してください。
    
    ```powershell
     Import-Csv -Path <Input CSV File Path and Name> | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId [-Password $_.Password]} | Export-Csv -Path <Output CSV File Path and Name>
    ```

   この例では、 *ファイル C:\My Documents\NewAccounts.csv* からユーザー アカウントを作成し、結果を *C:\My Documents\NewAccountResults.csv* という名前のファイルに記録します。
    
    ```powershell
    Import-Csv -Path "C:\My Documents\NewAccounts.csv" | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId} | Export-Csv -Path "C:\My Documents\NewAccountResults.csv"
    ```

3. 出力ファイルで結果を確認します。 パスワードを指定していないため、生成されたランダムなパスワードMicrosoft 365出力ファイルに表示されます。
    
## <a name="see-also"></a>関連項目

[Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)