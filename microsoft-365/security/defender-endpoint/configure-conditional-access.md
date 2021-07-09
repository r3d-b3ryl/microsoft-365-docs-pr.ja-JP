---
title: Microsoft Defender for Endpoint で条件付きアクセスを構成する
description: 条件付きアクセスを実装するために Intune、Microsoft 365 Defender、Azure で実行する必要がある手順について説明します。
keywords: 条件付きアクセス、条件付きアクセス、デバイス リスク、リスク レベル、統合、Intune 統合
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
ms.technology: mde
ms.openlocfilehash: 2c9462fa0d4be4d6ff78ba3e5db2cd4fa71fef0b
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339516"
---
# <a name="configure-conditional-access-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="c6606-104">Microsoft Defender for Endpoint で条件付きアクセスを構成する</span><span class="sxs-lookup"><span data-stu-id="c6606-104">Configure Conditional Access in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c6606-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="c6606-105">**Applies to:**</span></span>
- [<span data-ttu-id="c6606-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c6606-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c6606-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c6606-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="c6606-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="c6606-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c6606-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="c6606-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="c6606-110">このセクションでは、条件付きアクセスを適切に実装するために必要なすべての手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="c6606-110">This section guides you through all the steps you need to take to properly implement Conditional Access.</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="c6606-111">開始する前に</span><span class="sxs-lookup"><span data-stu-id="c6606-111">Before you begin</span></span>
>[!WARNING]
><span data-ttu-id="c6606-112">このシナリオでは、登録されているデバイスAD Azure がサポートされていない点に注意することが重要です。</span><span class="sxs-lookup"><span data-stu-id="c6606-112">It's important to note that Azure AD registered devices is not supported in this scenario.</span></span></br>
><span data-ttu-id="c6606-113">Intune に登録されているデバイスだけがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c6606-113">Only Intune enrolled devices are supported.</span></span>


<span data-ttu-id="c6606-114">すべてのデバイスが Intune に登録されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6606-114">You need to make sure that all your devices are enrolled in Intune.</span></span> <span data-ttu-id="c6606-115">Intune にデバイスを登録するには、次のオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6606-115">You can use any of the following options to enroll devices in Intune:</span></span>


- <span data-ttu-id="c6606-116">IT 管理者: 自動登録を有効にする方法の詳細については、「登録」[を参照Windowsしてください。](/intune/windows-enroll#enable-windows-10-automatic-enrollment)</span><span class="sxs-lookup"><span data-stu-id="c6606-116">IT Admin: For more information on how to enabling auto-enrollment, see [Windows Enrollment](/intune/windows-enroll#enable-windows-10-automatic-enrollment)</span></span>
- <span data-ttu-id="c6606-117">エンド ユーザー: Intune にデバイスを登録する方法の詳細Windows 10 Intune にデバイスを登録するWindows 10[を参照してください。](/intune/quickstart-enroll-windows-device)</span><span class="sxs-lookup"><span data-stu-id="c6606-117">End-user: For more information on how to enroll your Windows 10 device in Intune, see [Enroll your Windows 10 device in Intune](/intune/quickstart-enroll-windows-device)</span></span>
- <span data-ttu-id="c6606-118">エンド ユーザーの代替: Azure AD ドメインへの参加の詳細については、「How [to: Plan your Azure AD参加実装」を参照してください](/azure/active-directory/devices/azureadjoin-plan)。</span><span class="sxs-lookup"><span data-stu-id="c6606-118">End-user alternative: For more information on joining an Azure AD domain, see [How to: Plan your Azure AD join implementation](/azure/active-directory/devices/azureadjoin-plan).</span></span>



<span data-ttu-id="c6606-119">Intune ポータル、Intune ポータル、および Azure Microsoft 365 Defenderポータルで実行するADがあります。</span><span class="sxs-lookup"><span data-stu-id="c6606-119">There are steps you'll need to take in Microsoft 365 Defender, the Intune portal, and Azure AD portal.</span></span>

<span data-ttu-id="c6606-120">これらのポータルにアクセスし、条件付きアクセスを実装するために必要な役割に注意することが重要です。</span><span class="sxs-lookup"><span data-stu-id="c6606-120">It's important to note the required roles to access these portals and implement Conditional access:</span></span>
- <span data-ttu-id="c6606-121">**Microsoft 365 Defender** - 統合を有効にするには、グローバル管理者の役割を持つポータルにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6606-121">**Microsoft 365 Defender** - You'll need to sign into the portal with a global administrator role to turn on the integration.</span></span>
- <span data-ttu-id="c6606-122">**Intune** - 管理アクセス許可を持つセキュリティ管理者権限でポータルにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6606-122">**Intune** - You'll need to sign in to the portal with security administrator rights with management permissions.</span></span> 
- <span data-ttu-id="c6606-123">**Azure ADポータル** - グローバル管理者、セキュリティ管理者、または条件付きアクセス管理者としてサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6606-123">**Azure AD portal** - You'll need to sign in as a global administrator, security administrator, or Conditional Access administrator.</span></span>


> [!NOTE]
> <span data-ttu-id="c6606-124">Intune が管理され、Azure Microsoft Intuneがデバイスに参加しているAD環境Windows 10があります。</span><span class="sxs-lookup"><span data-stu-id="c6606-124">You'll need a Microsoft Intune environment, with Intune managed and Azure AD joined Windows 10 devices.</span></span>

<span data-ttu-id="c6606-125">条件付きアクセスを有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c6606-125">Take the following steps to enable Conditional Access:</span></span>
- <span data-ttu-id="c6606-126">手順 1: デバイスから接続Microsoft IntuneオンMicrosoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c6606-126">Step 1: Turn on the Microsoft Intune connection from Microsoft 365 Defender</span></span>
- <span data-ttu-id="c6606-127">手順 2: Intune で Defender for Endpoint 統合を有効にする</span><span class="sxs-lookup"><span data-stu-id="c6606-127">Step 2: Turn on the Defender for Endpoint integration in Intune</span></span>
- <span data-ttu-id="c6606-128">手順 3: Intune でコンプライアンス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="c6606-128">Step 3: Create the compliance policy in Intune</span></span>
- <span data-ttu-id="c6606-129">手順 4: ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="c6606-129">Step 4: Assign the policy</span></span> 
- <span data-ttu-id="c6606-130">手順 5: 条件付きアクセス ポリシー AD Azure を作成する</span><span class="sxs-lookup"><span data-stu-id="c6606-130">Step 5: Create an Azure AD Conditional Access policy</span></span>


### <a name="step-1-turn-on-the-microsoft-intune-connection"></a><span data-ttu-id="c6606-131">手順 1: 接続を有効Microsoft Intuneする</span><span class="sxs-lookup"><span data-stu-id="c6606-131">Step 1: Turn on the Microsoft Intune connection</span></span>
1. <span data-ttu-id="c6606-132">ナビゲーション ウィンドウで、[エンドポイントの全般高度な **設定** 接続  >    >    >  **] を選択Microsoft Intune**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="c6606-132">In the navigation pane, select **Settings** > **Endpoints** > **General** > **Advanced features** > **Microsoft Intune connection**.</span></span>
2. <span data-ttu-id="c6606-133">[設定] Microsoft Intuneを [オン] に **切り替える**。</span><span class="sxs-lookup"><span data-stu-id="c6606-133">Toggle the Microsoft Intune setting to **On**.</span></span>
3. <span data-ttu-id="c6606-134">[設定 **の保存] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c6606-134">Click **Save preferences**.</span></span>


### <a name="step-2-turn-on-the-defender-for-endpoint-integration-in-intune"></a><span data-ttu-id="c6606-135">手順 2: Intune で Defender for Endpoint 統合を有効にする</span><span class="sxs-lookup"><span data-stu-id="c6606-135">Step 2: Turn on the Defender for Endpoint integration in Intune</span></span>
1. <span data-ttu-id="c6606-136">[Azure portal](https://portal.azure.com) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="c6606-136">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="c6606-137">[デバイス **コンプライアンス**  >  **] [Microsoft Defender ATP] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6606-137">Select **Device compliance** > **Microsoft Defender ATP**.</span></span>
3. <span data-ttu-id="c6606-138">Microsoft Defender advanced threat protection **Connect Windows 10.0.15063+** デバイスを On に設定 **します**。</span><span class="sxs-lookup"><span data-stu-id="c6606-138">Set **Connect Windows 10.0.15063+ devices to Microsoft Defender Advanced Threat Protection** to **On**.</span></span>
4. <span data-ttu-id="c6606-139">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6606-139">Click **Save**.</span></span>


### <a name="step-3-create-the-compliance-policy-in-intune"></a><span data-ttu-id="c6606-140">手順 3: Intune でコンプライアンス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="c6606-140">Step 3: Create the compliance policy in Intune</span></span>
1. <span data-ttu-id="c6606-141">Azure portal [で、[すべてのサービス](https://portal.azure.com)**]** を選択し **、Intune** でフィルター処理し、[**すべてのサービス]** を選択Microsoft Intune。</span><span class="sxs-lookup"><span data-stu-id="c6606-141">In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.</span></span>
2. <span data-ttu-id="c6606-142">[デバイス **コンプライアンス ポリシー**  >  **] [ポリシー**  >  **の作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6606-142">Select **Device compliance** > **Policies** > **Create policy**.</span></span>
3. <span data-ttu-id="c6606-143">[名前] **と [説明** ] を **入力します**。</span><span class="sxs-lookup"><span data-stu-id="c6606-143">Enter a **Name** and **Description**.</span></span>
4. <span data-ttu-id="c6606-144">[**プラットフォーム] で\*\*\*\*、[Windows 10] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6606-144">In **Platform**, select **Windows 10 and later**.</span></span>
5. <span data-ttu-id="c6606-145">[デバイス **の正常性] 設定** で、[デバイスの脅威レベル] または [デバイスの脅威レベル] の下にあるデバイスを希望する **レベルに設定** します。</span><span class="sxs-lookup"><span data-stu-id="c6606-145">In the **Device Health** settings, set **Require the device to be at or under the Device Threat Level** to your preferred level:</span></span>

   - <span data-ttu-id="c6606-146">**セキュリティ** 保護 : このレベルが最も安全です。</span><span class="sxs-lookup"><span data-stu-id="c6606-146">**Secured**: This level is the most secure.</span></span> <span data-ttu-id="c6606-147">デバイスは、既存の脅威を持ち、会社のリソースに引き続きアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c6606-147">The device cannot have any existing threats and still access company resources.</span></span> <span data-ttu-id="c6606-148">脅威が見つかった場合、デバイスは非準拠として評価されます。</span><span class="sxs-lookup"><span data-stu-id="c6606-148">If any threats are found, the device is evaluated as noncompliant.</span></span>
   - <span data-ttu-id="c6606-149">**低**: 低レベルの脅威だけが存在する場合、デバイスは準拠しています。</span><span class="sxs-lookup"><span data-stu-id="c6606-149">**Low**: The device is compliant if only low-level threats exist.</span></span> <span data-ttu-id="c6606-150">中程度または高い脅威レベルを持つデバイスは、準拠していません。</span><span class="sxs-lookup"><span data-stu-id="c6606-150">Devices with medium or high threat levels are not compliant.</span></span>
   - <span data-ttu-id="c6606-151">**中**: デバイスで検出された脅威が低または中程度の場合、デバイスは準拠しています。</span><span class="sxs-lookup"><span data-stu-id="c6606-151">**Medium**: The device is compliant if the threats found on the device are low or medium.</span></span> <span data-ttu-id="c6606-152">高レベルの脅威が検出された場合、デバイスは非準拠と判断されます。</span><span class="sxs-lookup"><span data-stu-id="c6606-152">If high-level threats are detected, the device is determined as noncompliant.</span></span>
   - <span data-ttu-id="c6606-153">**高**: このレベルは安全性が最も低く、すべての脅威レベルを許可します。</span><span class="sxs-lookup"><span data-stu-id="c6606-153">**High**: This level is the least secure, and allows all threat levels.</span></span> <span data-ttu-id="c6606-154">そのため、高、中、低の脅威レベルを持つデバイスは、準拠しているとみなされます。</span><span class="sxs-lookup"><span data-stu-id="c6606-154">So devices that with high, medium or low threat levels are considered compliant.</span></span>

6. <span data-ttu-id="c6606-155">**[OK]** を選択し、[**作成]** を選択して変更を保存します (ポリシーを作成します)。</span><span class="sxs-lookup"><span data-stu-id="c6606-155">Select **OK**, and **Create** to save your changes (and create the policy).</span></span>

### <a name="step-4-assign-the-policy"></a><span data-ttu-id="c6606-156">手順 4: ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="c6606-156">Step 4: Assign the policy</span></span>
1. <span data-ttu-id="c6606-157">Azure portal [で、[すべてのサービス](https://portal.azure.com)**]** を選択し **、Intune** でフィルター処理し、[**すべてのサービス]** を選択Microsoft Intune。</span><span class="sxs-lookup"><span data-stu-id="c6606-157">In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.</span></span>
2. <span data-ttu-id="c6606-158">[**デバイス コンプライアンス ポリシー**  >  **] を選択>** Microsoft Defender for Endpoint コンプライアンス ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c6606-158">Select **Device compliance** > **Policies**> select your Microsoft Defender for Endpoint compliance policy.</span></span>
3. <span data-ttu-id="c6606-159">**[割り当て]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6606-159">Select **Assignments**.</span></span>
4. <span data-ttu-id="c6606-160">ポリシーを割り当てるには、Azure ADグループを含めるか除外します。</span><span class="sxs-lookup"><span data-stu-id="c6606-160">Include or exclude your Azure AD groups to assign them the policy.</span></span>
5. <span data-ttu-id="c6606-161">ポリシーをグループに展開するには、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6606-161">To deploy the policy to the groups, select **Save**.</span></span> <span data-ttu-id="c6606-162">ポリシーの対象となるユーザー デバイスは、コンプライアンスについて評価されます。</span><span class="sxs-lookup"><span data-stu-id="c6606-162">The user devices targeted by the policy are evaluated for compliance.</span></span>

### <a name="step-5-create-an-azure-ad-conditional-access-policy"></a><span data-ttu-id="c6606-163">手順 5: 条件付きアクセス ポリシー AD Azure を作成する</span><span class="sxs-lookup"><span data-stu-id="c6606-163">Step 5: Create an Azure AD Conditional Access policy</span></span>
1. <span data-ttu-id="c6606-164">Azure portal [で、[条件付きアクセス](https://portal.azure.com)**] Azure Active Directory**  >  **ポリシーを**  >  **開きます**。</span><span class="sxs-lookup"><span data-stu-id="c6606-164">In the [Azure portal](https://portal.azure.com), open **Azure Active Directory** > **Conditional Access** > **New policy**.</span></span>
2. <span data-ttu-id="c6606-165">ポリシー名を入力 **し、[** ユーザーとグループ **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6606-165">Enter a policy **Name**, and select **Users and groups**.</span></span> <span data-ttu-id="c6606-166">[含める] または [除外] オプションを使用してポリシーのグループを追加し、[完了] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6606-166">Use the Include or Exclude options to add your groups for the policy, and select **Done**.</span></span>
3. <span data-ttu-id="c6606-167">[ **クラウド アプリ] を** 選択し、保護するアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="c6606-167">Select **Cloud apps**, and choose which apps to protect.</span></span> <span data-ttu-id="c6606-168">たとえば、[アプリの選択 **] を** 選択し、[オンライン] と **[Office 365 SharePoint]** **を** Office 365 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="c6606-168">For example, choose **Select apps**, and select **Office 365 SharePoint Online** and **Office 365 Exchange Online**.</span></span> <span data-ttu-id="c6606-169">[**完了**] を選んで変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="c6606-169">Select **Done** to save your changes.</span></span>

4. <span data-ttu-id="c6606-170">[**条件**  >  **クライアント アプリ] を** 選択して、アプリとブラウザーにポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="c6606-170">Select **Conditions** > **Client apps** to apply the policy to apps and browsers.</span></span> <span data-ttu-id="c6606-171">たとえば、[はい] **を選択** し、[ **ブラウザー** とモバイル アプリと **デスクトップ クライアント] を有効にします**。</span><span class="sxs-lookup"><span data-stu-id="c6606-171">For example, select **Yes**, and then enable **Browser** and **Mobile apps and desktop clients**.</span></span> <span data-ttu-id="c6606-172">[**完了**] を選んで変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="c6606-172">Select **Done** to save your changes.</span></span>

5. <span data-ttu-id="c6606-173">[許可 **] を** 選択して、デバイスのコンプライアンスに基づいて条件付きアクセスを適用します。</span><span class="sxs-lookup"><span data-stu-id="c6606-173">Select **Grant** to apply Conditional Access based on device compliance.</span></span> <span data-ttu-id="c6606-174">たとえば、[アクセスを許可 **するデバイス**  >  **に準拠としてマークする] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6606-174">For example, select **Grant access** > **Require device to be marked as compliant**.</span></span> <span data-ttu-id="c6606-175">[選択 **] を** 選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="c6606-175">Choose **Select** to save your changes.</span></span>

6. <span data-ttu-id="c6606-176">[ポリシー **を有効にする]** を選択し、[ **作成] を選択して** 変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="c6606-176">Select **Enable policy**, and then **Create** to save your changes.</span></span>

<span data-ttu-id="c6606-177">詳細については、「Intune での条件付きアクセスを使用した Microsoft Defender for Endpoint のコンプライアンスの [適用」を参照してください](/intune/advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="c6606-177">For more information, see [Enforce compliance for Microsoft Defender for Endpoint with Conditional Access in Intune](/intune/advanced-threat-protection).</span></span>

><span data-ttu-id="c6606-178">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="c6606-178">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c6606-179">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="c6606-179">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-belowfoldlink)
