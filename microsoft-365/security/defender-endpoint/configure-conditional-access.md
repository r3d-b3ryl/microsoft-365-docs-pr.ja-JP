---
title: Microsoft Defender ATP で条件付きアクセスを構成する
description: 条件付きアクセスを実装するために Intune、Microsoft Defender セキュリティ センター、Azure で実行する必要がある手順について説明します。
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
ms.openlocfilehash: 0185d7875ac149909ef088d041383a1cf36a8a3a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165863"
---
# <a name="configure-conditional-access-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="af7f5-104">Microsoft Defender for Endpoint で条件付きアクセスを構成する</span><span class="sxs-lookup"><span data-stu-id="af7f5-104">Configure Conditional Access in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="af7f5-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="af7f5-105">**Applies to:**</span></span>
- [<span data-ttu-id="af7f5-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="af7f5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="af7f5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="af7f5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="af7f5-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="af7f5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="af7f5-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="af7f5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="af7f5-110">このセクションでは、条件付きアクセスを適切に実装するために必要なすべての手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="af7f5-110">This section guides you through all the steps you need to take to properly implement Conditional Access.</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="af7f5-111">はじめに</span><span class="sxs-lookup"><span data-stu-id="af7f5-111">Before you begin</span></span>
>[!WARNING]
><span data-ttu-id="af7f5-112">このシナリオでは、登録されているデバイスAD Azure がサポートされていない点に注意することが重要です。</span><span class="sxs-lookup"><span data-stu-id="af7f5-112">It's important to note that Azure AD registered devices is not supported in this scenario.</span></span></br>
><span data-ttu-id="af7f5-113">Intune に登録されているデバイスだけがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="af7f5-113">Only Intune enrolled devices are supported.</span></span>


<span data-ttu-id="af7f5-114">すべてのデバイスが Intune に登録されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="af7f5-114">You need to make sure that all your devices are enrolled in Intune.</span></span> <span data-ttu-id="af7f5-115">Intune にデバイスを登録するには、次のオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="af7f5-115">You can use any of the following options to enroll devices in Intune:</span></span>


- <span data-ttu-id="af7f5-116">IT 管理者: 自動登録を有効にする方法の詳細については、「Windows 登録」 [を参照してください。](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment)</span><span class="sxs-lookup"><span data-stu-id="af7f5-116">IT Admin: For more information on how to enabling auto-enrollment, see [Windows Enrollment](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment)</span></span>
- <span data-ttu-id="af7f5-117">エンド ユーザー: Intune に Windows 10 デバイスを登録する方法の詳細については、「Intune に Windows 10 デバイスを登録する」 [を参照してください。](https://docs.microsoft.com/intune/quickstart-enroll-windows-device)</span><span class="sxs-lookup"><span data-stu-id="af7f5-117">End-user: For more information on how to enroll your Windows 10 device in Intune, see [Enroll your Windows 10 device in Intune](https://docs.microsoft.com/intune/quickstart-enroll-windows-device)</span></span>
- <span data-ttu-id="af7f5-118">エンド ユーザーの代替: Azure AD ドメインへの参加の詳細については、「How [to: Plan your Azure AD参加実装」を参照してください](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan)。</span><span class="sxs-lookup"><span data-stu-id="af7f5-118">End-user alternative: For more information on joining an Azure AD domain, see [How to: Plan your Azure AD join implementation](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan).</span></span>



<span data-ttu-id="af7f5-119">Microsoft Defender セキュリティ センター、Intune ポータル、Azure セキュリティ ポータルで実行するADがあります。</span><span class="sxs-lookup"><span data-stu-id="af7f5-119">There are steps you'll need to take in Microsoft Defender Security Center, the Intune portal, and Azure AD portal.</span></span>

<span data-ttu-id="af7f5-120">これらのポータルにアクセスし、条件付きアクセスを実装するために必要な役割に注意することが重要です。</span><span class="sxs-lookup"><span data-stu-id="af7f5-120">It's important to note the required roles to access these portals and implement Conditional access:</span></span>
- <span data-ttu-id="af7f5-121">**Microsoft Defender セキュリティ センター** - 統合を有効にするには、グローバル管理者の役割を持つポータルにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="af7f5-121">**Microsoft Defender Security Center** - You'll need to sign into the portal with a global administrator role to turn on the integration.</span></span>
- <span data-ttu-id="af7f5-122">**Intune** - 管理アクセス許可を持つセキュリティ管理者権限でポータルにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="af7f5-122">**Intune** - You'll need to sign in to the portal with security administrator rights with management permissions.</span></span> 
- <span data-ttu-id="af7f5-123">**Azure ADポータル** - グローバル管理者、セキュリティ管理者、または条件付きアクセス管理者としてサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="af7f5-123">**Azure AD portal** - You'll need to sign in as a global administrator, security administrator, or Conditional Access administrator.</span></span>


> [!NOTE]
> <span data-ttu-id="af7f5-124">Microsoft Intune 環境が必要で、Intune が管理され、Azure AD Windows 10 デバイスに参加している必要があります。</span><span class="sxs-lookup"><span data-stu-id="af7f5-124">You'll need a Microsoft Intune environment, with Intune managed and Azure AD joined Windows 10 devices.</span></span>

<span data-ttu-id="af7f5-125">条件付きアクセスを有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="af7f5-125">Take the following steps to enable Conditional Access:</span></span>
- <span data-ttu-id="af7f5-126">手順 1: Microsoft Defender セキュリティ センターから Microsoft Intune 接続を有効にする</span><span class="sxs-lookup"><span data-stu-id="af7f5-126">Step 1: Turn on the Microsoft Intune connection from Microsoft Defender Security Center</span></span>
- <span data-ttu-id="af7f5-127">手順 2: Intune で Defender for Endpoint 統合を有効にする</span><span class="sxs-lookup"><span data-stu-id="af7f5-127">Step 2: Turn on the Defender for Endpoint integration in Intune</span></span>
- <span data-ttu-id="af7f5-128">手順 3: Intune でコンプライアンス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="af7f5-128">Step 3: Create the compliance policy in Intune</span></span>
- <span data-ttu-id="af7f5-129">手順 4: ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="af7f5-129">Step 4: Assign the policy</span></span> 
- <span data-ttu-id="af7f5-130">手順 5: 条件付きアクセス ポリシー AD Azure を作成する</span><span class="sxs-lookup"><span data-stu-id="af7f5-130">Step 5: Create an Azure AD Conditional Access policy</span></span>


### <a name="step-1-turn-on-the-microsoft-intune-connection"></a><span data-ttu-id="af7f5-131">手順 1: Microsoft Intune 接続を有効にする</span><span class="sxs-lookup"><span data-stu-id="af7f5-131">Step 1: Turn on the Microsoft Intune connection</span></span>
1. <span data-ttu-id="af7f5-132">ナビゲーション ウィンドウで、[設定] [**高度**  >  **な機能]**  >  **[Microsoft Intune 接続] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="af7f5-132">In the navigation pane, select **Settings** > **Advanced features** > **Microsoft Intune connection**.</span></span>
2. <span data-ttu-id="af7f5-133">Microsoft Intune の設定を [オン] に **切り替える**。</span><span class="sxs-lookup"><span data-stu-id="af7f5-133">Toggle the Microsoft Intune setting to **On**.</span></span>
3. <span data-ttu-id="af7f5-134">[設定 **の保存] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="af7f5-134">Click **Save preferences**.</span></span>


### <a name="step-2-turn-on-the-defender-for-endpoint-integration-in-intune"></a><span data-ttu-id="af7f5-135">手順 2: Intune で Defender for Endpoint 統合を有効にする</span><span class="sxs-lookup"><span data-stu-id="af7f5-135">Step 2: Turn on the Defender for Endpoint integration in Intune</span></span>
1. <span data-ttu-id="af7f5-136">[Azure portal](https://portal.azure.com) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="af7f5-136">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="af7f5-137">[デバイス **コンプライアンス**  >  **] [Microsoft Defender ATP] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="af7f5-137">Select **Device compliance** > **Microsoft Defender ATP**.</span></span>
3. <span data-ttu-id="af7f5-138">**[Windows 10.0.15063+** デバイスの接続] を [Microsoft Defender Advanced Threat Protection] に [オン] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="af7f5-138">Set **Connect Windows 10.0.15063+ devices to Microsoft Defender Advanced Threat Protection** to **On**.</span></span>
4. <span data-ttu-id="af7f5-139">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af7f5-139">Click **Save**.</span></span>


### <a name="step-3-create-the-compliance-policy-in-intune"></a><span data-ttu-id="af7f5-140">手順 3: Intune でコンプライアンス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="af7f5-140">Step 3: Create the compliance policy in Intune</span></span>
1. <span data-ttu-id="af7f5-141">Azure portal [で、[すべてのサービス](https://portal.azure.com)] を選択 **し\*\*\*\*、Intune** でフィルター処理し **、[Microsoft Intune] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="af7f5-141">In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.</span></span>
2. <span data-ttu-id="af7f5-142">[デバイス **コンプライアンス ポリシー**  >  **] [ポリシー**  >  **の作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="af7f5-142">Select **Device compliance** > **Policies** > **Create policy**.</span></span>
3. <span data-ttu-id="af7f5-143">[名前] **と [説明** ] を **入力します**。</span><span class="sxs-lookup"><span data-stu-id="af7f5-143">Enter a **Name** and **Description**.</span></span>
4. <span data-ttu-id="af7f5-144">[**プラットフォーム] で\*\*\*\*、[Windows 10 以降] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="af7f5-144">In **Platform**, select **Windows 10 and later**.</span></span>
5. <span data-ttu-id="af7f5-145">[デバイス **の正常性] 設定** で、[デバイスの脅威レベル] または [デバイスの脅威レベル] の下にあるデバイスを希望する **レベルに設定** します。</span><span class="sxs-lookup"><span data-stu-id="af7f5-145">In the **Device Health** settings, set **Require the device to be at or under the Device Threat Level** to your preferred level:</span></span>

   - <span data-ttu-id="af7f5-146">**セキュリティ** 保護 : このレベルが最も安全です。</span><span class="sxs-lookup"><span data-stu-id="af7f5-146">**Secured**: This level is the most secure.</span></span> <span data-ttu-id="af7f5-147">デバイスは、既存の脅威を持ち、会社のリソースに引き続きアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="af7f5-147">The device cannot have any existing threats and still access company resources.</span></span> <span data-ttu-id="af7f5-148">脅威が見つかった場合、デバイスは非準拠として評価されます。</span><span class="sxs-lookup"><span data-stu-id="af7f5-148">If any threats are found, the device is evaluated as noncompliant.</span></span>
   - <span data-ttu-id="af7f5-149">**低**: 低レベルの脅威だけが存在する場合、デバイスは準拠しています。</span><span class="sxs-lookup"><span data-stu-id="af7f5-149">**Low**: The device is compliant if only low-level threats exist.</span></span> <span data-ttu-id="af7f5-150">中程度または高い脅威レベルを持つデバイスは、準拠していません。</span><span class="sxs-lookup"><span data-stu-id="af7f5-150">Devices with medium or high threat levels are not compliant.</span></span>
   - <span data-ttu-id="af7f5-151">**中**: デバイスで検出された脅威が低または中程度の場合、デバイスは準拠しています。</span><span class="sxs-lookup"><span data-stu-id="af7f5-151">**Medium**: The device is compliant if the threats found on the device are low or medium.</span></span> <span data-ttu-id="af7f5-152">高レベルの脅威が検出された場合、デバイスは非準拠と判断されます。</span><span class="sxs-lookup"><span data-stu-id="af7f5-152">If high-level threats are detected, the device is determined as noncompliant.</span></span>
   - <span data-ttu-id="af7f5-153">**高**: このレベルは安全性が最も低く、すべての脅威レベルを許可します。</span><span class="sxs-lookup"><span data-stu-id="af7f5-153">**High**: This level is the least secure, and allows all threat levels.</span></span> <span data-ttu-id="af7f5-154">そのため、高、中、低の脅威レベルを持つデバイスは、準拠しているとみなされます。</span><span class="sxs-lookup"><span data-stu-id="af7f5-154">So devices that with high, medium or low threat levels are considered compliant.</span></span>

6. <span data-ttu-id="af7f5-155">**[OK]** を選択し、[**作成]** を選択して変更を保存します (ポリシーを作成します)。</span><span class="sxs-lookup"><span data-stu-id="af7f5-155">Select **OK**, and **Create** to save your changes (and create the policy).</span></span>

### <a name="step-4-assign-the-policy"></a><span data-ttu-id="af7f5-156">手順 4: ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="af7f5-156">Step 4: Assign the policy</span></span>
1. <span data-ttu-id="af7f5-157">Azure portal [で、[すべてのサービス](https://portal.azure.com)] を選択 **し\*\*\*\*、Intune** でフィルター処理し **、[Microsoft Intune] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="af7f5-157">In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.</span></span>
2. <span data-ttu-id="af7f5-158">[**デバイス コンプライアンス ポリシー**  >  **] を選択>** Microsoft Defender ATP コンプライアンス ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="af7f5-158">Select **Device compliance** > **Policies**> select your Microsoft Defender ATP compliance policy.</span></span>
3. <span data-ttu-id="af7f5-159">**[割り当て]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="af7f5-159">Select **Assignments**.</span></span>
4. <span data-ttu-id="af7f5-160">ポリシーを割り当てるには、Azure ADグループを含めるか除外します。</span><span class="sxs-lookup"><span data-stu-id="af7f5-160">Include or exclude your Azure AD groups to assign them the policy.</span></span>
5. <span data-ttu-id="af7f5-161">ポリシーをグループに展開するには、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="af7f5-161">To deploy the policy to the groups, select **Save**.</span></span> <span data-ttu-id="af7f5-162">ポリシーの対象となるユーザー デバイスは、コンプライアンスについて評価されます。</span><span class="sxs-lookup"><span data-stu-id="af7f5-162">The user devices targeted by the policy are evaluated for compliance.</span></span>

### <a name="step-5-create-an-azure-ad-conditional-access-policy"></a><span data-ttu-id="af7f5-163">手順 5: 条件付きアクセス ポリシー AD Azure を作成する</span><span class="sxs-lookup"><span data-stu-id="af7f5-163">Step 5: Create an Azure AD Conditional Access policy</span></span>
1. <span data-ttu-id="af7f5-164">Azure portal [で、Azure](https://portal.azure.com) **Active Directory 条件付きアクセス**  >  **の新しいポリシー**  >  **を開きます**。</span><span class="sxs-lookup"><span data-stu-id="af7f5-164">In the [Azure portal](https://portal.azure.com), open **Azure Active Directory** > **Conditional Access** > **New policy**.</span></span>
2. <span data-ttu-id="af7f5-165">ポリシー名を入力 **し、[** ユーザーとグループ **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="af7f5-165">Enter a policy **Name**, and select **Users and groups**.</span></span> <span data-ttu-id="af7f5-166">[含める] または [除外] オプションを使用してポリシーのグループを追加し、[完了] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="af7f5-166">Use the Include or Exclude options to add your groups for the policy, and select **Done**.</span></span>
3. <span data-ttu-id="af7f5-167">[ **クラウド アプリ] を** 選択し、保護するアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="af7f5-167">Select **Cloud apps**, and choose which apps to protect.</span></span> <span data-ttu-id="af7f5-168">たとえば、[アプリの **選択] を** 選択し **、[365 SharePoint Online] Office 365 Exchange Online** Office **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="af7f5-168">For example, choose **Select apps**, and select **Office 365 SharePoint Online** and **Office 365 Exchange Online**.</span></span> <span data-ttu-id="af7f5-169">[**完了**] を選んで変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="af7f5-169">Select **Done** to save your changes.</span></span>

4. <span data-ttu-id="af7f5-170">[**条件**  >  **クライアント アプリ] を** 選択して、アプリとブラウザーにポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="af7f5-170">Select **Conditions** > **Client apps** to apply the policy to apps and browsers.</span></span> <span data-ttu-id="af7f5-171">たとえば、[はい] **を選択** し、[ **ブラウザー** とモバイル アプリと **デスクトップ クライアント] を有効にします**。</span><span class="sxs-lookup"><span data-stu-id="af7f5-171">For example, select **Yes**, and then enable **Browser** and **Mobile apps and desktop clients**.</span></span> <span data-ttu-id="af7f5-172">[**完了**] を選んで変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="af7f5-172">Select **Done** to save your changes.</span></span>

5. <span data-ttu-id="af7f5-173">[許可 **] を** 選択して、デバイスのコンプライアンスに基づいて条件付きアクセスを適用します。</span><span class="sxs-lookup"><span data-stu-id="af7f5-173">Select **Grant** to apply Conditional Access based on device compliance.</span></span> <span data-ttu-id="af7f5-174">たとえば、[アクセスを許可 **するデバイス**  >  **に準拠としてマークする] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="af7f5-174">For example, select **Grant access** > **Require device to be marked as compliant**.</span></span> <span data-ttu-id="af7f5-175">[選択 **] を** 選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="af7f5-175">Choose **Select** to save your changes.</span></span>

6. <span data-ttu-id="af7f5-176">[ポリシー **を有効にする]** を選択し、[ **作成] を選択して** 変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="af7f5-176">Select **Enable policy**, and then **Create** to save your changes.</span></span>

<span data-ttu-id="af7f5-177">詳細については [、「Enable Microsoft Defender ATP with Conditional Access in Intune」を参照してください](https://docs.microsoft.com/intune/advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="af7f5-177">For more information, see [Enable Microsoft Defender ATP with Conditional Access in Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span></span>

><span data-ttu-id="af7f5-178">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="af7f5-178">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="af7f5-179">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="af7f5-179">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-belowfoldlink)
