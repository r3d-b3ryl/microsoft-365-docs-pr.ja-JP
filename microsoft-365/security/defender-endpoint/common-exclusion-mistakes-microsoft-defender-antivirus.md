---
title: 除外を定義するときに回避する一般的な間違い
description: Microsoft Defender ウイルス対策スキャンの除外を定義する場合は、一般的な間違いを避ける必要があります。
keywords: 除外、ファイル、拡張子、ファイルの種類、フォルダー名、ファイル名、スキャン
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: d14e37c8f3cfdfe8d88bfd4e255a431fbb8d6d41
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691081"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a><span data-ttu-id="fbd4d-104">除外を定義するときに回避する一般的な間違い</span><span class="sxs-lookup"><span data-stu-id="fbd4d-104">Common mistakes to avoid when defining exclusions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fbd4d-105">Microsoft Defender ウイルス対策をスキャンしないアイテムの除外リストを定義できます。</span><span class="sxs-lookup"><span data-stu-id="fbd4d-105">You can define an exclusion list for items that you don't want Microsoft Defender Antivirus to scan.</span></span> <span data-ttu-id="fbd4d-106">このような除外されたアイテムには、デバイスを脆弱にする脅威が含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fbd4d-106">Such excluded items could contain threats that make your device vulnerable.</span></span> 

<span data-ttu-id="fbd4d-107">この記事では、除外を定義するときに回避する必要がある一般的な間違いについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fbd4d-107">This article describes some common mistake that you should avoid when defining exclusions.</span></span> 

<span data-ttu-id="fbd4d-108">除外リストを定義する前に、「 [除外を定義するための推奨事項」を参照してください](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)。</span><span class="sxs-lookup"><span data-stu-id="fbd4d-108">Before defining your exclusion lists, see [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions).</span></span>

## <a name="excluding-certain-trusted-items"></a><span data-ttu-id="fbd4d-109">特定の信頼済みアイテムを除外する</span><span class="sxs-lookup"><span data-stu-id="fbd4d-109">Excluding certain trusted items</span></span>

<span data-ttu-id="fbd4d-110">特定のファイル、ファイルの種類、フォルダー、またはプロセスは、悪意のあるものではないと信頼している場合でも、スキャンから除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbd4d-110">Certain files, file types, folders, or processes should not be excluded from scanning even though you trust them to be not malicious.</span></span> 

<span data-ttu-id="fbd4d-111">次の表に示すフォルダーの場所、ファイル拡張子、およびプロセスの除外を定義しない。</span><span class="sxs-lookup"><span data-stu-id="fbd4d-111">Do not define exclusions for the folder locations, file extensions, and processes that are listed in the following table:</span></span>

| <span data-ttu-id="fbd4d-112">フォルダーの場所</span><span class="sxs-lookup"><span data-stu-id="fbd4d-112">Folder locations</span></span> | <span data-ttu-id="fbd4d-113">ファイル拡張子</span><span class="sxs-lookup"><span data-stu-id="fbd4d-113">File extensions</span></span> | <span data-ttu-id="fbd4d-114">プロセス</span><span class="sxs-lookup"><span data-stu-id="fbd4d-114">Processes</span></span> |
|:--|:--|:--|
| `%systemdrive%` <br/> `C:`<br/> `C:\` <br/> `C:\*` <br/> `%ProgramFiles%\Java` <br/> `C:\Program Files\Java` <br/> `%ProgramFiles%\Contoso\` <br/> `C:\Program Files\Contoso\` <br/> `%ProgramFiles(x86)%\Contoso\` <br/> `C:\Program Files (x86)\Contoso\` <br/> `C:\Temp` <br/> `C:\Temp\` <br/> `C:\Temp\*` <br/> `C:\Users\` <br/> `C:\Users\*` <br/> `C:\Users\<UserProfileName>\AppData\Local\Temp\` <br/> `C:\Users\<UserProfileName>\AppData\LocalLow\Temp\` <br/> `C:\Users\<UserProfileName>\AppData\Roaming\Temp\` <br/> `%Windir%\Prefetch` <br/> `C:\Windows\Prefetch` <br/> `C:\Windows\Prefetch\` <br/> `C:\Windows\Prefetch\*` <br/> `%Windir%\System32\Spool` <br/> `C:\Windows\System32\Spool` <br/> `C:\Windows\System32\CatRoot2` <br/> `%Windir%\Temp` <br/> `C:\Windows\Temp` <br/> `C:\Windows\Temp\` <br/> `C:\Windows\Temp\*` | `.7z` <br/> `.bat` <br/> `.bin` <br/> `.cab` <br/> `.cmd` <br/> `.com` <br/> `.cpl` <br/> `.dll` <br/> `.exe` <br/> `.fla` <br/> `.gif` <br/> `.gz` <br/> `.hta` <br/> `.inf` <br/> `.java` <br/> `.jar` <br/> `.job` <br/> `.jpeg` <br/> `.jpg` <br/> `.js` <br/> `.ko` <br/> `.ko.gz` <br/> `.msi` <br/> `.ocx` <br/> `.png` <br/> `.ps1` <br/> `.py` <br/> `.rar` <br/> `.reg` <br/> `.scr` <br/> `.sys` <br/> `.tar` <br/> `.tmp` <br/> `.url` <br/> `.vbe` <br/> `.vbs` <br/> `.wsf` <br/> `.zip` | `AcroRd32.exe` <br/> `bitsadmin.exe` <br/> `excel.exe` <br/> `iexplore.exe` <br/> `java.exe` <br/> `outlook.exe` <br/> `psexec.exe` <br/> `powerpnt.exe` <br/> `powershell.exe` <br/> `schtasks.exe`  <br/> `svchost.exe` <br/>`wmic.exe` <br/> `winword.exe` <br/> `wuauclt.exe` <br/> `addinprocess.exe` <br/> `addinprocess32.exe` <br/> `addinutil.exe` <br/> `bash.exe` <br/> <span data-ttu-id="fbd4d-115">`bginfo.exe`[1]</span><span class="sxs-lookup"><span data-stu-id="fbd4d-115">`bginfo.exe`[1]</span></span> <br/>`cdb.exe` <br/> `csi.exe` <br/> `dbghost.exe` <br/> `dbgsvc.exe` <br/> `dnx.exe` <br/> `fsi.exe` <br/> `fsiAnyCpu.exe` <br/> `kd.exe` <br/> `ntkd.exe` <br/> `lxssmanager.dll` <br/> <span data-ttu-id="fbd4d-116">`msbuild.exe`[2]</span><span class="sxs-lookup"><span data-stu-id="fbd4d-116">`msbuild.exe`[2]</span></span> <br/> `mshta.exe` <br/> `ntsd.exe` <br/> `rcsi.exe` <br/> `system.management.automation.dll` <br/> `windbg.exe` |

> [!NOTE]
> <span data-ttu-id="fbd4d-117">ファイルの種類 (、など) を除外するか、環境に最新の最新のソフトウェアを適用し、厳密な更新ポリシーを使用して脆弱性を処理する場合に `.gif` `.jpg` `.jpeg` `.png` 選択できます。</span><span class="sxs-lookup"><span data-stu-id="fbd4d-117">You can choose to exclude file types, such as `.gif`, `.jpg`, `.jpeg`, or `.png` if your environment has a modern, up-to-date software with a strict update policy to handle any vulnerabilities.</span></span>

## <a name="using-just-the-file-name-in-the-exclusion-list"></a><span data-ttu-id="fbd4d-118">除外リストでファイル名を使用する</span><span class="sxs-lookup"><span data-stu-id="fbd4d-118">Using just the file name in the exclusion list</span></span>

<span data-ttu-id="fbd4d-119">マルウェアは、信頼できるファイルと同じ名前を持ち、スキャンから除外する場合があります。</span><span class="sxs-lookup"><span data-stu-id="fbd4d-119">A malware may have the same name as that of the file that you trust and want to exclude from scanning.</span></span> <span data-ttu-id="fbd4d-120">したがって、潜在的なマルウェアをスキャンから除外しないようにするには、ファイル名を使用する代わりに、除外するファイルへの完全修飾パスを使用します。</span><span class="sxs-lookup"><span data-stu-id="fbd4d-120">Therefore, to avoid excluding a potential malware from scanning, use a fully qualified path to the file that you want to exclude instead of using just the file name.</span></span> <span data-ttu-id="fbd4d-121">たとえば、スキャンから除外する場合は、ファイルへの完全なパス (など) `Filename.exe` を使用します `C:\program files\contoso\Filename.exe` 。</span><span class="sxs-lookup"><span data-stu-id="fbd4d-121">For example, if you want to exclude `Filename.exe` from scanning, use the complete path to the file, such as `C:\program files\contoso\Filename.exe`.</span></span>

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a><span data-ttu-id="fbd4d-122">複数のサーバー ワークロードに対して 1 つの除外リストを使用する</span><span class="sxs-lookup"><span data-stu-id="fbd4d-122">Using a single exclusion list for multiple server workloads</span></span>

<span data-ttu-id="fbd4d-123">複数のサーバー ワークロードの除外を定義するには、1 つの除外リストを使用しません。</span><span class="sxs-lookup"><span data-stu-id="fbd4d-123">Do not use a single exclusion list to define exclusions for multiple server workloads.</span></span> <span data-ttu-id="fbd4d-124">異なるアプリケーションまたはサービス ワークロードの除外を複数の除外リストに分割します。</span><span class="sxs-lookup"><span data-stu-id="fbd4d-124">Split the exclusions for different application or service workloads into multiple exclusion lists.</span></span> <span data-ttu-id="fbd4d-125">たとえば、IIS Server ワークロードの除外リストは、ユーザーのワークロードの除外リストと異なるSQL Serverがあります。</span><span class="sxs-lookup"><span data-stu-id="fbd4d-125">For example, the exclusion list for your IIS Server workload must be different from the exclusion list for your SQL Server workload.</span></span>

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a><span data-ttu-id="fbd4d-126">ファイル名とフォルダー パスまたは拡張子の除外リストで不適切な環境変数をワイルドカードとして使用する</span><span class="sxs-lookup"><span data-stu-id="fbd4d-126">Using incorrect environment variables as wildcards in the file name and folder path or extension exclusion lists</span></span>

<span data-ttu-id="fbd4d-127">Microsoft Defender ウイルス対策サービスは、LocalSystem アカウントを使用してシステム コンテキストで実行されます。つまり、ユーザー環境変数ではなく、システム環境変数から情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="fbd4d-127">Microsoft Defender Antivirus Service runs in system context using the LocalSystem account, which means it gets information from the system environment variable, and not from the user environment variable.</span></span> <span data-ttu-id="fbd4d-128">除外リストでのワイルドカードとしての環境変数の使用は、システム変数と、NT AUTHORITY\SYSTEM アカウントとして実行されているプロセスに適用される変数に制限されます。</span><span class="sxs-lookup"><span data-stu-id="fbd4d-128">Use of environment variables as a wildcard in exclusion lists is limited to system variables and those applicable to processes running as an NT AUTHORITY\SYSTEM account.</span></span> <span data-ttu-id="fbd4d-129">したがって、Microsoft Defender ウイルス対策フォルダーとプロセスの除外を追加する場合は、ユーザー環境変数をワイルドカードとして使用しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbd4d-129">Therefore, do not use user environment variables as wildcards when adding Microsoft Defender Antivirus folder and process exclusions.</span></span> <span data-ttu-id="fbd4d-130">システム環境変数の完全 [な一覧については、「System 環境変数](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbd4d-130">See the table under [System environment variables](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) for a complete list of system environment variables.</span></span>

<span data-ttu-id="fbd4d-131">除外 [リストでワイルドカードを使用する](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) 方法については、「ファイル名とフォルダー パスまたは拡張子の除外リストでワイルドカードを使用する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbd4d-131">See [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) for information on how to use wildcards in exclusion lists.</span></span>

## <a name="related-articles"></a><span data-ttu-id="fbd4d-132">関連記事</span><span class="sxs-lookup"><span data-stu-id="fbd4d-132">Related articles</span></span>

- [<span data-ttu-id="fbd4d-133">Microsoft Defender ウイルス対策スキャンで除外を構成および検証する</span><span class="sxs-lookup"><span data-stu-id="fbd4d-133">Configure and validate exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="fbd4d-134">ファイル拡張子とフォルダーの場所に基づいて除外を構成および検証する</span><span class="sxs-lookup"><span data-stu-id="fbd4d-134">Configure and validate exclusions based on file extension and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="fbd4d-135">プロセスによって開いたファイルの除外を構成および検証する</span><span class="sxs-lookup"><span data-stu-id="fbd4d-135">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="fbd4d-136">Windows Server で Microsoft Defender ウイルス対策の除外を構成する</span><span class="sxs-lookup"><span data-stu-id="fbd4d-136">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
