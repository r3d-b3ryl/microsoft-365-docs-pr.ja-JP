---
title: PowerShell を使用してMicrosoft 365サービスへのアクセスを無効にする
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/27/2020
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
- Ent_Office_Other
- PowerShell
- LIL_Placement
- seo-marvel-apr2020
ms.assetid: 264f4f0d-e2cd-44da-a9d9-23bef250a720
description: この記事では、PowerShell を使用してユーザーのサービスへのアクセスを無効にするMicrosoft 365説明します。
ms.openlocfilehash: bce02c40bf6ca99d74b8747fb0c5eb5c0b485888
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60173465"
---
# <a name="disable-access-to-microsoft-365-services-with-powershell"></a>PowerShell を使用してMicrosoft 365サービスへのアクセスを無効にする

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

ライセンス プランMicrosoft 365アカウントにライセンスが割り当てられている場合、Microsoft 365サービスは、そのライセンスからユーザーが利用できます。 ただし、ユーザーがアクセスMicrosoft 365サービスを制御できます。 たとえば、ライセンスでオンライン サービスへのアクセスを許可SharePoint、そのサービスへのアクセスを無効にできます。 PowerShell を使用すると、次の特定のライセンス プランの任意の数のサービスへのアクセスを無効にできます。

- 個々のアカウント。
- アカウントのグループ。
- 組織内のすべてのアカウント。

>[!Note]
>他のMicrosoft 365依存している場合に、指定したサービスを無効にできない可能性があるサービスの依存関係があります。
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する

最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

次に、次のコマンドを使用して、使用可能なライセンス プラン (AccountSkuIds とも呼ばれる) を表示します。

```powershell
Get-MsolAccountSku | Select AccountSkuId | Sort AccountSkuId
```

>[!Note]
>PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に **Msol** が含まれるコマンドレットをサポートしていません。 これらのコマンドレットを引き続き使用するには、Windows PowerShell から実行する必要があります。
>

詳細については [、「PowerShell でライセンスとサービスを表示する」を参照してください](view-licenses-and-services-with-microsoft-365-powershell.md)。
    
このトピックの手順の前と後の結果を確認するには、「PowerShell でアカウント ライセンスとサービスの詳細を [表示する」を参照してください](view-account-license-and-service-details-with-microsoft-365-powershell.md)。
    
このトピックで説明されている手順を自動化する PowerShell スクリプトが利用可能です。 具体的には、このスクリプトを使用すると、Sway を含む、Microsoft 365のサービスを表示および無効にできます。 詳細については [、「PowerShell を使用して Sway へのアクセスを無効にする」を参照してください](disable-access-to-sway-with-microsoft-365-powershell.md)。
    
    
### <a name="disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan"></a>特定のライセンスMicrosoft 365特定のユーザーの特定のサービスを無効にする
  
特定のライセンス プランに対してユーザー Microsoft 365サービスの特定のセットを無効にするには、次の手順を実行します。
  
#### <a name="step-1-identify-the-undesired-services-in-the-licensing-plan-by-using-the-following-syntax"></a>手順 1: 次の構文を使用して、ライセンス 計画で望ましくないサービスを特定します。
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId <AccountSkuId> -DisabledPlans "<UndesiredService1>", "<UndesiredService2>"...
```

次の使用例は、ライセンス プラン (Office E3) で Office および SharePoint Online サービスを無効にする **LicenseOptions** オブジェクトを `litwareinc:ENTERPRISEPACK` Office 365 Enterpriseします。
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId "litwareinc:ENTERPRISEPACK" -DisabledPlans "SHAREPOINTWAC", "SHAREPOINTENTERPRISE"
```

#### <a name="step-2-use-the-licenseoptions-object-from-step-1-on-one-or-more-users"></a>手順 2: 1 つ以上のユーザーに対して、手順 1 の **LicenseOptions** オブジェクトを使用します。
    
サービスが無効になっている新しいアカウントを作成するには、次の構文を使用します。
    
```powershell
New-MsolUser -UserPrincipalName <Account> -DisplayName <DisplayName> -FirstName <FirstName> -LastName <LastName> -LicenseAssignment <AccountSkuId> -LicenseOptions $LO -UsageLocation <CountryCode>
```

次の例では、手順 1 で説明されているライセンスを割り当て、サービスを無効にする Allie Bellew の新しいアカウントを作成します。
    
```powershell
New-MsolUser -UserPrincipalName allieb@litwareinc.com -DisplayName "Allie Bellew" -FirstName Allie -LastName Bellew -LicenseAssignment litwareinc:ENTERPRISEPACK -LicenseOptions $LO -UsageLocation US
```

PowerShell for Microsoft 365でユーザー アカウントを作成する方法の詳細については[、「Create user accounts with PowerShell」を参照してください](create-user-accounts-with-microsoft-365-powershell.md)。
    
ライセンスを付与された既存のユーザー用のサービスを無効にするには、次の構文を使用します。
    
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -LicenseOptions $LO
```

この例では、ユーザー BelindaN@litwareinc.com に対してサービスを無効にします。
    
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -LicenseOptions $LO
```

手順 1 で説明されているサービスを既存のすべてのライセンス ユーザーに対して無効にするには **、Get-MsolAccountSku** コマンドレット **(litwareinc:ENTERPRISEPACK** など) の表示から Microsoft 365 プランの名前を指定し、次のコマンドを実行します。
    
```powershell
$acctSKU="<AccountSkuId>"
$AllLicensed = Get-MsolUser -All | Where {$_.isLicensed -eq $true -and $_.licenses.AccountSku.SkuPartNumber -contains ($acctSKU).Substring($acctSKU.IndexOf(":")+1, $acctSKU.Length-$acctSKU.IndexOf(":")-1)}
$AllLicensed | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

 All パラメーターを使用 **せずに Get-MsolUser** コマンドレットを使用すると、最初の 500 ユーザー アカウントだけが返されます。

既存のユーザーのグループに対してサービスを無効にするには、次のいずれかの方法を使用して、ユーザーを特定します。
    
**方法 1.既存のアカウント属性に基づいてアカウントをフィルター処理する** 

この設定を行うには、次の構文を使用します。
    
```powershell
$x = Get-MsolUser -All <FilterableAttributes>
$x | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

次の使用例は、米国の Sales 部門のユーザーのサービスを無効にします。
    
```powershell
$USSales = Get-MsolUser -All -Department "Sales" -UsageLocation "US"
$USSales | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

**方法 2: 特定のアカウントの一覧を使用する** 

これを行うには、次の手順を実行します。
    
1. 次のように各行に 1 つのアカウントが含まれるテキスト ファイルを作成します。
    
   ```powershell
   akol@contoso.com
   tjohnston@contoso.com
   kakers@contoso.com
   ```

   この例では、テキスト ファイルは C: \\ My Documents \\Accounts.txt。
    
2. 次のコマンドを実行します。
    
   ```powershell
   Get-Content "C:\My Documents\Accounts.txt" | foreach {Set-MsolUserLicense -UserPrincipalName $_ -LicenseOptions $LO}
   ```

複数のライセンス プランのサービスへのアクセスを無効にする場合は、ライセンス プランごとに上記の手順を繰り返し、次のことを確認します。

- ユーザー アカウントにはライセンス プランが割り当て済みです。
- 無効にするサービスは、ライセンス プランで利用できます。

ライセンス プランに割りMicrosoft 365しているユーザーのサービスを無効にするには、「ユーザー ライセンスの割り当て中にサービスへのアクセスを無効にする」[を参照してください](disable-access-to-services-while-assigning-user-licenses.md)。

### <a name="assign-all-services-in-a-licensing-plan-to-a-user-account"></a>ライセンス プラン内のすべてのサービスをユーザー アカウントに割り当てる

サービスが無効になっているユーザー アカウントの場合は、次のコマンドを使用して、特定のライセンス プランのすべてのサービスを有効にすることができます。

```powershell
$userUPN="<user account UPN>"
$acctSKU="<AccountSkuId>"
$LO = New-MsolLicenseOptions -AccountSkuId $acctSKU
Set-MsolUserLicense -UserPrincipalName $userUPN -LicenseOptions $LO
```

## <a name="related-topic"></a>関連トピック

[Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)
