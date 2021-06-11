---
title: ライブ応答コマンドの例
description: Microsoft Defender for Endpoint の基本的なライブ応答コマンドまたは高度なライブ応答コマンドを実行する方法と、その使用例を参照してください。
keywords: たとえば、コマンド、cli、リモート、シェル、接続、ライブ、応答、リアルタイム、コマンド、スクリプト、修復、ハント、エクスポート、ログ、ドロップ、ダウンロード、ファイル
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 389d9ad4a3e5fc876e7bded89389202e95bfda45
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879122"
---
# <a name="live-response-command-examples"></a><span data-ttu-id="608aa-104">ライブ応答コマンドの例</span><span class="sxs-lookup"><span data-stu-id="608aa-104">Live response command examples</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="608aa-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="608aa-105">**Applies to:**</span></span>
- [<span data-ttu-id="608aa-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="608aa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="608aa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="608aa-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="608aa-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="608aa-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="608aa-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="608aa-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="608aa-110">ライブ応答で使用される一般的なコマンドについて説明し、その一般的な使用例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="608aa-110">Learn about common commands used in live response and see examples on how they are typically used.</span></span>

<span data-ttu-id="608aa-111">付与されている役割に応じて、基本的なライブ応答コマンドまたは高度なライブ応答コマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="608aa-111">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="608aa-112">基本的なコマンドと高度なコマンドの詳細については、「ライブ応答を使用してデバイス上のエンティティを調査 [する」を参照してください](live-response.md)。</span><span class="sxs-lookup"><span data-stu-id="608aa-112">For more information on basic and advanced commands, see [Investigate entities on devices using live response](live-response.md).</span></span>


## <a name="analyze"></a><span data-ttu-id="608aa-113">分析</span><span class="sxs-lookup"><span data-stu-id="608aa-113">analyze</span></span> 

```console
# Analyze the file malware.txt
analyze file c:\Users\user\Desktop\malware.txt
```

```console
# Analyze the process by PID
analyze process 1234
```

## <a name="connections"></a><span data-ttu-id="608aa-114">接続</span><span class="sxs-lookup"><span data-stu-id="608aa-114">connections</span></span>

```console
# List active connections in json format using parameter name
connections -output json
```

```console
# List active connections in json format without parameter name
connections json
```

## <a name="dir"></a><span data-ttu-id="608aa-115">dir</span><span class="sxs-lookup"><span data-stu-id="608aa-115">dir</span></span>

```console
# List files and sub-folders in the current folder
dir
```

```console
# List files and sub-folders in a specific folder
dir C:\Users\user\Desktop\
```

```console
# List files and subfolders in the current folder in json format
dir -output json
```

## <a name="fileinfo"></a><span data-ttu-id="608aa-116">fileinfo</span><span class="sxs-lookup"><span data-stu-id="608aa-116">fileinfo</span></span>

```console
# Display information about a file
fileinfo C:\Windows\notepad.exe
```

## <a name="findfile"></a><span data-ttu-id="608aa-117">findfile</span><span class="sxs-lookup"><span data-stu-id="608aa-117">findfile</span></span>

```console
# Find file by name
findfile test.txt
```

## <a name="getfile"></a><span data-ttu-id="608aa-118">getfile</span><span class="sxs-lookup"><span data-stu-id="608aa-118">getfile</span></span>

```console
# Download a file from a machine
getfile c:\Users\user\Desktop\work.txt
```

```console
# Download a file from a machine, automatically run prerequisite commands
getfile c:\Users\user\Desktop\work.txt -auto
```

>[!NOTE]
>
> <span data-ttu-id="608aa-119">次のファイルの種類 **は、Live** Response 内からこのコマンドを使用してダウンロードできません。</span><span class="sxs-lookup"><span data-stu-id="608aa-119">The following file types **cannot** be downloaded using this command from within Live Response:</span></span>
>
> * [<span data-ttu-id="608aa-120">Reparse ポイント ファイル</span><span class="sxs-lookup"><span data-stu-id="608aa-120">Reparse point files</span></span>](/windows/desktop/fileio/reparse-points/)
> * [<span data-ttu-id="608aa-121">スパース ファイル</span><span class="sxs-lookup"><span data-stu-id="608aa-121">Sparse files</span></span>](/windows/desktop/fileio/sparse-files/)
> * <span data-ttu-id="608aa-122">空のファイル</span><span class="sxs-lookup"><span data-stu-id="608aa-122">Empty files</span></span>
> * <span data-ttu-id="608aa-123">仮想ファイル、またはローカルに完全に存在しないファイル</span><span class="sxs-lookup"><span data-stu-id="608aa-123">Virtual files, or files that are not fully present locally</span></span>
>
> <span data-ttu-id="608aa-124">これらのファイルの種類 **は** [PowerShell でサポートされています](/powershell/scripting/overview?view=powershell-6/?&preserve-view=true)。</span><span class="sxs-lookup"><span data-stu-id="608aa-124">These file types **are** supported by [PowerShell](/powershell/scripting/overview?view=powershell-6/?&preserve-view=true).</span></span>
>
> <span data-ttu-id="608aa-125">Live Response 内からこのコマンドを使用する際に問題が発生した場合は、PowerShell を代わりに使用します。</span><span class="sxs-lookup"><span data-stu-id="608aa-125">Use PowerShell as an alternative, if you have problems using this command from within Live Response.</span></span>

## <a name="processes"></a><span data-ttu-id="608aa-126">processes</span><span class="sxs-lookup"><span data-stu-id="608aa-126">processes</span></span>
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

## <a name="putfile"></a><span data-ttu-id="608aa-127">putfile</span><span class="sxs-lookup"><span data-stu-id="608aa-127">putfile</span></span>

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

## <a name="registry"></a><span data-ttu-id="608aa-128">レジストリ</span><span class="sxs-lookup"><span data-stu-id="608aa-128">registry</span></span>

```console
# Show information about the values in a registry key
registry HKEY_CURRENT_USER\Console
```

```console
# Show information about a specific registry value
registry HKEY_CURRENT_USER\Console\\ScreenBufferSize
```


## <a name="remediate"></a><span data-ttu-id="608aa-129">remediate</span><span class="sxs-lookup"><span data-stu-id="608aa-129">remediate</span></span>

```console
# Remediate file in specific path
remediate file c:\Users\user\Desktop\malware.exe
```

```console
# Remediate process with specific PID
remediate process 7960
```

```console
# See list of all remediated entities
remediate list
```

## <a name="run"></a><span data-ttu-id="608aa-130">run</span><span class="sxs-lookup"><span data-stu-id="608aa-130">run</span></span>

```console
# Run PowerShell script from the library without arguments
run script.ps1
```

```console
# Run PowerShell script from the library with arguments
run get-process-by-name.ps1 -parameters "-processName Registry"
```
>[!NOTE]
>
> <span data-ttu-id="608aa-131">**'** run ' や '**getfile**'などの長時間実行されているコマンドの場合は、コマンドの最後に ' ' 記号を使用して、バックグラウンドでそのアクションを **&** 実行できます。</span><span class="sxs-lookup"><span data-stu-id="608aa-131">For long running commands such as '**run**' or '**getfile**', you may want to use the '**&**' symbol at the end of the command to perform that action in the background.</span></span>
> <span data-ttu-id="608aa-132">これにより、コンピューターの調査を続行し、'**fg**' basic コマンドを使用して実行すると、バックグラウンド コマンドに [戻る可能性があります](live-response.md#basic-commands)。</span><span class="sxs-lookup"><span data-stu-id="608aa-132">This will allow you to continue investigating the machine and return to the background command when done using '**fg**' [basic command](live-response.md#basic-commands).</span></span>
>
## <a name="scheduledtask"></a><span data-ttu-id="608aa-133">scheduledtask</span><span class="sxs-lookup"><span data-stu-id="608aa-133">scheduledtask</span></span>

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


## <a name="undo"></a><span data-ttu-id="608aa-134">元に戻す</span><span class="sxs-lookup"><span data-stu-id="608aa-134">undo</span></span>

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


## <a name="library"></a><span data-ttu-id="608aa-135">ライブラリ</span><span class="sxs-lookup"><span data-stu-id="608aa-135">library</span></span>

```console
# List files in the library
library
```

```console
# Delete a file from the library
library delete script.ps1
```
