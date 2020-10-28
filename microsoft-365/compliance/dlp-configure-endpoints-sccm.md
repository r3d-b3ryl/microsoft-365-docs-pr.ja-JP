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
description: 構成マネージャーを使用して、サービスに利用するように構成パッケージをデバイスに展開します。
ms.openlocfilehash: ea1b0cba10dc3e7120192e0c0ee87e2e354f1cc2
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769477"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a><span data-ttu-id="ab146-103">Configuration Manager を使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="ab146-103">Onboard Windows 10 devices using Configuration Manager</span></span>

<span data-ttu-id="ab146-104">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ab146-104">**Applies to:**</span></span>

- [<span data-ttu-id="ab146-105">Microsoft 365 エンドポイントのデータ損失防止 (DLP)</span><span class="sxs-lookup"><span data-stu-id="ab146-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)
- <span data-ttu-id="ab146-106">System Center 2012 R2 構成マネージャー</span><span class="sxs-lookup"><span data-stu-id="ab146-106">System Center 2012 R2 Configuration Manager</span></span>

### <a name="onboard-devices-using-system-center-configuration-manager"></a><span data-ttu-id="ab146-107">System Center Configuration Manager を使用しているオンボードデバイス</span><span class="sxs-lookup"><span data-stu-id="ab146-107">Onboard devices using System Center Configuration Manager</span></span>

1. <span data-ttu-id="ab146-108">サービスオンボードウィザードからダウンロードした Configuration Manager 構成パッケージ .zip ファイル ( *DeviceComplianceOnboardingPackage.zip* ) を開きます。</span><span class="sxs-lookup"><span data-stu-id="ab146-108">Open the Configuration Manager configuration package .zip file ( *DeviceComplianceOnboardingPackage.zip* ) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="ab146-109">[Microsoft コンプライアンスセンター](https://compliance.microsoft.com/)からパッケージを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="ab146-109">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="ab146-110">ナビゲーションウィンドウで、[ **設定** ] [  >  **デバイスのオン** ボードオンボード] を選択し  >  **Onboarding** ます。</span><span class="sxs-lookup"><span data-stu-id="ab146-110">In the navigation pane, select **Settings** > **Device Onboarding** > **Onboarding** .</span></span>

3. <span data-ttu-id="ab146-111">[ **展開方法** ] フィールドで、[ **Microsoft エンドポイント構成マネージャー 2012/2012 R2/1511/1602** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ab146-111">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** .</span></span>
 
4. <span data-ttu-id="ab146-112">[ **パッケージのダウンロード** ] を選択し、.zip ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="ab146-112">Select **Download package** , and save the .zip file.</span></span>

5. <span data-ttu-id="ab146-113">.Zip ファイルの内容を、パッケージを展開するネットワーク管理者がアクセスできる共有の読み取り専用の場所に展開します。</span><span class="sxs-lookup"><span data-stu-id="ab146-113">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="ab146-114">*Devicecompli/Onbookingscript* という名前のファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="ab146-114">You should have a file named *DeviceComplianceOnboardingScript.cmd* .</span></span>

6. <span data-ttu-id="ab146-115">[System Center 2012 R2 Configuration Manager 記事の「パッケージとプログラム](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))」に記載されている手順に従って、パッケージを展開します。</span><span class="sxs-lookup"><span data-stu-id="ab146-115">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) article.</span></span>

7. <span data-ttu-id="ab146-116">パッケージを展開する定義済みのデバイスコレクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="ab146-116">Choose a predefined device collection to deploy the package to.</span></span>

> [!NOTE]
> <span data-ttu-id="ab146-117">Microsoft 365 エンドポイントのデータ損失防止は、 [標準の状態 (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) フェーズでのオンボードをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="ab146-117">Microsoft 365 Endpoint data loss prevention doesn't support onboarding during the [Out-Of-Box Experience (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) phase.</span></span> <span data-ttu-id="ab146-118">Windows のインストールまたはアップグレードを実行した後、ユーザーが OOBE を完了していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ab146-118">Make sure users complete OOBE after running Windows installation or upgrading.</span></span>

>[!TIP]
> <span data-ttu-id="ab146-119">デバイスをオンにした後、検出テストを実行して、デバイスがサービスに適切に利用ていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="ab146-119">After onboarding the device, you can choose to run a detection test to verify that an device is properly onboarded to the service.</span></span> <span data-ttu-id="ab146-120">詳細については、「 [新規利用 Microsoft DEFENDER ATP デバイスで検出テストを実行](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab146-120">For more information, see [Run a detection test on a newly onboarded Microsoft Defender ATP device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test).</span></span>
>
> <span data-ttu-id="ab146-121">構成マネージャーアプリケーションで検出ルールを作成して、デバイスが利用されているかどうかを継続的にチェックすることができます。</span><span class="sxs-lookup"><span data-stu-id="ab146-121">Note that it is possible to create a detection rule on a Configuration Manager application to continuously check if a device has been onboarded.</span></span> <span data-ttu-id="ab146-122">アプリケーションは、パッケージとプログラムとは別の種類のオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="ab146-122">An application is a different type of object than a package and program.</span></span>
> <span data-ttu-id="ab146-123">デバイスがまだ利用 (保留中の OOBE の完了またはその他の理由により) になっていない場合、構成マネージャーは、ルールによって状態の変更が検出されるまでデバイスの onboard を再試行します。</span><span class="sxs-lookup"><span data-stu-id="ab146-123">If a device is not yet onboarded (due to pending OOBE completion or any other reason), Configuration Manager will retry to onboard the device until the rule detects the status change.</span></span>
> 
> <span data-ttu-id="ab146-124">この動作は、"OnboardingState" レジストリ値 (型 REG_DWORD) が1であるかどうかを検出する検出ルールを作成することによって実現できます。</span><span class="sxs-lookup"><span data-stu-id="ab146-124">This behavior can be accomplished by creating a detection rule checking if the "OnboardingState" registry value (of type REG_DWORD) = 1.</span></span>
> <span data-ttu-id="ab146-125">このレジストリ値は、"HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\ 状態" の下にあります。</span><span class="sxs-lookup"><span data-stu-id="ab146-125">This registry value is located under "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span></span>
<span data-ttu-id="ab146-126">詳細については、「 [System Center 2012 R2 構成マネージャーでの検出方法の構成](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab146-126">For more information, see [Configure Detection Methods in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="ab146-127">サンプルコレクションの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="ab146-127">Configure sample collection settings</span></span>

<span data-ttu-id="ab146-128">デバイスごとに、Microsoft Defender セキュリティセンターから要求が行われたときにデバイスからサンプルを収集して、詳細な分析のためにファイルを送信できるかどうかを示す構成値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="ab146-128">For each device, you can set a configuration value to state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

>[!NOTE]
><span data-ttu-id="ab146-129">これらの構成設定は、通常、Configuration Manager によって実行されます。</span><span class="sxs-lookup"><span data-stu-id="ab146-129">These configuration settings are typically done through Configuration Manager.</span></span> 

<span data-ttu-id="ab146-130">構成マネージャーの構成項目のコンプライアンス規則を設定して、デバイスの共有設定のサンプルを変更できます。</span><span class="sxs-lookup"><span data-stu-id="ab146-130">You can set a compliance rule for configuration item in Configuration Manager to change the sample share setting on a device.</span></span>

<span data-ttu-id="ab146-131">このルールは、対象デバイス上のレジストリキーの値を設定して、苦情があることを確認する *修復* コンプライアンスルール構成アイテムである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab146-131">This rule should be a *remediating* compliance rule configuration item that sets the value of a registry key on targeted devices to make sure they’re complaint.</span></span>

<span data-ttu-id="ab146-132">構成は、次のレジストリキーエントリで設定されます。</span><span class="sxs-lookup"><span data-stu-id="ab146-132">The configuration is set through the following registry key entry:</span></span>

```
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
<span data-ttu-id="ab146-133">ここで、</span><span class="sxs-lookup"><span data-stu-id="ab146-133">Where:</span></span><br>
<span data-ttu-id="ab146-134">キーの種類は D 語です。</span><span class="sxs-lookup"><span data-stu-id="ab146-134">Key type is a D-WORD.</span></span> <br>
<span data-ttu-id="ab146-135">使用可能な値は次のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="ab146-135">Possible values are:</span></span>
- <span data-ttu-id="ab146-136">0-このデバイスからのサンプルの共有を許可しません。</span><span class="sxs-lookup"><span data-stu-id="ab146-136">0 - doesn't allow sample sharing  from this device</span></span>
- <span data-ttu-id="ab146-137">1-このデバイスからのすべてのファイルの種類の共有を許可します。</span><span class="sxs-lookup"><span data-stu-id="ab146-137">1 - allows sharing of all file types from this device</span></span>

<span data-ttu-id="ab146-138">レジストリキーが存在しない場合の既定値は1です。</span><span class="sxs-lookup"><span data-stu-id="ab146-138">The default value in case the registry key doesn’t exist is 1.</span></span>

<span data-ttu-id="ab146-139">System Center Configuration Manager の準拠の詳細については、「 [System center 2012 R2 構成マネージャーのコンプライアンス設定に](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))ついて」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab146-139">For more information about System Center Configuration Manager Compliance, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="ab146-140">その他の推奨構成設定</span><span class="sxs-lookup"><span data-stu-id="ab146-140">Other recommended configuration settings</span></span>
<span data-ttu-id="ab146-141">サービスにデバイスを移動した後は、次の推奨構成設定でそれらを有効にすることによって、含まれている脅威保護機能を活用することが重要です。</span><span class="sxs-lookup"><span data-stu-id="ab146-141">After onboarding devices to the service, it's important to take advantage of the included threat protection capabilities by enabling them with the following recommended configuration settings.</span></span>

### <a name="device-collection-configuration"></a><span data-ttu-id="ab146-142">デバイスコレクションの構成</span><span class="sxs-lookup"><span data-stu-id="ab146-142">Device collection configuration</span></span>
<span data-ttu-id="ab146-143">エンドポイント構成マネージャー (バージョン2002以降) を使用している場合は、サーバーまたはダウンレベルクライアントを含めるように展開を広げることができます。</span><span class="sxs-lookup"><span data-stu-id="ab146-143">If you're using Endpoint Configuration Manager, version 2002 or later, you can choose to broaden the deployment to include servers or down-level clients.</span></span>


### <a name="next-generation-protection-configuration"></a><span data-ttu-id="ab146-144">次世代の保護構成</span><span class="sxs-lookup"><span data-stu-id="ab146-144">Next generation protection configuration</span></span>

<span data-ttu-id="ab146-145">次の構成設定をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ab146-145">The following configuration settings are recommended:</span></span>

<span data-ttu-id="ab146-146">**スキャン**</span><span class="sxs-lookup"><span data-stu-id="ab146-146">**Scan**</span></span>

- <span data-ttu-id="ab146-147">リムーバブル記憶域デバイス (USB ドライブなど) をスキャンする: はい</span><span class="sxs-lookup"><span data-stu-id="ab146-147">Scan removable storage devices such as USB drives: Yes</span></span>

<span data-ttu-id="ab146-148">**リアルタイム保護**</span><span class="sxs-lookup"><span data-stu-id="ab146-148">**Real-time Protection**</span></span>

- <span data-ttu-id="ab146-149">動作監視を有効にする: はい</span><span class="sxs-lookup"><span data-stu-id="ab146-149">Enable Behavioral Monitoring: Yes</span></span>
- <span data-ttu-id="ab146-150">ダウンロード時およびインストール前に、望ましくない可能性があるアプリケーションに対する保護を有効にする: はい</span><span class="sxs-lookup"><span data-stu-id="ab146-150">Enable protection against Potentially Unwanted Applications at download and prior to installation: Yes</span></span>

<span data-ttu-id="ab146-151">**クラウド保護サービス**</span><span class="sxs-lookup"><span data-stu-id="ab146-151">**Cloud Protection Service**</span></span>

- <span data-ttu-id="ab146-152">クラウド保護サービスのメンバーシップの種類: 上級メンバーシップ</span><span class="sxs-lookup"><span data-stu-id="ab146-152">Cloud Protection Service membership type: Advanced membership</span></span>

<span data-ttu-id="ab146-153">**攻撃対象領域の削減** 利用可能なすべてのルールを監査に構成します。</span><span class="sxs-lookup"><span data-stu-id="ab146-153">**Attack surface reduction** Configure all available rules to Audit.</span></span>

>[!NOTE]
> <span data-ttu-id="ab146-154">これらのアクティビティをブロックすると、正当なビジネスプロセスが中断することがあります。</span><span class="sxs-lookup"><span data-stu-id="ab146-154">Blocking these activities may interrupt legitimate business processes.</span></span> <span data-ttu-id="ab146-155">最善の方法は、監査対象をすべて設定し、有効にすることが安全なエンドポイントを特定し、誤検知が誤検知されないエンドポイントでそれらの設定を有効にすることです。</span><span class="sxs-lookup"><span data-stu-id="ab146-155">The best approach is setting everything to audit, identifying which ones are safe to turn on, and then enabling those settings on endpoints which do not have false positive detections.</span></span>

<span data-ttu-id="ab146-156">**ネットワーク保護**</span><span class="sxs-lookup"><span data-stu-id="ab146-156">**Network protection**</span></span>

<span data-ttu-id="ab146-157">監査モードまたはブロックモードでネットワーク保護を有効にする前に、「 [サポート」ページ](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)から入手できる、マルウェア対策プラットフォームの更新プログラムがインストールされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ab146-157">Prior to enabling network protection in audit or block mode, ensure that you've installed the antimalware platform update, which can be obtained from the [support page](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).</span></span>


<span data-ttu-id="ab146-158">**フォルダーアクセスの制御**</span><span class="sxs-lookup"><span data-stu-id="ab146-158">**Controlled folder access**</span></span>

<span data-ttu-id="ab146-159">少なくとも30日間は、この機能を監査モードで有効にします。</span><span class="sxs-lookup"><span data-stu-id="ab146-159">Enable the feature in audit mode for at least 30 days.</span></span> <span data-ttu-id="ab146-160">この期間が経過したら、検出を確認し、保護されたディレクトリへの書き込みが許可されているアプリケーションの一覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="ab146-160">After this period, review detections and create a list of applications that are allowed to write to protected directories.</span></span>

<span data-ttu-id="ab146-161">詳細については、「制御された [フォルダーアクセスを評価](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab146-161">For more information, see [Evaluate controlled folder access](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access).</span></span>


## <a name="offboard-devices-using-configuration-manager"></a><span data-ttu-id="ab146-162">構成マネージャーを使用した offboard デバイス</span><span class="sxs-lookup"><span data-stu-id="ab146-162">Offboard devices using Configuration Manager</span></span>

<span data-ttu-id="ab146-163">セキュリティ上の理由から、デバイスをオフにするために使用されるパッケージの有効期限は、ダウンロードされた日付から30日後になります。</span><span class="sxs-lookup"><span data-stu-id="ab146-163">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="ab146-164">有効期限切れのデバイスに送信されたオフボードパッケージは拒否されます。</span><span class="sxs-lookup"><span data-stu-id="ab146-164">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="ab146-165">オフボードパッケージをダウンロードすると、パッケージの有効期限日が通知され、パッケージ名にも含まれるようになります。</span><span class="sxs-lookup"><span data-stu-id="ab146-165">When downloading an offboarding package, you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="ab146-166">オンボードポリシーとオフボードポリシーを同じデバイスに同時に展開することはできません。そうしないと、予期しない競合が発生します。</span><span class="sxs-lookup"><span data-stu-id="ab146-166">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a><span data-ttu-id="ab146-167">Microsoft エンドポイント構成マネージャーの現在のブランチを使用した offboard デバイス</span><span class="sxs-lookup"><span data-stu-id="ab146-167">Offboard devices using Microsoft Endpoint Configuration Manager current branch</span></span>

<span data-ttu-id="ab146-168">Microsoft エンドポイント構成マネージャーの現在のブランチを使用する場合は、「オフ [ボード構成ファイルを作成](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab146-168">If you use Microsoft Endpoint Configuration Manager current branch, see [Create an offboarding configuration file](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).</span></span>

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a><span data-ttu-id="ab146-169">System Center 2012 R2 構成マネージャーを使用するオフボードデバイス</span><span class="sxs-lookup"><span data-stu-id="ab146-169">Offboard devices using System Center 2012 R2 Configuration Manager</span></span>

1. <span data-ttu-id="ab146-170">[Microsoft コンプライアンスセンター](https://compliance.microsoft.com/)からオフボードパッケージを取得します。</span><span class="sxs-lookup"><span data-stu-id="ab146-170">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/):</span></span>

2. <span data-ttu-id="ab146-171">ナビゲーションウィンドウで、[ **設定** ] [デバイスのオンボードオフボード] を選択し  >   **Device onboarding** >  **Offboarding** ます。</span><span class="sxs-lookup"><span data-stu-id="ab146-171">In the navigation pane, select **Settings** >  **Device onboarding**> **Offboarding** .</span></span>

3. <span data-ttu-id="ab146-172">オペレーティングシステムとして [Windows 10] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ab146-172">Select Windows 10 as the operating system.</span></span>

4. <span data-ttu-id="ab146-173">[ **展開方法** ] フィールドで、[ **Microsoft エンドポイント構成マネージャー 2012/2012 R2/1511/1602** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ab146-173">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** .</span></span>
    
5. <span data-ttu-id="ab146-174">[ **パッケージのダウンロード** ] を選択し、.zip ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="ab146-174">Select **Download package** , and save the .zip file.</span></span>

6. <span data-ttu-id="ab146-175">.Zip ファイルの内容を、パッケージを展開するネットワーク管理者がアクセスできる共有の読み取り専用の場所に展開します。</span><span class="sxs-lookup"><span data-stu-id="ab146-175">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="ab146-176">*DeviceComplianceOffboardingScript_valid_until_YYYY* という名前のファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="ab146-176">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* .</span></span>

7. <span data-ttu-id="ab146-177">[System Center 2012 R2 Configuration Manager 記事の「パッケージとプログラム](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))」に記載されている手順に従って、パッケージを展開します。</span><span class="sxs-lookup"><span data-stu-id="ab146-177">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) article.</span></span>

8. <span data-ttu-id="ab146-178">パッケージを展開する定義済みのデバイスコレクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="ab146-178">Choose a predefined device collection to deploy the package to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ab146-179">オフボードを使用すると、デバイスはポータルへのセンサーデータの送信を停止しますが、デバイスからのデータは、必要なアラートへの参照も含めて最大6か月保持されます。</span><span class="sxs-lookup"><span data-stu-id="ab146-179">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="ab146-180">デバイス構成の監視</span><span class="sxs-lookup"><span data-stu-id="ab146-180">Monitor device configuration</span></span>

<span data-ttu-id="ab146-181">Microsoft エンドポイント構成マネージャーの現在のブランチを使用している場合は、Configuration Manager コンソールの組み込みの Microsoft Defender ATP ダッシュボードを使用します。</span><span class="sxs-lookup"><span data-stu-id="ab146-181">If you're using Microsoft Endpoint Configuration Manager current branch, use the built-in Microsoft Defender ATP dashboard in the Configuration Manager console.</span></span> <span data-ttu-id="ab146-182">詳細については、「 [Microsoft Defender Advanced Threat Protection-Monitor](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab146-182">For more information, see [Microsoft Defender Advanced Threat Protection - Monitor](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).</span></span>

<span data-ttu-id="ab146-183">System Center 2012 R2 構成マネージャーを使用している場合、監視は2つの部分で構成されます。</span><span class="sxs-lookup"><span data-stu-id="ab146-183">If you're using System Center 2012 R2 Configuration Manager, monitoring consists of two parts:</span></span>

1. <span data-ttu-id="ab146-184">構成パッケージが正しく展開されており、ネットワークのデバイス上で実行されていることを確認します (または正常に実行されています)。</span><span class="sxs-lookup"><span data-stu-id="ab146-184">Confirming the configuration package has been correctly deployed and is running (or has successfully run) on the devices in your network.</span></span>

2. <span data-ttu-id="ab146-185">デバイスが Microsoft 365 エンドポイントのデータ損失防止サービスに準拠していることを確認します (これにより、デバイスがオンボードプロセスを完了し、サービスへのデータのレポートを続行できることが保証されます)。</span><span class="sxs-lookup"><span data-stu-id="ab146-185">Checking that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service (this ensures the device can complete the onboarding process and can continue to report data to the service).</span></span>

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a><span data-ttu-id="ab146-186">構成パッケージが正しく展開されたことを確認する</span><span class="sxs-lookup"><span data-stu-id="ab146-186">Confirm the configuration package has been correctly deployed</span></span>

1. <span data-ttu-id="ab146-187">構成マネージャーコンソールで、ナビゲーションウィンドウの下部にある [ **監視** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab146-187">In the Configuration Manager console, click **Monitoring** at the bottom of the navigation pane.</span></span>

2. <span data-ttu-id="ab146-188">[ **概要** ] を選択し、[ **展開** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ab146-188">Select **Overview** and then **Deployments** .</span></span>

3. <span data-ttu-id="ab146-189">パッケージ名を使用して展開上でを選択します。</span><span class="sxs-lookup"><span data-stu-id="ab146-189">Select on the deployment with the package name.</span></span>

4. <span data-ttu-id="ab146-190">[ **完了統計** ] と [コンテンツの **状態** ] の下にあるステータスインジケーターを確認します。</span><span class="sxs-lookup"><span data-stu-id="ab146-190">Review the status indicators under **Completion Statistics** and **Content Status** .</span></span>

    <span data-ttu-id="ab146-191">失敗した展開 ( **エラー** 、 **要件が満たされていない** 、または失敗した **状態** ) がある場合は、デバイスのトラブルシューティングが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="ab146-191">If there are failed deployments (devices with **Error** , **Requirements Not Met** , or **Failed statuses** ), you may need to  troubleshoot the devices.</span></span> <span data-ttu-id="ab146-192">詳細については、「 [Microsoft Defender Advanced Threat Protection のオンボード問題のトラブルシューティング](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab146-192">For more information, see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

    ![エラーなしで展開が成功したことを示す構成マネージャー](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-365-endpoint-data-loss-prevention-service"></a><span data-ttu-id="ab146-194">デバイスが Microsoft 365 エンドポイントのデータ損失防止サービスに準拠していることを確認する</span><span class="sxs-lookup"><span data-stu-id="ab146-194">Check that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service</span></span>

<span data-ttu-id="ab146-195">System Center 2012 R2 構成マネージャーの構成アイテムのコンプライアンスルールを設定して、展開を監視することができます。</span><span class="sxs-lookup"><span data-stu-id="ab146-195">You can set a compliance rule for configuration item in System Center 2012 R2 Configuration Manager to monitor your deployment.</span></span>

> [!NOTE]
> <span data-ttu-id="ab146-196">この手順とレジストリエントリは、エンドポイント DLP だけでなく、Advanced Threat Protection にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="ab146-196">This procedure and registry entry applies to Endpoint DLP as well as Advanced Threat Protection.</span></span>

<span data-ttu-id="ab146-197">このルールは、対象デバイス上のレジストリキーの値を監視する、 *修復以外* のコンプライアンスルール構成項目である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab146-197">This rule should be a *non-remediating* compliance rule configuration item that monitors the value of a registry key on targeted devices.</span></span>

<span data-ttu-id="ab146-198">次のレジストリキーエントリを監視します。</span><span class="sxs-lookup"><span data-stu-id="ab146-198">Monitor the following registry key entry:</span></span>
```
Path: “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status”
Name: “OnboardingState”
Value: “1”
```
<span data-ttu-id="ab146-199">詳細については、「 [System Center 2012 R2 構成マネージャーのコンプライアンス設定に](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))ついて」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab146-199">For more information, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ab146-200">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab146-200">Related topics</span></span>
- [<span data-ttu-id="ab146-201">グループポリシーを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="ab146-201">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="ab146-202">モバイルデバイス管理ツールを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="ab146-202">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="ab146-203">ローカルスクリプトを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="ab146-203">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="ab146-204">オンボードの非永続仮想デスクトップインフラストラクチャ (VDI) デバイス</span><span class="sxs-lookup"><span data-stu-id="ab146-204">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="ab146-205">新しく利用 Microsoft Defender ATP デバイスで検出テストを実行する</span><span class="sxs-lookup"><span data-stu-id="ab146-205">Run a detection test on a newly onboarded Microsoft Defender ATP device</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="ab146-206">Microsoft Defender Advanced Threat Protection のオンボード問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ab146-206">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
