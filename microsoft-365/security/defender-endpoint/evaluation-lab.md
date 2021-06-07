---
title: Microsoft Defender for Endpoint 評価ラボ
description: Microsoft Defender for Endpoint の機能について説明し、攻撃シミュレーションを実行し、脅威を防止、検出、修復する方法を確認します。
keywords: エンドポイント用 Microsoft Defender の評価、評価、ラボ、シミュレーション、Windows 10、Windows Server 2019、評価ラボ
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-evalutatemtp
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c785dbb759afe77b14f41985b9f451a4ec52e29f
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778235"
---
# <a name="microsoft-defender-for-endpoint-evaluation-lab"></a><span data-ttu-id="3ea11-104">Microsoft Defender for Endpoint 評価ラボ</span><span class="sxs-lookup"><span data-stu-id="3ea11-104">Microsoft Defender for Endpoint evaluation lab</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3ea11-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3ea11-105">**Applies to:**</span></span>
- [<span data-ttu-id="3ea11-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3ea11-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="3ea11-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3ea11-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="3ea11-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="3ea11-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3ea11-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="3ea11-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


<span data-ttu-id="3ea11-110">包括的なセキュリティ製品評価を行う場合、エンドツーエンドの攻撃シミュレーションを実際に実行する前に、複雑な環境とデバイス構成が必要になる複雑なプロセスになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3ea11-110">Conducting a comprehensive security product evaluation can be a complex process requiring cumbersome environment and device configuration before an end-to-end attack simulation can actually be done.</span></span> <span data-ttu-id="3ea11-111">複雑さを加えるのは、シミュレーション アクティビティ、アラート、および結果が評価中に反映される場所を追跡する際の課題です。</span><span class="sxs-lookup"><span data-stu-id="3ea11-111">Adding to the complexity is the challenge of tracking where the simulation activities, alerts, and results are reflected during the evaluation.</span></span>

<span data-ttu-id="3ea11-112">Microsoft Defender for Endpoint 評価ラボは、プラットフォームの機能の評価、シミュレーションの実行、予防、検出、修復機能の実行に集中できるよう、デバイスと環境構成の複雑さを排除するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="3ea11-112">The Microsoft Defender for Endpoint evaluation lab is designed to eliminate the complexities of device and environment configuration so that you can  focus on evaluating the capabilities of the platform, running simulations, and seeing the prevention, detection, and remediation features in action.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUM]

<span data-ttu-id="3ea11-113">セットアップの簡略化により、独自のテスト シナリオと事前に作成されたシミュレーションの実行に集中して、Defender for Endpoint のパフォーマンスを確認できます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-113">With the simplified set-up experience, you can focus on running your own test scenarios and the pre-made simulations to see how Defender for Endpoint performs.</span></span> 

<span data-ttu-id="3ea11-114">自動調査、高度な狩猟、脅威分析など、プラットフォームの強力な機能に完全にアクセスでき、Defender for Endpoint が提供する包括的な保護スタックをテストできます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-114">You'll have full access to the powerful capabilities of the platform such as automated investigations, advanced hunting, and threat analytics, allowing you to test the comprehensive protection stack that Defender for Endpoint offers.</span></span> 

<span data-ttu-id="3ea11-115">Windows 10 または Windows Server 2019 デバイスを追加して、最新の OS バージョンと適切なセキュリティ コンポーネントがインストールされ、Office 2019 Standard がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-115">You can add Windows 10 or Windows Server 2019 devices that come pre-configured to have the latest OS versions and the right security components in place as well as Office 2019 Standard installed.</span></span>

<span data-ttu-id="3ea11-116">また、脅威シミュレーターをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-116">You can also install threat simulators.</span></span> <span data-ttu-id="3ea11-117">Defender for Endpoint は、業界をリードする脅威シミュレーション プラットフォームと提携し、ポータルから出ることなく Defender for Endpoint の機能をテストするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-117">Defender for Endpoint has partnered with industry leading threat simulation platforms to help you test out the Defender for Endpoint capabilities without having to leave the portal.</span></span>

 <span data-ttu-id="3ea11-118">お好みのシミュレーターをインストールし、評価ラボ内でシナリオを実行し、プラットフォームのパフォーマンスを即座に確認できます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-118">Install your preferred simulator, run scenarios within the evaluation lab, and instantly see how the platform performs - all conveniently available at no extra cost to you.</span></span> <span data-ttu-id="3ea11-119">また、さまざまなシミュレーションにアクセスして、シミュレーション カタログから実行できます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-119">You'll also have convenient access to wide array of simulations which you can access and run from the simulations catalog.</span></span>
    

## <a name="before-you-begin"></a><span data-ttu-id="3ea11-120">はじめに</span><span class="sxs-lookup"><span data-stu-id="3ea11-120">Before you begin</span></span>
<span data-ttu-id="3ea11-121">評価ラボにアクセスするには、ライセンス[](minimum-requirements.md#licensing-requirements)要件を満たすか、Microsoft Defender for Endpoint への試用版アクセス権が必要です。</span><span class="sxs-lookup"><span data-stu-id="3ea11-121">You'll need to fulfill the [licensing requirements](minimum-requirements.md#licensing-requirements) or have trial access to Microsoft Defender for Endpoint to access the evaluation lab.</span></span>

<span data-ttu-id="3ea11-122">次のセキュリティ設定 **の管理権限** が必要です。</span><span class="sxs-lookup"><span data-stu-id="3ea11-122">You must have **Manage security settings** permissions to:</span></span>
- <span data-ttu-id="3ea11-123">ラボを作成する</span><span class="sxs-lookup"><span data-stu-id="3ea11-123">Create the lab</span></span>
- <span data-ttu-id="3ea11-124">デバイスの作成</span><span class="sxs-lookup"><span data-stu-id="3ea11-124">Create devices</span></span>
- <span data-ttu-id="3ea11-125">パスワードのリセット</span><span class="sxs-lookup"><span data-stu-id="3ea11-125">Reset password</span></span>
- <span data-ttu-id="3ea11-126">シミュレーションの作成</span><span class="sxs-lookup"><span data-stu-id="3ea11-126">Create simulations</span></span> 
 
<span data-ttu-id="3ea11-127">役割ベースのアクセス制御 (RBAC) を有効にし、少なくとも 1 つのコンピューター グループを作成した場合、ユーザーはすべてのコンピューター グループにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ea11-127">If you enabled role-based access control (RBAC) and created at least a one machine group, users must have access to All machine groups.</span></span>

<span data-ttu-id="3ea11-128">詳細については、「役割の作成 [と管理」を参照してください](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="3ea11-128">For more information, see [Create and manage roles](user-roles.md).</span></span>

<span data-ttu-id="3ea11-129">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="3ea11-129">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3ea11-130">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="3ea11-130">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink)


## <a name="get-started-with-the-lab"></a><span data-ttu-id="3ea11-131">ラボの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="3ea11-131">Get started with the lab</span></span>
<span data-ttu-id="3ea11-132">メニューからラボにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-132">You can access the lab from the menu.</span></span> <span data-ttu-id="3ea11-133">ナビゲーション メニューで、[評価] と **[チュートリアル] を選択し、[>] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3ea11-133">In the navigation menu, select **Evaluation and tutorials > Evaluation lab**.</span></span>

![メニューの評価ラボのイメージ](images/evaluation-lab-menu.png)

>[!NOTE]
>- <span data-ttu-id="3ea11-135">選択した環境構造の種類に応じて、デバイスはライセンス認証日から指定された時間数で利用できます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-135">Depending the type of environment structure you select, devices will be available for the specified number of hours from the day of activation.</span></span>
>- <span data-ttu-id="3ea11-136">各環境は、制限された一連のテスト デバイスでプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-136">Each environment is provisioned with a limited set of test devices.</span></span> <span data-ttu-id="3ea11-137">プロビジョニングされたデバイスを使用し、それらを削除した場合は、より多くのデバイスを要求できます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-137">When you've used up the provisioned devices and have deleted them, you can request for more devices.</span></span> 
>- <span data-ttu-id="3ea11-138">月に 1 回、ラボ リソースを要求できます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-138">You can request for lab resources once a month.</span></span> 

<span data-ttu-id="3ea11-139">ラボを既に持っていますか?</span><span class="sxs-lookup"><span data-stu-id="3ea11-139">Already have a lab?</span></span> <span data-ttu-id="3ea11-140">新しい脅威シミュレーターを有効にし、アクティブなデバイスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ea11-140">Make sure to enable the new threat simulators and have active devices.</span></span>

## <a name="setup-the-evaluation-lab"></a><span data-ttu-id="3ea11-141">評価ラボのセットアップ</span><span class="sxs-lookup"><span data-stu-id="3ea11-141">Setup the evaluation lab</span></span>

1. <span data-ttu-id="3ea11-142">ナビゲーション ウィンドウで、[評価とチュートリアル]**評価** ラボを  >  **選択** し、[セットアップ ラボ]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3ea11-142">In the navigation pane, select **Evaluation and tutorials** > **Evaluation lab**, then select **Setup lab**.</span></span>

    ![評価ラボのウェルカム ページのイメージ](images/evaluation-lab-setup.png)

2. <span data-ttu-id="3ea11-144">評価のニーズに応じて、より長い期間、またはより短い期間のデバイスが少ない環境をセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-144">Depending on your evaluation needs, you can choose to setup an environment with fewer devices for a longer period or more devices for a shorter period.</span></span> <span data-ttu-id="3ea11-145">好みのラボ構成を選択し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3ea11-145">Select your preferred lab configuration then select **Next**.</span></span>

    ![ラボ構成オプションのイメージ](images/lab-creation-page.png) 


3. <span data-ttu-id="3ea11-147">(省略可能)ラボに脅威シミュレーターをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-147">(Optional) You can choose to install threat simulators in the lab.</span></span> 

    ![インストール シミュレーター エージェントのイメージ](images/install-agent.png)

    >[!IMPORTANT]
    ><span data-ttu-id="3ea11-149">最初に、条項と情報共有に関する声明に同意し、同意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ea11-149">You'll first need to accept and provide consent to the terms and information sharing statements.</span></span> 

4. <span data-ttu-id="3ea11-150">使用する脅威シミュレーション エージェントを選択し、詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="3ea11-150">Select the threat simulation agent you'd like to use and enter your details.</span></span> <span data-ttu-id="3ea11-151">また、後で脅威シミュレーターをインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-151">You can also choose to install threat simulators at a later time.</span></span> <span data-ttu-id="3ea11-152">ラボのセットアップ中に脅威シミュレーション エージェントをインストールする場合は、追加するデバイスに脅威シミュレーション エージェントを簡単にインストールできます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-152">If you choose to install threat simulation agents during the lab setup, you'll enjoy the benefit of having them conveniently installed on the devices you add.</span></span>  
    
    ![概要ページの画像](images/lab-setup-summary.png)

5.  <span data-ttu-id="3ea11-154">概要を確認し、[セットアップ ラボ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3ea11-154">Review the summary and select **Setup lab**.</span></span>  

<span data-ttu-id="3ea11-155">ラボのセットアップ プロセスが完了したら、デバイスを追加してシミュレーションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-155">After the lab setup process is complete, you can add devices and run simulations.</span></span> 


## <a name="add-devices"></a><span data-ttu-id="3ea11-156">デバイスの追加</span><span class="sxs-lookup"><span data-stu-id="3ea11-156">Add devices</span></span>
<span data-ttu-id="3ea11-157">環境にデバイスを追加すると、Defender for Endpoint は接続の詳細を示す構成済みのデバイスをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="3ea11-157">When you add a device to your environment, Defender for Endpoint sets up a well-configured device with connection details.</span></span> <span data-ttu-id="3ea11-158">サーバー 2019 Windows 10またはWindows追加できます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-158">You can add Windows 10 or Windows Server 2019 devices.</span></span>

<span data-ttu-id="3ea11-159">デバイスは、OS および Office 2019 Standard の最新バージョンと、Java、Python、SysIntenals などの他のアプリで構成されます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-159">The device will be configured with the most up-to-date version of the OS and Office 2019 Standard as well as other apps such as Java, Python, and SysIntenals.</span></span> 

<span data-ttu-id="3ea11-160">ラボのセットアップ中に脅威シミュレーターの追加を選択した場合、すべてのデバイスに追加するデバイスに脅威シミュレーター エージェントがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-160">If you chose to add a threat simulator during the lab setup, all devices will have the threat simulator agent installed in the devices that you add.</span></span>

<span data-ttu-id="3ea11-161">デバイスは自動的にテナントにオンボードされ、推奨されるセキュリティ Windowsオンおよび監査モードになります。作業は不要です。</span><span class="sxs-lookup"><span data-stu-id="3ea11-161">The device will automatically be onboarded to your tenant with the recommended Windows security components turned on and in audit mode - with no effort on your side.</span></span> 

<span data-ttu-id="3ea11-162">次のセキュリティ コンポーネントは、テスト デバイスで事前に構成されています。</span><span class="sxs-lookup"><span data-stu-id="3ea11-162">The following security components are pre-configured in the test devices:</span></span>

- [<span data-ttu-id="3ea11-163">攻撃面の減少</span><span class="sxs-lookup"><span data-stu-id="3ea11-163">Attack surface reduction</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard)
- [<span data-ttu-id="3ea11-164">一目でブロックする</span><span class="sxs-lookup"><span data-stu-id="3ea11-164">Block at first sight</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)
- [<span data-ttu-id="3ea11-165">制御されたフォルダー アクセス</span><span class="sxs-lookup"><span data-stu-id="3ea11-165">Controlled folder access</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)
- [<span data-ttu-id="3ea11-166">エクスプロイト保護</span><span class="sxs-lookup"><span data-stu-id="3ea11-166">Exploit protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/enable-exploit-protection)
- [<span data-ttu-id="3ea11-167">ネットワーク保護</span><span class="sxs-lookup"><span data-stu-id="3ea11-167">Network protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
- [<span data-ttu-id="3ea11-168">望ましくない可能性のあるアプリケーションの検出</span><span class="sxs-lookup"><span data-stu-id="3ea11-168">Potentially unwanted application detection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [<span data-ttu-id="3ea11-169">クラウドによる保護</span><span class="sxs-lookup"><span data-stu-id="3ea11-169">Cloud-delivered protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [<span data-ttu-id="3ea11-170">Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="3ea11-170">Microsoft Defender SmartScreen</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview)

>[!NOTE]
> <span data-ttu-id="3ea11-171">Microsoft Defender ウイルス対策オンになります (監査モードではありません)。</span><span class="sxs-lookup"><span data-stu-id="3ea11-171">Microsoft Defender Antivirus will be on (not in audit mode).</span></span> <span data-ttu-id="3ea11-172">シミュレーションMicrosoft Defender ウイルス対策ブロックする場合は、デバイスでリアルタイム保護をオフWindows セキュリティ。</span><span class="sxs-lookup"><span data-stu-id="3ea11-172">If Microsoft Defender Antivirus blocks you from running your simulation, you can turn off real-time protection on the device through Windows Security.</span></span> <span data-ttu-id="3ea11-173">詳細については、「Configure [always-on protection」を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="3ea11-173">For more information, see [Configure always-on protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="3ea11-174">自動調査の設定は、テナントの設定に依存します。</span><span class="sxs-lookup"><span data-stu-id="3ea11-174">Automated investigation settings will be dependent on tenant settings.</span></span> <span data-ttu-id="3ea11-175">既定では半自動で構成されます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-175">It will be configured to be semi-automated by default.</span></span> <span data-ttu-id="3ea11-176">詳細については、「自動調査 [の概要」を参照してください](automated-investigations.md)。</span><span class="sxs-lookup"><span data-stu-id="3ea11-176">For more information, see [Overview of Automated investigations](automated-investigations.md).</span></span>

>[!NOTE]
><span data-ttu-id="3ea11-177">テスト デバイスへの接続は RDP を使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-177">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="3ea11-178">ファイアウォールの設定で RDP 接続が許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ea11-178">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="3ea11-179">ダッシュボードで、[デバイスの追加 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3ea11-179">From the dashboard, select **Add device**.</span></span> 

2. <span data-ttu-id="3ea11-180">追加するデバイスの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="3ea11-180">Choose the type of device to add.</span></span> <span data-ttu-id="3ea11-181">サーバー 2019 にWindows 10またはWindows選択できます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-181">You can choose to add Windows 10 or Windows Server 2019.</span></span>

    ![デバイス オプションを使用したラボセットアップのイメージ](images/add-machine-options.png)


    >[!NOTE]
    ><span data-ttu-id="3ea11-183">デバイスの作成プロセスで問題が発生した場合は、通知が送信され、新しい要求を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ea11-183">If something goes wrong with the device creation process, you'll be notified and you'll need to submit a new request.</span></span> <span data-ttu-id="3ea11-184">デバイスの作成に失敗した場合は、許可された全体的なクォータに対してカウントされません。</span><span class="sxs-lookup"><span data-stu-id="3ea11-184">If the device creation fails, it will not be counted against the overall allowed quota.</span></span> 

3. <span data-ttu-id="3ea11-185">接続の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-185">The connection details are displayed.</span></span> <span data-ttu-id="3ea11-186">[ **コピー] を** 選択して、デバイスのパスワードを保存します。</span><span class="sxs-lookup"><span data-stu-id="3ea11-186">Select **Copy** to save the password for the device.</span></span>

    >[!NOTE]
    ><span data-ttu-id="3ea11-187">パスワードは 1 回だけ表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-187">The password is only displayed once.</span></span> <span data-ttu-id="3ea11-188">後で使用するために必ず保存してください。</span><span class="sxs-lookup"><span data-stu-id="3ea11-188">Be sure to save it for later use.</span></span>

    ![接続の詳細で追加されたデバイスのイメージ](images/add-machine-eval-lab.png)

4. <span data-ttu-id="3ea11-190">デバイスのセットアップが開始されます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-190">Device set up begins.</span></span> <span data-ttu-id="3ea11-191">これには、最大で約 30 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3ea11-191">This can take up to approximately 30 minutes.</span></span> 

5. <span data-ttu-id="3ea11-192">[デバイス] タブを選択して、テスト デバイスの状態、リスクと露出レベル、シミュレーターのインストールの状態 **を確認** します。</span><span class="sxs-lookup"><span data-stu-id="3ea11-192">See the status of test devices, the risk and exposure levels, and the status of simulator installations by selecting the **Devices** tab.</span></span> 

    ![[デバイスのイメージ] タブ](images/machines-tab.png)
    

    > [!TIP]
    > <span data-ttu-id="3ea11-194">[ **シミュレーターの状態]** 列で、情報アイコンにカーソルを合わせると、エージェントのインストール状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-194">In the **Simulator status** column, you can hover over the information icon to know the installation status of an agent.</span></span>

## <a name="request-for-more-devices"></a><span data-ttu-id="3ea11-195">その他のデバイスの要求</span><span class="sxs-lookup"><span data-stu-id="3ea11-195">Request for more devices</span></span>
<span data-ttu-id="3ea11-196">すべての既存のデバイスを使用して削除すると、より多くのデバイスを要求できます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-196">When all existing devices are used and deleted, you can request for more devices.</span></span> <span data-ttu-id="3ea11-197">月に 1 回、ラボ リソースを要求できます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-197">You can request for lab resources once a month.</span></span> 


1. <span data-ttu-id="3ea11-198">評価ラボ ダッシュボードで、[その他のデバイス **を要求する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3ea11-198">From the evaluation lab dashboard, select **Request for more devices**.</span></span>

   ![より多くのデバイスに対する要求のイメージ](images/request-more-devices.png)

2. <span data-ttu-id="3ea11-200">構成を選択します。</span><span class="sxs-lookup"><span data-stu-id="3ea11-200">Choose your configuration.</span></span> 
3. <span data-ttu-id="3ea11-201">要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="3ea11-201">Submit the request.</span></span> 

<span data-ttu-id="3ea11-202">要求が正常に送信されると、緑色の確認バナーと最後の提出日が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-202">When the request is submitted successfully you'll see a green confirmation banner and the date of the last submission.</span></span>
 
<span data-ttu-id="3ea11-203">要求の状態は [ユーザーの操作]タブで確認できます。これは数時間で承認されます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-203">You can find the status of your request in the **User Actions** tab, which will be approved in a matter of hours.</span></span>

<span data-ttu-id="3ea11-204">承認されると、要求されたデバイスがラボ セットアップに追加され、より多くのデバイスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-204">When approved, the requested devices will be added to your lab set up and you’ll be able to create more devices.</span></span> 


> [!TIP]
> <span data-ttu-id="3ea11-205">ラボの詳細を確認するには、シミュレーション ライブラリを確認することを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="3ea11-205">To get more out of your lab, don’t forget to check out our simulations library.</span></span>

## <a name="simulate-attack-scenarios"></a><span data-ttu-id="3ea11-206">攻撃シナリオのシミュレーション</span><span class="sxs-lookup"><span data-stu-id="3ea11-206">Simulate attack scenarios</span></span>
<span data-ttu-id="3ea11-207">テスト デバイスを使用して、テスト デバイスに接続して独自の攻撃シミュレーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="3ea11-207">Use the test devices to run your own attack simulations by connecting to them.</span></span> 

<span data-ttu-id="3ea11-208">攻撃シナリオは、次の方法でシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-208">You can simulate attack scenarios using:</span></span>
- <span data-ttu-id="3ea11-209">["Do It Yourself" 攻撃のシナリオ](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="3ea11-209">The ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials)</span></span>
- <span data-ttu-id="3ea11-210">脅威シミュレーター</span><span class="sxs-lookup"><span data-stu-id="3ea11-210">Threat simulators</span></span>

<span data-ttu-id="3ea11-211">高度な検索を使用[してデータ](advanced-hunting-query-language.md)をクエリし[](threat-analytics.md)、脅威分析を使用して、新たな脅威に関するレポートを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-211">You can also use [Advanced hunting](advanced-hunting-query-language.md) to query data and [Threat analytics](threat-analytics.md) to view reports about emerging threats.</span></span>

### <a name="do-it-yourself-attack-scenarios"></a><span data-ttu-id="3ea11-212">Do-it-yourself 攻撃のシナリオ</span><span class="sxs-lookup"><span data-stu-id="3ea11-212">Do-it-yourself attack scenarios</span></span>
<span data-ttu-id="3ea11-213">事前に作成されたシミュレーションを探している場合は、"Do It [Yourself" 攻撃シナリオを使用できます](https://securitycenter.windows.com/tutorials)。</span><span class="sxs-lookup"><span data-stu-id="3ea11-213">If you are looking for a pre-made simulation, you can use our ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials).</span></span> <span data-ttu-id="3ea11-214">これらのスクリプトは安全で文書化され、使いやすいです。</span><span class="sxs-lookup"><span data-stu-id="3ea11-214">These scripts are safe, documented, and easy to use.</span></span> <span data-ttu-id="3ea11-215">これらのシナリオは、Defender for Endpoint の機能を反映し、調査のエクスペリエンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3ea11-215">These scenarios will reflect Defender for Endpoint capabilities and walk you through investigation experience.</span></span>


>[!NOTE]
><span data-ttu-id="3ea11-216">テスト デバイスへの接続は RDP を使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-216">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="3ea11-217">ファイアウォールの設定で RDP 接続が許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ea11-217">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="3ea11-218">Connectを選択して、デバイスにアクセスし、攻撃シミュレーション **をConnect。**</span><span class="sxs-lookup"><span data-stu-id="3ea11-218">Connect to your device and run an attack simulation by selecting **Connect**.</span></span> 

    ![テスト デバイスの接続ボタンのイメージ](images/test-machine-table.png)

2. <span data-ttu-id="3ea11-220">RDP ファイルを保存し、[開く] を選択して **起動Connect。**</span><span class="sxs-lookup"><span data-stu-id="3ea11-220">Save the RDP file and launch it by selecting **Connect**.</span></span>

    ![リモート デスクトップ接続のイメージ](images/remote-connection.png)

    >[!NOTE]
    ><span data-ttu-id="3ea11-222">初期セットアップ中に保存されたパスワードのコピーが存在しない場合は、メニューから [パスワードのリセット] を選択してパスワードをリセットできます。[パスワードのリセットの ![ イメージ]](images/reset-password-test-machine.png)</span><span class="sxs-lookup"><span data-stu-id="3ea11-222">If you don't have a copy of the password saved during the initial setup, you can reset the password by selecting **Reset password** from the menu: ![Image of reset password](images/reset-password-test-machine.png)</span></span><br>
    > <span data-ttu-id="3ea11-223">デバイスは状態を "パスワードリセットの実行" に変更し、数分で新しいパスワードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-223">The device will change it’s state to “Executing password reset", then you’ll be presented with your new password in a few minutes.</span></span>

3. <span data-ttu-id="3ea11-224">デバイスの作成手順中に表示されたパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="3ea11-224">Enter the password that was displayed during the device creation step.</span></span> 

   ![資格情報を入力するウィンドウのイメージ](images/enter-password.png)

4. <span data-ttu-id="3ea11-226">デバイスで Do-it-yourself 攻撃シミュレーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="3ea11-226">Run Do-it-yourself attack simulations on the device.</span></span> 


### <a name="threat-simulator-scenarios"></a><span data-ttu-id="3ea11-227">脅威シミュレーターのシナリオ</span><span class="sxs-lookup"><span data-stu-id="3ea11-227">Threat simulator scenarios</span></span>
<span data-ttu-id="3ea11-228">ラボのセットアップ中にサポートされている脅威シミュレーターのインストールを選択した場合は、評価ラボ デバイスで組み込みのシミュレーションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-228">If you chose to install any of the supported threat simulators during the lab setup, you can run the built-in simulations on the evaluation lab devices.</span></span> 


<span data-ttu-id="3ea11-229">サード パーティプラットフォームを使用して脅威シミュレーションを実行すると、ラボ環境の範囲内で Microsoft Defender for Endpoint の機能を評価できます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-229">Running threat simulations using third-party platforms is a good way to evaluate Microsoft Defender for Endpoint capabilities within the confines of a lab environment.</span></span>

>[!NOTE]
><span data-ttu-id="3ea11-230">シミュレーションを実行する前に、次の要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3ea11-230">Before you can run simulations, ensure the following requirements are met:</span></span>
>- <span data-ttu-id="3ea11-231">評価ラボにデバイスを追加する必要があります</span><span class="sxs-lookup"><span data-stu-id="3ea11-231">Devices must be added to the evaluation lab</span></span>
>- <span data-ttu-id="3ea11-232">脅威シミュレーターは評価ラボにインストールする必要があります</span><span class="sxs-lookup"><span data-stu-id="3ea11-232">Threat simulators must be installed in the evaluation lab</span></span>

1. <span data-ttu-id="3ea11-233">ポータルで [シミュレーションの作成 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3ea11-233">From the portal select **Create simulation**.</span></span>

2. <span data-ttu-id="3ea11-234">脅威シミュレーターを選択します。</span><span class="sxs-lookup"><span data-stu-id="3ea11-234">Select a threat simulator.</span></span>

    ![脅威シミュレーターの選択のイメージ](images/select-simulator.png)

3. <span data-ttu-id="3ea11-236">シミュレーションを選択するか、シミュレーション ギャラリーを参照して使用可能なシミュレーションを参照します。</span><span class="sxs-lookup"><span data-stu-id="3ea11-236">Choose a simulation or look through the simulation gallery to browse through the available simulations.</span></span> 

    <span data-ttu-id="3ea11-237">シミュレーション ギャラリーは、次の場所から取得できます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-237">You can get to the simulation gallery from:</span></span>
    - <span data-ttu-id="3ea11-238">シミュレーションの概要タイルの主 **な** 評価ダッシュボードまたは</span><span class="sxs-lookup"><span data-stu-id="3ea11-238">The main evaluation dashboard in the **Simulations overview** tile or</span></span>
    - <span data-ttu-id="3ea11-239">ナビゲーション ウィンドウの [評価] と **[チュートリアル]** から [シミュレーション] &をクリックし、[シミュレーション  >  カタログ]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3ea11-239">By navigating from the navigation pane **Evaluation and tutorials** > **Simulation & tutorials**, then select **Simulations catalog**.</span></span>

4. <span data-ttu-id="3ea11-240">シミュレーションを実行するデバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="3ea11-240">Select the devices where you'd like to run the simulation on.</span></span>

5. <span data-ttu-id="3ea11-241">[シミュレーション **の作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3ea11-241">Select **Create simulation**.</span></span>

6. <span data-ttu-id="3ea11-242">[シミュレーション] タブを選択して、シミュレーションの進行状況 **を表示** します。シミュレーションの状態、アクティブなアラート、その他の詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="3ea11-242">View the progress of a simulation by selecting the **Simulations** tab. View the simulation state, active alerts, and other details.</span></span> 

    ![[シミュレーションのイメージ] タブ](images/simulations-tab.png)
    
<span data-ttu-id="3ea11-244">シミュレーションを実行した後、ラボの進行状況バーを表示し **、Microsoft Defender for Endpoint** を調べ、自動調査と修復をトリガーしてください。</span><span class="sxs-lookup"><span data-stu-id="3ea11-244">After running your simulations, we encourage you to walk through the lab progress bar and explore **Microsoft Defender for Endpoint triggered an automated investigation and remediation**.</span></span> <span data-ttu-id="3ea11-245">機能によって収集および分析された証拠を確認します。</span><span class="sxs-lookup"><span data-stu-id="3ea11-245">Check out the evidence collected and analyzed by the feature.</span></span>

<span data-ttu-id="3ea11-246">豊富なクエリ言語と生の利用統計情報を使用して高度な検索を通じて攻撃証拠を探し、Threat analytics に記載されている世界全体の脅威を確認します。</span><span class="sxs-lookup"><span data-stu-id="3ea11-246">Hunt for attack evidence through advanced hunting by using the rich query language and raw telemetry and check out some world-wide threats documented in Threat analytics.</span></span>


## <a name="simulation-gallery"></a><span data-ttu-id="3ea11-247">シミュレーション ギャラリー</span><span class="sxs-lookup"><span data-stu-id="3ea11-247">Simulation gallery</span></span>
<span data-ttu-id="3ea11-248">Microsoft Defender for Endpoint は、さまざまな脅威シミュレーション プラットフォームと提携し、ポータル内からプラットフォームの機能を簡単にテストできます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-248">Microsoft Defender for Endpoint has partnered with various threat simulation platforms to give you convenient access to test the capabilities of the platform right from the within the portal.</span></span> 

<span data-ttu-id="3ea11-249">メニューから [シミュレーションとチュートリアル]**シミュレーション** カタログに移動して、使用可能なすべての  >  **シミュレーション** を表示します。</span><span class="sxs-lookup"><span data-stu-id="3ea11-249">View all the available simulations by going to  **Simulations and tutorials** > **Simulations catalog**  from the menu.</span></span> 

<span data-ttu-id="3ea11-250">サポートされているサードパーティの脅威シミュレーション エージェントの一覧が一覧表示され、特定の種類のシミュレーションと詳細な説明がカタログに記載されています。</span><span class="sxs-lookup"><span data-stu-id="3ea11-250">A list of supported third-party threat simulation agents are listed, and specific types of simulations along with detailed descriptions are provided on the catalog.</span></span> 

<span data-ttu-id="3ea11-251">カタログから任意の使用可能なシミュレーションを簡単に実行できます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-251">You can conveniently run any available simulation right from the catalog.</span></span>  


![シミュレーション カタログのイメージ](images/simulations-catalog.png)

<span data-ttu-id="3ea11-253">各シミュレーションには、攻撃シナリオの詳細な説明と、使用する MITRE 攻撃手法や実行する高度な検索クエリのサンプルなどの参照が付属しています。</span><span class="sxs-lookup"><span data-stu-id="3ea11-253">Each simulation comes with an in-depth description of the attack scenario and references such as the MITRE attack techniques used and sample Advanced hunting queries you run.</span></span>

<span data-ttu-id="3ea11-254">**例:** 
 ![シミュレーションの説明の詳細の画像1](images/simulation-details-aiq.png)</span><span class="sxs-lookup"><span data-stu-id="3ea11-254">**Examples:**
![Image of simulation description details1](images/simulation-details-aiq.png)</span></span>


![シミュレーションの説明の詳細の画像2](images/simulation-details-sb.png)


## <a name="evaluation-report"></a><span data-ttu-id="3ea11-256">評価レポート</span><span class="sxs-lookup"><span data-stu-id="3ea11-256">Evaluation report</span></span>
<span data-ttu-id="3ea11-257">ラボ レポートは、デバイスで実施されたシミュレーションの結果を要約します。</span><span class="sxs-lookup"><span data-stu-id="3ea11-257">The lab reports summarize the results of the simulations conducted on the devices.</span></span>

![評価レポートのイメージ](images/eval-report.png)

<span data-ttu-id="3ea11-259">一目でわかると、次の情報をすばやく確認できます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-259">At a glance, you'll quickly be able to see:</span></span>
- <span data-ttu-id="3ea11-260">トリガーされたインシデント</span><span class="sxs-lookup"><span data-stu-id="3ea11-260">Incidents that were triggered</span></span>
- <span data-ttu-id="3ea11-261">生成されたアラート</span><span class="sxs-lookup"><span data-stu-id="3ea11-261">Generated alerts</span></span>
- <span data-ttu-id="3ea11-262">露出レベルの評価</span><span class="sxs-lookup"><span data-stu-id="3ea11-262">Assessments on exposure level</span></span> 
- <span data-ttu-id="3ea11-263">検出された脅威カテゴリ</span><span class="sxs-lookup"><span data-stu-id="3ea11-263">Threat categories observed</span></span>
- <span data-ttu-id="3ea11-264">検出ソース</span><span class="sxs-lookup"><span data-stu-id="3ea11-264">Detection sources</span></span>
- <span data-ttu-id="3ea11-265">自動化された調査</span><span class="sxs-lookup"><span data-stu-id="3ea11-265">Automated investigations</span></span>


## <a name="provide-feedback"></a><span data-ttu-id="3ea11-266">フィードバックの提供</span><span class="sxs-lookup"><span data-stu-id="3ea11-266">Provide feedback</span></span>
<span data-ttu-id="3ea11-267">フィードバックは、高度な攻撃から環境を保護する上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3ea11-267">Your feedback helps us get better in protecting your environment from advanced attacks.</span></span> <span data-ttu-id="3ea11-268">製品の機能と評価結果からエクスペリエンスとインプレッションを共有します。</span><span class="sxs-lookup"><span data-stu-id="3ea11-268">Share your experience and impressions from product capabilities and evaluation results.</span></span>

<span data-ttu-id="3ea11-269">[フィードバックの提供] を選択して、ご意見 **をお寄せください**。</span><span class="sxs-lookup"><span data-stu-id="3ea11-269">Let us know what you think, by selecting **Provide feedback**.</span></span>

![フィードバックを提供するイメージ](images/send-us-feedback-eval-lab.png)
