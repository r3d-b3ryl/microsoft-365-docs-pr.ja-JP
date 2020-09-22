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
ms.openlocfilehash: 6e33ceb6a9daa88bfefd4ec08ac9f2a9f34a942f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198681"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>EOP 設定を複数のテナントに適用するスクリプトのサンプル

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


以下のサンプル スクリプトにより、複数のテナント (会社) を管理する Microsoft Exchange Online Protection (EOP) 管理者は、Windows PowerShell を使用して構成設定をテナントに適用できます。

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>複数のテナントでスクリプトまたはコマンドレットを実行するには

1. Excel などのアプリケーションを使用して, .csv ファイル (c:\scripts\inputfile.csv など) を作成します。

2. .csv ファイルで、次の 2 つの列名を指定します。「UserName」および「Cmdlet」。

3. .csv ファイルの各行で、テナントの管理者名を UserName 列に追加し、そのテナントのために実行するコマンドレットを Cmdlet 列に追加します。例えば、admin@contoso.com と Get-AcceptedDomain を使用します。

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

```powershell
# This script runs Windows PowerShell cmdlets on multiple tenants.
# Usage: RunCmdletOnMultipleTenants.ps1 inputfile.csv
#
# .csv input file sample:
# UserName,Cmdlet
# admin@contoso.com,Get-AcceptedDomain | ft Name
# URI for connecting to remote Windows PowerShell
$URI = "https://ps.protection.outlook.com/powershell-liveid/"
# Get the .csv file name as an argument to this script.
$FilePath = $args[0]
# Import the UserName and Cmdlet values from the .csv file.
$CompanyList = Import-CSV $FilePath
# Loop through each entry from the .csv file.
ForEach ($Company in $CompanyList) {
# Get the current entry's UserName.
$UserName = $Company.UserName
# Get the current entry's Cmdlet.
$Cmdlet = $Company.Cmdlet
# Create a PowerShell credential object by using the current entry's UserName. Prompt for the password.
$UserCredential = Get-Credential -username $UserName
# Log on to a new Windows PowerShell session.
$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri $URI -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $Session
# Here's where the script to be run on the tenant goes.
# In this example, the cmdlet in the .csv file runs.
Invoke-Expression $Cmdlet
# End the current PowerShell session.
Remove-PsSession -Session $Session
}
```
