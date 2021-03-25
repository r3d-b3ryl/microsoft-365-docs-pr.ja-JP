---
title: グループ ポリシーを使用して Windows 10 デバイスを Microsoft Defender ATP にオンボードする
description: グループ ポリシーを使用して、構成パッケージを Windows 10 デバイスに展開して、サービスにオンボードします。
keywords: グループ ポリシーを使用したデバイスの構成、デバイス管理、Windows ATP デバイスの構成、Microsoft Defender for Endpoint デバイスのオンボード、グループ ポリシー
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
ms.openlocfilehash: fc4b17ef96e85d3bacd4e83c2de3f4bb7fbfa5c3
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166173"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a><span data-ttu-id="abc91-104">グループ ポリシーを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="abc91-104">Onboard Windows 10 devices using Group Policy</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="abc91-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="abc91-105">**Applies to:**</span></span>

- <span data-ttu-id="abc91-106">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="abc91-106">Group Policy</span></span>
- [<span data-ttu-id="abc91-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="abc91-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="abc91-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="abc91-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="abc91-109">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="abc91-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="abc91-110">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="abc91-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsgp-abovefoldlink)


> [!NOTE]
> <span data-ttu-id="abc91-111">グループ ポリシー (GP) 更新プログラムを使用してパッケージを展開するには、グループ ポリシー以降Windows Server 2008 R2必要があります。</span><span class="sxs-lookup"><span data-stu-id="abc91-111">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>
> 
> <span data-ttu-id="abc91-112">Windows Server 2019 では、グループ ポリシーの基本設定で作成される XML ファイルの NT AUTHORITY\Well-Known-System-Account を NT AUTHORITY\SYSTEM に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="abc91-112">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="abc91-113">グループ ポリシーを使用したオンボード デバイス</span><span class="sxs-lookup"><span data-stu-id="abc91-113">Onboard devices using Group Policy</span></span>

<span data-ttu-id="abc91-114">[![さまざまな展開パスを示す PDF のイメージ](images/onboard-gp.png)](images/onboard-gp.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="abc91-114">[![Image of the PDF showing the various deployment paths](images/onboard-gp.png)](images/onboard-gp.png#lightbox)</span></span>

<span data-ttu-id="abc91-115">PDF または[Visio を参照](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)[して、Defender](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) for Endpoint の展開のさまざまなパスを確認してください。</span><span class="sxs-lookup"><span data-stu-id="abc91-115">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Defender for Endpoint.</span></span> 



1. <span data-ttu-id="abc91-116">サービス オンボーディング ウィザードからダウンロードした GP *構成パッケージ*.zip ファイル (WindowsDefenderATPOnboardingPackage.zip) を開きます。</span><span class="sxs-lookup"><span data-stu-id="abc91-116">Open the GP configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="abc91-117">Microsoft Defender セキュリティ センターからパッケージ [を取得できます](https://securitycenter.windows.com/)。</span><span class="sxs-lookup"><span data-stu-id="abc91-117">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>
 
    1. <span data-ttu-id="abc91-118">ナビゲーション ウィンドウで、[設定オンボーディング]  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="abc91-118">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

    1. <span data-ttu-id="abc91-119">オペレーティング システムとして [Windows 10] を選択します。</span><span class="sxs-lookup"><span data-stu-id="abc91-119">Select Windows 10 as the operating system.</span></span>
    
    1. <span data-ttu-id="abc91-120">[展開方法 **] フィールドで** 、[グループ ポリシー] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="abc91-120">In the **Deployment method** field, select **Group policy**.</span></span>
    
    1. <span data-ttu-id="abc91-121">[パッケージ **のダウンロード] を** クリックし、.zip ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="abc91-121">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="abc91-122">.zip ファイルの内容を、デバイスがアクセスできる共有の読み取り専用の場所に展開します。</span><span class="sxs-lookup"><span data-stu-id="abc91-122">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="abc91-123">*OptionalParamsPolicy* というフォルダーと *WindowsDefenderATPOnboardingScript.cmd というファイルが必要です*。</span><span class="sxs-lookup"><span data-stu-id="abc91-123">You should have a folder called *OptionalParamsPolicy* and the file *WindowsDefenderATPOnboardingScript.cmd*.</span></span>

3. <span data-ttu-id="abc91-124">グループ ポリシー [管理コンソール](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) を開き、構成するグループ ポリシー オブジェクト (GPO) を右クリックし、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="abc91-124">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

4. <span data-ttu-id="abc91-125">グループ ポリシー **管理エディターで、[\*\*\*\*コンピューターの構成**] 、[基本設定] の順に移動し、[コントロール パネルの **設定] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="abc91-125">In the **Group Policy Management Editor**, go to **Computer configuration**, then **Preferences**, and then **Control panel settings**.</span></span>

5. <span data-ttu-id="abc91-126">[スケジュールされたタスク **] を** 右クリックし、[新規] をポイントし、[イミディエイト タスク] (少なくとも Windows **7) をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="abc91-126">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate Task (At least Windows 7)**.</span></span>

6. <span data-ttu-id="abc91-127">開く **[タスク]** ウィンドウで、[全般] タブ **に移動** します。[セキュリティ **オプション] で、[\*\*\*\*ユーザーまたはグループの変更**] をクリックし、[SYSTEM] と入力し、[名前の確認] をクリック **して** **[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="abc91-127">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK**.</span></span> <span data-ttu-id="abc91-128">NT AUTHORITY\SYSTEM は、タスクが実行されるユーザー アカウントとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="abc91-128">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

7. <span data-ttu-id="abc91-129">[ **ユーザーがログオンするかどうかを実行する] を選択し** 、[最高の特権で実行する **] チェック ボックスを** オンにします。</span><span class="sxs-lookup"><span data-stu-id="abc91-129">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

8. <span data-ttu-id="abc91-130">[操作] タブ **に移動し** 、[新規] **をクリックします。** [アクション **] フィールドで [プログラム** の開始] が選択 **されている必要** があります。</span><span class="sxs-lookup"><span data-stu-id="abc91-130">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="abc91-131">共有 *WindowsDefenderATPOnboardingScript.cmd* ファイルのファイル名と場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="abc91-131">Enter the file name and location of the shared *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

9. <span data-ttu-id="abc91-132">**[OK] を** クリックし、開いている GPMC ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="abc91-132">Click **OK** and close any open GPMC windows.</span></span>

>[!TIP]
> <span data-ttu-id="abc91-133">デバイスのオンボード後、検出テストを実行して、デバイスがサービスに適切にオンボードされていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="abc91-133">After onboarding the device, you can choose to run a detection test to verify that the device is properly onboarded to the service.</span></span> <span data-ttu-id="abc91-134">詳細については、「新しくオンボードされた Defender for Endpoint デバイスで検出テストを実行 [する」を参照してください](run-detection-test.md)。</span><span class="sxs-lookup"><span data-stu-id="abc91-134">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint device](run-detection-test.md).</span></span>

## <a name="additional-defender-for-endpoint-configuration-settings"></a><span data-ttu-id="abc91-135">エンドポイントの追加の Defender 構成設定</span><span class="sxs-lookup"><span data-stu-id="abc91-135">Additional Defender for Endpoint configuration settings</span></span>
<span data-ttu-id="abc91-136">各デバイスについて、Microsoft Defender Security Center を介して詳細な分析用のファイルを提出する要求が行われたときに、デバイスからサンプルを収集できるかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="abc91-136">For each device, you can state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

<span data-ttu-id="abc91-137">グループ ポリシー (GP) を使用して、ディープ分析機能で使用されるサンプル共有の設定などの設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="abc91-137">You can use Group Policy (GP) to configure settings, such as settings for the sample sharing used in the deep analysis feature.</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="abc91-138">サンプル コレクション設定の構成</span><span class="sxs-lookup"><span data-stu-id="abc91-138">Configure sample collection settings</span></span>
1.  <span data-ttu-id="abc91-139">GP 管理デバイスで、構成パッケージから次のファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="abc91-139">On your GP management device, copy the following files from the configuration package:</span></span>

    - <span data-ttu-id="abc91-140">_AtpConfiguration.admx を_ _C: Windows \\ \\ PolicyDefinitions にコピーする_</span><span class="sxs-lookup"><span data-stu-id="abc91-140">Copy _AtpConfiguration.admx_ into _C:\\Windows\\PolicyDefinitions_</span></span>

    - <span data-ttu-id="abc91-141">_AtpConfiguration.adml を_ _C: Windows \\ \\ PolicyDefinitions \\ ja-US にコピーする_</span><span class="sxs-lookup"><span data-stu-id="abc91-141">Copy _AtpConfiguration.adml_ into _C:\\Windows\\PolicyDefinitions\\en-US_</span></span>

    <span data-ttu-id="abc91-142">グループ ポリシー管理用テンプレートに [セントラル ストア](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)を使用している場合は、構成パッケージから次のファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="abc91-142">If you are using a [Central Store for Group Policy Administrative Templates](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra), copy the following files from the configuration package:</span></span>
    
    - <span data-ttu-id="abc91-143">SysVol ポリシー _\\ \\ \<forest.root\> \\ \\ \<forest.root\> \\ \\ PolicyDefinitions に AtpConfiguration.admx をコピーする_</span><span class="sxs-lookup"><span data-stu-id="abc91-143">Copy _AtpConfiguration.admx_ into _\\\\\<forest.root\>\\SysVol\\\<forest.root\>\\Policies\\PolicyDefinitions_</span></span>

    - <span data-ttu-id="abc91-144">_AtpConfiguration.adml を_ _\\ \\ \<forest.root\> \\ SysVol \\ \<forest.root\> \\ ポリシー \\ PolicyDefinitions \\ en-US にコピーする_</span><span class="sxs-lookup"><span data-stu-id="abc91-144">Copy _AtpConfiguration.adml_ into _\\\\\<forest.root\>\\SysVol\\\<forest.root\>\\Policies\\PolicyDefinitions\\en-US_</span></span>

2.  <span data-ttu-id="abc91-145">グループ ポリシー [管理コンソールを開き](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)、構成する GPO を右クリックし、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="abc91-145">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11), right-click the GPO you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="abc91-146">グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="abc91-146">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="abc91-147">[ポリシー **] をクリックし**、[管理 **用テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="abc91-147">Click **Policies**, then **Administrative templates**.</span></span>

5.  <span data-ttu-id="abc91-148">[Windows **コンポーネント] をクリック** し **、[ATP] Windows Defenderクリックします**。</span><span class="sxs-lookup"><span data-stu-id="abc91-148">Click **Windows components** and then **Windows Defender ATP**.</span></span>

6.  <span data-ttu-id="abc91-149">デバイスからのサンプル共有を有効または無効にする場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="abc91-149">Choose to enable or disable sample sharing from your devices.</span></span>

>[!NOTE]
> <span data-ttu-id="abc91-150">値を設定しない場合、既定値はサンプル コレクションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="abc91-150">If you don't set a value, the default value is to enable sample collection.</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="abc91-151">その他の推奨構成設定</span><span class="sxs-lookup"><span data-stu-id="abc91-151">Other recommended configuration settings</span></span>

### <a name="update-endpoint-protection-configuration"></a><span data-ttu-id="abc91-152">エンドポイント保護構成の更新</span><span class="sxs-lookup"><span data-stu-id="abc91-152">Update endpoint protection configuration</span></span>

<span data-ttu-id="abc91-153">オンボーディング スクリプトを構成したら、同じグループ ポリシーの編集を続けてエンドポイント保護構成を追加します。</span><span class="sxs-lookup"><span data-stu-id="abc91-153">After configuring the onboarding script, continue editing the same group policy to add endpoint protection configurations.</span></span> <span data-ttu-id="abc91-154">Windows 10 または Server 2019 を実行しているシステムからグループ ポリシーの編集を実行して、必要なすべての Microsoft Defender ウイルス対策機能を確実に使用します。</span><span class="sxs-lookup"><span data-stu-id="abc91-154">Perform group policy edits from a system running Windows 10 or Server 2019 to ensure you have all of the required Microsoft Defender Antivirus capabilities.</span></span> <span data-ttu-id="abc91-155">Defender ATP 構成設定を登録するには、グループ ポリシー オブジェクトを閉じて再度開く必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="abc91-155">You may need to close and reopen the group policy object to register the Defender ATP configuration settings.</span></span>

<span data-ttu-id="abc91-156">すべてのポリシーは 、 の下に位置します `Computer Configuration\Policies\Administrative Templates` 。</span><span class="sxs-lookup"><span data-stu-id="abc91-156">All policies are located under `Computer Configuration\Policies\Administrative Templates`.</span></span>

<span data-ttu-id="abc91-157">**ポリシーの場所:** \Windows Components\Windows Defender ATP</span><span class="sxs-lookup"><span data-stu-id="abc91-157">**Policy location:** \Windows Components\Windows Defender ATP</span></span>

<span data-ttu-id="abc91-158">ポリシー</span><span class="sxs-lookup"><span data-stu-id="abc91-158">Policy</span></span> | <span data-ttu-id="abc91-159">Setting</span><span class="sxs-lookup"><span data-stu-id="abc91-159">Setting</span></span> 
:---|:---
<span data-ttu-id="abc91-160">Enable\Disable Sample collection</span><span class="sxs-lookup"><span data-stu-id="abc91-160">Enable\Disable Sample collection</span></span>|   <span data-ttu-id="abc91-161">[有効] - [コンピューターでサンプル コレクションを有効にする] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="abc91-161">Enabled - "Enable sample collection on machines" checked</span></span>

<br/>

<span data-ttu-id="abc91-162">**ポリシーの場所:**  \Windows Components\Windows Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="abc91-162">**Policy location:**  \Windows Components\Windows Defender Antivirus</span></span>

<span data-ttu-id="abc91-163">ポリシー</span><span class="sxs-lookup"><span data-stu-id="abc91-163">Policy</span></span> | <span data-ttu-id="abc91-164">Setting</span><span class="sxs-lookup"><span data-stu-id="abc91-164">Setting</span></span> 
:---|:---
<span data-ttu-id="abc91-165">望ましくない可能性があるアプリケーションの検出を構成する</span><span class="sxs-lookup"><span data-stu-id="abc91-165">Configure detection for potentially unwanted applications</span></span> | <span data-ttu-id="abc91-166">有効、ブロック</span><span class="sxs-lookup"><span data-stu-id="abc91-166">Enabled, Block</span></span>

<br/>

<span data-ttu-id="abc91-167">**ポリシーの場所:** \Windows Components\Windows Defender ウイルス対策\MAPS</span><span class="sxs-lookup"><span data-stu-id="abc91-167">**Policy location:** \Windows Components\Windows Defender Antivirus\MAPS</span></span>

<span data-ttu-id="abc91-168">ポリシー</span><span class="sxs-lookup"><span data-stu-id="abc91-168">Policy</span></span> | <span data-ttu-id="abc91-169">Setting</span><span class="sxs-lookup"><span data-stu-id="abc91-169">Setting</span></span> 
:---|:---
<span data-ttu-id="abc91-170">Microsoft MAPS に参加する</span><span class="sxs-lookup"><span data-stu-id="abc91-170">Join Microsoft MAPS</span></span> | <span data-ttu-id="abc91-171">有効、高度なマップ</span><span class="sxs-lookup"><span data-stu-id="abc91-171">Enabled, Advanced MAPS</span></span>
<span data-ttu-id="abc91-172">詳細な分析が必要な場合にファイル サンプルを送信する</span><span class="sxs-lookup"><span data-stu-id="abc91-172">Send file samples when further analysis is required</span></span> | <span data-ttu-id="abc91-173">有効、安全なサンプルの送信</span><span class="sxs-lookup"><span data-stu-id="abc91-173">Enabled, Send safe samples</span></span>

<br/>

<span data-ttu-id="abc91-174">**ポリシーの場所:** \Windows Components\Windows Defenderウイルス対策\リアルタイム保護</span><span class="sxs-lookup"><span data-stu-id="abc91-174">**Policy location:** \Windows Components\Windows Defender Antivirus\Real-time Protection</span></span>

<span data-ttu-id="abc91-175">ポリシー</span><span class="sxs-lookup"><span data-stu-id="abc91-175">Policy</span></span> | <span data-ttu-id="abc91-176">Setting</span><span class="sxs-lookup"><span data-stu-id="abc91-176">Setting</span></span> 
:---|:---
<span data-ttu-id="abc91-177">リアルタイム保護をオフにする</span><span class="sxs-lookup"><span data-stu-id="abc91-177">Turn off real-time protection</span></span>|<span data-ttu-id="abc91-178">無効</span><span class="sxs-lookup"><span data-stu-id="abc91-178">Disabled</span></span>
<span data-ttu-id="abc91-179">動作の監視を有効にする</span><span class="sxs-lookup"><span data-stu-id="abc91-179">Turn on behavior monitoring</span></span>|<span data-ttu-id="abc91-180">有効</span><span class="sxs-lookup"><span data-stu-id="abc91-180">Enabled</span></span>
<span data-ttu-id="abc91-181">ダウンロードしたファイルと添付ファイルをスキャンする</span><span class="sxs-lookup"><span data-stu-id="abc91-181">Scan all downloaded files and attachments</span></span>|<span data-ttu-id="abc91-182">有効</span><span class="sxs-lookup"><span data-stu-id="abc91-182">Enabled</span></span>
<span data-ttu-id="abc91-183">コンピューター上のファイルとプログラムのアクティビティを監視する</span><span class="sxs-lookup"><span data-stu-id="abc91-183">Monitor file and program activity on your computer</span></span>|<span data-ttu-id="abc91-184">有効</span><span class="sxs-lookup"><span data-stu-id="abc91-184">Enabled</span></span>

<br/>

<span data-ttu-id="abc91-185">**ポリシーの場所:**  \Windows Components\Windows Defenderウイルス対策\スキャン</span><span class="sxs-lookup"><span data-stu-id="abc91-185">**Policy location:**  \Windows Components\Windows Defender Antivirus\Scan</span></span>

<span data-ttu-id="abc91-186">これらの設定は、エンドポイントの定期的なスキャンを構成します。</span><span class="sxs-lookup"><span data-stu-id="abc91-186">These settings configure periodic scans of the endpoint.</span></span> <span data-ttu-id="abc91-187">毎週のクイック スキャンを実行することをお勧めします。パフォーマンスが許容されます。</span><span class="sxs-lookup"><span data-stu-id="abc91-187">We recommend performing a weekly quick scan, performance permitting.</span></span>

<span data-ttu-id="abc91-188">ポリシー</span><span class="sxs-lookup"><span data-stu-id="abc91-188">Policy</span></span> | <span data-ttu-id="abc91-189">Setting</span><span class="sxs-lookup"><span data-stu-id="abc91-189">Setting</span></span> 
:---|:---
<span data-ttu-id="abc91-190">スケジュールされたスキャンを実行する前に、最新のウイルスとスパイウェアのセキュリティ インテリジェンスを確認する</span><span class="sxs-lookup"><span data-stu-id="abc91-190">Check for the latest virus and spyware security intelligence before running a scheduled scan</span></span> |<span data-ttu-id="abc91-191">有効</span><span class="sxs-lookup"><span data-stu-id="abc91-191">Enabled</span></span>


<br/>

<span data-ttu-id="abc91-192">**ポリシーの場所:** \Windows Components\Windows Defender ウイルス対策\Windows Defender Exploit Guard\Attack Surface Reduction</span><span class="sxs-lookup"><span data-stu-id="abc91-192">**Policy location:** \Windows Components\Windows Defender Antivirus\Windows Defender Exploit Guard\Attack Surface Reduction</span></span>

<span data-ttu-id="abc91-193">[攻撃表面の縮小ルールのカスタマイズ] から攻撃表面の縮小 GUID [の現在のリストを取得する](customize-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="abc91-193">Get the current list of attack surface reduction GUIDs from [Customize attack surface reduction rules](customize-attack-surface-reduction.md)</span></span>

1. <span data-ttu-id="abc91-194">[攻撃表面 **縮小の構成] ポリシーを開** きます。</span><span class="sxs-lookup"><span data-stu-id="abc91-194">Open the **Configure Attack Surface Reduction** policy.</span></span>

1. <span data-ttu-id="abc91-195">**[有効]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="abc91-195">Select **Enabled**.</span></span>

1. <span data-ttu-id="abc91-196">[表示] **ボタンを** 選択します。</span><span class="sxs-lookup"><span data-stu-id="abc91-196">Select the **Show** button.</span></span>

1. <span data-ttu-id="abc91-197">[値の名前] フィールドに **、値が** 2 の各 GUID を追加します。</span><span class="sxs-lookup"><span data-stu-id="abc91-197">Add each GUID in the **Value Name** field with a Value of 2.</span></span>

   <span data-ttu-id="abc91-198">これにより、監査専用に設定されます。</span><span class="sxs-lookup"><span data-stu-id="abc91-198">This will set each up for audit only.</span></span>

   ![攻撃表面の縮小構成のイメージ](images/asr-guid.png)



<span data-ttu-id="abc91-200">ポリシー</span><span class="sxs-lookup"><span data-stu-id="abc91-200">Policy</span></span> | <span data-ttu-id="abc91-201">Setting</span><span class="sxs-lookup"><span data-stu-id="abc91-201">Setting</span></span> 
:---|:---
<span data-ttu-id="abc91-202">フォルダー アクセスの制御を構成する</span><span class="sxs-lookup"><span data-stu-id="abc91-202">Configure Controlled folder access</span></span>| <span data-ttu-id="abc91-203">有効、監査モード</span><span class="sxs-lookup"><span data-stu-id="abc91-203">Enabled, Audit Mode</span></span>



## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="abc91-204">グループ ポリシーを使用してデバイスをオフボードする</span><span class="sxs-lookup"><span data-stu-id="abc91-204">Offboard devices using Group Policy</span></span>
<span data-ttu-id="abc91-205">セキュリティ上の理由から、Offboard デバイスに使用されるパッケージは、ダウンロード日から 30 日後に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="abc91-205">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="abc91-206">デバイスに送信された期限切れのオフボード パッケージは拒否されます。</span><span class="sxs-lookup"><span data-stu-id="abc91-206">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="abc91-207">オフボード パッケージをダウンロードすると、パッケージの有効期限が通知され、パッケージ名にも含まれます。</span><span class="sxs-lookup"><span data-stu-id="abc91-207">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="abc91-208">オンボーディングポリシーとオフボード ポリシーを同じデバイスに同時に展開し、それ以外の場合は予期しない競合を引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="abc91-208">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="abc91-209">Microsoft Defender セキュリティ センターからオフボード パッケージ [を取得します](https://securitycenter.windows.com/)。</span><span class="sxs-lookup"><span data-stu-id="abc91-209">Get the offboarding package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="abc91-210">ナビゲーション ウィンドウで、[設定] [**オフボード]**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="abc91-210">In the navigation pane, select **Settings** > **Offboarding**.</span></span>

    1. <span data-ttu-id="abc91-211">オペレーティング システムとして [Windows 10] を選択します。</span><span class="sxs-lookup"><span data-stu-id="abc91-211">Select Windows 10 as the operating system.</span></span>
    
    1. <span data-ttu-id="abc91-212">[展開方法 **] フィールドで** 、[グループ ポリシー] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="abc91-212">In the **Deployment method** field, select **Group policy**.</span></span>

    1. <span data-ttu-id="abc91-213">[パッケージ **のダウンロード] を** クリックし、.zip ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="abc91-213">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="abc91-214">.zip ファイルの内容を、デバイスがアクセスできる共有の読み取り専用の場所に展開します。</span><span class="sxs-lookup"><span data-stu-id="abc91-214">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="abc91-215">*-MM-DD.cmd WindowsDefenderATPOffboardingScript_valid_until_YYYYという名前のファイルが必要です*。</span><span class="sxs-lookup"><span data-stu-id="abc91-215">You should have a file named *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

3. <span data-ttu-id="abc91-216">グループ ポリシー [管理コンソール](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) を開き、構成するグループ ポリシー オブジェクト (GPO) を右クリックし、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="abc91-216">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

4. <span data-ttu-id="abc91-217">グループ ポリシー **管理エディターで、[\*\*\*\*コンピューターの構成**] 、[基本設定] の順に移動し、[コントロール パネルの **設定] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="abc91-217">In the **Group Policy Management Editor**, go to **Computer configuration,** then **Preferences**, and then **Control panel settings**.</span></span>

5. <span data-ttu-id="abc91-218">[スケジュールされたタスク] **を右クリック** し、[新規] をポイント **し**、[イミディエイト タスク] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="abc91-218">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate task**.</span></span>

6. <span data-ttu-id="abc91-219">開く **[タスク]** ウィンドウで、[全般] タブ **に移動** します。[セキュリティ オプション] の [ローカル SYSTEM ユーザー アカウント (BUILTIN\SYSTEM) **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="abc91-219">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options**.</span></span>

7. <span data-ttu-id="abc91-220">[ **ユーザーがログオンするかどうかを実行する] を選択し** 、[最高の特権で実行する **]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="abc91-220">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

8. <span data-ttu-id="abc91-221">[アクション] タブ **に移動し** 、[ **新規...] をクリックします**。[アクション **] フィールドで [プログラム** の開始] が選択 **されている必要** があります。</span><span class="sxs-lookup"><span data-stu-id="abc91-221">Go to the **Actions** tab and click **New...**. Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="abc91-222">共有ファイルのファイル名と場所を  *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd ファイルを入力* します。</span><span class="sxs-lookup"><span data-stu-id="abc91-222">Enter the file name and location of the shared  *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

9. <span data-ttu-id="abc91-223">**[OK] を** クリックし、開いている GPMC ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="abc91-223">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="abc91-224">Offboarding を使用すると、デバイスはポータルへのセンサー データの送信を停止しますが、デバイスからのデータ (通知への参照を含む) は最大 6 か月間保持されます。</span><span class="sxs-lookup"><span data-stu-id="abc91-224">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="abc91-225">デバイス構成の監視</span><span class="sxs-lookup"><span data-stu-id="abc91-225">Monitor device configuration</span></span>
<span data-ttu-id="abc91-226">グループ ポリシーでは、デバイス上のポリシーの展開を監視するオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="abc91-226">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="abc91-227">監視は、ポータルまたはさまざまな展開ツールを使用して直接実行できます。</span><span class="sxs-lookup"><span data-stu-id="abc91-227">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="abc91-228">ポータルを使用してデバイスを監視する</span><span class="sxs-lookup"><span data-stu-id="abc91-228">Monitor devices using the portal</span></span>
1. <span data-ttu-id="abc91-229">[Microsoft [Defender セキュリティ センター] に移動します](https://securitycenter.windows.com/)。</span><span class="sxs-lookup"><span data-stu-id="abc91-229">Go to [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span>
2. <span data-ttu-id="abc91-230">[デバイス **] リストをクリックします**。</span><span class="sxs-lookup"><span data-stu-id="abc91-230">Click **Devices list**.</span></span>
3. <span data-ttu-id="abc91-231">デバイスが表示されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="abc91-231">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="abc91-232">デバイスが [デバイス] リストに表示を開始するには、数日 **かかる場合があります**。</span><span class="sxs-lookup"><span data-stu-id="abc91-232">It can take several days for devices to start showing on the **Devices list**.</span></span> <span data-ttu-id="abc91-233">これには、ポリシーがデバイスに配布される時間、ユーザーがログオンする前にかかる時間、エンドポイントがレポートを開始するのにかかる時間が含まれます。</span><span class="sxs-lookup"><span data-stu-id="abc91-233">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="abc91-234">関連項目</span><span class="sxs-lookup"><span data-stu-id="abc91-234">Related topics</span></span>
- [<span data-ttu-id="abc91-235">Microsoft Endpoint Configuration Manager を使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="abc91-235">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="abc91-236">モバイル デバイス管理ツールを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="abc91-236">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="abc91-237">ローカル スクリプトを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="abc91-237">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="abc91-238">非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="abc91-238">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="abc91-239">新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する</span><span class="sxs-lookup"><span data-stu-id="abc91-239">Run a detection test on a newly onboarded Microsoft Defender for Endpoint devices</span></span>](run-detection-test.md)
- [<span data-ttu-id="abc91-240">Microsoft Defender for Endpoint オンボーディングの問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="abc91-240">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
