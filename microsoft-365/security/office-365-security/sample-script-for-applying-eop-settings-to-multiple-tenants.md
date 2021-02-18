---
title: EOP 設定のサンプル スクリプト - 複数のテナント
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
ms.custom:
- seo-marvel-apr2020
description: この記事では、PowerShell を使用して、Microsoft Exchange Online Protection (EOP) のテナントに構成設定を適用する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4823ed09cd8a9d72aef21df3d51213cb4512b4f9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288539"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a><span data-ttu-id="e22d9-103">EOP 設定を複数のテナントに適用するスクリプトのサンプル</span><span class="sxs-lookup"><span data-stu-id="e22d9-103">Sample script for applying EOP settings to multiple tenants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e22d9-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="e22d9-104">**Applies to**</span></span>
-  [<span data-ttu-id="e22d9-105">Exchange Online Protection スタンドアロン</span><span class="sxs-lookup"><span data-stu-id="e22d9-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="e22d9-106">次のサンプル スクリプトを使用すると、複数のテナント (企業) を管理する Microsoft Exchange Online Protection (EOP) 管理者は、Exchange Online PowerShell を使用して、テナントの構成設定を表示または適用できます。</span><span class="sxs-lookup"><span data-stu-id="e22d9-106">The following sample script lets Microsoft Exchange Online Protection (EOP) admins who manage multiple tenants (companies) use Exchange Online PowerShell to view and/or apply configuration settings to their tenants.</span></span>

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a><span data-ttu-id="e22d9-107">複数のテナントでスクリプトまたはコマンドレットを実行するには</span><span class="sxs-lookup"><span data-stu-id="e22d9-107">To run a script or cmdlet on multiple tenants</span></span>

1. <span data-ttu-id="e22d9-108">まだインストールしていない場合は [、Exchange Online V2 モジュールをインストールします](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)。</span><span class="sxs-lookup"><span data-stu-id="e22d9-108">If you haven't already, [install the Exchange Online V2 module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

2. <span data-ttu-id="e22d9-109">スプレッドシート アプリ (Excel など) を使用して、次の詳細を含む .csv ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="e22d9-109">Using an spreadsheet app (for example, Excel), create a .csv file with the following details:</span></span>

   - <span data-ttu-id="e22d9-110">[UserName] 列: 接続に使用するアカウント (例 `admin@contoso.onmicrosoft.com` :</span><span class="sxs-lookup"><span data-stu-id="e22d9-110">UserName column: The account that you'll use to connect (for example, `admin@contoso.onmicrosoft.com`).</span></span>
   - <span data-ttu-id="e22d9-111">コマンドレット列: 実行するコマンドレットまたはコマンド (たとえば、 `Get-AcceptedDomain` または `Get-AcceptedDomain | FT Name` )。</span><span class="sxs-lookup"><span data-stu-id="e22d9-111">Cmdlet column: The cmdlet or command to run (for example, `Get-AcceptedDomain` or `Get-AcceptedDomain | FT Name`).</span></span>

   <span data-ttu-id="e22d9-112">ファイルは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="e22d9-112">The file will look like this:</span></span>

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. <span data-ttu-id="e22d9-113">.csv ファイルは、見つけやすい場所 (たとえば、c:\scripts\inputfile.csv) に保存します。</span><span class="sxs-lookup"><span data-stu-id="e22d9-113">Save the .csv file in a location that's easy to find (for example, c:\scripts\inputfile.csv).</span></span>

4. <span data-ttu-id="e22d9-114">このスクリプト [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) メモ帳にコピーし、ファイルを見つけやすい場所 (c:\scripts など) に保存します。</span><span class="sxs-lookup"><span data-stu-id="e22d9-114">Copy the [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script into Notepad, and then save the file to a location that's easy to find (for example, c:\scripts).</span></span>

5. <span data-ttu-id="e22d9-115">次の構文を使用して、スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="e22d9-115">Run the script by using the following syntax:</span></span>

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   <span data-ttu-id="e22d9-116">次に例を示します:</span><span class="sxs-lookup"><span data-stu-id="e22d9-116">Here's an example:</span></span>

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. <span data-ttu-id="e22d9-117">各テナントがログオンし、スクリプトが実行されます。</span><span class="sxs-lookup"><span data-stu-id="e22d9-117">Each tenant will be logged on to, and the script will be run.</span></span>

## <a name="runcmdletonmultipletenantsps1"></a><span data-ttu-id="e22d9-118">RunCmdletOnMultipleTenants.ps1</span><span class="sxs-lookup"><span data-stu-id="e22d9-118">RunCmdletOnMultipleTenants.ps1</span></span>

> [!NOTE]
> <span data-ttu-id="e22d9-119">環境に合わせてスクリプト `Connect-IPPSSession` 内の行を変更する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="e22d9-119">You might need to modify the `Connect-IPPSSession` line in the script to match your environment.</span></span> <span data-ttu-id="e22d9-120">たとえば、Office 365 Germany では、スクリプトの現在の値とは異なる _ConnectionUri_ 値が必要です。</span><span class="sxs-lookup"><span data-stu-id="e22d9-120">For example, Office 365 Germany requires a different _ConnectionUri_ value than the current value in a script.</span></span> <span data-ttu-id="e22d9-121">詳細については [、「Exchange Online Powershell への接続」を参照してください](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e22d9-121">For details, see Connect to [Exchange Online Powershell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

```powershell
# This script runs Windows PowerShell cmdlets on multiple tenants.
#
# Usage: RunCmdletOnMultipleTenants.ps1 inputfile.csv
#
# .csv input file sample:
#
# UserName,Cmdlet
# admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
# admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name

# Get the .csv file name as an argument to this script.
$FilePath = $args[0]

# Import the UserName and Cmdlet values from the .csv file.
$CompanyList = Import-CSV $FilePath

# Load the EXO V2 module
Import-Module ExchangeOnlineManagement

# Loop through each entry from the .csv file.
ForEach ($Company in $CompanyList) {

# Get the current entry's UserName.
$UserName = $Company.UserName

# Get the current entry's Cmdlet.
$Cmdlet = $Company.Cmdlet

# Connect to EOP PowerShell by using the current entry's UserName. Prompt for the password.
Connect-IPPSSession -UserPrincipalName $UserName -ConnectionUri https://ps.protection.outlook.com/powershell-liveid/

# Here's where the script to be run on the tenant goes.
# In this example, the cmdlet in the .csv file runs.
Invoke-Expression $Cmdlet

# End the current PowerShell session.
Disconnect-ExchangeOnline -Confirm:$false
}
```
