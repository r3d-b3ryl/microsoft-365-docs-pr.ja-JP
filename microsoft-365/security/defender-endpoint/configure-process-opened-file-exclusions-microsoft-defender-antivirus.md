---
title: 特定のプロセスによって開かれたファイルの除外を構成する
description: 特定のプロセスによってファイルが開かれている場合は、スキャンからファイルを除外できます。
keywords: Microsoft Defender ウイルス対策、プロセス、除外、ファイル、スキャン
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.collection: M365-security-compliance
ms.openlocfilehash: 0dd59d2196ebb2c2af80fb53d43a009ff3a367d0
ms.sourcegitcommit: 3b194dd6f9ce531ae1b33d617ab45990d48bd3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/15/2022
ms.locfileid: "66102326"
---
# <a name="configure-exclusions-for-files-opened-by-processes"></a>プロセスによって開かれたファイルの除外を構成する


**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows 

特定のプロセスによって開かれたファイルは、Microsoft Defender ウイルス対策 スキャンから除外できます。 [除外リストを定義する前に、除外を定義する](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)おすすめを参照してください。

この記事では、除外リストを構成する方法について説明します。

## <a name="examples-of-exclusions"></a>除外の例

|除外|例|
|---|---|
|特定のファイル名を持つ任意のプロセスによって開かれるマシン上の任意のファイル|指定すると、 `test.exe` 次の方法で開かれたファイルが除外されます。 <p>`c:\sample\test.exe` <p> `d:\internal\files\test.exe`|
|特定のフォルダーの下の任意のプロセスによって開かれるコンピューター上の任意のファイル|指定すると、 `c:\test\sample\*` 次の方法で開かれたファイルが除外されます。 <p> `c:\test\sample\test.exe` <p> `c:\test\sample\test2.exe` <p> `c:\test\sample\utility.exe`|
|特定のフォルダー内の特定のプロセスによって開かれるコンピューター上の任意のファイル|指定すると `c:\test\process.exe` 、開かれたファイルのみが除外されます。 `c:\test\process.exe`|

プロセス除外リストにプロセスを追加すると、ファイルの場所に関係なく、そのプロセスによって開かれたファイルはスキャンMicrosoft Defender ウイルス対策されません。 ただし、プロセス自体は、 [ファイル除外リスト](configure-extension-file-exclusions-microsoft-defender-antivirus.md)にも追加されていない限り、スキャンされます。

除外は、 [常時オンのリアルタイムの保護と監視](configure-real-time-protection-microsoft-defender-antivirus.md)にのみ適用されます。 スケジュールされたスキャンやオンデマンド スキャンには適用されません。

除外リストに対するグループ ポリシーで行われた変更は、[Windows セキュリティ アプリ](microsoft-defender-security-center-antivirus.md)の一覧に **表示されます**。 ただし、Windows セキュリティ アプリで行われた変更は、グループ ポリシー リストには **表示されません**。

グループ ポリシー、Microsoft Endpoint Configuration Manager、Microsoft Intune、Windows セキュリティ アプリで除外リストを追加、削除、確認したり、ワイルドカードを使用してリストをさらにカスタマイズしたりできます。

PowerShell コマンドレットと WMI を使用して、リストの確認など、除外リストを構成することもできます。

既定では、リストに対して行われたローカル変更 (管理者特権を持つユーザー、PowerShell と WMI で行われた変更) は、グループ ポリシー、Configuration Manager、またはIntuneによって定義 (および展開) されたリストとマージされます。 競合の場合は、グループ ポリシーリストが優先されます。

[ローカルで定義された除外リストとグローバル定義の除外リストをマージして、](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists)ローカルの変更がマネージド デプロイ設定をオーバーライドできるようにする方法を構成できます。

## <a name="configure-the-list-of-exclusions-for-files-opened-by-specified-processes"></a>指定したプロセスによって開かれたファイルの除外の一覧を構成する

### <a name="use-microsoft-intune-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Microsoft Intuneを使用して、指定されたプロセスによって開かれたファイルをスキャンから除外する

詳細については、「[Microsoft Intune でデバイスの制限設定を構成する](/intune/device-restrictions-configure)」および「[Intune での Windows 10 の Microsoft Defender ウイルス対策デバイス制限設定](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)」を参照してください。

### <a name="use-microsoft-endpoint-manager-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Microsoft エンドポイント マネージャーを使用して、指定されたプロセスによって開かれたファイルをスキャンから除外する

Microsoft エンドポイント マネージャー (現在のブランチ) の構成の詳細については、「[マルウェア対策ポリシーを作成して展開する方法: 除外設定](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings)」を参照してください。

### <a name="use-group-policy-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>グループ ポリシーを使用して、指定されたプロセスによって開かれたファイルをスキャンから除外する

1. グループ ポリシー管理コンピューターで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開き、構成するグループ ポリシーオブジェクトを右クリックし、[編集] をクリック **します**。

2. **グループ ポリシー管理エディター** で **[コンピューターの構成**] に移動し、[**管理用テンプレート**] をクリックします。

3. ツリーを展開して **、除外Microsoft Defender ウイルス対策コンポーネント\>をWindows\>します**。

4. [ **プロセスの除外]** をダブルクリックし、除外を追加します。
    1. オプションを **[有効]** に設定します。
    2. [ **オプション]** セクションで、[ **表示]...** をクリックします。
    3. [ **値名** ] 列の下に、各プロセスを独自の行に入力します。 さまざまな種類のプロセス除外については、例の表を参照してください。 すべてのプロセスの **[値**] 列に **「0**」と入力します。

5. **[OK]** をクリックします。

### <a name="use-powershell-cmdlets-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>PowerShell コマンドレットを使用して、指定されたプロセスによって開かれたファイルをスキャンから除外する

PowerShell を使用して、プロセスによって開かれたファイルの除外を追加または削除するには、3 つのコマンドレットとパラメーターの組み合わせを使用する `-ExclusionProcess` 必要があります。 コマンドレットはすべて [Defender モジュールに含まれています](/powershell/module/defender/)。

コマンドレットの形式は次のとおりです。

```PowerShell
<cmdlet> -ExclusionProcess "<item>"
```

次のように指定できます。\<cmdlet\>

|構成アクション|PowerShell コマンドレット|
|---|---|
|リストを作成または上書きする|`Set-MpPreference`|
|一覧に追加する|`Add-MpPreference`|
|リストからアイテムを削除する|`Remove-MpPreference`|

> [!IMPORTANT]
> コマンドレットを使用してリストを作成した場合、 `Set-MpPreference` または `Add-MpPreference`コマンドレットを使用すると、既存の `Set-MpPreference` リストが上書きされます。

たとえば、次のコード スニペットを使用すると、Microsoft Defender AV スキャンによって、指定されたプロセスによって開かれたファイルが除外されます。

```PowerShell
Add-MpPreference -ExclusionProcess "c:\internal\test.exe"
```

Microsoft Defender ウイルス対策で PowerShell を使用する方法の詳細については、「PowerShell コマンドレットと[Microsoft Defender ウイルス対策コマンドレット](/powershell/module/defender)を使用したウイルス対策の管理」を参照してください。

### <a name="use-windows-management-instruction-wmi-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Windows管理命令 (WMI) を使用して、指定されたプロセスによって開かれたファイルをスキャンから除外する

次のプロパティに [対して、**MSFT_MpPreference** クラスの **Set**、**Add**、**および Remove** メソッド](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))を使用します。

```WMI
ExclusionProcess
```

**Set**、**Add**、**Remove** の使用は、PowerShell の対応する機能に似ています。 `Set-MpPreference``Add-MpPreference``Remove-MpPreference`

詳細と許可されるパラメーターについては、「[WINDOWS DEFENDER WMIv2 API」を](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)参照してください。

### <a name="use-the-windows-security-app-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Windows セキュリティ アプリを使用して、指定されたプロセスによって開かれたファイルをスキャンから除外する

手順については、「[Windows セキュリティ アプリで除外を追加](microsoft-defender-security-center-antivirus.md)する」を参照してください。

## <a name="use-wildcards-in-the-process-exclusion-list"></a>プロセス除外リストでワイルドカードを使用する

プロセス除外リストでのワイルドカードの使用は、他の除外リストでの使用とは異なります。

特に、疑問符 (`?`) ワイルドカードは使用できず、アスタリスク (`*`) ワイルドカードは完全なパスの末尾でのみ使用できます。 プロセス除外リスト内の項目を定義するときに、ワイルドカードとして環境変数 (など `%ALLUSERSPROFILE%`) を引き続き使用できます。

次の表では、プロセス除外リストでワイルドカードを使用する方法について説明します。

|ワイルドカード|使用例|一致する例|
|---|---|---|
|`*` (アスタリスク) <p> 任意の数の文字を置き換えます|`C:\MyData\*`|によって開かれたすべてのファイル `C:\MyData\file.exe`|
|環境変数 <p> 定義された変数は、除外が評価されるときにパスとして設定されます|`%ALLUSERSPROFILE%\CustomLogFiles\file.exe`|によって開かれたすべてのファイル `C:\ProgramData\CustomLogFiles\file.exe`|

## <a name="review-the-list-of-exclusions"></a>除外の一覧を確認する

MpCmdRun、PowerShell、[Microsoft Endpoint Configuration Manager、Intune](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings)、または[Windows セキュリティ アプリ](microsoft-defender-security-center-antivirus.md)を使用して、除外リスト内の[](/intune/device-restrictions-configure)項目を取得できます。

PowerShell を使用する場合は、次の 2 つの方法で一覧を取得できます。

- すべてのMicrosoft Defender ウイルス対策設定の状態を取得します。 各リストは別々の行に表示されますが、各リスト内の項目は同じ行に結合されます。
- すべての設定の状態を変数に書き込み、その変数を使用して、関心のある特定のリストのみを呼び出します。 それぞれの使用 `Add-MpPreference` は新しい行に書き込まれます。

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a>MpCmdRun を使用して除外リストを検証する

専用 [のコマンド ライン ツール mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)で除外を確認するには、次のコマンドを使用します。

```DOS
MpCmdRun.exe -CheckExclusion -path <path>
```

> [!NOTE]
> MpCmdRun で除外を確認するには、MICROSOFT DEFENDER ウイルス対策 CAMP バージョン 4.18.1812.3 (2018 年 12 月にリリース) 以降が必要です。

### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a>PowerShell を使用して、他のすべてのMicrosoft Defender ウイルス対策設定と共に除外の一覧を確認する

次のコマンドレットを使用します。

```PowerShell
Get-MpPreference
```

[PowerShell をMicrosoft Defender ウイルス対策で使用する方法の詳細については、「PowerShell コマンドレットを使用してMicrosoft Defender ウイルス対策](use-powershell-cmdlets-microsoft-defender-antivirus.md)[コマンドレットとMicrosoft Defender ウイルス対策コマンドレット](/powershell/module/defender)を構成および実行する」を参照してください。

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a>PowerShell を使用して特定の除外リストを取得する

次のコード スニペットを使用します (各行を個別のコマンドとして入力します)。 **WDAVprefs を変数** に名前を付ける任意のラベルに置き換えます。

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionProcess
```

[PowerShell をMicrosoft Defender ウイルス対策で使用する方法の詳細については、「PowerShell コマンドレットを使用してMicrosoft Defender ウイルス対策](use-powershell-cmdlets-microsoft-defender-antivirus.md)[コマンドレットとMicrosoft Defender ウイルス対策コマンドレット](/powershell/module/defender)を構成および実行する」を参照してください。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)

## <a name="related-articles"></a>関連記事

- [Microsoft Defender ウイルス対策 スキャンでの除外の構成と検証](configure-exclusions-microsoft-defender-antivirus.md)
- [ファイル名、拡張子、フォルダーの場所に基づいて除外を構成および検証する](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Windows サーバーでMicrosoft Defender ウイルス対策除外を構成する](configure-server-exclusions-microsoft-defender-antivirus.md)
- [除外を定義する際に避ける必要のある一般的な間違い](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策スキャンと修復の結果をカスタマイズ、開始、および確認する](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
