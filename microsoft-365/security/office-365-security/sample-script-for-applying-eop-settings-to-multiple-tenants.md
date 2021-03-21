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
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928510"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>EOP 設定を複数のテナントに適用するスクリプトのサンプル

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
-  [Exchange Online Protection スタンドアロン](exchange-online-protection-overview.md)

次のサンプル スクリプトでは、複数のテナント (企業) を管理する Microsoft Exchange Online Protection (EOP) 管理者が Exchange Online PowerShell を使用して、テナントに構成設定を表示および/または適用できます。

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>複数のテナントでスクリプトまたはコマンドレットを実行するには

1. まだインストールしていない場合は [、Exchange Online V2 モジュールをインストールします](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)。

2. スプレッドシート アプリ (Excel など) を使用して、次の詳細を含む .csv ファイルを作成します。

   - [UserName] 列: 接続に使用するアカウント (たとえば `admin@contoso.onmicrosoft.com` )。
   - コマンドレット列: 実行するコマンドレットまたはコマンド (たとえば、 `Get-AcceptedDomain` または `Get-AcceptedDomain | FT Name` )。

   ファイルは次のように表示されます。

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. .csv ファイルを見つけやすい場所に保存します (たとえば、c:\scripts\inputfile.csv)。

4. メモ帳 [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) スクリプトをコピーし、ファイルを見つけやすい場所 (c:\scripts など) に保存します。

5. 次の構文を使用して、スクリプトを実行します。

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   次に例を示します:

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. 各テナントにログオンし、スクリプトが実行されます。

## <a name="runcmdletonmultipletenantsps1"></a>RunCmdletOnMultipleTenants.ps1

> [!NOTE]
> 環境に合わせてスクリプト内 `Connect-IPPSSession` の行を変更する必要がある場合があります。 たとえば、Office 365 ドイツでは、スクリプトの現在の値とは異なる _ConnectionUri_ 値が必要です。 詳細については、「Connect to [Exchange Online Powershell」を参照してください](/powershell/exchange/connect-to-exchange-online-protection-powershell)。

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