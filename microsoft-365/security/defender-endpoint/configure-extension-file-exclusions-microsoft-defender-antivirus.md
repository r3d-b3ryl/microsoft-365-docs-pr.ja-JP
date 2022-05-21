---
title: 拡張機能、名前、または場所に基づいて除外を構成して検証する
description: ファイル拡張子、ファイル名、または場所に基づいて、Microsoft Defender ウイルス対策 スキャンからファイルを除外します。
keywords: 除外、ファイル、拡張子、ファイルの種類、フォルダー名、ファイル名、スキャン
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.collection: M365-security-compliance
ms.openlocfilehash: 864d67aeaa84713b1b2126b017fadacd0e43dc7a
ms.sourcegitcommit: 349f0f54b0397cdd7d8fbb9ef07f1b6654a32d6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2022
ms.locfileid: "65623001"
---
# <a name="configure-and-validate-exclusions-based-on-file-extension-and-folder-location"></a>ファイル拡張子とフォルダーの場所に基づいて除外を構成および検証する

**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

[スケジュールされたスキャン](schedule-antivirus-scans.md)、[オンデマンド](run-scan-microsoft-defender-antivirus.md) スキャン、[および常時オンのリアルタイム保護と監視](configure-real-time-protection-microsoft-defender-antivirus.md)に適用されるMicrosoft Defender ウイルス対策の除外を定義できます。 **通常、除外を適用する必要はありません**。 除外を適用する必要がある場合は、さまざまな種類から選択できます。

- ファイル拡張子とフォルダーの場所に基づく除外 (この記事で説明)
- [プロセスによって開かれるファイルの除外](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

> [!IMPORTANT]
> Microsoft Defender ウイルス対策除外は、[攻撃面縮小 (ASR) ルール](/microsoft-365/security/defender-endpoint/attack-surface-reduction)や[フォルダー アクセスの制御](/microsoft-365/security/defender-endpoint/controlled-folders)など、他のMicrosoft Defender for Endpoint機能には適用されません。 この記事で説明する方法を使用して除外したファイルは、引き続きEDRアラートやその他の検出をトリガーできます。
> ファイルを広範に除外するには、それらをMicrosoft Defender for Endpoint[カスタム インジケーター](/microsoft-365/security/defender-endpoint/manage-indicators)に追加します。

## <a name="before-you-begin"></a>開始する前に

[除外リストを定義する前に、除外を定義する](configure-exclusions-microsoft-defender-antivirus.md)おすすめを参照してください。

## <a name="exclusion-lists"></a>除外リスト

Microsoft Defender ウイルス対策 スキャンから特定のファイルを除外するには、除外リストを変更します。 Microsoft Defender ウイルス対策には、既知のオペレーティング システムの動作や一般的な管理ファイル (エンタープライズ管理、データベース管理、その他のエンタープライズ シナリオや状況で使用されるものなど) に基づく多くの自動除外が含まれます。

> [!NOTE]
> 不要と思われるアプリ (PUA) の検出にも除外が適用されます。
>
> 自動除外は、Windows Server 2016 以降にのみ適用されます。 これらの除外は、Windows セキュリティ アプリおよび PowerShell では表示されません。

次の表に、ファイル拡張子とフォルダーの場所に基づく除外の例をいくつか示します。

|除外|例|除外リスト|
|---|---|---|
|特定の拡張子を持つ任意のファイル|指定された拡張子を持つすべてのファイル(コンピューター上の任意の場所)。 <p> 有効な構文: `.test` と `test`|拡張機能の除外|
|特定のフォルダー内の任意のファイル|フォルダー内 `c:\test\sample` のすべてのファイル|ファイルとフォルダーの除外|
|特定のフォルダー内の特定のファイル|ファイル `c:\sample\sample.test` のみ|ファイルとフォルダーの除外|
|特定のプロセス|実行可能ファイル `c:\test\process.exe`|ファイルとフォルダーの除外|

## <a name="characteristics-of-exclusion-lists"></a>除外リストの特性

- フォルダーの除外は、サブフォルダーが再解析ポイントでない限り、そのフォルダーの下のすべてのファイルとフォルダーに適用されます。 再解析ポイントサブフォルダーは個別に除外する必要があります。
- ファイル拡張子は、パスまたはフォルダーが定義されていない場合、定義された拡張子を持つ任意のファイル名に適用されます。

## <a name="important-notes-about-exclusions-based-on-file-extensions-and-folder-locations"></a>ファイル拡張子とフォルダーの場所に基づく除外に関する重要な注意事項

- アスタリスク (\*) などのワイルドカードを使用すると、除外規則の解釈方法が変更されます。 ワイルドカードの動作に関する重要な情報については、「 [ファイル名とフォルダーパスまたは拡張子の除外リストでワイルドカードを使用](#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) する」セクションを参照してください。

- マップされたネットワーク ドライブを除外しないでください。 実際のネットワーク パスを指定します。

- Microsoft Defender ウイルス対策 サービスの開始後に作成され、除外リストに追加されたポイントを再解析するフォルダーは含まれません。 新しい再解析ポイントが有効な除外ターゲットとして認識されるように (Windowsを再起動して) サービスを再起動します。

- 除外は、 [スケジュールされたスキャン](scheduled-catch-up-scans-microsoft-defender-antivirus.md)、 [オンデマンド スキャン](run-scan-microsoft-defender-antivirus.md)、 [リアルタイム保護](configure-real-time-protection-microsoft-defender-antivirus.md)に適用されますが、Defender for Endpoint には適用されません。 Defender for Endpoint 全体で除外を定義するには、 [カスタム インジケーターを使用します](manage-indicators.md)。

- 既定では、リストに対して行われたローカル変更 (管理者特権を持つユーザー(PowerShell と WMI で行われた変更を含む) は、グループ ポリシー、Configuration Manager、またはIntuneによって定義 (および展開) されたリストとマージされます。 競合が発生した場合は、グループ ポリシー リストが優先されます。 さらに、グループ ポリシーで行われた除外リストの変更は[、Windows セキュリティ アプリ](microsoft-defender-security-center-antivirus.md)に表示されます。

- ローカルの変更がマネージド デプロイ設定をオーバーライドできるようにするには、 [ローカルおよびグローバルに定義された除外リストをマージする方法を構成](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists)します。

## <a name="configure-the-list-of-exclusions-based-on-folder-name-or-file-extension"></a>フォルダー名またはファイル拡張子に基づいて除外の一覧を構成する

Microsoft Defender ウイルス対策の除外を定義するには、いくつかの方法から選択できます。

### <a name="use-intune-to-configure-file-name-folder-or-file-extension-exclusions"></a>Intuneを使用して、ファイル名、フォルダー、またはファイル拡張子の除外を構成する

次の記事をご覧ください。

- [Microsoft Intune でデバイスの制限設定を構成する](/intune/device-restrictions-configure)
- [IntuneでWindows 10のデバイス制限設定をMicrosoft Defender ウイルス対策する](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

### <a name="use-configuration-manager-to-configure-file-name-folder-or-file-extension-exclusions"></a>Configuration Managerを使用して、ファイル名、フォルダー、またはファイル拡張子の除外を構成する

Microsoft エンドポイント マネージャー (現在のブランチ) の構成の詳細については、「[マルウェア対策ポリシーを作成して展開する方法: 除外設定](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings)」を参照してください。

### <a name="use-group-policy-to-configure-folder-or-file-extension-exclusions"></a>グループ ポリシーを使用してフォルダーまたはファイル拡張子の除外を構成する

> [!NOTE]
> ファイルへの完全修飾パスを指定すると、そのファイルのみが除外されます。 フォルダーが除外で定義されている場合は、そのフォルダーの下にあるすべてのファイルとサブディレクトリが除外されます。

1. グループ ポリシー管理コンピューターで、[[グループ ポリシー管理コンソール]](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)) を開き、構成するグループ ポリシー オブジェクトを右クリックして、**[編集]** をクリックします。

2. [**グループ ポリシー管理エディター**] で、[**コンピューターの構成**] に移動し、[**管理用テンプレート**] を選択します。

3. ツリーを展開して **、除外Windows Defender ウイルス対策コンポーネント** \> **をWindows** \> **します**。

4. 編集用の **[パスの除外]** 設定を開き、除外を追加します。
    1. オプションを **[有効]** に設定します。
    2. **[オプション]** セクションで、[**表示**] を選択します。
    3. [ **値名** ] 列で、各フォルダーを独自の行に指定します。
    4. ファイルを指定する場合は、ドライブ文字、フォルダー パス、ファイル名、拡張子など、ファイルへの完全修飾パスを入力してください。
    5. **[値]** 列に **「0**」と入力します。

5. その後で、**[OK]** を選択します。

6. [ **拡張機能の除外] 設定を** 開いて編集し、除外を追加します。
    1. オプションを **[有効]** に設定します。
    2. **[オプション]** セクションで、[**表示**] を選択します。
    3. [ **値名** ] 列の下に、各ファイル拡張子を独自の行に入力します。
    4. **[値]** 列に **「0**」と入力します。

7. その後で、**[OK]** を選択します。

<a id="ps"></a>

### <a name="use-powershell-cmdlets-to-configure-file-name-folder-or-file-extension-exclusions"></a>PowerShell コマンドレットを使用して、ファイル名、フォルダー、またはファイル拡張子の除外を構成する

PowerShell を使用して、拡張子、場所、またはファイル名に基づいてファイルの除外を追加または削除するには、3 つのコマンドレットと適切な除外リスト パラメーターを組み合わせて使用する必要があります。 コマンドレットはすべて [Defender モジュールに含まれています](/powershell/module/defender/)。

コマンドレットの形式は次のとおりです。

```PowerShell
<cmdlet> -<exclusion list> "<item>"
```

次の表に、PowerShell コマンドレットの部分で `<cmdlet>` 使用できるコマンドレットを示します。

|構成アクション|PowerShell コマンドレット|
|:---|:---|
|リストを作成または上書きする|`Set-MpPreference`|
|一覧に追加する|`Add-MpPreference`|
|リストからアイテムを削除する|`Remove-MpPreference`|

次の表に、PowerShell コマンドレットの部分で `<exclusion list>` 使用できる値を示します。

|除外の種類|PowerShell パラメーター|
|---|---|
|指定したファイル拡張子を持つすべてのファイル|`-ExclusionExtension`|
|フォルダー下のすべてのファイル (サブディレクトリ内のファイルを含む)、または特定のファイル|`-ExclusionPath`|

> [!IMPORTANT]
> コマンドレットを使用してリストを作成した場合、 `Set-MpPreference` または `Add-MpPreference`コマンドレットを使用すると、既存の `Set-MpPreference` リストが上書きされます。

たとえば、次のコード スニペットを使用すると、Microsoft Defender ウイルス対策 スキャンによってファイル拡張子を持つファイルが`.test`除外されます。

```PowerShell
Add-MpPreference -ExclusionExtension ".test"
```

> [!TIP]
> 詳細については、「[PowerShell コマンドレットを使用して Microsoft Defender ウイルス対策を構成および実行する](use-powershell-cmdlets-microsoft-defender-antivirus.md)」および「[Defender ウイルス対策 コマンドレット ](/powershell/module/defender/)」を参照してください。

### <a name="use-windows-management-instrumentation-wmi-to-configure-file-name-folder-or-file-extension-exclusions"></a>Windows Management Instrumentation (WMI) を使用して、ファイル名、フォルダー、またはファイル拡張子の除外を構成する

次のプロパティには [、MSFT_MpPreference クラスの Set、Add、および Remove メソッド](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) を使用します。

```WMI
ExclusionExtension
ExclusionPath
```

**Set**、**Add**、**Remove** の使用は、PowerShell の対応する機能に似ています。 `Set-MpPreference``Add-MpPreference``Remove-MpPreference`

> [!TIP]
> 詳細については、「[WINDOWS DEFENDER WMIv2 API」を参照してください](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。

<a id="man-tools"></a>

### <a name="use-the-windows-security-app-to-configure-file-name-folder-or-file-extension-exclusions"></a>Windows セキュリティ アプリを使用して、ファイル名、フォルダー、またはファイル拡張子の除外を構成する

手順については、「[Windows セキュリティ アプリで除外を追加](microsoft-defender-security-center-antivirus.md)する」を参照してください。

<a id="wildcards"></a>

## <a name="use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>ファイル名とフォルダーパスまたは拡張子の除外リストでワイルドカードを使用する

ファイル名またはフォルダー パスの除外リスト内の項目を定義するときに、アスタリスク `*`、疑問符 `?`、または環境変数 (など `%ALLUSERSPROFILE%`) をワイルドカードとして使用できます。 これらのワイルドカードの解釈方法は、他のアプリや言語での通常の使用方法とは異なります。 特定の制限事項については、このセクションを必ずお読みください。

> [!IMPORTANT]
> これらのワイルドカードには、主な制限事項と使用シナリオがあります。
>
> - 環境変数の使用は、コンピューター変数と、NT AUTHORITY\SYSTEM アカウントとして実行されているプロセスに適用できる変数に制限されます。
> - 1 つのエントリにつき最大 6 つのワイルドカードのみを使用できます。
> - ドライブ文字の代わりにワイルドカードを使用することはできません。
> - フォルダーの除外のアスタリスク `*` は、1 つのフォルダーに対応します。 複数のインスタンスを使用して、名前が指定されていない複数の `\*\` 入れ子になったフォルダーを示します。
> - 現在、Microsoft Endpoint Configuration Managerではワイルドカード文字 (など`*``?`) はサポートされていません。
    
次の表では、ワイルドカードを使用する方法と、いくつかの例を示します。

<br/><br/>

|ワイルドカード|例|
|---|---|
|`*` (アスタリスク) <p> **ファイル名とファイル拡張子を含めると**、アスタリスクは任意の数の文字を置き換え、引数で定義された最後のフォルダー内のファイルにのみ適用されます。 <p> **フォルダーの除外** では、アスタリスクは 1 つのフォルダーを置き換えます。 複数の `*` 入れ子になったフォルダーを示すには、フォルダーの `\` スラッシュと共に複数を使用します。 ワイルドカードフォルダーと名前付きフォルダーの数を照合すると、すべてのサブフォルダーも含まれます。|`C:\MyData\*.txt` 含む `C:\MyData\notes.txt` <p> `C:\somepath\*\Data` には、ファイル `C:\somepath\Archives\Data` とそのサブフォルダーとその `C:\somepath\Authorized\Data` サブフォルダーが含まれます。 <p> `C:\Serv\*\*\Backup` には、ファイルとその `C:\Serv\Primary\Denied\Backup` サブフォルダーとその `C:\Serv\Secondary\Allowed\Backup` サブフォルダーが含まれます。|
|`?` (疑問符)  <p> **ファイル名とファイル拡張子を含めると**、疑問符は 1 文字を置き換え、引数で定義された最後のフォルダー内のファイルにのみ適用されます。 <p> **フォルダーの除外** では、疑問符はフォルダー名の 1 文字を置き換えます。 ワイルドカードフォルダーと名前付きフォルダーの数を照合すると、すべてのサブフォルダーも含まれます。|`C:\MyData\my?.zip` 含む `C:\MyData\my1.zip` <p> `C:\somepath\?\Data` には、すべてのファイル `C:\somepath\P\Data` とそのサブフォルダーが含まれます  <p> `C:\somepath\test0?\Data` には、すべてのファイル `C:\somepath\test01\Data` とそのサブフォルダーが含まれます。|
|環境変数 <p> 定義された変数は、除外が評価されるときにパスとして設定されます。|`%ALLUSERSPROFILE%\CustomLogFiles` が含まれます。 `C:\ProgramData\CustomLogFiles\Folder1\file1.txt`|

> [!IMPORTANT]
> ファイル除外引数とフォルダー除外引数を混在させる場合、ルールは一致したフォルダー内のファイル引数の一致で停止し、サブフォルダー内のファイル一致は検索されません。
>
> たとえば、フォルダー `c:\data\final\marked` 内の "date" で始まるすべてのファイルを除外し、 `c:\data\review\marked` ルール引数 `c:\data\*\marked\date*`を使用して除外できます。
>
> ただし、この引数は、サブ `c:\data\final\marked` フォルダーまたはサブフォルダー内のファイルと `c:\data\review\marked`一致しません。

<a id="review"></a>

### <a name="system-environment-variables"></a>システム環境変数

次の表に、システム アカウント環境変数の一覧と説明を示します。

|このシステム環境変数...|これにリダイレクトされます|
|---|---|
|`%APPDATA%`|`C:\Users\UserName.DomainName\AppData\Roaming`|
|`%APPDATA%\Microsoft\Internet Explorer\Quick Launch`|`C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Internet Explorer\Quick Launch`|
|`%APPDATA%\Microsoft\Windows\Start Menu`|`C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Windows\Start Menu`|
|`%APPDATA%\Microsoft\Windows\Start Menu\Programs`|`C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Windows\Start Menu\Programs`|
|`%LOCALAPPDATA%`|`C:\Windows\System32\config\systemprofile\AppData\Local`|
|`%ProgramData%`|`C:\ProgramData`|
|`%ProgramFiles%`|`C:\Program Files`|
|`%ProgramFiles%\Common Files`|`C:\Program Files\Common Files`|
|`%ProgramFiles%\Windows Sidebar\Gadgets`|`C:\Program Files\Windows Sidebar\Gadgets`|
|`%ProgramFiles%\Common Files`|`C:\Program Files\Common Files`|
|`%ProgramFiles(x86)%`|`C:\Program Files (x86)`|
|`%ProgramFiles(x86)%\Common Files`|`C:\Program Files (x86)\Common Files`|
|`%SystemDrive%`|`C:`|
|`%SystemDrive%\Program Files`|`C:\Program Files`|
|`%SystemDrive%\Program Files (x86)`|`C:\Program Files (x86)`|
|`%SystemDrive%\Users`|`C:\Users`|
|`%SystemDrive%\Users\Public`|`C:\Users\Public`|
|`%SystemRoot%`|`C:\Windows`|
|`%windir%`|`C:\Windows`|
|`%windir%\Fonts`|`C:\Windows\Fonts`|
|`%windir%\Resources`|`C:\Windows\Resources`|
|`%windir%\resources\0409`|`C:\Windows\resources\0409`|
|`%windir%\system32`|`C:\Windows\System32`|
|`%ALLUSERSPROFILE%`|`C:\ProgramData`|
|`%ALLUSERSPROFILE%\Application Data`|`C:\ProgramData\Application Data`|
|`%ALLUSERSPROFILE%\Documents`|`C:\ProgramData\Documents`|
|`%ALLUSERSPROFILE%\Documents\My Music\Sample Music`|`C:\ProgramData\Documents\My Music\Sample Music`|
|`%ALLUSERSPROFILE%\Documents\My Music`|`C:\ProgramData\Documents\My Music`|
|`%ALLUSERSPROFILE%\Documents\My Pictures`|`C:\ProgramData\Documents\My Pictures`|
|`%ALLUSERSPROFILE%\Documents\My Pictures\Sample Pictures`|`C:\ProgramData\Documents\My Pictures\Sample Pictures`|
|`%ALLUSERSPROFILE%\Documents\My Videos`|`C:\ProgramData\Documents\My Videos`|
|`%ALLUSERSPROFILE%\Microsoft\Windows\DeviceMetadataStore`|`C:\ProgramData\Microsoft\Windows\DeviceMetadataStore`|
|`%ALLUSERSPROFILE%\Microsoft\Windows\GameExplorer`|`C:\ProgramData\Microsoft\Windows\GameExplorer`|
|`%ALLUSERSPROFILE%\Microsoft\Windows\Ringtones`|`C:\ProgramData\Microsoft\Windows\Ringtones`|
|`%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu`|`C:\ProgramData\Microsoft\Windows\Start Menu`|
|`%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs`|`C:\ProgramData\Microsoft\Windows\Start Menu\Programs`|
|`%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\Administrative Tools`|`C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Administrative Tools`|
|`%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\StartUp`|`C:\ProgramData\Microsoft\Windows\Start Menu\Programs\StartUp`|
|`%ALLUSERSPROFILE%\Microsoft\Windows\Templates`|`C:\ProgramData\Microsoft\Windows\Templates`|
|`%ALLUSERSPROFILE%\Start Menu`|`C:\ProgramData\Start Menu`|
|`%ALLUSERSPROFILE%\Start Menu\Programs`| `C:\ProgramData\Start Menu\Programs`|
|`%ALLUSERSPROFILE%\Start Menu\Programs\Administrative Tools`|`C:\ProgramData\Start Menu\Programs\Administrative Tools`|
|`%ALLUSERSPROFILE%\Templates`|`C:\ProgramData\Templates`|
|`%LOCALAPPDATA%\Microsoft\Windows\ConnectedSearch\Templates`|`C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\ConnectedSearch\Templates`|
|`%LOCALAPPDATA%\Microsoft\Windows\History`|`C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\History`|
|`%PUBLIC%`|`C:\Users\Public`|
|`%PUBLIC%\AccountPictures`|`C:\Users\Public\AccountPictures`|
|`%PUBLIC%\Desktop`|`C:\Users\Public\Desktop`|
|`%PUBLIC%\Documents`|`C:\Users\Public\Documents`|
|`%PUBLIC%\Downloads`|`C:\Users\Public\Downloads`|
|`%PUBLIC%\Music\Sample Music`|`C:\Users\Public\Music\Sample Music`|
|`%PUBLIC%\Music\Sample Playlists`|`C:\Users\Public\Music\Sample Playlists`|
|`%PUBLIC%\Pictures\Sample Pictures`|`C:\Users\Public\Pictures\Sample Pictures`|
|`%PUBLIC%\RecordedTV.library-ms`|`C:\Users\Public\RecordedTV.library-ms`|
|`%PUBLIC%\Videos`|`C:\Users\Public\Videos`|
|`%PUBLIC%\Videos\Sample Videos`|`C:\Users\Public\Videos\Sample Videos`|
|`%USERPROFILE%`|`C:\Users\UserName`|
|`%USERPROFILE%\AppData\Local`|`C:\Users\UserName\AppData\Local`|
|`%USERPROFILE%\AppData\LocalLow`|`C:\Users\UserName\AppData\LocalLow`|
|`%USERPROFILE%\AppData\Roaming`|`C:\Users\UserName\AppData\Roaming`|

## <a name="review-the-list-of-exclusions"></a>除外の一覧を確認する

除外リスト内の項目は、次のいずれかの方法で取得できます。

- [Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)
- [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies)
- [MpCmdRun](command-line-arguments-microsoft-defender-antivirus.md)
- [PowerShell](/powershell/module/defender)
- [Windows セキュリティ アプリを開きます。](microsoft-defender-security-center-antivirus.md)

> [!IMPORTANT]
> グループ ポリシーで行われた除外リストの変更 **は、**[Windows セキュリティ アプリ](microsoft-defender-security-center-antivirus.md)の一覧に表示されます。
>
> Windows セキュリティ アプリで行われた変更は、グループ ポリシー リストには **表示されません**。

PowerShell を使用する場合は、次の 2 つの方法で一覧を取得できます。

- すべてのMicrosoft Defender ウイルス対策設定の状態を取得します。 各リストは別々の行に表示されますが、各リスト内の項目は同じ行に結合されます。
- すべての設定の状態を変数に書き込み、その変数を使用して、関心のある特定のリストのみを呼び出します。 それぞれの使用 `Add-MpPreference` は新しい行に書き込まれます。

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a>MpCmdRun を使用して除外リストを検証する

専用 [のコマンド ライン ツール mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md)で除外を確認するには、次のコマンドを使用します。

```console
Start, CMD (Run as admin)
cd "%programdata%\microsoft\windows defender\platform"
cd 4.18.2111-5.0 (Where 4.18.2111-5.0 is this month's Microsoft Defender Antivirus "Platform Update".)
MpCmdRun.exe -CheckExclusion -path <path>
```

> [!NOTE]
> MpCmdRun で除外を確認するには、MICROSOFT DEFENDER ウイルス対策 CAMP バージョン 4.18.2111-5.0 (2021 年 12 月にリリース) 以降が必要です。

### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a>PowerShell を使用して、他のすべてのMicrosoft Defender ウイルス対策設定と共に除外の一覧を確認する

次のコマンドレットを使用します。

```PowerShell
Get-MpPreference
```

次の例では、リストに `ExclusionExtension` 含まれる項目が強調表示されています。

:::image type="content" source="../../media/wdav-powershell-get-exclusions-variable.png" alt-text="Get-MpPreference の PowerShell 出力" lightbox="../../media/wdav-powershell-get-exclusions-variable.png":::

詳細については、「[PowerShell コマンドレットを使用して Microsoft Defender ウイルス対策を構成および実行する](use-powershell-cmdlets-microsoft-defender-antivirus.md)」および「[Defender ウイルス対策 コマンドレット ](/powershell/module/defender/)」を参照してください。

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a>PowerShell を使用して特定の除外リストを取得する

次のコード スニペットを使用します (各行を個別のコマンドとして入力します)。 **WDAVprefs を変数** に名前を付ける任意のラベルに置き換えます。

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionExtension
$WDAVprefs.ExclusionPath
```

次の例では、コマンドレットを使用するたびに、一覧が新しい行に `Add-MpPreference` 分割されます。

:::image type="content" source="../../media/wdav-powershell-get-exclusions-variable.png" alt-text="除外リスト内のエントリのみを示す PowerShell 出力" lightbox="../../media/wdav-powershell-get-exclusions-variable.png":::

詳細については、「[PowerShell コマンドレットを使用して Microsoft Defender ウイルス対策を構成および実行する](use-powershell-cmdlets-microsoft-defender-antivirus.md)」および「[Defender ウイルス対策 コマンドレット ](/powershell/module/defender/)」を参照してください。

<a id="validate"></a>

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a>EICAR テスト ファイルを使用して除外リストを検証する

除外リストが動作していることを検証するには、コマンドレットまたは .NET WebClient クラスで PowerShell を `Invoke-WebRequest` 使用してテスト ファイルをダウンロードします。

次の PowerShell スニペットでは、除外規則に準拠するファイルに置き換えます `test.txt` 。 たとえば、拡張機能を除外した場合は、次のように`.testing``test.testing`置き換えます`test.txt`。 パスをテストする場合は、そのパス内でコマンドレットを実行していることを確認します。

```PowerShell
Invoke-WebRequest "http://www.eicar.org/download/eicar.com.txt" -OutFile "test.txt"
```

Microsoft Defender ウイルス対策がマルウェアを報告する場合、ルールは機能しません。 マルウェアのレポートがなく、ダウンロードしたファイルが存在する場合は、除外が機能します。 ファイルを開いて、 [EICAR テスト ファイル Web サイト](http://www.eicar.org/86-0-Intended-use.html)で説明されている内容と同じ内容であることを確認できます。

次の PowerShell コードを使用して、.NET WebClient クラスを呼び出してテスト ファイルをダウンロードすることもできます 。コマンドレットと `Invoke-WebRequest` 同様に、検証する規則に準拠するファイルに置き換えます `c:\test.txt` 。

```PowerShell
$client = new-object System.Net.WebClient
$client.DownloadFile("http://www.eicar.org/download/eicar.com.txt","c:\test.txt")
```

インターネットにアクセスできない場合は、次の PowerShell コマンドを使用して EICAR 文字列を新しいテキスト ファイルに書き込むことで、独自の EICAR テスト ファイルを作成できます。

```PowerShell
[io.file]::WriteAllText("test.txt",'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*')
```

文字列を空白のテキスト ファイルにコピーし、ファイル名または除外しようとしているフォルダーに保存することもできます。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)

## <a name="see-also"></a>関連項目

- [Microsoft Defender ウイルス対策 スキャンでの除外の構成と検証](configure-exclusions-microsoft-defender-antivirus.md)
- [プロセスによって開かれたファイルの除外を構成して検証する](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [Windows サーバーでMicrosoft Defender ウイルス対策除外を構成する](configure-server-exclusions-microsoft-defender-antivirus.md)
- [除外を定義する際に避ける必要のある一般的な間違い](common-exclusion-mistakes-microsoft-defender-antivirus.md)
