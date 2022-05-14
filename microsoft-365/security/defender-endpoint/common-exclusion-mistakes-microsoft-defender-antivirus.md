---
title: 除外を定義する際に避ける必要のある一般的な間違い
description: Microsoft Defender ウイルス対策 スキャンの除外を定義するときによくある間違いを回避します。
keywords: 除外、ファイル、拡張子、ファイルの種類、フォルダー名、ファイル名、スキャン
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
ms.topic: article
ms.date: 10/19/2021
ms.collection: M365-security-compliance
ms.openlocfilehash: 23c079f8f845e6116bc39b9edb3fb186883ef576
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2022
ms.locfileid: "65418228"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a>除外を定義する際に避ける必要のある一般的な間違い

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策 

**プラットフォーム**
- Windows
- macOS
- Linux

スキャンするMicrosoft Defender ウイルス対策しないアイテムの除外リストを定義できます。 このような除外されたアイテムには、デバイスを脆弱にする脅威が含まれている可能性があります。 この記事では、除外を定義するときに回避する必要がある一般的な間違いについて説明します。

除外リストを定義する前に、除外を[定義するためのおすすめを](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)参照してください。

## <a name="excluding-certain-trusted-items"></a>特定の信頼済みアイテムを除外する

特定のファイル、ファイルの種類、フォルダー、またはプロセスは、悪意がないと信頼している場合でも、スキャンから除外しないでください。

次のセクションに記載されているフォルダーの場所、ファイル拡張子、およびプロセスに対して除外を定義しないでください。
- フォルダーの場所
- ファイル拡張子
- プロセス

### <a name="folder-locations"></a>フォルダーの場所

一般に、次のフォルダーの場所に対して除外を定義しないでください。

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

`C:\Users\<UserProfileName>\AppData\Local\Temp\`**SharePointの例外に注意** してください:[SharePointでファイル レベルのウイルス対策保護](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9)を使用する場合は除外`C:\Users\ServiceAccount\AppData\Local\Temp`しないでください。

`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\`**SharePointの例外に注意** してください:[SharePointでファイル レベルのウイルス対策保護](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9)を使用する場合は除外`C:\Users\Default\AppData\Local\Temp`しないでください。

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

#### <a name="linux-and-macos-platforms"></a>Linux および macOS プラットフォーム

`/`

`/bin`

`/sbin`

`/usr/lib`


### <a name="file-extensions"></a>ファイル拡張子

一般に、次のファイル拡張子の除外は定義しないでください。

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

一般に、次のプロセスに対して除外を定義しないでください。

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

#### <a name="linux-and-macos-platforms"></a>Linux および macOS プラットフォーム

`bash`

`sh`

`python` と `python3`

`java`

`zsh`

> [!NOTE]
> 、などのファイルの種類を除外するか、`.gif``.jpg``.jpeg`環境`.png`に最新の最新のソフトウェアがあり、脆弱性を処理するための厳格な更新ポリシーを持つ場合は、除外することができます。

## <a name="using-just-the-file-name-in-the-exclusion-list"></a>除外リスト内のファイル名のみを使用する

マルウェアの名前は、信頼できるファイルの名前と同じで、スキャンから除外したい場合があります。 そのため、潜在的なマルウェアをスキャンから除外しないようにするには、ファイル名だけを使用するのではなく、除外するファイルへの完全修飾パスを使用します。 たとえば、スキャンから除外 `Filename.exe` する場合は、次のような `C:\program files\contoso\Filename.exe`ファイルへの完全なパスを使用します。

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a>複数のサーバー ワークロードに対して 1 つの除外リストを使用する

1 つの除外リストを使用して、複数のサーバー ワークロードの除外を定義しないでください。 異なるアプリケーションまたはサービスワークロードの除外を複数の除外リストに分割します。 たとえば、IIS Server ワークロードの除外リストは、SQL Server ワークロードの除外リストと異なる必要があります。

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>ファイル名とフォルダーパスまたは拡張子の除外リストで不適切な環境変数をワイルドカードとして使用する

Microsoft Defender ウイルス対策 サービスは、LocalSystem アカウントを使用してシステム コンテキストで実行されます。つまり、ユーザー環境変数からではなく、システム環境変数から情報を取得します。 除外リストでのワイルドカードとしての環境変数の使用は、システム変数と、NT AUTHORITY\SYSTEM アカウントとして実行されているプロセスに適用される変数に限定されます。 そのため、フォルダーとプロセスの除外を追加するときに、ワイルドカードとしてユーザー環境変数Microsoft Defender ウイルス対策使用しないでください。 システム環境変数の完全な一覧については、 [システム環境変数](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) の下の表を参照してください。

除外 [リストでワイルドカードを使用する方法については、「ファイル名とフォルダーパスまたは拡張子の除外リストでワイルドカード](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) を使用する」を参照してください。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)
