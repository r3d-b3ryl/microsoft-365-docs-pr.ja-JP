---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: 3d4ec38f0007460fa119e69eadc79cd9c51887ee
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2022
ms.locfileid: "66822603"
---
1. PowerShell バージョン 7 以降をインストールします。 詳細なガイダンスについては、「[Windows への PowerShell のインストール](/powershell/scripting/install/installing-powershell-on-windows)」を参照してください。

1. 管理者モードで PowerShell を実行します。
1. Microsoft Graph PowerShell モジュールをインストールする

    ```powershell
    Install-Module Microsoft.Graph
    Import-Module Microsoft.Graph
    ```

    バージョン 1.6.1 以降であることを確認します。

    ```powershell
    Get-InstalledModule Microsoft.Graph 
    ```

1. Teams Preview PowerShell モジュールをインストールします。

    ```powershell
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force
    Import-Module MicrosoftTeams 
    ```

    少なくともバージョン 4.1.0 で、Shifts コネクタ コマンドレットが含まれていることを確認します。

    ```powershell
    Get-Command -Module MicrosoftTeams -Name *teamsshiftsconnection* 
    ```

1. スクリプトの実行時にエラーが発生した場合は、PowerShell を終了するように設定します。

    ```powershell
    $ErrorActionPreference = "Stop" 
    ```

1. Windows で実行するスクリプトを有効にします。

    ```powershell
    Set-ExecutionPolicy bypass 
    ```