---
title: 制御されたフォルダー アクセスを有効にする
keywords: フォルダー アクセスの制御、Windows 10、Windows Defender、ランサムウェア、保護、ファイル、フォルダー、有効化、オン、使用
description: フォルダー アクセスの制御を有効にすることで重要なファイルを保護する方法について説明します。
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.topic: article
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
ms.openlocfilehash: ed0859e6018d171b48aac83d394eacbd2163c37b
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924685"
---
# <a name="enable-controlled-folder-access"></a><span data-ttu-id="addb5-104">制御されたフォルダー アクセスを有効にする</span><span class="sxs-lookup"><span data-stu-id="addb5-104">Enable controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="addb5-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="addb5-105">**Applies to:**</span></span>
- [<span data-ttu-id="addb5-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="addb5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="addb5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="addb5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="addb5-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="addb5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="addb5-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="addb5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="addb5-110">[フォルダー アクセスの制御により](controlled-folders.md) 、悪意のあるアプリやランサムウェアなどの脅威から貴重なデータを保護できます。</span><span class="sxs-lookup"><span data-stu-id="addb5-110">[Controlled folder access](controlled-folders.md) helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="addb5-111">フォルダー アクセスの制御は、サーバー 2019 Windows 10およびWindowsに含まれます。</span><span class="sxs-lookup"><span data-stu-id="addb5-111">Controlled folder access is included with Windows 10 and Windows Server 2019.</span></span>

<span data-ttu-id="addb5-112">次の方法を使用して、フォルダーアクセスの制御を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="addb5-112">You can enable controlled folder access by using any of these methods:</span></span>

* [<span data-ttu-id="addb5-113">Windows セキュリティアプリ</span><span class="sxs-lookup"><span data-stu-id="addb5-113">Windows Security app</span></span>](#windows-security-app)
* [<span data-ttu-id="addb5-114">Microsoft エンドポイント マネージャー</span><span class="sxs-lookup"><span data-stu-id="addb5-114">Microsoft Endpoint Manager</span></span>](#endpoint-manager)
* [<span data-ttu-id="addb5-115">モバイル デバイス管理 (MDM)</span><span class="sxs-lookup"><span data-stu-id="addb5-115">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="addb5-116">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="addb5-116">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
* [<span data-ttu-id="addb5-117">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="addb5-117">Group Policy</span></span>](#group-policy)
* [<span data-ttu-id="addb5-118">PowerShell</span><span class="sxs-lookup"><span data-stu-id="addb5-118">PowerShell</span></span>](#powershell)

<span data-ttu-id="addb5-119">[監査モード](evaluate-controlled-folder-access.md) を使用すると、デバイスの通常の使用に影響を与えることなく、機能の動作をテスト (およびイベントの確認) を行えます。</span><span class="sxs-lookup"><span data-stu-id="addb5-119">[Audit mode](evaluate-controlled-folder-access.md) allows you to test how the feature would work (and review events) without impacting the normal use of the device.</span></span>

<span data-ttu-id="addb5-120">ローカル管理者リストのマージを無効にするグループ ポリシー設定は、フォルダー アクセスの制御設定を上書きします。</span><span class="sxs-lookup"><span data-stu-id="addb5-120">Group Policy settings that disable local administrator list merging will override controlled folder access settings.</span></span> <span data-ttu-id="addb5-121">また、フォルダー アクセスの制御によってローカル管理者が設定した保護フォルダーと許可されたアプリも上書きされます。</span><span class="sxs-lookup"><span data-stu-id="addb5-121">They also override protected folders and allowed apps set by the local administrator through controlled folder access.</span></span> <span data-ttu-id="addb5-122">これらのポリシーには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="addb5-122">These policies include:</span></span>

* <span data-ttu-id="addb5-123">Microsoft Defender ウイルス対策 **リストのローカル管理者のマージ動作を構成する**</span><span class="sxs-lookup"><span data-stu-id="addb5-123">Microsoft Defender Antivirus **Configure local administrator merge behavior for lists**</span></span>
* <span data-ttu-id="addb5-124">System Center Endpoint Protection **ユーザーによる除外と上書きの追加を許可する**</span><span class="sxs-lookup"><span data-stu-id="addb5-124">System Center Endpoint Protection **Allow users to add exclusions and overrides**</span></span>

<span data-ttu-id="addb5-125">ローカル リストのマージを無効にする方法の詳細については、「ユーザーが Microsoft Defender AV ポリシー設定をローカルで変更するを防止または許可する」 [を参照してください](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="addb5-125">For more information about disabling local list merging, see [Prevent or allow users to locally modify Microsoft Defender AV policy settings](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus).</span></span>

## <a name="windows-security-app"></a><span data-ttu-id="addb5-126">Windows セキュリティアプリ</span><span class="sxs-lookup"><span data-stu-id="addb5-126">Windows Security app</span></span>

1. <span data-ttu-id="addb5-127">タスク バー Windows セキュリティシールド アイコンを選択して、アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="addb5-127">Open the Windows Security app by selecting the shield icon in the task bar.</span></span> <span data-ttu-id="addb5-128">スタート メニューで Defender を検索 **することもできます**。</span><span class="sxs-lookup"><span data-stu-id="addb5-128">You can also search the start menu for **Defender**.</span></span>

2. <span data-ttu-id="addb5-129">[ウイルス **対策] &タイル** (または左側のメニュー バーのシールド アイコン) を選択し、[ランサムウェア保護] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="addb5-129">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Ransomware protection**.</span></span>

3. <span data-ttu-id="addb5-130">[フォルダー アクセスの制御] **のスイッチを [オン]** に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="addb5-130">Set the switch for **Controlled folder access** to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="addb5-131">グループ ポリシー、PowerShell、または MDM CSP を使用してフォルダー アクセスの制御が構成されている場合、デバイスの再起動後に Windows セキュリティ アプリで状態が変更されます。</span><span class="sxs-lookup"><span data-stu-id="addb5-131">If controlled folder access is configured with Group Policy, PowerShell, or MDM CSPs, the state will change in the Windows Security app after a restart of the device.</span></span>
> <span data-ttu-id="addb5-132">これらのツールを使用して機能が **監査** モードに設定されている場合、アプリWindows セキュリティ状態が [オフ] と表示 **されます**。</span><span class="sxs-lookup"><span data-stu-id="addb5-132">If the feature is set to **Audit mode** with any of those tools, the Windows Security app will show the state as **Off**.</span></span>
> <span data-ttu-id="addb5-133">ユーザー プロファイル データを保護する場合は、ユーザー プロファイルをインストール ドライブの既定のWindowsすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="addb5-133">If you are protecting user profile data, we recommend that the user profile should be on the default Windows installation drive.</span></span>

## <a name="endpoint-manager"></a><span data-ttu-id="addb5-134">エンドポイント マネージャー</span><span class="sxs-lookup"><span data-stu-id="addb5-134">Endpoint Manager</span></span>

1. <span data-ttu-id="addb5-135">[エンドポイント セキュリティ][を開](https://endpoint.microsoft.com)エンドポイント マネージャーに **サインインします**。</span><span class="sxs-lookup"><span data-stu-id="addb5-135">Sign in to the [Endpoint Manager](https://endpoint.microsoft.com) and open **Endpoint Security**.</span></span>

2. <span data-ttu-id="addb5-136">[攻撃表面 **の縮小ポリシー] に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="addb5-136">Go to **Attack Surface Reduction** > **Policy**.</span></span>

3. <span data-ttu-id="addb5-137">[**プラットフォーム] を** 選択 **し、[Windows 10] 以降を** 選択し、プロファイル攻撃表面縮小ルール [作成]**を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="addb5-137">Select **Platform**, choose **Windows 10 and later**, and select the profile **Attack Surface Reduction rules** > **Create**.</span></span>

4.  <span data-ttu-id="addb5-138">ポリシーに名前を付け、説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="addb5-138">Name the policy and add a description.</span></span> <span data-ttu-id="addb5-139">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="addb5-139">Select **Next**.</span></span>

5.  <span data-ttu-id="addb5-140">下までスクロールし、[フォルダー保護を有効にする] ドロップダウンを選択し、[有効にする] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="addb5-140">Scroll down to the bottom, select the **Enable Folder Protection** drop-down, and choose **Enable**.</span></span>

6.  <span data-ttu-id="addb5-141">[ **保護する必要がある追加のフォルダーの一覧] を選択し** 、保護する必要があるフォルダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="addb5-141">Select **List of additional folders that need to be protected** and add the folders that need to be protected.</span></span>

7.  <span data-ttu-id="addb5-142">[ **保護されたフォルダーにアクセスできる** アプリの一覧] を選択し、保護されたフォルダーにアクセスできるアプリを追加します。</span><span class="sxs-lookup"><span data-stu-id="addb5-142">Select **List of apps that have access to protected folders** and add the apps that have access to protected folders.</span></span>

8.  <span data-ttu-id="addb5-143">[ **攻撃表面の縮小** ルールからファイルとパスを除外する] を選択し、攻撃表面の縮小ルールから除外する必要があるファイルとパスを追加します。</span><span class="sxs-lookup"><span data-stu-id="addb5-143">Select **Exclude files and paths from attack surface reduction rules** and add the files and paths that need to be excluded from attack surface reduction rules.</span></span>

9.  <span data-ttu-id="addb5-144">プロファイルの割り **当てを選択し**、[すべてのデバイス] で [すべてのユーザー&割り当てる] **を選択し、[** 保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="addb5-144">Select the profile **Assignments**, assign to **All Users & All Devices**, and select **Save**.</span></span>

10.  <span data-ttu-id="addb5-145">[次 **へ]** を選択して、開いている各ブレードを保存し、[作成] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="addb5-145">Select **Next** to save each open blade and then **Create**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="addb5-146">ワイルドカードはアプリケーションでサポートされますが、フォルダーではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="addb5-146">Wildcards are supported for applications, but not for folders.</span></span> <span data-ttu-id="addb5-147">サブフォルダーは保護されません。</span><span class="sxs-lookup"><span data-stu-id="addb5-147">Subfolders are not protected.</span></span> <span data-ttu-id="addb5-148">許可されたアプリは、再起動するまでイベントをトリガーし続ける。</span><span class="sxs-lookup"><span data-stu-id="addb5-148">Allowed apps will continue to trigger events until they are restarted.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="addb5-149">モバイル デバイス管理 (MDM)</span><span class="sxs-lookup"><span data-stu-id="addb5-149">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="addb5-150">アプリが保護されたフォルダーに変更を加えるのを許可するには [、./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender) 構成サービス プロバイダー (CSP) を使用します。</span><span class="sxs-lookup"><span data-stu-id="addb5-150">Use the [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="addb5-151">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="addb5-151">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="addb5-152">この **Microsoft Endpoint Configuration Manager、Exploit** Guard の [アセットと  >  **コンプライアンス] Endpoint Protection Windows Defender**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="addb5-152">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="addb5-153">[ホーム **エクスプ**  >  **ロイト ガード ポリシーの作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="addb5-153">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="addb5-154">名前と説明を入力し、[フォルダー **アクセスの制御**] を選択し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="addb5-154">Enter a name and a description, select **Controlled folder access**, and select **Next**.</span></span>

4. <span data-ttu-id="addb5-155">変更をブロックまたは監査するか、他のアプリを許可するか、他のフォルダーを追加するか選択し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="addb5-155">Choose whether block or audit changes, allow other apps, or add other folders, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="addb5-156">Wilcard はアプリケーションでサポートされますが、フォルダーではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="addb5-156">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="addb5-157">サブフォルダーは保護されません。</span><span class="sxs-lookup"><span data-stu-id="addb5-157">Subfolders are not protected.</span></span> <span data-ttu-id="addb5-158">許可されたアプリは、再起動するまでイベントをトリガーし続ける。</span><span class="sxs-lookup"><span data-stu-id="addb5-158">Allowed apps will continue to trigger events until they are restarted.</span></span>

5. <span data-ttu-id="addb5-159">設定を確認し、[次へ] **を選択** してポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="addb5-159">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="addb5-160">ポリシーが作成された後、閉 **じます**。</span><span class="sxs-lookup"><span data-stu-id="addb5-160">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="addb5-161">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="addb5-161">Group Policy</span></span>

1. <span data-ttu-id="addb5-162">グループ ポリシー管理デバイスで、グループ ポリシー [管理](https://technet.microsoft.com/library/cc731212.aspx)コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="addb5-162">On your Group Policy management device, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="addb5-163">**[グループ ポリシー管理エディター]** で、**[コンピューターの構成]** に移動し、**[管理用テンプレート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="addb5-163">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="addb5-164">ツリーを展開して **、Exploit Guard Windowsアクセス> Microsoft Defender ウイルス対策 > Windows Defender管理>コンポーネントを表示します**。</span><span class="sxs-lookup"><span data-stu-id="addb5-164">Expand the tree to **Windows components > Microsoft Defender Antivirus > Windows Defender Exploit Guard > Controlled folder access**.</span></span>

4. <span data-ttu-id="addb5-165">[フォルダー アクセスの構成 **] 設定** をダブルクリックし、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="addb5-165">Double-click the **Configure Controlled folder access** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="addb5-166">[オプション] セクションで、次のいずれかのオプションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="addb5-166">In the options section you must specify one of the following options:</span></span>
    * <span data-ttu-id="addb5-167">**有効** - 悪意のあるアプリや疑わしいアプリでは、保護されたフォルダー内のファイルを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="addb5-167">**Enable** - Malicious and suspicious apps won't be allowed to make changes to files in protected folders.</span></span> <span data-ttu-id="addb5-168">通知は、イベント ログWindowsされます。</span><span class="sxs-lookup"><span data-stu-id="addb5-168">A notification will be provided in the Windows event log.</span></span>
    * <span data-ttu-id="addb5-169">**無効 (既定)** - フォルダー アクセスの制御機能が機能しません。</span><span class="sxs-lookup"><span data-stu-id="addb5-169">**Disable (Default)** - The Controlled folder access feature won't work.</span></span> <span data-ttu-id="addb5-170">すべてのアプリは、保護されたフォルダー内のファイルを変更できます。</span><span class="sxs-lookup"><span data-stu-id="addb5-170">All apps can make changes to files in protected folders.</span></span>
    * <span data-ttu-id="addb5-171">**監査モード** - 悪意のあるアプリや疑わしいアプリが保護されたフォルダー内のファイルに変更を加えた場合、変更が許可されます。</span><span class="sxs-lookup"><span data-stu-id="addb5-171">**Audit Mode** - Changes will be allowed if a malicious or suspicious app attempts to make a change to a file in a protected folder.</span></span> <span data-ttu-id="addb5-172">ただし、組織への影響を評価Windowsイベント ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="addb5-172">However, it will be recorded in the Windows event log where you can assess the impact on your organization.</span></span>
    * <span data-ttu-id="addb5-173">**[ディスクの変更** をブロックする] - 信頼されていないアプリがディスク セクターに書き込む試みは、Windowsログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="addb5-173">**Block disk modification only** - Attempts by untrusted apps to write to disk sectors will be logged in Windows Event log.</span></span> <span data-ttu-id="addb5-174">これらのログは、Microsoft  > のアプリケーションとサービス > Windows > Windows Defender > ID 1123 >確認できます。</span><span class="sxs-lookup"><span data-stu-id="addb5-174">These logs can be found in **Applications and Services Logs** > Microsoft > Windows > Windows Defender > Operational > ID 1123.</span></span>
    * <span data-ttu-id="addb5-175">ディスク **の** 変更の監査のみ - 保護されたディスク セクターへの書き込みのみを Windows イベント ログに記録します([アプリケーションとサービス ログ Microsoft Windows Windows Defender  >    >    >    >  **運用**  >  **ID 1124]** の下)。</span><span class="sxs-lookup"><span data-stu-id="addb5-175">**Audit disk modification only** - Only attempts to write to protected disk sectors will be recorded in the Windows event log (under **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational** > **ID 1124**).</span></span> <span data-ttu-id="addb5-176">保護されたフォルダー内のファイルを変更または削除しようとすると、記録されません。</span><span class="sxs-lookup"><span data-stu-id="addb5-176">Attempts to modify or delete files in protected folders won't be recorded.</span></span>

      ![グループ ポリシー オプションのスクリーンショット [有効] と [監査モード] がドロップダウンで選択されている](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> <span data-ttu-id="addb5-178">管理されたフォルダー アクセスを完全に有効にするには、[グループ ポリシー] オプションを [有効] に設定し、[オプション] ドロップダウン メニューの [ブロック] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="addb5-178">To fully enable controlled folder access, you must set the Group Policy option to **Enabled** and select **Block** in the options drop-down menu.</span></span>

## <a name="powershell"></a><span data-ttu-id="addb5-179">PowerShell</span><span class="sxs-lookup"><span data-stu-id="addb5-179">PowerShell</span></span>

1. <span data-ttu-id="addb5-180">[**スタート] メニューに「powershell」** と入力し、Windows PowerShellを右クリックし **、[** 管理者として **実行] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="addb5-180">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="addb5-181">次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="addb5-181">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

<span data-ttu-id="addb5-182">代わりにを指定することで、監査モードで機能 `AuditMode` を有効にできます `Enabled` 。</span><span class="sxs-lookup"><span data-stu-id="addb5-182">You can enable the feature in audit mode by specifying `AuditMode` instead of `Enabled`.</span></span>

<span data-ttu-id="addb5-183">機能 `Disabled` をオフにする場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="addb5-183">Use `Disabled` to turn off the feature.</span></span>

## <a name="see-also"></a><span data-ttu-id="addb5-184">関連項目</span><span class="sxs-lookup"><span data-stu-id="addb5-184">See also</span></span>

* [<span data-ttu-id="addb5-185">フォルダー アクセスを制御して重要なフォルダーを保護する</span><span class="sxs-lookup"><span data-stu-id="addb5-185">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="addb5-186">制御されたフォルダー アクセスをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="addb5-186">Customize controlled folder access</span></span>](customize-controlled-folders.md)
* [<span data-ttu-id="addb5-187">Microsoft Defender for Endpoint の評価</span><span class="sxs-lookup"><span data-stu-id="addb5-187">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-mde.md)
