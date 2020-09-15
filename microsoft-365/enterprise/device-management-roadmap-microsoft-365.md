---
title: Microsoft 365 のデバイス管理のロードマップ
keywords: Microsoft 365、Microsoft 365 for enterprise、Microsoft 365 ドキュメント、モバイルデバイス管理、Intune
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
ms.openlocfilehash: bb19c38d5cf92cfc04ac83bc29573ea24c93ef30
ms.sourcegitcommit: 13ae76220b4ad688438a5d1031a6e1b5300ffa23
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "47775173"
---
# <a name="device-management-roadmap-for-microsoft-365"></a><span data-ttu-id="ba2e4-104">Microsoft 365 のデバイス管理のロードマップ</span><span class="sxs-lookup"><span data-stu-id="ba2e4-104">Device management roadmap for Microsoft 365</span></span>

<span data-ttu-id="ba2e4-105">Microsoft 365 for enterprise では、組織内のデバイスとアプリを管理するのに役立つ機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="ba2e4-105">Microsoft 365 for enterprise includes features to help manage devices, and their apps, within your organization.</span></span> <span data-ttu-id="ba2e4-106">モバイルデバイスを管理することにより、組織のリソースを保護し、保護することができます。</span><span class="sxs-lookup"><span data-stu-id="ba2e4-106">Managing mobile devices helps you secure and protect your organization's resources.</span></span>

<span data-ttu-id="ba2e4-107">デバイス管理には、次の2つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="ba2e4-107">There are two options for device management:</span></span>

- [<span data-ttu-id="ba2e4-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ba2e4-108">Microsoft Intune</span></span>](#microsoft-intune)
- [<span data-ttu-id="ba2e4-109">基本的なモビリティとセキュリティ</span><span class="sxs-lookup"><span data-stu-id="ba2e4-109">Basic Mobility and Security</span></span>](#basic-mobility-and-security)

## <a name="microsoft-intune"></a><span data-ttu-id="ba2e4-110">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ba2e4-110">Microsoft Intune</span></span>

<span data-ttu-id="ba2e4-111">Microsoft Intune を使用して、モバイルデバイス管理またはモバイルアプリケーション管理を使用して、組織へのアクセスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="ba2e4-111">You can use Microsoft Intune to manage access to your organization using mobile device management or mobile application management.</span></span> <span data-ttu-id="ba2e4-112">モバイルデバイスの管理は、ユーザーが Intune にデバイスを登録するときに行います。</span><span class="sxs-lookup"><span data-stu-id="ba2e4-112">Mobile device management is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="ba2e4-113">登録されたデバイスは、管理されたデバイスです。そのため、組織のポリシー、ルール、および設定を受信することができます。</span><span class="sxs-lookup"><span data-stu-id="ba2e4-113">After a device is enrolled, it is a managed device; therefore, it can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="ba2e4-114">たとえば、特定のアプリをインストールしたり、パスワードポリシーを作成したり、VPN 接続をインストールしたりできます。</span><span class="sxs-lookup"><span data-stu-id="ba2e4-114">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="ba2e4-115">独自の個人用デバイスを使用しているユーザーは、自分のデバイスを登録したり、Intune および組織のポリシーによって管理したりすることは望まない場合があります。</span><span class="sxs-lookup"><span data-stu-id="ba2e4-115">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="ba2e4-116">ただし、組織のリソースとデータを保護する必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="ba2e4-116">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="ba2e4-117">このシナリオでは、モバイルアプリケーション管理を使用してアプリを保護することができます。</span><span class="sxs-lookup"><span data-stu-id="ba2e4-117">In this scenario, you can protect your apps using mobile application management.</span></span> <span data-ttu-id="ba2e4-118">たとえば、モバイルアプリケーション管理ポリシーを使用して、ユーザーがデバイス上の Microsoft SharePoint にアクセスするときに PIN を入力するよう要求することができます。</span><span class="sxs-lookup"><span data-stu-id="ba2e4-118">For example, you can use a mobile application management policy that requires a user to enter a PIN when accessing Microsoft SharePoint on the device.</span></span>

<span data-ttu-id="ba2e4-119">また、個人デバイスおよび組織所有のデバイスを管理する方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="ba2e4-119">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="ba2e4-120">使用方法に応じて、デバイスを異なる方法で扱うことができます。</span><span class="sxs-lookup"><span data-stu-id="ba2e4-120">You might want to treat devices differently, depending on their uses.</span></span>

<span data-ttu-id="ba2e4-121">Intune を使用してデバイスを管理するには、 [ここ](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide)から開始してください。</span><span class="sxs-lookup"><span data-stu-id="ba2e4-121">To manage devices using Intune, start [here](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide).</span></span>

## <a name="basic-mobility-and-security"></a><span data-ttu-id="ba2e4-122">基本的なモビリティとセキュリティ</span><span class="sxs-lookup"><span data-stu-id="ba2e4-122">Basic Mobility and Security</span></span>

<span data-ttu-id="ba2e4-123">これは Microsoft 365 に組み込まれており、iPhones、Ipad、Androids、Windows phone などのユーザーのモバイルデバイスをセキュリティで保護し、管理することができます。</span><span class="sxs-lookup"><span data-stu-id="ba2e4-123">This is built into Microsoft 365 and helps you secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="ba2e4-124">デバイスのセキュリティ ポリシーを作成および管理したり、リモートでデバイスをワイプしたり、詳細なデバイス レポートを参照できます。</span><span class="sxs-lookup"><span data-stu-id="ba2e4-124">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span>

<span data-ttu-id="ba2e4-125">基本的なモビリティとセキュリティを使用してデバイスを管理するには、 [ここ](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)から開始してください。</span><span class="sxs-lookup"><span data-stu-id="ba2e4-125">To manage devices using Basic Mobility and Security, start [here](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd).</span></span>
 
## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="ba2e4-126">ID とデバイスのアクセスに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="ba2e4-126">Identity and device access recommendations</span></span>

<span data-ttu-id="ba2e4-127">Microsoft では、セキュアで生産性の高い労働力を確保するために [ID とデバイスのアクセス](microsoft-365-policies-configurations.md)に関する一連の推奨事項を提供しています。</span><span class="sxs-lookup"><span data-stu-id="ba2e4-127">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="ba2e4-128">デバイスアクセスの場合は、次の記事の推奨事項と設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="ba2e4-128">For device access, use the recommendations and settings in these articles:</span></span>

- [<span data-ttu-id="ba2e4-129">前提条件</span><span class="sxs-lookup"><span data-stu-id="ba2e4-129">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="ba2e4-130">共通 ID とデバイスのアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="ba2e4-130">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a><span data-ttu-id="ba2e4-131">Contoso 社が Microsoft 365 のデバイス管理を行った方法</span><span class="sxs-lookup"><span data-stu-id="ba2e4-131">How Contoso did device management for Microsoft 365</span></span>

<span data-ttu-id="ba2e4-132">架空の典型的な多国籍企業が Microsoft 365 cloud services を使用してモバイルデバイス管理インフラストラクチャを展開する方法については、「 [mobile device management For Contoso](contoso-mdm.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba2e4-132">For information about how a fictional but representative multi-national business deployed their mobile device management infrastructure with Microsoft 365 cloud services, see [Mobile device management for Contoso](contoso-mdm.md).</span></span>
