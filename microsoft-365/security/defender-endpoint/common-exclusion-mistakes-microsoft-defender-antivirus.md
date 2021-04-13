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
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a>除外を定義するときに回避する一般的な間違い

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

Microsoft Defender ウイルス対策をスキャンしないアイテムの除外リストを定義できます。 このような除外されたアイテムには、デバイスを脆弱にする脅威が含まれている可能性があります。 

この記事では、除外を定義するときに回避する必要がある一般的な間違いについて説明します。 

除外リストを定義する前に、「 [除外を定義するための推奨事項」を参照してください](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)。

## <a name="excluding-certain-trusted-items"></a>特定の信頼済みアイテムを除外する

特定のファイル、ファイルの種類、フォルダー、またはプロセスは、悪意のあるものではないと信頼している場合でも、スキャンから除外する必要があります。 

次の表に示すフォルダーの場所、ファイル拡張子、およびプロセスの除外を定義しない。

| フォルダーの場所 | ファイル拡張子 | プロセス |
|:--|:--|:--|
| `%systemdrive%` <br/> `C:`<br/> `C:\` <br/> `C:\*` <br/> `%ProgramFiles%\Java` <br/> `C:\Program Files\Java` <br/> `%ProgramFiles%\Contoso\` <br/> `C:\Program Files\Contoso\` <br/> `%ProgramFiles(x86)%\Contoso\` <br/> `C:\Program Files (x86)\Contoso\` <br/> `C:\Temp` <br/> `C:\Temp\` <br/> `C:\Temp\*` <br/> `C:\Users\` <br/> `C:\Users\*` <br/> `C:\Users\<UserProfileName>\AppData\Local\Temp\` <br/> `C:\Users\<UserProfileName>\AppData\LocalLow\Temp\` <br/> `C:\Users\<UserProfileName>\AppData\Roaming\Temp\` <br/> `%Windir%\Prefetch` <br/> `C:\Windows\Prefetch` <br/> `C:\Windows\Prefetch\` <br/> `C:\Windows\Prefetch\*` <br/> `%Windir%\System32\Spool` <br/> `C:\Windows\System32\Spool` <br/> `C:\Windows\System32\CatRoot2` <br/> `%Windir%\Temp` <br/> `C:\Windows\Temp` <br/> `C:\Windows\Temp\` <br/> `C:\Windows\Temp\*` | `.7z` <br/> `.bat` <br/> `.bin` <br/> `.cab` <br/> `.cmd` <br/> `.com` <br/> `.cpl` <br/> `.dll` <br/> `.exe` <br/> `.fla` <br/> `.gif` <br/> `.gz` <br/> `.hta` <br/> `.inf` <br/> `.java` <br/> `.jar` <br/> `.job` <br/> `.jpeg` <br/> `.jpg` <br/> `.js` <br/> `.ko` <br/> `.ko.gz` <br/> `.msi` <br/> `.ocx` <br/> `.png` <br/> `.ps1` <br/> `.py` <br/> `.rar` <br/> `.reg` <br/> `.scr` <br/> `.sys` <br/> `.tar` <br/> `.tmp` <br/> `.url` <br/> `.vbe` <br/> `.vbs` <br/> `.wsf` <br/> `.zip` | `AcroRd32.exe` <br/> `bitsadmin.exe` <br/> `excel.exe` <br/> `iexplore.exe` <br/> `java.exe` <br/> `outlook.exe` <br/> `psexec.exe` <br/> `powerpnt.exe` <br/> `powershell.exe` <br/> `schtasks.exe`  <br/> `svchost.exe` <br/>`wmic.exe` <br/> `winword.exe` <br/> `wuauclt.exe` <br/> `addinprocess.exe` <br/> `addinprocess32.exe` <br/> `addinutil.exe` <br/> `bash.exe` <br/> `bginfo.exe`[1] <br/>`cdb.exe` <br/> `csi.exe` <br/> `dbghost.exe` <br/> `dbgsvc.exe` <br/> `dnx.exe` <br/> `fsi.exe` <br/> `fsiAnyCpu.exe` <br/> `kd.exe` <br/> `ntkd.exe` <br/> `lxssmanager.dll` <br/> `msbuild.exe`[2] <br/> `mshta.exe` <br/> `ntsd.exe` <br/> `rcsi.exe` <br/> `system.management.automation.dll` <br/> `windbg.exe` |

> [!NOTE]
> ファイルの種類 (、など) を除外するか、環境に最新の最新のソフトウェアを適用し、厳密な更新ポリシーを使用して脆弱性を処理する場合に `.gif` `.jpg` `.jpeg` `.png` 選択できます。

## <a name="using-just-the-file-name-in-the-exclusion-list"></a>除外リストでファイル名を使用する

マルウェアは、信頼できるファイルと同じ名前を持ち、スキャンから除外する場合があります。 したがって、潜在的なマルウェアをスキャンから除外しないようにするには、ファイル名を使用する代わりに、除外するファイルへの完全修飾パスを使用します。 たとえば、スキャンから除外する場合は、ファイルへの完全なパス (など) `Filename.exe` を使用します `C:\program files\contoso\Filename.exe` 。

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a>複数のサーバー ワークロードに対して 1 つの除外リストを使用する

複数のサーバー ワークロードの除外を定義するには、1 つの除外リストを使用しません。 異なるアプリケーションまたはサービス ワークロードの除外を複数の除外リストに分割します。 たとえば、IIS Server ワークロードの除外リストは、ユーザーのワークロードの除外リストと異なるSQL Serverがあります。

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>ファイル名とフォルダー パスまたは拡張子の除外リストで不適切な環境変数をワイルドカードとして使用する

Microsoft Defender ウイルス対策サービスは、LocalSystem アカウントを使用してシステム コンテキストで実行されます。つまり、ユーザー環境変数ではなく、システム環境変数から情報を取得します。 除外リストでのワイルドカードとしての環境変数の使用は、システム変数と、NT AUTHORITY\SYSTEM アカウントとして実行されているプロセスに適用される変数に制限されます。 したがって、Microsoft Defender ウイルス対策フォルダーとプロセスの除外を追加する場合は、ユーザー環境変数をワイルドカードとして使用しない必要があります。 システム環境変数の完全 [な一覧については、「System 環境変数](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) 」の表を参照してください。

除外 [リストでワイルドカードを使用する](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) 方法については、「ファイル名とフォルダー パスまたは拡張子の除外リストでワイルドカードを使用する」を参照してください。

## <a name="related-articles"></a>関連記事

- [Microsoft Defender ウイルス対策スキャンで除外を構成および検証する](configure-exclusions-microsoft-defender-antivirus.md)
- [ファイル拡張子とフォルダーの場所に基づいて除外を構成および検証する](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [プロセスによって開いたファイルの除外を構成および検証する](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [Windows Server で Microsoft Defender ウイルス対策の除外を構成する](configure-server-exclusions-microsoft-defender-antivirus.md)
