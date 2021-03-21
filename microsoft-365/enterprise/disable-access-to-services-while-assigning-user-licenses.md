---
title: ユーザー ライセンスの割り当て中に Microsoft 365 サービスへのアクセスを無効にする
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/24/2020
audience: Admin
ms.topic: article
ms.collection: Ent_O365
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
ms.assetid: bb003bdb-3c22-4141-ae3b-f0656fc23b9c
description: PowerShell for Microsoft 365 を使用して、ユーザー アカウントにライセンスを割り当て、特定のサービス プランを同時に無効にする方法について説明します。
ms.openlocfilehash: 7486968f6f4822047a1697ee1e05129277fd11a8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929434"
---
# <a name="disable-access-to-microsoft-365-services-while-assigning-user-licenses"></a>ユーザー ライセンスの割り当て中に Microsoft 365 サービスへのアクセスを無効にする

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365 サブスクリプションには、個々のサービスのサービス プランが用意されています。 Microsoft 365 管理者は、多くの場合、ユーザーにライセンスを割り当てるときに特定のプランを無効にする必要があります。 この記事の手順では、Microsoft 365 ライセンスを割り当てながら、個々のユーザー アカウントまたは複数のユーザー アカウントに PowerShell を使用して特定のサービス プランを無効にできます。

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する

まず [、Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
  

次に、このコマンドを使用してテナントのライセンス プランを一覧表示します。

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

次に、ライセンスを追加するアカウントのサインイン名 (ユーザー プリンシパル名 (UPN) とも呼ばれる) を取得します。

次に、有効にするサービスの一覧をコンパイルします。 ライセンス プラン (製品名とも呼ばれる) の完全な一覧、付属のサービス プラン、対応する表示名については、「ライセンスの製品名とサービス プラン識別子」を [参照してください](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)。

以下のコマンド ブロックで、ユーザー アカウントのユーザー プリンシパル名、SKU パーツ番号、およびサービス プランの一覧を入力して、説明テキストと文字を有効にして削除 \< and > します。 次に、完成したコマンドを PowerShell コマンド プロンプトで実行します。
  
```powershell
$userUPN="<user account UPN>"
$skuPart="<SKU part number>"
$serviceList=<double-quoted enclosed, comma-separated list of enabled services>
$user = Get-AzureADUser -ObjectID $userUPN
$skuID= (Get-AzureADSubscribedSku  | Where {$_.SkuPartNumber -eq $skuPart}).SkuID
$SkuFeaturesToEnable = @($serviceList)
$StandardLicense = Get-AzureADSubscribedSku | Where {$_.SkuId -eq $skuID}
$SkuFeaturesToDisable = $StandardLicense.ServicePlans | ForEach-Object { $_ | Where {$_.ServicePlanName -notin $SkuFeaturesToEnable }}
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = $StandardLicense.SkuId
$License.DisabledPlans = $SkuFeaturesToDisable.ServicePlanId
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $user.ObjectId -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する

まず [、Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

次に、このコマンドを実行して現在のサブスクリプションを確認します。
  
```powershell
Get-MsolAccountSku
```

>[!Note]
>PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に **Msol** が含まれるコマンドレットをサポートしていません。 これらのコマンドレットを引き続き使用するには、Windows PowerShell から実行する必要があります。
>

`Get-MsolAccountSku` コマンドの出力に関して次に説明します。
  
- **AccountSkuId** は、次の形式で組織 \<OrganizationName> のサブスクリプション \<Subscription> です。 これは、Microsoft 365 に登録するときに指定した値であり、組織 \<OrganizationName> に固有の値です。 値 \<Subscription> は、特定のサブスクリプションの値です。 たとえば、litwareinc:ENTERPRISEPACK の場合、組織名は litwareinc、サブスクリプション名は ENTERPRISEPACK (Office 365 Enterprise E3) です。
    
- **ActiveUnits** は、サブスクリプションで購入したライセンス数です。
    
- **WarningUnits** は、まだ更新しておらず、30 日の猶予期間を過ぎると有効期限切れになる、サブスクリプション内のライセンス数です。
    
- **ConsumedUnits** は、このサブスクリプションでユーザーに割り当てたライセンスの数です。
    
ライセンスを取得するユーザーを含む Microsoft 365 サブスクリプションの AccountSkuId に注意してください。 また、割り当てるのに十分なライセンスが存在する **(ActiveUnits から ConsumedUnits** を減算する) **必要があります** 。
  
次に、このコマンドを実行して、すべてのサブスクリプションで利用可能な Microsoft 365 サービス プランの詳細を確認します。
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

このコマンドの出力に基づいて、ユーザーにライセンスを割り当てるときに無効にするサービス プランを判別します。
  
サービス プランとそれに対応する Microsoft 365 サービスの一部を次に示します。

次の表に、最も一般的なサービスの Microsoft 365 サービス プランとその親しみ名を示します。 実際のサービス プランの一覧とは、異なる場合があります。 
  
|**サービス プラン**|**説明**|
|:-----|:-----|
| `SWAY` <br/> |Sway  <br/> |
| `TEAMS1` <br/> |Microsoft Teams  <br/> |
| `YAMMER_ENTERPRISE` <br/> |Yammer  <br/> |
| `RMS_S_ENTERPRISE` <br/> |Azure Rights Management (RMS)  <br/> |
| `OFFICESUBSCRIPTION` <br/> |Microsoft 365 Apps for enterprise (以前は Office *365 ProPlus)*  <br/> |
| `MCOSTANDARD` <br/> |Skype for Business Online  <br/> |
| `SHAREPOINTWAC` <br/> |Office   <br/> |
| `SHAREPOINTENTERPRISE` <br/> |SharePoint Online  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |Exchange Online プラン 2  <br/> |
   
ライセンス プラン (製品名とも呼ばれる) の完全な一覧、付属のサービス プラン、対応する表示名については、「ライセンスの製品名とサービス プラン識別子」を [参照してください](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)。
   
この時点で、AccountSkuId と無効にするサービス プランが決まったため、1 ユーザーまたは複数ユーザーにライセンスを割り当てることができます。
  
### <a name="for-a-single-user"></a>単一ユーザーの場合

1 人のユーザーの場合は、ユーザー アカウントのユーザー プリンシパル名、AccountSkuId、およびサービス プランの一覧を入力して、説明テキストと文字を無効にして削除 \< and > します。 次に、完成したコマンドを PowerShell コマンド プロンプトで実行します。
  
```powershell
$userUPN="<the user's account name in email format>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the service plans to disable> )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

コマンド ブロックの例を以下に示します。アカウント名は belindan@contoso.com で、ライセンスは contoso:ENTERPRISEPACK であり、RMS_S_ENTERPRISE、SWAY、INTUNE_O365、YAMMER_ENTERPRISE の各サービス プランを無効にします。
  
```powershell
$userUPN="belindan@contoso.com"
$accountSkuId="contoso:ENTERPRISEPACK"
$planList=@( "RMS_S_ENTERPRISE","SWAY","INTUNE_O365","YAMMER_ENTERPRISE" )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

### <a name="for-multiple-users"></a>複数ユーザーの場合

この管理タスクを複数ユーザーに実行するには、UserPrincipalName フィールドと UsageLocation フィールドが含まれるコンマ区切り値 (CSV) テキスト ファイルを作成します。次に例を示します。
  
```powershell
UserPrincipalName,UsageLocation
ClaudeL@contoso.onmicrosoft.com,FR
LynneB@contoso.onmicrosoft.com,US
ShawnM@contoso.onmicrosoft.com,US
```

その後、入力および出力の各 CSV ファイルの場所、アカウント SKU ID、無効にするサービス プランの一覧を入力し、完成したコマンドを PowerShell コマンド プロンプトで実行します。
  
```powershell
$inFileName="<path and file name of the input CSV file that contains the users, example: C:\admin\Users2License.CSV>"
$outFileName="<path and file name of the output CSV file that records the results, example: C:\admin\Users2License-Done.CSV>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the plans to disable> )
$users=Import-Csv $inFileName
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
ForEach ($user in $users)
{
$user.Userprincipalname
$upn=$user.UserPrincipalName
Set-MsolUserLicense -UserPrincipalName $upn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $upn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
$users | Get-MsolUser | Select UserPrincipalName, Islicensed,Usagelocation | Export-Csv $outFileName
}
```

この PowerShell コマンド ブロックは以下の処理を行います。
  
- 各ユーザーのユーザー プリンシパル名を表示します。
    
- 各ユーザーにカスタマイズされたライセンスを割り当てます。
    
- 処理されたすべてのユーザーが含まれる CSV ファイルを作成し、そのライセンス状態を示します。
    
## <a name="see-also"></a>関連項目

[PowerShell を使用して Microsoft 365 サービスへのアクセスを無効にする](disable-access-to-services-with-microsoft-365-powershell.md)
  
[PowerShell を使用して Sway へのアクセスを無効にする](disable-access-to-sway-with-microsoft-365-powershell.md)
  
[Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)