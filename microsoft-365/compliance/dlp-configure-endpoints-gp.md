---
title: グループ ポリシーを使用した Windows 10 デバイスのオンボード
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: グループ ポリシーを使用して、サービスにオンボードWindows 10デバイスに構成パッケージを展開します。
ms.openlocfilehash: 284de5169324b6da4038cfe0b50b2f2ffa40e3fd
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893288"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a><span data-ttu-id="bc2df-103">グループ ポリシー Windows 10デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="bc2df-103">Onboard Windows 10 devices using Group Policy</span></span> 

<span data-ttu-id="bc2df-104">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="bc2df-104">**Applies to:**</span></span>

- [<span data-ttu-id="bc2df-105">Microsoft 365エンドポイント データ損失防止 (DLP)</span><span class="sxs-lookup"><span data-stu-id="bc2df-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)
- <span data-ttu-id="bc2df-106">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="bc2df-106">Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="bc2df-107">グループ ポリシー (GP) 更新プログラムを使用してパッケージを展開するには、サーバー 2008 R2 以降Windowsする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc2df-107">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>

> <span data-ttu-id="bc2df-108">サーバー Windows 2019 では、グループ ポリシーの基本設定で作成される XML ファイルの NT AUTHORITY\Well-Known-System-Account を NT AUTHORITY\SYSTEM に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc2df-108">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="bc2df-109">グループ ポリシーを使用してデバイスをオンボードする</span><span class="sxs-lookup"><span data-stu-id="bc2df-109">Onboard devices using Group Policy</span></span>

1. <span data-ttu-id="bc2df-110">サービス オンボーディング ウィザードから.zipした gp 構成 *パッケージ*(DeviceComplianceOnboardingPackage.zip) を開きます。</span><span class="sxs-lookup"><span data-stu-id="bc2df-110">Open the GP configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="bc2df-111">また、Microsoft コンプライアンス センターからパッケージ [を取得できます。](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span><span class="sxs-lookup"><span data-stu-id="bc2df-111">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span></span>

2. <span data-ttu-id="bc2df-112">ナビゲーション ウィンドウで、[デバイス オンボーディング]**設定**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bc2df-112">In the navigation pane, select **Settings** > **Device Onboarding**.</span></span>

3. <span data-ttu-id="bc2df-113">[展開方法 **] フィールドで** 、[グループ ポリシー] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bc2df-113">In the **Deployment method** field, select **Group policy**.</span></span>

4. <span data-ttu-id="bc2df-114">[パッケージ **のダウンロード] を** クリックし、.zip保存します。</span><span class="sxs-lookup"><span data-stu-id="bc2df-114">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="bc2df-115">デバイスからアクセスできる.zipファイルの内容を読み取り専用の共有場所に抽出します。</span><span class="sxs-lookup"><span data-stu-id="bc2df-115">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="bc2df-116">*OptionalParamsPolicy* というフォルダーと *DeviceComplianceLocalOnboardingScript.cmd というファイルが必要です*。</span><span class="sxs-lookup"><span data-stu-id="bc2df-116">You should have a folder called *OptionalParamsPolicy* and the file *DeviceComplianceLocalOnboardingScript.cmd*.</span></span>

6. <span data-ttu-id="bc2df-117">グループ ポリシー [管理コンソール](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) を開き、構成するグループ ポリシー オブジェクト (GPO) を右クリックし、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="bc2df-117">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

7. <span data-ttu-id="bc2df-118">グループ ポリシー **管理エディターで、[\*\*\*\*コンピューターの構成**] 、[基本設定] の順に移動し、[コントロール パネルの **設定] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="bc2df-118">In the **Group Policy Management Editor**, go to **Computer configuration**, then **Preferences**, and then **Control panel settings**.</span></span>

8. <span data-ttu-id="bc2df-119">[スケジュールされたタスク **] を** 右クリックし、[新規] をポイントし、[イミディエイト タスク] (少なくとも Windows **7) をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="bc2df-119">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate Task (At least Windows 7)**.</span></span>

9. <span data-ttu-id="bc2df-120">開く **[タスク]** ウィンドウで、[全般] タブ **に移動** します。[セキュリティ **オプション] で、[\*\*\*\*ユーザーまたはグループの変更**] をクリックし、[SYSTEM] と入力し、[名前の確認] をクリック **して** **[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="bc2df-120">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK**.</span></span> <span data-ttu-id="bc2df-121">NT AUTHORITY\SYSTEM は、タスクが実行されるユーザー アカウントとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc2df-121">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

10. <span data-ttu-id="bc2df-122">[ **ユーザーがログオンするかどうかを実行する] を選択し** 、[最高の特権で実行する **] チェック ボックスを** オンにします。</span><span class="sxs-lookup"><span data-stu-id="bc2df-122">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

11. <span data-ttu-id="bc2df-123">[操作] タブ **に移動し** 、[新規] **をクリックします。** [アクション **] フィールドで [プログラム** の開始] が選択 **されている必要** があります。</span><span class="sxs-lookup"><span data-stu-id="bc2df-123">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="bc2df-124">共有 *WindowsDefenderATPOnboardingScript.cmd* ファイルのファイル名と場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="bc2df-124">Enter the file name and location of the shared *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

12. <span data-ttu-id="bc2df-125">**[OK] を** クリックし、開いている GPMC ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="bc2df-125">Click **OK** and close any open GPMC windows.</span></span>


## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="bc2df-126">グループ ポリシーを使用してデバイスをオフボードする</span><span class="sxs-lookup"><span data-stu-id="bc2df-126">Offboard devices using Group Policy</span></span>
<span data-ttu-id="bc2df-127">セキュリティ上の理由から、Offboard デバイスに使用されるパッケージは、ダウンロード日から 30 日後に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="bc2df-127">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="bc2df-128">デバイスに送信された期限切れのオフボード パッケージは拒否されます。</span><span class="sxs-lookup"><span data-stu-id="bc2df-128">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="bc2df-129">オフボード パッケージをダウンロードすると、パッケージの有効期限が通知され、パッケージ名にも含まれます。</span><span class="sxs-lookup"><span data-stu-id="bc2df-129">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="bc2df-130">オンボーディングポリシーとオフボード ポリシーを同じデバイスに同時に展開し、それ以外の場合は予期しない競合を引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bc2df-130">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="bc2df-131">Microsoft コンプライアンス センターからオフボード パッケージ [を取得します](https://compliance.microsoft.com/compliancesettings/deviceonboarding)。</span><span class="sxs-lookup"><span data-stu-id="bc2df-131">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding).</span></span>

2. <span data-ttu-id="bc2df-132">ナビゲーション ウィンドウで、[オンボーディング **/設定**  >  **オンボーディング]**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bc2df-132">In the navigation pane, select **Settings** > **//Device onboarding** > **Offboarding**.</span></span>

3. <span data-ttu-id="bc2df-133">[展開方法 **] フィールドで** 、[グループ ポリシー] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bc2df-133">In the **Deployment method** field, select **Group policy**.</span></span>

4. <span data-ttu-id="bc2df-134">[パッケージ **のダウンロード] を** クリックし、.zip保存します。</span><span class="sxs-lookup"><span data-stu-id="bc2df-134">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="bc2df-135">デバイスからアクセスできる.zipファイルの内容を読み取り専用の共有場所に抽出します。</span><span class="sxs-lookup"><span data-stu-id="bc2df-135">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="bc2df-136">*-MM-DD.cmd DeviceComplianceOffboardingScript_valid_until_YYYYという名前のファイルが必要です*。</span><span class="sxs-lookup"><span data-stu-id="bc2df-136">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

6. <span data-ttu-id="bc2df-137">グループ ポリシー [管理コンソール](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) を開き、構成するグループ ポリシー オブジェクト (GPO) を右クリックし、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="bc2df-137">Open the [Group Policy Management Console](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

7. <span data-ttu-id="bc2df-138">グループ ポリシー **管理エディターで、[\*\*\*\*コンピューターの構成**] 、[基本設定] の順に移動し、[コントロール パネルの **設定] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="bc2df-138">In the **Group Policy Management Editor**, go to **Computer configuration,** then **Preferences**, and then **Control panel settings**.</span></span>

8. <span data-ttu-id="bc2df-139">[スケジュールされたタスク] **を右クリック** し、[新規] をポイント **し**、[イミディエイト タスク] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="bc2df-139">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate task**.</span></span>

9. <span data-ttu-id="bc2df-140">開く **[タスク]** ウィンドウで、[全般] タブ **に移動** します。[セキュリティ オプション] の [ローカル SYSTEM ユーザー アカウント (BUILTIN\SYSTEM) **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bc2df-140">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options**.</span></span>

10. <span data-ttu-id="bc2df-141">[ **ユーザーがログオンするかどうかを実行する] を選択し** 、[最高の特権で実行する **]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="bc2df-141">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

11. <span data-ttu-id="bc2df-142">[アクション] タブ **に移動し** 、[ **新規...] をクリックします**。[アクション **] フィールドで [プログラム** の開始] が選択 **されている必要** があります。</span><span class="sxs-lookup"><span data-stu-id="bc2df-142">Go to the **Actions** tab and click **New...**. Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="bc2df-143">共有ファイルのファイル名と場所を  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd ファイルを入力* します。</span><span class="sxs-lookup"><span data-stu-id="bc2df-143">Enter the file name and location of the shared  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

12. <span data-ttu-id="bc2df-144">**[OK] を** クリックし、開いている GPMC ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="bc2df-144">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bc2df-145">オフボードにより、デバイスはポータルへのセンサー データの送信を停止しますが、デバイスからのデータは停止します。</span><span class="sxs-lookup"><span data-stu-id="bc2df-145">Offboarding causes the device to stop sending sensor data to the portal but data from the device.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="bc2df-146">デバイス構成の監視</span><span class="sxs-lookup"><span data-stu-id="bc2df-146">Monitor device configuration</span></span>
<span data-ttu-id="bc2df-147">グループ ポリシーでは、デバイス上のポリシーの展開を監視するオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="bc2df-147">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="bc2df-148">監視は、ポータルまたはさまざまな展開ツールを使用して直接実行できます。</span><span class="sxs-lookup"><span data-stu-id="bc2df-148">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="bc2df-149">ポータルを使用してデバイスを監視する</span><span class="sxs-lookup"><span data-stu-id="bc2df-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="bc2df-150">[Microsoft コンプライアンス [センター] に移動します](https://compliance.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="bc2df-150">Go to [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>
2. <span data-ttu-id="bc2df-151">[デバイス **一覧] を** クリックします。</span><span class="sxs-lookup"><span data-stu-id="bc2df-151">Click **Devices** list.</span></span>
3. <span data-ttu-id="bc2df-152">デバイスが表示されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="bc2df-152">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="bc2df-153">デバイスが [デバイス] リストに表示を開始するには、数日 **かかる場合があります**。</span><span class="sxs-lookup"><span data-stu-id="bc2df-153">It can take several days for devices to start showing on the **Devices list**.</span></span> <span data-ttu-id="bc2df-154">これには、ポリシーがデバイスに配布される時間、ユーザーがログオンする前にかかる時間、エンドポイントがレポートを開始するのにかかる時間が含まれます。</span><span class="sxs-lookup"><span data-stu-id="bc2df-154">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="bc2df-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc2df-155">Related topics</span></span>
- [<span data-ttu-id="bc2df-156">デバイスをWindows 10デバイスをオンボードMicrosoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="bc2df-156">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="bc2df-157">モバイル デバイス管理ツールを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="bc2df-157">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="bc2df-158">ローカル スクリプトを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="bc2df-158">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="bc2df-159">非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="bc2df-159">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="bc2df-160">新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する</span><span class="sxs-lookup"><span data-stu-id="bc2df-160">Run a detection test on a newly onboarded Microsoft Defender for Endpoint devices</span></span>](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="bc2df-161">オンボーディングMicrosoft Defender Advanced Threat Protectionのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="bc2df-161">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)