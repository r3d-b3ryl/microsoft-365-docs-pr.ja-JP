---
title: 拡張機能、名前、または場所に基づいて除外を構成および検証する
description: ファイル拡張子、ファイルMicrosoft Defender ウイルス対策場所に基づいて、ファイルをスキャンから除外します。
keywords: 除外、ファイル、拡張子、ファイルの種類、フォルダー名、ファイル名、スキャン
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: f8d274443e67ab89952508870aa118d7e13378e0
ms.sourcegitcommit: 6c342a956b2dbc32be33bac1a23a5038490f1b40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58533425"
---
# <a name="configure-and-validate-exclusions-based-on-file-extension-and-folder-location"></a>ファイル拡張子とフォルダーの場所に基づいて除外を構成および検証する

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender ウイルス対策

スケジュールされたスキャン、オンデマンド スキャンMicrosoft Defender ウイルス対策常時オン、リアルタイムの[](schedule-antivirus-scans.md)保護と監視[](run-scan-microsoft-defender-antivirus.md)に適用されるアプリケーションの除外[を定義できます](configure-real-time-protection-microsoft-defender-antivirus.md)。 **一般に、除外を適用する必要はない必要があります**。 除外を適用する必要がある場合は、いくつかの異なる種類から選択できます。

- ファイル拡張子とフォルダーの場所に基づく除外 (この記事で説明)
- [プロセスによって開くファイルの除外](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

> [!IMPORTANT]
> Microsoft Defender ウイルス対策除外は、エンドポイントの検出と応答[(EDR)、](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)攻撃表面の縮小[(ASR)](/microsoft-365/security/defender-endpoint/attack-surface-reduction)ルール、フォルダー アクセスの制御など、他の Microsoft Defender for Endpoint 機能には[適用されません](/microsoft-365/security/defender-endpoint/controlled-folders)。 この記事で説明する方法を使用して除外するファイルは、アラートや他の検出EDRトリガーできます。
> ファイルを広く除外するには、Microsoft Defender for Endpoint カスタム インジケーターに [ファイルを追加します](/microsoft-365/security/defender-endpoint/manage-indicators)。

## <a name="before-you-begin"></a>開始する前に

除外 [リストを定義する前に、「除外を](configure-exclusions-microsoft-defender-antivirus.md) 定義するための推奨事項」を参照してください。

## <a name="exclusion-lists"></a>除外リスト

特定のファイルをスキャンからMicrosoft Defender ウイルス対策するには、除外リストを変更します。 Microsoft Defender ウイルス対策には、既知のオペレーティング システムの動作や一般的な管理ファイル (エンタープライズ管理、データベース管理、その他のエンタープライズ シナリオや状況で使用されるファイルなど) に基づく多くの自動除外が含まれます。

> [!NOTE]
> 除外は、望ましくない可能性のあるアプリ (PUA) の検出にも適用されます。
>
> 自動除外は、ユーザーおよびWindows Server 2016にのみ適用されます。 これらの除外は、アプリと PowerShell のWindows セキュリティ表示されません。

次の表に、ファイル拡張子とフォルダーの場所に基づく除外の例を示します。

<br>

****

|除外|例|除外リスト|
|---|---|---|
|特定の拡張子を持つファイル|指定した拡張子を持つすべてのファイル (コンピューター上の任意の場所)。 <p> 有効な構文: `.test` と `test`|拡張機能の除外|
|特定のフォルダーの下のファイル|フォルダーの下のすべての `c:\test\sample` ファイル|ファイルとフォルダーの除外|
|特定のフォルダー内の特定のファイル|ファイル `c:\sample\sample.test` のみ|ファイルとフォルダーの除外|
|特定のプロセス|実行可能ファイル `c:\test\process.exe`|ファイルとフォルダーの除外|
|

## <a name="characteristics-of-exclusion-lists"></a>除外リストの特性

- フォルダーの除外は、サブフォルダーが再解析ポイントである場合を含め、そのフォルダーの下のすべてのファイルとフォルダーに適用されます。 Reparse ポイントサブフォルダーは個別に除外する必要があります。
- パスまたはフォルダーが定義されていない場合、ファイル拡張子は、定義された拡張子を持つ任意のファイル名に適用されます。

## <a name="important-notes-about-exclusions-based-on-file-extensions-and-folder-locations"></a>ファイル拡張子とフォルダーの場所に基づく除外に関する重要な注意事項

- アスタリスク ( ) などのワイルドカードを使用 \* すると、除外ルールの解釈方法が変更されます。 ワイルドカードの [動作に関する重要な](#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) 情報については、「ファイル名とフォルダー パスまたは拡張子の除外リストでワイルドカードを使用する」セクションを参照してください。

- マップされたネットワーク ドライブを除外しない。 実際のネットワーク パスを指定します。

- Microsoft Defender ウイルス対策 サービスの開始後に作成され、除外リストに追加された再解析ポイントであるフォルダーは含まれません。 新しい再解析ポイントが有効な除外ターゲットとして認識されるWindowsサービスを再起動します(再起動Windows)。

- 除外は、スケジュール[されたスキャン](scheduled-catch-up-scans-microsoft-defender-antivirus.md)、[オンデマンド](run-scan-microsoft-defender-antivirus.md)スキャン、リアルタイム保護[](configure-real-time-protection-microsoft-defender-antivirus.md)に適用されますが、Defender for Endpoint 全体には適用されません。 Defender for Endpoint 全体で除外を定義するには、カスタム インジケーター [を使用します](manage-indicators.md)。

- 既定では、リストに対して行われたローカルの変更 (PowerShell および WMI による変更を含む管理者特権を持つユーザー) は、グループ ポリシー、Configuration Manager、Intune によって定義 (展開) されたリストと結合されます。 グループ ポリシーの一覧は、競合がある場合に優先されます。 さらに、グループ ポリシーで行われた除外リストの変更は、アプリ内Windows セキュリティ[表示されます](microsoft-defender-security-center-antivirus.md)。

- ローカルの変更による管理展開設定の上書きを許可するには、ローカルで定義された除外リストとグローバルに定義された除外リストの結合方法 [を構成します](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists)。

## <a name="configure-the-list-of-exclusions-based-on-folder-name-or-file-extension"></a>フォルダー名またはファイル拡張子に基づいて除外の一覧を構成する

複数の方法から選択して、ユーザーの除外を定義Microsoft Defender ウイルス対策。

### <a name="use-intune-to-configure-file-name-folder-or-file-extension-exclusions"></a>Intune を使用してファイル名、フォルダー、またはファイル拡張子の除外を構成する

次の記事をご覧ください。

- [デバイス制限の設定を構成Microsoft Intune](/intune/device-restrictions-configure)
- [Microsoft Defender ウイルス対策 Intune のデバイス制限Windows 10設定](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

### <a name="use-configuration-manager-to-configure-file-name-folder-or-file-extension-exclusions"></a>Configuration Manager を使用してファイル名、フォルダー、またはファイル拡張子の除外を構成する

詳細[については、「マルウェア対策ポリシーを作成](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings)して展開する方法: 除外設定」を参照Microsoft エンドポイント マネージャー (現在のブランチ)。

### <a name="use-group-policy-to-configure-folder-or-file-extension-exclusions"></a>グループ ポリシーを使用してフォルダーまたはファイル拡張子の除外を構成する

> [!NOTE]
> ファイルへの完全修飾パスを指定すると、そのファイルだけが除外されます。 フォルダーが除外で定義されている場合、そのフォルダーの下のすべてのファイルとサブディレクトリは除外されます。

1. グループ ポリシー管理コンピューターで、[[グループ ポリシー管理コンソール]](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)) を開き、構成するグループ ポリシー オブジェクトを右クリックして、**[編集]** をクリックします。

2. グループ ポリシー **管理エディターで、[コンピューター** の構成] に **移動し、[** 管理用 **テンプレート] を選択します**。

3. ツリーを展開して、[**除外Windowsコンポーネント** \> **Microsoft Defender ウイルス対策** \> **展開します**。

4. 編集用 **に [パスの除外]** 設定を開き、除外を追加します。
    1. オプションを [有効] に **設定します**。
    2. [オプション] **セクションで** 、[表示] **を選択します**。
    3. [値名] 列の下の各フォルダーを独自 **の行に指定** します。
    4. ファイルを指定する場合は、ドライブ文字、フォルダー パス、ファイル名、拡張子など、ファイルへの完全修飾パスを入力してください。 [値 **] 列に「0」****と入力** します。

5. **[OK]** をクリックします。

6. [拡張機能 **の除外] 設定を** 開いて編集し、除外を追加します。
    1. オプションを [有効] に **設定します**。
    2. [オプション] **セクションで** 、[表示] **を選択します**。
    3. [値] 列の [値名] 列 **[0]** の下に、それぞれのファイル拡張子を独自の行に **入力** します。

7. **[OK]** をクリックします。

<a id="ps"></a>

### <a name="use-powershell-cmdlets-to-configure-file-name-folder-or-file-extension-exclusions"></a>PowerShell コマンドレットを使用してファイル名、フォルダー、またはファイル拡張子の除外を構成する

PowerShell を使用して、拡張子、場所、またはファイル名に基づいてファイルの除外を追加または削除するには、3 つのコマンドレットと適切な除外リスト パラメーターを組み合わせて使用する必要があります。 コマンドレットはすべて Defender モジュール [内です](/powershell/module/defender/)。

コマンドレットの形式は次のとおりです。

```PowerShell
<cmdlet> -<exclusion list> "<item>"
```

次の表に、PowerShell コマンドレットの部分で使用 `<cmdlet>` できるコマンドレットを示します。

<br>

****

|構成アクション|PowerShell コマンドレット|
|:---|:---|
|リストを作成または上書きする|`Set-MpPreference`|
|リストに追加する|`Add-MpPreference`|
|リストからアイテムを削除する|`Remove-MpPreference`|
|

次の表に、PowerShell コマンドレットの部分で使用できる `<exclusion list>` 値を示します。

<br>

****

|除外の種類|PowerShell パラメーター|
|---|---|
|指定したファイル拡張子を持つすべてのファイル|`-ExclusionExtension`|
|フォルダーの下のすべてのファイル (サブディレクトリ内のファイルを含む)、または特定のファイル|`-ExclusionPath`|
|

> [!IMPORTANT]
> コマンドレットを使用するか、または使用してリストを作成した場合は、 `Set-MpPreference` `Add-MpPreference` `Set-MpPreference` 既存のリストが上書きされます。

たとえば、次のコード スニペットを使用すると、Microsoft Defender ウイルス対策ファイル拡張子を持つファイルが `.test` 除外されます。

```PowerShell
Add-MpPreference -ExclusionExtension ".test"
```

> [!TIP]
> 詳細については、「[PowerShell コマンドレットを使用して Microsoft Defender ウイルス対策を構成および実行する](use-powershell-cmdlets-microsoft-defender-antivirus.md)」および「[Defender コマンドレット](/powershell/module/defender/)」を参照してください。

### <a name="use-windows-management-instruction-wmi-to-configure-file-name-folder-or-file-extension-exclusions"></a>[Windows管理命令 (WMI) を使用して、ファイル名、フォルダー、またはファイル拡張子の除外を構成する

次の [プロパティのクラスの Set メソッド、Add メソッド、Remove](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) メソッドMSFT_MpPreference使用します。

```WMI
ExclusionExtension
ExclusionPath
```

**Set、Add、Remove** を使用すると、PowerShell の対応するユーザーと類似 `Set-MpPreference` しています。 `Add-MpPreference` `Remove-MpPreference`

> [!TIP]
> 詳細については[、「WMIv2 API Windows Defenderを参照してください](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。

<a id="man-tools"></a>

### <a name="use-the-windows-security-app-to-configure-file-name-folder-or-file-extension-exclusions"></a>ファイル名、Windows セキュリティ、またはファイル拡張子の除外を構成するには、アプリを使用します。

手順[については、「アプリの除外をWindows セキュリティする」](microsoft-defender-security-center-antivirus.md)を参照してください。

<a id="wildcards"></a>

## <a name="use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>ファイル名とフォルダー パスまたは拡張子の除外リストでワイルドカードを使用する

ファイル名またはフォルダー パス除外リストの項目を定義する場合は、アスタリスク、疑問符、環境変数 (など) をワイルドカードとして `*` `?` `%ALLUSERSPROFILE%` 使用できます。 これらのワイルドカードの解釈方法は、他のアプリや言語での通常の使用法とは異なります。 特定の制限について理解するには、必ずこのセクションを参照してください。

> [!IMPORTANT]
> 次のワイルドカードには、主な制限と使用シナリオがあります。
>
> - 環境変数の使用は、コンピューター変数と、NT AUTHORITY\SYSTEM アカウントとして実行されているプロセスに適用可能な変数に制限されます。
> - ドライブ文字の代りでワイルドカードを使用することはできません。
> - フォルダー除外 `*` のアスタリスクは、1 つのフォルダーに対して配置されます。 複数のインスタンスを使用して `\*\` 、名前が指定されていない複数の入れ子になったフォルダーを示します。

次の表では、ワイルドカードの使用方法と例を示します。

<br>

****

|ワイルドカード|例|
|---|---|
|`*` (アスタリスク) <p> ファイル **名とファイル拡張子** の組み込みでは、アスタリスクは任意の数の文字を置き換え、引数で定義された最後のフォルダー内のファイルにのみ適用されます。 <p> フォルダー **の除外では、** アスタリスクによって 1 つのフォルダーが置き換されます。 複数のフォルダー `*` スラッシュを使用して、 `\` 複数の入れ子になったフォルダーを示します。 ワイルドカード フォルダーと名前付きフォルダーの数を一致した後、すべてのサブフォルダーも含まれます。|`C:\MyData\*.txt` を含む `C:\MyData\notes.txt` <p> `C:\somepath\*\Data` に含まれるファイル `C:\somepath\Archives\Data` とそのサブフォルダー、およびサブ `C:\somepath\Authorized\Data` フォルダー <p> `C:\Serv\*\*\Backup` に含まれるファイル `C:\Serv\Primary\Denied\Backup` とそのサブフォルダー `C:\Serv\Secondary\Allowed\Backup` とそのサブフォルダー|
|`?` (疑問符)  <p> ファイル **名とファイル拡張子** の包含では、疑問符は 1 文字を置き換え、引数で定義された最後のフォルダー内のファイルにのみ適用されます。 <p> フォルダー **の除外では、** 疑問符はフォルダー名の 1 文字を置き換えます。 ワイルドカード フォルダーと名前付きフォルダーの数を一致した後、すべてのサブフォルダーも含まれます。|`C:\MyData\my?.zip` を含む `C:\MyData\my1.zip` <p> `C:\somepath\?\Data` ファイルとそのサブフォルダー `C:\somepath\P\Data` を含む  <p> `C:\somepath\test0?\Data` ファイルとそのサブフォルダー `C:\somepath\test01\Data` が含まれる場合|
|環境変数 <p> 定義された変数は、除外が評価される際にパスとして設定されます。|`%ALLUSERSPROFILE%\CustomLogFiles` を含む `C:\ProgramData\CustomLogFiles\Folder1\file1.txt`|
|

> [!IMPORTANT]
> ファイル除外引数とフォルダー除外引数を混在すると、ルールは一致したフォルダーの file 引数一致で停止し、サブフォルダー内のファイル一致は検索されません。
>
> たとえば、フォルダー内の "date" で始まるすべてのファイルを除外し、rule 引数 `c:\data\final\marked` `c:\data\review\marked` を使用して除外できます `c:\data\*\marked\date*` 。
>
> ただし、この引数はサブフォルダーまたはサブフォルダー内のファイルと一致 `c:\data\final\marked` しません `c:\data\review\marked` 。

<a id="review"></a>

### <a name="system-environment-variables"></a>システム環境変数

次の表に、システム アカウント環境変数の一覧と説明を示します。

<br>

****

|このシステム環境変数...|リダイレクト先|
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
|`%ALLUSERSPROFILE%\Start Menu\Programs`|C:\ProgramData\Start Menu\Programs|
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
|`%USERPROFILE%`|`C:\Windows\System32\config\systemprofile`|
|`%USERPROFILE%\AppData\Local`|`C:\Windows\System32\config\systemprofile\AppData\Local`|
|`%USERPROFILE%\AppData\LocalLow`|`C:\Windows\System32\config\systemprofile\AppData\LocalLow`|
|`%USERPROFILE%\AppData\Roaming`|`C:\Windows\System32\config\systemprofile\AppData\Roaming`|
|

## <a name="review-the-list-of-exclusions"></a>除外の一覧を確認する

除外リスト内のアイテムを取得するには、次のいずれかの方法を使用します。

- [Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)
- [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies)
- MpCmdRun
- PowerShell
- [Windows セキュリティアプリ](microsoft-defender-security-center-antivirus.md)

> [!IMPORTANT]
> グループ ポリシーで行われた除外リストの変更 **は、** アプリ内のリスト [にWindows セキュリティされます](microsoft-defender-security-center-antivirus.md)。
>
> アプリで行われたWindows セキュリティ **グループ** ポリシー リストには表示されない。

PowerShell を使用する場合は、次の 2 つの方法でリストを取得できます。

- すべてのユーザー設定のMicrosoft Defender ウイルス対策します。 各リストは別々の行に表示されますが、各リスト内のアイテムは同じ行に結合されます。
- すべての基本設定の状態を変数に書き込み、その変数を使用して、関心のある特定のリストのみを呼び出します。 各使用は `Add-MpPreference` 、新しい行に書き込まれます。

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a>MpCmdRun を使用して除外リストを検証する

専用のコマンド ライン ツールを使用して除外を確認するには [mpcmdrun.exeコマンドを ](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)使用します。

```DOS
Start, CMD (Run as admin)
cd "%programdata%\microsoft\windows defender\platform"
cd 4.18.1812.3 (Where 4.18.1812.3 is this month's MDAV "Platform Update".)
MpCmdRun.exe -CheckExclusion -path <path>
```

> [!NOTE]
> MpCmdRun で除外をチェックするには、Microsoft Defender ウイルス対策 CAMP バージョン 4.18.1812.3 (2018 年 12 月にリリース) 以降が必要です。

### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a>PowerShell を使用して、他のすべてのユーザー設定とMicrosoft Defender ウイルス対策一覧を確認する

次のコマンドレットを使用します。

```PowerShell
Get-MpPreference
```

次の例では、リストに含まれるアイテム `ExclusionExtension` が強調表示されます。

:::image type="content" source="../../media/wdav-powershell-get-exclusions-variable.png" alt-text="Get-MpPreference の PowerShell 出力":::

詳細については、「[PowerShell コマンドレットを使用して Microsoft Defender ウイルス対策を構成および実行する](use-powershell-cmdlets-microsoft-defender-antivirus.md)」および「[Defender コマンドレット](/powershell/module/defender/)」を参照してください。

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a>PowerShell を使用して特定の除外リストを取得する

次のコード スニペットを使用します (各行を個別のコマンドとして入力します)。 **WDAVprefs を変数** に名前を付けしたいラベルに置き換える:

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionExtension
$WDAVprefs.ExclusionPath
```

次の例では、コマンドレットを使用するごとに、リストが新しい行に分割 `Add-MpPreference` されます。

:::image type="content" source="../../media/wdav-powershell-get-exclusions-variable.png" alt-text="除外リスト内のエントリのみを表示する PowerShell 出力":::

詳細については、「[PowerShell コマンドレットを使用して Microsoft Defender ウイルス対策を構成および実行する](use-powershell-cmdlets-microsoft-defender-antivirus.md)」および「[Defender コマンドレット](/powershell/module/defender/)」を参照してください。

<a id="validate"></a>

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a>EICAR テスト ファイルを使用して除外リストを検証する

コマンドレットまたは .NET WebClient クラスで PowerShell を使用してテスト ファイルをダウンロードすることで、除外リストが機能している `Invoke-WebRequest` のを検証できます。

次の PowerShell スニペットで、除外 `test.txt` ルールに準拠したファイルに置き換えます。 たとえば、拡張機能を除外した場合は、 `.testing` に置き換 `test.txt` える `test.testing` 。 パスをテストする場合は、そのパス内でコマンドレットを実行してください。

```PowerShell
Invoke-WebRequest "http://www.eicar.org/download/eicar.com.txt" -OutFile "test.txt"
```

マルウェアMicrosoft Defender ウイルス対策報告する場合、ルールは機能していません。 マルウェアの報告がない場合、ダウンロードしたファイルが存在する場合は、除外が機能しています。 ファイルを開き、内容が EICAR テスト ファイル Web サイトで説明されている内容と [同じことを確認できます](http://www.eicar.org/86-0-Intended-use.html)。

また、次の PowerShell コードを使用して、.NET WebClient クラスを呼び出して、コマンドレットと同様にテスト ファイルをダウンロードし、検証するルールに準拠したファイルに置き換 `Invoke-WebRequest` `c:\test.txt` えることができます。

```PowerShell
$client = new-object System.Net.WebClient
$client.DownloadFile("http://www.eicar.org/download/eicar.com.txt","c:\test.txt")
```

インターネット にアクセスできない場合は、次の PowerShell コマンドを使用して EICAR 文字列を新しいテキスト ファイルに書き込み、独自の EICAR テスト ファイルを作成できます。

```PowerShell
[io.file]::WriteAllText("test.txt",'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*')
```

文字列を空白のテキスト ファイルにコピーして、ファイル名または除外するフォルダーに保存することもできます。

## <a name="see-also"></a>関連項目

- [カスタム スキャンで除外を構成Microsoft Defender ウイルス対策する](configure-exclusions-microsoft-defender-antivirus.md)
- [プロセスによって開いたファイルの除外を構成および検証する](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [サーバー Microsoft Defender ウイルス対策の除外をWindowsする](configure-server-exclusions-microsoft-defender-antivirus.md)
- [除外を定義する際に避ける必要のある一般的な間違い](common-exclusion-mistakes-microsoft-defender-antivirus.md)
