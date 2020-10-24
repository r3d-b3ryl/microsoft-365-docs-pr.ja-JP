---
title: PowerShell を使用して Microsoft 365 ユーザーアカウントを作成する
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
- PowerShell
- Ent_Office_Other
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: PowerShell を使用して、個別または複数の Microsoft 365 ユーザーアカウントを作成する方法。
ms.openlocfilehash: d96de72ca3e7c4a439665c3ebf751a8fe25ce572
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754212"
---
# <a name="create-microsoft-365-user-accounts-with-powershell"></a>PowerShell を使用して Microsoft 365 ユーザーアカウントを作成する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365 の PowerShell を使用すると、複数のアカウントを含むユーザーアカウントを効率的に作成できます。

PowerShell でユーザーアカウントを作成する場合、特定のアカウントのプロパティが常に必要です。 その他のプロパティは必須ではありませんが、重要です。 次の表を参照してください。
  
|**プロパティ名**|**必須**|**説明**|
|:-----|:-----|:-----|
|**DisplayName** <br/> |はい  <br/> |これは、Microsoft 365 サービスで使用される表示名です。 たとえば、 *Caleb が ls*というようになります。 <br/> |
|**UserPrincipalName** <br/> |はい  <br/> |これは、Microsoft 365 サービスへのサインインに使用されるアカウント名です。 たとえば、 *Calebs \@ contoso.onmicrosoft.com*などです。  <br/> |
|**FirstName** <br/> |いいえ  <br/> ||
|**LastName** <br/> |いいえ  <br/> ||
|**LicenseAssignment** <br/> |いいえ  <br/> |これは、使用可能なライセンスがユーザーアカウントに割り当てられているライセンスプラン (ライセンスプランまたは SKU とも呼ばれます) です。 ライセンスでは、アカウントで利用できる Microsoft 365 サービスが定義されています。 アカウントを作成するときに、ユーザーにライセンスを割り当てる必要はありませんが、そのアカウントには Microsoft 365 サービスにアクセスするためのライセンスが必要です。 ユーザー アカウントにライセンスを割り当てる期間は作成後 30 日です。 |
|**Password** <br/> |いいえ  <br/> | パスワードを指定しない場合、ランダムなパスワードがユーザー アカウントに割り当てられ、パスワードはコマンドの結果に表示されます。 パスワードを指定する場合は、次の種類の 8 ~ 16 文字の ASCII テキスト文字である必要があります。小文字、大文字、数字、記号。<br/> |
|**UsageLocation** <br/> |いいえ  <br/> |これは有効な ISO 3166-1 alpha 国コードです。 たとえば、米国 *の場合* は、フランスの *FR* の場合はというようになります。 一部の Microsoft 365 サービスは特定の国では利用できないため、この値を提供することは重要です。 アカウントでこの値が構成されていない限り、ユーザーアカウントにライセンスを割り当てることはできません。 詳細については、「 [ライセンス制限につい](https://go.microsoft.com/fwlink/p/?LinkId=691730)て」を参照してください。<br/> |

>[!Note]
>Microsoft 365 管理センターを使用して[ユーザーアカウントを作成する方法について説明](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users)します。
> 
> その他のリソースの一覧については、「 [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/)」を参照してください。
>   

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する

最初に、 [Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)します。

接続した後、次の構文を使用して個別のアカウントを作成します。
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="<user account password>"
New-AzureADUser -DisplayName "<display name>" -GivenName "<first name>" -SurName "<last name>" -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -MailNickName <mailbox name> -PasswordProfile $PasswordProfile -AccountEnabled $true
```

この例では、US user *Caleb ls*のアカウントを作成します。
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="3Rv0y1q39/chsy"
New-AzureADUser -DisplayName "Caleb Sills" -GivenName "Caleb" -SurName "Sills" -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -MailNickName calebs -PasswordProfile $PasswordProfile -AccountEnabled $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する

最初に、 [Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)します。

### <a name="create-an-individual-user-account"></a>個別のユーザー アカウントの作成

個別のアカウントを作成するには、次の構文を使用します。
  
```powershell
New-MsolUser -DisplayName <display name> -FirstName <first name> -LastName <last name> -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -LicenseAssignment <licensing plan name> [-Password <Password>]
```

>[!Note]
>PowerShell Core は、Windows PowerShell モジュールの Microsoft Azure Active Directory モジュールと、名前に *Msol* が含まれるコマンドレットをサポートしていません。 これらのコマンドレットを Windows PowerShell から実行します。
>

使用可能なライセンスのプラン名を一覧表示するには、次のコマンドを使用します。

````powershell
Get-MsolAccountSku
````

この例では、US user *Caleb ls*のアカウントを作成し、 `contoso:ENTERPRISEPACK` (Office 365 Enterprise E3) ライセンスプランからライセンスを割り当てます。
  
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
   >CSV ファイルの最初の行にある列の名前と順序は任意です。 ただし、他のファイル内のデータの順序が列名の順序と一致していることを確認してください。 また、Microsoft 365 コマンドの PowerShell でパラメーター値の列名を使用します。
    
2. 次の構文を使用してください。
    
    ```powershell
     Import-Csv -Path <Input CSV File Path and Name> | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId [-Password $_.Password]} | Export-Csv -Path <Output CSV File Path and Name>
    ```

   この例では、ファイル *C:\My Documents\NewAccounts.csv* からユーザーアカウントを作成し、 *C:\My Documents\NewAccountResults.csv*という名前のファイルに結果を記録します。
    
    ```powershell
    Import-Csv -Path "C:\My Documents\NewAccounts.csv" | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId} | Export-Csv -Path "C:\My Documents\NewAccountResults.csv"
    ```

3. 出力ファイルで結果を確認します。 パスワードを指定していないため、Microsoft 365 によって生成されたランダムなパスワードが出力ファイルに表示されます。
    
## <a name="see-also"></a>関連項目

[Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)
