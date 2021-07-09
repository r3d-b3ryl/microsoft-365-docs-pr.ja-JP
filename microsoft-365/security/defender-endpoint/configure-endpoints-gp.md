---
title: グループ Windows 10経由で Microsoft Defender for Endpoint にデバイスをオンボードする
description: グループ ポリシーを使用して、サービスにオンボードWindows 10デバイスに構成パッケージを展開します。
keywords: グループ ポリシーを使用したデバイスの構成、デバイス管理、エンドポイント デバイス用 Microsoft Defender の構成、Microsoft Defender for Endpoint デバイスのオンボード、グループ ポリシー
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 26bdb0fbdb417d9e7fb01e4c3a863c44e57b7fb7
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339624"
---
# <a name="onboard-the-windows-10-devices-using-group-policy"></a><span data-ttu-id="67686-104">グループ ポリシーをWindows 10デバイスにオンボードする</span><span class="sxs-lookup"><span data-stu-id="67686-104">Onboard the Windows 10 devices using Group Policy</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="67686-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="67686-105">**Applies to:**</span></span>

- <span data-ttu-id="67686-106">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="67686-106">Group Policy</span></span>
- [<span data-ttu-id="67686-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="67686-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="67686-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="67686-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="67686-109">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="67686-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="67686-110">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="67686-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsgp-abovefoldlink)

> [!NOTE]
> <span data-ttu-id="67686-111">グループ ポリシー (GP) 更新プログラムを使用してパッケージを展開するには、サーバー 2008 R2 以降Windowsする必要があります。</span><span class="sxs-lookup"><span data-stu-id="67686-111">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>
>
> <span data-ttu-id="67686-112">サーバー Windows 2019 では、グループ ポリシーの基本設定で作成される XML ファイルの NT AUTHORITY\Well-Known-System-Account を NT AUTHORITY\SYSTEM に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="67686-112">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="67686-113">グループ ポリシーを使用してデバイスをオンボードする</span><span class="sxs-lookup"><span data-stu-id="67686-113">Onboard devices using Group Policy</span></span>

<span data-ttu-id="67686-114">[![さまざまな展開パスを示す PDF のイメージ](images/onboard-gp.png)](images/onboard-gp.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="67686-114">[![Image of the PDF showing the various deployment paths](images/onboard-gp.png)](images/onboard-gp.png#lightbox)</span></span>

<span data-ttu-id="67686-115">[[](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)エンドポイント用 Defender [Visio展開](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)] のさまざまなパスを確認するには、PDF またはドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="67686-115">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Defender for Endpoint.</span></span>

1. <span data-ttu-id="67686-116">サービス オンボーディング ウィザードから.zipした gp 構成 *パッケージ*(WindowsDefenderATPOnboardingPackage.zip) を開きます。</span><span class="sxs-lookup"><span data-stu-id="67686-116">Open the GP configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="67686-117">また、次のポータルから[パッケージをMicrosoft 365 Defenderすることもできます](https://security.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="67686-117">You can also get the package from [Microsoft 365 Defender portal](https://security.microsoft.com/):</span></span>

    1. <span data-ttu-id="67686-118">ナビゲーション ウィンドウで、[エンドポイント **デバイス設定**  >    >  **オンボーディング]**   >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="67686-118">In the navigation pane, select **Settings** > **Endpoints** > **Device management**  > **Onboarding**.</span></span>

    1. <span data-ttu-id="67686-119">オペレーティング システムWindows 10を選択します。</span><span class="sxs-lookup"><span data-stu-id="67686-119">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="67686-120">[展開方法 **] フィールドで** 、[グループ ポリシー] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="67686-120">In the **Deployment method** field, select **Group policy**.</span></span>

    1. <span data-ttu-id="67686-121">[パッケージ **のダウンロード] を** クリックし、.zip保存します。</span><span class="sxs-lookup"><span data-stu-id="67686-121">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="67686-122">デバイスからアクセスできる.zipファイルの内容を読み取り専用の共有場所に抽出します。</span><span class="sxs-lookup"><span data-stu-id="67686-122">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="67686-123">*OptionalParamsPolicy* というフォルダーと *WindowsDefenderATPOnboardingScript.cmd というファイルが必要です*。</span><span class="sxs-lookup"><span data-stu-id="67686-123">You should have a folder called *OptionalParamsPolicy* and the file *WindowsDefenderATPOnboardingScript.cmd*.</span></span>

3. <span data-ttu-id="67686-124">グループ ポリシー [管理コンソール](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) を開き、構成するグループ ポリシー オブジェクト (GPO) を右クリックし、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="67686-124">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

4. <span data-ttu-id="67686-125">グループ ポリシー **管理エディターで、[\*\*\*\*コンピューターの構成**] 、[基本設定] の順に移動し、[コントロール パネルの **設定] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="67686-125">In the **Group Policy Management Editor**, go to **Computer configuration**, then **Preferences**, and then **Control panel settings**.</span></span>

5. <span data-ttu-id="67686-126">[スケジュールされたタスク **] を** 右クリックし、[新規] をポイントし、[イミディエイト タスク] (少なくとも Windows **7) をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="67686-126">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate Task (At least Windows 7)**.</span></span>

6. <span data-ttu-id="67686-127">開く **[タスク]** ウィンドウで、[全般] タブ **に移動** します。[セキュリティ **オプション] で、[\*\*\*\*ユーザーまたはグループの変更**] をクリックし、[SYSTEM] と入力し、[名前の確認] をクリック **して** **[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="67686-127">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK**.</span></span> <span data-ttu-id="67686-128">NT AUTHORITY\SYSTEM は、タスクが実行されるユーザー アカウントとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="67686-128">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

7. <span data-ttu-id="67686-129">[ **ユーザーがログオンするかどうかを実行する] を選択し** 、[最高の特権で実行する **] チェック ボックスを** オンにします。</span><span class="sxs-lookup"><span data-stu-id="67686-129">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

8. <span data-ttu-id="67686-130">[操作] タブ **に移動し** 、[新規] **をクリックします。** [アクション **] フィールドで [プログラム** の開始] が選択 **されている必要** があります。</span><span class="sxs-lookup"><span data-stu-id="67686-130">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="67686-131">共有  *WindowsDefenderATPOnboardingScript.cmd* ファイルの NetBIOS パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="67686-131">Enter the NetBIOS path of the shared  *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

9. <span data-ttu-id="67686-132">**[OK] を** クリックし、開いている GPMC ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="67686-132">Click **OK** and close any open GPMC windows.</span></span>

> [!TIP]
> <span data-ttu-id="67686-133">デバイスのオンボード後、検出テストを実行して、デバイスがサービスに適切にオンボードされていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="67686-133">After onboarding the device, you can choose to run a detection test to verify that the device is properly onboarded to the service.</span></span> <span data-ttu-id="67686-134">詳細については、「新しくオンボードされた Defender for Endpoint デバイスで検出テストを実行 [する」を参照してください](run-detection-test.md)。</span><span class="sxs-lookup"><span data-stu-id="67686-134">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint device](run-detection-test.md).</span></span>

## <a name="additional-defender-for-endpoint-configuration-settings"></a><span data-ttu-id="67686-135">エンドポイントの追加の Defender 構成設定</span><span class="sxs-lookup"><span data-stu-id="67686-135">Additional Defender for Endpoint configuration settings</span></span>
<span data-ttu-id="67686-136">デバイスごとに、詳細分析用にファイルを送信する要求が行われたときに、デバイスからサンプルをMicrosoft 365 Defenderできるかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="67686-136">For each device, you can state whether samples can be collected from the device when a request is made through Microsoft 365 Defender to submit a file for deep analysis.</span></span>

<span data-ttu-id="67686-137">グループ ポリシー (GP) を使用して、ディープ分析機能で使用されるサンプル共有の設定などの設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="67686-137">You can use Group Policy (GP) to configure settings, such as settings for the sample sharing used in the deep analysis feature.</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="67686-138">サンプル コレクション設定の構成</span><span class="sxs-lookup"><span data-stu-id="67686-138">Configure sample collection settings</span></span>

1. <span data-ttu-id="67686-139">GP 管理デバイスで、構成パッケージから次のファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="67686-139">On your GP management device, copy the following files from the  configuration package:</span></span>

    - <span data-ttu-id="67686-140">_AtpConfiguration.admx を_ _C: \\ \\ policyDefinitions Windowsコピーする_</span><span class="sxs-lookup"><span data-stu-id="67686-140">Copy _AtpConfiguration.admx_ into _C:\\Windows\\PolicyDefinitions_</span></span>

    - <span data-ttu-id="67686-141">_AtpConfiguration.adml_ を C: Windows _\\ \\ PolicyDefinitions \\ en-US にコピーする_</span><span class="sxs-lookup"><span data-stu-id="67686-141">Copy _AtpConfiguration.adml_ into _C:\\Windows\\PolicyDefinitions\\en-US_</span></span>

    <span data-ttu-id="67686-142">グループ ポリシー管理用テンプレートに [セントラル ストア](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)を使用している場合は、構成パッケージから次のファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="67686-142">If you are using a [Central Store for Group Policy Administrative Templates](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra), copy the following files from the  configuration package:</span></span>

    - <span data-ttu-id="67686-143">SysVol ポリシー _\\ \\ \<forest.root\> \\ \\ \<forest.root\> \\ \\ PolicyDefinitions に AtpConfiguration.admx をコピーする_</span><span class="sxs-lookup"><span data-stu-id="67686-143">Copy _AtpConfiguration.admx_ into _\\\\\<forest.root\>\\SysVol\\\<forest.root\>\\Policies\\PolicyDefinitions_</span></span>

    - <span data-ttu-id="67686-144">_AtpConfiguration.adml を_ _\\ \\ \<forest.root\> \\ SysVol \\ \<forest.root\> \\ ポリシー \\ PolicyDefinitions \\ en-US にコピーする_</span><span class="sxs-lookup"><span data-stu-id="67686-144">Copy _AtpConfiguration.adml_ into _\\\\\<forest.root\>\\SysVol\\\<forest.root\>\\Policies\\PolicyDefinitions\\en-US_</span></span>

2. <span data-ttu-id="67686-145">グループ ポリシー [管理コンソールを開き](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)、構成する GPO を右クリックし、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="67686-145">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11), right-click the GPO you want to configure and click **Edit**.</span></span>

3. <span data-ttu-id="67686-146">グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="67686-146">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

4. <span data-ttu-id="67686-147">[ポリシー **] をクリックし**、[管理 **用テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="67686-147">Click **Policies**, then **Administrative templates**.</span></span>

5. <span data-ttu-id="67686-148">[コンポーネント **Windows] をクリック** し **、[ATP] Windows Defenderをクリックします**。</span><span class="sxs-lookup"><span data-stu-id="67686-148">Click **Windows components** and then **Windows Defender ATP**.</span></span>

6. <span data-ttu-id="67686-149">デバイスからのサンプル共有を有効または無効にする場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="67686-149">Choose to enable or disable sample sharing from your devices.</span></span>

> [!NOTE]
> <span data-ttu-id="67686-150">値を設定しない場合、既定値はサンプル コレクションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="67686-150">If you don't set a value, the default value is to enable sample collection.</span></span>

## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="67686-151">その他の推奨構成設定</span><span class="sxs-lookup"><span data-stu-id="67686-151">Other recommended configuration settings</span></span>

### <a name="update-endpoint-protection-configuration"></a><span data-ttu-id="67686-152">エンドポイント保護構成の更新</span><span class="sxs-lookup"><span data-stu-id="67686-152">Update endpoint protection configuration</span></span>

<span data-ttu-id="67686-153">オンボーディング スクリプトを構成したら、同じグループ ポリシーの編集を続けてエンドポイント保護構成を追加します。</span><span class="sxs-lookup"><span data-stu-id="67686-153">After configuring the onboarding script, continue editing the same group policy to add endpoint protection configurations.</span></span> <span data-ttu-id="67686-154">グループ ポリシーの編集は、Windows 10または Server 2019 を実行しているシステムから実行し、必要なすべての機能をMicrosoft Defender ウイルス対策します。</span><span class="sxs-lookup"><span data-stu-id="67686-154">Perform group policy edits from a system running Windows 10 or Server 2019 to ensure you have all of the required Microsoft Defender Antivirus capabilities.</span></span> <span data-ttu-id="67686-155">Defender ATP 構成設定を登録するには、グループ ポリシー オブジェクトを閉じて再度開く必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="67686-155">You may need to close and reopen the group policy object to register the Defender ATP configuration settings.</span></span>

<span data-ttu-id="67686-156">すべてのポリシーは 、 の下に位置します `Computer Configuration\Policies\Administrative Templates` 。</span><span class="sxs-lookup"><span data-stu-id="67686-156">All policies are located under `Computer Configuration\Policies\Administrative Templates`.</span></span>

<span data-ttu-id="67686-157">**ポリシーの場所:** \Windows コンポーネント\atp Windows Defender</span><span class="sxs-lookup"><span data-stu-id="67686-157">**Policy location:** \Windows Components\Windows Defender ATP</span></span>

<span data-ttu-id="67686-158">ポリシー</span><span class="sxs-lookup"><span data-stu-id="67686-158">Policy</span></span> | <span data-ttu-id="67686-159">Setting</span><span class="sxs-lookup"><span data-stu-id="67686-159">Setting</span></span>
:---|:---
<span data-ttu-id="67686-160">Enable\Disable Sample collection</span><span class="sxs-lookup"><span data-stu-id="67686-160">Enable\Disable Sample collection</span></span>| <span data-ttu-id="67686-161">[有効] - [コンピューターでサンプル コレクションを有効にする] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="67686-161">Enabled - "Enable sample collection on machines" checked</span></span>

<br>

<span data-ttu-id="67686-162">**ポリシーの場所:** \Windows コンポーネント\Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="67686-162">**Policy location:**  \Windows Components\Microsoft Defender Antivirus</span></span>

<span data-ttu-id="67686-163">ポリシー</span><span class="sxs-lookup"><span data-stu-id="67686-163">Policy</span></span> | <span data-ttu-id="67686-164">Setting</span><span class="sxs-lookup"><span data-stu-id="67686-164">Setting</span></span>
:---|:---
<span data-ttu-id="67686-165">望ましくない可能性があるアプリケーションの検出を構成する</span><span class="sxs-lookup"><span data-stu-id="67686-165">Configure detection for potentially unwanted applications</span></span> | <span data-ttu-id="67686-166">有効、ブロック</span><span class="sxs-lookup"><span data-stu-id="67686-166">Enabled, Block</span></span>

<br>

<span data-ttu-id="67686-167">**ポリシーの場所:** \Windows コンポーネント\Microsoft Defender ウイルス対策\MAPS</span><span class="sxs-lookup"><span data-stu-id="67686-167">**Policy location:** \Windows Components\Microsoft Defender Antivirus\MAPS</span></span>

<span data-ttu-id="67686-168">ポリシー</span><span class="sxs-lookup"><span data-stu-id="67686-168">Policy</span></span> | <span data-ttu-id="67686-169">Setting</span><span class="sxs-lookup"><span data-stu-id="67686-169">Setting</span></span>
:---|:---
<span data-ttu-id="67686-170">Microsoft MAPS に参加する</span><span class="sxs-lookup"><span data-stu-id="67686-170">Join Microsoft MAPS</span></span> | <span data-ttu-id="67686-171">有効、高度なマップ</span><span class="sxs-lookup"><span data-stu-id="67686-171">Enabled, Advanced MAPS</span></span>
<span data-ttu-id="67686-172">詳細な分析が必要な場合にファイル サンプルを送信する</span><span class="sxs-lookup"><span data-stu-id="67686-172">Send file samples when further analysis is required</span></span> | <span data-ttu-id="67686-173">有効、安全なサンプルの送信</span><span class="sxs-lookup"><span data-stu-id="67686-173">Enabled, Send safe samples</span></span>

<br>

<span data-ttu-id="67686-174">**ポリシーの場所:** \Windows コンポーネント\Microsoft Defender ウイルス対策\リアルタイム保護</span><span class="sxs-lookup"><span data-stu-id="67686-174">**Policy location:** \Windows Components\Microsoft Defender Antivirus\Real-time Protection</span></span>

<span data-ttu-id="67686-175">ポリシー</span><span class="sxs-lookup"><span data-stu-id="67686-175">Policy</span></span> | <span data-ttu-id="67686-176">Setting</span><span class="sxs-lookup"><span data-stu-id="67686-176">Setting</span></span>
:---|:---
<span data-ttu-id="67686-177">リアルタイム保護をオフにする</span><span class="sxs-lookup"><span data-stu-id="67686-177">Turn off real-time protection</span></span>|<span data-ttu-id="67686-178">無効</span><span class="sxs-lookup"><span data-stu-id="67686-178">Disabled</span></span>
<span data-ttu-id="67686-179">動作の監視を有効にする</span><span class="sxs-lookup"><span data-stu-id="67686-179">Turn on behavior monitoring</span></span>|<span data-ttu-id="67686-180">Enabled</span><span class="sxs-lookup"><span data-stu-id="67686-180">Enabled</span></span>
<span data-ttu-id="67686-181">ダウンロードしたファイルと添付ファイルをスキャンする</span><span class="sxs-lookup"><span data-stu-id="67686-181">Scan all downloaded files and attachments</span></span>|<span data-ttu-id="67686-182">Enabled</span><span class="sxs-lookup"><span data-stu-id="67686-182">Enabled</span></span>
<span data-ttu-id="67686-183">コンピューター上のファイルとプログラムのアクティビティを監視する</span><span class="sxs-lookup"><span data-stu-id="67686-183">Monitor file and program activity on your computer</span></span>|<span data-ttu-id="67686-184">Enabled</span><span class="sxs-lookup"><span data-stu-id="67686-184">Enabled</span></span>

<br>

<span data-ttu-id="67686-185">**ポリシーの場所:** \Windows コンポーネント\Microsoft Defender ウイルス対策\Scan</span><span class="sxs-lookup"><span data-stu-id="67686-185">**Policy location:**  \Windows Components\Microsoft Defender Antivirus\Scan</span></span>

<span data-ttu-id="67686-186">これらの設定は、エンドポイントの定期的なスキャンを構成します。</span><span class="sxs-lookup"><span data-stu-id="67686-186">These settings configure periodic scans of the endpoint.</span></span> <span data-ttu-id="67686-187">毎週のクイック スキャンを実行することをお勧めします。パフォーマンスが許容されます。</span><span class="sxs-lookup"><span data-stu-id="67686-187">We recommend performing a weekly quick scan, performance permitting.</span></span>

<span data-ttu-id="67686-188">ポリシー</span><span class="sxs-lookup"><span data-stu-id="67686-188">Policy</span></span> | <span data-ttu-id="67686-189">Setting</span><span class="sxs-lookup"><span data-stu-id="67686-189">Setting</span></span> 
:---|:---
<span data-ttu-id="67686-190">スケジュールされたスキャンを実行する前に、最新のウイルスとスパイウェアのセキュリティ インテリジェンスを確認する</span><span class="sxs-lookup"><span data-stu-id="67686-190">Check for the latest virus and spyware security intelligence before running a scheduled scan</span></span> |<span data-ttu-id="67686-191">Enabled</span><span class="sxs-lookup"><span data-stu-id="67686-191">Enabled</span></span>

<br>

<span data-ttu-id="67686-192">**ポリシーの場所:** \Windows コンポーネント\Microsoft Defender ウイルス対策\Microsoft Defender Exploit Guard\Attack Surface Reduction</span><span class="sxs-lookup"><span data-stu-id="67686-192">**Policy location:** \Windows Components\Microsoft Defender Antivirus\Microsoft Defender Exploit Guard\Attack Surface Reduction</span></span>

<span data-ttu-id="67686-193">[攻撃表面の縮小ルールのカスタマイズ] から攻撃表面の縮小 GUID [の現在のリストを取得する](customize-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="67686-193">Get the current list of attack surface reduction GUIDs from [Customize attack surface reduction rules](customize-attack-surface-reduction.md)</span></span>

1. <span data-ttu-id="67686-194">[攻撃表面 **縮小の構成] ポリシーを開** きます。</span><span class="sxs-lookup"><span data-stu-id="67686-194">Open the **Configure Attack Surface Reduction** policy.</span></span>

1. <span data-ttu-id="67686-195">**[有効]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="67686-195">Select **Enabled**.</span></span>

1. <span data-ttu-id="67686-196">[表示] **ボタンを** 選択します。</span><span class="sxs-lookup"><span data-stu-id="67686-196">Select the **Show** button.</span></span>

1. <span data-ttu-id="67686-197">[値の名前] フィールドに **、値が** 2 の各 GUID を追加します。</span><span class="sxs-lookup"><span data-stu-id="67686-197">Add each GUID in the **Value Name** field with a Value of 2.</span></span>

   <span data-ttu-id="67686-198">これにより、監査専用に設定されます。</span><span class="sxs-lookup"><span data-stu-id="67686-198">This will set each up for audit only.</span></span>

   ![攻撃表面の縮小構成のイメージ](images/asr-guid.png)

<span data-ttu-id="67686-200">ポリシー</span><span class="sxs-lookup"><span data-stu-id="67686-200">Policy</span></span> | <span data-ttu-id="67686-201">Setting</span><span class="sxs-lookup"><span data-stu-id="67686-201">Setting</span></span>
:---|:---
<span data-ttu-id="67686-202">フォルダー アクセスの制御を構成する</span><span class="sxs-lookup"><span data-stu-id="67686-202">Configure Controlled folder access</span></span>| <span data-ttu-id="67686-203">有効、監査モード</span><span class="sxs-lookup"><span data-stu-id="67686-203">Enabled, Audit Mode</span></span>

## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="67686-204">グループ ポリシーを使用してデバイスをオフボードする</span><span class="sxs-lookup"><span data-stu-id="67686-204">Offboard devices using Group Policy</span></span>

<span data-ttu-id="67686-205">セキュリティ上の理由から、Offboard デバイスに使用されるパッケージは、ダウンロード日から 30 日後に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="67686-205">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="67686-206">デバイスに送信された期限切れのオフボード パッケージは拒否されます。</span><span class="sxs-lookup"><span data-stu-id="67686-206">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="67686-207">オフボード パッケージをダウンロードすると、パッケージの有効期限が通知され、パッケージ名にも含まれます。</span><span class="sxs-lookup"><span data-stu-id="67686-207">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="67686-208">オンボーディングポリシーとオフボード ポリシーを同じデバイスに同時に展開し、それ以外の場合は予期しない競合を引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="67686-208">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="67686-209">ポータルからオフボード パッケージ[Microsoft 365 Defenderします](https://security.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="67686-209">Get the offboarding package from [Microsoft 365 Defender portal](https://security.microsoft.com/):</span></span>

    1. <span data-ttu-id="67686-210">ナビゲーション ウィンドウで、[エンドポイント **デバイス** 設定  >  **オフ**  >  **ボード]**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="67686-210">In the navigation pane, select **Settings** > **Endpoints** > **Device management** > **Offboarding**.</span></span>

    1. <span data-ttu-id="67686-211">オペレーティング システムWindows 10を選択します。</span><span class="sxs-lookup"><span data-stu-id="67686-211">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="67686-212">[展開方法 **] フィールドで** 、[グループ ポリシー] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="67686-212">In the **Deployment method** field, select **Group policy**.</span></span>

    1. <span data-ttu-id="67686-213">[パッケージ **のダウンロード] を** クリックし、.zip保存します。</span><span class="sxs-lookup"><span data-stu-id="67686-213">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="67686-214">デバイスからアクセスできる.zipファイルの内容を読み取り専用の共有場所に抽出します。</span><span class="sxs-lookup"><span data-stu-id="67686-214">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="67686-215">*-MM-DD.cmd WindowsDefenderATPOffboardingScript_valid_until_YYYYという名前のファイルが必要です*。</span><span class="sxs-lookup"><span data-stu-id="67686-215">You should have a file named *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

3. <span data-ttu-id="67686-216">グループ ポリシー [管理コンソール](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) を開き、構成するグループ ポリシー オブジェクト (GPO) を右クリックし、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="67686-216">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

4. <span data-ttu-id="67686-217">グループ ポリシー **管理エディターで、[\*\*\*\*コンピューターの構成**] 、[基本設定] の順に移動し、[コントロール パネルの **設定] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="67686-217">In the **Group Policy Management Editor**, go to **Computer configuration,** then **Preferences**, and then **Control panel settings**.</span></span>

5. <span data-ttu-id="67686-218">[スケジュールされたタスク] **を右クリック** し、[新規] をポイント **し**、[イミディエイト タスク] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="67686-218">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate task**.</span></span>

6. <span data-ttu-id="67686-219">開く **[タスク]** ウィンドウで、[全般] タブ **に移動** します。[セキュリティ オプション] の [ローカル SYSTEM ユーザー アカウント (BUILTIN\SYSTEM) **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="67686-219">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options**.</span></span>

7. <span data-ttu-id="67686-220">[ **ユーザーがログオンするかどうかを実行する] を選択し** 、[最高の特権で実行する **]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="67686-220">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

8. <span data-ttu-id="67686-221">[アクション] タブ **に移動し** 、[ **新規...] をクリックします**。[アクション **] フィールドで [プログラム** の開始] が選択 **されている必要** があります。</span><span class="sxs-lookup"><span data-stu-id="67686-221">Go to the **Actions** tab and click **New...**. Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="67686-222">共有ファイル *-MM-DD.cmd ファイルWindowsDefenderATPOffboardingScript_valid_until_YYYY NetBIOS パスを入力* します。</span><span class="sxs-lookup"><span data-stu-id="67686-222">Enter the NetBIOS path of the shared *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

9. <span data-ttu-id="67686-223">**[OK] を** クリックし、開いている GPMC ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="67686-223">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67686-224">Offboarding を使用すると、デバイスはポータルへのセンサー データの送信を停止しますが、デバイスからのデータ (通知への参照を含む) は最大 6 か月間保持されます。</span><span class="sxs-lookup"><span data-stu-id="67686-224">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

## <a name="monitor-device-configuration"></a><span data-ttu-id="67686-225">デバイス構成の監視</span><span class="sxs-lookup"><span data-stu-id="67686-225">Monitor device configuration</span></span>

<span data-ttu-id="67686-226">グループ ポリシーでは、デバイス上のポリシーの展開を監視するオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="67686-226">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="67686-227">監視は、ポータルまたはさまざまな展開ツールを使用して直接実行できます。</span><span class="sxs-lookup"><span data-stu-id="67686-227">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="67686-228">ポータルを使用してデバイスを監視する</span><span class="sxs-lookup"><span data-stu-id="67686-228">Monitor devices using the portal</span></span>

1. <span data-ttu-id="67686-229">[ポータル] [Microsoft 365 Defender移動します](https://security.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="67686-229">Go to [Microsoft 365 Defender portal](https://security.microsoft.com/).</span></span>
2. <span data-ttu-id="67686-230">[デバイス **インベントリ] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="67686-230">Click **Devices inventory**.</span></span>
3. <span data-ttu-id="67686-231">デバイスが表示されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="67686-231">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="67686-232">デバイスが [デバイス] リストに表示を開始するには、数日 **かかる場合があります**。</span><span class="sxs-lookup"><span data-stu-id="67686-232">It can take several days for devices to start showing on the **Devices list**.</span></span> <span data-ttu-id="67686-233">これには、ポリシーがデバイスに配布される時間、ユーザーがログオンする前にかかる時間、エンドポイントがレポートを開始するのにかかる時間が含まれます。</span><span class="sxs-lookup"><span data-stu-id="67686-233">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>

## <a name="related-topics"></a><span data-ttu-id="67686-234">関連項目</span><span class="sxs-lookup"><span data-stu-id="67686-234">Related topics</span></span>

- [<span data-ttu-id="67686-235">デバイスをWindows 10デバイスをオンボードMicrosoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="67686-235">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="67686-236">モバイル デバイス管理ツールを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="67686-236">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="67686-237">ローカル スクリプトを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="67686-237">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="67686-238">非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="67686-238">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="67686-239">新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する</span><span class="sxs-lookup"><span data-stu-id="67686-239">Run a detection test on a newly onboarded Microsoft Defender for Endpoint devices</span></span>](run-detection-test.md)
- [<span data-ttu-id="67686-240">Microsoft Defender for Endpoint オンボーディングの問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="67686-240">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
