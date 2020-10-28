---
title: グループポリシーを使用した Windows 10 デバイスのオンボード
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
description: グループポリシーを使用して、サービスに利用されるように Windows 10 デバイスに構成パッケージを展開します。
ms.openlocfilehash: a9e91f41b6e86e9f75d79d420c0ee830f1e3acf3
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769447"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a><span data-ttu-id="bab29-103">グループポリシーを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="bab29-103">Onboard Windows 10 devices using Group Policy</span></span> 

<span data-ttu-id="bab29-104">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="bab29-104">**Applies to:**</span></span>

- [<span data-ttu-id="bab29-105">Microsoft 365 エンドポイントのデータ損失防止 (DLP)</span><span class="sxs-lookup"><span data-stu-id="bab29-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)
- <span data-ttu-id="bab29-106">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="bab29-106">Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="bab29-107">グループポリシー (GP) の更新プログラムを使用してパッケージを展開するには、Windows Server 2008 R2 以降のバージョンである必要があります。</span><span class="sxs-lookup"><span data-stu-id="bab29-107">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>

> <span data-ttu-id="bab29-108">Windows Server 2019 では、NT AUTHORITY\Well-Known-System-Account を、グループポリシー設定によって作成された XML ファイルの NT AUTHORITY\SYSTEM に置き換える必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="bab29-108">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="bab29-109">グループポリシーを使用しているオンボードデバイス</span><span class="sxs-lookup"><span data-stu-id="bab29-109">Onboard devices using Group Policy</span></span>

1. <span data-ttu-id="bab29-110">サービスオンボードウィザードからダウンロードした GP 構成パッケージ .zip ファイル ( *DeviceComplianceOnboardingPackage.zip* ) を開きます。</span><span class="sxs-lookup"><span data-stu-id="bab29-110">Open the GP configuration package .zip file ( *DeviceComplianceOnboardingPackage.zip* ) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="bab29-111">[Microsoft コンプライアンスセンター](https://compliance.microsoft.com/compliancesettings/deviceonboarding)からパッケージを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="bab29-111">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding)</span></span>

2. <span data-ttu-id="bab29-112">ナビゲーションウィンドウで、[ **設定** ] [  >  **デバイスのオンボード** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bab29-112">In the navigation pane, select **Settings** > **Device Onboarding** .</span></span>

3. <span data-ttu-id="bab29-113">[ **展開方法** ] フィールドで、[ **グループポリシー** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bab29-113">In the **Deployment method** field, select **Group policy** .</span></span>

4. <span data-ttu-id="bab29-114">[ **パッケージのダウンロード** ] をクリックし、.zip ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="bab29-114">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="bab29-115">.Zip ファイルの内容を、デバイスからアクセスできる共有の読み取り専用の場所に抽出します。</span><span class="sxs-lookup"><span data-stu-id="bab29-115">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="bab29-116">*OptionalParamsPolicy* という名前のフォルダーと、ファイル *Devicecompliofflocalonbookscript. cmd* が必要です。</span><span class="sxs-lookup"><span data-stu-id="bab29-116">You should have a folder called *OptionalParamsPolicy* and the file *DeviceComplianceLocalOnboardingScript.cmd* .</span></span>

6. <span data-ttu-id="bab29-117">[グループポリシー管理コンソール](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)(GPMC) を開き、構成するグループポリシーオブジェクト (GPO) を右クリックして、[ **編集** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bab29-117">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit** .</span></span>

7. <span data-ttu-id="bab29-118">**グループポリシー管理エディター** で、[コンピューターの **構成** ]、[ **環境** 設定]、[ **コントロールパネルの設定** ] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="bab29-118">In the **Group Policy Management Editor** , go to **Computer configuration** , then **Preferences** , and then **Control panel settings** .</span></span>

8. <span data-ttu-id="bab29-119">[ **タスク** ] を右クリックし、[ **新規** ] をポイントして、[ **即時タスク] (少なくとも Windows 7 以降)** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bab29-119">Right-click **Scheduled tasks** , point to **New** , and then click **Immediate Task (At least Windows 7)** .</span></span>

9. <span data-ttu-id="bab29-120">開いた **タスク** ウィンドウで、 **[全般** ] タブに移動します。[ **セキュリティオプション** ] で、[ **ユーザーまたはグループの変更** ] をクリックし、「SYSTEM」と入力して、[ **名前の確認** ] をクリックし、[ **OK]**</span><span class="sxs-lookup"><span data-stu-id="bab29-120">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK** .</span></span> <span data-ttu-id="bab29-121">[NT AUTHORITY\SYSTEM] は、タスクを実行するユーザーアカウントとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="bab29-121">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

10. <span data-ttu-id="bab29-122">[ **ユーザーがログオンしているかどうかにかかわらず実行する** ] を選択し、[ **最上位の特権で実行** する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="bab29-122">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

11. <span data-ttu-id="bab29-123">[ **操作** ] タブに移動し、[ **新規** ] をクリックします。[ **アクション** ] フィールドで [ **プログラムの開始** ] が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bab29-123">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="bab29-124">共有されている *WindowsDefenderATPOnboardingScript* ファイルのファイル名と場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="bab29-124">Enter the file name and location of the shared *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

12. <span data-ttu-id="bab29-125">[ **OK]** をクリックし、開いているすべての GPMC ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="bab29-125">Click **OK** and close any open GPMC windows.</span></span>


## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="bab29-126">グループポリシーを使用したオフボードデバイス</span><span class="sxs-lookup"><span data-stu-id="bab29-126">Offboard devices using Group Policy</span></span>
<span data-ttu-id="bab29-127">セキュリティ上の理由から、デバイスをオフにするために使用されるパッケージの有効期限は、ダウンロードされた日付から30日後になります。</span><span class="sxs-lookup"><span data-stu-id="bab29-127">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="bab29-128">有効期限切れのデバイスに送信されたオフボードパッケージは拒否されます。</span><span class="sxs-lookup"><span data-stu-id="bab29-128">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="bab29-129">オフボードパッケージをダウンロードすると、パッケージの有効期限日が通知され、パッケージ名にも含まれるようになります。</span><span class="sxs-lookup"><span data-stu-id="bab29-129">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="bab29-130">オンボードポリシーとオフボードポリシーを同じデバイスに同時に展開することはできません。そうしないと、予期しない競合が発生します。</span><span class="sxs-lookup"><span data-stu-id="bab29-130">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="bab29-131">[Microsoft コンプライアンスセンター](https://compliance.microsoft.com/compliancesettings/deviceonboarding)からオフボードパッケージを取得します。</span><span class="sxs-lookup"><span data-stu-id="bab29-131">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/compliancesettings/deviceonboarding).</span></span>

2. <span data-ttu-id="bab29-132">ナビゲーションウィンドウで、[ **設定** /デバイスのオンボードオフボード] を選択し  >  **//Device onboarding**  >  **Offboarding** ます。</span><span class="sxs-lookup"><span data-stu-id="bab29-132">In the navigation pane, select **Settings** > **//Device onboarding** > **Offboarding** .</span></span>

3. <span data-ttu-id="bab29-133">[ **展開方法** ] フィールドで、[ **グループポリシー** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bab29-133">In the **Deployment method** field, select **Group policy** .</span></span>

4. <span data-ttu-id="bab29-134">[ **パッケージのダウンロード** ] をクリックし、.zip ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="bab29-134">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="bab29-135">.Zip ファイルの内容を、デバイスからアクセスできる共有の読み取り専用の場所に抽出します。</span><span class="sxs-lookup"><span data-stu-id="bab29-135">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="bab29-136">*DeviceComplianceOffboardingScript_valid_until_YYYY* という名前のファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="bab29-136">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* .</span></span>

6. <span data-ttu-id="bab29-137">[グループポリシー管理コンソール](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)(GPMC) を開き、構成するグループポリシーオブジェクト (GPO) を右クリックして、[ **編集** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bab29-137">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit** .</span></span>

7. <span data-ttu-id="bab29-138">**グループポリシー管理エディター** で、[コンピューターの **構成]、** [ **環境** 設定]、[ **コントロールパネルの設定** ] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="bab29-138">In the **Group Policy Management Editor** , go to **Computer configuration,** then **Preferences** , and then **Control panel settings** .</span></span>

8. <span data-ttu-id="bab29-139">[ **タスク** ] を右クリックし、[ **新規** ] をポイントして、[ **即時タスク** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bab29-139">Right-click **Scheduled tasks** , point to **New** , and then click **Immediate task** .</span></span>

9. <span data-ttu-id="bab29-140">開いた **タスク** ウィンドウで、 **[全般** ] タブに移動します。[ **セキュリティオプション** ] で、[ローカルシステム] ユーザーアカウント (BUILTIN\SYSTEM) を選択します。</span><span class="sxs-lookup"><span data-stu-id="bab29-140">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options** .</span></span>

10. <span data-ttu-id="bab29-141">[ **ユーザーがログオンしているかどうかにかかわらず実行する** ] を選択し、[ **最上位の特権で実行** する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="bab29-141">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

11. <span data-ttu-id="bab29-142">[ **操作** ] タブに移動し、[ **新規** ] をクリックします。[ **アクション** ] フィールドで [ **プログラムの開始** ] が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bab29-142">Go to the **Actions** tab and click **New...** . Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="bab29-143">共有された  *DeviceComplianceOffboardingScript_valid_until_YYYY* のファイル名と場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="bab29-143">Enter the file name and location of the shared  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

12. <span data-ttu-id="bab29-144">[ **OK]** をクリックし、開いているすべての GPMC ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="bab29-144">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bab29-145">オフボードは、デバイスがポータルへのセンサーデータの送信を停止しますが、デバイスからデータを送信します。</span><span class="sxs-lookup"><span data-stu-id="bab29-145">Offboarding causes the device to stop sending sensor data to the portal but data from the device.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="bab29-146">デバイス構成の監視</span><span class="sxs-lookup"><span data-stu-id="bab29-146">Monitor device configuration</span></span>
<span data-ttu-id="bab29-147">グループポリシーを使用すると、デバイスにポリシーの展開を監視するオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="bab29-147">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="bab29-148">監視は、ポータル上で直接実行することも、さまざまな展開ツールを使用して行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="bab29-148">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="bab29-149">ポータルを使用してデバイスを監視する</span><span class="sxs-lookup"><span data-stu-id="bab29-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="bab29-150">[Microsoft コンプライアンスセンター](https://compliance.microsoft.com/)に移動します。</span><span class="sxs-lookup"><span data-stu-id="bab29-150">Go to [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>
2. <span data-ttu-id="bab29-151">[ **デバイス** リスト] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bab29-151">Click **Devices** list.</span></span>
3. <span data-ttu-id="bab29-152">デバイスが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bab29-152">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="bab29-153">デバイス **リスト** にデバイスが表示されるまでに数日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bab29-153">It can take several days for devices to start showing on the **Devices list** .</span></span> <span data-ttu-id="bab29-154">これには、ポリシーがデバイスに配布されるまでの時間、ユーザーがログオンするまでにかかる時間、およびエンドポイントがレポートを開始するのにかかる時間が含まれます。</span><span class="sxs-lookup"><span data-stu-id="bab29-154">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="bab29-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="bab29-155">Related topics</span></span>
- [<span data-ttu-id="bab29-156">Microsoft エンドポイント構成マネージャーを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="bab29-156">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="bab29-157">モバイルデバイス管理ツールを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="bab29-157">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="bab29-158">ローカルスクリプトを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="bab29-158">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="bab29-159">オンボードの非永続仮想デスクトップインフラストラクチャ (VDI) デバイス</span><span class="sxs-lookup"><span data-stu-id="bab29-159">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="bab29-160">新しく利用 Microsoft Defender ATP デバイスで検出テストを実行する</span><span class="sxs-lookup"><span data-stu-id="bab29-160">Run a detection test on a newly onboarded Microsoft Defender ATP devices</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="bab29-161">Microsoft Defender Advanced Threat Protection のオンボード問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="bab29-161">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
