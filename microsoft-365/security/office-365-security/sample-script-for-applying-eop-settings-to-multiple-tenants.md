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
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>EOP 設定を複数のテナントに適用するスクリプトのサンプル

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
-  [Exchange Online Protection スタンドアロン](exchange-online-protection-overview.md)

次のサンプル スクリプトを使用すると、複数のテナント (企業) を管理する Microsoft Exchange Online Protection (EOP) 管理者は、Exchange Online PowerShell を使用して、テナントの構成設定を表示または適用できます。

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>複数のテナントでスクリプトまたはコマンドレットを実行するには

1. まだインストールしていない場合は [、Exchange Online V2 モジュールをインストールします](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)。

2. スプレッドシート アプリ (Excel など) を使用して、次の詳細を含む .csv ファイルを作成します。

   - [UserName] 列: 接続に使用するアカウント (例 `admin@contoso.onmicrosoft.com` :
   - コマンドレット列: 実行するコマンドレットまたはコマンド (たとえば、 `Get-AcceptedDomain` または `Get-AcceptedDomain | FT Name` )。

   ファイルは次のように表示されます。

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. .csv ファイルは、見つけやすい場所 (たとえば、c:\scripts\inputfile.csv) に保存します。

4. このスクリプト [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) メモ帳にコピーし、ファイルを見つけやすい場所 (c:\scripts など) に保存します。

5. 次の構文を使用して、スクリプトを実行します。

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   次に例を示します:

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. 各テナントがログオンし、スクリプトが実行されます。

## <a name="runcmdletonmultipletenantsps1"></a>RunCmdletOnMultipleTenants.ps1

> [!NOTE]
> 環境に合わせてスクリプト `Connect-IPPSSession` 内の行を変更する必要がある場合があります。 たとえば、Office 365 Germany では、スクリプトの現在の値とは異なる _ConnectionUri_ 値が必要です。 詳細については [、「Exchange Online Powershell への接続」を参照してください](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

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
