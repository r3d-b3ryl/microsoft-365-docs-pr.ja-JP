---
title: Android の Microsoft Defender ATP
ms.reviewer: ''
description: Android 用 Microsoft Defender ATP をインストールして使用する方法について説明します。
keywords: microsoft、Defender、atp、android、インストール、展開、アンインストール、intune
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
ms.openlocfilehash: 8311cb703bc5232e1421d19892fec9cdbc94b052
ms.sourcegitcommit: 72ae1b49e7a3d3199272fcb4c39f5daec0d66f1a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51698196"
---
# <a name="microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="f30f9-104">Android 上のエンドポイント用 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f30f9-104">Microsoft Defender for Endpoint on Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f30f9-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f30f9-105">**Applies to:**</span></span>
- [<span data-ttu-id="f30f9-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f30f9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f30f9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f30f9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f30f9-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="f30f9-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f30f9-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="f30f9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="f30f9-110">このトピックでは、Android 上で Defender for Endpoint をインストール、構成、更新、および使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f30f9-110">This topic describes how to install, configure, update, and use Defender for Endpoint on Android.</span></span>

> [!CAUTION]
> <span data-ttu-id="f30f9-111">Android で Defender for Endpoint と共に他のサード パーティ製のエンドポイント保護製品を実行すると、パフォーマンスの問題や予期しないシステム エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f30f9-111">Running other third-party endpoint protection products alongside Defender for Endpoint on Android is likely to cause performance problems and unpredictable system errors.</span></span>


## <a name="how-to-install-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="f30f9-112">Android に Microsoft Defender for Endpoint をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="f30f9-112">How to install Microsoft Defender for Endpoint on Android</span></span>

### <a name="prerequisites"></a><span data-ttu-id="f30f9-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="f30f9-113">Prerequisites</span></span>

-   <span data-ttu-id="f30f9-114">**エンド ユーザー向け**</span><span class="sxs-lookup"><span data-stu-id="f30f9-114">**For end users**</span></span>

    -   <span data-ttu-id="f30f9-115">アプリのエンド ユーザーに割り当てられた Microsoft Defender for Endpoint ライセンス。</span><span class="sxs-lookup"><span data-stu-id="f30f9-115">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="f30f9-116">[「Microsoft Defender for Endpoint ライセンス要件」を参照してください。](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="f30f9-116">See [Microsoft Defender for Endpoint licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span></span>

    -   <span data-ttu-id="f30f9-117">Intune ポータル サイト アプリは Google Play から [ダウンロードできます。Android](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) デバイスで利用できます。</span><span class="sxs-lookup"><span data-stu-id="f30f9-117">Intune Company Portal app can be downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and is available on the Android device.</span></span>

        -   <span data-ttu-id="f30f9-118">さらに、Intune ポータル サイト アプリ[](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal)を介してデバイスを登録して、Intune デバイスコンプライアンス ポリシーを適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="f30f9-118">Additionally, device(s) can be [enrolled](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="f30f9-119">これには、エンド ユーザーに Microsoft Intune ライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f30f9-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>

    -   <span data-ttu-id="f30f9-120">ライセンスを割り当てる方法の詳細については、「ユーザーにライセンスを割り当 [てる」を参照してください](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)。</span><span class="sxs-lookup"><span data-stu-id="f30f9-120">For more information on how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>
        

-   <span data-ttu-id="f30f9-121">**管理者向け**</span><span class="sxs-lookup"><span data-stu-id="f30f9-121">**For Administrators**</span></span>

    -   <span data-ttu-id="f30f9-122">Microsoft Defender セキュリティ センター ポータルへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="f30f9-122">Access to the Microsoft Defender Security Center portal.</span></span>

        > [!NOTE]
        > <span data-ttu-id="f30f9-123">Microsoft Intune は、Android に Microsoft Defender for Endpoint を展開する唯一のサポートされるモバイル デバイス管理 (MDM) ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="f30f9-123">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint on Android.</span></span> <span data-ttu-id="f30f9-124">現在、Intune で Defender for Endpoint for Android 関連のデバイス コンプライアンス ポリシーを適用するには、現在登録されているデバイスだけがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f30f9-124">Currently only enrolled devices are supported for enforcing Defender for Endpoint for Android related device compliance policies in Intune.</span></span> 

    -   <span data-ttu-id="f30f9-125">Microsoft [Endpoint Manager 管理センターにアクセスして](https://go.microsoft.com/fwlink/?linkid=2109431)、組織内の登録済みユーザー グループにアプリを展開します。</span><span class="sxs-lookup"><span data-stu-id="f30f9-125">Access [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

### <a name="system-requirements"></a><span data-ttu-id="f30f9-126">システム要件</span><span class="sxs-lookup"><span data-stu-id="f30f9-126">System Requirements</span></span>

-   <span data-ttu-id="f30f9-127">Android 6.0 以上を実行している Android デバイス。</span><span class="sxs-lookup"><span data-stu-id="f30f9-127">Android devices running Android 6.0 and above.</span></span>
-   <span data-ttu-id="f30f9-128">Intune ポータル サイト アプリは [、Google Play からダウンロードして](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) インストールされます。</span><span class="sxs-lookup"><span data-stu-id="f30f9-128">Intune Company Portal app is downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and installed.</span></span> <span data-ttu-id="f30f9-129">Intune デバイス コンプライアンス ポリシーを適用するには、デバイスの登録が必要です。</span><span class="sxs-lookup"><span data-stu-id="f30f9-129">Device enrollment is required for Intune device compliance policies to be enforced.</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="f30f9-130">インストール手順</span><span class="sxs-lookup"><span data-stu-id="f30f9-130">Installation instructions</span></span>

<span data-ttu-id="f30f9-131">Microsoft Defender for Endpoint on Android では、登録されているデバイスの両方のモード (従来のデバイス管理者モードと Android Enterprise モード) へのインストールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f30f9-131">Microsoft Defender for Endpoint on Android supports installation on both modes of enrolled devices - the legacy Device Administrator and Android Enterprise modes.</span></span>
<span data-ttu-id="f30f9-132">**現在、Android Enterprise では、仕事用プロファイルと企業所有の完全管理ユーザー デバイス登録を持つ個人所有のデバイスがサポートされています。準備ができたら、他の Android Enterprise モードのサポートが発表されます。**</span><span class="sxs-lookup"><span data-stu-id="f30f9-132">**Currently, Personally-owned devices with work profile and Corporate-owned fully managed user device enrollments are supported in Android Enterprise. Support for other Android Enterprise modes will be announced when ready.**</span></span>

<span data-ttu-id="f30f9-133">Android での Microsoft Defender for Endpoint の展開は、Microsoft Intune (MDM) 経由です。</span><span class="sxs-lookup"><span data-stu-id="f30f9-133">Deployment of Microsoft Defender for Endpoint on Android is via Microsoft Intune (MDM).</span></span>
<span data-ttu-id="f30f9-134">詳細については [、「Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune」を参照してください](android-intune.md)。</span><span class="sxs-lookup"><span data-stu-id="f30f9-134">For more information, see [Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune](android-intune.md).</span></span>


> [!NOTE]
> <span data-ttu-id="f30f9-135">**Android 上のエンドポイント用 Microsoft Defender は [、Google Play で利用](https://play.google.com/store/apps/details?id=com.microsoft.scmx) できます。**</span><span class="sxs-lookup"><span data-stu-id="f30f9-135">**Microsoft Defender for Endpoint on Android is available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) now.**</span></span> <br> <span data-ttu-id="f30f9-136">Intune から Google Play に接続して、デバイス管理者モードと Android Enterprise entrollment モード全体で Microsoft Defender for Endpoint アプリを展開できます。</span><span class="sxs-lookup"><span data-stu-id="f30f9-136">You can connect to Google Play from Intune to deploy Microsoft Defender for Endpoint app, across Device Administrator and Android Enterprise entrollment modes.</span></span> 

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="f30f9-137">Android 上のエンドポイント用 Microsoft Defender を構成する方法</span><span class="sxs-lookup"><span data-stu-id="f30f9-137">How to Configure Microsoft Defender for Endpoint on Android</span></span>

<span data-ttu-id="f30f9-138">Android の機能で Microsoft Defender for Endpoint を構成する方法については、「Configure Microsoft Defender for Endpoint on Android フィーチャー [」を参照してください](android-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="f30f9-138">Guidance on how to configure Microsoft Defender for Endpoint on Android features is available in [Configure Microsoft Defender for Endpoint on Android features](android-configure.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="f30f9-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="f30f9-139">Related topics</span></span>
- [<span data-ttu-id="f30f9-140">Microsoft Intune を使用して Android に Microsoft Defender for Endpoint を展開する</span><span class="sxs-lookup"><span data-stu-id="f30f9-140">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span>](android-intune.md)
- [<span data-ttu-id="f30f9-141">Android の機能でエンドポイント用 Microsoft Defender を構成する</span><span class="sxs-lookup"><span data-stu-id="f30f9-141">Configure Microsoft Defender for Endpoint on Android features</span></span>](android-configure.md)

