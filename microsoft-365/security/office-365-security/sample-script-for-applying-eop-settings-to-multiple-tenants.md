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
description: この記事では、PowerShell を使用して、ユーザー保護 (EOP) のテナントに構成設定を適用するMicrosoft Exchange Online説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 77a1dce25901845628f8148c44a0d0783088255e
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206555"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a><span data-ttu-id="f0083-103">EOP 設定を複数のテナントに適用するスクリプトのサンプル</span><span class="sxs-lookup"><span data-stu-id="f0083-103">Sample script for applying EOP settings to multiple tenants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f0083-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="f0083-104">**Applies to**</span></span>
-  [<span data-ttu-id="f0083-105">Exchange Online Protectionスタンドアロン</span><span class="sxs-lookup"><span data-stu-id="f0083-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="f0083-106">次のサンプル スクリプトでは、複数のテナント (企業) を管理する Microsoft Exchange Online Protection (EOP) 管理者が Exchange Online PowerShell を使用して、テナントに構成設定を表示および/または適用できます。</span><span class="sxs-lookup"><span data-stu-id="f0083-106">The following sample script lets Microsoft Exchange Online Protection (EOP) admins who manage multiple tenants (companies) use Exchange Online PowerShell to view and/or apply configuration settings to their tenants.</span></span>

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a><span data-ttu-id="f0083-107">複数のテナントでスクリプトまたはコマンドレットを実行するには</span><span class="sxs-lookup"><span data-stu-id="f0083-107">To run a script or cmdlet on multiple tenants</span></span>

1. <span data-ttu-id="f0083-108">まだインストールしていない場合は[、V2 モジュールExchange Onlineインストールします](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)。</span><span class="sxs-lookup"><span data-stu-id="f0083-108">If you haven't already, [install the Exchange Online V2 module](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

2. <span data-ttu-id="f0083-109">スプレッドシート アプリ (たとえば、Excel) を使用して、次.csvファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="f0083-109">Using an spreadsheet app (for example, Excel), create a .csv file with the following details:</span></span>

   - <span data-ttu-id="f0083-110">[UserName] 列: 接続に使用するアカウント (たとえば `admin@contoso.onmicrosoft.com` )。</span><span class="sxs-lookup"><span data-stu-id="f0083-110">UserName column: The account that you'll use to connect (for example, `admin@contoso.onmicrosoft.com`).</span></span>
   - <span data-ttu-id="f0083-111">コマンドレット列: 実行するコマンドレットまたはコマンド (たとえば、 `Get-AcceptedDomain` または `Get-AcceptedDomain | FT Name` )。</span><span class="sxs-lookup"><span data-stu-id="f0083-111">Cmdlet column: The cmdlet or command to run (for example, `Get-AcceptedDomain` or `Get-AcceptedDomain | FT Name`).</span></span>

   <span data-ttu-id="f0083-112">ファイルは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0083-112">The file will look like this:</span></span>

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. <span data-ttu-id="f0083-113">ファイルを.csv簡単に見つけることができる場所に保存します (たとえば、c:\scripts\inputfile.csv)。</span><span class="sxs-lookup"><span data-stu-id="f0083-113">Save the .csv file in a location that's easy to find (for example, c:\scripts\inputfile.csv).</span></span>

4. <span data-ttu-id="f0083-114">RunCmdletOnMultipleTenants.ps1スクリプト[を](#runcmdletonmultipletenantsps1)メモ帳にコピーし、ファイルを見つけやすい場所 (c:\scripts など) に保存します。</span><span class="sxs-lookup"><span data-stu-id="f0083-114">Copy the [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script into Notepad, and then save the file to a location that's easy to find (for example, c:\scripts).</span></span>

5. <span data-ttu-id="f0083-115">次の構文を使用して、スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0083-115">Run the script by using the following syntax:</span></span>

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   <span data-ttu-id="f0083-116">次に例を示します:</span><span class="sxs-lookup"><span data-stu-id="f0083-116">Here's an example:</span></span>

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. <span data-ttu-id="f0083-117">各テナントにログオンし、スクリプトが実行されます。</span><span class="sxs-lookup"><span data-stu-id="f0083-117">Each tenant will be logged on to, and the script will be run.</span></span>

## <a name="runcmdletonmultipletenantsps1"></a><span data-ttu-id="f0083-118">RunCmdletOnMultipleTenants.ps1</span><span class="sxs-lookup"><span data-stu-id="f0083-118">RunCmdletOnMultipleTenants.ps1</span></span>

> [!NOTE]
> <span data-ttu-id="f0083-119">環境に合わせてスクリプト内 `Connect-IPPSSession` の行を変更する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="f0083-119">You might need to modify the `Connect-IPPSSession` line in the script to match your environment.</span></span> <span data-ttu-id="f0083-120">たとえば、ドイツOffice 365スクリプトの現在の値とは異なる _ConnectionUri_ 値が必要です。</span><span class="sxs-lookup"><span data-stu-id="f0083-120">For example, Office 365 Germany requires a different _ConnectionUri_ value than the current value in a script.</span></span> <span data-ttu-id="f0083-121">詳細については、「Powershell のConnectをExchange Online[する」を参照してください](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f0083-121">For details, see Connect to [Exchange Online Powershell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

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