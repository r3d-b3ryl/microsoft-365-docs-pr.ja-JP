---
title: ユーザーとデバイス アクセスの保護
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/17/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: Microsoft 365 データとサービスへのユーザーとデバイスのアクセスを保護し、データ損失から保護する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9ff7bd2ff8b4b333eb30a6cc82797a8968941e0b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051699"
---
# <a name="protect-user-and-device-access"></a><span data-ttu-id="addd4-103">ユーザーとデバイス アクセスの保護</span><span class="sxs-lookup"><span data-stu-id="addd4-103">Protect user and device access</span></span>

<span data-ttu-id="addd4-104">Microsoft 365 のデータとサービスへのアクセスを保護することは、サイバー攻撃から防御し、データ損失から保護するために重要です。</span><span class="sxs-lookup"><span data-stu-id="addd4-104">Protecting access to your Microsoft 365 data and services is crucial to defending against cyberattacks and guarding against data loss.</span></span> <span data-ttu-id="addd4-105">同じ保護は、環境内の他の SaaS アプリケーション、および Azure Active Directory アプリケーション プロキシで公開されたオンプレミス アプリケーションにも適用できます。</span><span class="sxs-lookup"><span data-stu-id="addd4-105">The same protections can be applied to other SaaS applications in your environment and even to on-premises applications published with Azure Active Directory Application Proxy.</span></span>
  
## <a name="step-1-review-recommendations"></a><span data-ttu-id="addd4-106">手順 1: 推奨事項を確認する</span><span class="sxs-lookup"><span data-stu-id="addd4-106">Step 1: Review recommendations</span></span>

<span data-ttu-id="addd4-107">Office 365、他の SaaS サービス、および Azure AD アプリケーション プロキシで公開したオンプレミス アプリケーションにアクセスする ID とデバイスを保護するために推奨される機能。</span><span class="sxs-lookup"><span data-stu-id="addd4-107">Recommended capabilities for protecting identities and devices that access Office 365, other SaaS services, and on-premises applications published with Azure AD Application Proxy.</span></span>
  
<span data-ttu-id="addd4-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [その他の言語](https://www.microsoft.com/download/details.aspx?id=55032)</span><span class="sxs-lookup"><span data-stu-id="addd4-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [More languages](https://www.microsoft.com/download/details.aspx?id=55032)</span></span>
  
## <a name="step-2-protect-administrator-accounts-and-access"></a><span data-ttu-id="addd4-109">手順 2: 管理者アカウントとアクセスを保護する</span><span class="sxs-lookup"><span data-stu-id="addd4-109">Step 2: Protect administrator accounts and access</span></span>
<span data-ttu-id="addd4-110">Microsoft 365 環境の管理に使用する管理アカウントには、管理者特権が含まれます。</span><span class="sxs-lookup"><span data-stu-id="addd4-110">The administrative accounts you use to administer your Microsoft 365 environment include elevated privileges.</span></span> <span data-ttu-id="addd4-111">これらは、ハッカーやサイバー攻撃者にとって貴重なターゲットです。</span><span class="sxs-lookup"><span data-stu-id="addd4-111">These are valuable targets for hackers and cyberattackers.</span></span> 

<span data-ttu-id="addd4-112">まず、管理用に管理者アカウントのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="addd4-112">Begin by using administrator accounts only for administration.</span></span> <span data-ttu-id="addd4-113">管理者は、通常の非管理用に個別のユーザー アカウントを持ち、ジョブ機能に関連付けられたタスクを完了するために必要な場合にのみ管理アカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="addd4-113">Admins should have a separate user account for regular, non-administrative use and only use their administrative account when necessary to complete a task associated with their job function.</span></span>

<span data-ttu-id="addd4-114">多要素認証と条件付きアクセスで管理者アカウントを保護します。</span><span class="sxs-lookup"><span data-stu-id="addd4-114">Protect your administrator accounts with multi-factor authentication and conditional access.</span></span> <span data-ttu-id="addd4-115">詳細については、「管理者アカウントの [保護」を参照してください](../security/defender-365-security/identity-access-prerequisites.md#protecting-administrator-accounts)。</span><span class="sxs-lookup"><span data-stu-id="addd4-115">For more information, see [Protecting administrator accounts](../security/defender-365-security/identity-access-prerequisites.md#protecting-administrator-accounts).</span></span> 

<span data-ttu-id="addd4-116">次に、365 で特権アクセス管理Officeします。</span><span class="sxs-lookup"><span data-stu-id="addd4-116">Next, configure privileged access management in Office 365.</span></span> <span data-ttu-id="addd4-117">特権アクセスの管理では、Office 365 の特権的管理タスクを細かくアクセス制限できます。</span><span class="sxs-lookup"><span data-stu-id="addd4-117">Privileged access management allows granular access control over privileged admin tasks in Office 365.</span></span> <span data-ttu-id="addd4-118">これは、機密データへの永続的なアクセスまたは重要な構成設定へのアクセスを持つ既存の特権管理者アカウントを使用する可能性のある侵害から組織を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="addd4-118">It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span>

- [<span data-ttu-id="addd4-119">特権アクセス管理の概要</span><span class="sxs-lookup"><span data-stu-id="addd4-119">Overview of privileged access management</span></span>](privileged-access-management-overview.md)
- [<span data-ttu-id="addd4-120">特権アクセス管理を構成する</span><span class="sxs-lookup"><span data-stu-id="addd4-120">Configure privileged access management</span></span>](privileged-access-management-configuration.md)

<span data-ttu-id="addd4-121">もう 1 つの推奨事項は、管理作業用に特別に構成されたワークステーションを使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="addd4-121">Another top recommendation is to use workstations specifically configured for administrative work.</span></span> <span data-ttu-id="addd4-122">これらは、管理タスクにのみ使用される専用デバイスです。</span><span class="sxs-lookup"><span data-stu-id="addd4-122">These are dedicated devices that are only used for administrative tasks.</span></span> <span data-ttu-id="addd4-123">「 [特権アクセスのセキュリティ保護」を参照してください](/windows-server/identity/securing-privileged-access/securing-privileged-access)。</span><span class="sxs-lookup"><span data-stu-id="addd4-123">See [Securing privileged access](/windows-server/identity/securing-privileged-access/securing-privileged-access).</span></span>

<span data-ttu-id="addd4-124">最後に、テナントに 2 つ以上の緊急アクセス アカウントを作成することで、管理アクセスの不注意による影響を軽減できます。</span><span class="sxs-lookup"><span data-stu-id="addd4-124">Finally, you can mitigate the impact of inadvertent lack of administrative access by creating two or more emergency access accounts in your tenant.</span></span> <span data-ttu-id="addd4-125">「Azure AD で緊急 [アクセス アカウントを管理する」を参照してください](/azure/active-directory/users-groups-roles/directory-emergency-access)。</span><span class="sxs-lookup"><span data-stu-id="addd4-125">See [Manage emergency access accounts in Azure AD](/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span> 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a><span data-ttu-id="addd4-126">手順 3: 推奨される ID とデバイス アクセス ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="addd4-126">Step 3: Configure recommended identity and device access policies</span></span>
<span data-ttu-id="addd4-127">多要素認証 (MFA) と条件付きアクセス ポリシーは、侵害されたアカウントや不正アクセスを軽減するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="addd4-127">Multi-factor authentication (MFA) and conditional access policies are powerful tools for mitigating against compromised accounts and unauthorized access.</span></span> <span data-ttu-id="addd4-128">一緒にテストされた一連のポリシーを実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="addd4-128">We recommend implementing a set of policies that have been tested together.</span></span> <span data-ttu-id="addd4-129">展開手順を含む詳細については、「Identity and [device access configurations」を参照してください](../security/defender-365-security/microsoft-365-policies-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="addd4-129">For more information, including deployment steps, see [Identity and device access configurations](../security/defender-365-security/microsoft-365-policies-configurations.md).</span></span>

 <span data-ttu-id="addd4-130">これらのポリシーは、次の機能を実装します。</span><span class="sxs-lookup"><span data-stu-id="addd4-130">These policies implement the following capabilities:</span></span>
- <span data-ttu-id="addd4-131">Mult-factor 認証</span><span class="sxs-lookup"><span data-stu-id="addd4-131">Mult-factor authentication</span></span>
- <span data-ttu-id="addd4-132">条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="addd4-132">Conditional access</span></span>
- <span data-ttu-id="addd4-133">Intune アプリ保護 (デバイスのアプリとデータ保護)</span><span class="sxs-lookup"><span data-stu-id="addd4-133">Intune app protection (app and data protection for devices)</span></span>
- <span data-ttu-id="addd4-134">Intune デバイス コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="addd4-134">Intune device compliance</span></span>
- <span data-ttu-id="addd4-135">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="addd4-135">Azure AD Identity Protection</span></span>

<span data-ttu-id="addd4-136">Intune デバイスのコンプライアンスを実装するには、デバイスの登録が必要です。</span><span class="sxs-lookup"><span data-stu-id="addd4-136">Implementing Intune device compliance requires device enrollment.</span></span> <span data-ttu-id="addd4-137">デバイスを管理すると、環境内のリソースへのアクセスを許可する前に、デバイスが正常で準拠することを確認できます。</span><span class="sxs-lookup"><span data-stu-id="addd4-137">Managing devices allows you to ensure that they are healthy and compliant before allowing them access to resources in your environment.</span></span> <span data-ttu-id="addd4-138">[「Intune での管理用デバイスの登録」を参照してください。](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="addd4-138">See [Enroll devices for management in Intune](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span></span>

## <a name="step-4-configure-sharepoint-device-access-policies"></a><span data-ttu-id="addd4-139">手順 4: SharePoint デバイス アクセス ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="addd4-139">Step 4: Configure SharePoint device access policies</span></span>

<span data-ttu-id="addd4-140">Microsoft では、デバイス アクセス制御を使用して、機密性の高い規制の高いコンテンツを使用して SharePoint サイト内のコンテンツを保護することを推奨します。</span><span class="sxs-lookup"><span data-stu-id="addd4-140">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="addd4-141">詳細については [、「SharePoint サイトとファイルのセキュリティ保護に関するポリシーの推奨事項」を参照してください](../security/defender-365-security/sharepoint-file-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="addd4-141">For more information, see [Policy recommendations for securing SharePoint sites and files](../security/defender-365-security/sharepoint-file-access-policies.md).</span></span>



