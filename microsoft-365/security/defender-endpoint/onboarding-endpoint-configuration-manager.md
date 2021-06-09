---
title: Microsoft Endpoint Configuration Manager を使用したオンボーディング
description: デバイスを使用して Microsoft Defender for Endpoint にオンボードするMicrosoft Endpoint Configuration Manager
keywords: オンボーディング、構成、展開、展開、エンドポイント構成マネージャー、Microsoft Defender for Endpoint、コレクション作成、エンドポイント検出応答、次世代保護、攻撃表面の縮小、Microsoft エンドポイント構成マネージャー
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
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: eab23ddeb9011e80cf2835b8d38b2d3fad4b7089
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843508"
---
# <a name="onboarding-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="3b1a3-104">Microsoft Endpoint Configuration Manager を使用したオンボーディング</span><span class="sxs-lookup"><span data-stu-id="3b1a3-104">Onboarding using Microsoft Endpoint Configuration Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3b1a3-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3b1a3-105">**Applies to:**</span></span>
- [<span data-ttu-id="3b1a3-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3b1a3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3b1a3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3b1a3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3b1a3-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="3b1a3-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3b1a3-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="3b1a3-110">この記事は展開ガイドの一部であり、オンボーディング方法の例として機能します。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-110">This article is part of the Deployment guide and acts as an example onboarding method.</span></span> 

<span data-ttu-id="3b1a3-111">「計画 [」トピック](deployment-strategy.md) では、デバイスをサービスにオンボードする方法がいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-111">In the [Planning](deployment-strategy.md) topic, there were several methods provided to onboard devices to the service.</span></span> <span data-ttu-id="3b1a3-112">このトピックでは、共同管理アーキテクチャについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-112">This topic covers the co-management architecture.</span></span> 

<span data-ttu-id="3b1a3-113">![クラウドネイティブ アーキテクチャのイメージ ](images/co-management-architecture.png)
 *環境アーキテクチャの図*</span><span class="sxs-lookup"><span data-stu-id="3b1a3-113">![Image of cloud-native architecture](images/co-management-architecture.png)
*Diagram of environment architectures*</span></span>


<span data-ttu-id="3b1a3-114">Defender for Endpoint はさまざまなエンドポイントとツールのオンボーディングをサポートしますが、この記事ではそれらをカバーしません。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-114">While Defender for Endpoint supports onboarding of various endpoints and tools, this article does not cover them.</span></span> <span data-ttu-id="3b1a3-115">サポートされている他の展開ツールと方法を使用した一般的なオンボーディングの詳細については、「オンボードの概要 [」を参照してください](onboarding.md)。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-115">For information on general onboarding using other supported deployment tools and methods, see [Onboarding overview](onboarding.md).</span></span>



<span data-ttu-id="3b1a3-116">このトピックでは、次のユーザーをガイドします。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-116">This topic guides users in:</span></span>
- <span data-ttu-id="3b1a3-117">手順 1: サービスWindowsデバイスをオンボーディングする</span><span class="sxs-lookup"><span data-stu-id="3b1a3-117">Step 1: Onboarding Windows devices to the service</span></span> 
- <span data-ttu-id="3b1a3-118">手順 2: Defender for Endpoint の機能を構成する</span><span class="sxs-lookup"><span data-stu-id="3b1a3-118">Step 2: Configuring Defender for Endpoint capabilities</span></span>

<span data-ttu-id="3b1a3-119">このオンボーディング ガイダンスでは、次の基本的な手順について説明します。このガイドでは、ユーザーの使用に必要なMicrosoft Endpoint Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-119">This onboarding guidance will walk you through the following basic steps that you need to take when using Microsoft Endpoint Configuration Manager:</span></span>
- <span data-ttu-id="3b1a3-120">**コレクションの作成Microsoft Endpoint Configuration Manager**</span><span class="sxs-lookup"><span data-stu-id="3b1a3-120">**Creating a collection in Microsoft Endpoint Configuration Manager**</span></span>
- <span data-ttu-id="3b1a3-121">**Microsoft Defender for Endpoint の機能を構成するには、Microsoft Endpoint Configuration Manager**</span><span class="sxs-lookup"><span data-stu-id="3b1a3-121">**Configuring Microsoft Defender for Endpoint capabilities using Microsoft Endpoint Configuration Manager**</span></span>

>[!NOTE]
><span data-ttu-id="3b1a3-122">この展開Windowsでは、このデバイスのみを対象とします。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-122">Only Windows devices are covered in this example deployment.</span></span> 



## <a name="step-1-onboard-windows-devices-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="3b1a3-123">手順 1: デバイスを使用WindowsデバイスをオンボードMicrosoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3b1a3-123">Step 1: Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>

### <a name="collection-creation"></a><span data-ttu-id="3b1a3-124">コレクションの作成</span><span class="sxs-lookup"><span data-stu-id="3b1a3-124">Collection creation</span></span>
<span data-ttu-id="3b1a3-125">既存のWindows 10デバイスMicrosoft Endpoint Configuration Managerオンボーディングするには、展開で既存のコレクションをターゲットにするか、テスト用に新しいコレクションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-125">To onboard Windows 10 devices with Microsoft Endpoint Configuration Manager, the deployment can target an existing collection or a new collection can be created for testing.</span></span> 

<span data-ttu-id="3b1a3-126">グループ ポリシーや手動メソッドなどのツールを使用したオンボーディングでは、システムにエージェントはインストールされない。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-126">Onboarding using tools such as Group policy or manual method does not install any agent on the system.</span></span> 

<span data-ttu-id="3b1a3-127">コンソール内Microsoft Endpoint Configuration Managerオンボーディング プロセスは、コンソール内のコンプライアンス設定の一部として構成されます。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-127">Within the Microsoft Endpoint Configuration Manager console the onboarding process will be configured as part of the compliance settings within the console.</span></span>

<span data-ttu-id="3b1a3-128">この必要な構成を受け取るシステムは、Configuration Manager クライアントが管理ポイントからこのポリシーを受け取り続ける限り、その構成を維持します。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-128">Any system that receives this required configuration will maintain that configuration for as long as the Configuration Manager client continues to receive this policy from the management point.</span></span> 

<span data-ttu-id="3b1a3-129">以下の手順に従って、デバイスを使用してエンドポイントをオンボードMicrosoft Endpoint Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-129">Follow the steps below to onboard endpoints using Microsoft Endpoint Configuration Manager.</span></span>

1. <span data-ttu-id="3b1a3-130">コンソールMicrosoft Endpoint Configuration Manager、[アセット] と [**コンプライアンスの概要] \> デバイス コレクション \> に移動します**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-130">In Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Device Collections**.</span></span>            

    ![ウィザードのMicrosoft Endpoint Configuration Manager 1](images/configmgr-device-collections.png)

2. <span data-ttu-id="3b1a3-132">[デバイス コレクション] **を右クリックし** 、[デバイス コレクション **の作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-132">Right Click **Device Collection** and select **Create Device Collection**.</span></span>

    ![ウィザード 2 Microsoft Endpoint Configuration Managerのイメージ](images/configmgr-create-device-collection.png)

3. <span data-ttu-id="3b1a3-134">[名前]**と [制限\*\*\*\*コレクション] を指定し、[** 次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-134">Provide a **Name** and **Limiting Collection**, then select **Next**.</span></span>

    ![ウィザードのMicrosoft Endpoint Configuration Manager 3](images/configmgr-limiting-collection.png)

4. <span data-ttu-id="3b1a3-136">[ルール **の追加] を選択** し、[ **クエリ ルール] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-136">Select **Add Rule** and choose **Query Rule**.</span></span>

    ![ウィザードのMicrosoft Endpoint Configuration Manager 4](images/configmgr-query-rule.png)

5.  <span data-ttu-id="3b1a3-138">[直接 **メンバーシップ ウィザード** ] で **[次へ] をクリックし** 、[クエリ ステートメントの **編集] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-138">Click **Next** on the **Direct Membership Wizard** and click on **Edit Query Statement**.</span></span>

     ![ウィザードのMicrosoft Endpoint Configuration Manager 5](images/configmgr-direct-membership.png)

6. <span data-ttu-id="3b1a3-140">[ **条件] を** 選択し、星のアイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-140">Select **Criteria** and then choose the star icon.</span></span>

     ![ウィザードのMicrosoft Endpoint Configuration Manager 6](images/configmgr-criteria.png)

7. <span data-ttu-id="3b1a3-142">条件の種類を **単純な** 値として保持し、オペレーティング システム **-** ビルド番号 、演算子の値が **14393** 以上の場合は、OK をクリックする場所を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-142">Keep criterion type as **simple value**, choose where as **Operating System - build number**, operator as **is greater than or equal to** and value **14393** and click on **OK**.</span></span>

    ![ウィザード 7 Microsoft Endpoint Configuration Managerイメージ](images/configmgr-simple-value.png)

8. <span data-ttu-id="3b1a3-144">[次 **へ] と [** 閉じる] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-144">Select **Next** and **Close**.</span></span>

    ![ウィザードのMicrosoft Endpoint Configuration Manager 8](images/configmgr-membership-rules.png)

9. <span data-ttu-id="3b1a3-146">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-146">Select **Next**.</span></span>

    ![ウィザードのMicrosoft Endpoint Configuration Manager 9](images/configmgr-confirm.png)


<span data-ttu-id="3b1a3-148">このタスクを完了すると、環境内のすべてのエンドポイントWindows 10デバイス コレクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-148">After completing this task, you now have a device collection with all the Windows 10 endpoints in the environment.</span></span> 


## <a name="step-2-configure-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="3b1a3-149">手順 2: Microsoft Defender for Endpoint の機能を構成する</span><span class="sxs-lookup"><span data-stu-id="3b1a3-149">Step 2: Configure Microsoft Defender for Endpoint capabilities</span></span> 
<span data-ttu-id="3b1a3-150">このセクションでは、デバイス上のデバイスを使用して次の機能Microsoft Endpoint Configuration Manager構成Windowsします。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-150">This section guides you in configuring the following capabilities using Microsoft Endpoint Configuration Manager on Windows devices:</span></span>

- [<span data-ttu-id="3b1a3-151">**エンドポイントでの検出と対応**</span><span class="sxs-lookup"><span data-stu-id="3b1a3-151">**Endpoint detection and response**</span></span>](#endpoint-detection-and-response)
- [<span data-ttu-id="3b1a3-152">**次世代の保護**</span><span class="sxs-lookup"><span data-stu-id="3b1a3-152">**Next-generation protection**</span></span>](#next-generation-protection)
- [<span data-ttu-id="3b1a3-153">**攻撃面の減少**</span><span class="sxs-lookup"><span data-stu-id="3b1a3-153">**Attack surface reduction**</span></span>](#attack-surface-reduction)


### <a name="endpoint-detection-and-response"></a><span data-ttu-id="3b1a3-154">エンドポイントの検出および応答</span><span class="sxs-lookup"><span data-stu-id="3b1a3-154">Endpoint detection and response</span></span>
#### <a name="windows-10"></a><span data-ttu-id="3b1a3-155">Windows 10</span><span class="sxs-lookup"><span data-stu-id="3b1a3-155">Windows 10</span></span>
<span data-ttu-id="3b1a3-156">Microsoft Defender セキュリティ センター内から、System Center Configuration Manager でポリシーを作成し、そのポリシーを Windows 10 デバイスに展開するために使用できる '.onboarding' ポリシーをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-156">From within the Microsoft Defender Security Center it is possible to download the '.onboarding' policy that can be used to create the policy in System Center Configuration Manager and deploy that policy to Windows 10 devices.</span></span>

1. <span data-ttu-id="3b1a3-157">[ポータル] Microsoft Defender セキュリティ センター、[オンボーディング][設定を選択します](https://securitycenter.windows.com/preferences2/onboarding)。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-157">From a Microsoft Defender Security Center Portal, select [Settings and then Onboarding](https://securitycenter.windows.com/preferences2/onboarding).</span></span>



2. <span data-ttu-id="3b1a3-158">[展開方法] で、サポートされているバージョンのファイルを **Microsoft Endpoint Configuration Manager。**</span><span class="sxs-lookup"><span data-stu-id="3b1a3-158">Under Deployment method select the supported version of **Microsoft Endpoint Configuration Manager**.</span></span>

    ![Microsoft Defender for Endpoint オンボーディング ウィザード 10 のイメージ](images/mdatp-onboarding-wizard.png)

3. <span data-ttu-id="3b1a3-160">[パッケージ **のダウンロード] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-160">Select **Download package**.</span></span>

    ![Microsoft Defender for Endpoint オンボーディング ウィザードのイメージ11](images/mdatp-download-package.png)

4. <span data-ttu-id="3b1a3-162">パッケージをアクセス可能な場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-162">Save the package to an accessible location.</span></span>
5. <span data-ttu-id="3b1a3-163">[Microsoft Endpoint Configuration Manager] で、[アセットとコンプライアンス] の [概要] >**ポリシー> Endpoint Protection > Microsoft Defender ATP移動します**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-163">In  Microsoft Endpoint Configuration Manager, navigate to: **Assets and Compliance > Overview > Endpoint Protection > Microsoft Defender ATP Policies**.</span></span>

6. <span data-ttu-id="3b1a3-164">[ポリシー] を **右Microsoft Defender ATPし、[** ポリシーの **作成] Microsoft Defender ATPします**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-164">Right-click **Microsoft Defender ATP Policies** and select **Create Microsoft Defender ATP Policy**.</span></span>

    ![ウィザードのMicrosoft Endpoint Configuration Manager 12](images/configmgr-create-policy.png)

7. <span data-ttu-id="3b1a3-166">名前と説明を入力し、[ **オン** ボーディング] が選択されている場合は、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-166">Enter the name and description, verify **Onboarding** is selected, then select **Next**.</span></span>

    ![ウィザードのMicrosoft Endpoint Configuration Manager 13](images/configmgr-policy-name.png)


8. <span data-ttu-id="3b1a3-168">[ **参照**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-168">Click **Browse**.</span></span>

9. <span data-ttu-id="3b1a3-169">上記の手順 4 からダウンロードしたファイルの場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-169">Navigate to the location of the downloaded file from step 4 above.</span></span>

10. <span data-ttu-id="3b1a3-170">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-170">Click **Next**.</span></span>
11. <span data-ttu-id="3b1a3-171">適切なサンプル (None または All ファイルの種類)**を使用\*\*\*\*してエージェントを構成します**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-171">Configure the Agent with the appropriate samples (**None** or **All file types**).</span></span>

    ![構成設定のイメージ1](images/configmgr-config-settings.png)

12. <span data-ttu-id="3b1a3-173">適切な利用統計情報 (標準または **迅速) を\*\*\*\*選択し**、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-173">Select the appropriate telemetry (**Normal** or **Expedited**) then click **Next**.</span></span>

    ![構成設定のイメージ2](images/configmgr-telemetry.png)

14. <span data-ttu-id="3b1a3-175">構成を確認し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-175">Verify the configuration, then click **Next**.</span></span>

     ![構成設定のイメージ 3](images/configmgr-verify-configuration.png)

15. <span data-ttu-id="3b1a3-177">ウィザードが **完了したら** 、[閉じる] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-177">Click **Close** when the Wizard completes.</span></span>

16.  <span data-ttu-id="3b1a3-178">コンソールでMicrosoft Endpoint Configuration Manager作成した Defender for Endpoint ポリシーを右クリックし、[展開] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-178">In the Microsoft Endpoint Configuration Manager console, right-click the Defender for Endpoint policy you just created and select **Deploy**.</span></span>

     ![構成設定のイメージ 4](images/configmgr-deploy.png)

17. <span data-ttu-id="3b1a3-180">右側のパネルで、前に作成したコレクションを選択し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-180">On the right panel, select the previously created collection and click **OK**.</span></span>

    ![構成設定のイメージ5](images/configmgr-select-collection.png)


#### <a name="previous-versions-of-windows-client-windows-7-and-windows-81"></a><span data-ttu-id="3b1a3-182">以前のバージョンの Windows クライアント (Windows 7 および Windows 8.1)</span><span class="sxs-lookup"><span data-stu-id="3b1a3-182">Previous versions of Windows Client (Windows 7 and Windows 8.1)</span></span>
<span data-ttu-id="3b1a3-183">以下の手順に従って、以前のバージョンのデバイスのオンボーディングに必要な Defender for Endpoint Workspace ID と Workspace Key を特定Windows。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-183">Follow the steps below to identify the Defender for Endpoint Workspace ID and Workspace Key, that will be required for the onboarding of previous versions of Windows.</span></span>

1. <span data-ttu-id="3b1a3-184">[新しいポータルMicrosoft Defender セキュリティ センターオンボーディング] を設定 >**します**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-184">From a Microsoft Defender Security Center Portal, select **Settings > Onboarding**.</span></span>

2. <span data-ttu-id="3b1a3-185">[オペレーティング システム] で **、[Windows 7 SP1 と 8.1] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-185">Under operating system choose **Windows 7 SP1 and 8.1**.</span></span>

3. <span data-ttu-id="3b1a3-186">ワークスペース **ID とワークスペース キー\*\*\*\*をコピーして** 保存します。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-186">Copy the **Workspace ID** and **Workspace Key** and save them.</span></span> <span data-ttu-id="3b1a3-187">これらは、プロセスの後半で使用されます。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-187">They will be used later in the process.</span></span>

    ![オンボーディングのイメージ](images/91b738e4b97c4272fd6d438d8c2d5269.png)

4. <span data-ttu-id="3b1a3-189">[インストール] Microsoft Monitoring Agent (MMA) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-189">Install the Microsoft Monitoring Agent (MMA).</span></span> <br>
    <span data-ttu-id="3b1a3-190">MMA は現在 (2019 年 1 月現在) 次のオペレーティング システムWindowsサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-190">MMA is currently (as of January 2019) supported on the following Windows Operating Systems:</span></span>

    -   <span data-ttu-id="3b1a3-191">サーバー SKU: Windows Server 2008 SP1 以降</span><span class="sxs-lookup"><span data-stu-id="3b1a3-191">Server SKUs: Windows Server 2008 SP1 or Newer</span></span>

    -   <span data-ttu-id="3b1a3-192">クライアント SKU: Windows 7 SP1 以降</span><span class="sxs-lookup"><span data-stu-id="3b1a3-192">Client SKUs: Windows 7 SP1 and later</span></span>

    <span data-ttu-id="3b1a3-193">MMA エージェントをデバイスにインストールするWindowsがあります。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-193">The MMA agent will need to be installed on Windows devices.</span></span> <span data-ttu-id="3b1a3-194">エージェントをインストールするには、MMA を使用してデータ[](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)を収集するために、一部のシステムでカスタマー エクスペリエンスと診断テレメトリの更新プログラムをダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-194">To install the agent, some systems will need to download the [Update for customer experience and diagnostic telemetry](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) in order to collect the data with MMA.</span></span> <span data-ttu-id="3b1a3-195">これらのシステム バージョンには、次のものが含まれますが、これらに限定されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-195">These system versions include but may not be limited to:</span></span>

    -   <span data-ttu-id="3b1a3-196">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="3b1a3-196">Windows 8.1</span></span>

    -   <span data-ttu-id="3b1a3-197">Windows 7</span><span class="sxs-lookup"><span data-stu-id="3b1a3-197">Windows 7</span></span>

    -   <span data-ttu-id="3b1a3-198">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="3b1a3-198">Windows Server 2016</span></span>

    -   <span data-ttu-id="3b1a3-199">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="3b1a3-199">Windows Server 2012 R2</span></span>

    -   <span data-ttu-id="3b1a3-200">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="3b1a3-200">Windows Server 2008 R2</span></span>

    <span data-ttu-id="3b1a3-201">具体的には、Windows 7 SP1 の場合は、次のパッチをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-201">Specifically, for Windows 7 SP1, the following patches must be installed:</span></span>

    -   <span data-ttu-id="3b1a3-202">[KB4074598 のインストール](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="3b1a3-202">Install [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>

    -   <span data-ttu-id="3b1a3-203">[4.5 .NET Framework以降](https://www.microsoft.com/download/details.aspx?id=30653)**)** または 
         [KB3154518 のいずれかをインストールします](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-203">Install either [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) **or**
        [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework).</span></span>
        <span data-ttu-id="3b1a3-204">両方を同じシステムにインストールしない。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-204">Do not install both on the same system.</span></span>

5. <span data-ttu-id="3b1a3-205">プロキシを使用してインターネットに接続する場合は、「プロキシ設定の構成」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-205">If you're using a proxy to connect to the Internet see the Configure proxy settings section.</span></span>

<span data-ttu-id="3b1a3-206">完了すると、1 時間以内にポータルにオンボード エンドポイントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-206">Once completed, you should see onboarded endpoints in the portal within an hour.</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="3b1a3-207">次世代の保護</span><span class="sxs-lookup"><span data-stu-id="3b1a3-207">Next generation protection</span></span> 
<span data-ttu-id="3b1a3-208">Windows Defender ウイルス対策は、デスクトップ、ポータブル コンピューター、サーバーを対象に次世代の保護機能を提供する、組み込みのマルウェア対策ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-208">Microsoft Defender Antivirus is a built-in antimalware solution that provides next generation protection for desktops, portable computers, and servers.</span></span>

1. <span data-ttu-id="3b1a3-209">このコンソールMicrosoft Endpoint Configuration Manager、マルウェア対策ポリシーの [アセットと **\> \> コンプライアンスEndpoint Protection] \>** に移動し、[マルウェア対策ポリシーの作成]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-209">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Antimalware Polices** and choose **Create Antimalware Policy**.</span></span>

    ![マルウェア対策ポリシーのイメージ](images/9736e0358e86bc778ce1bd4c516adb8b.png)

2. <span data-ttu-id="3b1a3-211">[**スケジュールされたスキャン\*\*\*\*]、[** スキャン設定]、[既定のアクション]、[リアルタイム保護]、[除外設定]、[詳細設定]、[脅威の上書き]、**クラウド保護サービス** とセキュリティ インテリジェンスの更新を選択し **、[OK] を選択します**。   </span><span class="sxs-lookup"><span data-stu-id="3b1a3-211">Select **Scheduled scans**, **Scan settings**, **Default actions**, **Real-time protection**, **Exclusion settings**, **Advanced**, **Threat overrides**, **Cloud Protection Service** and **Security intelligence   updates** and choose **OK**.</span></span>

    ![次世代保護ウィンドウのイメージ 1](images/1566ad81bae3d714cc9e0d47575a8cbd.png)

    <span data-ttu-id="3b1a3-213">特定の業界または一部の企業のお客様は、ウイルス対策の構成方法に関する特定のニーズを持っている場合があります。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-213">In certain industries or some select enterprise customers might have specific needs on how Antivirus is configured.</span></span>

  
    [<span data-ttu-id="3b1a3-214">クイック スキャンとフル スキャン、およびカスタム スキャン</span><span class="sxs-lookup"><span data-stu-id="3b1a3-214">Quick scan versus full scan and custom scan</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/scheduled-catch-up-scans-microsoft-defender-antivirus#quick-scan-versus-full-scan-and-custom-scan)

    <span data-ttu-id="3b1a3-215">詳細については、「Windows セキュリティ[構成フレームワーク」を参照してください。](/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)</span><span class="sxs-lookup"><span data-stu-id="3b1a3-215">For more details, see [Windows Security configuration framework](/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)</span></span>
  
    ![次世代保護ウィンドウ 2 のイメージ](images/cd7daeb392ad5a36f2d3a15d650f1e96.png)

    ![次世代保護ウィンドウのイメージ 3](images/36c7c2ed737f2f4b54918a4f20791d4b.png)

    ![次世代保護ウィンドウのイメージ 4](images/a28afc02c1940d5220b233640364970c.png)

    ![次世代保護ウィンドウのイメージ 5](images/5420a8790c550f39f189830775a6d4c9.png)

    ![次世代保護ウィンドウのイメージ 6](images/33f08a38f2f4dd12a364f8eac95e8c6b.png)

    ![次世代保護ウィンドウのイメージ 7](images/41b9a023bc96364062c2041a8f5c344e.png)

    ![次世代保護ウィンドウ 8 のイメージ](images/945c9c5d66797037c3caeaa5c19f135c.png)

    ![次世代保護ウィンドウのイメージ 9](images/3876ca687391bfc0ce215d221c683970.png)

3. <span data-ttu-id="3b1a3-224">新しく作成したマルウェア対策ポリシーを右クリックし、[展開] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-224">Right-click on the newly created antimalware policy and select **Deploy**.</span></span>

    ![次世代保護ウィンドウ 10 のイメージ](images/f5508317cd8c7870627cb4726acd5f3d.png)

4. <span data-ttu-id="3b1a3-226">新しいマルウェア対策ポリシーをユーザーコレクションにWindows 10し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-226">Target the new antimalware policy to your Windows 10 collection and click **OK**.</span></span>

     ![次世代保護ウィンドウ 11 のイメージ](images/configmgr-select-collection.png)

<span data-ttu-id="3b1a3-228">このタスクを完了すると、このタスクが正常に構成Windows Defender ウイルス対策。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-228">After completing this task, you now have successfully configured Windows Defender Antivirus.</span></span>

### <a name="attack-surface-reduction"></a><span data-ttu-id="3b1a3-229">攻撃面の縮小</span><span class="sxs-lookup"><span data-stu-id="3b1a3-229">Attack surface reduction</span></span>
<span data-ttu-id="3b1a3-230">Defender for Endpoint の攻撃表面の縮小の柱には、Exploit Guard で使用できる機能セットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-230">The attack surface reduction pillar of Defender for Endpoint includes the feature set that is available under Exploit Guard.</span></span> <span data-ttu-id="3b1a3-231">攻撃表面の縮小 (ASR) ルール、フォルダー アクセスの制御、ネットワーク保護、エクスプロイト保護。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-231">Attack surface reduction (ASR) rules, Controlled Folder Access, Network Protection and Exploit Protection.</span></span> 

<span data-ttu-id="3b1a3-232">これらの機能はすべて監査モードとブロック モードを提供します。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-232">All these features provide an audit mode and a block mode.</span></span> <span data-ttu-id="3b1a3-233">監査モードでは、エンド ユーザーに影響はありません。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-233">In audit mode there is no end-user impact.</span></span> <span data-ttu-id="3b1a3-234">これは、追加のテレメトリを収集し、その他のアプリケーションで使用Microsoft Defender セキュリティ センター。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-234">All it does is collect additional telemetry and make it available in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="3b1a3-235">展開の目的は、セキュリティ コントロールをブロック モードにステップ バイ ステップで移動する方法です。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-235">The goal with a deployment is to step-by-step move security controls into block mode.</span></span>

<span data-ttu-id="3b1a3-236">監査モードで ASR ルールを設定するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-236">To set ASR rules in Audit mode:</span></span>

1. <span data-ttu-id="3b1a3-237">[セキュリティ コンソールMicrosoft Endpoint Configuration Manager、Exploit Guard の [アセットとコンプライアンスの概要] Endpoint Protection Windows Defender **\> \> \> し、[Exploit Guard** ポリシーの作成]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-237">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

   ![コンソール0 Microsoft Endpoint Configuration Managerイメージ](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2.  <span data-ttu-id="3b1a3-239">[攻撃 **表面の縮小] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-239">Select **Attack Surface Reduction**.</span></span>
   

3. <span data-ttu-id="3b1a3-240">ルールを [監査] に **設定し、[** 次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-240">Set rules to **Audit** and click **Next**.</span></span>


    ![コンソール 1 Microsoft Endpoint Configuration Managerイメージ](images/d18e40c9e60aecf1f9a93065cb7567bd.png)

4. <span data-ttu-id="3b1a3-242">[次へ] をクリックして、新しい Exploit Guard ポリシーを **確認します**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-242">Confirm the new Exploit Guard policy by clicking on **Next**.</span></span>

    ![コンソール 2 Microsoft Endpoint Configuration Managerイメージ](images/0a6536f2c4024c08709cac8fcf800060.png)

    
5. <span data-ttu-id="3b1a3-244">ポリシーが作成されると、[閉じる] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-244">Once the policy is created click **Close**.</span></span>

    ![コンソール 3 Microsoft Endpoint Configuration Managerのイメージ](images/95d23a07c2c8bc79176788f28cef7557.png)

    ![コンソール 1 Microsoft エンドポイント マネージャーイメージ](images/95d23a07c2c8bc79176788f28cef7557.png)
   

6.  <span data-ttu-id="3b1a3-247">新しく作成したポリシーを右クリックし、[展開] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-247">Right-click on the newly created policy and choose **Deploy**.</span></span>
    
    ![コンソール 4 Microsoft Endpoint Configuration Managerイメージ](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. <span data-ttu-id="3b1a3-249">ポリシーを新しく作成したコレクションにWindows 10し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-249">Target the policy to the newly created Windows 10 collection and click **OK**.</span></span>

    ![コンソール 5 Microsoft Endpoint Configuration Managerのイメージ](images/0ccfe3e803be4b56c668b220b51da7f7.png)

<span data-ttu-id="3b1a3-251">このタスクを完了すると、監査モードで ASR ルールが正常に構成されました。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-251">After completing this task, you now have successfully configured ASR rules in audit mode.</span></span>  
  
<span data-ttu-id="3b1a3-252">ASR ルールがエンドポイントに正しく適用されているかどうかを確認する追加の手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-252">Below are additional steps to verify whether ASR rules are correctly applied to endpoints.</span></span> <span data-ttu-id="3b1a3-253">(これには数分かかる場合があります)</span><span class="sxs-lookup"><span data-stu-id="3b1a3-253">(This may take few minutes)</span></span>


1. <span data-ttu-id="3b1a3-254">Web ブラウザーからに移動します <https://securitycenter.windows.com> 。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-254">From a web browser, navigate to <https://securitycenter.windows.com>.</span></span>

2.  <span data-ttu-id="3b1a3-255">左側 **のメニューから [構成** の管理] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-255">Select **Configuration management** from left side menu.</span></span>

3. <span data-ttu-id="3b1a3-256">[攻撃 **表面管理] パネルの [攻撃表面の** 管理に移動] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-256">Click **Go to attack surface management** in the Attack surface management panel.</span></span> 
    
    ![攻撃表面管理のイメージ](images/security-center-attack-surface-mgnt-tile.png)

4. <span data-ttu-id="3b1a3-258">攻撃表面 **縮小ルール** レポートの [構成] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-258">Click **Configuration** tab in Attack surface reduction rules reports.</span></span> <span data-ttu-id="3b1a3-259">各デバイスの ASR ルール構成の概要と ASR ルールの状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-259">It shows ASR rules configuration overview and ASR rules status on each devices.</span></span>

    ![攻撃表面の縮小ルールレポートのスクリーンショット1](images/f91f406e6e0aae197a947d3b0e8b2d0d.png)

5. <span data-ttu-id="3b1a3-261">各デバイスをクリックすると、ASR ルールの構成の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-261">Click each device shows configuration details of ASR rules.</span></span>

    ![攻撃表面の縮小ルールレポートのスクリーンショット 2](images/24bfb16ed561cbb468bd8ce51130ca9d.png)

<span data-ttu-id="3b1a3-263">詳細 [については、「オプティマイズ ASR ルールの展開と検出」](/microsoft-365/security/defender-endpoint/configure-machines-asr)   を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-263">See [Optimize ASR rule deployment and detections](/microsoft-365/security/defender-endpoint/configure-machines-asr)   for more details.</span></span>  


#### <a name="set-network-protection-rules-in-audit-mode"></a><span data-ttu-id="3b1a3-264">監査モードでネットワーク保護ルールを設定します。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-264">Set Network Protection rules in Audit mode:</span></span>
1. <span data-ttu-id="3b1a3-265">[セキュリティ コンソールMicrosoft Endpoint Configuration Manager、Exploit Guard の [アセットとコンプライアンスの概要] Endpoint Protection Windows Defender **\> \> \> し、[Exploit Guard** ポリシーの作成]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-265">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and  Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

    ![Configuration Manager1 System Centerスクリーンショット](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. <span data-ttu-id="3b1a3-267">[ネットワーク **保護] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-267">Select **Network protection**.</span></span>

3. <span data-ttu-id="3b1a3-268">設定を [監査] に **設定し、[次** へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-268">Set the setting to **Audit** and click **Next**.</span></span> 

    ![Confirugatiom Manager2 System Centerスクリーンショット](images/c039b2e05dba1ade6fb4512456380c9f.png)

4. <span data-ttu-id="3b1a3-270">[次へ] をクリックして、新しい Exploit Guard ポリシーを **確認します**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-270">Confirm the new Exploit Guard Policy by clicking **Next**.</span></span>
    
    ![スクリーンショット Exploit GUard policy1](images/0a6536f2c4024c08709cac8fcf800060.png)

5. <span data-ttu-id="3b1a3-272">ポリシーが作成されると、[閉じる] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-272">Once the policy is created click on **Close**.</span></span>

    ![スクリーンショット Exploit GUard policy2](images/95d23a07c2c8bc79176788f28cef7557.png)

6. <span data-ttu-id="3b1a3-274">新しく作成したポリシーを右クリックし、[展開] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-274">Right-click on the newly created policy and choose **Deploy**.</span></span>

    ![スクリーンショット Microsoft Endpoint Configuration Manager1](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. <span data-ttu-id="3b1a3-276">新しく作成したコレクションのポリシーを選択しWindows 10 OK を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-276">Select the policy to the newly created Windows 10 collection and choose **OK**.</span></span>

    ![スクリーンショット Microsoft Endpoint Configuration Manager2](images/0ccfe3e803be4b56c668b220b51da7f7.png)



<span data-ttu-id="3b1a3-278">このタスクを完了すると、監査モードでネットワーク保護が正常に構成されました。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-278">After completing this task, you now have successfully configured Network Protection in audit mode.</span></span>

#### <a name="to-set-controlled-folder-access-rules-in-audit-mode"></a><span data-ttu-id="3b1a3-279">監査モードでフォルダー アクセスの制御ルールを設定するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-279">To set Controlled Folder Access rules in Audit mode:</span></span>

1. <span data-ttu-id="3b1a3-280">[セキュリティ コンソールMicrosoft Endpoint Configuration Manager、Exploit Guard の [アセットとコンプライアンスの概要] Endpoint Protection Windows Defender **\> \> \> し、[Exploit Guard** ポリシーの作成]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-280">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

    ![Microsoft Endpoint Configuration Manager3 のスクリーンショット](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. <span data-ttu-id="3b1a3-282">[フォルダー **アクセスの制御] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-282">Select **Controlled folder access**.</span></span>
    
3. <span data-ttu-id="3b1a3-283">構成を [監査] に **設定し、[次** へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-283">Set the configuration to **Audit** and click **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager4 のスクリーンショット](images/a8b934dab2dbba289cf64fe30e0e8aa4.png)    
    
4. <span data-ttu-id="3b1a3-285">[次へ] をクリックして、新しい Exploit Guard ポリシーを **確認します**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-285">Confirm the new Exploit Guard Policy by clicking on **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager5 のスクリーンショット](images/0a6536f2c4024c08709cac8fcf800060.png)

5. <span data-ttu-id="3b1a3-287">ポリシーが作成されると、[閉じる] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-287">Once the policy is created click on **Close**.</span></span>

    ![Microsoft Endpoint Configuration Manager6 のスクリーンショット](images/95d23a07c2c8bc79176788f28cef7557.png)

6. <span data-ttu-id="3b1a3-289">新しく作成したポリシーを右クリックし、[展開] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-289">Right-click on the newly created policy and choose **Deploy**.</span></span>

    ![Microsoft Endpoint Configuration Manager7 のスクリーンショット](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7.  <span data-ttu-id="3b1a3-291">ポリシーを新しく作成したコレクションにWindows 10し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-291">Target the policy to the newly created Windows 10 collection and click **OK**.</span></span>

    ![Microsoft Endpoint Configuration Manager8 のスクリーンショット](images/0ccfe3e803be4b56c668b220b51da7f7.png)

<span data-ttu-id="3b1a3-293">監査モードでフォルダー アクセスの制御が正常に構成されました。</span><span class="sxs-lookup"><span data-stu-id="3b1a3-293">You have now successfully configured Controlled folder access in audit mode.</span></span>

## <a name="related-topic"></a><span data-ttu-id="3b1a3-294">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3b1a3-294">Related topic</span></span>
- [<span data-ttu-id="3b1a3-295">Microsoft エンドポイント マネージャーを使用したオンボーディング</span><span class="sxs-lookup"><span data-stu-id="3b1a3-295">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
