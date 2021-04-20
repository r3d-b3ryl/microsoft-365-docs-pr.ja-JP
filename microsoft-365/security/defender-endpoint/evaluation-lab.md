---
title: Microsoft Defender for Endpoint 評価ラボ
description: Microsoft Defender for Endpoint の機能について説明し、攻撃シミュレーションを実行し、脅威を防止、検出、修復する方法を確認します。
keywords: mdatp、評価、ラボ、シミュレーション、Windows 10、Windows Server 2019、評価ラボを評価する
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
ms.openlocfilehash: 2382281fbb975daa18ec21aabaf5acf8d3fbfb2f
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893439"
---
# <a name="microsoft-defender-for-endpoint-evaluation-lab"></a><span data-ttu-id="17f74-104">Microsoft Defender for Endpoint 評価ラボ</span><span class="sxs-lookup"><span data-stu-id="17f74-104">Microsoft Defender for Endpoint evaluation lab</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="17f74-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="17f74-105">**Applies to:**</span></span>
- [<span data-ttu-id="17f74-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="17f74-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="17f74-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="17f74-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="17f74-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="17f74-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="17f74-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="17f74-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


<span data-ttu-id="17f74-110">包括的なセキュリティ製品評価を行う場合、エンドツーエンドの攻撃シミュレーションを実際に実行する前に、複雑な環境とデバイス構成が必要になる複雑なプロセスになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="17f74-110">Conducting a comprehensive security product evaluation can be a complex process requiring cumbersome environment and device configuration before an end-to-end attack simulation can actually be done.</span></span> <span data-ttu-id="17f74-111">複雑さを加えるのは、シミュレーション アクティビティ、アラート、および結果が評価中に反映される場所を追跡する際の課題です。</span><span class="sxs-lookup"><span data-stu-id="17f74-111">Adding to the complexity is the challenge of tracking where the simulation activities, alerts, and results are reflected during the evaluation.</span></span>

<span data-ttu-id="17f74-112">Microsoft Defender for Endpoint 評価ラボは、プラットフォームの機能の評価、シミュレーションの実行、予防、検出、修復機能の実行に集中できるよう、デバイスと環境構成の複雑さを排除するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="17f74-112">The Microsoft Defender for Endpoint evaluation lab is designed to eliminate the complexities of device and environment configuration so that you can  focus on evaluating the capabilities of the platform, running simulations, and seeing the prevention, detection, and remediation features in action.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUM]

<span data-ttu-id="17f74-113">セットアップの簡略化により、独自のテスト シナリオと事前に作成されたシミュレーションの実行に集中して、Defender for Endpoint のパフォーマンスを確認できます。</span><span class="sxs-lookup"><span data-stu-id="17f74-113">With the simplified set-up experience, you can focus on running your own test scenarios and the pre-made simulations to see how Defender for Endpoint performs.</span></span> 

<span data-ttu-id="17f74-114">自動調査、高度な狩猟、脅威分析など、プラットフォームの強力な機能に完全にアクセスでき、Defender for Endpoint が提供する包括的な保護スタックをテストできます。</span><span class="sxs-lookup"><span data-stu-id="17f74-114">You'll have full access to the powerful capabilities of the platform such as automated investigations, advanced hunting, and threat analytics, allowing you to test the comprehensive protection stack that Defender for Endpoint offers.</span></span> 

<span data-ttu-id="17f74-115">最新の OS バージョンと適切なセキュリティ コンポーネント、および Office 2019 Standard をインストールするように事前構成された Windows 10 または Windows Server 2019 デバイスを追加できます。</span><span class="sxs-lookup"><span data-stu-id="17f74-115">You can add Windows 10 or Windows Server 2019 devices that come pre-configured to have the latest OS versions and the right security components in place as well as Office 2019 Standard installed.</span></span>

<span data-ttu-id="17f74-116">また、脅威シミュレーターをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="17f74-116">You can also install threat simulators.</span></span> <span data-ttu-id="17f74-117">Defender for Endpoint は、業界をリードする脅威シミュレーション プラットフォームと提携し、ポータルから出ることなく Defender for Endpoint の機能をテストするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="17f74-117">Defender for Endpoint has partnered with industry leading threat simulation platforms to help you test out the Defender for Endpoint capabilities without having to leave the portal.</span></span>

 <span data-ttu-id="17f74-118">お好みのシミュレーターをインストールし、評価ラボ内でシナリオを実行し、プラットフォームのパフォーマンスを即座に確認できます。</span><span class="sxs-lookup"><span data-stu-id="17f74-118">Install your preferred simulator, run scenarios within the evaluation lab, and instantly see how the platform performs - all conveniently available at no extra cost to you.</span></span> <span data-ttu-id="17f74-119">また、さまざまなシミュレーションにアクセスして、シミュレーション カタログから実行できます。</span><span class="sxs-lookup"><span data-stu-id="17f74-119">You'll also have convenient access to wide array of simulations which you can access and run from the simulations catalog.</span></span>
    

## <a name="before-you-begin"></a><span data-ttu-id="17f74-120">開始する前に</span><span class="sxs-lookup"><span data-stu-id="17f74-120">Before you begin</span></span>
<span data-ttu-id="17f74-121">評価ラボにアクセスするには、ライセンス[](minimum-requirements.md#licensing-requirements)要件を満たすか、Microsoft Defender for Endpoint への試用版アクセス権が必要です。</span><span class="sxs-lookup"><span data-stu-id="17f74-121">You'll need to fulfill the [licensing requirements](minimum-requirements.md#licensing-requirements) or have trial access to Microsoft Defender for Endpoint to access the evaluation lab.</span></span>

<span data-ttu-id="17f74-122">次のセキュリティ設定 **の管理権限** が必要です。</span><span class="sxs-lookup"><span data-stu-id="17f74-122">You must have **Manage security settings** permissions to:</span></span>
- <span data-ttu-id="17f74-123">ラボを作成する</span><span class="sxs-lookup"><span data-stu-id="17f74-123">Create the lab</span></span>
- <span data-ttu-id="17f74-124">デバイスの作成</span><span class="sxs-lookup"><span data-stu-id="17f74-124">Create devices</span></span>
- <span data-ttu-id="17f74-125">パスワードのリセット</span><span class="sxs-lookup"><span data-stu-id="17f74-125">Reset password</span></span>
- <span data-ttu-id="17f74-126">シミュレーションの作成</span><span class="sxs-lookup"><span data-stu-id="17f74-126">Create simulations</span></span> 
 
<span data-ttu-id="17f74-127">役割ベースのアクセス制御 (RBAC) を有効にし、少なくとも 1 つのコンピューター グループを作成した場合、ユーザーはすべてのコンピューター グループにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="17f74-127">If you enabled role-based access control (RBAC) and created at least a one machine group, users must have access to All machine groups.</span></span>

<span data-ttu-id="17f74-128">詳細については、「役割の作成 [と管理」を参照してください](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="17f74-128">For more information, see [Create and manage roles](user-roles.md).</span></span>

<span data-ttu-id="17f74-129">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="17f74-129">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="17f74-130">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="17f74-130">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink)


## <a name="get-started-with-the-lab"></a><span data-ttu-id="17f74-131">ラボの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="17f74-131">Get started with the lab</span></span>
<span data-ttu-id="17f74-132">メニューからラボにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="17f74-132">You can access the lab from the menu.</span></span> <span data-ttu-id="17f74-133">ナビゲーション メニューで、[評価] と **[チュートリアル] を選択し、[>] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="17f74-133">In the navigation menu, select **Evaluation and tutorials > Evaluation lab**.</span></span>

![メニューの評価ラボのイメージ](images/evaluation-lab-menu.png)

>[!NOTE]
>- <span data-ttu-id="17f74-135">選択した環境構造の種類に応じて、デバイスはライセンス認証日から指定された時間数で利用できます。</span><span class="sxs-lookup"><span data-stu-id="17f74-135">Depending the type of environment structure you select, devices will be available for the specified number of hours from the day of activation.</span></span>
>- <span data-ttu-id="17f74-136">各環境は、制限された一連のテスト デバイスでプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="17f74-136">Each environment is provisioned with a limited set of test devices.</span></span> <span data-ttu-id="17f74-137">プロビジョニングされたデバイスを使いきった場合、新しいデバイスは提供されません。</span><span class="sxs-lookup"><span data-stu-id="17f74-137">When you've used up the provisioned devices, no new devices are provided.</span></span> <span data-ttu-id="17f74-138">削除されたデバイスでは、使用可能なテスト デバイスの数は更新されません。</span><span class="sxs-lookup"><span data-stu-id="17f74-138">A deleted device does not refresh the available test device count.</span></span>
>- <span data-ttu-id="17f74-139">リソースが使いきりになったときにラボを使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="17f74-139">You can no longer use the lab when the resources have been used up.</span></span> <span data-ttu-id="17f74-140">リセットも更新もされません。</span><span class="sxs-lookup"><span data-stu-id="17f74-140">It does not reset nor refresh.</span></span>
>- <span data-ttu-id="17f74-141">リソースは慎重に使用してください。ラボ のリソースは制限されています。</span><span class="sxs-lookup"><span data-stu-id="17f74-141">It is advisable to use the resources carefully.The lab resources are limited.</span></span> <span data-ttu-id="17f74-142">リセットも更新もされません。</span><span class="sxs-lookup"><span data-stu-id="17f74-142">They will not reset nor refresh.</span></span> 

<span data-ttu-id="17f74-143">ラボを既に持っていますか?</span><span class="sxs-lookup"><span data-stu-id="17f74-143">Already have a lab?</span></span> <span data-ttu-id="17f74-144">新しい脅威シミュレーターを有効にし、アクティブなデバイスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="17f74-144">Make sure to enable the new threat simulators and have active devices.</span></span>

## <a name="setup-the-evaluation-lab"></a><span data-ttu-id="17f74-145">評価ラボのセットアップ</span><span class="sxs-lookup"><span data-stu-id="17f74-145">Setup the evaluation lab</span></span>

1. <span data-ttu-id="17f74-146">ナビゲーション ウィンドウで、[評価とチュートリアル]**評価** ラボを  >  **選択** し、[セットアップ ラボ]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="17f74-146">In the navigation pane, select **Evaluation and tutorials** > **Evaluation lab**, then select **Setup lab**.</span></span>

    ![評価ラボのウェルカム ページのイメージ](images/evaluation-lab-setup.png)

2. <span data-ttu-id="17f74-148">評価のニーズに応じて、より長い期間、またはより短い期間のデバイスが少ない環境をセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="17f74-148">Depending on your evaluation needs, you can choose to setup an environment with fewer devices for a longer period or more devices for a shorter period.</span></span> <span data-ttu-id="17f74-149">好みのラボ構成を選択し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="17f74-149">Select your preferred lab configuration then select **Next**.</span></span>

    ![ラボ構成オプションのイメージ](images/lab-creation-page.png) 


3. <span data-ttu-id="17f74-151">(省略可能)ラボに脅威シミュレーターをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="17f74-151">(Optional) You can choose to install threat simulators in the lab.</span></span> 

    ![インストール シミュレーター エージェントのイメージ](images/install-agent.png)

    >[!IMPORTANT]
    ><span data-ttu-id="17f74-153">最初に、条項と情報共有に関する声明に同意し、同意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17f74-153">You'll first need to accept and provide consent to the terms and information sharing statements.</span></span> 

4. <span data-ttu-id="17f74-154">使用する脅威シミュレーション エージェントを選択し、詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="17f74-154">Select the threat simulation agent you'd like to use and enter your details.</span></span> <span data-ttu-id="17f74-155">また、後で脅威シミュレーターをインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="17f74-155">You can also choose to install threat simulators at a later time.</span></span> <span data-ttu-id="17f74-156">ラボのセットアップ中に脅威シミュレーション エージェントをインストールする場合は、追加するデバイスに脅威シミュレーション エージェントを簡単にインストールできます。</span><span class="sxs-lookup"><span data-stu-id="17f74-156">If you choose to install threat simulation agents during the lab setup, you'll enjoy the benefit of having them conveniently installed on the devices you add.</span></span>  
    
    ![概要ページの画像](images/lab-setup-summary.png)

5.  <span data-ttu-id="17f74-158">概要を確認し、[セットアップ ラボ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="17f74-158">Review the summary and select **Setup lab**.</span></span>  

<span data-ttu-id="17f74-159">ラボのセットアップ プロセスが完了したら、デバイスを追加してシミュレーションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="17f74-159">After the lab setup process is complete, you can add devices and run simulations.</span></span> 


## <a name="add-devices"></a><span data-ttu-id="17f74-160">デバイスの追加</span><span class="sxs-lookup"><span data-stu-id="17f74-160">Add devices</span></span>
<span data-ttu-id="17f74-161">環境にデバイスを追加すると、Defender for Endpoint は接続の詳細を示す構成済みのデバイスをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="17f74-161">When you add a device to your environment, Defender for Endpoint sets up a well-configured device with connection details.</span></span> <span data-ttu-id="17f74-162">Windows 10 または Windows Server 2019 デバイスを追加できます。</span><span class="sxs-lookup"><span data-stu-id="17f74-162">You can add Windows 10 or Windows Server 2019 devices.</span></span>

<span data-ttu-id="17f74-163">デバイスは、OS および Office 2019 Standard の最新バージョンと、Java、Python、SysIntenals などの他のアプリで構成されます。</span><span class="sxs-lookup"><span data-stu-id="17f74-163">The device will be configured with the most up-to-date version of the OS and Office 2019 Standard as well as other apps such as Java, Python, and SysIntenals.</span></span> 

   >[!TIP]
   > <span data-ttu-id="17f74-164">ラボに追加のデバイスが必要ですか?</span><span class="sxs-lookup"><span data-stu-id="17f74-164">Need more devices in your lab?</span></span> <span data-ttu-id="17f74-165">サポート チケットを提出して、Defender for Endpoint チームが要求を確認します。</span><span class="sxs-lookup"><span data-stu-id="17f74-165">Submit a support ticket to have your request reviewed by the Defender for Endpoint team.</span></span> 

<span data-ttu-id="17f74-166">ラボのセットアップ中に脅威シミュレーターの追加を選択した場合、すべてのデバイスに追加するデバイスに脅威シミュレーター エージェントがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="17f74-166">If you chose to add a threat simulator during the lab setup, all devices will have the threat simulator agent installed in the devices that you add.</span></span>

<span data-ttu-id="17f74-167">デバイスは、推奨される Windows セキュリティ コンポーネントをオンにし、監査モードでテナントに自動的にオンボードされます。作業は不要です。</span><span class="sxs-lookup"><span data-stu-id="17f74-167">The device will automatically be onboarded to your tenant with the recommended Windows security components turned on and in audit mode - with no effort on your side.</span></span> 

<span data-ttu-id="17f74-168">次のセキュリティ コンポーネントは、テスト デバイスで事前に構成されています。</span><span class="sxs-lookup"><span data-stu-id="17f74-168">The following security components are pre-configured in the test devices:</span></span>

- [<span data-ttu-id="17f74-169">攻撃面の減少</span><span class="sxs-lookup"><span data-stu-id="17f74-169">Attack surface reduction</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard)
- [<span data-ttu-id="17f74-170">一目でブロックする</span><span class="sxs-lookup"><span data-stu-id="17f74-170">Block at first sight</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)
- [<span data-ttu-id="17f74-171">制御されたフォルダー アクセス</span><span class="sxs-lookup"><span data-stu-id="17f74-171">Controlled folder access</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)
- [<span data-ttu-id="17f74-172">エクスプロイト保護</span><span class="sxs-lookup"><span data-stu-id="17f74-172">Exploit protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/enable-exploit-protection)
- [<span data-ttu-id="17f74-173">ネットワーク保護</span><span class="sxs-lookup"><span data-stu-id="17f74-173">Network protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
- [<span data-ttu-id="17f74-174">望ましくない可能性のあるアプリケーションの検出</span><span class="sxs-lookup"><span data-stu-id="17f74-174">Potentially unwanted application detection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [<span data-ttu-id="17f74-175">クラウドによる保護</span><span class="sxs-lookup"><span data-stu-id="17f74-175">Cloud-delivered protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [<span data-ttu-id="17f74-176">Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="17f74-176">Microsoft Defender SmartScreen</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview)

>[!NOTE]
> <span data-ttu-id="17f74-177">Microsoft Defender ウイルス対策はオンになります (監査モードではありません)。</span><span class="sxs-lookup"><span data-stu-id="17f74-177">Microsoft Defender Antivirus will be on (not in audit mode).</span></span> <span data-ttu-id="17f74-178">Microsoft Defender Antivirus でシミュレーションの実行がブロックされている場合は、Windows セキュリティを使用してデバイスのリアルタイム保護を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="17f74-178">If Microsoft Defender Antivirus blocks you from running your simulation, you can turn off real-time protection on the device through Windows Security.</span></span> <span data-ttu-id="17f74-179">詳細については、「Configure [always-on protection」を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="17f74-179">For more information, see [Configure always-on protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="17f74-180">自動調査の設定は、テナントの設定に依存します。</span><span class="sxs-lookup"><span data-stu-id="17f74-180">Automated investigation settings will be dependent on tenant settings.</span></span> <span data-ttu-id="17f74-181">既定では半自動で構成されます。</span><span class="sxs-lookup"><span data-stu-id="17f74-181">It will be configured to be semi-automated by default.</span></span> <span data-ttu-id="17f74-182">詳細については、「自動調査 [の概要」を参照してください](automated-investigations.md)。</span><span class="sxs-lookup"><span data-stu-id="17f74-182">For more information, see [Overview of Automated investigations](automated-investigations.md).</span></span>

>[!NOTE]
><span data-ttu-id="17f74-183">テスト デバイスへの接続は RDP を使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="17f74-183">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="17f74-184">ファイアウォールの設定で RDP 接続が許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="17f74-184">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="17f74-185">ダッシュボードで、[デバイスの追加 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="17f74-185">From the dashboard, select **Add device**.</span></span> 

2. <span data-ttu-id="17f74-186">追加するデバイスの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="17f74-186">Choose the type of device to add.</span></span> <span data-ttu-id="17f74-187">Windows 10 または Windows Server 2019 の追加を選択できます。</span><span class="sxs-lookup"><span data-stu-id="17f74-187">You can choose to add Windows 10 or Windows Server 2019.</span></span>

    ![デバイス オプションを使用したラボセットアップのイメージ](images/add-machine-options.png)


    >[!NOTE]
    ><span data-ttu-id="17f74-189">デバイスの作成プロセスで問題が発生した場合は、通知が送信され、新しい要求を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17f74-189">If something goes wrong with the device creation process, you'll be notified and you'll need to submit a new request.</span></span> <span data-ttu-id="17f74-190">デバイスの作成に失敗した場合は、許可された全体的なクォータに対してカウントされません。</span><span class="sxs-lookup"><span data-stu-id="17f74-190">If the device creation fails, it will not be counted against the overall allowed quota.</span></span> 

3. <span data-ttu-id="17f74-191">接続の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="17f74-191">The connection details are displayed.</span></span> <span data-ttu-id="17f74-192">[ **コピー] を** 選択して、デバイスのパスワードを保存します。</span><span class="sxs-lookup"><span data-stu-id="17f74-192">Select **Copy** to save the password for the device.</span></span>

    >[!NOTE]
    ><span data-ttu-id="17f74-193">パスワードは 1 回だけ表示されます。</span><span class="sxs-lookup"><span data-stu-id="17f74-193">The password is only displayed once.</span></span> <span data-ttu-id="17f74-194">後で使用するために必ず保存してください。</span><span class="sxs-lookup"><span data-stu-id="17f74-194">Be sure to save it for later use.</span></span>

    ![接続の詳細で追加されたデバイスのイメージ](images/add-machine-eval-lab.png)

4. <span data-ttu-id="17f74-196">デバイスのセットアップが開始されます。</span><span class="sxs-lookup"><span data-stu-id="17f74-196">Device set up begins.</span></span> <span data-ttu-id="17f74-197">これには、最大で約 30 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="17f74-197">This can take up to approximately 30 minutes.</span></span> 

5. <span data-ttu-id="17f74-198">[デバイス] タブを選択して、テスト デバイスの状態、リスクと露出レベル、シミュレーターのインストールの状態 **を確認** します。</span><span class="sxs-lookup"><span data-stu-id="17f74-198">See the status of test devices, the risk and exposure levels, and the status of simulator installations by selecting the **Devices** tab.</span></span> 

    ![[デバイスのイメージ] タブ](images/machines-tab.png)
    

    >[!TIP]
    ><span data-ttu-id="17f74-200">[ **シミュレーターの状態]** 列で、情報アイコンにカーソルを合わせると、エージェントのインストール状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="17f74-200">In the **Simulator status** column, you can hover over the information icon to know the installation status of an agent.</span></span>



## <a name="simulate-attack-scenarios"></a><span data-ttu-id="17f74-201">攻撃シナリオのシミュレーション</span><span class="sxs-lookup"><span data-stu-id="17f74-201">Simulate attack scenarios</span></span>
<span data-ttu-id="17f74-202">テスト デバイスを使用して、テスト デバイスに接続して独自の攻撃シミュレーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="17f74-202">Use the test devices to run your own attack simulations by connecting to them.</span></span> 

<span data-ttu-id="17f74-203">攻撃シナリオは、次の方法でシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="17f74-203">You can simulate attack scenarios using:</span></span>
- <span data-ttu-id="17f74-204">["Do It Yourself" 攻撃のシナリオ](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="17f74-204">The ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials)</span></span>
- <span data-ttu-id="17f74-205">脅威シミュレーター</span><span class="sxs-lookup"><span data-stu-id="17f74-205">Threat simulators</span></span>

<span data-ttu-id="17f74-206">高度な検索を使用[してデータ](advanced-hunting-query-language.md)をクエリし[](threat-analytics.md)、脅威分析を使用して、新たな脅威に関するレポートを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="17f74-206">You can also use [Advanced hunting](advanced-hunting-query-language.md) to query data and [Threat analytics](threat-analytics.md) to view reports about emerging threats.</span></span>

### <a name="do-it-yourself-attack-scenarios"></a><span data-ttu-id="17f74-207">Do-it-yourself 攻撃のシナリオ</span><span class="sxs-lookup"><span data-stu-id="17f74-207">Do-it-yourself attack scenarios</span></span>
<span data-ttu-id="17f74-208">事前に作成されたシミュレーションを探している場合は、"Do It [Yourself" 攻撃シナリオを使用できます](https://securitycenter.windows.com/tutorials)。</span><span class="sxs-lookup"><span data-stu-id="17f74-208">If you are looking for a pre-made simulation, you can use our ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials).</span></span> <span data-ttu-id="17f74-209">これらのスクリプトは安全で文書化され、使いやすいです。</span><span class="sxs-lookup"><span data-stu-id="17f74-209">These scripts are safe, documented, and easy to use.</span></span> <span data-ttu-id="17f74-210">これらのシナリオは、Defender for Endpoint の機能を反映し、調査のエクスペリエンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="17f74-210">These scenarios will reflect Defender for Endpoint capabilities and walk you through investigation experience.</span></span>


>[!NOTE]
><span data-ttu-id="17f74-211">テスト デバイスへの接続は RDP を使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="17f74-211">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="17f74-212">ファイアウォールの設定で RDP 接続が許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="17f74-212">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="17f74-213">[接続] を選択して、デバイスに接続し、攻撃シミュレーションを **実行します**。</span><span class="sxs-lookup"><span data-stu-id="17f74-213">Connect to your device and run an attack simulation by selecting **Connect**.</span></span> 

    ![テスト デバイスの接続ボタンのイメージ](images/test-machine-table.png)

2. <span data-ttu-id="17f74-215">RDP ファイルを保存し、[接続] を選択して起動 **します**。</span><span class="sxs-lookup"><span data-stu-id="17f74-215">Save the RDP file and launch it by selecting **Connect**.</span></span>

    ![リモート デスクトップ接続のイメージ](images/remote-connection.png)

    >[!NOTE]
    ><span data-ttu-id="17f74-217">初期セットアップ中に保存されたパスワードのコピーが存在しない場合は、メニューから [パスワードのリセット] を選択してパスワードをリセットできます。[パスワードのリセットの ![ イメージ]](images/reset-password-test-machine.png)</span><span class="sxs-lookup"><span data-stu-id="17f74-217">If you don't have a copy of the password saved during the initial setup, you can reset the password by selecting **Reset password** from the menu: ![Image of reset password](images/reset-password-test-machine.png)</span></span><br>
    > <span data-ttu-id="17f74-218">デバイスは状態を "パスワードリセットの実行" に変更し、数分で新しいパスワードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="17f74-218">The device will change it’s state to “Executing password reset", then you’ll be presented with your new password in a few minutes.</span></span>

3. <span data-ttu-id="17f74-219">デバイスの作成手順中に表示されたパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="17f74-219">Enter the password that was displayed during the device creation step.</span></span> 

   ![資格情報を入力するウィンドウのイメージ](images/enter-password.png)

4. <span data-ttu-id="17f74-221">デバイスで Do-it-yourself 攻撃シミュレーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="17f74-221">Run Do-it-yourself attack simulations on the device.</span></span> 


### <a name="threat-simulator-scenarios"></a><span data-ttu-id="17f74-222">脅威シミュレーターのシナリオ</span><span class="sxs-lookup"><span data-stu-id="17f74-222">Threat simulator scenarios</span></span>
<span data-ttu-id="17f74-223">ラボのセットアップ中にサポートされている脅威シミュレーターのインストールを選択した場合は、評価ラボ デバイスで組み込みのシミュレーションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="17f74-223">If you chose to install any of the supported threat simulators during the lab setup, you can run the built-in simulations on the evaluation lab devices.</span></span> 


<span data-ttu-id="17f74-224">サード パーティプラットフォームを使用して脅威シミュレーションを実行すると、ラボ環境の範囲内で Microsoft Defender for Endpoint の機能を評価できます。</span><span class="sxs-lookup"><span data-stu-id="17f74-224">Running threat simulations using third-party platforms is a good way to evaluate Microsoft Defender for Endpoint capabilities within the confines of a lab environment.</span></span>

>[!NOTE]
><span data-ttu-id="17f74-225">シミュレーションを実行する前に、次の要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="17f74-225">Before you can run simulations, ensure the following requirements are met:</span></span>
>- <span data-ttu-id="17f74-226">評価ラボにデバイスを追加する必要があります</span><span class="sxs-lookup"><span data-stu-id="17f74-226">Devices must be added to the evaluation lab</span></span>
>- <span data-ttu-id="17f74-227">脅威シミュレーターは評価ラボにインストールする必要があります</span><span class="sxs-lookup"><span data-stu-id="17f74-227">Threat simulators must be installed in the evaluation lab</span></span>

1. <span data-ttu-id="17f74-228">ポータルで [シミュレーションの作成 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="17f74-228">From the portal select **Create simulation**.</span></span>

2. <span data-ttu-id="17f74-229">脅威シミュレーターを選択します。</span><span class="sxs-lookup"><span data-stu-id="17f74-229">Select a threat simulator.</span></span>

    ![脅威シミュレーターの選択のイメージ](images/select-simulator.png)

3. <span data-ttu-id="17f74-231">シミュレーションを選択するか、シミュレーション ギャラリーを参照して使用可能なシミュレーションを参照します。</span><span class="sxs-lookup"><span data-stu-id="17f74-231">Choose a simulation or look through the simulation gallery to browse through the available simulations.</span></span> 

    <span data-ttu-id="17f74-232">シミュレーション ギャラリーは、次の場所から取得できます。</span><span class="sxs-lookup"><span data-stu-id="17f74-232">You can get to the simulation gallery from:</span></span>
    - <span data-ttu-id="17f74-233">シミュレーションの概要タイルの主 **な** 評価ダッシュボードまたは</span><span class="sxs-lookup"><span data-stu-id="17f74-233">The main evaluation dashboard in the **Simulations overview** tile or</span></span>
    - <span data-ttu-id="17f74-234">ナビゲーション ウィンドウの [評価] と **[チュートリアル]** から [シミュレーション] &をクリックし、[シミュレーション  >  カタログ]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="17f74-234">By navigating from the navigation pane **Evaluation and tutorials** > **Simulation & tutorials**, then select **Simulations catalog**.</span></span>

4. <span data-ttu-id="17f74-235">シミュレーションを実行するデバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="17f74-235">Select the devices where you'd like to run the simulation on.</span></span>

5. <span data-ttu-id="17f74-236">[シミュレーション **の作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="17f74-236">Select **Create simulation**.</span></span>

6. <span data-ttu-id="17f74-237">[シミュレーション] タブを選択して、シミュレーションの進行状況 **を表示** します。シミュレーションの状態、アクティブなアラート、その他の詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="17f74-237">View the progress of a simulation by selecting the **Simulations** tab. View the simulation state, active alerts, and other details.</span></span> 

    ![[シミュレーションのイメージ] タブ](images/simulations-tab.png)
    
<span data-ttu-id="17f74-239">シミュレーションを実行した後、ラボの進行状況バーを表示し **、Microsoft Defender for Endpoint** を調べ、自動調査と修復をトリガーしてください。</span><span class="sxs-lookup"><span data-stu-id="17f74-239">After running your simulations, we encourage you to walk through the lab progress bar and explore **Microsoft Defender for Endpoint triggered an automated investigation and remediation**.</span></span> <span data-ttu-id="17f74-240">機能によって収集および分析された証拠を確認します。</span><span class="sxs-lookup"><span data-stu-id="17f74-240">Check out the evidence collected and analyzed by the feature.</span></span>

<span data-ttu-id="17f74-241">豊富なクエリ言語と生の利用統計情報を使用して高度な検索を通じて攻撃証拠を探し、Threat analytics に記載されている世界全体の脅威を確認します。</span><span class="sxs-lookup"><span data-stu-id="17f74-241">Hunt for attack evidence through advanced hunting by using the rich query language and raw telemetry and check out some world-wide threats documented in Threat analytics.</span></span>


## <a name="simulation-gallery"></a><span data-ttu-id="17f74-242">シミュレーション ギャラリー</span><span class="sxs-lookup"><span data-stu-id="17f74-242">Simulation gallery</span></span>
<span data-ttu-id="17f74-243">Microsoft Defender for Endpoint は、さまざまな脅威シミュレーション プラットフォームと提携し、ポータル内からプラットフォームの機能を簡単にテストできます。</span><span class="sxs-lookup"><span data-stu-id="17f74-243">Microsoft Defender for Endpoint has partnered with various threat simulation platforms to give you convenient access to test the capabilities of the platform right from the within the portal.</span></span> 

<span data-ttu-id="17f74-244">メニューから [シミュレーションとチュートリアル]**シミュレーション** カタログに移動して、使用可能なすべての  >  **シミュレーション** を表示します。</span><span class="sxs-lookup"><span data-stu-id="17f74-244">View all the available simulations by going to  **Simulations and tutorials** > **Simulations catalog**  from the menu.</span></span> 

<span data-ttu-id="17f74-245">サポートされているサードパーティの脅威シミュレーション エージェントの一覧が一覧表示され、特定の種類のシミュレーションと詳細な説明がカタログに記載されています。</span><span class="sxs-lookup"><span data-stu-id="17f74-245">A list of supported third-party threat simulation agents are listed, and specific types of simulations along with detailed descriptions are provided on the catalog.</span></span> 

<span data-ttu-id="17f74-246">カタログから任意の使用可能なシミュレーションを簡単に実行できます。</span><span class="sxs-lookup"><span data-stu-id="17f74-246">You can conveniently run any available simulation right from the catalog.</span></span>  


![シミュレーション カタログのイメージ](images/simulations-catalog.png)

<span data-ttu-id="17f74-248">各シミュレーションには、攻撃シナリオの詳細な説明と、使用する MITRE 攻撃手法や実行する高度な検索クエリのサンプルなどの参照が付属しています。</span><span class="sxs-lookup"><span data-stu-id="17f74-248">Each simulation comes with an in-depth description of the attack scenario and references such as the MITRE attack techniques used and sample Advanced hunting queries you run.</span></span>

<span data-ttu-id="17f74-249">**例:** 
 ![シミュレーションの説明の詳細の画像1](images/simulation-details-aiq.png)</span><span class="sxs-lookup"><span data-stu-id="17f74-249">**Examples:**
![Image of simulation description details1](images/simulation-details-aiq.png)</span></span>


![シミュレーションの説明の詳細の画像2](images/simulation-details-sb.png)


## <a name="evaluation-report"></a><span data-ttu-id="17f74-251">評価レポート</span><span class="sxs-lookup"><span data-stu-id="17f74-251">Evaluation report</span></span>
<span data-ttu-id="17f74-252">ラボ レポートは、デバイスで実施されたシミュレーションの結果を要約します。</span><span class="sxs-lookup"><span data-stu-id="17f74-252">The lab reports summarize the results of the simulations conducted on the devices.</span></span>

![評価レポートのイメージ](images/eval-report.png)

<span data-ttu-id="17f74-254">一目でわかると、次の情報をすばやく確認できます。</span><span class="sxs-lookup"><span data-stu-id="17f74-254">At a glance, you'll quickly be able to see:</span></span>
- <span data-ttu-id="17f74-255">トリガーされたインシデント</span><span class="sxs-lookup"><span data-stu-id="17f74-255">Incidents that were triggered</span></span>
- <span data-ttu-id="17f74-256">生成されたアラート</span><span class="sxs-lookup"><span data-stu-id="17f74-256">Generated alerts</span></span>
- <span data-ttu-id="17f74-257">露出レベルの評価</span><span class="sxs-lookup"><span data-stu-id="17f74-257">Assessments on exposure level</span></span> 
- <span data-ttu-id="17f74-258">検出された脅威カテゴリ</span><span class="sxs-lookup"><span data-stu-id="17f74-258">Threat categories observed</span></span>
- <span data-ttu-id="17f74-259">検出ソース</span><span class="sxs-lookup"><span data-stu-id="17f74-259">Detection sources</span></span>
- <span data-ttu-id="17f74-260">自動化された調査</span><span class="sxs-lookup"><span data-stu-id="17f74-260">Automated investigations</span></span>


## <a name="provide-feedback"></a><span data-ttu-id="17f74-261">フィードバックの提供</span><span class="sxs-lookup"><span data-stu-id="17f74-261">Provide feedback</span></span>
<span data-ttu-id="17f74-262">フィードバックは、高度な攻撃から環境を保護する上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="17f74-262">Your feedback helps us get better in protecting your environment from advanced attacks.</span></span> <span data-ttu-id="17f74-263">製品の機能と評価結果からエクスペリエンスとインプレッションを共有します。</span><span class="sxs-lookup"><span data-stu-id="17f74-263">Share your experience and impressions from product capabilities and evaluation results.</span></span>

<span data-ttu-id="17f74-264">[フィードバックの提供] を選択して、ご意見 **をお寄せください**。</span><span class="sxs-lookup"><span data-stu-id="17f74-264">Let us know what you think, by selecting **Provide feedback**.</span></span>

![フィードバックを提供するイメージ](images/send-us-feedback-eval-lab.png)
