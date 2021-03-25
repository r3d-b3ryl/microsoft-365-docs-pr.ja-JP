---
title: Windows 以外のデバイスを Microsoft Defender for Endpoint サービスにオンボードする
description: センサー データを Microsoft Defender ATP サービスに送信できるよう、Windows 以外のデバイスを構成します。
keywords: Windows 以外のデバイスのオンボード、macos、Linux、デバイス管理、Windows ATP デバイスの構成、Microsoft Defender for Endpoint デバイスの構成
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
ms.openlocfilehash: c292c57c179a832728b03a7fc94fb7085d3ea0ec
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166079"
---
# <a name="onboard-non-windows-devices"></a><span data-ttu-id="fcd44-104">Windows 以外のデバイスをオンボードする</span><span class="sxs-lookup"><span data-stu-id="fcd44-104">Onboard non-Windows devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="fcd44-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="fcd44-105">**Applies to:**</span></span>
- [<span data-ttu-id="fcd44-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fcd44-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fcd44-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fcd44-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="fcd44-108">**プラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="fcd44-108">**Platforms**</span></span>
- <span data-ttu-id="fcd44-109">macOS</span><span class="sxs-lookup"><span data-stu-id="fcd44-109">macOS</span></span>
- <span data-ttu-id="fcd44-110">Linux</span><span class="sxs-lookup"><span data-stu-id="fcd44-110">Linux</span></span>

><span data-ttu-id="fcd44-111">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="fcd44-111">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fcd44-112">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="fcd44-112">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-nonwindows-abovefoldlink) 

<span data-ttu-id="fcd44-113">Defender for Endpoint は、Windows および Windows 以外のプラットフォームに対して一元的なセキュリティ操作エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="fcd44-113">Defender for Endpoint provides a centralized security operations experience for Windows as well as non-Windows platforms.</span></span> <span data-ttu-id="fcd44-114">Microsoft Defender Security Center でサポートされているさまざまなオペレーティング システム (OS) からのアラートを確認し、組織のネットワークをより保護することができます。</span><span class="sxs-lookup"><span data-stu-id="fcd44-114">You'll be able to see alerts from various supported operating systems (OS) in Microsoft Defender Security Center and better protect your organization's network.</span></span> 

<span data-ttu-id="fcd44-115">統合を機能するには、Defender for Endpoint と互換性のある Linux ディストリビューションと macOS の正確なバージョンを知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcd44-115">You'll need to know the exact Linux distros and macOS versions that are compatible with Defender for Endpoint for the integration to work.</span></span> <span data-ttu-id="fcd44-116">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcd44-116">For more information, see:</span></span>
- [<span data-ttu-id="fcd44-117">Microsoft Defender for Endpoint for Linux システム要件</span><span class="sxs-lookup"><span data-stu-id="fcd44-117">Microsoft Defender for Endpoint for Linux system requirements</span></span>](microsoft-defender-endpoint-linux.md#system-requirements)  
- <span data-ttu-id="fcd44-118">[Microsoft Defender for Endpoint for Mac システム要件](microsoft-defender-endpoint-mac.md#system-requirements).</span><span class="sxs-lookup"><span data-stu-id="fcd44-118">[Microsoft Defender for Endpoint for Mac system requirements](microsoft-defender-endpoint-mac.md#system-requirements).</span></span>

## <a name="onboarding-non-windows-devices"></a><span data-ttu-id="fcd44-119">Windows 以外のデバイスのオンボーディング</span><span class="sxs-lookup"><span data-stu-id="fcd44-119">Onboarding non-Windows devices</span></span>
<span data-ttu-id="fcd44-120">Windows 以外のデバイスをオンボードするには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcd44-120">You'll need to take the following steps to onboard non-Windows devices:</span></span>
1. <span data-ttu-id="fcd44-121">オンボーディングの好みの方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="fcd44-121">Select your preferred method of onboarding:</span></span>

   - <span data-ttu-id="fcd44-122">macOS デバイスの場合は、Microsoft Defender ATP またはサード パーティ製ソリューションを使用してオンボードを選択できます。</span><span class="sxs-lookup"><span data-stu-id="fcd44-122">For macOS devices, you can choose to onboard through Microsoft Defender ATP or through a third-party solution.</span></span> <span data-ttu-id="fcd44-123">詳細については [、「Microsoft Defender for Endpoint for Mac」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac)。</span><span class="sxs-lookup"><span data-stu-id="fcd44-123">For more information, see [Microsoft Defender for Endpoint for Mac](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac).</span></span>
   - <span data-ttu-id="fcd44-124">その他の Windows 以外のデバイスの場合は、[サードパーティとの統合による Windows 以外のデバイスのオンボード **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fcd44-124">For other non-Windows devices choose **Onboard non-Windows devices through third-party integration**.</span></span>   
       
     1. <span data-ttu-id="fcd44-125">ナビゲーション ウィンドウで、[相互運用性パートナー]**を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="fcd44-125">In the navigation pane, select **Interoperability** > **Partners**.</span></span> <span data-ttu-id="fcd44-126">サード パーティ製のソリューションが一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="fcd44-126">Make sure the third-party solution is listed.</span></span>

        2. <span data-ttu-id="fcd44-127">[パートナー **アプリケーション] タブで** 、Windows 以外のデバイスをサポートするパートナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="fcd44-127">In the **Partner Applications** tab, select the partner that supports your non-Windows devices.</span></span>

        3. <span data-ttu-id="fcd44-128">[ **パートナー ページを開く]** を選択して、パートナーのページを開きます。</span><span class="sxs-lookup"><span data-stu-id="fcd44-128">Select **Open partner page** to open the partner's page.</span></span> <span data-ttu-id="fcd44-129">ページに記載されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="fcd44-129">Follow the instructions provided on the page.</span></span>

        4. <span data-ttu-id="fcd44-130">アカウントを作成するか、パートナー ソリューションをサブスクライブした後、組織のテナントのグローバル管理者がパートナー アプリケーションからのアクセス許可要求を受け入れるという要求を受け入れるステージに進む必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcd44-130">After creating an account or subscribing to the partner solution, you should get to a stage where a tenant Global Admin in your organization is asked to accept a permission request from the partner application.</span></span> <span data-ttu-id="fcd44-131">アクセス許可要求を注意深く読み、必要なサービスと一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcd44-131">Read the permission request carefully to make sure that it is aligned with the service that you require.</span></span> 

        
2. <span data-ttu-id="fcd44-132">サード パーティソリューションの指示に従って検出テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="fcd44-132">Run a detection test by following the instructions of the third-party solution.</span></span>

## <a name="offboard-non-windows-devices"></a><span data-ttu-id="fcd44-133">Windows 以外のオフボード デバイス</span><span class="sxs-lookup"><span data-stu-id="fcd44-133">Offboard non-Windows devices</span></span>

1. <span data-ttu-id="fcd44-134">サード パーティのドキュメントに従って、Microsoft Defender for Endpoint からサード パーティ製ソリューションを切断します。</span><span class="sxs-lookup"><span data-stu-id="fcd44-134">Follow the third-party's documentation to disconnect the third-party solution from Microsoft Defender for Endpoint.</span></span>

2. <span data-ttu-id="fcd44-135">Azure のサードパーティ ソリューションのアクセス許可を削除し、ADします。</span><span class="sxs-lookup"><span data-stu-id="fcd44-135">Remove permissions for the third-party solution in your Azure AD tenant.</span></span>
   1. <span data-ttu-id="fcd44-136">[Azure portal](https://portal.azure.com) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="fcd44-136">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
   2. <span data-ttu-id="fcd44-137">[Azure **Active Directory >エンタープライズ アプリケーション] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fcd44-137">Select **Azure Active Directory > Enterprise Applications**.</span></span>
   3. <span data-ttu-id="fcd44-138">オフボードするアプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="fcd44-138">Select the application you'd like to offboard.</span></span>
   4. <span data-ttu-id="fcd44-139">[削除] **ボタンを** 選択します。</span><span class="sxs-lookup"><span data-stu-id="fcd44-139">Select the **Delete** button.</span></span>


## <a name="related-topics"></a><span data-ttu-id="fcd44-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="fcd44-140">Related topics</span></span>
- [<span data-ttu-id="fcd44-141">オンボード Windows 10 デバイス</span><span class="sxs-lookup"><span data-stu-id="fcd44-141">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="fcd44-142">オンボード サーバー</span><span class="sxs-lookup"><span data-stu-id="fcd44-142">Onboard servers</span></span>](configure-server-endpoints.md)
- [<span data-ttu-id="fcd44-143">プロキシとインターネット接続の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="fcd44-143">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="fcd44-144">Microsoft Defender for Endpoint オンボーディングの問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="fcd44-144">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
