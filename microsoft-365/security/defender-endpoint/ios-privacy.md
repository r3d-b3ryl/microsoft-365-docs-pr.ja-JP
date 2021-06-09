---
title: プライバシー情報 - Microsoft Defender for Endpoint on iOS
ms.reviewer: ''
description: iOS 上の Microsoft Defender for Endpoint のプライバシー情報について説明します。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, ios, policy, overview
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
ms.openlocfilehash: a232bd8d600df37d5b9b01921859556476ced345
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822372"
---
# <a name="privacy-information---microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="093c8-104">プライバシー情報 - Microsoft Defender for Endpoint on iOS</span><span class="sxs-lookup"><span data-stu-id="093c8-104">Privacy information - Microsoft Defender for Endpoint on iOS</span></span>

<span data-ttu-id="093c8-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="093c8-105">**Applies to:**</span></span>
- [<span data-ttu-id="093c8-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="093c8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="093c8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="093c8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="093c8-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="093c8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="093c8-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="093c8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!NOTE]
> <span data-ttu-id="093c8-110">iOS のエンドポイントの Defender は、VPN を使用して Web 保護機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="093c8-110">Defender for Endpoint on iOS uses a VPN to provide the Web Protection feature.</span></span> <span data-ttu-id="093c8-111">これは通常の VPN ではなく、デバイスの外部でトラフィックを受け取らないローカルまたは自己ループ VPN です。</span><span class="sxs-lookup"><span data-stu-id="093c8-111">This is not a regular VPN and is a local or self-looping VPN that does not take traffic outside the device.</span></span> <span data-ttu-id="093c8-112">**Microsoft または組織では、閲覧アクティビティが表示されない。**</span><span class="sxs-lookup"><span data-stu-id="093c8-112">**Microsoft or your organization, does not see your browsing activity.**</span></span>

<span data-ttu-id="093c8-113">iOS のエンドポイント用 Defender は、構成済みの iOS デバイスから情報を収集し、Defender for Endpoint を持つ同じテナントに格納します。</span><span class="sxs-lookup"><span data-stu-id="093c8-113">Defender for Endpoint on iOS collects information from your configured iOS devices and stores it in the same tenant where you have Defender for Endpoint.</span></span> <span data-ttu-id="093c8-114">この情報は、IOS の Defender for Endpoint をセキュリティで保護し、最新の状態に保ち、期待通り実行し、サービスをサポートするために収集されます。</span><span class="sxs-lookup"><span data-stu-id="093c8-114">The information is collected to help keep Defender for Endpoint on iOS secure, up-to-date, performing as expected, and to support the service.</span></span>

<span data-ttu-id="093c8-115">データ ストレージの詳細については [、「Microsoft Defender for Endpoint data storage and privacy」を参照してください](data-storage-privacy.md)。</span><span class="sxs-lookup"><span data-stu-id="093c8-115">For more information about data storage, see [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md).</span></span>


<span data-ttu-id="093c8-116">Android および iOS モバイル デバイスの Microsoft Defender for Endpoint に関する最も一般的なプライバシーに関する質問の詳細については [、「Microsoft Defender for Endpoint and your](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-and-your-privacy-on-android-and-ios-mobile-devices-4109bc54-8ec5-4433-9c33-d359b75ac22a)privacy on Android and iOS mobile devices」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="093c8-116">For more information on most common privacy questions about Microsoft Defender for Endpoint on Android and iOS mobile devices, see [Microsoft Defender for Endpoint and your privacy on Android and iOS mobile devices](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-and-your-privacy-on-android-and-ios-mobile-devices-4109bc54-8ec5-4433-9c33-d359b75ac22a).</span></span>

## <a name="required-data"></a><span data-ttu-id="093c8-117">必須データ</span><span class="sxs-lookup"><span data-stu-id="093c8-117">Required data</span></span> 

<span data-ttu-id="093c8-118">必要なデータは、iOS の Defender for Endpoint を期待通り動作させるのに必要なデータで構成されます。</span><span class="sxs-lookup"><span data-stu-id="093c8-118">Required data consists of data that is necessary to make Defender for Endpoint on iOS work as expected.</span></span> <span data-ttu-id="093c8-119">このデータはサービスの運用に不可欠であり、エンド ユーザー、組織、デバイス、アプリに関連するデータを含めできます。</span><span class="sxs-lookup"><span data-stu-id="093c8-119">This data is essential to the operation of the service and can include data related to the end user, organization, device, and apps.</span></span> 

<span data-ttu-id="093c8-120">収集するデータの種類の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="093c8-120">Here is a list of the types of data being collected:</span></span> 

### <a name="web-page-or-network-information"></a><span data-ttu-id="093c8-121">Web ページまたはネットワーク情報</span><span class="sxs-lookup"><span data-stu-id="093c8-121">Web page or Network information</span></span> 

- <span data-ttu-id="093c8-122">悪意のある接続または Web ページが検出された場合にのみ、Web サイトのドメイン名と IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="093c8-122">Domain name and IP address of the website only when a malicious connection or web page is detected.</span></span> 

### <a name="device-and-account-information"></a><span data-ttu-id="093c8-123">デバイスとアカウントの情報</span><span class="sxs-lookup"><span data-stu-id="093c8-123">Device and account information</span></span> 

- <span data-ttu-id="093c8-124">日付、時刻、iOS & CPU 情報、デバイス識別子などのデバイス情報 (デバイス識別子は次の 1 つ) です。</span><span class="sxs-lookup"><span data-stu-id="093c8-124">Device information such as date & time, iOS version, CPU info, and Device identifier, where Device identifier is one of the following:</span></span> 

    - <span data-ttu-id="093c8-125">Wi-Fi MAC アドレス</span><span class="sxs-lookup"><span data-stu-id="093c8-125">Wi-Fi adapter MAC address</span></span> 

    - <span data-ttu-id="093c8-126">ランダムに生成されたグローバル一意識別子 (GUID)</span><span class="sxs-lookup"><span data-stu-id="093c8-126">Randomly generated globally unique identifier (GUID)</span></span> 

- <span data-ttu-id="093c8-127">テナント、デバイス、およびユーザー情報</span><span class="sxs-lookup"><span data-stu-id="093c8-127">Tenant, Device, and User information</span></span> 

    - <span data-ttu-id="093c8-128">Azure Active Directory (AD) デバイス ID と Azure ユーザー ID - デバイスを一意に識別します。ユーザーは、それぞれ Azure Active directory にあります。</span><span class="sxs-lookup"><span data-stu-id="093c8-128">Azure Active Directory (AD) Device ID and Azure User ID - Uniquely identifies the device, User respectively at Azure Active directory.</span></span> 

    - <span data-ttu-id="093c8-129">Azure テナント ID - 組織内の組織を識別する GUID Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="093c8-129">Azure tenant ID - GUID that identifies your organization within Azure Active Directory.</span></span> 

    - <span data-ttu-id="093c8-130">Microsoft Defender for Endpoint org ID - デバイスが属する企業に関連付けられた一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="093c8-130">Microsoft Defender for Endpoint org ID - Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="093c8-131">Microsoft は、企業の選択セットと影響を受ける企業の数に影響を与える問題が発生した場合の識別を許可します。</span><span class="sxs-lookup"><span data-stu-id="093c8-131">Allows Microsoft to identify if there are issues affecting a select set of enterprises and the number of enterprises impacted.</span></span> 

    - <span data-ttu-id="093c8-132">ユーザー プリンシパル名 - ユーザーの電子メール ID。</span><span class="sxs-lookup"><span data-stu-id="093c8-132">User Principal Name - Email ID of the user.</span></span> 

### <a name="product-and-service-usage-data"></a><span data-ttu-id="093c8-133">製品とサービスの使用状況データ</span><span class="sxs-lookup"><span data-stu-id="093c8-133">Product and service usage data</span></span> 

<span data-ttu-id="093c8-134">次の情報は、デバイスにインストールされている Microsoft Defender for Endpoint アプリの場合にのみ収集されます。</span><span class="sxs-lookup"><span data-stu-id="093c8-134">The following information is collected only for Microsoft Defender for Endpoint app installed on the device.</span></span> 

- <span data-ttu-id="093c8-135">名前、バージョン、アプリアップグレードの状態を含むアプリ パッケージ情報。</span><span class="sxs-lookup"><span data-stu-id="093c8-135">App package info, including name, version, and app upgrade status.</span></span> 

- <span data-ttu-id="093c8-136">アプリで実行されるアクション。</span><span class="sxs-lookup"><span data-stu-id="093c8-136">Actions done in the app.</span></span> 

- <span data-ttu-id="093c8-137">iOS によって生成されたクラッシュ レポート ログ。</span><span class="sxs-lookup"><span data-stu-id="093c8-137">Crash report logs generated by iOS.</span></span> 

- <span data-ttu-id="093c8-138">メモリ使用量データ。</span><span class="sxs-lookup"><span data-stu-id="093c8-138">Memory usage data.</span></span> 

## <a name="optional-data"></a><span data-ttu-id="093c8-139">オプションのデータ</span><span class="sxs-lookup"><span data-stu-id="093c8-139">Optional Data</span></span> 

<span data-ttu-id="093c8-140">オプションのデータには、クライアントからの診断データとフィードバック データが含まれます。</span><span class="sxs-lookup"><span data-stu-id="093c8-140">Optional data includes diagnostic data and feedback data from the client.</span></span> <span data-ttu-id="093c8-141">オプションの診断データは、製品の改良に役立ち、問題の検出、診断、修正に役立つ高度な情報を提供する追加データです。</span><span class="sxs-lookup"><span data-stu-id="093c8-141">Optional diagnostic data is additional data that helps us make product improvements and provides enhanced information to help us detect, diagnose, and fix issues.</span></span> <span data-ttu-id="093c8-142">このデータは診断のみを目的としますが、サービス自体には必要ありません。</span><span class="sxs-lookup"><span data-stu-id="093c8-142">This data is only for diagnostic purposes and is not required for the service itself.</span></span> 

<span data-ttu-id="093c8-143">オプションの診断データには、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="093c8-143">Optional diagnostic data includes:</span></span> 

- <span data-ttu-id="093c8-144">Defender for Endpoint のアプリ、CPU、およびネットワーク使用率。</span><span class="sxs-lookup"><span data-stu-id="093c8-144">App, CPU, and network usage for Defender for Endpoint.</span></span> 

- <span data-ttu-id="093c8-145">Defender for Endpoint 用に管理者が構成した機能。</span><span class="sxs-lookup"><span data-stu-id="093c8-145">Features configured by the admin for Defender for Endpoint.</span></span> 

<span data-ttu-id="093c8-146">フィードバック データは、ユーザーが提供するアプリ内フィードバックを通じて収集されます。</span><span class="sxs-lookup"><span data-stu-id="093c8-146">Feedback Data is collected through in-app feedback provided by the user.</span></span> 

- <span data-ttu-id="093c8-147">ユーザーの電子メール アドレスを指定する場合。</span><span class="sxs-lookup"><span data-stu-id="093c8-147">The user's email address, if they choose to provide it.</span></span>

- <span data-ttu-id="093c8-148">フィードバックの種類 (微笑み、顔をしかめ、アイデア) と、ユーザーが送信したフィードバックコメント。</span><span class="sxs-lookup"><span data-stu-id="093c8-148">Feedback type (smile, frown, idea) and any feedback comments submitted by the user.</span></span> 

<span data-ttu-id="093c8-149">詳細については、「プライバシーの詳細 [」を参照してください](https://aka.ms/mdatpiosprivacystatement)。</span><span class="sxs-lookup"><span data-stu-id="093c8-149">For more information, see [More on Privacy](https://aka.ms/mdatpiosprivacystatement).</span></span>


