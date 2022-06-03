---
title: ライブ応答コマンドの例
description: Microsoft Defender for Endpointの基本的なライブ応答コマンドまたは高度なライブ応答コマンドの実行について説明し、それらの使用方法の例を参照してください。
keywords: 例, コマンド, cli, remote, shell, connection, live, response, リアルタイム, コマンド, スクリプト, 修復, ハント, エクスポート, ログ, ドロップ, ダウンロード, ファイル
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 77a1bd5c9234b7a38266be55825726e683557eb4
ms.sourcegitcommit: 35f167725bec5fd4fe131781a53d96b060cf232d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2022
ms.locfileid: "65872389"
---
# <a name="live-response-command-examples"></a>ライブ応答コマンドの例

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

ライブ応答で使用される一般的なコマンドについて説明し、一般的な使用方法の例を参照してください。

持っているロールに応じて、基本または高度なライブ応答コマンドを実行できます。 基本コマンドと高度なコマンドの詳細については、「 [ライブ応答を使用してデバイス上のエンティティを調査](live-response.md)する」を参照してください。

## `analyze`

```console
# Analyze the file malware.txt
analyze file c:\Users\user\Desktop\malware.txt
```

```console
# Analyze the process by PID
analyze process 1234
```

## `connections`

```console
# List active connections in json format using parameter name
connections -output json
```

```console
# List active connections in json format without parameter name
connections json
```

## `dir`

```console
# List files and sub-folders in the current folder (by default it will show relative paths [-relative_path])
dir
```

```console
# List files and sub-folders in the current folder, with their full path
dir -full_path
```

```console
# List files and sub-folders in a specific folder
dir C:\Users\user\Desktop\
```

```console
# List files and subfolders in the current folder in json format
dir -output json
```

## `fileinfo`

```console
# Display information about a file
fileinfo C:\Windows\notepad.exe
```

## `findfile`

```console
# Find file by name
findfile test.txt
```

## `getfile`

```console
# Download a file from a machine
getfile c:\Users\user\Desktop\work.txt
```

```console
# Download a file from a machine, automatically run prerequisite commands
getfile c:\Users\user\Desktop\work.txt -auto
```

> [!NOTE]
>
> 次のファイルの種類は、Live Response 内からこのコマンドを使用してダウンロード *できません* 。
>
> - [ポイント ファイルを再解析する](/windows-hardware/drivers/ifs/reparse-points)
> - [スパース ファイル](/windows-server/administration/windows-commands/fsutil-sparse)
> - 空のファイル
> - 仮想ファイル、または完全にローカルに存在しないファイル
>
> これらのファイルの種類は [、PowerShell](/powershell/scripting/overview) でサポート *されています*。
>
> Live Response 内からこのコマンドを使用する際に問題が発生した場合は、代わりに PowerShell を使用します。

## `library`

```console
# List files in the library
library
```

```console
# Delete a file from the library
library delete script.ps1
```

## `processes`

```console
# Show all processes
processes
```

```console
# Get process by pid
processes 123
```

```console
# Get process by pid with argument name
processes -pid 123
```

```console
# Get process by name
processes -name notepad.exe
```

## `putfile`

```console
# Upload file from library
putfile get-process-by-name.ps1
```

```console
# Upload file from library, overwrite file if it exists
putfile get-process-by-name.ps1 -overwrite
```

```console
# Upload file from library, keep it on the machine after a restart
putfile get-process-by-name.ps1 -keep
```

## `registry`

```console
# Show information about the values in a registry key
registry HKEY_CURRENT_USER\Console
```

```console
# Show information about a specific registry value (the double backslash \\ indicates a registry value versus key)
registry HKEY_CURRENT_USER\Console\\ScreenBufferSize
```


## `remediate`

```console
# Remediate file in specific path
remediate file c:\Users\user\Desktop\malware.exe
```

```console
# Remediate process with specific PID
remediate process 7960
```

```console
# Remediate a registry value (the double backslash \\ indicates a registry value versus key)
remediate registry HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run\\SPStartup
```

```console
# See list of all remediated entities
remediate list
```

## `run`

```console
# Run PowerShell script from the library without arguments
run script.ps1
```

```console
# Run PowerShell script from the library with arguments
run get-process-by-name.ps1 -parameters "-processName Registry"
```

> [!NOTE]
>
> 実行時間の長いコマンド ('**run**' や '**getfile**' など) の場合は、コマンドの末尾にある '**&**' 記号を使用して、バックグラウンドでそのアクションを実行することができます。
> これにより、コンピューターの調査を続行し、'**fg**' 基本コマンドを使用して完了するとバックグラウンド [コマンド](live-response.md#basic-commands)に戻ります。

## `scheduledtask`

```console
# Get all scheduled tasks
scheduledtasks
```

```console
# Get specific scheduled task by location and name
scheduledtasks Microsoft\Windows\Subscription\LicenseAcquisition
```

```console
# Get specific scheduled task by location and name with spacing
scheduledtasks "Microsoft\Configuration Manager\Configuration Manager Health Evaluation"
```

## `undo`

```console
# Restore remediated registry
undo registry HKEY_CURRENT_USER\Console\ScreenBufferSize
```

```console
# Restore remediated scheduledtask
undo scheduledtask Microsoft\Windows\Subscription\LicenseAcquisition
```

```console
# Restore remediated file
undo file c:\Users\user\Desktop\malware.exe
```
