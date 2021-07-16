---
title: Microsoft Defender for Endpoint サービスWindowsデバイス以外のデバイスをオンボードする
description: Microsoft Defender for Endpoint サービスWindowsセンサー データを送信できるよう、デバイス以外のデバイスを構成します。
keywords: オンボードの非Windowsデバイス、macos、Linux、デバイス管理、エンドポイント デバイス用 Microsoft Defender の構成
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
ms.openlocfilehash: 4aff505f9f35b6144360eed5992ac36cf0847617
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454711"
---
# <a name="onboard-non-windows-devices"></a><span data-ttu-id="d288f-104">Windows 以外のデバイスをオンボードする</span><span class="sxs-lookup"><span data-stu-id="d288f-104">Onboard non-Windows devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d288f-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d288f-105">**Applies to:**</span></span>
- [<span data-ttu-id="d288f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d288f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d288f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d288f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="d288f-108">**プラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="d288f-108">**Platforms**</span></span>
- <span data-ttu-id="d288f-109">macOS</span><span class="sxs-lookup"><span data-stu-id="d288f-109">macOS</span></span>
- <span data-ttu-id="d288f-110">Linux</span><span class="sxs-lookup"><span data-stu-id="d288f-110">Linux</span></span>

><span data-ttu-id="d288f-111">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="d288f-111">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d288f-112">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="d288f-112">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-nonwindows-abovefoldlink) 

<span data-ttu-id="d288f-113">Defender for Endpoint は、セキュリティ プラットフォームだけでなく、Windowsプラットフォームにも一元的なセキュリティWindows提供します。</span><span class="sxs-lookup"><span data-stu-id="d288f-113">Defender for Endpoint provides a centralized security operations experience for Windows as well as non-Windows platforms.</span></span> <span data-ttu-id="d288f-114">サポートされているさまざまなオペレーティング システム (OS) からのアラートを、組織のネットワークMicrosoft 365 Defender保護するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d288f-114">You'll be able to see alerts from various supported operating systems (OS) in Microsoft 365 Defender and better protect your organization's network.</span></span> 

<span data-ttu-id="d288f-115">統合を機能するには、Defender for Endpoint と互換性のある Linux ディストリビューションと macOS の正確なバージョンを知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="d288f-115">You'll need to know the exact Linux distros and macOS versions that are compatible with Defender for Endpoint for the integration to work.</span></span> <span data-ttu-id="d288f-116">詳しくは、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d288f-116">For more information, see:</span></span>
- [<span data-ttu-id="d288f-117">Microsoft Defender for Endpoint on Linux システム要件</span><span class="sxs-lookup"><span data-stu-id="d288f-117">Microsoft Defender for Endpoint on Linux system requirements</span></span>](microsoft-defender-endpoint-linux.md#system-requirements)  
- <span data-ttu-id="d288f-118">[Microsoft Defender for Endpoint on macOS system requirements](microsoft-defender-endpoint-mac.md#system-requirements).</span><span class="sxs-lookup"><span data-stu-id="d288f-118">[Microsoft Defender for Endpoint on macOS system requirements](microsoft-defender-endpoint-mac.md#system-requirements).</span></span>

## <a name="onboarding-non-windows-devices"></a><span data-ttu-id="d288f-119">非デバイスのオンボードWindowsする</span><span class="sxs-lookup"><span data-stu-id="d288f-119">Onboarding non-Windows devices</span></span>
<span data-ttu-id="d288f-120">非デバイスをオンボードするには、次の手順を実行Windows必要があります。</span><span class="sxs-lookup"><span data-stu-id="d288f-120">You'll need to take the following steps to onboard non-Windows devices:</span></span>
1. <span data-ttu-id="d288f-121">オンボーディングの好みの方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="d288f-121">Select your preferred method of onboarding:</span></span>

   - <span data-ttu-id="d288f-122">macOS デバイスの場合は、Microsoft Defender for Endpoint またはサード パーティ製ソリューションを使用してオンボードを選択できます。</span><span class="sxs-lookup"><span data-stu-id="d288f-122">For macOS devices, you can choose to onboard through Microsoft Defender for Endpoint or through a third-party solution.</span></span> <span data-ttu-id="d288f-123">詳細については [、「Microsoft Defender for Endpoint on Mac」を参照してください](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac)。</span><span class="sxs-lookup"><span data-stu-id="d288f-123">For more information, see [Microsoft Defender for Endpoint on Mac](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac).</span></span>

   - <span data-ttu-id="d288f-124">その他の非デバイスWindows、サードパーティとの統合を通じてWindowsデバイスのオンボード **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d288f-124">For other non-Windows devices, choose **Onboard non-Windows devices through third-party integration**.</span></span>   
    1. <span data-ttu-id="d288f-125">ナビゲーション ウィンドウで、[相互運用性パートナー]**を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d288f-125">In the navigation pane, select **Interoperability** > **Partners**.</span></span> <span data-ttu-id="d288f-126">サード パーティ製のソリューションが一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="d288f-126">Make sure the third-party solution is listed.</span></span>
    2. <span data-ttu-id="d288f-127">[パートナー **アプリケーション] タブ** で、ユーザー以外のデバイスをサポートするパートナー Windowsします。</span><span class="sxs-lookup"><span data-stu-id="d288f-127">In the **Partner Applications** tab, select the partner that supports your non-Windows devices.</span></span>
    3. <span data-ttu-id="d288f-128">[ **パートナー ページを開く]** を選択して、パートナーのページを開きます。</span><span class="sxs-lookup"><span data-stu-id="d288f-128">Select **Open partner page** to open the partner's page.</span></span> <span data-ttu-id="d288f-129">ページに記載されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d288f-129">Follow the instructions provided on the page.</span></span>
    4. <span data-ttu-id="d288f-130">アカウントを作成するか、パートナー ソリューションをサブスクライブした後、組織のテナントのグローバル管理者がパートナー アプリケーションからのアクセス許可要求を受け入れるという要求を受け入れるステージに進む必要があります。</span><span class="sxs-lookup"><span data-stu-id="d288f-130">After creating an account or subscribing to the partner solution, you should get to a stage where a tenant Global Admin in your organization is asked to accept a permission request from the partner application.</span></span> <span data-ttu-id="d288f-131">アクセス許可要求を注意深く読み、必要なサービスと一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="d288f-131">Read the permission request carefully to make sure that it is aligned with the service that you require.</span></span> 

        
2. <span data-ttu-id="d288f-132">サード パーティソリューションの指示に従って検出テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="d288f-132">Run a detection test by following the instructions of the third-party solution.</span></span>

## <a name="offboard-non-windows-devices"></a><span data-ttu-id="d288f-133">オフボードの非Windowsデバイス</span><span class="sxs-lookup"><span data-stu-id="d288f-133">Offboard non-Windows devices</span></span>

1. <span data-ttu-id="d288f-134">サード パーティのドキュメントに従って、Microsoft Defender for Endpoint からサード パーティ製ソリューションを切断します。</span><span class="sxs-lookup"><span data-stu-id="d288f-134">Follow the third-party's documentation to disconnect the third-party solution from Microsoft Defender for Endpoint.</span></span>

2. <span data-ttu-id="d288f-135">Azure のサードパーティ ソリューションのアクセス許可を削除し、ADします。</span><span class="sxs-lookup"><span data-stu-id="d288f-135">Remove permissions for the third-party solution in your Azure AD tenant.</span></span>
   1. <span data-ttu-id="d288f-136">[Azure portal](https://portal.azure.com) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="d288f-136">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
   2. <span data-ttu-id="d288f-137">[アプリケーション **Azure Active Directory > Enterprise] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d288f-137">Select **Azure Active Directory > Enterprise Applications**.</span></span>
   3. <span data-ttu-id="d288f-138">オフボードするアプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="d288f-138">Select the application you'd like to offboard.</span></span>
   4. <span data-ttu-id="d288f-139">[削除] **ボタンを** 選択します。</span><span class="sxs-lookup"><span data-stu-id="d288f-139">Select the **Delete** button.</span></span>


## <a name="related-topics"></a><span data-ttu-id="d288f-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="d288f-140">Related topics</span></span>
- [<span data-ttu-id="d288f-141">Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="d288f-141">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="d288f-142">オンボード サーバー</span><span class="sxs-lookup"><span data-stu-id="d288f-142">Onboard servers</span></span>](configure-server-endpoints.md)
- [<span data-ttu-id="d288f-143">プロキシとインターネット接続の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="d288f-143">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="d288f-144">Microsoft Defender for Endpoint オンボーディングの問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d288f-144">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
