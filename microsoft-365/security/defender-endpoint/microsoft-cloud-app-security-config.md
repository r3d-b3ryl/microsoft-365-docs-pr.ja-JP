---
title: Microsoft Cloud App Security の統合を構成する
ms.reviewer: ''
description: 設定を有効にして、Microsoft Defender for Endpoint と Microsoft Cloud App Security の統合を有効にする方法について説明します。
keywords: クラウド、アプリ、セキュリティ、設定、統合、検出、レポート
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
ms.openlocfilehash: ddf32b26191826ab6ecbad6b9d047ac7bbb6276a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068532"
---
# <a name="configure-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="26a49-104">Microsoft Defender for Endpoint で Microsoft Cloud App Security を構成する</span><span class="sxs-lookup"><span data-stu-id="26a49-104">Configure Microsoft Cloud App Security in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="26a49-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="26a49-105">**Applies to:**</span></span>
- [<span data-ttu-id="26a49-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="26a49-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="26a49-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="26a49-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="26a49-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="26a49-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="26a49-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="26a49-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="26a49-110">Microsoft Defender for Endpoint クラウド アプリ検出シグナルの恩恵を受けるには、Microsoft Cloud App Security 統合を有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="26a49-110">To benefit from Microsoft Defender for Endpoint cloud app discovery signals, turn on Microsoft Cloud App Security integration.</span></span>

>[!NOTE]
><span data-ttu-id="26a49-111">この機能は、Windows 10 バージョン[](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)1709 (OS ビルド 16299.1085 および[KB4493441)](https://support.microsoft.com/help/4493441)、Windows 10 を実行しているデバイスの E5 ライセンスで利用できます。 バージョン 1803 (OS ビルド 17134.704 [KB4493464)](https://support.microsoft.com/help/4493464)、Windows 10 バージョン 1809 (OS ビルド 17763.379 および[KB4489899)](https://support.microsoft.com/help/4489899)以降の Windows 10 バージョン。</span><span class="sxs-lookup"><span data-stu-id="26a49-111">This feature will be available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10, version 1709 (OS Build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, version 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, version 1809 (OS Build 17763.379 with [KB4489899](https://support.microsoft.com/help/4489899)) or later Windows 10 versions.</span></span>

> <span data-ttu-id="26a49-112">Microsoft Defender for Endpoint と Microsoft Cloud App Security の詳細な統合については、「Microsoft Defender for Endpoint integration with Microsoft Cloud App [Security」](https://docs.microsoft.com/cloud-app-security/mde-integration) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26a49-112">See [Microsoft Defender for Endpoint integration with Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/mde-integration) for detailed integration of Microsoft Defender for Endpoint with Microsoft Cloud App Security.</span></span> 

## <a name="enable-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="26a49-113">エンドポイント向け Microsoft Defender で Microsoft Cloud App Security を有効にする</span><span class="sxs-lookup"><span data-stu-id="26a49-113">Enable Microsoft Cloud App Security in Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="26a49-114">ナビゲーション ウィンドウで、[基本設定]**セットアップの [高度な**  >  **機能] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="26a49-114">In the navigation pane, select **Preferences setup** > **Advanced features**.</span></span>
2. <span data-ttu-id="26a49-115">[Microsoft **Cloud App Security] を選択** し、トグルを [オン] に **切り替えます**。</span><span class="sxs-lookup"><span data-stu-id="26a49-115">Select **Microsoft Cloud App Security** and switch the toggle to **On**.</span></span>
3. <span data-ttu-id="26a49-116">[設定 **の保存] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="26a49-116">Click **Save preferences**.</span></span>

<span data-ttu-id="26a49-117">アクティブ化されると、Microsoft Defender for Endpoint は検出信号のクラウド アプリ セキュリティへの転送を直ちに開始します。</span><span class="sxs-lookup"><span data-stu-id="26a49-117">Once activated, Microsoft Defender for Endpoint will immediately start forwarding discovery signals to Cloud App Security.</span></span>

## <a name="view-the-data-collected"></a><span data-ttu-id="26a49-118">収集されたデータを表示する</span><span class="sxs-lookup"><span data-stu-id="26a49-118">View the data collected</span></span>

<span data-ttu-id="26a49-119">Microsoft Cloud Apps Security で Microsoft Defender for Endpoint データを表示およびアクセスするには、「Cloud App Security でデバイスを調査する [」を参照してください](https://docs.microsoft.com/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security)。</span><span class="sxs-lookup"><span data-stu-id="26a49-119">To view and access Microsoft Defender for Endpoint data in Microsoft Cloud Apps Security, see [Investigate devices in Cloud App Security](https://docs.microsoft.com/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security).</span></span>


<span data-ttu-id="26a49-120">クラウド検出の詳細については、「検出されたアプリを操作 [する」を参照してください](https://docs.microsoft.com/cloud-app-security/discovered-apps)。</span><span class="sxs-lookup"><span data-stu-id="26a49-120">For more information about cloud discovery, see [Working with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>

<span data-ttu-id="26a49-121">Microsoft Cloud App Security の試用に興味がある場合は [、「Microsoft Cloud App Security Trial」を参照してください](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1)。</span><span class="sxs-lookup"><span data-stu-id="26a49-121">If you're interested in trying Microsoft Cloud App Security, see [Microsoft Cloud App Security Trial](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1).</span></span>

## <a name="related-topic"></a><span data-ttu-id="26a49-122">関連トピック</span><span class="sxs-lookup"><span data-stu-id="26a49-122">Related topic</span></span>
- [<span data-ttu-id="26a49-123">Microsoft Cloud App Security の統合</span><span class="sxs-lookup"><span data-stu-id="26a49-123">Microsoft Cloud App Security integration</span></span>](microsoft-cloud-app-security-integration.md)
