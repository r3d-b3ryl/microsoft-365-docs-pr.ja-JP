---
title: 除外を定義する際に避ける必要のある一般的な間違い
description: スキャンの除外を定義する際によくある間違いMicrosoft Defender ウイルス対策避ける。
keywords: 除外、ファイル、拡張子、ファイルの種類、フォルダー名、ファイル名、スキャン
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 06/15/2021
ms.openlocfilehash: f9ca83fcfba4b79898a0fed527e38947a4c230d6
ms.sourcegitcommit: 959c3c3633e40b7b0f5e2c8372409778005a24db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/15/2021
ms.locfileid: "52950133"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a><span data-ttu-id="5dd5d-104">除外を定義する際に避ける必要のある一般的な間違い</span><span class="sxs-lookup"><span data-stu-id="5dd5d-104">Common mistakes to avoid when defining exclusions</span></span>

<span data-ttu-id="5dd5d-105">スキャンしないアイテムの除外リストをMicrosoft Defender ウイルス対策できます。</span><span class="sxs-lookup"><span data-stu-id="5dd5d-105">You can define an exclusion list for items that you don't want Microsoft Defender Antivirus to scan.</span></span> <span data-ttu-id="5dd5d-106">このような除外されたアイテムには、デバイスを脆弱にする脅威が含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5dd5d-106">Such excluded items could contain threats that make your device vulnerable.</span></span> <span data-ttu-id="5dd5d-107">この記事では、除外を定義するときに回避する必要がある一般的な間違いについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5dd5d-107">This article describes some common mistake that you should avoid when defining exclusions.</span></span> 

<span data-ttu-id="5dd5d-108">除外リストを定義する前に、除外[おすすめを参照してください](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)。</span><span class="sxs-lookup"><span data-stu-id="5dd5d-108">Before defining your exclusion lists, see [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions).</span></span>

## <a name="excluding-certain-trusted-items"></a><span data-ttu-id="5dd5d-109">特定の信頼済みアイテムを除外する</span><span class="sxs-lookup"><span data-stu-id="5dd5d-109">Excluding certain trusted items</span></span>

<span data-ttu-id="5dd5d-110">特定のファイル、ファイルの種類、フォルダー、またはプロセスは、悪意のあるものではないと信頼している場合でも、スキャンから除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5dd5d-110">Certain files, file types, folders, or processes should not be excluded from scanning even though you trust them to be not malicious.</span></span> 

<span data-ttu-id="5dd5d-111">次のセクションに記載されているフォルダーの場所、ファイル拡張子、およびプロセスの除外を定義しない。</span><span class="sxs-lookup"><span data-stu-id="5dd5d-111">Do not define exclusions for the folder locations, file extensions, and processes that are listed in the following sections:</span></span>
- <span data-ttu-id="5dd5d-112">フォルダーの場所</span><span class="sxs-lookup"><span data-stu-id="5dd5d-112">Folder locations</span></span>
- <span data-ttu-id="5dd5d-113">ファイル拡張子</span><span class="sxs-lookup"><span data-stu-id="5dd5d-113">File extensions</span></span>
- <span data-ttu-id="5dd5d-114">プロセス</span><span class="sxs-lookup"><span data-stu-id="5dd5d-114">Processes</span></span>

### <a name="folder-locations"></a><span data-ttu-id="5dd5d-115">フォルダーの場所</span><span class="sxs-lookup"><span data-stu-id="5dd5d-115">Folder locations</span></span>

<span data-ttu-id="5dd5d-116">一般に、次のフォルダーの場所に対して除外を定義しない。</span><span class="sxs-lookup"><span data-stu-id="5dd5d-116">In general, do not define exclusions for the following folder locations:</span></span>

`%systemdrive%` 

`C:`

`C:\`

`C:\*`

`%ProgramFiles%\Java`

`C:\Program Files\Java` 

`%ProgramFiles%\Contoso\` 

`C:\Program Files\Contoso\` 

`%ProgramFiles(x86)%\Contoso\` 

`C:\Program Files (x86)\Contoso\`

`C:\Temp`

`C:\Temp\`

`C:\Temp\*`

`C:\Users\`

`C:\Users\*`

<span data-ttu-id="5dd5d-117">`C:\Users\<UserProfileName>\AppData\Local\Temp\`**次の例外に注意してください:SharePoint** でファイル レベルのウイルス対策保護を使用する場合 `C:\Users\ServiceAccount\AppData\Local\Temp` [は除外SharePoint。](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9)</span><span class="sxs-lookup"><span data-stu-id="5dd5d-117">`C:\Users\<UserProfileName>\AppData\Local\Temp\` **Note the following exception for SharePoint**: Do exclude `C:\Users\ServiceAccount\AppData\Local\Temp` when you use [file-level antivirus protection in SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).</span></span>

<span data-ttu-id="5dd5d-118">`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\`**次の例外に注意してください:SharePoint** でファイル レベルのウイルス対策保護を使用する場合 `C:\Users\Default\AppData\Local\Temp` [は除外SharePoint。](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9)</span><span class="sxs-lookup"><span data-stu-id="5dd5d-118">`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\` **Note the following exception for SharePoint**: Do exclude `C:\Users\Default\AppData\Local\Temp` when you use [file-level antivirus protection in SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).</span></span>

`%Windir%\Prefetch`

`C:\Windows\Prefetch`

`C:\Windows\Prefetch\`

`C:\Windows\Prefetch\*`

`%Windir%\System32\Spool`

`C:\Windows\System32\Spool`

`C:\Windows\System32\CatRoot2`
`%Windir%\Temp`

`C:\Windows\Temp`

`C:\Windows\Temp\`

`C:\Windows\Temp\*`

### <a name="file-extensions"></a><span data-ttu-id="5dd5d-119">ファイル拡張子</span><span class="sxs-lookup"><span data-stu-id="5dd5d-119">File extensions</span></span>

<span data-ttu-id="5dd5d-120">一般に、次のファイル拡張子の除外は定義しない。</span><span class="sxs-lookup"><span data-stu-id="5dd5d-120">In general, do not define exclusions for the following file extensions:</span></span>

`.7z`

`.bat`

`.bin`

`.cab`

`.cmd`

`.com` 

`.cpl`

`.dll`

`.exe`

`.fla`

`.gif`

`.gz`

`.hta`

`.inf`

`.java`

`.jar`

`.job`

`.jpeg`

`.jpg`

`.js`

`.ko`

`.ko.gz`

`.msi`

`.ocx`

`.png`

`.ps1`

`.py`

`.rar`

`.reg`

`.scr`

`.sys`

`.tar`

`.tmp`

`.url`

`.vbe`

`.vbs`

`.wsf`

`.zip`

### <a name="processes"></a><span data-ttu-id="5dd5d-121">プロセス</span><span class="sxs-lookup"><span data-stu-id="5dd5d-121">Processes</span></span> 

<span data-ttu-id="5dd5d-122">一般に、次のプロセスの除外を定義しない。</span><span class="sxs-lookup"><span data-stu-id="5dd5d-122">In general, do not define exclusions for the following processes:</span></span>

`AcroRd32.exe`  

`bitsadmin.exe`  

`excel.exe`  

`iexplore.exe`  

`java.exe`  

`outlook.exe`  

`psexec.exe`  

`powerpnt.exe`  

`powershell.exe`  

`schtasks.exe`

`svchost.exe` 

`wmic.exe`  

`winword.exe`  

`wuauclt.exe`  

`addinprocess.exe`  

`addinprocess32.exe`  

`addinutil.exe`  

`bash.exe`  

`bginfo.exe` 

`cdb.exe`  

`csi.exe`  

`dbghost.exe`  

`dbgsvc.exe`  

`dnx.exe`

`dotnet.exe`

`fsi.exe`  

`fsiAnyCpu.exe`  

`kd.exe`  

`ntkd.exe`  

`lxssmanager.dll`  

`msbuild.exe` 

`mshta.exe`  

`ntsd.exe`  

`rcsi.exe`  

`system.management.automation.dll`  

`windbg.exe`

> [!NOTE]
> <span data-ttu-id="5dd5d-123">ファイルの種類 (、など) を除外するか、環境に最新の最新のソフトウェアを適用し、厳密な更新ポリシーを使用して脆弱性を処理する場合に `.gif` `.jpg` `.jpeg` `.png` 選択できます。</span><span class="sxs-lookup"><span data-stu-id="5dd5d-123">You can choose to exclude file types, such as `.gif`, `.jpg`, `.jpeg`, or `.png` if your environment has a modern, up-to-date software with a strict update policy to handle any vulnerabilities.</span></span>

## <a name="using-just-the-file-name-in-the-exclusion-list"></a><span data-ttu-id="5dd5d-124">除外リストでファイル名を使用する</span><span class="sxs-lookup"><span data-stu-id="5dd5d-124">Using just the file name in the exclusion list</span></span>

<span data-ttu-id="5dd5d-125">マルウェアは、信頼できるファイルと同じ名前を持ち、スキャンから除外する場合があります。</span><span class="sxs-lookup"><span data-stu-id="5dd5d-125">A malware may have the same name as that of the file that you trust and want to exclude from scanning.</span></span> <span data-ttu-id="5dd5d-126">したがって、潜在的なマルウェアをスキャンから除外しないようにするには、ファイル名を使用する代わりに、除外するファイルへの完全修飾パスを使用します。</span><span class="sxs-lookup"><span data-stu-id="5dd5d-126">Therefore, to avoid excluding a potential malware from scanning, use a fully qualified path to the file that you want to exclude instead of using just the file name.</span></span> <span data-ttu-id="5dd5d-127">たとえば、スキャンから除外する場合は、ファイルへの完全なパス (など) `Filename.exe` を使用します `C:\program files\contoso\Filename.exe` 。</span><span class="sxs-lookup"><span data-stu-id="5dd5d-127">For example, if you want to exclude `Filename.exe` from scanning, use the complete path to the file, such as `C:\program files\contoso\Filename.exe`.</span></span>

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a><span data-ttu-id="5dd5d-128">複数のサーバー ワークロードに対して 1 つの除外リストを使用する</span><span class="sxs-lookup"><span data-stu-id="5dd5d-128">Using a single exclusion list for multiple server workloads</span></span>

<span data-ttu-id="5dd5d-129">複数のサーバー ワークロードの除外を定義するには、1 つの除外リストを使用しません。</span><span class="sxs-lookup"><span data-stu-id="5dd5d-129">Do not use a single exclusion list to define exclusions for multiple server workloads.</span></span> <span data-ttu-id="5dd5d-130">異なるアプリケーションまたはサービス ワークロードの除外を複数の除外リストに分割します。</span><span class="sxs-lookup"><span data-stu-id="5dd5d-130">Split the exclusions for different application or service workloads into multiple exclusion lists.</span></span> <span data-ttu-id="5dd5d-131">たとえば、IIS Server ワークロードの除外リストは、ユーザーのワークロードの除外リストと異なるSQL Serverがあります。</span><span class="sxs-lookup"><span data-stu-id="5dd5d-131">For example, the exclusion list for your IIS Server workload must be different from the exclusion list for your SQL Server workload.</span></span>

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a><span data-ttu-id="5dd5d-132">ファイル名とフォルダー パスまたは拡張子の除外リストで不適切な環境変数をワイルドカードとして使用する</span><span class="sxs-lookup"><span data-stu-id="5dd5d-132">Using incorrect environment variables as wildcards in the file name and folder path or extension exclusion lists</span></span>

<span data-ttu-id="5dd5d-133">Microsoft Defender ウイルス対策サービスは LocalSystem アカウントを使用してシステム コンテキストで実行されます。つまり、ユーザー環境変数ではなく、システム環境変数から情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="5dd5d-133">Microsoft Defender Antivirus Service runs in system context using the LocalSystem account, which means it gets information from the system environment variable, and not from the user environment variable.</span></span> <span data-ttu-id="5dd5d-134">除外リストでのワイルドカードとしての環境変数の使用は、システム変数と、NT AUTHORITY\SYSTEM アカウントとして実行されているプロセスに適用される変数に制限されます。</span><span class="sxs-lookup"><span data-stu-id="5dd5d-134">Use of environment variables as a wildcard in exclusion lists is limited to system variables and those applicable to processes running as an NT AUTHORITY\SYSTEM account.</span></span> <span data-ttu-id="5dd5d-135">したがって、ユーザーの環境変数をワイルドカードとして使用しない場合は、フォルダー Microsoft Defender ウイルス対策除外を追加してください。</span><span class="sxs-lookup"><span data-stu-id="5dd5d-135">Therefore, do not use user environment variables as wildcards when adding Microsoft Defender Antivirus folder and process exclusions.</span></span> <span data-ttu-id="5dd5d-136">システム環境変数の完全 [な一覧については、「System 環境変数](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5dd5d-136">See the table under [System environment variables](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) for a complete list of system environment variables.</span></span>

<span data-ttu-id="5dd5d-137">除外 [リストでワイルドカードを使用する](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) 方法については、「ファイル名とフォルダー パスまたは拡張子の除外リストでワイルドカードを使用する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5dd5d-137">See [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) for information on how to use wildcards in exclusion lists.</span></span>

