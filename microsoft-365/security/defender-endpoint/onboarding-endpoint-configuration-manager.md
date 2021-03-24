---
title: Microsoft Endpoint Configuration Manager を使用したオンボーディング
description: Microsoft Endpoint Configuration Manager を使用して Microsoft Defender for Endpoint にオンボードする方法について説明します。
keywords: オンボーディング、構成、展開、展開、エンドポイント構成マネージャー、mdatp、高度な脅威保護、コレクションの作成、エンドポイント検出応答、次世代保護、攻撃表面の縮小、Microsoft エンドポイント構成マネージャー
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
ms.openlocfilehash: 6e6f3cfbf471e7b99e2ce5215491e32c955e3833
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51061049"
---
# <a name="onboarding-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="e7e38-104">Microsoft Endpoint Configuration Manager を使用したオンボーディング</span><span class="sxs-lookup"><span data-stu-id="e7e38-104">Onboarding using Microsoft Endpoint Configuration Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e7e38-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e7e38-105">**Applies to:**</span></span>
- [<span data-ttu-id="e7e38-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e7e38-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="e7e38-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e7e38-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e7e38-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="e7e38-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e7e38-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="e7e38-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="e7e38-110">この記事は展開ガイドの一部であり、オンボーディング方法の例として機能します。</span><span class="sxs-lookup"><span data-stu-id="e7e38-110">This article is part of the Deployment guide and acts as an example onboarding method.</span></span> 

<span data-ttu-id="e7e38-111">「計画 [」トピック](deployment-strategy.md) では、デバイスをサービスにオンボードする方法がいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="e7e38-111">In the [Planning](deployment-strategy.md) topic, there were several methods provided to onboard devices to the service.</span></span> <span data-ttu-id="e7e38-112">このトピックでは、共同管理アーキテクチャについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e7e38-112">This topic covers the co-management architecture.</span></span> 

<span data-ttu-id="e7e38-113">![クラウドネイティブ アーキテクチャのイメージ ](images/co-management-architecture.png)
 *環境アーキテクチャの図*</span><span class="sxs-lookup"><span data-stu-id="e7e38-113">![Image of cloud-native architecture](images/co-management-architecture.png)
*Diagram of environment architectures*</span></span>


<span data-ttu-id="e7e38-114">Defender for Endpoint はさまざまなエンドポイントとツールのオンボーディングをサポートしますが、この記事ではそれらをカバーしません。</span><span class="sxs-lookup"><span data-stu-id="e7e38-114">While Defender for Endpoint supports onboarding of various endpoints and tools, this article does not cover them.</span></span> <span data-ttu-id="e7e38-115">サポートされている他の展開ツールと方法を使用した一般的なオンボーディングの詳細については、「オンボードの概要 [」を参照してください](onboarding.md)。</span><span class="sxs-lookup"><span data-stu-id="e7e38-115">For information on general onboarding using other supported deployment tools and methods, see [Onboarding overview](onboarding.md).</span></span>



<span data-ttu-id="e7e38-116">このトピックでは、次のユーザーをガイドします。</span><span class="sxs-lookup"><span data-stu-id="e7e38-116">This topic guides users in:</span></span>
- <span data-ttu-id="e7e38-117">手順 1: Windows デバイスをサービスにオンボーディングする</span><span class="sxs-lookup"><span data-stu-id="e7e38-117">Step 1: Onboarding Windows devices to the service</span></span> 
- <span data-ttu-id="e7e38-118">手順 2: Defender for Endpoint の機能を構成する</span><span class="sxs-lookup"><span data-stu-id="e7e38-118">Step 2: Configuring Defender for Endpoint capabilities</span></span>

<span data-ttu-id="e7e38-119">このオンボーディング ガイダンスでは、Microsoft Endpoint Configuration Manager を使用する場合に実行する必要がある次の基本的な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="e7e38-119">This onboarding guidance will walk you through the following basic steps that you need to take when using Microsoft Endpoint Configuration Manager:</span></span>
- <span data-ttu-id="e7e38-120">**Microsoft Endpoint Configuration Manager でのコレクションの作成**</span><span class="sxs-lookup"><span data-stu-id="e7e38-120">**Creating a collection in Microsoft Endpoint Configuration Manager**</span></span>
- <span data-ttu-id="e7e38-121">**Microsoft Endpoint Configuration Manager を使用した Microsoft Defender for Endpoint の機能の構成**</span><span class="sxs-lookup"><span data-stu-id="e7e38-121">**Configuring Microsoft Defender for Endpoint capabilities using Microsoft Endpoint Configuration Manager**</span></span>

>[!NOTE]
><span data-ttu-id="e7e38-122">この展開例では、Windows デバイスのみについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e7e38-122">Only Windows devices are covered in this example deployment.</span></span> 



## <a name="step-1-onboard-windows-devices-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="e7e38-123">手順 1: Microsoft Endpoint Configuration Manager を使用して Windows デバイスをオンボードする</span><span class="sxs-lookup"><span data-stu-id="e7e38-123">Step 1: Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>

### <a name="collection-creation"></a><span data-ttu-id="e7e38-124">コレクションの作成</span><span class="sxs-lookup"><span data-stu-id="e7e38-124">Collection creation</span></span>
<span data-ttu-id="e7e38-125">Microsoft Endpoint Configuration Manager を使用して Windows 10 デバイスをオンボードするには、展開で既存のコレクションをターゲットにするか、テスト用に新しいコレクションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e7e38-125">To onboard Windows 10 devices with Microsoft Endpoint Configuration Manager, the deployment can target an existing collection or a new collection can be created for testing.</span></span> 

<span data-ttu-id="e7e38-126">グループ ポリシーや手動メソッドなどのツールを使用したオンボーディングでは、システムにエージェントはインストールされない。</span><span class="sxs-lookup"><span data-stu-id="e7e38-126">Onboarding using tools such as Group policy or manual method does not install any agent on the system.</span></span> 

<span data-ttu-id="e7e38-127">Microsoft Endpoint Configuration Manager コンソール内では、オンボーディング プロセスがコンソール内のコンプライアンス設定の一部として構成されます。</span><span class="sxs-lookup"><span data-stu-id="e7e38-127">Within the Microsoft Endpoint Configuration Manager console the onboarding process will be configured as part of the compliance settings within the console.</span></span>

<span data-ttu-id="e7e38-128">この必要な構成を受け取るシステムは、Configuration Manager クライアントが管理ポイントからこのポリシーを受け取り続ける限り、その構成を維持します。</span><span class="sxs-lookup"><span data-stu-id="e7e38-128">Any system that receives this required configuration will maintain that configuration for as long as the Configuration Manager client continues to receive this policy from the management point.</span></span> 

<span data-ttu-id="e7e38-129">Microsoft Endpoint Configuration Manager を使用してエンドポイントをオンボードするには、以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e7e38-129">Follow the steps below to onboard endpoints using Microsoft Endpoint Configuration Manager.</span></span>

1. <span data-ttu-id="e7e38-130">Microsoft Endpoint Configuration Manager コンソールで、[アセット] と [コンプライアンス **の概要] \> デバイス コレクション \> に移動します**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-130">In Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Device Collections**.</span></span>            

    ![Microsoft Endpoint Configuration Manager ウィザード 1 のイメージ](images/configmgr-device-collections.png)

2. <span data-ttu-id="e7e38-132">[デバイス コレクション] **を右クリックし** 、[デバイス コレクション **の作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-132">Right Click **Device Collection** and select **Create Device Collection**.</span></span>

    ![Microsoft Endpoint Configuration Manager ウィザード 2 のイメージ](images/configmgr-create-device-collection.png)

3. <span data-ttu-id="e7e38-134">[名前]**と [制限\*\*\*\*コレクション] を指定し、[** 次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-134">Provide a **Name** and **Limiting Collection**, then select **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager ウィザード 3 のイメージ](images/configmgr-limiting-collection.png)

4. <span data-ttu-id="e7e38-136">[ルール **の追加] を選択** し、[ **クエリ ルール] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-136">Select **Add Rule** and choose **Query Rule**.</span></span>

    ![Microsoft Endpoint Configuration Manager ウィザード 4 のイメージ](images/configmgr-query-rule.png)

5.  <span data-ttu-id="e7e38-138">[直接 **メンバーシップ ウィザード** ] で **[次へ] をクリックし** 、[クエリ ステートメントの **編集] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-138">Click **Next** on the **Direct Membership Wizard** and click on **Edit Query Statement**.</span></span>

     ![Microsoft Endpoint Configuration Manager ウィザードのイメージ 5](images/configmgr-direct-membership.png)

6. <span data-ttu-id="e7e38-140">[ **条件] を** 選択し、星のアイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="e7e38-140">Select **Criteria** and then choose the star icon.</span></span>

     ![Microsoft Endpoint Configuration Manager ウィザード 6 のイメージ](images/configmgr-criteria.png)

7. <span data-ttu-id="e7e38-142">条件の種類を **単純な** 値として保持し、オペレーティング システム **-** ビルド番号 、演算子の値が **14393** 以上の場合は、OK をクリックする場所を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-142">Keep criterion type as **simple value**, choose where as **Operating System - build number**, operator as **is greater than or equal to** and value **14393** and click on **OK**.</span></span>

    ![Microsoft Endpoint Configuration Manager ウィザード 7 のイメージ](images/configmgr-simple-value.png)

8. <span data-ttu-id="e7e38-144">[次 **へ] と [** 閉じる] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-144">Select **Next** and **Close**.</span></span>

    ![Microsoft Endpoint Configuration Manager ウィザード 8 のイメージ](images/configmgr-membership-rules.png)

9. <span data-ttu-id="e7e38-146">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7e38-146">Select **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager ウィザードのイメージ 9](images/configmgr-confirm.png)


<span data-ttu-id="e7e38-148">このタスクを完了すると、環境内のすべての Windows 10 エンドポイントを持つデバイス コレクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e7e38-148">After completing this task, you now have a device collection with all the Windows 10 endpoints in the environment.</span></span> 


## <a name="step-2-configure-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="e7e38-149">手順 2: Microsoft Defender for Endpoint の機能を構成する</span><span class="sxs-lookup"><span data-stu-id="e7e38-149">Step 2: Configure Microsoft Defender for Endpoint capabilities</span></span> 
<span data-ttu-id="e7e38-150">このセクションでは、Windows デバイスで Microsoft Endpoint Configuration Manager を使用して次の機能を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e7e38-150">This section guides you in configuring the following capabilities using Microsoft Endpoint Configuration Manager on Windows devices:</span></span>

- [<span data-ttu-id="e7e38-151">**エンドポイントの検出および応答**</span><span class="sxs-lookup"><span data-stu-id="e7e38-151">**Endpoint detection and response**</span></span>](#endpoint-detection-and-response)
- [<span data-ttu-id="e7e38-152">**次世代の保護**</span><span class="sxs-lookup"><span data-stu-id="e7e38-152">**Next-generation protection**</span></span>](#next-generation-protection)
- [<span data-ttu-id="e7e38-153">**攻撃面の縮小**</span><span class="sxs-lookup"><span data-stu-id="e7e38-153">**Attack surface reduction**</span></span>](#attack-surface-reduction)


### <a name="endpoint-detection-and-response"></a><span data-ttu-id="e7e38-154">エンドポイントの検出および応答</span><span class="sxs-lookup"><span data-stu-id="e7e38-154">Endpoint detection and response</span></span>
#### <a name="windows-10"></a><span data-ttu-id="e7e38-155">Windows 10</span><span class="sxs-lookup"><span data-stu-id="e7e38-155">Windows 10</span></span>
<span data-ttu-id="e7e38-156">Microsoft Defender セキュリティ センター内から、System Center Configuration Manager でポリシーを作成し、そのポリシーを Windows 10 デバイスに展開するために使用できる '.onboarding' ポリシーをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="e7e38-156">From within the Microsoft Defender Security Center it is possible to download the '.onboarding' policy that can be used to create the policy in System Center Configuration Manager and deploy that policy to Windows 10 devices.</span></span>

1. <span data-ttu-id="e7e38-157">Microsoft Defender セキュリティ センター ポータルで、[設定] を選択 [し、[オンボーディング] を選択します](https://securitycenter.windows.com/preferences2/onboarding)。</span><span class="sxs-lookup"><span data-stu-id="e7e38-157">From a Microsoft Defender Security Center Portal, select [Settings and then Onboarding](https://securitycenter.windows.com/preferences2/onboarding).</span></span>



2. <span data-ttu-id="e7e38-158">[展開方法] で、サポートされている **バージョンの Microsoft Endpoint Configuration Manager を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-158">Under Deployment method select the supported version of **Microsoft Endpoint Configuration Manager**.</span></span>

    ![Microsoft Defender for Endpoint オンボーディング ウィザード 10 のイメージ](images/mdatp-onboarding-wizard.png)

3. <span data-ttu-id="e7e38-160">[パッケージ **のダウンロード] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-160">Select **Download package**.</span></span>

    ![Microsoft Defender for Endpoint オンボーディング ウィザードのイメージ11](images/mdatp-download-package.png)

4. <span data-ttu-id="e7e38-162">パッケージをアクセス可能な場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="e7e38-162">Save the package to an accessible location.</span></span>
5. <span data-ttu-id="e7e38-163">Microsoft Endpoint Configuration Manager で、[アセットとコンプライアンス] に移動し、[>の概要> Microsoft Defender ATP ポリシー> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-163">In  Microsoft Endpoint Configuration Manager, navigate to: **Assets and Compliance > Overview > Endpoint Protection > Microsoft Defender ATP Policies**.</span></span>

6. <span data-ttu-id="e7e38-164">[Microsoft **Defender ATP ポリシー] を右クリックし、[Microsoft** Defender ATP ポリシー **の作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-164">Right-click **Microsoft Defender ATP Policies** and select **Create Microsoft Defender ATP Policy**.</span></span>

    ![Microsoft Endpoint Configuration Manager ウィザード 12 のイメージ](images/configmgr-create-policy.png)

7. <span data-ttu-id="e7e38-166">名前と説明を入力し、[ **オン** ボーディング] が選択されている場合は、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-166">Enter the name and description, verify **Onboarding** is selected, then select **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager ウィザード 13 のイメージ](images/configmgr-policy-name.png)


8. <span data-ttu-id="e7e38-168">[ **参照**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7e38-168">Click **Browse**.</span></span>

9. <span data-ttu-id="e7e38-169">上記の手順 4 からダウンロードしたファイルの場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="e7e38-169">Navigate to the location of the downloaded file from step 4 above.</span></span>

10. <span data-ttu-id="e7e38-170">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7e38-170">Click **Next**.</span></span>
11. <span data-ttu-id="e7e38-171">適切なサンプル (None または All ファイルの種類)**を使用\*\*\*\*してエージェントを構成します**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-171">Configure the Agent with the appropriate samples (**None** or **All file types**).</span></span>

    ![構成設定のイメージ1](images/configmgr-config-settings.png)

12. <span data-ttu-id="e7e38-173">適切な利用統計情報 (標準または **迅速) を\*\*\*\*選択し**、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-173">Select the appropriate telemetry (**Normal** or **Expedited**) then click **Next**.</span></span>

    ![構成設定のイメージ2](images/configmgr-telemetry.png)

14. <span data-ttu-id="e7e38-175">構成を確認し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-175">Verify the configuration, then click **Next**.</span></span>

     ![構成設定のイメージ 3](images/configmgr-verify-configuration.png)

15. <span data-ttu-id="e7e38-177">ウィザードが **完了したら** 、[閉じる] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7e38-177">Click **Close** when the Wizard completes.</span></span>

16.  <span data-ttu-id="e7e38-178">Microsoft Endpoint Configuration Manager コンソールで、作成した Defender for Endpoint ポリシーを右クリックし、[展開] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-178">In the Microsoft Endpoint Configuration Manager console, right-click the Defender for Endpoint policy you just created and select **Deploy**.</span></span>

     ![構成設定のイメージ 4](images/configmgr-deploy.png)

17. <span data-ttu-id="e7e38-180">右側のパネルで、前に作成したコレクションを選択し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-180">On the right panel, select the previously created collection and click **OK**.</span></span>

    ![構成設定のイメージ5](images/configmgr-select-collection.png)


#### <a name="previous-versions-of-windows-client-windows-7-and-windows-81"></a><span data-ttu-id="e7e38-182">以前のバージョンの Windows クライアント (Windows 7 および Windows 8.1)</span><span class="sxs-lookup"><span data-stu-id="e7e38-182">Previous versions of Windows Client (Windows 7 and Windows 8.1)</span></span>
<span data-ttu-id="e7e38-183">以前のバージョンの Windows のオンボーディングに必要な Defender for Endpoint Workspace ID と Workspace Key を識別するには、以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e7e38-183">Follow the steps below to identify the Defender for Endpoint Workspace ID and Workspace Key, that will be required for the onboarding of previous versions of Windows.</span></span>

1. <span data-ttu-id="e7e38-184">Microsoft Defender セキュリティ センター ポータルで、[オンボーディング **の設定] >選択します**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-184">From a Microsoft Defender Security Center Portal, select **Settings > Onboarding**.</span></span>

2. <span data-ttu-id="e7e38-185">[オペレーティング システム] で、[Windows 7 SP1 **8.1] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-185">Under operating system choose **Windows 7 SP1 and 8.1**.</span></span>

3. <span data-ttu-id="e7e38-186">ワークスペース **ID とワークスペース キー\*\*\*\*をコピーして** 保存します。</span><span class="sxs-lookup"><span data-stu-id="e7e38-186">Copy the **Workspace ID** and **Workspace Key** and save them.</span></span> <span data-ttu-id="e7e38-187">これらは、プロセスの後半で使用されます。</span><span class="sxs-lookup"><span data-stu-id="e7e38-187">They will be used later in the process.</span></span>

    ![オンボーディングのイメージ](images/91b738e4b97c4272fd6d438d8c2d5269.png)

4. <span data-ttu-id="e7e38-189">Microsoft 監視エージェント (MMA) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="e7e38-189">Install the Microsoft Monitoring Agent (MMA).</span></span> <br>
    <span data-ttu-id="e7e38-190">MMA は現在 (2019 年 1 月現在) 次の Windows オペレーティング システムでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e7e38-190">MMA is currently (as of January 2019) supported on the following Windows Operating Systems:</span></span>

    -   <span data-ttu-id="e7e38-191">サーバー SKU: Windows Server 2008 SP1 以降</span><span class="sxs-lookup"><span data-stu-id="e7e38-191">Server SKUs: Windows Server 2008 SP1 or Newer</span></span>

    -   <span data-ttu-id="e7e38-192">クライアント SKU: Windows 7 SP1以降</span><span class="sxs-lookup"><span data-stu-id="e7e38-192">Client SKUs: Windows 7 SP1 and later</span></span>

    <span data-ttu-id="e7e38-193">MMA エージェントを Windows デバイスにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7e38-193">The MMA agent will need to be installed on Windows devices.</span></span> <span data-ttu-id="e7e38-194">エージェントをインストールするには、MMA を使用してデータ[](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)を収集するために、一部のシステムでカスタマー エクスペリエンスと診断テレメトリの更新プログラムをダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7e38-194">To install the agent, some systems will need to download the [Update for customer experience and diagnostic telemetry](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) in order to collect the data with MMA.</span></span> <span data-ttu-id="e7e38-195">これらのシステム バージョンには、次のものが含まれますが、これらに限定されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="e7e38-195">These system versions include but may not be limited to:</span></span>

    -   <span data-ttu-id="e7e38-196">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="e7e38-196">Windows 8.1</span></span>

    -   <span data-ttu-id="e7e38-197">Windows 7</span><span class="sxs-lookup"><span data-stu-id="e7e38-197">Windows 7</span></span>

    -   <span data-ttu-id="e7e38-198">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="e7e38-198">Windows Server 2016</span></span>

    -   <span data-ttu-id="e7e38-199">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="e7e38-199">Windows Server 2012 R2</span></span>

    -   <span data-ttu-id="e7e38-200">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="e7e38-200">Windows Server 2008 R2</span></span>

    <span data-ttu-id="e7e38-201">具体的には、次Windows 7 SP1パッチをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7e38-201">Specifically, for Windows 7 SP1, the following patches must be installed:</span></span>

    -   <span data-ttu-id="e7e38-202">[KB4074598 のインストール](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="e7e38-202">Install [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>

    -   <span data-ttu-id="e7e38-203">[4.5 .NET Framework以降](https://www.microsoft.com/download/details.aspx?id=30653)**)** または 
         [KB3154518 のいずれかをインストールします](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)。</span><span class="sxs-lookup"><span data-stu-id="e7e38-203">Install either [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) **or**
        [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework).</span></span>
        <span data-ttu-id="e7e38-204">両方を同じシステムにインストールしない。</span><span class="sxs-lookup"><span data-stu-id="e7e38-204">Do not install both on the same system.</span></span>

5. <span data-ttu-id="e7e38-205">プロキシを使用してインターネットに接続する場合は、「プロキシ設定の構成」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7e38-205">If you're using a proxy to connect to the Internet see the Configure proxy settings section.</span></span>

<span data-ttu-id="e7e38-206">完了すると、1 時間以内にポータルにオンボード エンドポイントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7e38-206">Once completed, you should see onboarded endpoints in the portal within an hour.</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="e7e38-207">次世代の保護</span><span class="sxs-lookup"><span data-stu-id="e7e38-207">Next generation protection</span></span> 
<span data-ttu-id="e7e38-208">Windows Defender ウイルス対策は、デスクトップ、ポータブル コンピューター、サーバーを対象に次世代の保護機能を提供する、組み込みのマルウェア対策ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="e7e38-208">Microsoft Defender Antivirus is a built-in antimalware solution that provides next generation protection for desktops, portable computers, and servers.</span></span>

1. <span data-ttu-id="e7e38-209">Microsoft Endpoint Configuration Manager コンソールで、[アセットとコンプライアンスの概要 エンドポイント保護マルウェア対策ポリシー] に移動し、[マルウェア対策ポリシーの作成]**を選択します**。 **\> \> \>**</span><span class="sxs-lookup"><span data-stu-id="e7e38-209">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Antimalware Polices** and choose **Create Antimalware Policy**.</span></span>

    ![マルウェア対策ポリシーのイメージ](images/9736e0358e86bc778ce1bd4c516adb8b.png)

2. <span data-ttu-id="e7e38-211">[**スケジュールされたスキャン\*\*\*\*]、[** スキャン設定]、[既定のアクション]、[リアルタイム保護]、[除外設定]、[詳細設定]、[脅威の上書き]、**クラウド保護サービス** とセキュリティ インテリジェンスの更新を選択し **、[OK] を選択します**。   </span><span class="sxs-lookup"><span data-stu-id="e7e38-211">Select **Scheduled scans**, **Scan settings**, **Default actions**, **Real-time protection**, **Exclusion settings**, **Advanced**, **Threat overrides**, **Cloud Protection Service** and **Security intelligence   updates** and choose **OK**.</span></span>

    ![次世代保護ウィンドウのイメージ 1](images/1566ad81bae3d714cc9e0d47575a8cbd.png)

    <span data-ttu-id="e7e38-213">特定の業界または一部の企業のお客様は、ウイルス対策の構成方法に関する特定のニーズを持っている場合があります。</span><span class="sxs-lookup"><span data-stu-id="e7e38-213">In certain industries or some select enterprise customers might have specific needs on how Antivirus is configured.</span></span>

  
    [<span data-ttu-id="e7e38-214">クイック スキャンとフル スキャン、およびカスタム スキャン</span><span class="sxs-lookup"><span data-stu-id="e7e38-214">Quick scan versus full scan and custom scan</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/scheduled-catch-up-scans-microsoft-defender-antivirus#quick-scan-versus-full-scan-and-custom-scan)

    <span data-ttu-id="e7e38-215">詳細については [、「Windows Security 構成フレームワーク」を参照してください。](https://docs.microsoft.com/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)</span><span class="sxs-lookup"><span data-stu-id="e7e38-215">For more details, see [Windows Security configuration framework](https://docs.microsoft.com/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)</span></span>
  
    ![次世代保護ウィンドウ 2 のイメージ](images/cd7daeb392ad5a36f2d3a15d650f1e96.png)

    ![次世代保護ウィンドウのイメージ 3](images/36c7c2ed737f2f4b54918a4f20791d4b.png)

    ![次世代保護ウィンドウのイメージ 4](images/a28afc02c1940d5220b233640364970c.png)

    ![次世代保護ウィンドウのイメージ 5](images/5420a8790c550f39f189830775a6d4c9.png)

    ![次世代保護ウィンドウのイメージ 6](images/33f08a38f2f4dd12a364f8eac95e8c6b.png)

    ![次世代保護ウィンドウのイメージ 7](images/41b9a023bc96364062c2041a8f5c344e.png)

    ![次世代保護ウィンドウ 8 のイメージ](images/945c9c5d66797037c3caeaa5c19f135c.png)

    ![次世代保護ウィンドウのイメージ 9](images/3876ca687391bfc0ce215d221c683970.png)

3. <span data-ttu-id="e7e38-224">新しく作成したマルウェア対策ポリシーを右クリックし、[展開] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-224">Right-click on the newly created antimalware policy and select **Deploy**.</span></span>

    ![次世代保護ウィンドウ 10 のイメージ](images/f5508317cd8c7870627cb4726acd5f3d.png)

4. <span data-ttu-id="e7e38-226">新しいマルウェア対策ポリシーを Windows 10 コレクションにターゲットに設定し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-226">Target the new antimalware policy to your Windows 10 collection and click **OK**.</span></span>

     ![次世代保護ウィンドウ 11 のイメージ](images/configmgr-select-collection.png)

<span data-ttu-id="e7e38-228">このタスクを完了すると、ウイルス対策プログラムの構成Windows Defender完了しました。</span><span class="sxs-lookup"><span data-stu-id="e7e38-228">After completing this task, you now have successfully configured Windows Defender Antivirus.</span></span>

### <a name="attack-surface-reduction"></a><span data-ttu-id="e7e38-229">攻撃面の縮小</span><span class="sxs-lookup"><span data-stu-id="e7e38-229">Attack surface reduction</span></span>
<span data-ttu-id="e7e38-230">Defender for Endpoint の攻撃表面の縮小の柱には、Exploit Guard で使用できる機能セットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e7e38-230">The attack surface reduction pillar of Defender for Endpoint includes the feature set that is available under Exploit Guard.</span></span> <span data-ttu-id="e7e38-231">攻撃表面の縮小 (ASR) ルール、フォルダー アクセスの制御、ネットワーク保護、エクスプロイト保護。</span><span class="sxs-lookup"><span data-stu-id="e7e38-231">Attack surface reduction (ASR) rules, Controlled Folder Access, Network Protection and Exploit Protection.</span></span> 

<span data-ttu-id="e7e38-232">これらの機能はすべて監査モードとブロック モードを提供します。</span><span class="sxs-lookup"><span data-stu-id="e7e38-232">All these features provide an audit mode and a block mode.</span></span> <span data-ttu-id="e7e38-233">監査モードでは、エンド ユーザーに影響はありません。</span><span class="sxs-lookup"><span data-stu-id="e7e38-233">In audit mode there is no end-user impact.</span></span> <span data-ttu-id="e7e38-234">これは、追加のテレメトリを収集し、Microsoft Defender セキュリティ センターで利用できる方法です。</span><span class="sxs-lookup"><span data-stu-id="e7e38-234">All it does is collect additional telemetry and make it available in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="e7e38-235">展開の目的は、セキュリティ コントロールをブロック モードにステップ バイ ステップで移動する方法です。</span><span class="sxs-lookup"><span data-stu-id="e7e38-235">The goal with a deployment is to step-by-step move security controls into block mode.</span></span>

<span data-ttu-id="e7e38-236">監査モードで ASR ルールを設定するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="e7e38-236">To set ASR rules in Audit mode:</span></span>

1. <span data-ttu-id="e7e38-237">Microsoft Endpoint Configuration Manager コンソールで、[Assets and Compliance Overview Endpoint Protection] に移動し **\> \> \> 、[Exploit Guard** Windows Defender作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-237">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

   ![Microsoft Endpoint Configuration Manager console0 のイメージ](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2.  <span data-ttu-id="e7e38-239">[攻撃 **表面の縮小] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-239">Select **Attack Surface Reduction**.</span></span>
   

3. <span data-ttu-id="e7e38-240">ルールを [監査] に **設定し、[** 次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-240">Set rules to **Audit** and click **Next**.</span></span>


    ![Microsoft Endpoint Configuration Manager console1 のイメージ](images/d18e40c9e60aecf1f9a93065cb7567bd.png)

4. <span data-ttu-id="e7e38-242">[次へ] をクリックして、新しい Exploit Guard ポリシーを **確認します**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-242">Confirm the new Exploit Guard policy by clicking on **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager コンソール 2 のイメージ](images/0a6536f2c4024c08709cac8fcf800060.png)

    
5. <span data-ttu-id="e7e38-244">ポリシーが作成されると、[閉じる] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-244">Once the policy is created click **Close**.</span></span>

    ![Microsoft Endpoint Configuration Manager console3 のイメージ](images/95d23a07c2c8bc79176788f28cef7557.png)

    ![Microsoft Endpoint Manager コンソール 1 のイメージ](images/95d23a07c2c8bc79176788f28cef7557.png)
   

6.  <span data-ttu-id="e7e38-247">新しく作成したポリシーを右クリックし、[展開] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-247">Right-click on the newly created policy and choose **Deploy**.</span></span>
    
    ![Microsoft Endpoint Configuration Manager console4 のイメージ](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. <span data-ttu-id="e7e38-249">ポリシーを新しく作成した Windows 10 コレクションにターゲット設定し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-249">Target the policy to the newly created Windows 10 collection and click **OK**.</span></span>

    ![Microsoft Endpoint Configuration Manager console5 のイメージ](images/0ccfe3e803be4b56c668b220b51da7f7.png)

<span data-ttu-id="e7e38-251">このタスクを完了すると、監査モードで ASR ルールが正常に構成されました。</span><span class="sxs-lookup"><span data-stu-id="e7e38-251">After completing this task, you now have successfully configured ASR rules in audit mode.</span></span>  
  
<span data-ttu-id="e7e38-252">ASR ルールがエンドポイントに正しく適用されているかどうかを確認する追加の手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e7e38-252">Below are additional steps to verify whether ASR rules are correctly applied to endpoints.</span></span> <span data-ttu-id="e7e38-253">(これには数分かかる場合があります)</span><span class="sxs-lookup"><span data-stu-id="e7e38-253">(This may take few minutes)</span></span>


1. <span data-ttu-id="e7e38-254">Web ブラウザーからに移動します <https://securitycenter.windows.com> 。</span><span class="sxs-lookup"><span data-stu-id="e7e38-254">From a web browser, navigate to <https://securitycenter.windows.com>.</span></span>

2.  <span data-ttu-id="e7e38-255">左側 **のメニューから [構成** の管理] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7e38-255">Select **Configuration management** from left side menu.</span></span>

3. <span data-ttu-id="e7e38-256">[攻撃 **表面管理] パネルの [攻撃表面の** 管理に移動] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7e38-256">Click **Go to attack surface management** in the Attack surface management panel.</span></span> 
    
    ![攻撃表面管理のイメージ](images/security-center-attack-surface-mgnt-tile.png)

4. <span data-ttu-id="e7e38-258">攻撃表面 **縮小ルール** レポートの [構成] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7e38-258">Click **Configuration** tab in Attack surface reduction rules reports.</span></span> <span data-ttu-id="e7e38-259">各デバイスの ASR ルール構成の概要と ASR ルールの状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7e38-259">It shows ASR rules configuration overview and ASR rules status on each devices.</span></span>

    ![攻撃表面の縮小ルールレポートのスクリーンショット1](images/f91f406e6e0aae197a947d3b0e8b2d0d.png)

5. <span data-ttu-id="e7e38-261">各デバイスをクリックすると、ASR ルールの構成の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7e38-261">Click each device shows configuration details of ASR rules.</span></span>

    ![攻撃表面の縮小ルールレポートのスクリーンショット 2](images/24bfb16ed561cbb468bd8ce51130ca9d.png)

<span data-ttu-id="e7e38-263">詳細 [については、「オプティマイズ ASR ルールの展開と検出」](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-asr)   を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7e38-263">See [Optimize ASR rule deployment and detections](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-asr)   for more details.</span></span>  


#### <a name="set-network-protection-rules-in-audit-mode"></a><span data-ttu-id="e7e38-264">監査モードでネットワーク保護ルールを設定します。</span><span class="sxs-lookup"><span data-stu-id="e7e38-264">Set Network Protection rules in Audit mode:</span></span>
1. <span data-ttu-id="e7e38-265">Microsoft Endpoint Configuration Manager コンソールで、[Assets and Compliance Overview Endpoint Protection] に移動し **\> \> \> 、[Exploit Guard** Windows Defender作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-265">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and  Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

    ![スクリーンショット System Center Configuration Manager1](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. <span data-ttu-id="e7e38-267">[ネットワーク **保護] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-267">Select **Network protection**.</span></span>

3. <span data-ttu-id="e7e38-268">設定を [監査] に **設定し、[次** へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-268">Set the setting to **Audit** and click **Next**.</span></span> 

    ![スクリーンショット System Center Confirugatiom Manager2](images/c039b2e05dba1ade6fb4512456380c9f.png)

4. <span data-ttu-id="e7e38-270">[次へ] をクリックして、新しい Exploit Guard ポリシーを **確認します**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-270">Confirm the new Exploit Guard Policy by clicking **Next**.</span></span>
    
    ![スクリーンショット Exploit GUard policy1](images/0a6536f2c4024c08709cac8fcf800060.png)

5. <span data-ttu-id="e7e38-272">ポリシーが作成されると、[閉じる] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-272">Once the policy is created click on **Close**.</span></span>

    ![スクリーンショット Exploit GUard policy2](images/95d23a07c2c8bc79176788f28cef7557.png)

6. <span data-ttu-id="e7e38-274">新しく作成したポリシーを右クリックし、[展開] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-274">Right-click on the newly created policy and choose **Deploy**.</span></span>

    ![スクリーンショット Microsoft Endpoint Configuration Manager1](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. <span data-ttu-id="e7e38-276">新しく作成した Windows 10 コレクションのポリシーを選択し **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-276">Select the policy to the newly created Windows 10 collection and choose **OK**.</span></span>

    ![スクリーンショット Microsoft Endpoint Configuration Manager2](images/0ccfe3e803be4b56c668b220b51da7f7.png)



<span data-ttu-id="e7e38-278">このタスクを完了すると、監査モードでネットワーク保護が正常に構成されました。</span><span class="sxs-lookup"><span data-stu-id="e7e38-278">After completing this task, you now have successfully configured Network Protection in audit mode.</span></span>

#### <a name="to-set-controlled-folder-access-rules-in-audit-mode"></a><span data-ttu-id="e7e38-279">監査モードでフォルダー アクセスの制御ルールを設定するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e7e38-279">To set Controlled Folder Access rules in Audit mode:</span></span>

1. <span data-ttu-id="e7e38-280">Microsoft Endpoint Configuration Manager コンソールで、[Assets and Compliance Overview Endpoint Protection] に移動し **\> \> \> 、[Exploit Guard** Windows Defender作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-280">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

    ![Microsoft Endpoint Configuration Manager3 のスクリーンショット](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. <span data-ttu-id="e7e38-282">[フォルダー **アクセスの制御] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-282">Select **Controlled folder access**.</span></span>
    
3. <span data-ttu-id="e7e38-283">構成を [監査] に **設定し、[次** へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-283">Set the configuration to **Audit** and click **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager4 のスクリーンショット](images/a8b934dab2dbba289cf64fe30e0e8aa4.png)    
    
4. <span data-ttu-id="e7e38-285">[次へ] をクリックして、新しい Exploit Guard ポリシーを **確認します**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-285">Confirm the new Exploit Guard Policy by clicking on **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager5 のスクリーンショット](images/0a6536f2c4024c08709cac8fcf800060.png)

5. <span data-ttu-id="e7e38-287">ポリシーが作成されると、[閉じる] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-287">Once the policy is created click on **Close**.</span></span>

    ![Microsoft Endpoint Configuration Manager6 のスクリーンショット](images/95d23a07c2c8bc79176788f28cef7557.png)

6. <span data-ttu-id="e7e38-289">新しく作成したポリシーを右クリックし、[展開] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-289">Right-click on the newly created policy and choose **Deploy**.</span></span>

    ![Microsoft Endpoint Configuration Manager7 のスクリーンショット](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7.  <span data-ttu-id="e7e38-291">ポリシーを新しく作成した Windows 10 コレクションにターゲット設定し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-291">Target the policy to the newly created Windows 10 collection and click **OK**.</span></span>

    ![Microsoft Endpoint Configuration Manager8 のスクリーンショット](images/0ccfe3e803be4b56c668b220b51da7f7.png)

<span data-ttu-id="e7e38-293">監査モードでフォルダー アクセスの制御が正常に構成されました。</span><span class="sxs-lookup"><span data-stu-id="e7e38-293">You have now successfully configured Controlled folder access in audit mode.</span></span>

## <a name="related-topic"></a><span data-ttu-id="e7e38-294">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e7e38-294">Related topic</span></span>
- [<span data-ttu-id="e7e38-295">Microsoft Endpoint Manager を使用したオンボーディング</span><span class="sxs-lookup"><span data-stu-id="e7e38-295">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
