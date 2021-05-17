---
title: 制御されたフォルダー アクセスを有効にする
keywords: フォルダー アクセスの制御、Windows 10、Windows Defender、ランサムウェア、保護、ファイル、フォルダー、有効化、オン、使用
description: フォルダー アクセスの制御を有効にすることで重要なファイルを保護する方法について説明します。
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: ee87ac3bdfe88596a5f1625904af53499488f35f
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51571010"
---
# <a name="enable-controlled-folder-access"></a><span data-ttu-id="e621b-104">制御されたフォルダー アクセスを有効にする</span><span class="sxs-lookup"><span data-stu-id="e621b-104">Enable controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e621b-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e621b-105">**Applies to:**</span></span>
- [<span data-ttu-id="e621b-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e621b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e621b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e621b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e621b-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="e621b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e621b-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="e621b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="e621b-110">[フォルダー アクセスの制御により](controlled-folders.md) 、悪意のあるアプリやランサムウェアなどの脅威から貴重なデータを保護できます。</span><span class="sxs-lookup"><span data-stu-id="e621b-110">[Controlled folder access](controlled-folders.md) helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="e621b-111">フォルダー アクセスの制御は、サーバー 2019 Windows 10およびWindowsに含まれます。</span><span class="sxs-lookup"><span data-stu-id="e621b-111">Controlled folder access is included with Windows 10 and Windows Server 2019.</span></span>

<span data-ttu-id="e621b-112">次の方法を使用して、フォルダーアクセスの制御を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="e621b-112">You can enable controlled folder access by using any of these methods:</span></span>

* [<span data-ttu-id="e621b-113">Windows セキュリティアプリ</span><span class="sxs-lookup"><span data-stu-id="e621b-113">Windows Security app</span></span>](#windows-security-app)
* [<span data-ttu-id="e621b-114">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="e621b-114">Microsoft Intune</span></span>](#intune)
* [<span data-ttu-id="e621b-115">モバイル デバイス管理 (MDM)</span><span class="sxs-lookup"><span data-stu-id="e621b-115">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="e621b-116">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e621b-116">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
* [<span data-ttu-id="e621b-117">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="e621b-117">Group Policy</span></span>](#group-policy)
* [<span data-ttu-id="e621b-118">PowerShell</span><span class="sxs-lookup"><span data-stu-id="e621b-118">PowerShell</span></span>](#powershell)

<span data-ttu-id="e621b-119">[監査モード](evaluate-controlled-folder-access.md) を使用すると、デバイスの通常の使用に影響を与えることなく、機能の動作をテスト (およびイベントの確認) を行えます。</span><span class="sxs-lookup"><span data-stu-id="e621b-119">[Audit mode](evaluate-controlled-folder-access.md) allows you to test how the feature would work (and review events) without impacting the normal use of the device.</span></span>

<span data-ttu-id="e621b-120">ローカル管理者リストのマージを無効にするグループ ポリシー設定は、フォルダー アクセスの制御設定を上書きします。</span><span class="sxs-lookup"><span data-stu-id="e621b-120">Group Policy settings that disable local administrator list merging will override controlled folder access settings.</span></span> <span data-ttu-id="e621b-121">また、フォルダー アクセスの制御によってローカル管理者が設定した保護フォルダーと許可されたアプリも上書きされます。</span><span class="sxs-lookup"><span data-stu-id="e621b-121">They also override protected folders and allowed apps set by the local administrator through controlled folder access.</span></span> <span data-ttu-id="e621b-122">これらのポリシーには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e621b-122">These policies include:</span></span>

* <span data-ttu-id="e621b-123">Microsoft Defender ウイルス対策 **リストのローカル管理者のマージ動作を構成する**</span><span class="sxs-lookup"><span data-stu-id="e621b-123">Microsoft Defender Antivirus **Configure local administrator merge behavior for lists**</span></span>
* <span data-ttu-id="e621b-124">System Center Endpoint Protection **ユーザーによる除外と上書きの追加を許可する**</span><span class="sxs-lookup"><span data-stu-id="e621b-124">System Center Endpoint Protection **Allow users to add exclusions and overrides**</span></span>

<span data-ttu-id="e621b-125">ローカル リストのマージを無効にする方法の詳細については、「ユーザーが Microsoft Defender AV ポリシー設定をローカルで変更するを防止または許可する」 [を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged)。</span><span class="sxs-lookup"><span data-stu-id="e621b-125">For more information about disabling local list merging, see [Prevent or allow users to locally modify Microsoft Defender AV policy settings](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged).</span></span>

## <a name="windows-security-app"></a><span data-ttu-id="e621b-126">Windows セキュリティアプリ</span><span class="sxs-lookup"><span data-stu-id="e621b-126">Windows Security app</span></span>

1. <span data-ttu-id="e621b-127">タスク バー Windows セキュリティシールド アイコンを選択して、アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="e621b-127">Open the Windows Security app by selecting the shield icon in the task bar.</span></span> <span data-ttu-id="e621b-128">スタート メニューで Defender を検索 **することもできます**。</span><span class="sxs-lookup"><span data-stu-id="e621b-128">You can also search the start menu for **Defender**.</span></span>

2. <span data-ttu-id="e621b-129">[ウイルス **対策] &タイル** (または左側のメニュー バーのシールド アイコン) を選択し、[ランサムウェア保護] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e621b-129">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Ransomware protection**.</span></span>

3. <span data-ttu-id="e621b-130">[フォルダー アクセスの制御] **のスイッチを [オン]** に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="e621b-130">Set the switch for **Controlled folder access** to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="e621b-131">グループ ポリシー、PowerShell、または MDM CSP を使用してフォルダー アクセスの制御が構成されている場合、デバイスの再起動後に Windows セキュリティ アプリで状態が変更されます。</span><span class="sxs-lookup"><span data-stu-id="e621b-131">If controlled folder access is configured with Group Policy, PowerShell, or MDM CSPs, the state will change in the Windows Security app after a restart of the device.</span></span>
> <span data-ttu-id="e621b-132">これらのツールを使用して機能が **監査** モードに設定されている場合、アプリWindows セキュリティ状態が [オフ] と表示 **されます**。</span><span class="sxs-lookup"><span data-stu-id="e621b-132">If the feature is set to **Audit mode** with any of those tools, the Windows Security app will show the state as **Off**.</span></span>
> <span data-ttu-id="e621b-133">ユーザー プロファイル データを保護する場合は、ユーザー プロファイルをインストール ドライブの既定のWindowsすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e621b-133">If you are protecting user profile data, we recommend that the user profile should be on the default Windows installation drive.</span></span>

## <a name="intune"></a><span data-ttu-id="e621b-134">Intune</span><span class="sxs-lookup"><span data-stu-id="e621b-134">Intune</span></span>

1. <span data-ttu-id="e621b-135">Azure ポータルにサインイン [し、Intune](https://portal.azure.com) を開きます。</span><span class="sxs-lookup"><span data-stu-id="e621b-135">Sign in to the [Azure portal](https://portal.azure.com) and open Intune.</span></span>

2. <span data-ttu-id="e621b-136">[デバイス構成 **プロファイル]**  >  **[プロファイルの**  >  **作成] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="e621b-136">Go to **Device configuration** > **Profiles** > **Create profile**.</span></span>

3. <span data-ttu-id="e621b-137">プロファイルに名前を付け、[Windows 10 **とエンドポイント保護**]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e621b-137">Name the profile, choose **Windows 10 and later** and **Endpoint protection**.</span></span> <br/> <span data-ttu-id="e621b-138">![エンドポイント保護プロファイルの作成](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile)</span><span class="sxs-lookup"><span data-stu-id="e621b-138">![Create endpoint protection profile](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile)</span></span> <br/>

4. <span data-ttu-id="e621b-139">「Configure **Windows Defender**  >  **Exploit Guard**  >  **管理フォルダー アクセスを有効にする」に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="e621b-139">Go to **Configure** > **Windows Defender Exploit Guard** > **Controlled folder access** > **Enable**.</span></span>

5. <span data-ttu-id="e621b-140">保護されたフォルダーにアクセスできる各アプリケーションへのパスと、保護が必要な追加のフォルダーへのパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="e621b-140">Type the path to each application that has access to protected folders and the path to any additional folder that needs protection.</span></span> <span data-ttu-id="e621b-141">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e621b-141">Select **Add**.</span></span><br/> <span data-ttu-id="e621b-142">![Intune でフォルダー アクセスの制御を有効にする](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)</span><span class="sxs-lookup"><span data-stu-id="e621b-142">![Enable controlled folder access in Intune](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)</span></span><br/>

   > [!NOTE]
   > <span data-ttu-id="e621b-143">Wilcard はアプリケーションでサポートされますが、フォルダーではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="e621b-143">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="e621b-144">サブフォルダーは保護されません。</span><span class="sxs-lookup"><span data-stu-id="e621b-144">Subfolders are not protected.</span></span> <span data-ttu-id="e621b-145">許可されたアプリは、再起動するまでイベントをトリガーし続ける。</span><span class="sxs-lookup"><span data-stu-id="e621b-145">Allowed apps will continue to trigger events until they are restarted.</span></span>

6. <span data-ttu-id="e621b-146">**[OK] を選択** して、開いている各ブレードを保存し、[作成]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e621b-146">Select **OK** to save each open blade and **Create**.</span></span>

7. <span data-ttu-id="e621b-147">プロファイルの割り **当てを選択し**、[すべてのデバイス] の [すべての **ユーザー&割り当** てる] 、および [保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e621b-147">Select the profile **Assignments**, assign to **All Users & All Devices**, and **Save**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="e621b-148">モバイル デバイス管理 (MDM)</span><span class="sxs-lookup"><span data-stu-id="e621b-148">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="e621b-149">アプリが保護されたフォルダーに変更を加えるのを許可するには [、./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) 構成サービス プロバイダー (CSP) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e621b-149">Use the [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="e621b-150">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e621b-150">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="e621b-151">この **Microsoft Endpoint Configuration Manager、Exploit** Guard の [アセットと  >  **コンプライアンス] Endpoint Protection Windows Defender**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="e621b-151">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="e621b-152">[ホーム **エクスプ**  >  **ロイト ガード ポリシーの作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e621b-152">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="e621b-153">名前と説明を入力し、[フォルダー **アクセスの制御**] を選択し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e621b-153">Enter a name and a description, select **Controlled folder access**, and select **Next**.</span></span>

4. <span data-ttu-id="e621b-154">変更をブロックまたは監査するか、他のアプリを許可するか、他のフォルダーを追加するか選択し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e621b-154">Choose whether block or audit changes, allow other apps, or add other folders, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="e621b-155">Wilcard はアプリケーションでサポートされますが、フォルダーではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="e621b-155">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="e621b-156">サブフォルダーは保護されません。</span><span class="sxs-lookup"><span data-stu-id="e621b-156">Subfolders are not protected.</span></span> <span data-ttu-id="e621b-157">許可されたアプリは、再起動するまでイベントをトリガーし続ける。</span><span class="sxs-lookup"><span data-stu-id="e621b-157">Allowed apps will continue to trigger events until they are restarted.</span></span>

5. <span data-ttu-id="e621b-158">設定を確認し、[次へ] **を選択** してポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e621b-158">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="e621b-159">ポリシーが作成された後、閉 **じます**。</span><span class="sxs-lookup"><span data-stu-id="e621b-159">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="e621b-160">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="e621b-160">Group Policy</span></span>

1. <span data-ttu-id="e621b-161">グループ ポリシー管理デバイスで、グループ ポリシー [管理](https://technet.microsoft.com/library/cc731212.aspx)コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="e621b-161">On your Group Policy management device, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="e621b-162">**[グループ ポリシー管理エディター]** で、**[コンピューターの構成]** に移動し、**[管理用テンプレート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e621b-162">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="e621b-163">ツリーを展開して **、Exploit Guard Windowsアクセス> Microsoft Defender ウイルス対策 > Windows Defender管理>コンポーネントを表示します**。</span><span class="sxs-lookup"><span data-stu-id="e621b-163">Expand the tree to **Windows components > Microsoft Defender Antivirus > Windows Defender Exploit Guard > Controlled folder access**.</span></span>

4. <span data-ttu-id="e621b-164">[フォルダー アクセスの構成 **] 設定** をダブルクリックし、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="e621b-164">Double-click the **Configure Controlled folder access** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="e621b-165">[オプション] セクションで、次のいずれかのオプションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e621b-165">In the options section you must specify one of the following options:</span></span>
    * <span data-ttu-id="e621b-166">**有効** - 悪意のあるアプリや疑わしいアプリでは、保護されたフォルダー内のファイルを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="e621b-166">**Enable** - Malicious and suspicious apps won't be allowed to make changes to files in protected folders.</span></span> <span data-ttu-id="e621b-167">通知は、イベント ログWindowsされます。</span><span class="sxs-lookup"><span data-stu-id="e621b-167">A notification will be provided in the Windows event log.</span></span>
    * <span data-ttu-id="e621b-168">**無効 (既定)** - フォルダー アクセスの制御機能が機能しません。</span><span class="sxs-lookup"><span data-stu-id="e621b-168">**Disable (Default)** - The Controlled folder access feature won't work.</span></span> <span data-ttu-id="e621b-169">すべてのアプリは、保護されたフォルダー内のファイルを変更できます。</span><span class="sxs-lookup"><span data-stu-id="e621b-169">All apps can make changes to files in protected folders.</span></span>
    * <span data-ttu-id="e621b-170">**監査モード** - 悪意のあるアプリや疑わしいアプリが保護されたフォルダー内のファイルに変更を加えた場合、変更が許可されます。</span><span class="sxs-lookup"><span data-stu-id="e621b-170">**Audit Mode** - Changes will be allowed if a malicious or suspicious app attempts to make a change to a file in a protected folder.</span></span> <span data-ttu-id="e621b-171">ただし、組織への影響を評価Windowsイベント ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="e621b-171">However, it will be recorded in the Windows event log where you can assess the impact on your organization.</span></span>
    * <span data-ttu-id="e621b-172">**[ディスクの変更** をブロックする] - 信頼されていないアプリがディスク セクターに書き込む試みは、Windowsログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="e621b-172">**Block disk modification only** - Attempts by untrusted apps to write to disk sectors will be logged in Windows Event log.</span></span> <span data-ttu-id="e621b-173">これらのログは、Microsoft  > のアプリケーションとサービス > Windows > Windows Defender > ID 1123 >確認できます。</span><span class="sxs-lookup"><span data-stu-id="e621b-173">These logs can be found in **Applications and Services Logs** > Microsoft > Windows > Windows Defender > Operational > ID 1123.</span></span>
    * <span data-ttu-id="e621b-174">ディスク **の** 変更の監査のみ - 保護されたディスク セクターへの書き込みのみを Windows イベント ログに記録します([アプリケーションとサービス ログ Microsoft Windows Windows Defender  >    >    >    >  **運用**  >  **ID 1124]** の下)。</span><span class="sxs-lookup"><span data-stu-id="e621b-174">**Audit disk modification only** - Only attempts to write to protected disk sectors will be recorded in the Windows event log (under **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational** > **ID 1124**).</span></span> <span data-ttu-id="e621b-175">保護されたフォルダー内のファイルを変更または削除しようとすると、記録されません。</span><span class="sxs-lookup"><span data-stu-id="e621b-175">Attempts to modify or delete files in protected folders won't be recorded.</span></span>

      ![グループ ポリシー オプションのスクリーンショット [有効] と [監査モード] がドロップダウンで選択されている](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> <span data-ttu-id="e621b-177">管理されたフォルダー アクセスを完全に有効にするには、[グループ ポリシー] オプションを [有効] に設定し、[オプション] ドロップダウン メニューの [ブロック] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e621b-177">To fully enable controlled folder access, you must set the Group Policy option to **Enabled** and select **Block** in the options drop-down menu.</span></span>

## <a name="powershell"></a><span data-ttu-id="e621b-178">PowerShell</span><span class="sxs-lookup"><span data-stu-id="e621b-178">PowerShell</span></span>

1. <span data-ttu-id="e621b-179">[**スタート] メニューに「powershell」** と入力し、Windows PowerShellを右クリックし **、[** 管理者として **実行] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e621b-179">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="e621b-180">次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="e621b-180">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

<span data-ttu-id="e621b-181">代わりにを指定することで、監査モードで機能 `AuditMode` を有効にできます `Enabled` 。</span><span class="sxs-lookup"><span data-stu-id="e621b-181">You can enable the feature in audit mode by specifying `AuditMode` instead of `Enabled`.</span></span>

<span data-ttu-id="e621b-182">機能 `Disabled` をオフにする場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="e621b-182">Use `Disabled` to turn off the feature.</span></span>

## <a name="see-also"></a><span data-ttu-id="e621b-183">関連項目</span><span class="sxs-lookup"><span data-stu-id="e621b-183">See also</span></span>

* [<span data-ttu-id="e621b-184">フォルダー アクセスを制御して重要なフォルダーを保護する</span><span class="sxs-lookup"><span data-stu-id="e621b-184">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="e621b-185">制御されたフォルダー アクセスをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="e621b-185">Customize controlled folder access</span></span>](customize-controlled-folders.md)
* [<span data-ttu-id="e621b-186">Microsoft Defender for Endpoint の評価</span><span class="sxs-lookup"><span data-stu-id="e621b-186">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-mde.md)
