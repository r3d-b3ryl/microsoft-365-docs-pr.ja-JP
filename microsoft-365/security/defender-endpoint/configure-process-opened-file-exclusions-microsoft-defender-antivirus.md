---
title: 特定のプロセスによって開いたファイルの除外を構成する
description: 特定のプロセスでファイルを開いている場合は、スキャンからファイルを除外できます。
keywords: Microsoft Defender ウイルス対策、プロセス、除外、ファイル、スキャン
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
ms.openlocfilehash: 4a117d2743436381029d047693f81303e5908b2b
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690891"
---
# <a name="configure-exclusions-for-files-opened-by-processes"></a>プロセスによって開いたファイルの除外を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

特定のプロセスで開いたファイルは、Microsoft Defender ウイルス対策スキャンから除外できます。 除外 [リストを定義する前に、「除外を](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) 定義するための推奨事項」を参照してください。

この記事では、除外リストを構成する方法について説明します。 

## <a name="examples-of-exclusions"></a>除外の例

|除外 | 例 |
|---|---|
|特定のファイル名を持つ任意のプロセスによって開いたコンピューター上のファイル | 指定すると `test.exe` 、次の方法で開いたファイルが除外されます。 <br/>`c:\sample\test.exe`<br/>`d:\internal\files\test.exe` |  
|特定のフォルダーの下の任意のプロセスによって開いたコンピューター上のファイル | 指定すると `c:\test\sample\*` 、次の方法で開いたファイルが除外されます。<br/>`c:\test\sample\test.exe`<br/>`c:\test\sample\test2.exe`<br/>`c:\test\sample\utility.exe` | 
|特定のフォルダー内の特定のプロセスによって開いたコンピューター上のすべてのファイル | 指定すると `c:\test\process.exe` 、開いたファイルだけが除外されます。 `c:\test\process.exe` |


プロセス除外リストにプロセスを追加しても、ファイルの場所に関係なく、そのプロセスで開いたファイルはスキャンされません。 ただし、ファイル除外リストにも追加されていない限り、プロセス自体 [がスキャンされます](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。

除外は、常時オン [のリアルタイム保護と監視にのみ適用されます](configure-real-time-protection-microsoft-defender-antivirus.md)。 スケジュールされたスキャンやオンデマンド スキャンには適用されません。

グループ ポリシーを使用して除外リストに加えた変更 **は、Windows** セキュリティ アプリのリスト [に表示されます](microsoft-defender-security-center-antivirus.md)。 ただし、Windows セキュリティ アプリで行われた変更 **は、グループ** ポリシー リストには表示されない。

グループ ポリシー、Microsoft Endpoint Configuration Manager、Microsoft Intune、および Windows セキュリティ アプリで除外リストの追加、削除、および確認を行い、ワイルドカードを使用してリストをさらにカスタマイズできます。

PowerShell コマンドレットと WMI を使用して、リストの確認など、除外リストを構成することもできます。

既定では、リストに対して行われたローカルの変更 (管理者特権を持つユーザー、PowerShell と WMI で行われた変更) は、グループ ポリシー、Configuration Manager、または Intune によって定義された (展開された) リストと結合されます。 グループ ポリシーの一覧は、競合が発生した場合に優先されます。

ローカルで [定義された除外リスト](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) とグローバルに定義された除外リストの結合方法を構成して、ローカルの変更で管理展開設定を上書きできます。

## <a name="configure-the-list-of-exclusions-for-files-opened-by-specified-processes"></a>指定したプロセスによって開いたファイルの除外の一覧を構成する

### <a name="use-microsoft-intune-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Microsoft Intune を使用して、指定したプロセスで開いたファイルをスキャンから除外する

詳細 [については、「Configure device Restriction settings in Microsoft Intune」](/intune/device-restrictions-configure) および [「Microsoft Defender Antivirus device Restriction settings for Windows 10 in Intune」](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) を参照してください。

### <a name="use-microsoft-endpoint-manager-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Microsoft Endpoint Manager を使用して、指定したプロセスで開いたファイルをスキャンから除外する

Microsoft Endpoint Manager ( [現在の](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) ブランチ) の構成の詳細については、「マルウェア対策ポリシーを作成して展開する方法: 除外設定」を参照してください。

### <a name="use-group-policy-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>グループ ポリシーを使用して、指定したプロセスで開いたファイルをスキャンから除外する

1. グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。

2. グループ ポリシー **管理エディターで、[コンピューター** の構成] に **移動し、[** 管理用 **テンプレート] をクリックします**。

3. ツリーを **Microsoft Defender ウイルス対策と除外> Windows コンポーネント>展開します**。

4. [除外の処理 **] をダブルクリックし** 、除外を追加します。

    1. オプションを [有効] に **設定します**。
    2. [オプション] **セクションで** 、[ **表示.... をクリックします**。
    3. [値名] 列の下に、各プロセス **を独自の行に入力** します。 さまざまな種類のプロセスの除外については、例の表を参照してください。  すべての **プロセスの [** 値] **列に 0** を入力します。

5. **[OK]** をクリックします。

### <a name="use-powershell-cmdlets-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>PowerShell コマンドレットを使用して、指定したプロセスで開いたファイルをスキャンから除外する

PowerShell を使用してプロセスによって開いたファイルの除外を追加または削除するには、パラメーターと 3 つのコマンドレットを組み合わせて使用する必要 `-ExclusionProcess` があります。 コマンドレットはすべて Defender モジュール [内です](/powershell/module/defender/)。

コマンドレットの形式は次の形式です。

```PowerShell
<cmdlet> -ExclusionProcess "<item>"
```

以下を次のように使用できます \<cmdlet> 。

|構成アクション | PowerShell コマンドレット |
|---|---|
|リストを作成または上書きする | `Set-MpPreference` |
|リストに追加する | `Add-MpPreference` |
|リストからアイテムを削除する | `Remove-MpPreference` |

>[!IMPORTANT]
>コマンドレットを使用するか、または使用してリストを作成した場合は、 `Set-MpPreference` `Add-MpPreference` `Set-MpPreference` 既存のリストが上書きされます。

たとえば、次のコード スニペットを使用すると、Microsoft Defender AV スキャンによって、指定したプロセスで開いたファイルが除外されます。

```PowerShell
Add-MpPreference -ExclusionProcess "c:\internal\test.exe"
```

Microsoft Defender Antivirus で PowerShell を使用する方法の詳細については、「Manage antivirus with PowerShell コマンドレット」および [「Microsoft Defender Antivirus コマンドレット」を参照してください](/powershell/module/defender)。

### <a name="use-windows-management-instruction-wmi-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Windows 管理命令 (WMI) を使用して、指定したプロセスで開いたファイルをスキャンから除外する

次の [**プロパティの****クラスの** **Set メソッド、Add** **メソッド、Remove**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))メソッドMSFT_MpPreference使用します。

```WMI
ExclusionProcess
```

**Set、Add、****および** **Remove** の使用は、PowerShell の対応するユーザーと類似 `Set-MpPreference` しています。 `Add-MpPreference` `Remove-MpPreference`

詳細および許可されるパラメーターについては  [、「WMIv2 API のWindows Defender参照してください](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。

### <a name="use-the-windows-security-app-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Windows セキュリティ アプリを使用して、指定したプロセスで開いたファイルをスキャンから除外する

手順 [については、「Windows セキュリティ アプリで除外を追加する」](microsoft-defender-security-center-antivirus.md) を参照してください。

## <a name="use-wildcards-in-the-process-exclusion-list"></a>プロセス除外リストでワイルドカードを使用する

プロセス除外リストでのワイルドカードの使用は、他の除外リストでのワイルドカードの使用とは異なります。

特に、疑問符 ( ) ワイルドカードは使用できません。アスタリスク ( ) ワイルドカードは完全なパスの最後 `?` `*` でのみ使用できます。 プロセス除外リストで項目を定義する場合は、ワイルドカードとして環境変数 ( `%ALLUSERSPROFILE%` など) を使用できます。

次の表に、プロセス除外リストでワイルドカードを使用する方法を示します。

|ワイルドカード | 使用例 | 一致例 |
|:---|:---|:---|
|`*` (アスタリスク) <br/><br/> 任意の数の文字を置き換える | `C:\MyData\*` | によって開くすべてのファイル `C:\MyData\file.exe` |
|環境変数 <br/><br/> 定義された変数は、除外が評価される際にパスとして設定されます。 | `%ALLUSERSPROFILE%\CustomLogFiles\file.exe` | によって開くすべてのファイル `C:\ProgramData\CustomLogFiles\file.exe` |

## <a name="review-the-list-of-exclusions"></a>除外の一覧を確認する

除外リスト内のアイテムは、MpCmdRun、PowerShell、Microsoft [Endpoint Configuration Manager、Intune、](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings)または[Windows セキュリティ アプリで取得できます](microsoft-defender-security-center-antivirus.md)。 [](/intune/device-restrictions-configure)

PowerShell を使用する場合は、次の 2 つの方法でリストを取得できます。

- すべての Microsoft Defender ウイルス対策の基本設定の状態を取得します。 各リストは別々の行に表示されますが、各リスト内のアイテムは同じ行に結合されます。
- すべての基本設定の状態を変数に書き込み、その変数を使用して、関心のある特定のリストのみを呼び出します。 各使用は `Add-MpPreference` 、新しい行に書き込まれます。

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a>MpCmdRun を使用して除外リストを検証する

専用のコマンド ライン ツールを使用して除外を確認するには [mpcmdrun.exeコマンドを ](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)使用します。

```DOS
MpCmdRun.exe -CheckExclusion -path <path>
```

> [!NOTE]
> MpCmdRun で除外をチェックするには、Microsoft Defender Antivirus CAMP バージョン 4.18.1812.3 (2018 年 12 月リリース) 以降が必要です。


### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a>PowerShell を使用して、他のすべての Microsoft Defender ウイルス対策の基本設定と一緒に除外の一覧を確認する

次のコマンドレットを使用します。

```PowerShell
Get-MpPreference
```

[Microsoft Defender ウイルス対策で PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)を使用する方法の詳細については、「Use PowerShell コマンドレットを使用して Microsoft Defender Antivirus コマンドレットと[Defender](/powershell/module/defender)コマンドレットを構成および実行する」を参照してください。

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a>PowerShell を使用して特定の除外リストを取得する

次のコード スニペットを使用します (各行を個別のコマンドとして入力します)。 **WDAVprefs を変数** に名前を付けしたいラベルに置き換える:

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionProcess
```

[Microsoft Defender ウイルス対策で PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)を使用する方法の詳細については、「Use PowerShell コマンドレットを使用して Microsoft Defender Antivirus コマンドレットと[Defender](/powershell/module/defender)コマンドレットを構成および実行する」を参照してください。

## <a name="related-articles"></a>関連記事

- [Microsoft Defender ウイルス対策スキャンで除外を構成および検証する](configure-exclusions-microsoft-defender-antivirus.md)
- [ファイル名、拡張子、フォルダーの場所に基づいて除外を構成および検証する](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Windows Server で Microsoft Defender ウイルス対策の除外を構成する](configure-server-exclusions-microsoft-defender-antivirus.md)
- [除外を定義するときに回避する一般的な間違い](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策スキャンと修復の結果をカスタマイズ、開始、および確認する](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Windows 10 の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-in-windows-10.md)