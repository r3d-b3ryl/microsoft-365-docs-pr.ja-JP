---
title: Configuration Manager を使用した Windows 10 デバイスのオンボード
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Configuration Manager を使用してデバイスに構成パッケージを展開し、サービスにオンボードします。
ms.openlocfilehash: ac05581ce33e94859dbd67848197878595d5ed0f
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893298"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a><span data-ttu-id="76c00-103">Configuration Manager を使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="76c00-103">Onboard Windows 10 devices using Configuration Manager</span></span>

<span data-ttu-id="76c00-104">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="76c00-104">**Applies to:**</span></span>

- [<span data-ttu-id="76c00-105">Microsoft 365エンドポイント データ損失防止 (DLP)</span><span class="sxs-lookup"><span data-stu-id="76c00-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)
- <span data-ttu-id="76c00-106">System Center 2012 R2 構成マネージャー</span><span class="sxs-lookup"><span data-stu-id="76c00-106">System Center 2012 R2 Configuration Manager</span></span>

### <a name="onboard-devices-using-system-center-configuration-manager"></a><span data-ttu-id="76c00-107">デバイスを使用したオンボード System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="76c00-107">Onboard devices using System Center Configuration Manager</span></span>

1. <span data-ttu-id="76c00-108">サービス オンボーディング ウィザードからダウンロード *.zipファイル*(DeviceComplianceOnboardingPackage.zip) の Configuration Manager 構成パッケージを開きます。</span><span class="sxs-lookup"><span data-stu-id="76c00-108">Open the Configuration Manager configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="76c00-109">また、Microsoft コンプライアンス センターからパッケージ [を取得できます](https://compliance.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="76c00-109">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="76c00-110">ナビゲーション ウィンドウで、[デバイス オンボーディング オン **ボーディング] 設定**  >  **を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="76c00-110">In the navigation pane, select **Settings** > **Device Onboarding** > **Onboarding**.</span></span>

3. <span data-ttu-id="76c00-111">[展開 **方法] フィールド** で、[Microsoft Endpoint Configuration Manager **2012/2012 R2/1511/1602] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="76c00-111">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602**.</span></span>
 
4. <span data-ttu-id="76c00-112">[ **パッケージのダウンロード]** を選択し、ファイルを.zipします。</span><span class="sxs-lookup"><span data-stu-id="76c00-112">Select **Download package**, and save the .zip file.</span></span>

5. <span data-ttu-id="76c00-113">パッケージを展開するネットワーク管理者がアクセスできる共有の読み取り専用の場所に、.zip ファイルの内容を抽出します。</span><span class="sxs-lookup"><span data-stu-id="76c00-113">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="76c00-114">*DeviceComplianceOnboardingScript.cmd という名前のファイルが必要です*。</span><span class="sxs-lookup"><span data-stu-id="76c00-114">You should have a file named *DeviceComplianceOnboardingScript.cmd*.</span></span>

6. <span data-ttu-id="76c00-115">[2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10))の「パッケージとプログラム」の記事の手順に従ってSystem Centerパッケージを展開します。</span><span class="sxs-lookup"><span data-stu-id="76c00-115">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10)) article.</span></span>

7. <span data-ttu-id="76c00-116">パッケージを展開する定義済みのデバイス コレクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="76c00-116">Choose a predefined device collection to deploy the package to.</span></span>

> [!NOTE]
> <span data-ttu-id="76c00-117">Microsoft 365エンドポイントのデータ損失防止では、アウトオブボックス エクスペリエンス[(OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87)フェーズのオンボーディングはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="76c00-117">Microsoft 365 Endpoint data loss prevention doesn't support onboarding during the [Out-Of-Box Experience (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) phase.</span></span> <span data-ttu-id="76c00-118">インストールまたはアップグレードの実行後にユーザーが OOBE をWindows確認します。</span><span class="sxs-lookup"><span data-stu-id="76c00-118">Make sure users complete OOBE after running Windows installation or upgrading.</span></span>

>[!TIP]
> <span data-ttu-id="76c00-119">デバイスのオンボード後、検出テストを実行して、デバイスがサービスに適切にオンボードされていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="76c00-119">After onboarding the device, you can choose to run a detection test to verify that an device is properly onboarded to the service.</span></span> <span data-ttu-id="76c00-120">詳細については、「新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する [」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)。</span><span class="sxs-lookup"><span data-stu-id="76c00-120">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test).</span></span>
>
> <span data-ttu-id="76c00-121">Configuration Manager アプリケーションで検出ルールを作成して、デバイスがオンボードされた場合に継続的にチェックを行える点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="76c00-121">Note that it is possible to create a detection rule on a Configuration Manager application to continuously check if a device has been onboarded.</span></span> <span data-ttu-id="76c00-122">アプリケーションは、パッケージやプログラムとは異なる種類のオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="76c00-122">An application is a different type of object than a package and program.</span></span>
> <span data-ttu-id="76c00-123">デバイスがまだオンボードされていない場合 (保留中の OOBE の完了その他の理由により)、Configuration Manager は、ルールが状態の変更を検出するまで、デバイスのオンボードを再試行します。</span><span class="sxs-lookup"><span data-stu-id="76c00-123">If a device is not yet onboarded (due to pending OOBE completion or any other reason), Configuration Manager will retry to onboard the device until the rule detects the status change.</span></span>
> 
> <span data-ttu-id="76c00-124">この動作は、"OnboardingState" レジストリ値 (タイプ REG_DWORD) が 1 の場合に検出ルールチェックを作成することで実現できます。</span><span class="sxs-lookup"><span data-stu-id="76c00-124">This behavior can be accomplished by creating a detection rule checking if the "OnboardingState" registry value (of type REG_DWORD) = 1.</span></span>
> <span data-ttu-id="76c00-125">このレジストリ値は、"HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status" の下にあります。</span><span class="sxs-lookup"><span data-stu-id="76c00-125">This registry value is located under "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span></span>
<span data-ttu-id="76c00-126">詳細については[、「Configure Detection Methods in System Center 2012 R2 Configuration Manager」を参照してください](/previous-versions/system-center/system-center-2012-R2/gg682159(v=technet.10)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)。</span><span class="sxs-lookup"><span data-stu-id="76c00-126">For more information, see [Configure Detection Methods in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682159(v=technet.10)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="76c00-127">サンプル コレクション設定の構成</span><span class="sxs-lookup"><span data-stu-id="76c00-127">Configure sample collection settings</span></span>

<span data-ttu-id="76c00-128">デバイスごとに構成値を設定して、Microsoft Defender セキュリティ センター から詳細分析用にファイルを送信する要求が行われたときに、デバイスからサンプルを収集できるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="76c00-128">For each device, you can set a configuration value to state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

>[!NOTE]
><span data-ttu-id="76c00-129">これらの構成設定は、通常、Configuration Manager を介して行われます。</span><span class="sxs-lookup"><span data-stu-id="76c00-129">These configuration settings are typically done through Configuration Manager.</span></span> 

<span data-ttu-id="76c00-130">Configuration Manager で構成アイテムのコンプライアンス ルールを設定して、デバイスのサンプル共有設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="76c00-130">You can set a compliance rule for configuration item in Configuration Manager to change the sample share setting on a device.</span></span>

<span data-ttu-id="76c00-131">このルールは、対象デバイスのレジストリ キーの値を設定して、苦情を確実に受け取るコンプライアンス ルール構成項目を修復する必要があります。</span><span class="sxs-lookup"><span data-stu-id="76c00-131">This rule should be a *remediating* compliance rule configuration item that sets the value of a registry key on targeted devices to make sure they’re complaint.</span></span>

<span data-ttu-id="76c00-132">構成は、次のレジストリ キー エントリを使用して設定されます。</span><span class="sxs-lookup"><span data-stu-id="76c00-132">The configuration is set through the following registry key entry:</span></span>

```
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
<span data-ttu-id="76c00-133">ここで、</span><span class="sxs-lookup"><span data-stu-id="76c00-133">Where:</span></span><br>
<span data-ttu-id="76c00-134">キーの種類は D-WORD です。</span><span class="sxs-lookup"><span data-stu-id="76c00-134">Key type is a D-WORD.</span></span> <br>
<span data-ttu-id="76c00-135">使用可能な値は次のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="76c00-135">Possible values are:</span></span>
- <span data-ttu-id="76c00-136">0 - このデバイスからのサンプル共有を許可しない</span><span class="sxs-lookup"><span data-stu-id="76c00-136">0 - doesn't allow sample sharing  from this device</span></span>
- <span data-ttu-id="76c00-137">1 - このデバイスからすべての種類のファイルを共有できます</span><span class="sxs-lookup"><span data-stu-id="76c00-137">1 - allows sharing of all file types from this device</span></span>

<span data-ttu-id="76c00-138">レジストリ キーが存在しない場合の既定値は 1 です。</span><span class="sxs-lookup"><span data-stu-id="76c00-138">The default value in case the registry key doesn’t exist is 1.</span></span>

<span data-ttu-id="76c00-139">コンプライアンスの詳細については、「System Center Configuration Manager [System Center 2012 R2](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10))Configuration Manager のコンプライアンス設定の概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76c00-139">For more information about System Center Configuration Manager Compliance, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10)).</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="76c00-140">その他の推奨構成設定</span><span class="sxs-lookup"><span data-stu-id="76c00-140">Other recommended configuration settings</span></span>
<span data-ttu-id="76c00-141">デバイスをサービスにオンボーディングした後、以下の推奨構成設定でデバイスを有効にすることで、含まれている脅威保護機能を活用することが重要です。</span><span class="sxs-lookup"><span data-stu-id="76c00-141">After onboarding devices to the service, it's important to take advantage of the included threat protection capabilities by enabling them with the following recommended configuration settings.</span></span>

### <a name="device-collection-configuration"></a><span data-ttu-id="76c00-142">デバイス コレクションの構成</span><span class="sxs-lookup"><span data-stu-id="76c00-142">Device collection configuration</span></span>
<span data-ttu-id="76c00-143">バージョン 2002 以降のエンドポイント構成マネージャーを使用している場合は、展開を拡大してサーバーまたはダウンレベルのクライアントを含める方法を選択できます。</span><span class="sxs-lookup"><span data-stu-id="76c00-143">If you're using Endpoint Configuration Manager, version 2002 or later, you can choose to broaden the deployment to include servers or down-level clients.</span></span>


### <a name="next-generation-protection-configuration"></a><span data-ttu-id="76c00-144">次世代の保護構成</span><span class="sxs-lookup"><span data-stu-id="76c00-144">Next generation protection configuration</span></span>

<span data-ttu-id="76c00-145">次の構成設定をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="76c00-145">The following configuration settings are recommended:</span></span>

<span data-ttu-id="76c00-146">**スキャン**</span><span class="sxs-lookup"><span data-stu-id="76c00-146">**Scan**</span></span>

- <span data-ttu-id="76c00-147">USB ドライブなどのリムーバブル 記憶域デバイスをスキャンする: はい</span><span class="sxs-lookup"><span data-stu-id="76c00-147">Scan removable storage devices such as USB drives: Yes</span></span>

<span data-ttu-id="76c00-148">**リアルタイム保護**</span><span class="sxs-lookup"><span data-stu-id="76c00-148">**Real-time Protection**</span></span>

- <span data-ttu-id="76c00-149">動作監視を有効にする: はい</span><span class="sxs-lookup"><span data-stu-id="76c00-149">Enable Behavioral Monitoring: Yes</span></span>
- <span data-ttu-id="76c00-150">ダウンロード時およびインストール前に望ましくない可能性があるアプリケーションに対する保護を有効にする: はい</span><span class="sxs-lookup"><span data-stu-id="76c00-150">Enable protection against Potentially Unwanted Applications at download and prior to installation: Yes</span></span>

<span data-ttu-id="76c00-151">**クラウド保護サービス**</span><span class="sxs-lookup"><span data-stu-id="76c00-151">**Cloud Protection Service**</span></span>

- <span data-ttu-id="76c00-152">Cloud Protection Service メンバーシップの種類: 高度なメンバーシップ</span><span class="sxs-lookup"><span data-stu-id="76c00-152">Cloud Protection Service membership type: Advanced membership</span></span>

<span data-ttu-id="76c00-153">**攻撃表面の縮小** 使用可能なすべてのルールを [監査] に構成します。</span><span class="sxs-lookup"><span data-stu-id="76c00-153">**Attack surface reduction** Configure all available rules to Audit.</span></span>

>[!NOTE]
> <span data-ttu-id="76c00-154">これらのアクティビティをブロックすると、正当なビジネス プロセスが中断される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="76c00-154">Blocking these activities may interrupt legitimate business processes.</span></span> <span data-ttu-id="76c00-155">最善の方法は、すべてを監査に設定し、有効にしても安全な設定を特定し、誤検知検出を持つエンドポイントでこれらの設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="76c00-155">The best approach is setting everything to audit, identifying which ones are safe to turn on, and then enabling those settings on endpoints which do not have false positive detections.</span></span>

<span data-ttu-id="76c00-156">**ネットワーク保護**</span><span class="sxs-lookup"><span data-stu-id="76c00-156">**Network protection**</span></span>

<span data-ttu-id="76c00-157">監査モードまたはブロック モードでネットワーク保護を有効にする前に、サポート ページから入手できるマルウェア対策プラットフォーム更新プログラムがインストール [されていることを確認してください](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)。</span><span class="sxs-lookup"><span data-stu-id="76c00-157">Prior to enabling network protection in audit or block mode, ensure that you've installed the antimalware platform update, which can be obtained from the [support page](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).</span></span>


<span data-ttu-id="76c00-158">**制御されたフォルダー アクセス**</span><span class="sxs-lookup"><span data-stu-id="76c00-158">**Controlled folder access**</span></span>

<span data-ttu-id="76c00-159">監査モードで機能を 30 日以上有効にします。</span><span class="sxs-lookup"><span data-stu-id="76c00-159">Enable the feature in audit mode for at least 30 days.</span></span> <span data-ttu-id="76c00-160">この期間が終了した後、検出を確認し、保護されたディレクトリへの書き込みを許可するアプリケーションの一覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="76c00-160">After this period, review detections and create a list of applications that are allowed to write to protected directories.</span></span>

<span data-ttu-id="76c00-161">詳細については、「管理フォルダー アクセス [の評価」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access)。</span><span class="sxs-lookup"><span data-stu-id="76c00-161">For more information, see [Evaluate controlled folder access](/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access).</span></span>


## <a name="offboard-devices-using-configuration-manager"></a><span data-ttu-id="76c00-162">Configuration Manager を使用したオフボード デバイス</span><span class="sxs-lookup"><span data-stu-id="76c00-162">Offboard devices using Configuration Manager</span></span>

<span data-ttu-id="76c00-163">セキュリティ上の理由から、Offboard デバイスに使用されるパッケージは、ダウンロード日から 30 日後に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="76c00-163">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="76c00-164">デバイスに送信された期限切れのオフボード パッケージは拒否されます。</span><span class="sxs-lookup"><span data-stu-id="76c00-164">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="76c00-165">オフボード パッケージをダウンロードすると、パッケージの有効期限が通知され、パッケージ名にも含まれます。</span><span class="sxs-lookup"><span data-stu-id="76c00-165">When downloading an offboarding package, you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="76c00-166">オンボーディングポリシーとオフボード ポリシーを同じデバイスに同時に展開し、それ以外の場合は予期しない競合を引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="76c00-166">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a><span data-ttu-id="76c00-167">現在のブランチを使用Microsoft Endpoint Configuration Managerオフボード デバイス</span><span class="sxs-lookup"><span data-stu-id="76c00-167">Offboard devices using Microsoft Endpoint Configuration Manager current branch</span></span>

<span data-ttu-id="76c00-168">現在のブランチでMicrosoft Endpoint Configuration Manager場合は、「[オフボード構成ファイルを作成する」を参照してください](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)。</span><span class="sxs-lookup"><span data-stu-id="76c00-168">If you use Microsoft Endpoint Configuration Manager current branch, see [Create an offboarding configuration file](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).</span></span>

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a><span data-ttu-id="76c00-169">2012 R2 Configuration Manager System Centerを使用するオフボード デバイス</span><span class="sxs-lookup"><span data-stu-id="76c00-169">Offboard devices using System Center 2012 R2 Configuration Manager</span></span>

1. <span data-ttu-id="76c00-170">Microsoft コンプライアンス センターからオフボード パッケージ [を取得します](https://compliance.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="76c00-170">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/):</span></span>

2. <span data-ttu-id="76c00-171">ナビゲーション ウィンドウで、[デバイスオンボーディング **設定**  >   **オフボード]** >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="76c00-171">In the navigation pane, select **Settings** >  **Device onboarding**> **Offboarding**.</span></span>

3. <span data-ttu-id="76c00-172">オペレーティング システムWindows 10を選択します。</span><span class="sxs-lookup"><span data-stu-id="76c00-172">Select Windows 10 as the operating system.</span></span>

4. <span data-ttu-id="76c00-173">[展開 **方法] フィールド** で、[Microsoft Endpoint Configuration Manager **2012/2012 R2/1511/1602] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="76c00-173">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602**.</span></span>
    
5. <span data-ttu-id="76c00-174">[ **パッケージのダウンロード]** を選択し、ファイルを.zipします。</span><span class="sxs-lookup"><span data-stu-id="76c00-174">Select **Download package**, and save the .zip file.</span></span>

6. <span data-ttu-id="76c00-175">パッケージを展開するネットワーク管理者がアクセスできる共有の読み取り専用の場所に、.zip ファイルの内容を抽出します。</span><span class="sxs-lookup"><span data-stu-id="76c00-175">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="76c00-176">*-MM-DD.cmd DeviceComplianceOffboardingScript_valid_until_YYYYという名前のファイルが必要です*。</span><span class="sxs-lookup"><span data-stu-id="76c00-176">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

7. <span data-ttu-id="76c00-177">[2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10))の「パッケージとプログラム」の記事の手順に従ってSystem Centerパッケージを展開します。</span><span class="sxs-lookup"><span data-stu-id="76c00-177">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10)) article.</span></span>

8. <span data-ttu-id="76c00-178">パッケージを展開する定義済みのデバイス コレクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="76c00-178">Choose a predefined device collection to deploy the package to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="76c00-179">Offboarding を使用すると、デバイスはポータルへのセンサー データの送信を停止しますが、デバイスからのデータ (通知への参照を含む) は最大 6 か月間保持されます。</span><span class="sxs-lookup"><span data-stu-id="76c00-179">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="76c00-180">デバイス構成の監視</span><span class="sxs-lookup"><span data-stu-id="76c00-180">Monitor device configuration</span></span>

<span data-ttu-id="76c00-181">現在のブランチでMicrosoft Endpoint Configuration Manager場合は、Configuration Manager コンソールの組み込みの Microsoft Defender for Endpoint ダッシュボードを使用します。</span><span class="sxs-lookup"><span data-stu-id="76c00-181">If you're using Microsoft Endpoint Configuration Manager current branch, use the built-in Microsoft Defender for Endpoint dashboard in the Configuration Manager console.</span></span> <span data-ttu-id="76c00-182">詳細については、「Microsoft Defender Advanced Threat Protection [- モニター」を参照してください](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)。</span><span class="sxs-lookup"><span data-stu-id="76c00-182">For more information, see [Microsoft Defender Advanced Threat Protection - Monitor](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).</span></span>

<span data-ttu-id="76c00-183">2012 R2 Configuration Manager System Center使用している場合、監視は次の 2 つの部分で構成されます。</span><span class="sxs-lookup"><span data-stu-id="76c00-183">If you're using System Center 2012 R2 Configuration Manager, monitoring consists of two parts:</span></span>

1. <span data-ttu-id="76c00-184">構成パッケージが正しく展開され、ネットワーク内のデバイスで実行 (または正常に実行) されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="76c00-184">Confirming the configuration package has been correctly deployed and is running (or has successfully run) on the devices in your network.</span></span>

2. <span data-ttu-id="76c00-185">デバイスが Microsoft 365 Endpoint データ損失防止サービスに準拠しているのを確認します (これにより、デバイスはオンボーディング プロセスを完了し、引き続きサービスにデータを報告できます)。</span><span class="sxs-lookup"><span data-stu-id="76c00-185">Checking that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service (this ensures the device can complete the onboarding process and can continue to report data to the service).</span></span>

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a><span data-ttu-id="76c00-186">構成パッケージが正しく展開されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="76c00-186">Confirm the configuration package has been correctly deployed</span></span>

1. <span data-ttu-id="76c00-187">Configuration Manager コンソールで、ナビゲーション ウィンドウ **の** 下部にある [監視] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76c00-187">In the Configuration Manager console, click **Monitoring** at the bottom of the navigation pane.</span></span>

2. <span data-ttu-id="76c00-188">[概要 **] を選択** し、[ **展開] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="76c00-188">Select **Overview** and then **Deployments**.</span></span>

3. <span data-ttu-id="76c00-189">パッケージ名を使用して展開を選択します。</span><span class="sxs-lookup"><span data-stu-id="76c00-189">Select on the deployment with the package name.</span></span>

4. <span data-ttu-id="76c00-190">[完了統計] と [コンテンツ **の状態] の下の** 状態インジケーター **を確認します**。</span><span class="sxs-lookup"><span data-stu-id="76c00-190">Review the status indicators under **Completion Statistics** and **Content Status**.</span></span>

    <span data-ttu-id="76c00-191">失敗した展開 (エラー、要件が満たされていないデバイス、または失敗した状態) がある場合は、デバイスのトラブルシューティングが必要な場合があります。 </span><span class="sxs-lookup"><span data-stu-id="76c00-191">If there are failed deployments (devices with **Error**, **Requirements Not Met**, or **Failed statuses**), you may need to  troubleshoot the devices.</span></span> <span data-ttu-id="76c00-192">詳細については、「オンボードの問題に[関するトラブルシューティングMicrosoft Defender Advanced Threat Protection」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)。</span><span class="sxs-lookup"><span data-stu-id="76c00-192">For more information, see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

    ![エラーがない展開が正常に実行されたことを示す Configuration Manager](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-365-endpoint-data-loss-prevention-service"></a><span data-ttu-id="76c00-194">デバイスがエンドポイント データ損失防止サービスMicrosoft 365準拠しているを確認する</span><span class="sxs-lookup"><span data-stu-id="76c00-194">Check that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service</span></span>

<span data-ttu-id="76c00-195">2012 R2 Configuration Manager で構成アイテムのコンプライアンス System Center設定して、展開を監視できます。</span><span class="sxs-lookup"><span data-stu-id="76c00-195">You can set a compliance rule for configuration item in System Center 2012 R2 Configuration Manager to monitor your deployment.</span></span>

> [!NOTE]
> <span data-ttu-id="76c00-196">この手順とレジストリ エントリは、エンドポイント DLP および Advanced Threat Protection に適用されます。</span><span class="sxs-lookup"><span data-stu-id="76c00-196">This procedure and registry entry applies to Endpoint DLP as well as Advanced Threat Protection.</span></span>

<span data-ttu-id="76c00-197">このルールは *、対象となる* デバイスのレジストリ キーの値を監視する、修復されていないコンプライアンス ルール構成アイテムである必要があります。</span><span class="sxs-lookup"><span data-stu-id="76c00-197">This rule should be a *non-remediating* compliance rule configuration item that monitors the value of a registry key on targeted devices.</span></span>

<span data-ttu-id="76c00-198">次のレジストリ キー エントリを監視します。</span><span class="sxs-lookup"><span data-stu-id="76c00-198">Monitor the following registry key entry:</span></span>
```
Path: “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status”
Name: “OnboardingState”
Value: “1”
```
<span data-ttu-id="76c00-199">詳細については[、「2012 R2](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10))Configuration Manager のコンプライアンスSystem Center概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76c00-199">For more information, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10)).</span></span>

## <a name="related-topics"></a><span data-ttu-id="76c00-200">関連項目</span><span class="sxs-lookup"><span data-stu-id="76c00-200">Related topics</span></span>
- [<span data-ttu-id="76c00-201">グループ ポリシー Windows 10デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="76c00-201">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="76c00-202">モバイル デバイス管理ツールを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="76c00-202">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="76c00-203">ローカル スクリプトを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="76c00-203">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="76c00-204">非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="76c00-204">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="76c00-205">新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する</span><span class="sxs-lookup"><span data-stu-id="76c00-205">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="76c00-206">オンボーディングMicrosoft Defender Advanced Threat Protectionのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="76c00-206">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)