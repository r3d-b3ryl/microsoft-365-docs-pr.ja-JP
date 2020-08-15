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
ms.openlocfilehash: 1c5a06c75ede11697e2ecf17c47eb035e78dcd27
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691852"
---
# <a name="device-management-roadmap-for-microsoft-365"></a><span data-ttu-id="0121a-104">Microsoft 365 のデバイス管理のロードマップ</span><span class="sxs-lookup"><span data-stu-id="0121a-104">Device management roadmap for Microsoft 365</span></span>


<span data-ttu-id="0121a-105">Microsoft 365 for enterprise では、組織内のデバイスとアプリを管理するのに役立つ機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="0121a-105">Microsoft 365 for enterprise includes features to help manage devices, and their apps, within your organization.</span></span> <span data-ttu-id="0121a-106">モバイルデバイスを管理することにより、組織のリソースを保護し、保護することができます。</span><span class="sxs-lookup"><span data-stu-id="0121a-106">Managing mobile devices helps you secure and protect your organization's resources.</span></span>

<span data-ttu-id="0121a-107">デバイスの管理には2つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="0121a-107">There are two options for device management.</span></span>

## <a name="microsoft-intune"></a><span data-ttu-id="0121a-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="0121a-108">Microsoft Intune</span></span>

<span data-ttu-id="0121a-109">Intune は、モバイルデバイス管理 (MDM) またはモバイルアプリケーション管理 (MAM) を使用して、組織へのアクセスを管理するためのオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="0121a-109">Intune gives you options to manage access to your organization using Mobile Device Management (MDM) or Mobile Application Management (MAM).</span></span> <span data-ttu-id="0121a-110">MDM は、ユーザーが Intune にデバイスを登録するときに行います。</span><span class="sxs-lookup"><span data-stu-id="0121a-110">MDM is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="0121a-111">登録されると、管理対象デバイスであり、組織で使用されているすべてのポリシー、ルール、および設定を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="0121a-111">Once enrolled, they are managed devices, and can receive any policies, rules, and settings used by your organization.</span></span> <span data-ttu-id="0121a-112">たとえば、具体的なアプリをインストールしたり、パスワードポリシーを作成したり、VPN 接続をインストールしたりできます。</span><span class="sxs-lookup"><span data-stu-id="0121a-112">For example, you can install specifics apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="0121a-113">独自の個人用デバイスを使用しているユーザーは、デバイスの登録や、Intune およびポリシーによる管理を行わないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="0121a-113">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your policies.</span></span> <span data-ttu-id="0121a-114">ただし、組織のリソースとデータを保護する必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="0121a-114">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="0121a-115">このシナリオでは、MAM を使用してアプリを保護することができます。</span><span class="sxs-lookup"><span data-stu-id="0121a-115">In this scenario, you can protect your apps using MAM.</span></span> <span data-ttu-id="0121a-116">たとえば、ユーザーがデバイス上の SharePoint にアクセスするときに PIN を入力する必要がある MAM ポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0121a-116">For example, you can use a MAM policy that requires a user to enter a PIN when accessing SharePoint on the device.</span></span>

<span data-ttu-id="0121a-117">また、個人または組織所有のデバイスを管理する方法も決定します。</span><span class="sxs-lookup"><span data-stu-id="0121a-117">You'll also determine how you're going to manage personal or organization-owned devices.</span></span> <span data-ttu-id="0121a-118">使用方法に応じて、デバイスを異なる方法で扱うことができます。</span><span class="sxs-lookup"><span data-stu-id="0121a-118">You may want to treat devices differently, depending on their use.</span></span> 

<span data-ttu-id="0121a-119">[ここ](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide)から開始してください。</span><span class="sxs-lookup"><span data-stu-id="0121a-119">Start [here](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide).</span></span>

## <a name="basic-mobility-and-security"></a><span data-ttu-id="0121a-120">基本的なモビリティとセキュリティ</span><span class="sxs-lookup"><span data-stu-id="0121a-120">Basic Mobility and Security</span></span>
 
<span data-ttu-id="0121a-121">これは Microsoft 365 に組み込まれており、iPhones、Ipad、Androids、Windows phone などのユーザーのモバイルデバイスをセキュリティで保護し、管理することができます。</span><span class="sxs-lookup"><span data-stu-id="0121a-121">This is built into Microsoft 365 and helps you secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="0121a-122">デバイスのセキュリティ ポリシーを作成および管理したり、リモートでデバイスをワイプしたり、詳細なデバイス レポートを参照できます。</span><span class="sxs-lookup"><span data-stu-id="0121a-122">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span> 

<span data-ttu-id="0121a-123">[ここ](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)から開始してください。</span><span class="sxs-lookup"><span data-stu-id="0121a-123">Start [here](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd).</span></span>
 
## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="0121a-124">ID とデバイスのアクセスに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="0121a-124">Identity and device access recommendations</span></span>

<span data-ttu-id="0121a-125">Microsoft では、セキュアで生産性の高い労働力を確保するために [ID とデバイスのアクセス](microsoft-365-policies-configurations.md)に関する一連の推奨事項を提供しています。</span><span class="sxs-lookup"><span data-stu-id="0121a-125">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="0121a-126">デバイスアクセスの場合は、このフェーズの手順と共に次の記事の推奨事項と設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="0121a-126">For device access, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="0121a-127">前提条件</span><span class="sxs-lookup"><span data-stu-id="0121a-127">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="0121a-128">共通 ID とデバイスのアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="0121a-128">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-device-management-for-microsoft-365"></a><span data-ttu-id="0121a-129">Microsoft でのデバイス管理の方法 (Microsoft 365)</span><span class="sxs-lookup"><span data-stu-id="0121a-129">How Microsoft does device management for Microsoft 365</span></span>

<span data-ttu-id="0121a-130">Microsoft の IT 専門家 [が EMS を使用してデバイスを管理](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR8)する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0121a-130">Learn how IT experts at Microsoft [manage devices with EMS](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR8).</span></span>

## <a name="how-contoso-did-device-management-for-microsoft-365"></a><span data-ttu-id="0121a-131">Contoso 社が Microsoft 365 のデバイス管理を行った方法</span><span class="sxs-lookup"><span data-stu-id="0121a-131">How Contoso did device management for Microsoft 365</span></span>

<span data-ttu-id="0121a-132">架空の多国籍企業である Contoso Corporation が、Microsoft 365 cloud services を使用して [モバイルデバイス管理インフラストラクチャを展開](contoso-mdm.md) した方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0121a-132">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed their mobile device management infrastructure](contoso-mdm.md) with Microsoft 365 cloud services.</span></span>

![Contoso 社](../media/contoso-overview/contoso-icon.png)
