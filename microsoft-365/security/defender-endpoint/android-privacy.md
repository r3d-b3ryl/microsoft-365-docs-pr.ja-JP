---
title: Android 用 Microsoft Defender ATP - プライバシー情報
description: プライバシーコントロール、プライバシーに影響を与えるポリシー設定を構成する方法、および Microsoft Defender ATP for Android で収集された診断データに関する情報。
keywords: microsoft, defender, atp, android, プライバシー, 診断
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
ms.openlocfilehash: abb22b2e733d1e40bd4f2733ef2d25767c69ccf7
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163329"
---
#  <a name="microsoft-defender-for-endpoint-for-android---privacy-information"></a><span data-ttu-id="83c9d-104">Microsoft Defender for Endpoint for Android - プライバシー情報</span><span class="sxs-lookup"><span data-stu-id="83c9d-104">Microsoft Defender for Endpoint for Android - Privacy information</span></span>

<span data-ttu-id="83c9d-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="83c9d-105">**Applies to:**</span></span>
- [<span data-ttu-id="83c9d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="83c9d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="83c9d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="83c9d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="83c9d-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="83c9d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="83c9d-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="83c9d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="83c9d-110">Defender for Endpoint for Android は、構成済みの Android デバイスから情報を収集し、Defender for Endpoint を持つ同じテナントに格納します。</span><span class="sxs-lookup"><span data-stu-id="83c9d-110">Defender for Endpoint for Android collects information from your configured Android devices and stores it in the same tenant where you have Defender for Endpoint.</span></span>

<span data-ttu-id="83c9d-111">情報は、Defender for Endpoint for Android のセキュリティを確保し、最新の状態に保ち、期待通り実行し、サービスをサポートするために収集されます。</span><span class="sxs-lookup"><span data-stu-id="83c9d-111">Information is collected to help keep Defender for Endpoint for Android secure, up-to-date, performing as expected and to support the service.</span></span>

## <a name="required-data"></a><span data-ttu-id="83c9d-112">必須データ</span><span class="sxs-lookup"><span data-stu-id="83c9d-112">Required Data</span></span> 

<span data-ttu-id="83c9d-113">必要なデータは、Android 用 Defender for Endpoint を期待通り動作させるのに必要なデータで構成されます。</span><span class="sxs-lookup"><span data-stu-id="83c9d-113">Required data consists of data that is necessary to make Defender for Endpoint for Android work as expected.</span></span> <span data-ttu-id="83c9d-114">このデータはサービスの運用に不可欠であり、エンド ユーザー、組織、デバイス、アプリに関連するデータを含めできます。</span><span class="sxs-lookup"><span data-stu-id="83c9d-114">This data is essential to the operation of the service and can include data related to the end user, organization, device, and apps.</span></span> <span data-ttu-id="83c9d-115">収集するデータの種類の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="83c9d-115">Here's a list of the types of data being collected:</span></span>

### <a name="app-information"></a><span data-ttu-id="83c9d-116">アプリ情報</span><span class="sxs-lookup"><span data-stu-id="83c9d-116">App information</span></span>

<span data-ttu-id="83c9d-117">デバイス上の Android アプリケーション パッケージ (APK) に関する情報 (以下を含む)</span><span class="sxs-lookup"><span data-stu-id="83c9d-117">Information about Android application packages (APKs) on the device including</span></span>

-  <span data-ttu-id="83c9d-118">ソースのインストール</span><span class="sxs-lookup"><span data-stu-id="83c9d-118">Install source</span></span>
-  <span data-ttu-id="83c9d-119">APK の保存場所 (ファイル パス)</span><span class="sxs-lookup"><span data-stu-id="83c9d-119">Storage location (file path) of the APK</span></span>
-  <span data-ttu-id="83c9d-120">インストールの時間、APK のサイズ、およびアクセス許可</span><span class="sxs-lookup"><span data-stu-id="83c9d-120">Time of install, size of APK and permissions</span></span>

### <a name="web-page--network-information"></a><span data-ttu-id="83c9d-121">Web ページ / ネットワーク情報</span><span class="sxs-lookup"><span data-stu-id="83c9d-121">Web page / Network information</span></span>

- <span data-ttu-id="83c9d-122">[完全な URL] (サポートされているブラウザーの場合) (クリック時)</span><span class="sxs-lookup"><span data-stu-id="83c9d-122">Full URL (on supported browsers), when clicked</span></span>
- <span data-ttu-id="83c9d-123">接続情報</span><span class="sxs-lookup"><span data-stu-id="83c9d-123">Connection information</span></span>
- <span data-ttu-id="83c9d-124">プロトコルの種類 (HTTP、HTTPS など)</span><span class="sxs-lookup"><span data-stu-id="83c9d-124">Protocol type (such as HTTP, HTTPS, etc.)</span></span>


### <a name="device-and-account-information"></a><span data-ttu-id="83c9d-125">デバイスとアカウントの情報</span><span class="sxs-lookup"><span data-stu-id="83c9d-125">Device and account information</span></span>

- <span data-ttu-id="83c9d-126">日付、時刻、&、OEM モデル、CPU 情報、デバイス識別子などのデバイス情報</span><span class="sxs-lookup"><span data-stu-id="83c9d-126">Device information such as date & time, Android version, OEM model, CPU       info, and Device identifier</span></span>
- <span data-ttu-id="83c9d-127">デバイス識別子は、次のいずれかを示します。</span><span class="sxs-lookup"><span data-stu-id="83c9d-127">Device identifier is one of the below:</span></span>
    - <span data-ttu-id="83c9d-128">Wi-Fi MAC アドレス</span><span class="sxs-lookup"><span data-stu-id="83c9d-128">Wi-Fi adapter MAC address</span></span>
    - <span data-ttu-id="83c9d-129">[Android ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (デバイスの初回起動時に Android によって生成された場合)</span><span class="sxs-lookup"><span data-stu-id="83c9d-129">[Android       ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (as generated by Android at the time of first boot of the device)</span></span>
    - <span data-ttu-id="83c9d-130">ランダムに生成されたグローバル一意識別子 (GUID)</span><span class="sxs-lookup"><span data-stu-id="83c9d-130">Randomly generated globally unique identifier (GUID)</span></span>

- <span data-ttu-id="83c9d-131">テナント、デバイス、およびユーザー情報</span><span class="sxs-lookup"><span data-stu-id="83c9d-131">Tenant, Device and User information</span></span>
    -   <span data-ttu-id="83c9d-132">Azure Active Directory (AD) デバイス ID と Azure ユーザー ID: デバイスを一意に識別します。ユーザーは、それぞれ Azure Active directory にあります。</span><span class="sxs-lookup"><span data-stu-id="83c9d-132">Azure Active Directory (AD) Device ID and Azure User ID: Uniquely     identifies the device, User respectively at Azure Active directory.</span></span>

    -   <span data-ttu-id="83c9d-133">Azure テナント ID - Azure Active Directory 内の組織を識別する GUID</span><span class="sxs-lookup"><span data-stu-id="83c9d-133">Azure tenant ID - GUID that identifies your organization within     Azure Active Directory</span></span>

    -   <span data-ttu-id="83c9d-134">Microsoft Defender ATP 組織 ID - デバイスが属する企業に関連付けられた一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="83c9d-134">Microsoft Defender ATP org ID - Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="83c9d-135">Microsoft は、問題が企業の選択セットに影響を与えるかどうか、および影響を受け取る企業の数を特定できます。</span><span class="sxs-lookup"><span data-stu-id="83c9d-135">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted</span></span> 

    -   <span data-ttu-id="83c9d-136">ユーザー プリンシパル名 – ユーザーの電子メール ID</span><span class="sxs-lookup"><span data-stu-id="83c9d-136">User Principal Name – Email ID of the user</span></span>

### <a name="product-and-service-usage-data"></a><span data-ttu-id="83c9d-137">製品とサービスの使用状況データ</span><span class="sxs-lookup"><span data-stu-id="83c9d-137">Product and service usage data</span></span>
-   <span data-ttu-id="83c9d-138">名前、バージョン、アプリアップグレードの状態を含むアプリ パッケージ情報</span><span class="sxs-lookup"><span data-stu-id="83c9d-138">App package info, including name, version, and app upgrade status</span></span>

-   <span data-ttu-id="83c9d-139">アプリで実行されるアクション</span><span class="sxs-lookup"><span data-stu-id="83c9d-139">Actions performed in the app</span></span>

-   <span data-ttu-id="83c9d-140">脅威の検出情報 (脅威名、カテゴリなど)</span><span class="sxs-lookup"><span data-stu-id="83c9d-140">Threat detection information, such as threat name, category, etc.</span></span>

-   <span data-ttu-id="83c9d-141">Android によって生成されたクラッシュ レポート ログ</span><span class="sxs-lookup"><span data-stu-id="83c9d-141">Crash report logs generated by Android</span></span>

## <a name="optional-data"></a><span data-ttu-id="83c9d-142">オプションのデータ</span><span class="sxs-lookup"><span data-stu-id="83c9d-142">Optional Data</span></span>

<span data-ttu-id="83c9d-143">オプションのデータには、診断データとフィードバック データが含まれます。</span><span class="sxs-lookup"><span data-stu-id="83c9d-143">Optional data includes diagnostic data and feedback data.</span></span> <span data-ttu-id="83c9d-144">オプションの診断データは、製品の改良に役立ち、問題の検出、診断、修正に役立つ高度な情報を提供する追加データです。</span><span class="sxs-lookup"><span data-stu-id="83c9d-144">Optional diagnostic data is additional data that helps us make product improvements and provides enhanced information to help us detect, diagnose, and fix issues.</span></span> <span data-ttu-id="83c9d-145">オプションの診断データには、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="83c9d-145">Optional diagnostic data includes:</span></span>

-   <span data-ttu-id="83c9d-146">アプリ、CPU、およびネットワークの使用状況</span><span class="sxs-lookup"><span data-stu-id="83c9d-146">App, CPU, and network usage</span></span>

-   <span data-ttu-id="83c9d-147">アプリの観点からデバイスの状態 (スキャンの状態、スキャンのタイミング、付与されたアプリのアクセス許可、アップグレードの状態など)</span><span class="sxs-lookup"><span data-stu-id="83c9d-147">State of the device from the app perspective, including scan status, scan timings, app permissions granted, and upgrade status</span></span>

-   <span data-ttu-id="83c9d-148">管理者が構成した機能</span><span class="sxs-lookup"><span data-stu-id="83c9d-148">Features configured by the admin</span></span>

-   <span data-ttu-id="83c9d-149">デバイス上のブラウザーに関する基本情報</span><span class="sxs-lookup"><span data-stu-id="83c9d-149">Basic information about the browsers on the device</span></span>

<span data-ttu-id="83c9d-150">**フィードバック データは** 、ユーザーが提供するアプリ内フィードバックを通じて収集されます。</span><span class="sxs-lookup"><span data-stu-id="83c9d-150">**Feedback Data** is collected through in-app feedback provided by the user</span></span>

-   <span data-ttu-id="83c9d-151">ユーザーの電子メール アドレスを指定する場合</span><span class="sxs-lookup"><span data-stu-id="83c9d-151">The user’s email address, if they choose to provide it</span></span>

-   <span data-ttu-id="83c9d-152">フィードバックの種類 (微笑み、顔をしかめ、アイデア) と、ユーザーが送信したフィードバック コメント</span><span class="sxs-lookup"><span data-stu-id="83c9d-152">Feedback type (smile, frown, idea) and any feedback comments submitted by the user</span></span>
