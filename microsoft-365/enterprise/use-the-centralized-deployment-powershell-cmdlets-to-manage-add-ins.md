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
description: 一元展開 PowerShell コマンドレットを使用して、Microsoft 365 組織Officeアドインを展開および管理できます。
ms.openlocfilehash: 7872deedfcfe058f0a4ac63c489bbed139699d18
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924674"
---
# <a name="use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins"></a><span data-ttu-id="e4a2e-103">集中展開 PowerShell コマンドレットを使用してアドインを管理する</span><span class="sxs-lookup"><span data-stu-id="e4a2e-103">Use the Centralized Deployment PowerShell cmdlets to manage add-ins</span></span>

<span data-ttu-id="e4a2e-104">Microsoft 365 のグローバル管理者は、集中展開機能を使用して Office アドインをユーザーに展開できます (「管理センターで Office アドインを展開する」を [参照](../admin/manage/manage-deployment-of-add-ins.md)してください)。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-104">As a Microsoft 365 global admin, you can deploy Office add-ins to users via the Centralized Deployment feature (see [Deploy Office Add-ins in the admin center](../admin/manage/manage-deployment-of-add-ins.md)).</span></span> <span data-ttu-id="e4a2e-105">Microsoft 365 管理センター Officeアドインを展開する以外にも、Microsoft PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-105">In addition to deploying Office add-ins via the Microsoft 365 admin center, you can also use Microsoft PowerShell.</span></span> <span data-ttu-id="e4a2e-106">[O365 の一元化されたAdd-In展開モジュールをインストールWindows PowerShell。](https://www.powershellgallery.com/packages/O365CentralizedAddInDeployment)</span><span class="sxs-lookup"><span data-stu-id="e4a2e-106">Install the [O365 Centralized Add-In Deployment Module for Windows PowerShell](https://www.powershellgallery.com/packages/O365CentralizedAddInDeployment).</span></span> 

<span data-ttu-id="e4a2e-107">モジュールをダウンロードした後、通常のウィンドウを開Windows PowerShell次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-107">After you download the module, open a regular Windows PowerShell window and run the following cmdlet:</span></span>

```powershell
 Import-Module -Name O365CentralizedAddInDeployment
```
    
## <a name="connect-using-your-admin-credentials"></a><span data-ttu-id="e4a2e-108">管理者資格情報を使用して接続する</span><span class="sxs-lookup"><span data-stu-id="e4a2e-108">Connect using your admin credentials</span></span>

<span data-ttu-id="e4a2e-109">集中展開コマンドレットを使用する前に、サインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-109">Before you can use the Centralized Deployment cmdlets, you need to sign in.</span></span>
  
1. <span data-ttu-id="e4a2e-110">PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-110">Start PowerShell.</span></span>
    
2. <span data-ttu-id="e4a2e-111">会社の管理者資格情報を使用して PowerShell に接続します。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-111">Connect to PowerShell by using your company admin credentials.</span></span> <span data-ttu-id="e4a2e-112">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-112">Run the following cmdlet.</span></span>
    
  ```powershell
  Connect-OrganizationAddInService
  ```

3. <span data-ttu-id="e4a2e-113">[資格情報 **の入力] ページ** で、Microsoft 365 グローバル管理者資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-113">In the **Enter Credentials** page, enter your Microsoft 365 global admin credentials.</span></span> <span data-ttu-id="e4a2e-114">または、資格情報をコマンドレットに直接入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-114">Alternately, you can enter your credentials directly into the cmdlet.</span></span> 
    
    <span data-ttu-id="e4a2e-115">会社の管理者資格情報を PSCredential オブジェクトとして指定する次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-115">Run the following cmdlet specifying your company admin credentials as a PSCredential object.</span></span>
    
  ```powershell
  $secpasswd = ConvertTo-SecureString "MyPassword" -AsPlainText -Force
  $mycredentials = New-Object System.Management.Automation.PSCredential ("serviceaccount@contoso.com", $secpasswd)
  Connect-OrganizationAddInService -Credential $mycredentials
  ```

> [!NOTE]
> <span data-ttu-id="e4a2e-116">PowerShell の使用の詳細については、「Connect [to Microsoft 365 with PowerShell」を参照してください](./connect-to-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-116">For more information about using PowerShell, see [Connect to Microsoft 365 with PowerShell](./connect-to-microsoft-365-powershell.md).</span></span> 
  
## <a name="upload-an-add-in-manifest"></a><span data-ttu-id="e4a2e-117">アドイン マニフェストのアップロード</span><span class="sxs-lookup"><span data-stu-id="e4a2e-117">Upload an add-in manifest</span></span>

<span data-ttu-id="e4a2e-118">**New-OrganizationAdd-In** コマンドレットを実行して、ファイルの場所または URL のいずれかであるパスからアドイン マニフェストをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-118">Run the **New-OrganizationAdd-In** cmdlet to upload an add-in manifest from a path, which can be either a file location or URL.</span></span> <span data-ttu-id="e4a2e-119">次の例は  _、ManifestPath_ パラメーターの値のファイルの場所を示しています。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-119">The following example shows a file location for the value of the  _ManifestPath_ parameter.</span></span> 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

<span data-ttu-id="e4a2e-120">次の例に示すように **、New-OrganizationAdd-In** コマンドレットを実行してアドインをアップロードし  _、Members_ パラメーターを使用してユーザーまたはグループに直接割り当てすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-120">You can also run the **New-OrganizationAdd-In** cmdlet to upload an add-in and assign it to users or groups directly by using the  _Members_ parameter, as shown in the following example.</span></span> <span data-ttu-id="e4a2e-121">メンバーの電子メール アドレスをコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-121">Separate the email addresses of members with a comma.</span></span> 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US' -Members  'KathyBonner@contoso.com', 'MaxHargrave@contoso.com'
```

## <a name="upload-an-add-in-from-the-office-store"></a><span data-ttu-id="e4a2e-122">アドインをストアからOfficeする</span><span class="sxs-lookup"><span data-stu-id="e4a2e-122">Upload an add-in from the Office Store</span></span>

<span data-ttu-id="e4a2e-123">**New-OrganizationAddIn コマンドレットを実行** して、新しい組織のストアからOfficeします。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-123">Run the **New-OrganizationAddIn** cmdlet to upload a manifest from the Office Store.</span></span>
  
<span data-ttu-id="e4a2e-124">次の例では **、New-OrganizationAddIn** コマンドレットは、米国の場所とコンテンツ 市場のアドインの AssetId を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-124">In the following example, the **New-OrganizationAddIn** cmdlet specifies the AssetId for an add-in for a United States location and content market.</span></span>
  
```powershell
New-OrganizationAddIn -AssetId 'WA104099688' -Locale 'en-US' -ContentMarket 'en-US'
```

<span data-ttu-id="e4a2e-125">_AssetId_ パラメーターの値を確認するには、アドインの [ストア] web ページOffice URL からコピーできます。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-125">To determine the value for the  _AssetId_ parameter, you can copy it from the URL of the Office Store webpage for the add-in.</span></span> <span data-ttu-id="e4a2e-126">AssetIds は常に "WA" で始まり、その後に数値が続きます。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-126">AssetIds always begin with "WA" followed by a number.</span></span> <span data-ttu-id="e4a2e-127">たとえば、前の例では、WA104099688 の AssetId 値のソースは、アドインの Office ストア Web ページ URL です。 [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688)</span><span class="sxs-lookup"><span data-stu-id="e4a2e-127">For example, in the previous example, the source for the AssetId value of WA104099688 is the Office Store webpage URL for the add-in: [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688).</span></span>
  
<span data-ttu-id="e4a2e-128">_Locale_ パラメーターと _ContentMarket_ パラメーターの値は同一であり、アドインのインストールを行う国/地域を示します。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-128">The values for the  _Locale_ parameter and the  _ContentMarket_ parameter are identical and indicate the country/region you're trying to install the add-in from.</span></span> <span data-ttu-id="e4a2e-129">形式は en-US、fr-FR です。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-129">The format is en-US, fr-FR.</span></span> <span data-ttu-id="e4a2e-130">など。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-130">and so forth.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e4a2e-131">Office ストアからアップロードされたアドインは、最新の更新プログラムが Office ストアで利用できる数日以内に更新されます。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-131">Add-ins uploaded from the Office Store will update automatically within a few days of the latest update being available on the Office Store.</span></span> 
  
## <a name="get-details-of-an-add-in"></a><span data-ttu-id="e4a2e-132">アドインの詳細を取得する</span><span class="sxs-lookup"><span data-stu-id="e4a2e-132">Get details of an add-in</span></span>

<span data-ttu-id="e4a2e-133">次に **示すように Get-OrganizationAddIn** コマンドレットを実行して、アドインの製品 ID を含むテナントにアップロードされたすべてのアドインの詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-133">Run the **Get-OrganizationAddIn** cmdlet as shown below to get details of all add-ins uploaded to the tenant, included an add-in's product ID.</span></span>
  
```powershell
Get-OrganizationAddIn
```

<span data-ttu-id="e4a2e-134">_ProductId_ **パラメーターの値を指定して Get-OrganizationAddIn** コマンドレットを実行し、詳細を取得するアドインを指定します。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-134">Run the **Get-OrganizationAddIn** cmdlet with a value for the  _ProductId_ parameter to specify which add-in you want to retrieve details for.</span></span> 
  
```powershell
Get-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

<span data-ttu-id="e4a2e-135">すべてのアドインと割り当てられたユーザーとグループの詳細を取得するには、次の例に示すように **、Get-OrganizationAddIn** コマンドレットの出力を Format-List コマンドレットにパイプ処理します。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-135">To get full details of all the add-ins plus the assigned users and groups, pipe the output of the **Get-OrganizationAddIn** cmdlet to the Format-List cmdlet, as shown in the following example.</span></span>
  
```powershell
foreach($G in (Get-organizationAddIn)){Get-OrganizationAddIn -ProductId $G.ProductId | Format-List}
```

## <a name="turn-on-or-turn-off-an-add-in"></a><span data-ttu-id="e4a2e-136">アドインを有効またはオフにする</span><span class="sxs-lookup"><span data-stu-id="e4a2e-136">Turn on or turn off an add-in</span></span>

<span data-ttu-id="e4a2e-137">アドインを無効にし、割り当てられているユーザーとグループにアクセスできなくなった場合は、次の例に示すように _、ProductId_ パラメーターと _Enabled_ パラメーターを設定して **Set-OrganizationAddIn** コマンドレットを実行します。 `$false`</span><span class="sxs-lookup"><span data-stu-id="e4a2e-137">To turn off an add-in so users and groups that are assigned to it will no longer have access, run the **Set-OrganizationAddIn** cmdlet with the  _ProductId_ parameter and the  _Enabled_ parameter set to  `$false`, as shown in the following example.</span></span>
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $false
```

<span data-ttu-id="e4a2e-138">アドインを有効に戻す場合は、Enabled パラメーターをに設定して同  _じコマンドレット_ を実行します  `$true` 。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-138">To turn an add-in back on, run the same cmdlet with the  _Enabled_ parameter set to  `$true`.</span></span>
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $true
```

## <a name="add-or-remove-users-from-an-add-in"></a><span data-ttu-id="e4a2e-139">アドインにユーザーを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="e4a2e-139">Add or remove users from an add-in</span></span>

<span data-ttu-id="e4a2e-140">ユーザーとグループを特定のアドインに追加するには _、ProductId、Add、_ および Members パラメーターを使用して **Set-OrganizationAddInAssignments** _コマンドレットを__実行_ します。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-140">To add users and groups to a specific add-in, run the **Set-OrganizationAddInAssignments** cmdlet with the  _ProductId_,  _Add_, and  _Members_ parameters.</span></span> <span data-ttu-id="e4a2e-141">メンバーの電子メール アドレスをコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-141">Separate the email addresses of members with a comma.</span></span> 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Add -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

<span data-ttu-id="e4a2e-142">ユーザーとグループを削除するには、Remove パラメーターを使用して同じコマンドレット  _を実行_ します。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-142">To remove users and groups, run the same cmdlet using the  _Remove_ parameter.</span></span> 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Remove -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

<span data-ttu-id="e4a2e-143">テナント上のすべてのユーザーにアドインを割り当てるには、値をに設定した  _AssignToEveryone_ パラメーターを使用して同じコマンドレットを実行します  `$true` 。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-143">To assign an add-in to all users on the tenant, run the same cmdlet using the  _AssignToEveryone_ parameter with the value set to  `$true`.</span></span>
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $true
```

<span data-ttu-id="e4a2e-144">アドインをすべてのユーザーに割り当てず、以前に割り当てられたユーザーとグループに戻すには、同じコマンドレットを実行し、その値をに設定して  _AssignToEveryone_ パラメーターをオフにします  `$false` 。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-144">To not assign an add-in to everyone and revert to the previously assigned users and groups, you can run the same cmdlet and turn off the  _AssignToEveryone_ parameter by setting its value to  `$false`.</span></span>
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $false
```

## <a name="update-an-add-in"></a><span data-ttu-id="e4a2e-145">アドインを更新する</span><span class="sxs-lookup"><span data-stu-id="e4a2e-145">Update an add-in</span></span>

<span data-ttu-id="e4a2e-146">マニフェストからアドインを更新するには、次の例に示すように _、ProductId、ManifestPath、_ および _Locale_ パラメーターを使用して **Set-OrganizationAddIn** コマンドレットを実行します。 </span><span class="sxs-lookup"><span data-stu-id="e4a2e-146">To update an add-in from a manifest, run the **Set-OrganizationAddIn** cmdlet with the  _ProductId_,  _ManifestPath_, and  _Locale_ parameters, as shown in the following example.</span></span> 
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

> [!NOTE]
> <span data-ttu-id="e4a2e-147">Office ストアからアップロードされたアドインは、最新の更新プログラムが Office ストアで利用できる数日以内に更新されます。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-147">Add-ins uploaded from the Office Store will update automatically within a few days of the latest update being available on the Office Store.</span></span> 
  
## <a name="delete-an-add-in"></a><span data-ttu-id="e4a2e-148">アドインを削除する</span><span class="sxs-lookup"><span data-stu-id="e4a2e-148">Delete an add-in</span></span>

<span data-ttu-id="e4a2e-149">アドインを削除するには、次の例に示すように _、ProductId_ パラメーターを使用して **Remove-OrganizationAddIn** コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-149">To delete an add-in, run the **Remove-OrganizationAddIn** cmdlet with the  _ProductId_ parameter, as shown in the following example.</span></span> 
  
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

## <a name="get-detailed-help-for-each-cmdlet"></a><span data-ttu-id="e4a2e-150">各コマンドレットの詳細なヘルプを取得する</span><span class="sxs-lookup"><span data-stu-id="e4a2e-150">Get detailed help for each cmdlet</span></span>

<span data-ttu-id="e4a2e-151">Get-help コマンドレットを使用して、各コマンドレットの詳細なヘルプを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-151">You can look at detailed help for each cmdlet by using the Get-help cmdlet.</span></span> <span data-ttu-id="e4a2e-152">たとえば、次のコマンドレットは、このコマンドレットの詳細Remove-OrganizationAddInします。</span><span class="sxs-lookup"><span data-stu-id="e4a2e-152">For example, the following cmdlet provides detailed information about the Remove-OrganizationAddIn cmdlet.</span></span>
  
```powershell
Get-help Remove-OrganizationAddIn -Full
```