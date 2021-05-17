---
title: Android 用 Microsoft Defender for Endpoint
ms.reviewer: ''
description: Android に Microsoft Defender for Endpoint をインストールして使用する方法について説明します。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, android, installation, deploy, uninstallation, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3f8a8c04f608096e5c226d6899fbbd983bd8d8c1
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246430"
---
# <a name="microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="3212f-104">Android 用 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3212f-104">Microsoft Defender for Endpoint on Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3212f-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3212f-105">**Applies to:**</span></span>
- [<span data-ttu-id="3212f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3212f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3212f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3212f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3212f-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="3212f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3212f-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="3212f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="3212f-110">このトピックでは、Android 上で Defender for Endpoint をインストール、構成、更新、および使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3212f-110">This topic describes how to install, configure, update, and use Defender for Endpoint on Android.</span></span>

> [!CAUTION]
> <span data-ttu-id="3212f-111">Android で Defender for Endpoint と共に他のサード パーティ製のエンドポイント保護製品を実行すると、パフォーマンスの問題や予期しないシステム エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3212f-111">Running other third-party endpoint protection products alongside Defender for Endpoint on Android is likely to cause performance problems and unpredictable system errors.</span></span>


## <a name="how-to-install-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="3212f-112">Android に Microsoft Defender for Endpoint をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="3212f-112">How to install Microsoft Defender for Endpoint on Android</span></span>

### <a name="prerequisites"></a><span data-ttu-id="3212f-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="3212f-113">Prerequisites</span></span>

-   <span data-ttu-id="3212f-114">**エンド ユーザー向け**</span><span class="sxs-lookup"><span data-stu-id="3212f-114">**For end users**</span></span>

    -   <span data-ttu-id="3212f-115">アプリのエンド ユーザーに割り当てられた Microsoft Defender for Endpoint ライセンス。</span><span class="sxs-lookup"><span data-stu-id="3212f-115">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="3212f-116">[「Microsoft Defender for Endpoint ライセンス要件」を参照してください。](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="3212f-116">See [Microsoft Defender for Endpoint licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span></span>

    -   <span data-ttu-id="3212f-117">Intune ポータル サイトは Google Play からダウンロード[可能](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)で、Android デバイスで利用できます。</span><span class="sxs-lookup"><span data-stu-id="3212f-117">Intune Company Portal app can be downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and is available on the Android device.</span></span>

        -   <span data-ttu-id="3212f-118">さらに、Intune デバイスコンプライアンス ポリシーを[](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal)適用するために、Intune ポータル サイトアプリを介してデバイスを登録できます。</span><span class="sxs-lookup"><span data-stu-id="3212f-118">Additionally, device(s) can be [enrolled](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="3212f-119">これには、エンド ユーザーにライセンスを割り当てるMicrosoft Intune必要があります。</span><span class="sxs-lookup"><span data-stu-id="3212f-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>

    -   <span data-ttu-id="3212f-120">ライセンスを割り当てる方法の詳細については、「ユーザーにライセンスを割り当 [てる」を参照してください](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)。</span><span class="sxs-lookup"><span data-stu-id="3212f-120">For more information on how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>
        

-   <span data-ttu-id="3212f-121">**管理者向け**</span><span class="sxs-lookup"><span data-stu-id="3212f-121">**For Administrators**</span></span>

    -   <span data-ttu-id="3212f-122">ポータルへのアクセスMicrosoft Defender セキュリティ センターします。</span><span class="sxs-lookup"><span data-stu-id="3212f-122">Access to the Microsoft Defender Security Center portal.</span></span>

        > [!NOTE]
        > <span data-ttu-id="3212f-123">Microsoft Intuneは、Android に Microsoft Defender for Endpoint を展開する場合にサポートされている唯一のモバイル デバイス管理 (MDM) ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="3212f-123">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint on Android.</span></span> <span data-ttu-id="3212f-124">現在、Intune で Android 関連のデバイス コンプライアンス ポリシーで Defender for Endpoint を適用する場合は、現在登録されているデバイスだけがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3212f-124">Currently only enrolled devices are supported for enforcing Defender for Endpoint on Android related device compliance policies in Intune.</span></span> 

    -   <span data-ttu-id="3212f-125">管理[Microsoft エンドポイント マネージャーアクセスして](https://go.microsoft.com/fwlink/?linkid=2109431)、組織の登録済みユーザー グループにアプリを展開します。</span><span class="sxs-lookup"><span data-stu-id="3212f-125">Access [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>
        
### <a name="network-requirements"></a><span data-ttu-id="3212f-126">ネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="3212f-126">Network Requirements</span></span>

- <span data-ttu-id="3212f-127">Microsoft Defender for Endpoint on Android がネットワークに接続されている場合に機能するには [、Microsoft Defender for Endpoint](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)サービス URL へのアクセスを有効にするようにファイアウォール/プロキシを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3212f-127">For Microsoft Defender for Endpoint on Android to function when connected to a network the firewall/proxy will need to be configured to [enable access to Microsoft Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

### <a name="system-requirements"></a><span data-ttu-id="3212f-128">システム要件</span><span class="sxs-lookup"><span data-stu-id="3212f-128">System Requirements</span></span>

-   <span data-ttu-id="3212f-129">Android 6.0 以上を実行している Android デバイス。</span><span class="sxs-lookup"><span data-stu-id="3212f-129">Android devices running Android 6.0 and above.</span></span>
-   <span data-ttu-id="3212f-130">Intune ポータル サイトは Google Play から[ダウンロードされ、](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)インストールされます。</span><span class="sxs-lookup"><span data-stu-id="3212f-130">Intune Company Portal app is downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and installed.</span></span> <span data-ttu-id="3212f-131">Intune デバイス コンプライアンス ポリシーを適用するには、デバイスの登録が必要です。</span><span class="sxs-lookup"><span data-stu-id="3212f-131">Device enrollment is required for Intune device compliance policies to be enforced.</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="3212f-132">インストール手順</span><span class="sxs-lookup"><span data-stu-id="3212f-132">Installation instructions</span></span>

<span data-ttu-id="3212f-133">Android 上の Microsoft Defender for Endpoint は、登録されているデバイスの両方のモード (従来のデバイス管理者モードと Android デバイス モード) へのインストールEnterpriseサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3212f-133">Microsoft Defender for Endpoint on Android supports installation on both modes of enrolled devices - the legacy Device Administrator and Android Enterprise modes.</span></span>
<span data-ttu-id="3212f-134">**現在、仕事用プロファイルと企業所有の完全に管理されたユーザー デバイス登録を持つ個人所有のデバイスは、Android Enterprise でサポートされています。他の Android Enterpriseのサポートは、準備ができたら発表されます。**</span><span class="sxs-lookup"><span data-stu-id="3212f-134">**Currently, Personally-owned devices with work profile and Corporate-owned fully managed user device enrollments are supported in Android Enterprise. Support for other Android Enterprise modes will be announced when ready.**</span></span>

<span data-ttu-id="3212f-135">Android での Microsoft Defender for Endpoint の展開は、Microsoft Intune (MDM) 経由です。</span><span class="sxs-lookup"><span data-stu-id="3212f-135">Deployment of Microsoft Defender for Endpoint on Android is via Microsoft Intune (MDM).</span></span>
<span data-ttu-id="3212f-136">詳細については、「Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune」[を参照してください](android-intune.md)。</span><span class="sxs-lookup"><span data-stu-id="3212f-136">For more information, see [Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune](android-intune.md).</span></span>


> [!NOTE]
> <span data-ttu-id="3212f-137">**Android 上のエンドポイント用 Microsoft Defender は [、Google Play で利用](https://play.google.com/store/apps/details?id=com.microsoft.scmx) できます。**</span><span class="sxs-lookup"><span data-stu-id="3212f-137">**Microsoft Defender for Endpoint on Android is available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) now.**</span></span> <br> <span data-ttu-id="3212f-138">Intune から Google Play に接続して、Microsoft Defender for Endpoint アプリを展開し、デバイス管理者モードと Android デバイス Enterprise展開できます。</span><span class="sxs-lookup"><span data-stu-id="3212f-138">You can connect to Google Play from Intune to deploy Microsoft Defender for Endpoint app, across Device Administrator and Android Enterprise entrollment modes.</span></span> 

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="3212f-139">Android 上のエンドポイント用 Microsoft Defender を構成する方法</span><span class="sxs-lookup"><span data-stu-id="3212f-139">How to Configure Microsoft Defender for Endpoint on Android</span></span>

<span data-ttu-id="3212f-140">Android の機能で Microsoft Defender for Endpoint を構成する方法については、「Configure Microsoft Defender for Endpoint on Android フィーチャー [」を参照してください](android-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="3212f-140">Guidance on how to configure Microsoft Defender for Endpoint on Android features is available in [Configure Microsoft Defender for Endpoint on Android features](android-configure.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="3212f-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="3212f-141">Related topics</span></span>
- [<span data-ttu-id="3212f-142">Microsoft Intune を使用した Android 用 Microsoft Defender for Endpoint の展開</span><span class="sxs-lookup"><span data-stu-id="3212f-142">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span>](android-intune.md)
- [<span data-ttu-id="3212f-143">Android 機能用に Microsoft Defender for Endpoint を構成する</span><span class="sxs-lookup"><span data-stu-id="3212f-143">Configure Microsoft Defender for Endpoint on Android features</span></span>](android-configure.md)

