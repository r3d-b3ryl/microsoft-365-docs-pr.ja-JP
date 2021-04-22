---
title: Configuration Manager を使用した Windows 10 デバイスのオンボード
description: Configuration Manager を使用してデバイスに構成パッケージを展開し、サービスにオンボードします。
keywords: sccm を使用したオンボード デバイス、デバイス管理、エンドポイント デバイス用 Microsoft Defender の構成
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
ms.date: 02/07/2020
ms.technology: mde
ms.openlocfilehash: e919f697048840b0eb7bffd34914328fe233f823
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935163"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a><span data-ttu-id="20165-104">Configuration Manager を使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="20165-104">Onboard Windows 10 devices using Configuration Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="20165-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="20165-105">**Applies to:**</span></span>

- [<span data-ttu-id="20165-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="20165-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="20165-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="20165-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- <span data-ttu-id="20165-108">Microsoft Endpoint Configuration Manager current branch</span><span class="sxs-lookup"><span data-stu-id="20165-108">Microsoft Endpoint Configuration Manager current branch</span></span>
- <span data-ttu-id="20165-109">System Center 2012 R2 構成マネージャー</span><span class="sxs-lookup"><span data-stu-id="20165-109">System Center 2012 R2 Configuration Manager</span></span>

><span data-ttu-id="20165-110">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="20165-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="20165-111">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="20165-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointssccm-abovefoldlink)

## <a name="supported-client-operating-systems"></a><span data-ttu-id="20165-112">サポートされているクライアント オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="20165-112">Supported client operating systems</span></span>

<span data-ttu-id="20165-113">実行している Configuration Manager のバージョンに基づいて、次のクライアント オペレーティング システムをオンボードできます。</span><span class="sxs-lookup"><span data-stu-id="20165-113">Based on the version of Configuration Manager you're running, the following client operating systems can be onboarded:</span></span>

#### <a name="configuration-manager-version-1910-and-prior"></a><span data-ttu-id="20165-114">Configuration Manager バージョン 1910 以前</span><span class="sxs-lookup"><span data-stu-id="20165-114">Configuration Manager version 1910 and prior</span></span>

- <span data-ttu-id="20165-115">Windows 10 を実行しているクライアント コンピューター</span><span class="sxs-lookup"><span data-stu-id="20165-115">Clients computers running Windows 10</span></span> 

#### <a name="configuration-manager-version-2002-and-later"></a><span data-ttu-id="20165-116">Configuration Manager バージョン 2002 以降</span><span class="sxs-lookup"><span data-stu-id="20165-116">Configuration Manager version 2002 and later</span></span>

<span data-ttu-id="20165-117">Configuration Manager バージョン 2002 から、次のオペレーティング システムをオンボードできます。</span><span class="sxs-lookup"><span data-stu-id="20165-117">Starting in Configuration Manager version 2002, you can onboard the following operating systems:</span></span>

- <span data-ttu-id="20165-118">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="20165-118">Windows 8.1</span></span>
- <span data-ttu-id="20165-119">Windows 10</span><span class="sxs-lookup"><span data-stu-id="20165-119">Windows 10</span></span>
- <span data-ttu-id="20165-120">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="20165-120">Windows Server 2012 R2</span></span>
- <span data-ttu-id="20165-121">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="20165-121">Windows Server 2016</span></span>
- <span data-ttu-id="20165-122">Windows Server 2016 バージョン 1803 以降</span><span class="sxs-lookup"><span data-stu-id="20165-122">Windows Server 2016, version 1803 or later</span></span>
- <span data-ttu-id="20165-123">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="20165-123">Windows Server 2019</span></span>

>[!NOTE]
><span data-ttu-id="20165-124">R2 Windows Server 2012、Windows Server 2016、および Windows Server 2019 をオンボードする方法の詳細については、「オンボード Windows サーバー」 [を参照してください](configure-server-endpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="20165-124">For more information on how to onboard Windows Server 2012 R2, Windows Server 2016, and Windows Server 2019, see, [Onboard Windows servers](configure-server-endpoints.md).</span></span>



### <a name="onboard-devices-using-system-center-configuration-manager"></a><span data-ttu-id="20165-125">System Center Configuration Manager を使用したオンボード デバイス</span><span class="sxs-lookup"><span data-stu-id="20165-125">Onboard devices using System Center Configuration Manager</span></span>


<span data-ttu-id="20165-126">[![さまざまな展開パスを示す PDF のイメージ](images/onboard-config-mgr.png)](images/onboard-config-mgr.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="20165-126">[![Image of the PDF showing the various deployment paths](images/onboard-config-mgr.png)](images/onboard-config-mgr.png#lightbox)</span></span>


<span data-ttu-id="20165-127">MICROSOFT Defender for [](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) Endpoint の展開のさまざまなパスを確認するには[、PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)または Visio を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20165-127">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Microsoft Defender for Endpoint.</span></span> 



1. <span data-ttu-id="20165-128">サービス オンボーディング ウィザードからダウンロードした Configuration Manager 構成 *パッケージ*.zip ファイル (WindowsDefenderATPOnboardingPackage.zip) を開きます。</span><span class="sxs-lookup"><span data-stu-id="20165-128">Open the Configuration Manager configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="20165-129">Microsoft Defender セキュリティ センターからパッケージ [を取得できます](https://securitycenter.windows.com/)。</span><span class="sxs-lookup"><span data-stu-id="20165-129">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="20165-130">ナビゲーション ウィンドウで、[設定オンボーディング]  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="20165-130">In the navigation pane, select **Settings** > **Onboarding**.</span></span>
    
    1. <span data-ttu-id="20165-131">オペレーティング システムとして [Windows 10] を選択します。</span><span class="sxs-lookup"><span data-stu-id="20165-131">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="20165-132">[展開方法 **] フィールドで\*\*\*\*、[System Center Configuration Manager 2012/2012 R2/1511/1602] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="20165-132">In the **Deployment method** field, select **System Center Configuration Manager 2012/2012 R2/1511/1602**.</span></span>
    
    1. <span data-ttu-id="20165-133">[ **パッケージのダウンロード]** を選択し、.zip ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="20165-133">Select **Download package**, and save the .zip file.</span></span>

2. <span data-ttu-id="20165-134">.zip ファイルの内容を、パッケージを展開するネットワーク管理者がアクセスできる共有の読み取り専用の場所に展開します。</span><span class="sxs-lookup"><span data-stu-id="20165-134">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="20165-135">*WindowsDefenderATPOnboardingScript.cmd という名前のファイルが必要です*。</span><span class="sxs-lookup"><span data-stu-id="20165-135">You should have a file named *WindowsDefenderATPOnboardingScript.cmd*.</span></span>

3. <span data-ttu-id="20165-136">「System [Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) のパッケージとプログラム」の記事の手順に従ってパッケージを展開します。</span><span class="sxs-lookup"><span data-stu-id="20165-136">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) article.</span></span>

    <span data-ttu-id="20165-137">a.</span><span class="sxs-lookup"><span data-stu-id="20165-137">a.</span></span> <span data-ttu-id="20165-138">パッケージを展開する定義済みのデバイス コレクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="20165-138">Choose a predefined device collection to deploy the package to.</span></span>

> [!NOTE]
> <span data-ttu-id="20165-139">Defender for Endpoint は、アウトオブボックス エクスペリエンス [(OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) フェーズ中のオンボーディングをサポートしない。</span><span class="sxs-lookup"><span data-stu-id="20165-139">Defender for Endpoint doesn't support onboarding during the [Out-Of-Box Experience (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) phase.</span></span> <span data-ttu-id="20165-140">Windows のインストールまたはアップグレードを実行した後、ユーザーが OOBE を完了してください。</span><span class="sxs-lookup"><span data-stu-id="20165-140">Make sure users complete OOBE after running Windows installation or upgrading.</span></span>

>[!TIP]
> <span data-ttu-id="20165-141">デバイスのオンボード後、検出テストを実行して、デバイスがサービスに適切にオンボードされていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="20165-141">After onboarding the device, you can choose to run a detection test to verify that an device is properly onboarded to the service.</span></span> <span data-ttu-id="20165-142">詳細については、「新しくオンボードされた Defender for Endpoint デバイスで検出テストを実行 [する」を参照してください](run-detection-test.md)。</span><span class="sxs-lookup"><span data-stu-id="20165-142">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint device](run-detection-test.md).</span></span>
>
> <span data-ttu-id="20165-143">Configuration Manager アプリケーションで検出ルールを作成して、デバイスがオンボードされた場合に継続的にチェックを行える点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="20165-143">Note that it is possible to create a detection rule on a Configuration Manager application to continuously check if a device has been onboarded.</span></span> <span data-ttu-id="20165-144">アプリケーションは、パッケージやプログラムとは異なる種類のオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="20165-144">An application is a different type of object than a package and program.</span></span>
> <span data-ttu-id="20165-145">デバイスがまだオンボードされていない場合 (保留中の OOBE の完了その他の理由により)、Configuration Manager は、ルールが状態の変更を検出するまで、デバイスのオンボードを再試行します。</span><span class="sxs-lookup"><span data-stu-id="20165-145">If a device is not yet onboarded (due to pending OOBE completion or any other reason), Configuration Manager will retry to onboard the device until the rule detects the status change.</span></span>
> 
> <span data-ttu-id="20165-146">この動作は、"OnboardingState" レジストリ値 (タイプ REG_DWORD) が 1 の場合に検出ルールチェックを作成することで実現できます。</span><span class="sxs-lookup"><span data-stu-id="20165-146">This behavior can be accomplished by creating a detection rule checking if the "OnboardingState" registry value (of type REG_DWORD) = 1.</span></span>
> <span data-ttu-id="20165-147">このレジストリ値は、"HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status" の下にあります。</span><span class="sxs-lookup"><span data-stu-id="20165-147">This registry value is located under "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span></span>
<span data-ttu-id="20165-148">詳細については [、「Configure Detection Methods in System Center 2012 R2 Configuration Manager」を参照してください](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)。</span><span class="sxs-lookup"><span data-stu-id="20165-148">For more information, see [Configure Detection Methods in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="20165-149">サンプル コレクション設定の構成</span><span class="sxs-lookup"><span data-stu-id="20165-149">Configure sample collection settings</span></span>

<span data-ttu-id="20165-150">デバイスごとに構成値を設定して、Microsoft Defender Security Center を介して詳細分析用のファイルを送信する要求が行われたときに、デバイスからサンプルを収集できるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="20165-150">For each device, you can set a configuration value to state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

>[!NOTE]
><span data-ttu-id="20165-151">これらの構成設定は、通常、Configuration Manager を介して行われます。</span><span class="sxs-lookup"><span data-stu-id="20165-151">These configuration settings are typically done through Configuration Manager.</span></span> 

<span data-ttu-id="20165-152">Configuration Manager で構成アイテムのコンプライアンス ルールを設定して、デバイスのサンプル共有設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="20165-152">You can set a compliance rule for configuration item in Configuration Manager to change the sample share setting on a device.</span></span>

<span data-ttu-id="20165-153">このルールは、対象デバイスのレジストリ キーの値を設定して、苦情を確実に受け取るコンプライアンス ルール構成項目を修復する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20165-153">This rule should be a *remediating* compliance rule configuration item that sets the value of a registry key on targeted devices to make sure they’re complaint.</span></span>

<span data-ttu-id="20165-154">構成は、次のレジストリ キー エントリを使用して設定されます。</span><span class="sxs-lookup"><span data-stu-id="20165-154">The configuration is set through the following registry key entry:</span></span>

```console
Path: "HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection"
Name: "AllowSampleCollection"
Value: 0 or 1
```

<span data-ttu-id="20165-155">ここで、</span><span class="sxs-lookup"><span data-stu-id="20165-155">Where:</span></span><br>
<span data-ttu-id="20165-156">キーの種類は D-WORD です。</span><span class="sxs-lookup"><span data-stu-id="20165-156">Key type is a D-WORD.</span></span> <br>
<span data-ttu-id="20165-157">使用可能な値は次のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="20165-157">Possible values are:</span></span>
- <span data-ttu-id="20165-158">0 - このデバイスからのサンプル共有を許可しない</span><span class="sxs-lookup"><span data-stu-id="20165-158">0 - doesn't allow sample sharing  from this device</span></span>
- <span data-ttu-id="20165-159">1 - このデバイスからすべての種類のファイルを共有できます</span><span class="sxs-lookup"><span data-stu-id="20165-159">1 - allows sharing of all file types from this device</span></span>

<span data-ttu-id="20165-160">レジストリ キーが存在しない場合の既定値は 1 です。</span><span class="sxs-lookup"><span data-stu-id="20165-160">The default value in case the registry key doesn’t exist is 1.</span></span>

<span data-ttu-id="20165-161">System Center Configuration Manager コンプライアンスの詳細については、「System Center [2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))のコンプライアンス設定の概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20165-161">For more information about System Center Configuration Manager Compliance, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="20165-162">その他の推奨構成設定</span><span class="sxs-lookup"><span data-stu-id="20165-162">Other recommended configuration settings</span></span>
<span data-ttu-id="20165-163">デバイスをサービスにオンボーディングした後、以下の推奨構成設定でデバイスを有効にすることで、含まれている脅威保護機能を活用することが重要です。</span><span class="sxs-lookup"><span data-stu-id="20165-163">After onboarding devices to the service, it's important to take advantage of the included threat protection capabilities by enabling them with the following recommended configuration settings.</span></span>

### <a name="device-collection-configuration"></a><span data-ttu-id="20165-164">デバイス コレクションの構成</span><span class="sxs-lookup"><span data-stu-id="20165-164">Device collection configuration</span></span>
<span data-ttu-id="20165-165">バージョン 2002 以降のエンドポイント構成マネージャーを使用している場合は、展開を拡大してサーバーまたはダウンレベルのクライアントを含める方法を選択できます。</span><span class="sxs-lookup"><span data-stu-id="20165-165">If you're using Endpoint Configuration Manager, version 2002 or later, you can choose to broaden the deployment to include servers or down-level clients.</span></span>


### <a name="next-generation-protection-configuration"></a><span data-ttu-id="20165-166">次世代の保護構成</span><span class="sxs-lookup"><span data-stu-id="20165-166">Next generation protection configuration</span></span>
<span data-ttu-id="20165-167">次の構成設定をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="20165-167">The following configuration settings are recommended:</span></span>

<span data-ttu-id="20165-168">**スキャン**</span><span class="sxs-lookup"><span data-stu-id="20165-168">**Scan**</span></span> <br>
- <span data-ttu-id="20165-169">USB ドライブなどのリムーバブル 記憶域デバイスをスキャンする: はい</span><span class="sxs-lookup"><span data-stu-id="20165-169">Scan removable storage devices such as USB drives: Yes</span></span>

<span data-ttu-id="20165-170">**リアルタイム保護**</span><span class="sxs-lookup"><span data-stu-id="20165-170">**Real-time Protection**</span></span> <br>
- <span data-ttu-id="20165-171">動作監視を有効にする: はい</span><span class="sxs-lookup"><span data-stu-id="20165-171">Enable Behavioral Monitoring: Yes</span></span>
- <span data-ttu-id="20165-172">ダウンロード時およびインストール前に望ましくない可能性があるアプリケーションに対する保護を有効にする: はい</span><span class="sxs-lookup"><span data-stu-id="20165-172">Enable protection against Potentially Unwanted Applications at download and prior to installation: Yes</span></span>

<span data-ttu-id="20165-173">**クラウド保護サービス**</span><span class="sxs-lookup"><span data-stu-id="20165-173">**Cloud Protection Service**</span></span>
- <span data-ttu-id="20165-174">Cloud Protection Service メンバーシップの種類: 高度なメンバーシップ</span><span class="sxs-lookup"><span data-stu-id="20165-174">Cloud Protection Service membership type: Advanced membership</span></span>

<span data-ttu-id="20165-175">**攻撃表面の縮小** 使用可能なすべてのルールを [監査] に構成します。</span><span class="sxs-lookup"><span data-stu-id="20165-175">**Attack surface reduction** Configure all available rules to Audit.</span></span>

>[!NOTE]
> <span data-ttu-id="20165-176">これらのアクティビティをブロックすると、正当なビジネス プロセスが中断される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="20165-176">Blocking these activities may interrupt legitimate business processes.</span></span> <span data-ttu-id="20165-177">最善の方法は、すべてを監査に設定し、有効にしても安全な設定を特定し、誤検知検出を持つエンドポイントでこれらの設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="20165-177">The best approach is setting everything to audit, identifying which ones are safe to turn on, and then enabling those settings on endpoints which do not have false positive detections.</span></span>


<span data-ttu-id="20165-178">**ネットワーク保護**</span><span class="sxs-lookup"><span data-stu-id="20165-178">**Network protection**</span></span> <br>
<span data-ttu-id="20165-179">監査モードまたはブロック モードでネットワーク保護を有効にする前に、サポート ページから入手できるマルウェア対策プラットフォーム更新プログラムがインストール [されていることを確認してください](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)。</span><span class="sxs-lookup"><span data-stu-id="20165-179">Prior to enabling network protection in audit or block mode, ensure that you've installed the antimalware platform update, which can be obtained from the [support page](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).</span></span>


<span data-ttu-id="20165-180">**制御されたフォルダー アクセス**</span><span class="sxs-lookup"><span data-stu-id="20165-180">**Controlled folder access**</span></span><br>
<span data-ttu-id="20165-181">監査モードで機能を 30 日以上有効にします。</span><span class="sxs-lookup"><span data-stu-id="20165-181">Enable the feature in audit mode for at least 30 days.</span></span> <span data-ttu-id="20165-182">この期間が終了した後、検出を確認し、保護されたディレクトリへの書き込みを許可するアプリケーションの一覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="20165-182">After this period, review detections and create a list of applications that are allowed to write to protected directories.</span></span>

<span data-ttu-id="20165-183">詳細については、「管理フォルダー アクセス [の評価」を参照してください](evaluate-controlled-folder-access.md)。</span><span class="sxs-lookup"><span data-stu-id="20165-183">For more information, see [Evaluate controlled folder access](evaluate-controlled-folder-access.md).</span></span>


## <a name="offboard-devices-using-configuration-manager"></a><span data-ttu-id="20165-184">Configuration Manager を使用したオフボード デバイス</span><span class="sxs-lookup"><span data-stu-id="20165-184">Offboard devices using Configuration Manager</span></span>

<span data-ttu-id="20165-185">セキュリティ上の理由から、Offboard デバイスに使用されるパッケージは、ダウンロード日から 30 日後に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="20165-185">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="20165-186">デバイスに送信された期限切れのオフボード パッケージは拒否されます。</span><span class="sxs-lookup"><span data-stu-id="20165-186">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="20165-187">オフボード パッケージをダウンロードすると、パッケージの有効期限が通知され、パッケージ名にも含まれます。</span><span class="sxs-lookup"><span data-stu-id="20165-187">When downloading an offboarding package, you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="20165-188">オンボーディングポリシーとオフボード ポリシーを同じデバイスに同時に展開し、それ以外の場合は予期しない競合を引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="20165-188">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

### <a name="offboard-devices-using-microsoft-endpoint-manager-current-branch"></a><span data-ttu-id="20165-189">Microsoft Endpoint Manager カレント ブランチを使用するオフボード デバイス</span><span class="sxs-lookup"><span data-stu-id="20165-189">Offboard devices using Microsoft Endpoint Manager current branch</span></span>

<span data-ttu-id="20165-190">Microsoft Endpoint Manager カレント ブランチを使用する場合は、「 [オフボード構成ファイルを作成する」を参照してください](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)。</span><span class="sxs-lookup"><span data-stu-id="20165-190">If you use Microsoft Endpoint Manager current branch, see [Create an offboarding configuration file](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).</span></span>

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a><span data-ttu-id="20165-191">System Center 2012 R2 Configuration Manager を使用するオフボード デバイス</span><span class="sxs-lookup"><span data-stu-id="20165-191">Offboard devices using System Center 2012 R2 Configuration Manager</span></span>

1. <span data-ttu-id="20165-192">Microsoft Defender セキュリティ センターからオフボード パッケージ [を取得します](https://securitycenter.windows.com/)。</span><span class="sxs-lookup"><span data-stu-id="20165-192">Get the offboarding package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="20165-193">ナビゲーション ウィンドウで、[設定] [**オフボード]**  >   **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="20165-193">In the navigation pane, select **Settings** >  **Offboarding**.</span></span>

    1. <span data-ttu-id="20165-194">オペレーティング システムとして [Windows 10] を選択します。</span><span class="sxs-lookup"><span data-stu-id="20165-194">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="20165-195">[展開方法 **] フィールドで\*\*\*\*、[System Center Configuration Manager 2012/2012 R2/1511/1602] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="20165-195">In the **Deployment method** field, select **System Center Configuration Manager 2012/2012 R2/1511/1602**.</span></span>
    
    1. <span data-ttu-id="20165-196">[ **パッケージのダウンロード]** を選択し、.zip ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="20165-196">Select **Download package**, and save the .zip file.</span></span>

2. <span data-ttu-id="20165-197">.zip ファイルの内容を、パッケージを展開するネットワーク管理者がアクセスできる共有の読み取り専用の場所に展開します。</span><span class="sxs-lookup"><span data-stu-id="20165-197">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="20165-198">*-MM-DD.cmd WindowsDefenderATPOffboardingScript_valid_until_YYYYという名前のファイルが必要です*。</span><span class="sxs-lookup"><span data-stu-id="20165-198">You should have a file named *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

3. <span data-ttu-id="20165-199">「System [Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) のパッケージとプログラム」の記事の手順に従ってパッケージを展開します。</span><span class="sxs-lookup"><span data-stu-id="20165-199">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) article.</span></span>

    <span data-ttu-id="20165-200">a.</span><span class="sxs-lookup"><span data-stu-id="20165-200">a.</span></span> <span data-ttu-id="20165-201">パッケージを展開する定義済みのデバイス コレクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="20165-201">Choose a predefined device collection to deploy the package to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="20165-202">Offboarding を使用すると、デバイスはポータルへのセンサー データの送信を停止しますが、デバイスからのデータ (通知への参照を含む) は最大 6 か月間保持されます。</span><span class="sxs-lookup"><span data-stu-id="20165-202">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="20165-203">デバイス構成の監視</span><span class="sxs-lookup"><span data-stu-id="20165-203">Monitor device configuration</span></span>

<span data-ttu-id="20165-204">Microsoft Endpoint Manager の現在のブランチを使用している場合は、Configuration Manager コンソールの組み込みの Defender for Endpoint ダッシュボードを使用します。</span><span class="sxs-lookup"><span data-stu-id="20165-204">If you're using Microsoft Endpoint Manager current branch, use the built-in Defender for Endpoint dashboard in the Configuration Manager console.</span></span> <span data-ttu-id="20165-205">詳細については [、「Defender for Endpoint - Monitor」を参照してください](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)。</span><span class="sxs-lookup"><span data-stu-id="20165-205">For more information, see [Defender for Endpoint - Monitor](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).</span></span>

<span data-ttu-id="20165-206">System Center 2012 R2 Configuration Manager を使用している場合、監視は次の 2 つの部分で構成されます。</span><span class="sxs-lookup"><span data-stu-id="20165-206">If you're using System Center 2012 R2 Configuration Manager, monitoring consists of two parts:</span></span>

1. <span data-ttu-id="20165-207">構成パッケージが正しく展開され、ネットワーク内のデバイスで実行 (または正常に実行) されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="20165-207">Confirming the configuration package has been correctly deployed and is running (or has successfully run) on the devices in your network.</span></span>

2. <span data-ttu-id="20165-208">デバイスが Defender for Endpoint サービスに準拠しているのを確認します (これにより、デバイスはオンボーディング プロセスを完了し、引き続きサービスにデータを報告できます)。</span><span class="sxs-lookup"><span data-stu-id="20165-208">Checking that the devices are compliant with the Defender for Endpoint service (this ensures the device can complete the onboarding process and can continue to report data to the service).</span></span>

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a><span data-ttu-id="20165-209">構成パッケージが正しく展開されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="20165-209">Confirm the configuration package has been correctly deployed</span></span>

1. <span data-ttu-id="20165-210">Configuration Manager コンソールで、ナビゲーション ウィンドウ **の** 下部にある [監視] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20165-210">In the Configuration Manager console, click **Monitoring** at the bottom of the navigation pane.</span></span>

2. <span data-ttu-id="20165-211">[概要 **] を選択** し、[ **展開] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="20165-211">Select **Overview** and then **Deployments**.</span></span>

3. <span data-ttu-id="20165-212">パッケージ名を使用して展開を選択します。</span><span class="sxs-lookup"><span data-stu-id="20165-212">Select on the deployment with the package name.</span></span>

4. <span data-ttu-id="20165-213">[完了統計] と [コンテンツ **の状態] の下の** 状態インジケーター **を確認します**。</span><span class="sxs-lookup"><span data-stu-id="20165-213">Review the status indicators under **Completion Statistics** and **Content Status**.</span></span>

    <span data-ttu-id="20165-214">失敗した展開 (エラー、要件が満たされていないデバイス、または失敗した状態) がある場合は、デバイスのトラブルシューティングが必要な場合があります。 </span><span class="sxs-lookup"><span data-stu-id="20165-214">If there are failed deployments (devices with **Error**, **Requirements Not Met**, or **Failed statuses**), you may need to  troubleshoot the devices.</span></span> <span data-ttu-id="20165-215">詳細については [、「Troubleshoot Microsoft Defender for Endpoint オンボーディングの問題」を参照してください](troubleshoot-onboarding.md)。</span><span class="sxs-lookup"><span data-stu-id="20165-215">For more information, see, [Troubleshoot Microsoft Defender for Endpoint onboarding issues](troubleshoot-onboarding.md).</span></span>

    ![エラーがない展開が正常に実行されたことを示す Configuration Manager](images/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="20165-217">デバイスが Microsoft Defender for Endpoint サービスに準拠しているのを確認する</span><span class="sxs-lookup"><span data-stu-id="20165-217">Check that the devices are compliant with the Microsoft Defender for Endpoint service</span></span>

<span data-ttu-id="20165-218">System Center 2012 R2 Configuration Manager で構成アイテムのコンプライアンス ルールを設定して、展開を監視できます。</span><span class="sxs-lookup"><span data-stu-id="20165-218">You can set a compliance rule for configuration item in System Center 2012 R2 Configuration Manager to monitor your deployment.</span></span>

<span data-ttu-id="20165-219">このルールは *、対象となる* デバイスのレジストリ キーの値を監視する、修復されていないコンプライアンス ルール構成アイテムである必要があります。</span><span class="sxs-lookup"><span data-stu-id="20165-219">This rule should be a *non-remediating* compliance rule configuration item that monitors the value of a registry key on targeted devices.</span></span>

<span data-ttu-id="20165-220">次のレジストリ キー エントリを監視します。</span><span class="sxs-lookup"><span data-stu-id="20165-220">Monitor the following registry key entry:</span></span>

```console
Path: "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status"
Name: "OnboardingState"
Value: "1"
```

<span data-ttu-id="20165-221">詳細については [、「System Center 2012 R2 Configuration Manager のコンプライアンス設定の概要」を参照してください](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))。</span><span class="sxs-lookup"><span data-stu-id="20165-221">For more information, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span></span>

## <a name="related-topics"></a><span data-ttu-id="20165-222">関連項目</span><span class="sxs-lookup"><span data-stu-id="20165-222">Related topics</span></span>
- [<span data-ttu-id="20165-223">グループ ポリシーを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="20165-223">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="20165-224">モバイル デバイス管理ツールを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="20165-224">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="20165-225">ローカル スクリプトを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="20165-225">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="20165-226">非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="20165-226">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="20165-227">新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する</span><span class="sxs-lookup"><span data-stu-id="20165-227">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="20165-228">Microsoft Defender for Endpoint オンボーディングの問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="20165-228">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
