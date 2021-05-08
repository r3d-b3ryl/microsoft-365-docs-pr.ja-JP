---
title: 特定のプロセスによって開いたファイルの除外を構成する
description: 特定のプロセスでファイルを開いている場合は、スキャンからファイルを除外できます。
keywords: Microsoft Defender ウイルス対策、プロセス、除外、ファイル、スキャン
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
ms.openlocfilehash: 2fdc646cf616ff6a6fa36a83be3d2b1dd0432fbe
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274618"
---
# <a name="configure-exclusions-for-files-opened-by-processes"></a><span data-ttu-id="99fee-104">プロセスによって開いたファイルの除外を構成する</span><span class="sxs-lookup"><span data-stu-id="99fee-104">Configure exclusions for files opened by processes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="99fee-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="99fee-105">**Applies to:**</span></span>

- [<span data-ttu-id="99fee-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="99fee-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="99fee-107">特定のプロセスによって開いたファイルを、特定のスキャンからMicrosoft Defender ウイルス対策できます。</span><span class="sxs-lookup"><span data-stu-id="99fee-107">You can exclude files that have been opened by specific processes from Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="99fee-108">除外 [リストを定義する前に、「除外を](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) 定義するための推奨事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99fee-108">See [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) before defining your exclusion lists.</span></span>

<span data-ttu-id="99fee-109">この記事では、除外リストを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="99fee-109">This article describes how to configure exclusion lists.</span></span> 

## <a name="examples-of-exclusions"></a><span data-ttu-id="99fee-110">除外の例</span><span class="sxs-lookup"><span data-stu-id="99fee-110">Examples of exclusions</span></span>

|<span data-ttu-id="99fee-111">除外</span><span class="sxs-lookup"><span data-stu-id="99fee-111">Exclusion</span></span> | <span data-ttu-id="99fee-112">例</span><span class="sxs-lookup"><span data-stu-id="99fee-112">Example</span></span> |
|---|---|
|<span data-ttu-id="99fee-113">特定のファイル名を持つ任意のプロセスによって開いたコンピューター上のファイル</span><span class="sxs-lookup"><span data-stu-id="99fee-113">Any file on the machine that is opened by any process with a specific file name</span></span> | <span data-ttu-id="99fee-114">指定すると `test.exe` 、次の方法で開いたファイルが除外されます。</span><span class="sxs-lookup"><span data-stu-id="99fee-114">Specifying `test.exe` would exclude files opened by:</span></span> <br/>`c:\sample\test.exe`<br/>`d:\internal\files\test.exe` |  
|<span data-ttu-id="99fee-115">特定のフォルダーの下の任意のプロセスによって開いたコンピューター上のファイル</span><span class="sxs-lookup"><span data-stu-id="99fee-115">Any file on the machine that is opened by any process under a specific folder</span></span> | <span data-ttu-id="99fee-116">指定すると `c:\test\sample\*` 、次の方法で開いたファイルが除外されます。</span><span class="sxs-lookup"><span data-stu-id="99fee-116">Specifying `c:\test\sample\*` would exclude files opened by:</span></span><br/>`c:\test\sample\test.exe`<br/>`c:\test\sample\test2.exe`<br/>`c:\test\sample\utility.exe` | 
|<span data-ttu-id="99fee-117">特定のフォルダー内の特定のプロセスによって開いたコンピューター上のすべてのファイル</span><span class="sxs-lookup"><span data-stu-id="99fee-117">Any file on the machine that is opened by a specific process in a specific folder</span></span> | <span data-ttu-id="99fee-118">指定すると `c:\test\process.exe` 、開いたファイルだけが除外されます。 `c:\test\process.exe`</span><span class="sxs-lookup"><span data-stu-id="99fee-118">Specifying `c:\test\process.exe` would exclude files only opened by `c:\test\process.exe`</span></span> |


<span data-ttu-id="99fee-119">プロセス除外リストにプロセスを追加すると、Microsoft Defender ウイルス対策場所に関係なく、そのプロセスで開いたファイルはスキャンされません。</span><span class="sxs-lookup"><span data-stu-id="99fee-119">When you add a process to the process exclusion list, Microsoft Defender Antivirus won't scan files opened by that process, no matter where the files are located.</span></span> <span data-ttu-id="99fee-120">ただし、ファイル除外リストにも追加されていない限り、プロセス自体 [がスキャンされます](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="99fee-120">The process itself, however, will be scanned unless it has also been added to the [file exclusion list](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="99fee-121">除外は、常時オン [のリアルタイム保護と監視にのみ適用されます](configure-real-time-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="99fee-121">The exclusions only apply to [always-on real-time protection and monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="99fee-122">スケジュールされたスキャンやオンデマンド スキャンには適用されません。</span><span class="sxs-lookup"><span data-stu-id="99fee-122">They don't apply to scheduled or on-demand scans.</span></span>

<span data-ttu-id="99fee-123">グループ ポリシーを使用して除外リストに加えた変更は **、** アプリのリストに [Windows セキュリティされます](microsoft-defender-security-center-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="99fee-123">Changes made with Group Policy to the exclusion lists **will show** in the lists in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span> <span data-ttu-id="99fee-124">ただし、アプリで行われた変更 **Windows セキュリティグループ** ポリシー の一覧には表示されない。</span><span class="sxs-lookup"><span data-stu-id="99fee-124">However, changes made in the Windows Security app **will not show** in the Group Policy lists.</span></span>

<span data-ttu-id="99fee-125">グループ ポリシー、Microsoft Endpoint Configuration Manager、Microsoft Intune、および Windows セキュリティ アプリで除外リストの追加、削除、および確認を行い、ワイルドカードを使用してリストをさらにカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="99fee-125">You can add, remove, and review the lists for exclusions in Group Policy, Microsoft Endpoint Configuration Manager, Microsoft Intune, and with the Windows Security app, and you can use wildcards to further customize the lists.</span></span>

<span data-ttu-id="99fee-126">PowerShell コマンドレットと WMI を使用して、リストの確認など、除外リストを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="99fee-126">You can also use PowerShell cmdlets and WMI to configure the exclusion lists, including reviewing your lists.</span></span>

<span data-ttu-id="99fee-127">既定では、リストに対して行われたローカルの変更 (管理者特権を持つユーザー、PowerShell と WMI で行われた変更) は、グループ ポリシー、Configuration Manager、または Intune によって定義された (展開された) リストと結合されます。</span><span class="sxs-lookup"><span data-stu-id="99fee-127">By default, local changes made to the lists (by users with administrator privileges; changes made with PowerShell and WMI) will be merged with the lists as defined (and deployed) by Group Policy, Configuration Manager, or Intune.</span></span> <span data-ttu-id="99fee-128">グループ ポリシーの一覧は、競合が発生した場合に優先されます。</span><span class="sxs-lookup"><span data-stu-id="99fee-128">The Group Policy lists will take precedence in the case of conflicts.</span></span>

<span data-ttu-id="99fee-129">ローカルで [定義された除外リスト](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) とグローバルに定義された除外リストの結合方法を構成して、ローカルの変更で管理展開設定を上書きできます。</span><span class="sxs-lookup"><span data-stu-id="99fee-129">You can [configure how locally and globally defined exclusions lists are merged](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) to allow local changes to override managed deployment settings.</span></span>

## <a name="configure-the-list-of-exclusions-for-files-opened-by-specified-processes"></a><span data-ttu-id="99fee-130">指定したプロセスによって開いたファイルの除外の一覧を構成する</span><span class="sxs-lookup"><span data-stu-id="99fee-130">Configure the list of exclusions for files opened by specified processes</span></span>

### <a name="use-microsoft-intune-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="99fee-131">指定Microsoft Intuneによって開いたファイルをスキャンから除外するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="99fee-131">Use Microsoft Intune to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="99fee-132">詳細[については、「デバイス制限](/intune/device-restrictions-configure)設定の構成」を参照Microsoft Intune Intune Microsoft Defender ウイルス対策デバイス制限設定Windows 10[デバイス](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)制限設定を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99fee-132">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

### <a name="use-microsoft-endpoint-manager-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="99fee-133">指定Microsoft エンドポイント マネージャーによって開いたファイルをスキャンから除外するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="99fee-133">Use Microsoft Endpoint Manager to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="99fee-134">詳細[については、「マルウェア対策ポリシーを作成](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings)して展開する方法: 除外設定」を参照Microsoft エンドポイント マネージャー (現在のブランチ)。</span><span class="sxs-lookup"><span data-stu-id="99fee-134">See [How to create and deploy antimalware policies: Exclusion settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) for details on configuring Microsoft Endpoint Manager (current branch).</span></span>

### <a name="use-group-policy-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="99fee-135">グループ ポリシーを使用して、指定したプロセスで開いたファイルをスキャンから除外する</span><span class="sxs-lookup"><span data-stu-id="99fee-135">Use Group Policy to exclude files that have been opened by specified processes from scans</span></span>

1. <span data-ttu-id="99fee-136">グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="99fee-136">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="99fee-137">グループ ポリシー **管理エディターで、[コンピューター** の構成] に **移動し、[** 管理用 **テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="99fee-137">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="99fee-138">ツリーを展開して、**除外Windowsコンポーネント> Microsoft Defender ウイルス対策 >展開します**。</span><span class="sxs-lookup"><span data-stu-id="99fee-138">Expand the tree to **Windows components > Microsoft Defender Antivirus > Exclusions**.</span></span>

4. <span data-ttu-id="99fee-139">[除外の処理 **] をダブルクリックし** 、除外を追加します。</span><span class="sxs-lookup"><span data-stu-id="99fee-139">Double-click **Process Exclusions** and add the exclusions:</span></span>

    1. <span data-ttu-id="99fee-140">オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="99fee-140">Set the option to **Enabled**.</span></span>
    2. <span data-ttu-id="99fee-141">[オプション] **セクションで** 、[ **表示.... をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="99fee-141">Under the **Options** section, click **Show...**.</span></span>
    3. <span data-ttu-id="99fee-142">[値名] 列の下に、各プロセス **を独自の行に入力** します。</span><span class="sxs-lookup"><span data-stu-id="99fee-142">Enter each process on its own line under the **Value name** column.</span></span> <span data-ttu-id="99fee-143">さまざまな種類のプロセスの除外については、例の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99fee-143">See the example table for the different types of process exclusions.</span></span>  <span data-ttu-id="99fee-144">すべての **プロセスの [** 値] **列に 0** を入力します。</span><span class="sxs-lookup"><span data-stu-id="99fee-144">Enter **0** in the **Value** column for all processes.</span></span>

5. <span data-ttu-id="99fee-145">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99fee-145">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="99fee-146">PowerShell コマンドレットを使用して、指定したプロセスで開いたファイルをスキャンから除外する</span><span class="sxs-lookup"><span data-stu-id="99fee-146">Use PowerShell cmdlets to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="99fee-147">PowerShell を使用してプロセスによって開いたファイルの除外を追加または削除するには、パラメーターと 3 つのコマンドレットを組み合わせて使用する必要 `-ExclusionProcess` があります。</span><span class="sxs-lookup"><span data-stu-id="99fee-147">Using PowerShell to add or remove exclusions for files that have been opened by processes requires using a combination of three cmdlets with the `-ExclusionProcess` parameter.</span></span> <span data-ttu-id="99fee-148">コマンドレットはすべて Defender モジュール [内です](/powershell/module/defender/)。</span><span class="sxs-lookup"><span data-stu-id="99fee-148">The cmdlets are all in the [Defender module](/powershell/module/defender/).</span></span>

<span data-ttu-id="99fee-149">コマンドレットの形式は次の形式です。</span><span class="sxs-lookup"><span data-stu-id="99fee-149">The format for the cmdlets is:</span></span>

```PowerShell
<cmdlet> -ExclusionProcess "<item>"
```

<span data-ttu-id="99fee-150">以下を次のように使用できます \<cmdlet> 。</span><span class="sxs-lookup"><span data-stu-id="99fee-150">The following are allowed as the \<cmdlet>:</span></span>

|<span data-ttu-id="99fee-151">構成アクション</span><span class="sxs-lookup"><span data-stu-id="99fee-151">Configuration action</span></span> | <span data-ttu-id="99fee-152">PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="99fee-152">PowerShell cmdlet</span></span> |
|---|---|
|<span data-ttu-id="99fee-153">リストを作成または上書きする</span><span class="sxs-lookup"><span data-stu-id="99fee-153">Create or overwrite the list</span></span> | `Set-MpPreference` |
|<span data-ttu-id="99fee-154">リストに追加する</span><span class="sxs-lookup"><span data-stu-id="99fee-154">Add to the list</span></span> | `Add-MpPreference` |
|<span data-ttu-id="99fee-155">リストからアイテムを削除する</span><span class="sxs-lookup"><span data-stu-id="99fee-155">Remove items from the list</span></span> | `Remove-MpPreference` |

>[!IMPORTANT]
><span data-ttu-id="99fee-156">コマンドレットを使用するか、または使用してリストを作成した場合は、 `Set-MpPreference` `Add-MpPreference` `Set-MpPreference` 既存のリストが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="99fee-156">If you have created a list, either with `Set-MpPreference` or `Add-MpPreference`, using the `Set-MpPreference` cmdlet again will overwrite the existing list.</span></span>

<span data-ttu-id="99fee-157">たとえば、次のコード スニペットを使用すると、Microsoft Defender AV スキャンによって、指定したプロセスで開いたファイルが除外されます。</span><span class="sxs-lookup"><span data-stu-id="99fee-157">For example, the following code snippet would cause Microsoft Defender AV scans to exclude any file that is opened by the specified process:</span></span>

```PowerShell
Add-MpPreference -ExclusionProcess "c:\internal\test.exe"
```

<span data-ttu-id="99fee-158">PowerShell と一緒に PowerShell を使用する方法Microsoft Defender ウイルス対策、「Manage antivirus with PowerShell コマンドレット」および「Microsoft Defender ウイルス対策[コマンドレット」を参照してください](/powershell/module/defender)。</span><span class="sxs-lookup"><span data-stu-id="99fee-158">For more information on how to use PowerShell with Microsoft Defender Antivirus, see Manage antivirus with PowerShell cmdlets and [Microsoft Defender Antivirus cmdlets](/powershell/module/defender).</span></span>

### <a name="use-windows-management-instruction-wmi-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="99fee-159">[Windows管理命令 (WMI) を使用して、指定したプロセスで開いたファイルをスキャンから除外する</span><span class="sxs-lookup"><span data-stu-id="99fee-159">Use Windows Management Instruction (WMI) to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="99fee-160">次の [**プロパティの\*\*\*\*クラスの** **Set メソッド、Add** **メソッド、Remove**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))メソッドMSFT_MpPreference使用します。</span><span class="sxs-lookup"><span data-stu-id="99fee-160">Use the [**Set**, **Add**, and **Remove** methods of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ExclusionProcess
```

<span data-ttu-id="99fee-161">**Set、Add、\*\*\*\*および** **Remove** の使用は、PowerShell の対応するユーザーと類似 `Set-MpPreference` しています。 `Add-MpPreference` `Remove-MpPreference`</span><span class="sxs-lookup"><span data-stu-id="99fee-161">The use of **Set**, **Add**, and **Remove** is analogous to their counterparts in PowerShell: `Set-MpPreference`, `Add-MpPreference`, and `Remove-MpPreference`.</span></span>

<span data-ttu-id="99fee-162">詳細および許可されるパラメーターについては[、「WMIv2 API Windows Defender参照してください](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。</span><span class="sxs-lookup"><span data-stu-id="99fee-162">For more information and allowed parameters, see  [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

### <a name="use-the-windows-security-app-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="99fee-163">指定したプロセスWindows セキュリティ開いたファイルをスキャンから除外するには、アプリアプリを使用します。</span><span class="sxs-lookup"><span data-stu-id="99fee-163">Use the Windows Security app to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="99fee-164">手順[については、「アプリの除外をWindows セキュリティする」](microsoft-defender-security-center-antivirus.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99fee-164">See [Add exclusions in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions.</span></span>

## <a name="use-wildcards-in-the-process-exclusion-list"></a><span data-ttu-id="99fee-165">プロセス除外リストでワイルドカードを使用する</span><span class="sxs-lookup"><span data-stu-id="99fee-165">Use wildcards in the process exclusion list</span></span>

<span data-ttu-id="99fee-166">プロセス除外リストでのワイルドカードの使用は、他の除外リストでのワイルドカードの使用とは異なります。</span><span class="sxs-lookup"><span data-stu-id="99fee-166">The use of wildcards in the process exclusion list is different from their use in other exclusion lists.</span></span>

<span data-ttu-id="99fee-167">特に、疑問符 ( ) ワイルドカードは使用できません。アスタリスク ( ) ワイルドカードは完全なパスの最後 `?` `*` でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="99fee-167">In particular, you cannot use the question mark (`?`) wildcard, and the asterisk (`*`) wildcard can only be used at the end of a complete path.</span></span> <span data-ttu-id="99fee-168">プロセス除外リストで項目を定義する場合は、ワイルドカードとして環境変数 ( `%ALLUSERSPROFILE%` など) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="99fee-168">You can still use environment variables (such as `%ALLUSERSPROFILE%`) as wildcards when defining items in the process exclusion list.</span></span>

<span data-ttu-id="99fee-169">次の表に、プロセス除外リストでワイルドカードを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="99fee-169">The following table describes how the wildcards can be used in the process exclusion list:</span></span>

|<span data-ttu-id="99fee-170">ワイルドカード</span><span class="sxs-lookup"><span data-stu-id="99fee-170">Wildcard</span></span> | <span data-ttu-id="99fee-171">使用例</span><span class="sxs-lookup"><span data-stu-id="99fee-171">Example use</span></span> | <span data-ttu-id="99fee-172">一致例</span><span class="sxs-lookup"><span data-stu-id="99fee-172">Example matches</span></span> |
|:---|:---|:---|
|<span data-ttu-id="99fee-173">`*` (アスタリスク)</span><span class="sxs-lookup"><span data-stu-id="99fee-173">`*` (asterisk)</span></span> <br/><br/> <span data-ttu-id="99fee-174">任意の数の文字を置き換える</span><span class="sxs-lookup"><span data-stu-id="99fee-174">Replaces any number of characters</span></span> | `C:\MyData\*` | <span data-ttu-id="99fee-175">によって開くすべてのファイル `C:\MyData\file.exe`</span><span class="sxs-lookup"><span data-stu-id="99fee-175">Any file opened by `C:\MyData\file.exe`</span></span> |
|<span data-ttu-id="99fee-176">環境変数</span><span class="sxs-lookup"><span data-stu-id="99fee-176">Environment variables</span></span> <br/><br/> <span data-ttu-id="99fee-177">定義された変数は、除外が評価される際にパスとして設定されます。</span><span class="sxs-lookup"><span data-stu-id="99fee-177">The defined variable is populated as a path when the exclusion is evaluated</span></span> | `%ALLUSERSPROFILE%\CustomLogFiles\file.exe` | <span data-ttu-id="99fee-178">によって開くすべてのファイル `C:\ProgramData\CustomLogFiles\file.exe`</span><span class="sxs-lookup"><span data-stu-id="99fee-178">Any file opened by `C:\ProgramData\CustomLogFiles\file.exe`</span></span> |

## <a name="review-the-list-of-exclusions"></a><span data-ttu-id="99fee-179">除外の一覧を確認する</span><span class="sxs-lookup"><span data-stu-id="99fee-179">Review the list of exclusions</span></span>

<span data-ttu-id="99fee-180">除外リストのアイテムは、MpCmdRun、PowerShell、Microsoft Endpoint Configuration Manager、Intune、またはアプリWindows セキュリティ[できます](microsoft-defender-security-center-antivirus.md)。 [](/intune/device-restrictions-configure) [](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings)</span><span class="sxs-lookup"><span data-stu-id="99fee-180">You can retrieve the items in the exclusion list with MpCmdRun, PowerShell, [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings), [Intune](/intune/device-restrictions-configure), or the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

<span data-ttu-id="99fee-181">PowerShell を使用する場合は、次の 2 つの方法でリストを取得できます。</span><span class="sxs-lookup"><span data-stu-id="99fee-181">If you use PowerShell, you can retrieve the list in two ways:</span></span>

- <span data-ttu-id="99fee-182">すべてのユーザー設定のMicrosoft Defender ウイルス対策します。</span><span class="sxs-lookup"><span data-stu-id="99fee-182">Retrieve the status of all Microsoft Defender Antivirus preferences.</span></span> <span data-ttu-id="99fee-183">各リストは別々の行に表示されますが、各リスト内のアイテムは同じ行に結合されます。</span><span class="sxs-lookup"><span data-stu-id="99fee-183">Each of the lists will be displayed on separate lines, but the items within each list will be combined into the same line.</span></span>
- <span data-ttu-id="99fee-184">すべての基本設定の状態を変数に書き込み、その変数を使用して、関心のある特定のリストのみを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="99fee-184">Write the status of all preferences to a variable, and use that variable to only call the specific list you are interested in.</span></span> <span data-ttu-id="99fee-185">各使用は `Add-MpPreference` 、新しい行に書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="99fee-185">Each use of `Add-MpPreference` is written to a new line.</span></span>

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a><span data-ttu-id="99fee-186">MpCmdRun を使用して除外リストを検証する</span><span class="sxs-lookup"><span data-stu-id="99fee-186">Validate the exclusion list by using MpCmdRun</span></span>

<span data-ttu-id="99fee-187">専用のコマンド ライン ツールを使用して除外を確認するには [mpcmdrun.exeコマンドを ](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)使用します。</span><span class="sxs-lookup"><span data-stu-id="99fee-187">To check exclusions with the dedicated [command-line tool mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options), use the following command:</span></span>

```DOS
MpCmdRun.exe -CheckExclusion -path <path>
```

> [!NOTE]
> <span data-ttu-id="99fee-188">MpCmdRun で除外をチェックするには、Microsoft Defender ウイルス対策 CAMP バージョン 4.18.1812.3 (2018 年 12 月にリリース) 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="99fee-188">Checking exclusions with MpCmdRun requires Microsoft Defender Antivirus CAMP version 4.18.1812.3 (released in December 2018) or later.</span></span>


### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a><span data-ttu-id="99fee-189">PowerShell を使用して、他のすべてのユーザー設定とMicrosoft Defender ウイルス対策一覧を確認する</span><span class="sxs-lookup"><span data-stu-id="99fee-189">Review the list of exclusions alongside all other Microsoft Defender Antivirus preferences by using PowerShell</span></span>

<span data-ttu-id="99fee-190">次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="99fee-190">Use the following cmdlet:</span></span>

```PowerShell
Get-MpPreference
```

<span data-ttu-id="99fee-191">PowerShell[コマンドレットを](use-powershell-cmdlets-microsoft-defender-antivirus.md)構成して実行する方法の詳細については、「powerShell コマンドレットを使用して Microsoft Defender ウイルス対策 および[Defender](/powershell/module/defender)コマンドレットを構成および実行する」を参照Microsoft Defender ウイルス対策。</span><span class="sxs-lookup"><span data-stu-id="99fee-191">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a><span data-ttu-id="99fee-192">PowerShell を使用して特定の除外リストを取得する</span><span class="sxs-lookup"><span data-stu-id="99fee-192">Retrieve a specific exclusions list by using PowerShell</span></span>

<span data-ttu-id="99fee-193">次のコード スニペットを使用します (各行を個別のコマンドとして入力します)。 **WDAVprefs を変数** に名前を付けしたいラベルに置き換える:</span><span class="sxs-lookup"><span data-stu-id="99fee-193">Use the following code snippet (enter each line as a separate command); replace **WDAVprefs** with whatever label you want to name the variable:</span></span>

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionProcess
```

<span data-ttu-id="99fee-194">PowerShell[コマンドレットを](use-powershell-cmdlets-microsoft-defender-antivirus.md)構成して実行する方法の詳細については、「powerShell コマンドレットを使用して Microsoft Defender ウイルス対策 および[Defender](/powershell/module/defender)コマンドレットを構成および実行する」を参照Microsoft Defender ウイルス対策。</span><span class="sxs-lookup"><span data-stu-id="99fee-194">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="related-articles"></a><span data-ttu-id="99fee-195">関連記事</span><span class="sxs-lookup"><span data-stu-id="99fee-195">Related articles</span></span>

- [<span data-ttu-id="99fee-196">カスタム スキャンで除外を構成Microsoft Defender ウイルス対策する</span><span class="sxs-lookup"><span data-stu-id="99fee-196">Configure and validate exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="99fee-197">ファイル名、拡張子、フォルダーの場所に基づいて除外を構成および検証する</span><span class="sxs-lookup"><span data-stu-id="99fee-197">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="99fee-198">サーバー Microsoft Defender ウイルス対策の除外をWindowsする</span><span class="sxs-lookup"><span data-stu-id="99fee-198">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="99fee-199">除外を定義する際に避ける必要のある一般的な間違い</span><span class="sxs-lookup"><span data-stu-id="99fee-199">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [<span data-ttu-id="99fee-200">スキャンと修復の結果をカスタマイズ、開始Microsoft Defender ウイルス対策確認する</span><span class="sxs-lookup"><span data-stu-id="99fee-200">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="99fee-201">Windows 10 の Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="99fee-201">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)