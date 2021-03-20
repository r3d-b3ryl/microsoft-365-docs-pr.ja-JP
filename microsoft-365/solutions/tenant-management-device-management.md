---
title: 手順 5.  エンタープライズ テナント向け Microsoft 365 のデバイスとアプリの管理
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Microsoft 365 テナントのデバイスとアプリの管理に適切なオプションを展開します。
ms.openlocfilehash: 994ab7d21ae70307fa78e1f7249d39ac314a7358
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904614"
---
# <a name="step-5-device-and-app-management-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="88b3c-104">手順 5. </span><span class="sxs-lookup"><span data-stu-id="88b3c-104">Step 5.</span></span> <span data-ttu-id="88b3c-105">エンタープライズ テナント向け Microsoft 365 のデバイスとアプリの管理</span><span class="sxs-lookup"><span data-stu-id="88b3c-105">Device and app management for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="88b3c-106">Microsoft 365 for enterprise には、モバイル デバイス管理 (MDM) とモバイル アプリケーション管理 (MAM) を使用して、組織内のデバイスとそれらのデバイスでのアプリの使用を管理するのに役立つ機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="88b3c-106">Microsoft 365 for enterprise includes features to help manage devices and the use of apps on those devices within your organization with mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="88b3c-107">iOS、Android、macOS、Windows デバイスを管理して、データを含む組織のリソースへのアクセスを保護できます。</span><span class="sxs-lookup"><span data-stu-id="88b3c-107">You can manage iOS, Android, macOS, and Windows devices to protect access to your organization's resources, including your data.</span></span> <span data-ttu-id="88b3c-108">たとえば、組織外のユーザーに電子メールが送信されるのを防ぐか、組織のデータを作業者の個人デバイス上の個人データから分離できます。</span><span class="sxs-lookup"><span data-stu-id="88b3c-108">For example, you can prevent emails from being sent to people outside your organization or isolate organization data from personal data on your worker's personal devices.</span></span>

<span data-ttu-id="88b3c-109">ユーザー、デバイス、および Microsoft Teams のようなローカルおよびクラウドの生産性アプリの使用の検証と管理の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="88b3c-109">Here is an example of the validation and management of users, their devices, and their use of local and cloud productivity apps like Microsoft Teams.</span></span>

![ユーザー、デバイス、アプリの検証と管理](../media/tenant-management-overview/tenant-management-device-app-mgmt.png)

<span data-ttu-id="88b3c-111">組織のリソースをセキュリティで保護するために、Microsoft 365 for enterprise には、デバイスとアプリへのアクセスを管理するための機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="88b3c-111">To help you secure and protect your organization's resources, Microsoft 365 for enterprise includes features to help manage devices and their access to apps.</span></span> <span data-ttu-id="88b3c-112">デバイス管理には、次の 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="88b3c-112">There are two options for device management:</span></span>

- <span data-ttu-id="88b3c-113">Microsoft Intune は、企業向け包括的なデバイスおよびアプリ管理ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="88b3c-113">Microsoft Intune, which is a comprehensive device and app management solution for enterprises.</span></span>
- <span data-ttu-id="88b3c-114">基本的なモビリティとセキュリティは、組織内のデバイスを管理するためのすべての Microsoft 365 製品に含まれる Intune サービスのサブセットです。</span><span class="sxs-lookup"><span data-stu-id="88b3c-114">Basic Mobility and Security, which is a subset of Intune services included with all Microsoft 365 products for managing devices in your organization.</span></span> <span data-ttu-id="88b3c-115">詳細については、「基本モビリティと [セキュリティの機能」を参照してください](../admin/basic-mobility-security/capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="88b3c-115">For more information, see [Capabilities of Basic Mobility and Security](../admin/basic-mobility-security/capabilities.md).</span></span>

<span data-ttu-id="88b3c-116">Microsoft 365 E3 または E5 を使用している場合は、Intune を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88b3c-116">If you have Microsoft 365 E3 or E5, you should use Intune.</span></span>

## <a name="microsoft-intune"></a><span data-ttu-id="88b3c-117">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="88b3c-117">Microsoft Intune</span></span>

<span data-ttu-id="88b3c-118">Microsoft [Intune を使用して、MDM](/mem/intune/fundamentals/planning-guide) または MAM を使用して組織へのアクセスを管理します。</span><span class="sxs-lookup"><span data-stu-id="88b3c-118">You use [Microsoft Intune](/mem/intune/fundamentals/planning-guide) to manage access to your organization using MDM or MAM.</span></span> <span data-ttu-id="88b3c-119">MDM とは、ユーザーが Intune でデバイスを "登録" する場合です。</span><span class="sxs-lookup"><span data-stu-id="88b3c-119">MDM is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="88b3c-120">デバイスが登録された後、デバイスは管理対象デバイスであり、組織のポリシー、ルール、および設定を受け取る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="88b3c-120">After a device is enrolled, it is a managed device and can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="88b3c-121">たとえば、特定のアプリのインストール、パスワード ポリシーの作成、VPN 接続のインストールなどです。</span><span class="sxs-lookup"><span data-stu-id="88b3c-121">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="88b3c-122">自分の個人用デバイスを持つユーザーは、自分のデバイスを登録したり、Intune と組織のポリシーで管理したりしたくない場合があります。</span><span class="sxs-lookup"><span data-stu-id="88b3c-122">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="88b3c-123">ただし、組織のリソースとデータを保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88b3c-123">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="88b3c-124">このシナリオでは、MAM を使用してアプリを保護できます。</span><span class="sxs-lookup"><span data-stu-id="88b3c-124">In this scenario, you can protect your apps using MAM.</span></span> <span data-ttu-id="88b3c-125">たとえば、ユーザーがデバイス上の SharePoint にアクセスするときに PIN を入力する必要がある MAM ポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="88b3c-125">For example, you can use an MAM policy that requires a user to enter a PIN when accessing SharePoint on the device.</span></span>

<span data-ttu-id="88b3c-126">また、個人用デバイスと組織が所有するデバイスを管理する方法も決定します。</span><span class="sxs-lookup"><span data-stu-id="88b3c-126">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="88b3c-127">デバイスの使い方に応じて、デバイスの扱い方を変えてほしい場合があります。</span><span class="sxs-lookup"><span data-stu-id="88b3c-127">You might want to treat devices differently, depending on their uses.</span></span>

## <a name="identity-and-device-access-configurations"></a><span data-ttu-id="88b3c-128">ID とデバイスのアクセス構成</span><span class="sxs-lookup"><span data-stu-id="88b3c-128">Identity and device access configurations</span></span>

<span data-ttu-id="88b3c-129">Microsoft は、安全で生産性の高い従業員を確保するために [、ID](../security/office-365-security/microsoft-365-policies-configurations.md) とデバイス アクセスのための一連の構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="88b3c-129">Microsoft provides a set of configurations for [identity and device access](../security/office-365-security/microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="88b3c-130">これらの構成には、次の使用が含まれます。</span><span class="sxs-lookup"><span data-stu-id="88b3c-130">These configurations include the use of:</span></span>

- <span data-ttu-id="88b3c-131">Azure AD 条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="88b3c-131">Azure AD Conditional Access policies</span></span>
- <span data-ttu-id="88b3c-132">Microsoft Intune デバイスのコンプライアンスとアプリ保護ポリシー</span><span class="sxs-lookup"><span data-stu-id="88b3c-132">Microsoft Intune device compliance and app protection policies</span></span>
- <span data-ttu-id="88b3c-133">Azure AD Id Protection ユーザー リスク ポリシー</span><span class="sxs-lookup"><span data-stu-id="88b3c-133">Azure AD Identity Protection user risk policies</span></span>
- <span data-ttu-id="88b3c-134">クラウド アプリの追加ポリシー</span><span class="sxs-lookup"><span data-stu-id="88b3c-134">Additional policies of cloud apps</span></span>

<span data-ttu-id="88b3c-135">ユーザー、デバイス、Microsoft Teams のようなローカルおよびクラウドの生産性アプリの使用を検証および制限するこれらの設定とポリシーのアプリケーションの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="88b3c-135">Here is an example of the application of these settings and policies to validate and restrict users, their devices, and their use of local and cloud productivity apps like Microsoft Teams.</span></span>

![ユーザー、デバイス、およびアプリの使用に関する要件と制限に関する ID とデバイス アクセスの構成](../media/tenant-management-overview/tenant-management-device-app-mgmt-golden-config.png)

<span data-ttu-id="88b3c-137">デバイス アクセスとアプリ管理の場合は、次の記事の構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="88b3c-137">For device access and app management, use the configurations in these articles:</span></span>

- [<span data-ttu-id="88b3c-138">前提条件</span><span class="sxs-lookup"><span data-stu-id="88b3c-138">Prerequisites</span></span>](../security/office-365-security/identity-access-prerequisites.md)
- [<span data-ttu-id="88b3c-139">共通 ID とデバイスのアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="88b3c-139">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)

## <a name="results-of-step-5"></a><span data-ttu-id="88b3c-140">手順 5 の結果</span><span class="sxs-lookup"><span data-stu-id="88b3c-140">Results of Step 5</span></span>

<span data-ttu-id="88b3c-141">Microsoft 365 テナントのデバイスとアプリの管理では、Intune の設定とポリシーを決定して、ユーザー、デバイス、ローカルおよびクラウドの生産性アプリの使用を検証および制限します。</span><span class="sxs-lookup"><span data-stu-id="88b3c-141">For device and app management for your Microsoft 365 tenant, you have determined the Intune settings and policies to validate and restrict users, their devices, and their use of local and cloud productivity apps.</span></span>

<span data-ttu-id="88b3c-142">新しい要素が強調表示された Intune デバイスとアプリ管理を備えたテナントの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="88b3c-142">Here is an example of a tenant with Intune device and app management with the new elements highlighted.</span></span>

![Intune デバイスとアプリ管理を使用するテナントの例](../media/tenant-management-overview/tenant-management-tenant-build-step5.png)

<span data-ttu-id="88b3c-144">この図では、テナントには次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="88b3c-144">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="88b3c-145">Intune に登録されている組織所有のデバイス。</span><span class="sxs-lookup"><span data-stu-id="88b3c-145">Organization-owned devices enrolled in Intune.</span></span>
- <span data-ttu-id="88b3c-146">登録されたデバイスと個人用デバイスの Intune デバイスポリシーとアプリ ポリシー。</span><span class="sxs-lookup"><span data-stu-id="88b3c-146">Intune device and app policies for enrolled and personal devices.</span></span>

## <a name="ongoing-maintenance-for-device-and-app-management"></a><span data-ttu-id="88b3c-147">デバイスとアプリ管理の継続的なメンテナンス</span><span class="sxs-lookup"><span data-stu-id="88b3c-147">Ongoing maintenance for device and app management</span></span>

<span data-ttu-id="88b3c-148">継続的に、次の必要が生じ得る場合があります。</span><span class="sxs-lookup"><span data-stu-id="88b3c-148">On an ongoing basis, you might need to:</span></span> 

- <span data-ttu-id="88b3c-149">デバイスの登録を管理します。</span><span class="sxs-lookup"><span data-stu-id="88b3c-149">Manage device enrollment.</span></span>
- <span data-ttu-id="88b3c-150">追加のアプリ、デバイス、セキュリティ要件の設定とポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="88b3c-150">Revise your settings and policies for additional apps, devices, and security requirements.</span></span>