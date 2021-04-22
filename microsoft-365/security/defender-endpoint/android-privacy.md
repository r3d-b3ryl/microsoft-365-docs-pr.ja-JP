---
title: Android 用 Microsoft Defender for Endpoint - プライバシー情報
description: プライバシー制御、プライバシーに影響を与えるポリシー設定を構成する方法、および Android 上の Microsoft Defender for Endpoint で収集された診断データに関する情報。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, android, privacy, diagnostic
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1aaae2970cfb2f6da82507eefa87c8d0e2227661
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939626"
---
#  <a name="microsoft-defender-for-endpoint-on-android---privacy-information"></a><span data-ttu-id="36d46-104">Android 用 Microsoft Defender for Endpoint - プライバシー情報</span><span class="sxs-lookup"><span data-stu-id="36d46-104">Microsoft Defender for Endpoint on Android - Privacy information</span></span>

<span data-ttu-id="36d46-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="36d46-105">**Applies to:**</span></span>
- [<span data-ttu-id="36d46-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="36d46-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="36d46-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="36d46-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="36d46-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="36d46-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="36d46-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="36d46-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="36d46-110">Defender for Endpoint on Android は、構成済みの Android デバイスから情報を収集し、Defender for Endpoint がある同じテナントに保存します。</span><span class="sxs-lookup"><span data-stu-id="36d46-110">Defender for Endpoint on Android collects information from your configured Android devices and stores it in the same tenant where you have Defender for Endpoint.</span></span> <span data-ttu-id="36d46-111">この情報は、Defender for Endpoint for Android をセキュリティで保護し、最新の状態に保ち、期待通り実行し、サービスをサポートするために収集されます。</span><span class="sxs-lookup"><span data-stu-id="36d46-111">The information is collected to help keep Defender for Endpoint for Android secure, up-to-date, performing as expected, and to support the service.</span></span>

<span data-ttu-id="36d46-112">データ ストレージの詳細については [、「Microsoft Defender for Endpoint data storage and privacy」を参照してください](data-storage-privacy.md)。</span><span class="sxs-lookup"><span data-stu-id="36d46-112">For more information about data storage, see [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md).</span></span>

<span data-ttu-id="36d46-113">情報は、Defender for Endpoint for Android のセキュリティを確保し、最新の状態に保ち、期待通り実行し、サービスをサポートするために収集されます。</span><span class="sxs-lookup"><span data-stu-id="36d46-113">Information is collected to help keep Defender for Endpoint for Android secure, up-to-date, performing as expected and to support the service.</span></span>

## <a name="required-data"></a><span data-ttu-id="36d46-114">必須データ</span><span class="sxs-lookup"><span data-stu-id="36d46-114">Required Data</span></span> 

<span data-ttu-id="36d46-115">必要なデータは、Android 用 Defender for Endpoint を期待通り動作させるのに必要なデータで構成されます。</span><span class="sxs-lookup"><span data-stu-id="36d46-115">Required data consists of data that is necessary to make Defender for Endpoint for Android work as expected.</span></span> <span data-ttu-id="36d46-116">このデータはサービスの運用に不可欠であり、エンド ユーザー、組織、デバイス、アプリに関連するデータを含めできます。</span><span class="sxs-lookup"><span data-stu-id="36d46-116">This data is essential to the operation of the service and can include data related to the end user, organization, device, and apps.</span></span> <span data-ttu-id="36d46-117">収集するデータの種類の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="36d46-117">Here's a list of the types of data being collected:</span></span>

### <a name="app-information"></a><span data-ttu-id="36d46-118">アプリ情報</span><span class="sxs-lookup"><span data-stu-id="36d46-118">App information</span></span>

<span data-ttu-id="36d46-119">デバイス上 **の** 悪意のある Android アプリケーション パッケージ (APK) に関する情報 (以下を含む)</span><span class="sxs-lookup"><span data-stu-id="36d46-119">Information about **malicious** Android application packages (APKs) on the device including</span></span>

-  <span data-ttu-id="36d46-120">ソースのインストール</span><span class="sxs-lookup"><span data-stu-id="36d46-120">Install source</span></span>
-  <span data-ttu-id="36d46-121">APK の保存場所 (ファイル パス)</span><span class="sxs-lookup"><span data-stu-id="36d46-121">Storage location (file path) of the APK</span></span>
-  <span data-ttu-id="36d46-122">インストールの時間、APK のサイズ、およびアクセス許可</span><span class="sxs-lookup"><span data-stu-id="36d46-122">Time of install, size of APK and permissions</span></span>

### <a name="web-page--network-information"></a><span data-ttu-id="36d46-123">Web ページ / ネットワーク情報</span><span class="sxs-lookup"><span data-stu-id="36d46-123">Web page / Network information</span></span>

- <span data-ttu-id="36d46-124">悪意のある接続または Web ページが検出された場合にのみ、Web サイトの完全な URL。</span><span class="sxs-lookup"><span data-stu-id="36d46-124">Full URL of the website only when a malicious connection or web page is detected.</span></span>
- <span data-ttu-id="36d46-125">接続情報</span><span class="sxs-lookup"><span data-stu-id="36d46-125">Connection information</span></span>
- <span data-ttu-id="36d46-126">プロトコルの種類 (HTTP、HTTPS など)</span><span class="sxs-lookup"><span data-stu-id="36d46-126">Protocol type (such as HTTP, HTTPS, etc.)</span></span>


### <a name="device-and-account-information"></a><span data-ttu-id="36d46-127">デバイスとアカウントの情報</span><span class="sxs-lookup"><span data-stu-id="36d46-127">Device and account information</span></span>

- <span data-ttu-id="36d46-128">日付、時刻、&、OEM モデル、CPU 情報、デバイス識別子などのデバイス情報</span><span class="sxs-lookup"><span data-stu-id="36d46-128">Device information such as date & time, Android version, OEM model, CPU       info, and Device identifier</span></span>
- <span data-ttu-id="36d46-129">デバイス識別子は、次のいずれかを示します。</span><span class="sxs-lookup"><span data-stu-id="36d46-129">Device identifier is one of the below:</span></span>
    - <span data-ttu-id="36d46-130">Wi-Fi MAC アドレス</span><span class="sxs-lookup"><span data-stu-id="36d46-130">Wi-Fi adapter MAC address</span></span>
    - <span data-ttu-id="36d46-131">[Android ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (デバイスの初回起動時に Android によって生成された場合)</span><span class="sxs-lookup"><span data-stu-id="36d46-131">[Android       ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (as generated by Android at the time of first boot of the device)</span></span>
    - <span data-ttu-id="36d46-132">ランダムに生成されたグローバル一意識別子 (GUID)</span><span class="sxs-lookup"><span data-stu-id="36d46-132">Randomly generated globally unique identifier (GUID)</span></span>

- <span data-ttu-id="36d46-133">テナント、デバイス、およびユーザー情報</span><span class="sxs-lookup"><span data-stu-id="36d46-133">Tenant, Device and User information</span></span>
    -   <span data-ttu-id="36d46-134">Azure Active Directory (AD) デバイス ID と Azure ユーザー ID: デバイスを一意に識別します。ユーザーは、それぞれ Azure Active directory にあります。</span><span class="sxs-lookup"><span data-stu-id="36d46-134">Azure Active Directory (AD) Device ID and Azure User ID: Uniquely     identifies the device, User respectively at Azure Active directory.</span></span>

    -   <span data-ttu-id="36d46-135">Azure テナント ID - Azure Active Directory 内の組織を識別する GUID</span><span class="sxs-lookup"><span data-stu-id="36d46-135">Azure tenant ID - GUID that identifies your organization within     Azure Active Directory</span></span>

    -   <span data-ttu-id="36d46-136">Microsoft Defender for Endpoint org ID - デバイスが属する企業に関連付けられた一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="36d46-136">Microsoft Defender for Endpoint org ID - Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="36d46-137">Microsoft は、問題が企業の選択セットに影響を与えるかどうか、および影響を受け取る企業の数を特定できます。</span><span class="sxs-lookup"><span data-stu-id="36d46-137">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted</span></span> 

    -   <span data-ttu-id="36d46-138">ユーザー プリンシパル名 – ユーザーの電子メール ID</span><span class="sxs-lookup"><span data-stu-id="36d46-138">User Principal Name – Email ID of the user</span></span>

### <a name="product-and-service-usage-data"></a><span data-ttu-id="36d46-139">製品とサービスの使用状況データ</span><span class="sxs-lookup"><span data-stu-id="36d46-139">Product and service usage data</span></span>

<span data-ttu-id="36d46-140">次の情報は、デバイスにインストールされている Microsoft Defender for Endpoint アプリの場合にのみ収集されます。</span><span class="sxs-lookup"><span data-stu-id="36d46-140">The following information is collected only for Microsoft Defender for Endpoint app installed on the device.</span></span> 

-   <span data-ttu-id="36d46-141">名前、バージョン、アプリアップグレードの状態を含むアプリ パッケージ情報</span><span class="sxs-lookup"><span data-stu-id="36d46-141">App package info, including name, version, and app upgrade status</span></span>

-   <span data-ttu-id="36d46-142">アプリで実行されるアクション</span><span class="sxs-lookup"><span data-stu-id="36d46-142">Actions performed in the app</span></span>

-   <span data-ttu-id="36d46-143">脅威の検出情報 (脅威名、カテゴリなど)</span><span class="sxs-lookup"><span data-stu-id="36d46-143">Threat detection information, such as threat name, category, etc.</span></span>

-   <span data-ttu-id="36d46-144">Android によって生成されたクラッシュ レポート ログ</span><span class="sxs-lookup"><span data-stu-id="36d46-144">Crash report logs generated by Android</span></span>

## <a name="optional-data"></a><span data-ttu-id="36d46-145">オプションのデータ</span><span class="sxs-lookup"><span data-stu-id="36d46-145">Optional Data</span></span>

<span data-ttu-id="36d46-146">オプションのデータには、診断データとフィードバック データが含まれます。</span><span class="sxs-lookup"><span data-stu-id="36d46-146">Optional data includes diagnostic data and feedback data.</span></span> <span data-ttu-id="36d46-147">オプションの診断データは、製品の改良に役立ち、問題の検出、診断、修正に役立つ高度な情報を提供する追加データです。</span><span class="sxs-lookup"><span data-stu-id="36d46-147">Optional diagnostic data is additional data that helps us make product improvements and provides enhanced information to help us detect, diagnose, and fix issues.</span></span> <span data-ttu-id="36d46-148">オプションの診断データには、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="36d46-148">Optional diagnostic data includes:</span></span>

-   <span data-ttu-id="36d46-149">アプリ、CPU、およびネットワークの使用状況</span><span class="sxs-lookup"><span data-stu-id="36d46-149">App, CPU, and network usage</span></span>

-   <span data-ttu-id="36d46-150">アプリの観点からデバイスの状態 (スキャンの状態、スキャンのタイミング、付与されたアプリのアクセス許可、アップグレードの状態など)</span><span class="sxs-lookup"><span data-stu-id="36d46-150">State of the device from the app perspective, including scan status, scan timings, app permissions granted, and upgrade status</span></span>

-   <span data-ttu-id="36d46-151">管理者が構成した機能</span><span class="sxs-lookup"><span data-stu-id="36d46-151">Features configured by the admin</span></span>

-   <span data-ttu-id="36d46-152">デバイス上のブラウザーに関する基本情報</span><span class="sxs-lookup"><span data-stu-id="36d46-152">Basic information about the browsers on the device</span></span>

<span data-ttu-id="36d46-153">**フィードバック データは** 、ユーザーが提供するアプリ内フィードバックを通じて収集されます。</span><span class="sxs-lookup"><span data-stu-id="36d46-153">**Feedback Data** is collected through in-app feedback provided by the user</span></span>

-   <span data-ttu-id="36d46-154">ユーザーの電子メール アドレスを指定する場合</span><span class="sxs-lookup"><span data-stu-id="36d46-154">The user’s email address, if they choose to provide it</span></span>

-   <span data-ttu-id="36d46-155">フィードバックの種類 (微笑み、顔をしかめ、アイデア) と、ユーザーが送信したフィードバック コメント</span><span class="sxs-lookup"><span data-stu-id="36d46-155">Feedback type (smile, frown, idea) and any feedback comments submitted by the user</span></span>
