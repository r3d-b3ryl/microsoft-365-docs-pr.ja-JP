---
title: PowerShell を使用してユーザー アカウントからMicrosoft 365ライセンスを削除する
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/23/2020
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
- LIL_Placement
- O365ITProTrain
ms.assetid: e7e4dc5e-e299-482c-9414-c265e145134f
description: PowerShell を使用して、以前にユーザーに割り当てられたMicrosoft 365 ライセンスを削除する方法について説明します。
ms.openlocfilehash: c3317c651c561da4c8650e45ba3b64a135a1f6ce
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2022
ms.locfileid: "64823148"
---
# <a name="remove-microsoft-365-licenses-from-user-accounts-with-powershell"></a>PowerShell を使用してユーザー アカウントからMicrosoft 365ライセンスを削除する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

>[!Note]
>Microsoft 365 管理センター[を使用してユーザー アカウントからライセンスを削除する方法について説明](../admin/manage/remove-licenses-from-users.md)します。 その他のリソースの一覧については、「 [ユーザーとグループの管理](/admin)」を参照してください。
>

## <a name="use-the-microsoft-graph-powershell-sdk"></a>Microsoft Graph PowerShell SDK を使用する

まず、[Microsoft 365 テナントに接続します](/graph/powershell/get-started#authentication)。

ユーザーのライセンスの割り当てと削除には、User.ReadWrite.All アクセス許可スコープまたは[「ライセンスの割り当て」Graph API参照ページ](/graph/api/user-assignlicense)に一覧表示されている他のアクセス許可のいずれかが必要です。

テナントで使用可能なライセンスを読み取るには、Organization.Read.All アクセス許可スコープが必要です。

```powershell
Connect-Graph -Scopes User.ReadWrite.All, Organization.Read.All
```

組織内のライセンス プラン情報を表示するには、次のトピックを参照してください。

- [PowerShell を使用してライセンスとサービスを表示する](view-licenses-and-services-with-microsoft-365-powershell.md)

- [PowerShell を使用してアカウント のライセンスとサービスの詳細を表示する](view-account-license-and-service-details-with-microsoft-365-powershell.md)

### <a name="removing-licenses-from-user-accounts"></a>ユーザー アカウントからのライセンスの削除

既存のユーザー アカウントからライセンスを削除するには、次の構文を使用します:
  
```powershell
Set-MgUserLicense -UserId "<Account>" -RemoveLicenses @("<AccountSkuId1>") -AddLicenses @{}
```

この例では、**ユーザー BelindaN@litwareinc.com からSPE_E5** (Microsoft 365 E5) ライセンス プランを **削除します。**

```powershell
$e5Sku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'SPE_E5'
Set-MgUserLicense -UserId "belindan@litwareinc.com" -RemoveLicenses @($e5Sku.SkuId) -AddLicenses @{}
```

既存のライセンスユーザーのグループからすべてのライセンスを削除するには、次の構文を使用します。

```powershell
$licensedUsers = Get-MgUser -Filter 'assignedLicenses/$count ne 0' `
    -ConsistencyLevel eventual -CountVariable licensedUserCount -All `
    -Select UserPrincipalName,DisplayName,AssignedLicenses

foreach($user in $licensedUsers)
{
    $licencesToRemove = $user.AssignedLicenses | Select -ExpandProperty SkuId
    $user = Set-MgUserLicense -UserId $user.UserPrincipalName -RemoveLicenses $licencesToRemove -AddLicenses @{} 
}
```

別の方法として、ユーザー アカウントを削除してライセンスを解放することもできます。 詳細については、「 [PowerShell を使用したユーザー アカウントの削除と復元](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)」を参照してください。

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する

>Set-AzureADUserLicense コマンドレットは廃止される予定です。 上記のように、スクリプトを Microsoft Graph SDK のSet-MgUserLicense コマンドレットに移行してください。 詳細については、「[Microsoft Graphからライセンス管理 API にアクセスするようにアプリを移行する」を参照](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/migrate-your-apps-to-access-the-license-managements-apis-from/ba-p/2464366)してください。
>

まず、[Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。

次に、このコマンドを使用して、テナントのライセンス プランを一覧表示します。

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

次に、ライセンスを削除するアカウントのサインイン名 (ユーザー プリンシパル名 (UPN) とも呼ばれます) を取得します。

最後に、ユーザー サインイン名とライセンス プラン名を指定し、"<" 文字と ">" 文字を削除して、次のコマンドを実行します。

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$License.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $license
```

特定のユーザー アカウントのすべてのライセンスを削除するには、ユーザー サインイン名を指定し、"<" 文字と ">" 文字を削除して、次のコマンドを実行します。

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

>[!Note]
>Set-MsolUserLicenseおよびNew-MsolUser (-LicenseAssignment) コマンドレットは廃止される予定です。 上記のように、スクリプトを Microsoft Graph SDK のSet-MgUserLicense コマンドレットに移行してください。 詳細については、「[Microsoft Graphからライセンス管理 API にアクセスするようにアプリを移行する」を参照](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/migrate-your-apps-to-access-the-license-managements-apis-from/ba-p/2464366)してください。
>

まず、[Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。
   
組織のライセンス プラン (**AccountSkuID**) 情報を表示する方法については、以下のトピックをご覧ください。
    
  - [PowerShell を使用してライセンスとサービスを表示する](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [PowerShell を使用してアカウント のライセンスとサービスの詳細を表示する](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
_-All_ パラメーターなしで **Get-MsolUser** コマンドレットを使用する場合、最初の 500 個のアカウントだけが返されます。
    
### <a name="removing-licenses-from-user-accounts"></a>ユーザー アカウントからのライセンスの削除

既存のユーザー アカウントからライセンスを削除するには、次の構文を使用します:
  
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -RemoveLicenses "<AccountSkuId1>", "<AccountSkuId2>"...
```

>[!Note]
>PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に **Msol** が含まれるコマンドレットをサポートしていません。 これらのコマンドレットを引き続き使用するには、Windows PowerShell から実行する必要があります。
>

この例では、ユーザー アカウント BelindaN@litwareinc.com から **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) ライセンスを削除します。
  
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"
```

>[!Note]
>このコマンドレットを `Set-MsolUserLicense` 使用して、 *キャンセルされた* ライセンスからユーザーの割り当てを解除することはできません。 これは、Microsoft 365 管理センターのユーザー アカウントごとに個別に行う必要があります。
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

次の使用例は、米国の営業部門のすべてのユーザー アカウントからすべてのライセンスを削除します。
    
```powershell
$userArray = Get-MsolUser -All -Department "Sales" -UsageLocation "US" | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

- **特定のライセンスの特定のアカウントの一覧を使用する** これを行うには、次の手順に従います。
    
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
次の使用例は、テキスト ファイル C:\My Documents\Accounts.txtで定義されているユーザー アカウントから **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) ライセンスを削除します。
    
  ```powershell
  $x=Get-Content "C:\My Documents\Accounts.txt"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "litwareinc:ENTERPRISEPACK"
  }
  ```

既存のすべてのユーザー アカウントからすべてのライセンスを削除するには、次の構文を使用します。
  
```powershell
$userArray = Get-MsolUser -All | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

別の方法として、ユーザー アカウントを削除してライセンスを解放することもできます。 詳細については、「 [PowerShell を使用したユーザー アカウントの削除と復元](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)」を参照してください。
  
## <a name="see-also"></a>関連項目

[Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)
