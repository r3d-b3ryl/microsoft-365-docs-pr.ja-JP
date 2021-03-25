---
title: Microsoft Endpoint Manager を使用したオンボーディング
description: Microsoft エンドポイント マネージャーを使用して Microsoft Defender for Endpoint にオンボードする方法について説明します。
keywords: オンボーディング、構成、展開、展開、エンドポイント マネージャー、mdatp、高度な脅威保護、コレクションの作成、エンドポイント検出応答、次世代保護、攻撃表面の縮小、Microsoft エンドポイント マネージャー
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
ms.openlocfilehash: 9edcceca2f6cc7c2377eb388d7394a23dfbae99d
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186259"
---
# <a name="onboarding-using-microsoft-endpoint-manager"></a><span data-ttu-id="e15b5-104">Microsoft Endpoint Manager を使用したオンボーディング</span><span class="sxs-lookup"><span data-stu-id="e15b5-104">Onboarding using Microsoft Endpoint Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e15b5-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e15b5-105">**Applies to:**</span></span>
- [<span data-ttu-id="e15b5-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e15b5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e15b5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e15b5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="e15b5-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="e15b5-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e15b5-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="e15b5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="e15b5-110">この記事は展開ガイドの一部であり、オンボーディング方法の例として機能します。</span><span class="sxs-lookup"><span data-stu-id="e15b5-110">This article is part of the Deployment guide and acts as an example onboarding method.</span></span> 

<span data-ttu-id="e15b5-111">「計画 [」トピック](deployment-strategy.md) では、デバイスをサービスにオンボードする方法がいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="e15b5-111">In the [Planning](deployment-strategy.md) topic, there were several methods provided to onboard devices to the service.</span></span> <span data-ttu-id="e15b5-112">このトピックでは、クラウド ネイティブ アーキテクチャについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e15b5-112">This topic covers the cloud-native architecture.</span></span> 

<span data-ttu-id="e15b5-113">![クラウドネイティブ アーキテクチャのイメージ ](images/cloud-native-architecture.png)
 *環境アーキテクチャの図*</span><span class="sxs-lookup"><span data-stu-id="e15b5-113">![Image of cloud-native architecture](images/cloud-native-architecture.png)
*Diagram of environment architectures*</span></span>

<span data-ttu-id="e15b5-114">Defender for Endpoint はさまざまなエンドポイントとツールのオンボーディングをサポートしますが、この記事ではそれらをカバーしません。</span><span class="sxs-lookup"><span data-stu-id="e15b5-114">While Defender for Endpoint supports onboarding of various endpoints and tools, this article does not cover them.</span></span> <span data-ttu-id="e15b5-115">サポートされている他の展開ツールと方法を使用した一般的なオンボーディングの詳細については、「オンボードの概要 [」を参照してください](onboarding.md)。</span><span class="sxs-lookup"><span data-stu-id="e15b5-115">For information on general onboarding using other supported deployment tools and methods, see [Onboarding overview](onboarding.md).</span></span>


<span data-ttu-id="e15b5-116">[Microsoft Endpoint Manager は](https://docs.microsoft.com/mem/endpoint-manager-overview) 、複数のサービスを統合するソリューション プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="e15b5-116">[Microsoft Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview) is a solution platform that unifies several services.</span></span> <span data-ttu-id="e15b5-117">これには、 [クラウドベースのデバイス](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) 管理用の Microsoft Intune が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e15b5-117">It includes [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) for cloud-based device management.</span></span>


<span data-ttu-id="e15b5-118">このトピックでは、次のユーザーをガイドします。</span><span class="sxs-lookup"><span data-stu-id="e15b5-118">This topic guides users in:</span></span>
- <span data-ttu-id="e15b5-119">手順 1: Microsoft Endpoint Manager (MEM) でグループを作成してサービスにデバイスをオンボーディングし、構成を割り当てる</span><span class="sxs-lookup"><span data-stu-id="e15b5-119">Step 1: Onboarding devices to the service by creating a group in Microsoft Endpoint Manager (MEM) to assign configurations on</span></span>
- <span data-ttu-id="e15b5-120">手順 2: Microsoft Endpoint Manager を使用した Defender for Endpoint 機能の構成</span><span class="sxs-lookup"><span data-stu-id="e15b5-120">Step 2: Configuring Defender for Endpoint capabilities using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="e15b5-121">このオンボーディング ガイダンスでは、Microsoft Endpoint Manager を使用する際に実行する必要がある次の基本的な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="e15b5-121">This onboarding guidance will walk you through the following basic steps that you need to take when using Microsoft Endpoint Manager:</span></span>

-   [<span data-ttu-id="e15b5-122">ターゲット デバイスまたはユーザーの識別</span><span class="sxs-lookup"><span data-stu-id="e15b5-122">Identifying target devices or users</span></span>](#identify-target-devices-or-users)

    -   <span data-ttu-id="e15b5-123">Azure Active Directory グループの作成 (ユーザーまたはデバイス)</span><span class="sxs-lookup"><span data-stu-id="e15b5-123">Creating an Azure Active Directory group (User or Device)</span></span>

-   [<span data-ttu-id="e15b5-124">構成プロファイルの作成</span><span class="sxs-lookup"><span data-stu-id="e15b5-124">Creating a Configuration Profile</span></span>](#step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities)

    -   <span data-ttu-id="e15b5-125">Microsoft Endpoint Manager では、機能ごとに個別のポリシーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e15b5-125">In Microsoft Endpoint Manager, we'll guide you in creating a separate policy for each capability.</span></span>





## <a name="resources"></a><span data-ttu-id="e15b5-126">リソース</span><span class="sxs-lookup"><span data-stu-id="e15b5-126">Resources</span></span>


<span data-ttu-id="e15b5-127">プロセスの残りの部分に必要なリンクを次に示します。</span><span class="sxs-lookup"><span data-stu-id="e15b5-127">Here are the links you'll need for the rest of the process:</span></span>

-   [<span data-ttu-id="e15b5-128">MEM ポータル</span><span class="sxs-lookup"><span data-stu-id="e15b5-128">MEM portal</span></span>](https://aka.ms/memac)

-   [<span data-ttu-id="e15b5-129">セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="e15b5-129">Security Center</span></span>](https://securitycenter.windows.com/)

-   [<span data-ttu-id="e15b5-130">Intune セキュリティのベースライン</span><span class="sxs-lookup"><span data-stu-id="e15b5-130">Intune Security baselines</span></span>](https://docs.microsoft.com/mem/intune/protect/security-baseline-settings-defender-atp#microsoft-defender)

<span data-ttu-id="e15b5-131">Microsoft Endpoint Manager の詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e15b5-131">For more information about Microsoft Endpoint Manager, check out these resources:</span></span>
- <span data-ttu-id="e15b5-132">[[Microsoft Endpoint Manager] ページ](https://docs.microsoft.com/mem/)</span><span class="sxs-lookup"><span data-stu-id="e15b5-132">[Microsoft Endpoint Manager page](https://docs.microsoft.com/mem/)</span></span>
- [<span data-ttu-id="e15b5-133">Intune と ConfigMgr のコンバージェンスに関するブログ投稿</span><span class="sxs-lookup"><span data-stu-id="e15b5-133">Blog post on convergence of Intune and ConfigMgr</span></span>](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace/)
- [<span data-ttu-id="e15b5-134">MEM の概要ビデオ</span><span class="sxs-lookup"><span data-stu-id="e15b5-134">Introduction video on MEM</span></span>](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace)

## <a name="step-1-onboard-devices-by-creating-a-group-in-mem-to-assign-configurations-on"></a><span data-ttu-id="e15b5-135">手順 1: MEM で構成を割り当てるグループを作成してデバイスをオンボードする</span><span class="sxs-lookup"><span data-stu-id="e15b5-135">Step 1: Onboard devices by creating a group in MEM to assign configurations on</span></span>
### <a name="identify-target-devices-or-users"></a><span data-ttu-id="e15b5-136">ターゲット デバイスまたはユーザーを特定する</span><span class="sxs-lookup"><span data-stu-id="e15b5-136">Identify target devices or users</span></span>
<span data-ttu-id="e15b5-137">このセクションでは、構成を割り当てるテスト グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="e15b5-137">In this section, we will create a test group to assign your configurations on.</span></span>

>[!NOTE]
><span data-ttu-id="e15b5-138">Intune は Azure Active Directory (Azure Active Directory AD) グループを使用してデバイスとユーザーを管理します。</span><span class="sxs-lookup"><span data-stu-id="e15b5-138">Intune uses Azure Active Directory (Azure AD) groups to manage devices and users.</span></span> <span data-ttu-id="e15b5-139">Intune 管理者は、組織のニーズに合わせてグループを設定できます。</span><span class="sxs-lookup"><span data-stu-id="e15b5-139">As an Intune admin, you can set up groups to suit your organizational needs.</span></span><br>
<span data-ttu-id="e15b5-140">詳細については、「グループを追加して [ユーザーとデバイスを整理する」を参照してください](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)。</span><span class="sxs-lookup"><span data-stu-id="e15b5-140">For more information, see [Add groups to organize users and devices](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).</span></span>

### <a name="create-a-group"></a><span data-ttu-id="e15b5-141">グループを作成する</span><span class="sxs-lookup"><span data-stu-id="e15b5-141">Create a group</span></span>

1.  <span data-ttu-id="e15b5-142">MEM ポータルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e15b5-142">Open the MEM portal.</span></span>

2.  <span data-ttu-id="e15b5-143">[グループ **] を>新しいグループを開きます**。</span><span class="sxs-lookup"><span data-stu-id="e15b5-143">Open **Groups > New Group**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-144">![Microsoft Endpoint Manager portal1 のイメージ](images/66f724598d9c3319cba27f79dd4617a4.png)</span><span class="sxs-lookup"><span data-stu-id="e15b5-144">![Image of Microsoft Endpoint Manager portal1](images/66f724598d9c3319cba27f79dd4617a4.png)</span></span>

3.  <span data-ttu-id="e15b5-145">詳細を入力し、新しいグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="e15b5-145">Enter details and create a new group.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-146">![Microsoft Endpoint Manager portal2 のイメージ](images/b1e0206d675ad07db218b63cd9b9abc3.png)</span><span class="sxs-lookup"><span data-stu-id="e15b5-146">![Image of Microsoft Endpoint Manager portal2](images/b1e0206d675ad07db218b63cd9b9abc3.png)</span></span>

4.  <span data-ttu-id="e15b5-147">テスト ユーザーまたはデバイスを追加します。</span><span class="sxs-lookup"><span data-stu-id="e15b5-147">Add your test user or device.</span></span>

5.  <span data-ttu-id="e15b5-148">[グループ] **ウィンドウ>新しい** グループを開きます。</span><span class="sxs-lookup"><span data-stu-id="e15b5-148">From the **Groups > All groups** pane, open your new group.</span></span>

6.  <span data-ttu-id="e15b5-149">[メンバー  **] を>メンバーを追加します**。</span><span class="sxs-lookup"><span data-stu-id="e15b5-149">Select  **Members > Add members**.</span></span>

7.  <span data-ttu-id="e15b5-150">テスト ユーザーまたはデバイスを見つけて選択します。</span><span class="sxs-lookup"><span data-stu-id="e15b5-150">Find your test user or device and select it.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-151">![Microsoft Endpoint Manager portal3 のイメージ](images/149cbfdf221cdbde8159d0ab72644cd0.png)</span><span class="sxs-lookup"><span data-stu-id="e15b5-151">![Image of Microsoft Endpoint Manager portal3](images/149cbfdf221cdbde8159d0ab72644cd0.png)</span></span>

8.  <span data-ttu-id="e15b5-152">これで、テストグループにテストするメンバーが追加されました。</span><span class="sxs-lookup"><span data-stu-id="e15b5-152">Your testing group now has a member to test.</span></span>

## <a name="step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="e15b5-153">手順 2: Microsoft Defender for Endpoint の機能を構成する構成ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="e15b5-153">Step 2: Create configuration policies to configure Microsoft Defender for Endpoint capabilities</span></span>
<span data-ttu-id="e15b5-154">次のセクションでは、多数の構成ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e15b5-154">In the following section, you'll create a number of configuration policies.</span></span>

<span data-ttu-id="e15b5-155">最初に、Defender for Endpoint にオンボードするユーザーまたはデバイスのグループを選択する構成ポリシーを示します。</span><span class="sxs-lookup"><span data-stu-id="e15b5-155">First is a configuration policy to select which groups of users or devices will be onboarded to Defender for Endpoint:</span></span>

- [<span data-ttu-id="e15b5-156">エンドポイントの検出および応答</span><span class="sxs-lookup"><span data-stu-id="e15b5-156">Endpoint detection and response</span></span>](#endpoint-detection-and-response) 

<span data-ttu-id="e15b5-157">次に、いくつかの異なる種類のエンドポイント セキュリティ ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e15b5-157">Then you will continue by creating several different types of endpoint security policies:</span></span>

- [<span data-ttu-id="e15b5-158">次世代の保護</span><span class="sxs-lookup"><span data-stu-id="e15b5-158">Next-generation protection</span></span>](#next-generation-protection)
- [<span data-ttu-id="e15b5-159">攻撃面の縮小</span><span class="sxs-lookup"><span data-stu-id="e15b5-159">Attack surface reduction</span></span>](#attack-surface-reduction--attack-surface-reduction-rules)

### <a name="endpoint-detection-and-response"></a><span data-ttu-id="e15b5-160">エンドポイントの検出および応答</span><span class="sxs-lookup"><span data-stu-id="e15b5-160">Endpoint detection and response</span></span>

1.  <span data-ttu-id="e15b5-161">MEM ポータルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e15b5-161">Open the MEM portal.</span></span>

2.  <span data-ttu-id="e15b5-162">[エンドポイントの **検出と応答>エンドポイント セキュリティ] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="e15b5-162">Navigate to **Endpoint security > Endpoint detection and response**.</span></span> <span data-ttu-id="e15b5-163">[プロファイルの作成 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e15b5-163">Click on **Create Profile**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-164">![Microsoft Endpoint Manager portal4 のイメージ](images/58dcd48811147feb4ddc17212b7fe840.png)</span><span class="sxs-lookup"><span data-stu-id="e15b5-164">![Image of Microsoft Endpoint Manager portal4](images/58dcd48811147feb4ddc17212b7fe840.png)</span></span>

3.  <span data-ttu-id="e15b5-165">[ **プラットフォーム] で、[Windows 10 および Later, Profile - Endpoint detection and response and response >作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e15b5-165">Under **Platform, select Windows 10 and Later, Profile - Endpoint detection and response > Create**.</span></span>

4.  <span data-ttu-id="e15b5-166">名前と説明を入力し、[次へ] を  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e15b5-166">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-167">![Microsoft Endpoint Manager portal5 のイメージ](images/a5b2d23bdd50b160fef4afd25dda28d4.png)</span><span class="sxs-lookup"><span data-stu-id="e15b5-167">![Image of Microsoft Endpoint Manager portal5](images/a5b2d23bdd50b160fef4afd25dda28d4.png)</span></span>

5.  <span data-ttu-id="e15b5-168">必要に応じて設定を選択し、[次へ] を  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e15b5-168">Select settings as required, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-169">![Microsoft Endpoint Manager portal6 のイメージ](images/cea7e288b5d42a9baf1aef0754ade910.png)</span><span class="sxs-lookup"><span data-stu-id="e15b5-169">![Image of Microsoft Endpoint Manager portal6](images/cea7e288b5d42a9baf1aef0754ade910.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="e15b5-170">この例では、Defender for Endpoint が Intune に既に統合済みであるとして、これは自動的に設定されています。</span><span class="sxs-lookup"><span data-stu-id="e15b5-170">In this instance, this has been auto populated as Defender for Endpoint has already been integrated with Intune.</span></span> <span data-ttu-id="e15b5-171">統合の詳細については [、「Enable Microsoft Defender for Endpoint in Intune」を参照してください](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp)。</span><span class="sxs-lookup"><span data-stu-id="e15b5-171">For more information on the integration, see [Enable Microsoft Defender for Endpoint in Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp).</span></span>
    > 
    > <span data-ttu-id="e15b5-172">次の図は、Microsoft Defender for Endpoint が Intune と統合されていない場合に表示される例です。</span><span class="sxs-lookup"><span data-stu-id="e15b5-172">The following image is an example of what you'll see when Microsoft Defender for Endpoint is NOT integrated with Intune:</span></span>
    >
    > ![Microsoft Endpoint Manager portal7 のイメージ](images/2466460812371ffae2d19a10c347d6f4.png)

6.  <span data-ttu-id="e15b5-174">必要に応じてスコープ タグを追加し、[次へ] を  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e15b5-174">Add scope tags if necessary, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-175">![Microsoft Endpoint Manager portal8 のイメージ](images/ef844f52ec2c0d737ce793f68b5e8408.png)</span><span class="sxs-lookup"><span data-stu-id="e15b5-175">![Image of Microsoft Endpoint Manager portal8](images/ef844f52ec2c0d737ce793f68b5e8408.png)</span></span>

7.  <span data-ttu-id="e15b5-176">[含めるグループを選択して **グループを選択** する] をクリックしてテスト グループを追加し、[次へ] を  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e15b5-176">Add test group by clicking on **Select groups to include** and choose your group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-177">![Microsoft Endpoint Manager portal9 のイメージ](images/fc3525e20752da026ec9f46ab4fec64f.png)</span><span class="sxs-lookup"><span data-stu-id="e15b5-177">![Image of Microsoft Endpoint Manager portal9](images/fc3525e20752da026ec9f46ab4fec64f.png)</span></span>

8.  <span data-ttu-id="e15b5-178">確認して承諾し、[作成] を  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e15b5-178">Review and accept, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-179">![Microsoft Endpoint Manager portal10 のイメージ](images/289172dbd7bd34d55d24810d9d4d8158.png)</span><span class="sxs-lookup"><span data-stu-id="e15b5-179">![Image of Microsoft Endpoint Manager portal10](images/289172dbd7bd34d55d24810d9d4d8158.png)</span></span>

9.  <span data-ttu-id="e15b5-180">完了したポリシーを表示できます。</span><span class="sxs-lookup"><span data-stu-id="e15b5-180">You can view your completed policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-181">![Microsoft Endpoint Manager portal11 のイメージ](images/5a568b6878be8243ea2b9d82d41ed297.png)</span><span class="sxs-lookup"><span data-stu-id="e15b5-181">![Image of Microsoft Endpoint Manager portal11](images/5a568b6878be8243ea2b9d82d41ed297.png)</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="e15b5-182">次世代の保護</span><span class="sxs-lookup"><span data-stu-id="e15b5-182">Next-generation protection</span></span>

1.  <span data-ttu-id="e15b5-183">MEM ポータルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e15b5-183">Open the MEM portal.</span></span>

2.  <span data-ttu-id="e15b5-184">[ウイルス対策の **作成] >エンドポイント >に移動します**。</span><span class="sxs-lookup"><span data-stu-id="e15b5-184">Navigate to **Endpoint security > Antivirus > Create Policy**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-185">![Microsoft Endpoint Manager portal12 のイメージ](images/6b728d6e0d71108d768e368b416ff8ba.png)</span><span class="sxs-lookup"><span data-stu-id="e15b5-185">![Image of Microsoft Endpoint Manager portal12](images/6b728d6e0d71108d768e368b416ff8ba.png)</span></span>

3.  <span data-ttu-id="e15b5-186">[ **プラットフォーム] - [Windows 10 以降] の [Windows とプロファイル] の選択 – Microsoft Defender ウイルス対策>作成します**。</span><span class="sxs-lookup"><span data-stu-id="e15b5-186">Select **Platform - Windows 10 and Later - Windows and Profile – Microsoft Defender Antivirus > Create**.</span></span>

4.  <span data-ttu-id="e15b5-187">名前と説明を入力し、[次へ] を  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e15b5-187">Enter name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-188">![Microsoft Endpoint Manager portal13 のイメージ](images/a7d738dd4509d65407b7d12beaa3e917.png)</span><span class="sxs-lookup"><span data-stu-id="e15b5-188">![Image of Microsoft Endpoint Manager portal13](images/a7d738dd4509d65407b7d12beaa3e917.png)</span></span>

5.  <span data-ttu-id="e15b5-189">[構成 **設定] ページ** で、Microsoft Defender ウイルス対策 (クラウド保護、除外、セキュリティ保護、修復) に必要Real-Time設定します。</span><span class="sxs-lookup"><span data-stu-id="e15b5-189">In the **Configuration settings page**: Set the configurations you require for Microsoft Defender Antivirus (Cloud Protection, Exclusions, Real-Time Protection, and Remediation).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-190">![Microsoft Endpoint Manager portal14 のイメージ](images/3840b1576d6f79a1d72eb14760ef5e8c.png)</span><span class="sxs-lookup"><span data-stu-id="e15b5-190">![Image of Microsoft Endpoint Manager portal14](images/3840b1576d6f79a1d72eb14760ef5e8c.png)</span></span>

6.  <span data-ttu-id="e15b5-191">必要に応じてスコープ タグを追加し、[次へ] を  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e15b5-191">Add scope tags if necessary, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-192">![Microsoft Endpoint Manager portal15 のイメージ](images/2055e4f9b9141525c0eb681e7ba19381.png)</span><span class="sxs-lookup"><span data-stu-id="e15b5-192">![Image of Microsoft Endpoint Manager portal15](images/2055e4f9b9141525c0eb681e7ba19381.png)</span></span>

7.  <span data-ttu-id="e15b5-193">含めるグループを選択し、テスト グループに割り当て、[次へ] を  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e15b5-193">Select groups to include, assign to your test group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-194">![Microsoft Endpoint Manager portal16 のイメージ](images/48318a51adee06bff3908e8ad4944dc9.png)</span><span class="sxs-lookup"><span data-stu-id="e15b5-194">![Image of Microsoft Endpoint Manager portal16](images/48318a51adee06bff3908e8ad4944dc9.png)</span></span>

8.  <span data-ttu-id="e15b5-195">確認して作成し、[作成] を  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e15b5-195">Review and create, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-196">![Microsoft Endpoint Manager portal17 のイメージ](images/dfdadab79112d61bd3693d957084b0ec.png)</span><span class="sxs-lookup"><span data-stu-id="e15b5-196">![Image of Microsoft Endpoint Manager portal17](images/dfdadab79112d61bd3693d957084b0ec.png)</span></span>

9.  <span data-ttu-id="e15b5-197">作成した構成ポリシーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e15b5-197">You'll see the configuration policy you created.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-198">![Microsoft Endpoint Manager portal18 のイメージ](images/38180219e632d6e4ec7bd25a46398da8.png)</span><span class="sxs-lookup"><span data-stu-id="e15b5-198">![Image of Microsoft Endpoint Manager portal18](images/38180219e632d6e4ec7bd25a46398da8.png)</span></span>

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a><span data-ttu-id="e15b5-199">攻撃表面の縮小 – 攻撃表面の縮小ルール</span><span class="sxs-lookup"><span data-stu-id="e15b5-199">Attack Surface Reduction – Attack surface reduction rules</span></span>

1.  <span data-ttu-id="e15b5-200">MEM ポータルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e15b5-200">Open the MEM portal.</span></span>

2.  <span data-ttu-id="e15b5-201">[エンドポイント セキュリティ **] に移動>攻撃の表面を縮小します**。</span><span class="sxs-lookup"><span data-stu-id="e15b5-201">Navigate to **Endpoint security > Attack surface reduction**.</span></span>

3.  <span data-ttu-id="e15b5-202">[ポリシー  **の作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e15b5-202">Select  **Create Policy**.</span></span>

4.  <span data-ttu-id="e15b5-203">[ **プラットフォーム] - [Windows 10 以降] – [プロファイル] -**[攻撃表面縮小ルール] >を選択します。</span><span class="sxs-lookup"><span data-stu-id="e15b5-203">Select **Platform - Windows 10 and Later – Profile - Attack surface reduction rules > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-204">![Microsoft Endpoint Manager portal19 のイメージ](images/522d9bb4288dc9c1a957392b51384fdd.png)</span><span class="sxs-lookup"><span data-stu-id="e15b5-204">![Image of Microsoft Endpoint Manager portal19](images/522d9bb4288dc9c1a957392b51384fdd.png)</span></span>

5.  <span data-ttu-id="e15b5-205">名前と説明を入力し、[次へ] を  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e15b5-205">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-206">![Microsoft Endpoint Manager portal20 のイメージ](images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png)</span><span class="sxs-lookup"><span data-stu-id="e15b5-206">![Image of Microsoft Endpoint Manager portal20](images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png)</span></span>

6.  <span data-ttu-id="e15b5-207">[構成設定 **] ページ** で、攻撃表面の縮小ルールに必要な構成を設定し、[次へ] を  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e15b5-207">In the **Configuration settings page**: Set the configurations you require for Attack surface reduction rules, then select  **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e15b5-208">すべての攻撃表面縮小ルールを監査に構成します。</span><span class="sxs-lookup"><span data-stu-id="e15b5-208">We will be configuring all of the Attack surface reduction rules to Audit.</span></span>
    > 
    > <span data-ttu-id="e15b5-209">詳細については、「攻撃表面の [縮小ルール」を参照してください](attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="e15b5-209">For more information, see [Attack surface reduction rules](attack-surface-reduction.md).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-210">![Microsoft Endpoint Manager portal21 のイメージ](images/dd0c00efe615a64a4a368f54257777d0.png)</span><span class="sxs-lookup"><span data-stu-id="e15b5-210">![Image of Microsoft Endpoint Manager portal21](images/dd0c00efe615a64a4a368f54257777d0.png)</span></span>

7.  <span data-ttu-id="e15b5-211">必要に応じてスコープ タグを追加し、[次へ] を  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e15b5-211">Add Scope Tags as required, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-212">![Microsoft Endpoint Manager portal22 のイメージ](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span><span class="sxs-lookup"><span data-stu-id="e15b5-212">![Image of Microsoft Endpoint Manager portal22](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span></span>

8.  <span data-ttu-id="e15b5-213">テスト グループに含めるグループと割り当てるグループを選択し、[次へ] を  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e15b5-213">Select groups to include and assign to test group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-214">![Microsoft Endpoint Manager portal23 のイメージ](images/45cefc8e4e474321b4d47b4626346597.png)</span><span class="sxs-lookup"><span data-stu-id="e15b5-214">![Image of Microsoft Endpoint Manager portal23](images/45cefc8e4e474321b4d47b4626346597.png)</span></span>

9. <span data-ttu-id="e15b5-215">詳細を確認し、[作成] を  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e15b5-215">Review the details, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-216">![Microsoft Endpoint Manager portal24 のイメージ](images/2c2e87c5fedc87eba17be0cdeffdb17f.png)</span><span class="sxs-lookup"><span data-stu-id="e15b5-216">![Image of Microsoft Endpoint Manager portal24](images/2c2e87c5fedc87eba17be0cdeffdb17f.png)</span></span>

10. <span data-ttu-id="e15b5-217">ポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="e15b5-217">View the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-218">![Microsoft Endpoint Manager portal25 のイメージ](images/7a631d17cc42500dacad4e995823ffef.png)</span><span class="sxs-lookup"><span data-stu-id="e15b5-218">![Image of Microsoft Endpoint Manager portal25](images/7a631d17cc42500dacad4e995823ffef.png)</span></span>

### <a name="attack-surface-reduction--web-protection"></a><span data-ttu-id="e15b5-219">攻撃表面の縮小 – Web 保護</span><span class="sxs-lookup"><span data-stu-id="e15b5-219">Attack Surface Reduction – Web Protection</span></span>

1.  <span data-ttu-id="e15b5-220">MEM ポータルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e15b5-220">Open the MEM portal.</span></span>

2.  <span data-ttu-id="e15b5-221">[エンドポイント セキュリティ **] に移動>攻撃の表面を縮小します**。</span><span class="sxs-lookup"><span data-stu-id="e15b5-221">Navigate to **Endpoint security > Attack surface reduction**.</span></span>

3.  <span data-ttu-id="e15b5-222">[ポリシー  **の作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e15b5-222">Select  **Create Policy**.</span></span>

4.  <span data-ttu-id="e15b5-223">[Windows **10 および Later – Web 保護] を選択>作成します**。</span><span class="sxs-lookup"><span data-stu-id="e15b5-223">Select **Windows 10 and Later – Web protection > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-224">![Microsoft Endpoint Manager portal26 のイメージ](images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png)</span><span class="sxs-lookup"><span data-stu-id="e15b5-224">![Image of Microsoft Endpoint Manager portal26](images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png)</span></span>

5.  <span data-ttu-id="e15b5-225">名前と説明を入力し、[次へ] を  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e15b5-225">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-226">![Microsoft Endpoint Manager portal27 のイメージ](images/5be573a60cd4fa56a86a6668b62dd808.png)</span><span class="sxs-lookup"><span data-stu-id="e15b5-226">![Image of Microsoft Endpoint Manager portal27](images/5be573a60cd4fa56a86a6668b62dd808.png)</span></span>

6.  <span data-ttu-id="e15b5-227">[構成 **設定] ページで**、Web 保護に必要な構成を設定し、[次へ] を  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e15b5-227">In the **Configuration settings page**: Set the configurations you require for Web Protection, then select  **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e15b5-228">Web Protection をブロックに構成しています。</span><span class="sxs-lookup"><span data-stu-id="e15b5-228">We are configuring Web Protection to Block.</span></span>
    > 
    > <span data-ttu-id="e15b5-229">詳細については [、「Web Protection」を参照してください](web-protection-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="e15b5-229">For more information, see [Web Protection](web-protection-overview.md).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-230">![Microsoft Endpoint Manager portal28 のイメージ](images/6104aa33a56fab750cf30ecabef9f5b6.png)</span><span class="sxs-lookup"><span data-stu-id="e15b5-230">![Image of Microsoft Endpoint Manager portal28](images/6104aa33a56fab750cf30ecabef9f5b6.png)</span></span>

7.  <span data-ttu-id="e15b5-231">[次 **へ] で必要に応じてスコープ タグ>追加します**。</span><span class="sxs-lookup"><span data-stu-id="e15b5-231">Add **Scope Tags as required > Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-232">![Microsoft Endpoint Manager portal29 のイメージ](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span><span class="sxs-lookup"><span data-stu-id="e15b5-232">![Image of Microsoft Endpoint Manager portal29](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span></span>

8.  <span data-ttu-id="e15b5-233">[テスト **グループに割り当てる] を選択し、[次>します**。</span><span class="sxs-lookup"><span data-stu-id="e15b5-233">Select **Assign to test group > Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-234">![Microsoft Endpoint Manager portal30 のイメージ](images/45cefc8e4e474321b4d47b4626346597.png)</span><span class="sxs-lookup"><span data-stu-id="e15b5-234">![Image of Microsoft Endpoint Manager portal30](images/45cefc8e4e474321b4d47b4626346597.png)</span></span>

9.  <span data-ttu-id="e15b5-235">[レビュー **と作成] を選択>作成します**。</span><span class="sxs-lookup"><span data-stu-id="e15b5-235">Select **Review and Create > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-236">![Microsoft Endpoint Manager portal31 のイメージ](images/8ee0405f1a96c23d2eb6f737f11c1ae5.png)</span><span class="sxs-lookup"><span data-stu-id="e15b5-236">![Image of Microsoft Endpoint Manager portal31](images/8ee0405f1a96c23d2eb6f737f11c1ae5.png)</span></span>

10. <span data-ttu-id="e15b5-237">ポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="e15b5-237">View the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-238">![Microsoft Endpoint Manager portal32 のイメージ](images/e74f6f6c150d017a286e6ed3dffb7757.png)</span><span class="sxs-lookup"><span data-stu-id="e15b5-238">![Image of Microsoft Endpoint Manager portal32](images/e74f6f6c150d017a286e6ed3dffb7757.png)</span></span>

## <a name="validate-configuration-settings"></a><span data-ttu-id="e15b5-239">構成設定の検証</span><span class="sxs-lookup"><span data-stu-id="e15b5-239">Validate configuration settings</span></span>


### <a name="confirm-policies-have-been-applied"></a><span data-ttu-id="e15b5-240">ポリシーが適用されたのを確認する</span><span class="sxs-lookup"><span data-stu-id="e15b5-240">Confirm Policies have been applied</span></span>


<span data-ttu-id="e15b5-241">構成ポリシーが割り当てられると、適用に時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e15b5-241">Once the Configuration policy has been assigned, it will take some time to apply.</span></span>

<span data-ttu-id="e15b5-242">タイミングの詳細については、「Intune 構成情報 [」を参照してください](https://docs.microsoft.com/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned)。</span><span class="sxs-lookup"><span data-stu-id="e15b5-242">For information on timing, see [Intune configuration information](https://docs.microsoft.com/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).</span></span>

<span data-ttu-id="e15b5-243">構成ポリシーがテスト デバイスに適用されたと確認するには、構成ポリシーごとに次のプロセスに従います。</span><span class="sxs-lookup"><span data-stu-id="e15b5-243">To confirm that the configuration policy has been applied to your test device, follow the following process for each configuration policy.</span></span>

1.  <span data-ttu-id="e15b5-244">上記の手順に示すように、MEM ポータルを開き、関連するポリシーに移動します。</span><span class="sxs-lookup"><span data-stu-id="e15b5-244">Open the MEM portal and navigate to the relevant policy as shown in the steps above.</span></span> <span data-ttu-id="e15b5-245">次の例は、次世代の保護設定を示しています。</span><span class="sxs-lookup"><span data-stu-id="e15b5-245">The following example shows the next generation protection settings.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-246">[![Microsoft Endpoint Manager portal33 のイメージ ](images/43ab6aa74471ee2977e154a4a5ef2d39.png)](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="e15b5-246">[ ![Image of Microsoft Endpoint Manager portal33](images/43ab6aa74471ee2977e154a4a5ef2d39.png) ](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox)</span></span>

2.  <span data-ttu-id="e15b5-247">構成ポリシー **を選択して** 、ポリシーの状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="e15b5-247">Select  the **Configuration Policy** to view the policy status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-248">[![Microsoft Endpoint Manager portal34 のイメージ ](images/55ecaca0e4a022f0e29d45aeed724e6c.png)](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="e15b5-248">[ ![Image of Microsoft Endpoint Manager portal34](images/55ecaca0e4a022f0e29d45aeed724e6c.png) ](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)</span></span>

3.  <span data-ttu-id="e15b5-249">[  **デバイスの状態] を** 選択して、状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="e15b5-249">Select  **Device Status** to see the status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-250">[![Microsoft Endpoint Manager portal35 のイメージ ](images/18a50df62cc38749000dbfb48e9a4c9b.png)](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="e15b5-250">[ ![Image of Microsoft Endpoint Manager portal35](images/18a50df62cc38749000dbfb48e9a4c9b.png) ](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)</span></span>

4.  <span data-ttu-id="e15b5-251">[  **ユーザーの状態] を** 選択して、状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="e15b5-251">Select  **User Status** to see the status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-252">[![Microsoft Endpoint Manager portal36 のイメージ ](images/4e965749ff71178af8873bc91f9fe525.png)](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="e15b5-252">[ ![Image of Microsoft Endpoint Manager portal36](images/4e965749ff71178af8873bc91f9fe525.png) ](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)</span></span>

5.  <span data-ttu-id="e15b5-253">[  **設定ごとの状態] を選択** して、状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="e15b5-253">Select  **Per-setting status** to see the status.</span></span>

    >[!TIP]
    ><span data-ttu-id="e15b5-254">このビューは、別のポリシーと競合する設定を識別するのに非常に便利です。</span><span class="sxs-lookup"><span data-stu-id="e15b5-254">This view is very useful to identify any settings that conflict with another policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-255">[![Microsoft Endpoint Manager portal37 のイメージ ](images/42acc69d0128ed09804010bdbdf0a43c.png)](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="e15b5-255">[ ![Image of Microsoft Endpoint Manager portal37](images/42acc69d0128ed09804010bdbdf0a43c.png) ](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)</span></span>

### <a name="endpoint-detection-and-response"></a><span data-ttu-id="e15b5-256">エンドポイントの検出および応答</span><span class="sxs-lookup"><span data-stu-id="e15b5-256">Endpoint detection and response</span></span>


1.  <span data-ttu-id="e15b5-257">構成を適用する前に、Defender for Endpoint Protection サービスを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e15b5-257">Before applying the configuration, the Defender for Endpoint Protection service should not be started.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-258">[![[サービスのイメージ] パネル 1 ](images/b418a232a12b3d0a65fc98248dbb0e31.png)](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="e15b5-258">[ ![Image of Services panel1](images/b418a232a12b3d0a65fc98248dbb0e31.png) ](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)</span></span>

2.  <span data-ttu-id="e15b5-259">構成が適用された後、Defender for Endpoint Protection Service を開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e15b5-259">After the configuration has been applied, the Defender for Endpoint Protection Service should be started.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-260">[![[サービスのイメージ] パネル 2 ](images/a621b699899f1b41db211170074ea59e.png)](images/a621b699899f1b41db211170074ea59e.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="e15b5-260">[ ![Image of Services panel2](images/a621b699899f1b41db211170074ea59e.png) ](images/a621b699899f1b41db211170074ea59e.png#lightbox)</span></span>

3.  <span data-ttu-id="e15b5-261">サービスがデバイスで実行された後、デバイスは Microsoft Defender セキュリティ センターに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e15b5-261">After the services are running on the device, the device appears in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-262">[![Microsoft Defender セキュリティ センターのイメージ ](images/df0c64001b9219cfbd10f8f81a273190.png)](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="e15b5-262">[ ![Image of Microsoft Defender Security Center](images/df0c64001b9219cfbd10f8f81a273190.png) ](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="e15b5-263">次世代の保護</span><span class="sxs-lookup"><span data-stu-id="e15b5-263">Next-generation protection</span></span>

1.  <span data-ttu-id="e15b5-264">テスト デバイスにポリシーを適用する前に、以下に示すように手動で設定を管理できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e15b5-264">Before applying the policy on a test device, you should be able to manually manage the settings as shown below.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-265">![設定ページ 1 のイメージ](images/88efb4c3710493a53f2840c3eac3e3d3.png)</span><span class="sxs-lookup"><span data-stu-id="e15b5-265">![Image of setting page1](images/88efb4c3710493a53f2840c3eac3e3d3.png)</span></span>

2.  <span data-ttu-id="e15b5-266">ポリシーを適用した後、手動で設定を管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="e15b5-266">After the policy has been applied, you should not be able to manually manage the settings.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e15b5-267">次の図では **、クラウドによる保護を有効** に **し、[リアルタイム** 保護を有効にする] が管理として表示されています。</span><span class="sxs-lookup"><span data-stu-id="e15b5-267">In the following image **Turn on cloud-delivered protection** and **Turn on real-time protection** are being shown as managed.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e15b5-268">![設定ページ 2 のイメージ](images/9341428b2d3164ca63d7d4eaa5cff642.png)</span><span class="sxs-lookup"><span data-stu-id="e15b5-268">![Image of setting page2](images/9341428b2d3164ca63d7d4eaa5cff642.png)</span></span>

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a><span data-ttu-id="e15b5-269">攻撃表面の縮小 – 攻撃表面の縮小ルール</span><span class="sxs-lookup"><span data-stu-id="e15b5-269">Attack Surface Reduction – Attack surface reduction rules</span></span>


1.  <span data-ttu-id="e15b5-270">テスト デバイスにポリシーを適用する前に、PowerShell ウィンドウをペンで入力します `Get-MpPreference` 。</span><span class="sxs-lookup"><span data-stu-id="e15b5-270">Before applying the policy on a test device, pen a PowerShell Window and type `Get-MpPreference`.</span></span>

2.  <span data-ttu-id="e15b5-271">これは、コンテンツを含めずに次の行で応答する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e15b5-271">This should respond with the following lines with no content:</span></span>

    > <span data-ttu-id="e15b5-272">AttackSurfaceReductionOnlyExclusions:</span><span class="sxs-lookup"><span data-stu-id="e15b5-272">AttackSurfaceReductionOnlyExclusions:</span></span>
    > 
    > <span data-ttu-id="e15b5-273">AttackSurfaceReductionRules_Actions:</span><span class="sxs-lookup"><span data-stu-id="e15b5-273">AttackSurfaceReductionRules_Actions:</span></span>
    > 
    > <span data-ttu-id="e15b5-274">AttackSurfaceReductionRules_Ids:</span><span class="sxs-lookup"><span data-stu-id="e15b5-274">AttackSurfaceReductionRules_Ids:</span></span>

    ![コマンド ライン 1 のイメージ](images/cb0260d4b2636814e37eee427211fe71.png)

3.  <span data-ttu-id="e15b5-276">テスト デバイスにポリシーを適用した後、PowerShell Windows を開き、と入力します `Get-MpPreference` 。</span><span class="sxs-lookup"><span data-stu-id="e15b5-276">After applying the policy on a test device, open a PowerShell Windows and type `Get-MpPreference`.</span></span>

4.  <span data-ttu-id="e15b5-277">これは、次に示すように、コンテンツを含む次の行で応答する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e15b5-277">This should respond with the following lines with content as shown below:</span></span>

    ![コマンド ライン 2 のイメージ](images/619fb877791b1fc8bc7dfae1a579043d.png)

### <a name="attack-surface-reduction--web-protection"></a><span data-ttu-id="e15b5-279">攻撃表面の縮小 – Web 保護</span><span class="sxs-lookup"><span data-stu-id="e15b5-279">Attack Surface Reduction – Web Protection</span></span>

1.  <span data-ttu-id="e15b5-280">テスト デバイスで、PowerShell Windows を開き、と入力します `(Get-MpPreference).EnableNetworkProtection` 。</span><span class="sxs-lookup"><span data-stu-id="e15b5-280">On the test device, open a PowerShell Windows and type `(Get-MpPreference).EnableNetworkProtection`.</span></span>

2.  <span data-ttu-id="e15b5-281">これは、次に示すように 0 で応答する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e15b5-281">This should respond with a 0 as shown below.</span></span>

    ![コマンド ライン 3 のイメージ](images/196a8e194ac99d84221f405d0f684f8c.png)

3.  <span data-ttu-id="e15b5-283">ポリシーを適用した後、PowerShell Windows を開き、と入力します `(Get-MpPreference).EnableNetworkProtection` 。</span><span class="sxs-lookup"><span data-stu-id="e15b5-283">After applying the policy, open a PowerShell Windows and type `(Get-MpPreference).EnableNetworkProtection`.</span></span>

4.  <span data-ttu-id="e15b5-284">これは、次に示すように 1 で応答する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e15b5-284">This should respond with a 1 as shown below.</span></span>

    ![コマンド ライン 4 のイメージ](images/c06fa3bbc2f70d59dfe1e106cd9a4683.png)
