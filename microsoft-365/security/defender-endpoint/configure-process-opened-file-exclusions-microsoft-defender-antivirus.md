---
title: 特定のプロセスによって開いたファイルの除外を構成する
description: 特定のプロセスでファイルを開いている場合は、スキャンからファイルを除外できます。
keywords: Microsoft Defender ウイルス対策、プロセス、除外、ファイル、スキャン
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 94375bc843c6512616d49345bcc9e7f63899a708
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765085"
---
# <a name="configure-exclusions-for-files-opened-by-processes"></a><span data-ttu-id="999e4-104">プロセスによって開いたファイルの除外を構成する</span><span class="sxs-lookup"><span data-stu-id="999e4-104">Configure exclusions for files opened by processes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="999e4-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="999e4-105">**Applies to:**</span></span>

- [<span data-ttu-id="999e4-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="999e4-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="999e4-107">特定のプロセスで開いたファイルは、Microsoft Defender ウイルス対策スキャンから除外できます。</span><span class="sxs-lookup"><span data-stu-id="999e4-107">You can exclude files that have been opened by specific processes from Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="999e4-108">除外 [リストを定義する前に、「除外を](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) 定義するための推奨事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="999e4-108">See [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) before defining your exclusion lists.</span></span>

<span data-ttu-id="999e4-109">この記事では、除外リストを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="999e4-109">This article describes how to configure exclusion lists.</span></span> 

## <a name="examples-of-exclusions"></a><span data-ttu-id="999e4-110">除外の例</span><span class="sxs-lookup"><span data-stu-id="999e4-110">Examples of exclusions</span></span>

|<span data-ttu-id="999e4-111">除外</span><span class="sxs-lookup"><span data-stu-id="999e4-111">Exclusion</span></span> | <span data-ttu-id="999e4-112">例</span><span class="sxs-lookup"><span data-stu-id="999e4-112">Example</span></span> |
|---|---|
|<span data-ttu-id="999e4-113">特定のファイル名を持つ任意のプロセスによって開いたコンピューター上のファイル</span><span class="sxs-lookup"><span data-stu-id="999e4-113">Any file on the machine that is opened by any process with a specific file name</span></span> | <span data-ttu-id="999e4-114">指定すると `test.exe` 、次の方法で開いたファイルが除外されます。</span><span class="sxs-lookup"><span data-stu-id="999e4-114">Specifying `test.exe` would exclude files opened by:</span></span> <br/>`c:\sample\test.exe`<br/>`d:\internal\files\test.exe` |  
|<span data-ttu-id="999e4-115">特定のフォルダーの下の任意のプロセスによって開いたコンピューター上のファイル</span><span class="sxs-lookup"><span data-stu-id="999e4-115">Any file on the machine that is opened by any process under a specific folder</span></span> | <span data-ttu-id="999e4-116">指定すると `c:\test\sample\*` 、次の方法で開いたファイルが除外されます。</span><span class="sxs-lookup"><span data-stu-id="999e4-116">Specifying `c:\test\sample\*` would exclude files opened by:</span></span><br/>`c:\test\sample\test.exe`<br/>`c:\test\sample\test2.exe`<br/>`c:\test\sample\utility.exe` | 
|<span data-ttu-id="999e4-117">特定のフォルダー内の特定のプロセスによって開いたコンピューター上のすべてのファイル</span><span class="sxs-lookup"><span data-stu-id="999e4-117">Any file on the machine that is opened by a specific process in a specific folder</span></span> | <span data-ttu-id="999e4-118">指定すると `c:\test\process.exe` 、開いたファイルだけが除外されます。 `c:\test\process.exe`</span><span class="sxs-lookup"><span data-stu-id="999e4-118">Specifying `c:\test\process.exe` would exclude files only opened by `c:\test\process.exe`</span></span> |


<span data-ttu-id="999e4-119">プロセス除外リストにプロセスを追加しても、ファイルの場所に関係なく、そのプロセスで開いたファイルはスキャンされません。</span><span class="sxs-lookup"><span data-stu-id="999e4-119">When you add a process to the process exclusion list, Microsoft Defender Antivirus won't scan files opened by that process, no matter where the files are located.</span></span> <span data-ttu-id="999e4-120">ただし、ファイル除外リストにも追加されていない限り、プロセス自体 [がスキャンされます](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="999e4-120">The process itself, however, will be scanned unless it has also been added to the [file exclusion list](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="999e4-121">除外は、常時オン [のリアルタイム保護と監視にのみ適用されます](configure-real-time-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="999e4-121">The exclusions only apply to [always-on real-time protection and monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="999e4-122">スケジュールされたスキャンやオンデマンド スキャンには適用されません。</span><span class="sxs-lookup"><span data-stu-id="999e4-122">They don't apply to scheduled or on-demand scans.</span></span>

<span data-ttu-id="999e4-123">グループ ポリシーを使用して除外リストに加えた変更 **は、Windows** セキュリティ アプリのリスト [に表示されます](microsoft-defender-security-center-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="999e4-123">Changes made with Group Policy to the exclusion lists **will show** in the lists in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span> <span data-ttu-id="999e4-124">ただし、Windows セキュリティ アプリで行われた変更 **は、グループ** ポリシー リストには表示されない。</span><span class="sxs-lookup"><span data-stu-id="999e4-124">However, changes made in the Windows Security app **will not show** in the Group Policy lists.</span></span>

<span data-ttu-id="999e4-125">グループ ポリシー、Microsoft Endpoint Configuration Manager、Microsoft Intune、および Windows セキュリティ アプリで除外リストの追加、削除、および確認を行い、ワイルドカードを使用してリストをさらにカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="999e4-125">You can add, remove, and review the lists for exclusions in Group Policy, Microsoft Endpoint Configuration Manager, Microsoft Intune, and with the Windows Security app, and you can use wildcards to further customize the lists.</span></span>

<span data-ttu-id="999e4-126">PowerShell コマンドレットと WMI を使用して、リストの確認など、除外リストを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="999e4-126">You can also use PowerShell cmdlets and WMI to configure the exclusion lists, including reviewing your lists.</span></span>

<span data-ttu-id="999e4-127">既定では、リストに対して行われたローカルの変更 (管理者特権を持つユーザー、PowerShell と WMI で行われた変更) は、グループ ポリシー、Configuration Manager、または Intune によって定義された (展開された) リストと結合されます。</span><span class="sxs-lookup"><span data-stu-id="999e4-127">By default, local changes made to the lists (by users with administrator privileges; changes made with PowerShell and WMI) will be merged with the lists as defined (and deployed) by Group Policy, Configuration Manager, or Intune.</span></span> <span data-ttu-id="999e4-128">グループ ポリシーの一覧は、競合が発生した場合に優先されます。</span><span class="sxs-lookup"><span data-stu-id="999e4-128">The Group Policy lists will take precedence in the case of conflicts.</span></span>

<span data-ttu-id="999e4-129">ローカルで [定義された除外リスト](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) とグローバルに定義された除外リストの結合方法を構成して、ローカルの変更で管理展開設定を上書きできます。</span><span class="sxs-lookup"><span data-stu-id="999e4-129">You can [configure how locally and globally defined exclusions lists are merged](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) to allow local changes to override managed deployment settings.</span></span>

## <a name="configure-the-list-of-exclusions-for-files-opened-by-specified-processes"></a><span data-ttu-id="999e4-130">指定したプロセスによって開いたファイルの除外の一覧を構成する</span><span class="sxs-lookup"><span data-stu-id="999e4-130">Configure the list of exclusions for files opened by specified processes</span></span>

### <a name="use-microsoft-intune-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="999e4-131">Microsoft Intune を使用して、指定したプロセスで開いたファイルをスキャンから除外する</span><span class="sxs-lookup"><span data-stu-id="999e4-131">Use Microsoft Intune to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="999e4-132">詳細 [については、「Configure device Restriction settings in Microsoft Intune」](/intune/device-restrictions-configure) および [「Microsoft Defender Antivirus device Restriction settings for Windows 10 in Intune」](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="999e4-132">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

### <a name="use-microsoft-endpoint-manager-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="999e4-133">Microsoft Endpoint Manager を使用して、指定したプロセスで開いたファイルをスキャンから除外する</span><span class="sxs-lookup"><span data-stu-id="999e4-133">Use Microsoft Endpoint Manager to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="999e4-134">Microsoft Endpoint Manager ( [現在の](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) ブランチ) の構成の詳細については、「マルウェア対策ポリシーを作成して展開する方法: 除外設定」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="999e4-134">See [How to create and deploy antimalware policies: Exclusion settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) for details on configuring Microsoft Endpoint Manager (current branch).</span></span>

### <a name="use-group-policy-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="999e4-135">グループ ポリシーを使用して、指定したプロセスで開いたファイルをスキャンから除外する</span><span class="sxs-lookup"><span data-stu-id="999e4-135">Use Group Policy to exclude files that have been opened by specified processes from scans</span></span>

1. <span data-ttu-id="999e4-136">グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="999e4-136">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="999e4-137">グループ ポリシー **管理エディターで、[コンピューター** の構成] に **移動し、[** 管理用 **テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="999e4-137">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="999e4-138">ツリーを **Microsoft Defender ウイルス対策と除外> Windows コンポーネント>展開します**。</span><span class="sxs-lookup"><span data-stu-id="999e4-138">Expand the tree to **Windows components > Microsoft Defender Antivirus > Exclusions**.</span></span>

4. <span data-ttu-id="999e4-139">[除外の処理 **] をダブルクリックし** 、除外を追加します。</span><span class="sxs-lookup"><span data-stu-id="999e4-139">Double-click **Process Exclusions** and add the exclusions:</span></span>

    1. <span data-ttu-id="999e4-140">オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="999e4-140">Set the option to **Enabled**.</span></span>
    2. <span data-ttu-id="999e4-141">[オプション] **セクションで** 、[ **表示.... をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="999e4-141">Under the **Options** section, click **Show...**.</span></span>
    3. <span data-ttu-id="999e4-142">[値名] 列の下に、各プロセス **を独自の行に入力** します。</span><span class="sxs-lookup"><span data-stu-id="999e4-142">Enter each process on its own line under the **Value name** column.</span></span> <span data-ttu-id="999e4-143">さまざまな種類のプロセスの除外については、例の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="999e4-143">See the example table for the different types of process exclusions.</span></span>  <span data-ttu-id="999e4-144">すべての **プロセスの [** 値] **列に 0** を入力します。</span><span class="sxs-lookup"><span data-stu-id="999e4-144">Enter **0** in the **Value** column for all processes.</span></span>

5. <span data-ttu-id="999e4-145">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="999e4-145">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="999e4-146">PowerShell コマンドレットを使用して、指定したプロセスで開いたファイルをスキャンから除外する</span><span class="sxs-lookup"><span data-stu-id="999e4-146">Use PowerShell cmdlets to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="999e4-147">PowerShell を使用してプロセスによって開いたファイルの除外を追加または削除するには、パラメーターと 3 つのコマンドレットを組み合わせて使用する必要 `-ExclusionProcess` があります。</span><span class="sxs-lookup"><span data-stu-id="999e4-147">Using PowerShell to add or remove exclusions for files that have been opened by processes requires using a combination of three cmdlets with the `-ExclusionProcess` parameter.</span></span> <span data-ttu-id="999e4-148">コマンドレットはすべて Defender モジュール [内です](/powershell/module/defender/)。</span><span class="sxs-lookup"><span data-stu-id="999e4-148">The cmdlets are all in the [Defender module](/powershell/module/defender/).</span></span>

<span data-ttu-id="999e4-149">コマンドレットの形式は次の形式です。</span><span class="sxs-lookup"><span data-stu-id="999e4-149">The format for the cmdlets is:</span></span>

```PowerShell
<cmdlet> -ExclusionProcess "<item>"
```

<span data-ttu-id="999e4-150">以下を次のように使用できます \<cmdlet> 。</span><span class="sxs-lookup"><span data-stu-id="999e4-150">The following are allowed as the \<cmdlet>:</span></span>

|<span data-ttu-id="999e4-151">構成アクション</span><span class="sxs-lookup"><span data-stu-id="999e4-151">Configuration action</span></span> | <span data-ttu-id="999e4-152">PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="999e4-152">PowerShell cmdlet</span></span> |
|---|---|
|<span data-ttu-id="999e4-153">リストを作成または上書きする</span><span class="sxs-lookup"><span data-stu-id="999e4-153">Create or overwrite the list</span></span> | `Set-MpPreference` |
|<span data-ttu-id="999e4-154">リストに追加する</span><span class="sxs-lookup"><span data-stu-id="999e4-154">Add to the list</span></span> | `Add-MpPreference` |
|<span data-ttu-id="999e4-155">リストからアイテムを削除する</span><span class="sxs-lookup"><span data-stu-id="999e4-155">Remove items from the list</span></span> | `Remove-MpPreference` |

>[!IMPORTANT]
><span data-ttu-id="999e4-156">コマンドレットを使用するか、または使用してリストを作成した場合は、 `Set-MpPreference` `Add-MpPreference` `Set-MpPreference` 既存のリストが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="999e4-156">If you have created a list, either with `Set-MpPreference` or `Add-MpPreference`, using the `Set-MpPreference` cmdlet again will overwrite the existing list.</span></span>

<span data-ttu-id="999e4-157">たとえば、次のコード スニペットを使用すると、Microsoft Defender AV スキャンによって、指定したプロセスで開いたファイルが除外されます。</span><span class="sxs-lookup"><span data-stu-id="999e4-157">For example, the following code snippet would cause Microsoft Defender AV scans to exclude any file that is opened by the specified process:</span></span>

```PowerShell
Add-MpPreference -ExclusionProcess "c:\internal\test.exe"
```

<span data-ttu-id="999e4-158">Microsoft Defender Antivirus で PowerShell を使用する方法の詳細については、「Manage antivirus with PowerShell コマンドレット」および [「Microsoft Defender Antivirus コマンドレット」を参照してください](/powershell/module/defender)。</span><span class="sxs-lookup"><span data-stu-id="999e4-158">For more information on how to use PowerShell with Microsoft Defender Antivirus, see Manage antivirus with PowerShell cmdlets and [Microsoft Defender Antivirus cmdlets](/powershell/module/defender).</span></span>

### <a name="use-windows-management-instruction-wmi-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="999e4-159">Windows 管理命令 (WMI) を使用して、指定したプロセスで開いたファイルをスキャンから除外する</span><span class="sxs-lookup"><span data-stu-id="999e4-159">Use Windows Management Instruction (WMI) to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="999e4-160">次の [**プロパティの\*\*\*\*クラスの** **Set メソッド、Add** **メソッド、Remove**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))メソッドMSFT_MpPreference使用します。</span><span class="sxs-lookup"><span data-stu-id="999e4-160">Use the [**Set**, **Add**, and **Remove** methods of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ExclusionProcess
```

<span data-ttu-id="999e4-161">**Set、Add、\*\*\*\*および** **Remove** の使用は、PowerShell の対応するユーザーと類似 `Set-MpPreference` しています。 `Add-MpPreference` `Remove-MpPreference`</span><span class="sxs-lookup"><span data-stu-id="999e4-161">The use of **Set**, **Add**, and **Remove** is analogous to their counterparts in PowerShell: `Set-MpPreference`, `Add-MpPreference`, and `Remove-MpPreference`.</span></span>

<span data-ttu-id="999e4-162">詳細および許可されるパラメーターについては  [、「WMIv2 API のWindows Defender参照してください](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。</span><span class="sxs-lookup"><span data-stu-id="999e4-162">For more information and allowed parameters, see  [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

### <a name="use-the-windows-security-app-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="999e4-163">Windows セキュリティ アプリを使用して、指定したプロセスで開いたファイルをスキャンから除外する</span><span class="sxs-lookup"><span data-stu-id="999e4-163">Use the Windows Security app to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="999e4-164">手順 [については、「Windows セキュリティ アプリで除外を追加する」](microsoft-defender-security-center-antivirus.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="999e4-164">See [Add exclusions in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions.</span></span>

## <a name="use-wildcards-in-the-process-exclusion-list"></a><span data-ttu-id="999e4-165">プロセス除外リストでワイルドカードを使用する</span><span class="sxs-lookup"><span data-stu-id="999e4-165">Use wildcards in the process exclusion list</span></span>

<span data-ttu-id="999e4-166">プロセス除外リストでのワイルドカードの使用は、他の除外リストでのワイルドカードの使用とは異なります。</span><span class="sxs-lookup"><span data-stu-id="999e4-166">The use of wildcards in the process exclusion list is different from their use in other exclusion lists.</span></span>

<span data-ttu-id="999e4-167">特に、疑問符 ( ) ワイルドカードは使用できません。アスタリスク ( ) ワイルドカードは完全なパスの最後 `?` `*` でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="999e4-167">In particular, you cannot use the question mark (`?`) wildcard, and the asterisk (`*`) wildcard can only be used at the end of a complete path.</span></span> <span data-ttu-id="999e4-168">プロセス除外リストで項目を定義する場合は、ワイルドカードとして環境変数 ( `%ALLUSERSPROFILE%` など) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="999e4-168">You can still use environment variables (such as `%ALLUSERSPROFILE%`) as wildcards when defining items in the process exclusion list.</span></span>

<span data-ttu-id="999e4-169">次の表に、プロセス除外リストでワイルドカードを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="999e4-169">The following table describes how the wildcards can be used in the process exclusion list:</span></span>

|<span data-ttu-id="999e4-170">ワイルドカード</span><span class="sxs-lookup"><span data-stu-id="999e4-170">Wildcard</span></span> | <span data-ttu-id="999e4-171">使用例</span><span class="sxs-lookup"><span data-stu-id="999e4-171">Example use</span></span> | <span data-ttu-id="999e4-172">一致例</span><span class="sxs-lookup"><span data-stu-id="999e4-172">Example matches</span></span> |
|:---|:---|:---|
|<span data-ttu-id="999e4-173">`*` (アスタリスク)</span><span class="sxs-lookup"><span data-stu-id="999e4-173">`*` (asterisk)</span></span> <br/><br/> <span data-ttu-id="999e4-174">任意の数の文字を置き換える</span><span class="sxs-lookup"><span data-stu-id="999e4-174">Replaces any number of characters</span></span> | `C:\MyData\*` | <span data-ttu-id="999e4-175">によって開くすべてのファイル `C:\MyData\file.exe`</span><span class="sxs-lookup"><span data-stu-id="999e4-175">Any file opened by `C:\MyData\file.exe`</span></span> |
|<span data-ttu-id="999e4-176">環境変数</span><span class="sxs-lookup"><span data-stu-id="999e4-176">Environment variables</span></span> <br/><br/> <span data-ttu-id="999e4-177">定義された変数は、除外が評価される際にパスとして設定されます。</span><span class="sxs-lookup"><span data-stu-id="999e4-177">The defined variable is populated as a path when the exclusion is evaluated</span></span> | `%ALLUSERSPROFILE%\CustomLogFiles\file.exe` | <span data-ttu-id="999e4-178">によって開くすべてのファイル `C:\ProgramData\CustomLogFiles\file.exe`</span><span class="sxs-lookup"><span data-stu-id="999e4-178">Any file opened by `C:\ProgramData\CustomLogFiles\file.exe`</span></span> |

## <a name="review-the-list-of-exclusions"></a><span data-ttu-id="999e4-179">除外の一覧を確認する</span><span class="sxs-lookup"><span data-stu-id="999e4-179">Review the list of exclusions</span></span>

<span data-ttu-id="999e4-180">除外リスト内のアイテムは、MpCmdRun、PowerShell、Microsoft [Endpoint Configuration Manager、Intune、](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings)または[Windows セキュリティ アプリで取得できます](microsoft-defender-security-center-antivirus.md)。 [](/intune/device-restrictions-configure)</span><span class="sxs-lookup"><span data-stu-id="999e4-180">You can retrieve the items in the exclusion list with MpCmdRun, PowerShell, [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings), [Intune](/intune/device-restrictions-configure), or the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

<span data-ttu-id="999e4-181">PowerShell を使用する場合は、次の 2 つの方法でリストを取得できます。</span><span class="sxs-lookup"><span data-stu-id="999e4-181">If you use PowerShell, you can retrieve the list in two ways:</span></span>

- <span data-ttu-id="999e4-182">すべての Microsoft Defender ウイルス対策の基本設定の状態を取得します。</span><span class="sxs-lookup"><span data-stu-id="999e4-182">Retrieve the status of all Microsoft Defender Antivirus preferences.</span></span> <span data-ttu-id="999e4-183">各リストは別々の行に表示されますが、各リスト内のアイテムは同じ行に結合されます。</span><span class="sxs-lookup"><span data-stu-id="999e4-183">Each of the lists will be displayed on separate lines, but the items within each list will be combined into the same line.</span></span>
- <span data-ttu-id="999e4-184">すべての基本設定の状態を変数に書き込み、その変数を使用して、関心のある特定のリストのみを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="999e4-184">Write the status of all preferences to a variable, and use that variable to only call the specific list you are interested in.</span></span> <span data-ttu-id="999e4-185">各使用は `Add-MpPreference` 、新しい行に書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="999e4-185">Each use of `Add-MpPreference` is written to a new line.</span></span>

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a><span data-ttu-id="999e4-186">MpCmdRun を使用して除外リストを検証する</span><span class="sxs-lookup"><span data-stu-id="999e4-186">Validate the exclusion list by using MpCmdRun</span></span>

<span data-ttu-id="999e4-187">専用のコマンド ライン ツールを使用して除外を確認するには [mpcmdrun.exeコマンドを ](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)使用します。</span><span class="sxs-lookup"><span data-stu-id="999e4-187">To check exclusions with the dedicated [command-line tool mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options), use the following command:</span></span>

```DOS
MpCmdRun.exe -CheckExclusion -path <path>
```

> [!NOTE]
> <span data-ttu-id="999e4-188">MpCmdRun で除外をチェックするには、Microsoft Defender Antivirus CAMP バージョン 4.18.1812.3 (2018 年 12 月リリース) 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="999e4-188">Checking exclusions with MpCmdRun requires Microsoft Defender Antivirus CAMP version 4.18.1812.3 (released in December 2018) or later.</span></span>


### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a><span data-ttu-id="999e4-189">PowerShell を使用して、他のすべての Microsoft Defender ウイルス対策の基本設定と一緒に除外の一覧を確認する</span><span class="sxs-lookup"><span data-stu-id="999e4-189">Review the list of exclusions alongside all other Microsoft Defender Antivirus preferences by using PowerShell</span></span>

<span data-ttu-id="999e4-190">次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="999e4-190">Use the following cmdlet:</span></span>

```PowerShell
Get-MpPreference
```

<span data-ttu-id="999e4-191">[Microsoft Defender ウイルス対策で PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)を使用する方法の詳細については、「Use PowerShell コマンドレットを使用して Microsoft Defender Antivirus コマンドレットと[Defender](/powershell/module/defender)コマンドレットを構成および実行する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="999e4-191">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a><span data-ttu-id="999e4-192">PowerShell を使用して特定の除外リストを取得する</span><span class="sxs-lookup"><span data-stu-id="999e4-192">Retrieve a specific exclusions list by using PowerShell</span></span>

<span data-ttu-id="999e4-193">次のコード スニペットを使用します (各行を個別のコマンドとして入力します)。 **WDAVprefs を変数** に名前を付けしたいラベルに置き換える:</span><span class="sxs-lookup"><span data-stu-id="999e4-193">Use the following code snippet (enter each line as a separate command); replace **WDAVprefs** with whatever label you want to name the variable:</span></span>

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionProcess
```

<span data-ttu-id="999e4-194">[Microsoft Defender ウイルス対策で PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)を使用する方法の詳細については、「Use PowerShell コマンドレットを使用して Microsoft Defender Antivirus コマンドレットと[Defender](/powershell/module/defender)コマンドレットを構成および実行する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="999e4-194">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="related-articles"></a><span data-ttu-id="999e4-195">関連記事</span><span class="sxs-lookup"><span data-stu-id="999e4-195">Related articles</span></span>

- [<span data-ttu-id="999e4-196">Microsoft Defender ウイルス対策スキャンで除外を構成および検証する</span><span class="sxs-lookup"><span data-stu-id="999e4-196">Configure and validate exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="999e4-197">ファイル名、拡張子、フォルダーの場所に基づいて除外を構成および検証する</span><span class="sxs-lookup"><span data-stu-id="999e4-197">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="999e4-198">Windows Server で Microsoft Defender ウイルス対策の除外を構成する</span><span class="sxs-lookup"><span data-stu-id="999e4-198">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="999e4-199">除外を定義するときに回避する一般的な間違い</span><span class="sxs-lookup"><span data-stu-id="999e4-199">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [<span data-ttu-id="999e4-200">Microsoft Defender ウイルス対策スキャンと修復の結果をカスタマイズ、開始、および確認する</span><span class="sxs-lookup"><span data-stu-id="999e4-200">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="999e4-201">Windows 10 の Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="999e4-201">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)