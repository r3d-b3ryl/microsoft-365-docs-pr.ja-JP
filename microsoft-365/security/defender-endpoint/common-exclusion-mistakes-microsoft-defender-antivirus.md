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
ms.openlocfilehash: 5fc496fd0d40d5dd172fb45e8ce6b8d23ebab6da
ms.sourcegitcommit: ea4bc3b005d86b029700e56015a47b8cc6dca2a1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2021
ms.locfileid: "58509991"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a>除外を定義する際に避ける必要のある一般的な間違い

スキャンしないアイテムの除外リストをMicrosoft Defender ウイルス対策できます。 このような除外されたアイテムには、デバイスを脆弱にする脅威が含まれている可能性があります。 この記事では、除外を定義するときに回避する必要がある一般的な間違いについて説明します。

除外リストを定義する前に、「 [除外を定義するための推奨事項」を参照してください](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)。

## <a name="excluding-certain-trusted-items"></a>特定の信頼済みアイテムを除外する

特定のファイル、ファイルの種類、フォルダー、またはプロセスは、悪意のあるものではないと信頼している場合でも、スキャンから除外する必要があります。

次のセクションに記載されているフォルダーの場所、ファイル拡張子、およびプロセスの除外を定義しない。
- フォルダーの場所
- ファイル拡張子
- プロセス

### <a name="folder-locations"></a>フォルダーの場所

一般に、次のフォルダーの場所に対して除外を定義しない。

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

`C:\Users\<UserProfileName>\AppData\Local\Temp\`**次の例外に注意してください:SharePoint** でファイル レベルのウイルス対策保護を使用する場合 `C:\Users\ServiceAccount\AppData\Local\Temp` [は除外SharePoint。](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9)

`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\`**次の例外に注意してください:SharePoint** でファイル レベルのウイルス対策保護を使用する場合 `C:\Users\Default\AppData\Local\Temp` [は除外SharePoint。](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9)

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

### <a name="file-extensions"></a>ファイル拡張子

一般に、次のファイル拡張子の除外は定義しない。

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

### <a name="processes"></a>プロセス

一般に、次のプロセスの除外を定義しない。

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
> ファイルの種類 (、など) を除外するか、環境に最新の最新のソフトウェアを適用し、厳密な更新ポリシーを使用して脆弱性を処理する場合に `.gif` `.jpg` `.jpeg` `.png` 選択できます。

## <a name="using-just-the-file-name-in-the-exclusion-list"></a>除外リストでファイル名を使用する

マルウェアは、信頼できるファイルと同じ名前を持ち、スキャンから除外する場合があります。 したがって、潜在的なマルウェアをスキャンから除外しないようにするには、ファイル名を使用する代わりに、除外するファイルへの完全修飾パスを使用します。 たとえば、スキャンから除外する場合は、ファイルへの完全なパス (など) `Filename.exe` を使用します `C:\program files\contoso\Filename.exe` 。

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a>複数のサーバー ワークロードに対して 1 つの除外リストを使用する

複数のサーバー ワークロードの除外を定義するには、1 つの除外リストを使用しません。 異なるアプリケーションまたはサービス ワークロードの除外を複数の除外リストに分割します。 たとえば、IIS Server ワークロードの除外リストは、ユーザーのワークロードの除外リストと異なるSQL Serverがあります。

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>ファイル名とフォルダー パスまたは拡張子の除外リストで不適切な環境変数をワイルドカードとして使用する

Microsoft Defender ウイルス対策サービスは LocalSystem アカウントを使用してシステム コンテキストで実行されます。つまり、ユーザー環境変数ではなく、システム環境変数から情報を取得します。 除外リストでのワイルドカードとしての環境変数の使用は、システム変数と、NT AUTHORITY\SYSTEM アカウントとして実行されているプロセスに適用される変数に制限されます。 したがって、ユーザーの環境変数をワイルドカードとして使用しない場合は、フォルダー Microsoft Defender ウイルス対策除外を追加してください。 システム環境変数の完全 [な一覧については、「System 環境変数](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) 」の表を参照してください。

除外 [リストでワイルドカードを使用する](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) 方法については、「ファイル名とフォルダー パスまたは拡張子の除外リストでワイルドカードを使用する」を参照してください。
