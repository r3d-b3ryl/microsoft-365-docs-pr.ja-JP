---
title: PowerShell Microsoft 365アカウントからユーザー ライセンスを削除する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
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
- LIL_Placement
- O365ITProTrain
ms.assetid: e7e4dc5e-e299-482c-9414-c265e145134f
description: PowerShell を使用して、以前にユーザーに割り当Microsoft 365ライセンスを削除する方法について説明します。
ms.openlocfilehash: 42ed344a0cff959b2e99027b847cd6ab30fb5e62bc8d86b3b5901b7539a44965
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53904673"
---
# <a name="remove-microsoft-365-licenses-from-user-accounts-with-powershell"></a>PowerShell Microsoft 365アカウントからユーザー ライセンスを削除する

*この記事は、Microsoft 365 Enterprise と Office 365 Enterprise の両方に適用されます。*

>[!Note]
>[ユーザー アカウントからライセンスを削除する方法については](../admin/manage/remove-licenses-from-users.md)、Microsoft 365 管理センター。 その他のリソースの一覧については、「ユーザーと [グループの管理」を参照してください](../admin/add-users/index.yml)。
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する

最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。

次に、このコマンドを使用してテナントのライセンス プランを一覧表示します。

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

次に、ライセンスを削除するアカウントのサインイン名 (ユーザー プリンシパル名 (UPN) とも呼ばれる) を取得します。

最後に、ユーザー サインインとライセンス プラン名を指定し、"<" 文字と ">" 文字を削除し、これらのコマンドを実行します。

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$License.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $license
```

特定のユーザー アカウントのすべてのライセンスを削除するには、ユーザー サインイン名を指定し、"<" および ">" 文字を削除して、これらのコマンドを実行します。

```powershell
$userUPN="<user sign-in name (UPN)>"
$userList = Get-AzureADUser -ObjectID $userUPN
$Skus = $userList | Select -ExpandProperty AssignedLicenses | Select SkuID
if($userList.Count -ne 0) {
    if($Skus -is [array])
    {
        $licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
        for ($i=0; $i -lt $Skus.Count; $i++) {
            $Licenses.RemoveLicenses +=  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $Skus[$i].SkuId -EQ).SkuID   
        }
        Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
    } else {
        $licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
        $Licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $Skus.SkuId -EQ).SkuID
        Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
    }
}
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する

最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。
   
組織のライセンス プラン (**AccountSkuID**) 情報を表示する方法については、以下のトピックをご覧ください。
    
  - [PowerShell でライセンスとサービスを表示する](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [PowerShell でアカウント ライセンスとサービスの詳細を表示する](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
_-All_ パラメーターなしで **Get-MsolUser** コマンドレットを使用する場合、最初の 500 個のアカウントだけが返されます。
    
### <a name="removing-licenses-from-user-accounts"></a>ユーザー アカウントからのライセンスの削除

既存のユーザー アカウントからライセンスを削除するには、次の構文を使用します:
  
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -RemoveLicenses "<AccountSkuId1>", "<AccountSkuId2>"...
```

>[!Note]
>PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に **Msol** が含まれるコマンドレットをサポートしていません。 これらのコマンドレットを引き続き使用するには、Windows PowerShell から実行する必要があります。
>

次の使用例は **、litwareinc:ENTERPRISEPACK** (E3 Office 365 Enterprise) ライセンスをユーザー アカウント から削除 BelindaN@litwareinc.com。
  
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"
```

>[!Note]
>コマンドレットを使用して `Set-MsolUserLicense` 、キャンセルされたライセンスからユーザーの割り当 *てを解除* することはできません。 この操作は、ユーザー アカウント内のユーザー アカウントごとに個別に行Microsoft 365 管理センター。
>

既存のライセンスユーザーのグループからすべてのライセンスを削除するには、次のいずれかの方法を使用します。
  
- **既存のアカウント属性に基づいてアカウントをフィルターする** これを行うには、次の構文を使用します。
    
```powershell
$userArray = Get-MsolUser -All <FilterableAttributes> | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

この例では、米国の Sales 部門のすべてのユーザー アカウントからすべてのライセンスを削除します。
    
```powershell
$userArray = Get-MsolUser -All -Department "Sales" -UsageLocation "US" | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

- **特定のライセンスに特定のアカウントの一覧を使用する** これを行うには、次の手順を実行します。
    
1. 次のように各行に 1 つのアカウントが含まれるテキスト ファイルを作成し、保存します。
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

2. 次の構文を使用してください。
    
  ```powershell
  $x=Get-Content "<FileNameAndPath>"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "<AccountSkuId1>","<AccountSkuId2>"...
  }
  ```
この例では、テキスト ファイル C:\My Office 365 Enterprise で定義されているユーザー アカウントから **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) ライセンスを削除Documents\Accounts.txt。
    
  ```powershell
  $x=Get-Content "C:\My Documents\Accounts.txt"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "litwareinc:ENTERPRISEPACK"
  }
  ```

すべての既存のユーザー アカウントからすべてのライセンスを削除するには、次の構文を使用します。
  
```powershell
$userArray = Get-MsolUser -All | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

別の方法として、ユーザー アカウントを削除してライセンスを解放することもできます。 詳細については [、「PowerShell を使用してユーザー アカウントを削除して復元する」を参照してください](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)。
  
## <a name="see-also"></a>関連項目

[Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)