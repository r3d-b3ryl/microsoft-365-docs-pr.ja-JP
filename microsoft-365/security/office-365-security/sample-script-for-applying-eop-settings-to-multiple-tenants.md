---
title: EOP の設定のサンプルスクリプト-複数のテナント
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
ms.custom:
- seo-marvel-apr2020
description: この記事では、PowerShell を使用して Microsoft Exchange Online Protection (EOP) のテナントに構成設定を適用する方法について説明します。
ms.openlocfilehash: dbb4135c89ac8d351c40bd7d9ce5301500a9b81b
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376569"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>EOP 設定を複数のテナントに適用するスクリプトのサンプル

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


次のサンプルスクリプトを使用すると、複数のテナント (会社) を管理する Microsoft Exchange Online Protection (EOP) 管理者が Exchange Online PowerShell を使用して、構成設定を表示したり、テナントに適用したりできます。

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>複数のテナントでスクリプトまたはコマンドレットを実行するには

1. まだインストールしていない場合は、 [Exchange Online V2 モジュールをインストール](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)します。

2. スプレッドシートアプリ (たとえば、Excel) を使用して、次の詳細を含む .csv ファイルを作成します。

   - UserName 列: 接続に使用するアカウント (例: `admin@contoso.onmicrosoft.com` )。
   - コマンドレット列: 実行するコマンドレットまたはコマンド (例: `Get-AcceptedDomain` または `Get-AcceptedDomain | FT Name` )。

   このファイルは次のようになります。

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. 見つけやすい場所に .csv ファイルを保存します (たとえば、c:\scripts\inputfile.csv)。

4. [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1)スクリプトをメモ帳にコピーし、見つけやすい場所 (c:\scripts など) にファイルを保存します。

5. 次の構文を使用して、スクリプトを実行します。

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   次に例を示します:

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. 各テナントはにログオンされ、スクリプトが実行されます。

## <a name="runcmdletonmultipletenantsps1"></a>RunCmdletOnMultipleTenants.ps1

> [!NOTE]
> 環境に合わせてスクリプトの行を変更する必要がある場合があり `Connect-IPPSSession` ます。 たとえば、Office 365 ドイツでは、スクリプト内の現在の値とは異なる _Connectionuri_ 値が必要です。 詳細については、「 [Exchange Online Powershell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)への接続」を参照してください。

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
