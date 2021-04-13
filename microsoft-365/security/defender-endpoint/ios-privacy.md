---
title: プライバシー情報 - Microsoft Defender for Endpoint on iOS
ms.reviewer: ''
description: iOS 上の Microsoft Defender for Endpoint のプライバシー情報について説明します。
keywords: microsoft、defender、atp、ios、ポリシー、概要
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
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: f5598df8a9e3493a1c4922f672468dd54e84c31e
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688203"
---
# <a name="privacy-information---microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="34c94-104">プライバシー情報 - Microsoft Defender for Endpoint on iOS</span><span class="sxs-lookup"><span data-stu-id="34c94-104">Privacy information - Microsoft Defender for Endpoint on iOS</span></span>

<span data-ttu-id="34c94-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="34c94-105">**Applies to:**</span></span>
- [<span data-ttu-id="34c94-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="34c94-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="34c94-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="34c94-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="34c94-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="34c94-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="34c94-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="34c94-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!NOTE]
> <span data-ttu-id="34c94-110">Defender for Endpoint for iOS では、VPN を使用して Web 保護機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="34c94-110">Defender for Endpoint for iOS uses a VPN to provide the Web Protection feature.</span></span> <span data-ttu-id="34c94-111">これは通常の VPN ではなく、デバイスの外部でトラフィックを受け取らないローカルまたは自己ループ VPN です。</span><span class="sxs-lookup"><span data-stu-id="34c94-111">This is not a regular VPN and is a local or self-looping VPN that does not take traffic outside the device.</span></span> <span data-ttu-id="34c94-112">**Microsoft または組織では、閲覧アクティビティが表示されない。**</span><span class="sxs-lookup"><span data-stu-id="34c94-112">**Microsoft or your organization, does not see your browsing activity.**</span></span>

<span data-ttu-id="34c94-113">Defender for Endpoint for iOS は、構成済みの iOS デバイスから情報を収集し、Defender for Endpoint がある同じテナントに保存します。</span><span class="sxs-lookup"><span data-stu-id="34c94-113">Defender for Endpoint for iOS collects information from your configured iOS devices and stores it in the same tenant where you have Defender for Endpoint.</span></span> <span data-ttu-id="34c94-114">この情報は、Defender for Endpoint for iOS をセキュリティで保護し、最新の状態に保ち、期待通り実行し、サービスをサポートするために収集されます。</span><span class="sxs-lookup"><span data-stu-id="34c94-114">The information is collected to help keep Defender for Endpoint for iOS secure, up-to-date, performing as expected, and to support the service.</span></span>

<span data-ttu-id="34c94-115">データ ストレージの詳細については [、「Microsoft Defender for Endpoint data storage and privacy」を参照してください](data-storage-privacy.md)。</span><span class="sxs-lookup"><span data-stu-id="34c94-115">For more information about data storage, see [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md).</span></span>

## <a name="required-data"></a><span data-ttu-id="34c94-116">必須データ</span><span class="sxs-lookup"><span data-stu-id="34c94-116">Required data</span></span> 

<span data-ttu-id="34c94-117">必要なデータは、iOS 用 Defender for Endpoint を期待通り動作させるのに必要なデータで構成されます。</span><span class="sxs-lookup"><span data-stu-id="34c94-117">Required data consists of data that is necessary to make Defender for Endpoint for iOS work as expected.</span></span> <span data-ttu-id="34c94-118">このデータはサービスの運用に不可欠であり、エンド ユーザー、組織、デバイス、アプリに関連するデータを含めできます。</span><span class="sxs-lookup"><span data-stu-id="34c94-118">This data is essential to the operation of the service and can include data related to the end user, organization, device, and apps.</span></span> 

<span data-ttu-id="34c94-119">収集するデータの種類の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="34c94-119">Here is a list of the types of data being collected:</span></span> 

### <a name="web-page-or-network-information"></a><span data-ttu-id="34c94-120">Web ページまたはネットワーク情報</span><span class="sxs-lookup"><span data-stu-id="34c94-120">Web page or Network information</span></span> 

- <span data-ttu-id="34c94-121">悪意のある接続または Web ページが検出された場合にのみ、Web サイトのドメイン名。</span><span class="sxs-lookup"><span data-stu-id="34c94-121">Domain name of the website only when a malicious connection or web page is detected.</span></span> 

### <a name="device-and-account-information"></a><span data-ttu-id="34c94-122">デバイスとアカウントの情報</span><span class="sxs-lookup"><span data-stu-id="34c94-122">Device and account information</span></span> 

- <span data-ttu-id="34c94-123">日付、時刻、iOS & CPU 情報、デバイス識別子などのデバイス情報 (デバイス識別子は次の 1 つ) です。</span><span class="sxs-lookup"><span data-stu-id="34c94-123">Device information such as date & time, iOS version, CPU info, and Device identifier, where Device identifier is one of the following:</span></span> 

    - <span data-ttu-id="34c94-124">Wi-Fi MAC アドレス</span><span class="sxs-lookup"><span data-stu-id="34c94-124">Wi-Fi adapter MAC address</span></span> 

    - <span data-ttu-id="34c94-125">ランダムに生成されたグローバル一意識別子 (GUID)</span><span class="sxs-lookup"><span data-stu-id="34c94-125">Randomly generated globally unique identifier (GUID)</span></span> 

- <span data-ttu-id="34c94-126">テナント、デバイス、およびユーザー情報</span><span class="sxs-lookup"><span data-stu-id="34c94-126">Tenant, Device, and User information</span></span> 

    - <span data-ttu-id="34c94-127">Azure Active Directory (AD) デバイス ID と Azure ユーザー ID - デバイスを一意に識別します。ユーザーは、それぞれ Azure Active directory にあります。</span><span class="sxs-lookup"><span data-stu-id="34c94-127">Azure Active Directory (AD) Device ID and Azure User ID - Uniquely identifies the device, User respectively at Azure Active directory.</span></span> 

    - <span data-ttu-id="34c94-128">Azure テナント ID - Azure Active Directory 内の組織を識別する GUID。</span><span class="sxs-lookup"><span data-stu-id="34c94-128">Azure tenant ID - GUID that identifies your organization within Azure Active Directory.</span></span> 

    - <span data-ttu-id="34c94-129">Microsoft Defender for Endpoint org ID - デバイスが属する企業に関連付けられた一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="34c94-129">Microsoft Defender for Endpoint org ID - Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="34c94-130">Microsoft は、企業の選択セットと影響を受ける企業の数に影響を与える問題が発生した場合の識別を許可します。</span><span class="sxs-lookup"><span data-stu-id="34c94-130">Allows Microsoft to identify if there are issues affecting a select set of enterprises and the number of enterprises impacted.</span></span> 

    - <span data-ttu-id="34c94-131">ユーザー プリンシパル名 - ユーザーの電子メール ID。</span><span class="sxs-lookup"><span data-stu-id="34c94-131">User Principal Name - Email ID of the user.</span></span> 

### <a name="product-and-service-usage-data"></a><span data-ttu-id="34c94-132">製品とサービスの使用状況データ</span><span class="sxs-lookup"><span data-stu-id="34c94-132">Product and service usage data</span></span> 

<span data-ttu-id="34c94-133">次の情報は、デバイスにインストールされている Microsoft Defender for Endpoint アプリの場合にのみ収集されます。</span><span class="sxs-lookup"><span data-stu-id="34c94-133">The following information is collected only for Microsoft Defender for Endpoint app installed on the device.</span></span> 

- <span data-ttu-id="34c94-134">名前、バージョン、アプリアップグレードの状態を含むアプリ パッケージ情報。</span><span class="sxs-lookup"><span data-stu-id="34c94-134">App package info, including name, version, and app upgrade status.</span></span> 

- <span data-ttu-id="34c94-135">アプリで実行されるアクション。</span><span class="sxs-lookup"><span data-stu-id="34c94-135">Actions done in the app.</span></span> 

- <span data-ttu-id="34c94-136">iOS によって生成されたクラッシュ レポート ログ。</span><span class="sxs-lookup"><span data-stu-id="34c94-136">Crash report logs generated by iOS.</span></span> 

- <span data-ttu-id="34c94-137">メモリ使用量データ。</span><span class="sxs-lookup"><span data-stu-id="34c94-137">Memory usage data.</span></span> 

## <a name="optional-data"></a><span data-ttu-id="34c94-138">オプションのデータ</span><span class="sxs-lookup"><span data-stu-id="34c94-138">Optional Data</span></span> 

<span data-ttu-id="34c94-139">オプションのデータには、クライアントからの診断データとフィードバック データが含まれます。</span><span class="sxs-lookup"><span data-stu-id="34c94-139">Optional data includes diagnostic data and feedback data from the client.</span></span> <span data-ttu-id="34c94-140">オプションの診断データは、製品の改良に役立ち、問題の検出、診断、修正に役立つ高度な情報を提供する追加データです。</span><span class="sxs-lookup"><span data-stu-id="34c94-140">Optional diagnostic data is additional data that helps us make product improvements and provides enhanced information to help us detect, diagnose, and fix issues.</span></span> <span data-ttu-id="34c94-141">このデータは診断のみを目的としますが、サービス自体には必要ありません。</span><span class="sxs-lookup"><span data-stu-id="34c94-141">This data is only for diagnostic purposes and is not required for the service itself.</span></span> 

<span data-ttu-id="34c94-142">オプションの診断データには、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="34c94-142">Optional diagnostic data includes:</span></span> 

- <span data-ttu-id="34c94-143">Defender for Endpoint のアプリ、CPU、およびネットワーク使用率。</span><span class="sxs-lookup"><span data-stu-id="34c94-143">App, CPU, and network usage for Defender for Endpoint.</span></span> 

- <span data-ttu-id="34c94-144">Defender for Endpoint 用に管理者が構成した機能。</span><span class="sxs-lookup"><span data-stu-id="34c94-144">Features configured by the admin for Defender for Endpoint.</span></span> 

<span data-ttu-id="34c94-145">フィードバック データは、ユーザーが提供するアプリ内フィードバックを通じて収集されます。</span><span class="sxs-lookup"><span data-stu-id="34c94-145">Feedback Data is collected through in-app feedback provided by the user.</span></span> 

- <span data-ttu-id="34c94-146">ユーザーの電子メール アドレスを指定する場合。</span><span class="sxs-lookup"><span data-stu-id="34c94-146">The user's email address, if they choose to provide it.</span></span>

- <span data-ttu-id="34c94-147">フィードバックの種類 (微笑み、顔をしかめ、アイデア) と、ユーザーが送信したフィードバックコメント。</span><span class="sxs-lookup"><span data-stu-id="34c94-147">Feedback type (smile, frown, idea) and any feedback comments submitted by the user.</span></span> 

<span data-ttu-id="34c94-148">詳細については、「プライバシーの詳細 [」を参照してください](https://aka.ms/mdatpiosprivacystatement)。</span><span class="sxs-lookup"><span data-stu-id="34c94-148">For more information, see [More on Privacy](https://aka.ms/mdatpiosprivacystatement).</span></span>


