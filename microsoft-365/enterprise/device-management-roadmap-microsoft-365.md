---
title: Microsoft 365 のデバイス管理ロードマップ
keywords: Microsoft 365、Microsoft 365 enterprise、Microsoft 365 ドキュメント、モバイル デバイス管理、Intune
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 08/10/2020
ms.topic: conceptual
f1.keywords:
- NOCSH
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
description: Microsoft 365 のデバイス管理をセットアップするためのロードマップ。
ms.openlocfilehash: 79be47d6bc83c124f2203866986e06181a1f7f3d
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749541"
---
# <a name="device-management-roadmap-for-microsoft-365"></a><span data-ttu-id="845ab-104">Microsoft 365 のデバイス管理ロードマップ</span><span class="sxs-lookup"><span data-stu-id="845ab-104">Device management roadmap for Microsoft 365</span></span>

<span data-ttu-id="845ab-105">Microsoft 365 for enterprise には、組織内のデバイスとそのアプリを管理するのに役立つ機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="845ab-105">Microsoft 365 for enterprise includes features to help manage devices, and their apps, within your organization.</span></span> <span data-ttu-id="845ab-106">モバイル デバイスを管理すると、組織のリソースをセキュリティで保護し、保護できます。</span><span class="sxs-lookup"><span data-stu-id="845ab-106">Managing mobile devices helps you secure and protect your organization's resources.</span></span>

<span data-ttu-id="845ab-107">デバイス管理には、次の 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="845ab-107">There are two options for device management:</span></span>

- [<span data-ttu-id="845ab-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="845ab-108">Microsoft Intune</span></span>](#microsoft-intune)
- [<span data-ttu-id="845ab-109">基本的なモビリティとセキュリティ</span><span class="sxs-lookup"><span data-stu-id="845ab-109">Basic Mobility and Security</span></span>](#basic-mobility-and-security)

## <a name="microsoft-intune"></a><span data-ttu-id="845ab-110">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="845ab-110">Microsoft Intune</span></span>

<span data-ttu-id="845ab-111">Microsoft Intune を使用して、モバイル デバイス管理またはモバイル アプリケーション管理を使用して組織へのアクセスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="845ab-111">You can use Microsoft Intune to manage access to your organization using mobile device management or mobile application management.</span></span> <span data-ttu-id="845ab-112">モバイル デバイス管理は、ユーザーが Intune でデバイスを "登録" する場合です。</span><span class="sxs-lookup"><span data-stu-id="845ab-112">Mobile device management is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="845ab-113">デバイスが登録された後は、管理対象デバイスです。したがって、組織のポリシー、ルール、および設定を受け取る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="845ab-113">After a device is enrolled, it is a managed device; therefore, it can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="845ab-114">たとえば、特定のアプリのインストール、パスワード ポリシーの作成、VPN 接続のインストールなどです。</span><span class="sxs-lookup"><span data-stu-id="845ab-114">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="845ab-115">自分の個人用デバイスを持つユーザーは、デバイスを登録したり、Intune と組織のポリシーで管理したりしたくない場合があります。</span><span class="sxs-lookup"><span data-stu-id="845ab-115">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="845ab-116">ただし、組織のリソースとデータを保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="845ab-116">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="845ab-117">このシナリオでは、モバイル アプリケーション管理を使用してアプリを保護できます。</span><span class="sxs-lookup"><span data-stu-id="845ab-117">In this scenario, you can protect your apps using mobile application management.</span></span> <span data-ttu-id="845ab-118">たとえば、モバイル アプリケーション管理ポリシーを使用して、ユーザーがデバイス上の SharePoint Online にアクセスするときに PIN の入力を要求できます。</span><span class="sxs-lookup"><span data-stu-id="845ab-118">For example, you can use a mobile application management policy that requires a user to enter a PIN when accessing SharePoint Online on the device.</span></span>

<span data-ttu-id="845ab-119">また、個人のデバイスと組織が所有するデバイスを管理する方法も決定します。</span><span class="sxs-lookup"><span data-stu-id="845ab-119">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="845ab-120">デバイスの用途に応じて、デバイスの扱い方が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="845ab-120">You might want to treat devices differently, depending on their uses.</span></span>

## <a name="basic-mobility-and-security"></a><span data-ttu-id="845ab-121">基本的なモビリティとセキュリティ</span><span class="sxs-lookup"><span data-stu-id="845ab-121">Basic Mobility and Security</span></span>

<span data-ttu-id="845ab-122">これは Microsoft 365 に組み込み、iPhone、iPad、Android、Windows スマートフォンなど、ユーザーのモバイル デバイスのセキュリティ保護と管理に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="845ab-122">This is built into Microsoft 365 and helps you secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="845ab-123">デバイスのセキュリティ ポリシーを作成および管理したり、リモートでデバイスをワイプしたり、詳細なデバイス レポートを参照できます。</span><span class="sxs-lookup"><span data-stu-id="845ab-123">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span>

## <a name="choose-between-the-two-options"></a><span data-ttu-id="845ab-124">2 つのオプションから選択する</span><span class="sxs-lookup"><span data-stu-id="845ab-124">Choose between the two options</span></span>

<span data-ttu-id="845ab-125">最適なデバイス管理オプションを適切に評価するには [、「Basic Mobility Security](https://docs.microsoft.com/office365/securitycompliance/choose-between-mdm-and-intune)と Intune のどちらを選択する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="845ab-125">To help you better assess which device management option is best for you, see [Choose between Basic Mobility Security and Intune](https://docs.microsoft.com/office365/securitycompliance/choose-between-mdm-and-intune).</span></span>

<span data-ttu-id="845ab-126">評価に基づいて、次の方法でデバイスの管理を開始します。</span><span class="sxs-lookup"><span data-stu-id="845ab-126">Based on your assessment, get started managing your devices with:</span></span>

- [<span data-ttu-id="845ab-127">Intune</span><span class="sxs-lookup"><span data-stu-id="845ab-127">Intune</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide)
- [<span data-ttu-id="845ab-128">基本的なモビリティとセキュリティ</span><span class="sxs-lookup"><span data-stu-id="845ab-128">Basic Mobility and Security</span></span>](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)
 
## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="845ab-129">ID とデバイスのアクセスに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="845ab-129">Identity and device access recommendations</span></span>

<span data-ttu-id="845ab-130">Microsoft では、セキュアで生産性の高い労働力を確保するために [ID とデバイスのアクセス](../security/office-365-security/microsoft-365-policies-configurations.md)に関する一連の推奨事項を提供しています。</span><span class="sxs-lookup"><span data-stu-id="845ab-130">Microsoft provides a set of recommendations for [identity and device access](../security/office-365-security/microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="845ab-131">デバイス アクセスの場合は、次の記事の推奨事項と設定を使用してください。</span><span class="sxs-lookup"><span data-stu-id="845ab-131">For device access, use the recommendations and settings in these articles:</span></span>

- [<span data-ttu-id="845ab-132">前提条件</span><span class="sxs-lookup"><span data-stu-id="845ab-132">Prerequisites</span></span>](../security/office-365-security/identity-access-prerequisites.md)
- [<span data-ttu-id="845ab-133">共通 ID とデバイスのアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="845ab-133">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a><span data-ttu-id="845ab-134">Contoso 社が Microsoft 365 のデバイス管理を行った方法</span><span class="sxs-lookup"><span data-stu-id="845ab-134">How Contoso did device management for Microsoft 365</span></span>

<span data-ttu-id="845ab-135">架空の代表的な多国籍企業が、Microsoft 365 クラウド サービスを使用してモバイル デバイス管理インフラストラクチャを展開した方法については [、「Contoso](contoso-mdm.md)のモバイル デバイス管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="845ab-135">For information about how a fictional but representative multi-national business deployed their mobile device management infrastructure with Microsoft 365 cloud services, see [Mobile device management for Contoso](contoso-mdm.md).</span></span>
