---
title: 集中展開 PowerShell コマンドレットを使用してアドインを管理する
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/24/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
f1.keywords:
- NOCSH
ms.assetid: 94f4e86d-b8e5-42dd-b558-e6092f830ec9
ms.custom:
- seo-marvel-apr2020
description: 一元展開 PowerShell コマンドレットを使用して、組織のOfficeアドインを展開およびMicrosoft 365します。
ms.openlocfilehash: 37a60ffe7d17f09ecbdb70c80c880b2c7bd51645
ms.sourcegitcommit: 6a73f0f0c0360fc015d9c0d0af26fb6926d9477d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58745843"
---
# <a name="use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins"></a>集中展開 PowerShell コマンドレットを使用してアドインを管理する

グローバル管理者Microsoft 365、集中展開機能を使用して Office アドインをユーザーに展開できます (「管理センターに Office アドインを展開する」を[参照](../admin/manage/manage-deployment-of-add-ins.md)してください)。 Microsoft PowerShell を使用Officeアドインを展開するMicrosoft 365 管理センター、Microsoft PowerShell を使用できます。 [O365 一元化Add-In展開モジュールをインストールWindows PowerShell。](https://www.powershellgallery.com/packages/O365CentralizedAddInDeployment) 

モジュールをダウンロードした後、通常のウィンドウを開Windows PowerShell次のコマンドレットを実行します。

```powershell
 Import-Module -Name O365CentralizedAddInDeployment
```
    
## <a name="connect-using-your-admin-credentials"></a>Connect資格情報を使用する方法

集中展開コマンドレットを使用する前に、サインインする必要があります。
  
1. PowerShell を起動します。
    
2. Connect管理者の資格情報を使用して PowerShell にアクセスします。 次のコマンドレットを実行します。
    
  ```powershell
  Connect-OrganizationAddInService
  ```

3. [資格情報 **の入力] ページ** で、ユーザー管理者Microsoft 365 **グローバル管理者** の資格情報 **を** 入力します。 または、資格情報をコマンドレットに直接入力することもできます。 
    
    会社の管理者資格情報を PSCredential オブジェクトとして指定する次のコマンドレットを実行します。
    
  ```powershell
  $secpasswd = ConvertTo-SecureString "MyPassword" -AsPlainText -Force
  $mycredentials = New-Object System.Management.Automation.PSCredential ("serviceaccount@contoso.com", $secpasswd)
  Connect-OrganizationAddInService -Credential $mycredentials
  ```

> [!NOTE]
> PowerShell の使用の詳細については、「PowerShell Connect[をMicrosoft 365する」を参照してください](./connect-to-microsoft-365-powershell.md)。 
  
## <a name="upload-an-add-in-manifest"></a>アップロード マニフェストを作成する

**New-OrganizationAdd-In** コマンドレットを実行して、ファイルの場所または URL のいずれかであるパスからアドイン マニフェストをアップロードします。 次の例は  _、ManifestPath_ パラメーターの値のファイルの場所を示しています。 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

次の例に示すように **、New-OrganizationAdd-In** コマンドレットを実行してアドインをアップロードし  _、Members_ パラメーターを使用してユーザーまたはグループに直接割り当てすることもできます。 メンバーの電子メール アドレスをコンマで区切ります。 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US' -Members  'KathyBonner@contoso.com', 'MaxHargrave@contoso.com'
```

## <a name="upload-an-add-in-from-the-office-store"></a>アップロードストアからアドインをOfficeする

**New-OrganizationAddIn コマンドレットを実行** して、新しい組織のストアからOfficeします。
  
次の例では **、New-OrganizationAddIn** コマンドレットは、米国の場所とコンテンツ 市場のアドインの AssetId を指定します。
  
```powershell
New-OrganizationAddIn -AssetId 'WA104099688' -Locale 'en-US' -ContentMarket 'en-US'
```

_AssetId_ パラメーターの値を確認するには、アドインの [ストア] web ページOffice URL からコピーできます。 AssetIds は常に "WA" で始まり、その後に数値が続きます。 たとえば、前の例では、WA104099688 の AssetId 値のソースは、アドインの Office ストア Web ページ URL です。 [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688)
  
_Locale_ パラメーターと _ContentMarket_ パラメーターの値は同一であり、アドインのインストールを行う国/地域を示します。 形式は en-US、fr-FR です。 など。 
  
> [!NOTE]
> Office ストアからアップロードされたアドインは、最新の更新プログラムが Office ストアで利用できる数日以内に更新されます。 
  
## <a name="get-details-of-an-add-in"></a>アドインの詳細を取得する

次に **示すように Get-OrganizationAddIn** コマンドレットを実行して、アドインの製品 ID を含むテナントにアップロードされたすべてのアドインの詳細を取得します。
  
```powershell
Get-OrganizationAddIn
```

_ProductId_ **パラメーターの値を指定して Get-OrganizationAddIn** コマンドレットを実行し、詳細を取得するアドインを指定します。 
  
```powershell
Get-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

すべてのアドインと割り当てられたユーザーとグループの詳細を取得するには、次の例に示すように **、Get-OrganizationAddIn** コマンドレットの出力を Format-List コマンドレットにパイプ処理します。
  
```powershell
foreach($G in (Get-organizationAddIn)){Get-OrganizationAddIn -ProductId $G.ProductId | Format-List}
```

## <a name="turn-on-or-turn-off-an-add-in"></a>アドインを有効またはオフにする

アドインを無効にし、割り当てられているユーザーとグループにアクセスできなくなった場合は、次の例に示すように _、ProductId_ パラメーターと _Enabled_ パラメーターを設定して **Set-OrganizationAddIn** コマンドレットを実行します。 `$false`
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $false
```

アドインを有効に戻す場合は、Enabled パラメーターをに設定して同  _じコマンドレット_ を実行します  `$true` 。
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $true
```

## <a name="add-or-remove-users-from-an-add-in"></a>アドインにユーザーを追加または削除する

ユーザーとグループを特定のアドインに追加するには _、ProductId、Add、_ および Members パラメーターを使用して **Set-OrganizationAddInAssignments** _コマンドレットを__実行_ します。 メンバーの電子メール アドレスをコンマで区切ります。 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Add -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

ユーザーとグループを削除するには、Remove パラメーターを使用して同じコマンドレット  _を実行_ します。 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Remove -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

テナント上のすべてのユーザーにアドインを割り当てるには、値をに設定した  _AssignToEveryone_ パラメーターを使用して同じコマンドレットを実行します  `$true` 。
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $true
```

アドインをすべてのユーザーに割り当てず、以前に割り当てられたユーザーとグループに戻すには、同じコマンドレットを実行し、その値をに設定して  _AssignToEveryone_ パラメーターをオフにします  `$false` 。
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $false
```

## <a name="update-an-add-in"></a>アドインを更新する

マニフェストからアドインを更新するには、次の例に示すように _、ProductId、ManifestPath、_ および _Locale_ パラメーターを使用して **Set-OrganizationAddIn** コマンドレットを実行します。  
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

> [!NOTE]
> Office ストアからアップロードされたアドインは、最新の更新プログラムが Office ストアで利用できる数日以内に更新されます。 
  
## <a name="delete-an-add-in"></a>アドインを削除する

アドインを削除するには、次の例に示すように _、ProductId_ パラメーターを使用して **Remove-OrganizationAddIn** コマンドレットを実行します。 
  
```powershell
Remove-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

<!--
## Customize Microsoft Store add-ins for your organization

You must customize the add-in before you deploy it to your organization. Add-ins older than version 1.1 are not supported by this feature. 

We recommend that you deploy a customized add-in  to yourself first to make sure it works as expected before you deploy it to your entire organization.

Note also the following restrictions:
- All URLs must be absolute (include http or https) and valid.
- *DisplayName* must not exceed 125 characters 
- *DisplayName*, *Resources* and *AppDomains* must not include the following characters: 
 
    - \<
    -  \>
    -  ;
    -  =   

If you want to customize an add-in that has been deployed, you have to uninstall it in the admin center, and see [remove an add-in from local cache](#remove-an-add-in-from-local-cache) for steps to remove it from each computer it has been deployed to.

To customize an add-in, run the **Set –OrganizationAddInOverrides** cmdlet with the *ProductId* as a parameter, followed by the tag you want to overwrite and the new value. To find out how to get the *ProductId* see [get details of an add-in](#get-details-of-an-add-in) in this article. For example:

```powershell
 Set-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 -IconUrl "https://site.com/img.jpg" 
```
To customize multiple tags for an add-in, add those tags to the commandline:

```powershell
Set-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 -Hosts h1, 2 -DisplayName "New DocuSign W" -IconUrl "https://site.com/img.jpg" 
```

> [!IMPORTANT]
> You must apply multiple customized tags to one add-in as one command. If you customize tags one by one, only the last customization will be applied. Additionally, if you customize a tag by mistake, you must remove all customizations and start over.

### Tags you can customize

| Tag                  | Description          |
| :------------------- | :------------------- |
| \<IconURL>   </br>| The URL of the image used as the add-in’s icon (in admin center). </br> |
| \<DisplayName>| The title of the add-in  (in admin center).|
| \<Hosts>| List of apps that will support the add-in.|
| \<SourceLocation> | The source URL that the add-in will connect to.| 
| \<AppDomains> | A list of domains that the add-in can connect with. | 
| \<SupportURL>| The URL users can use to access help and support. | 
| \<Resources>  | This tag contains a number of elements including titles, tooltips, and icons of different sizes.| 
|
### Customize Resources tag

Any element in the <Resources> tag of the manifest can be customized dynamically. You first need to check the manifest to find the element id to which you want to assign a new value. The <Resources> tag looks like this:

```
<Resources>  
    <bt:Images> 
          <bt:Image id=”img16icon” DefaultValue=”https://site.com/img.jpg” 
    </bt:Images> 
</Resources> 
``` 
In this case, the element id for the image is “img16icon” and the value associated with it is “http:<i></i>//site.<i></i>com/img.jpg.”

Once you have identified the elements you want to customize, use the following command in Powershell to assign new values to the elements:

```powershell
Set-OrganizationAddInOverrides -Resources @{“ElementID” = “New Value”; “NextElementID” = “Next New Value”} 
```

You can customize as many elements with the command as you need to.

### Remove customization from an add-in

The only option currently available for deleting customizations is to delete all of them at once:

```powershell
Remove-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 
```

### View add-in customizations

To view a list of applied customizations, run the **Get-OrganizationAddInOverrides** cmdlet. If **Get-OrganizationAddInOverrides** is run without a *ProductId* then a list of all add-ins with applied overrides are returned.  

```powershell
Get-OrganizationAddInOverrides 
```
If ProductId is specified, then a list of overrides applied to that add-in is returned. 

```powershell
Get-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 
```

### Remove an add-in from local cache

If an add-in has been deployed, it has to be removed from the cache in each computer before it can be customized. To remive an add-in from cache:

1. Navigate to the “Users” folder in C:\ 
1. Go to your user folder
1. Navigate to AppData\Local\Microsoft\Office and select the folder associated with your version of Office
1. In the *Wef* folder delete the *Manifests* folder.

-->

## <a name="get-detailed-help-for-each-cmdlet"></a>各コマンドレットの詳細なヘルプを取得する

Get-help コマンドレットを使用して、各コマンドレットの詳細なヘルプを確認できます。 たとえば、次のコマンドレットは、このコマンドレットの詳細Remove-OrganizationAddInします。
  
```powershell
Get-help Remove-OrganizationAddIn -Full
```
