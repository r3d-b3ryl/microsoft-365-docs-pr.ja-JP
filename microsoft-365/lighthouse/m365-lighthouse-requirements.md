---
title: ユーザーの要件Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Managed Service Providers (MSP) の場合は、サービス プロバイダーで使用する要件の一覧Microsoft 365 Lighthouse。
ms.openlocfilehash: 9c87744053ffe3bace90534287cd2b81697f3554
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395355"
---
# <a name="requirements-for-microsoft-365-lighthouse"></a><span data-ttu-id="79f36-103">ユーザーの要件Microsoft 365 Lighthouse</span><span class="sxs-lookup"><span data-stu-id="79f36-103">Requirements for Microsoft 365 Lighthouse</span></span>

> [!NOTE]
> <span data-ttu-id="79f36-104">この記事で説明する機能はプレビューで、変更される可能性があります。また、この記事に記載されている要件を満たすパートナーだけが利用できます。</span><span class="sxs-lookup"><span data-stu-id="79f36-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the requirements listed in this article.</span></span> <span data-ttu-id="79f36-105">組織にアカウントが設定されていない場合Microsoft 365 Lighthouse[を参照してください](m365-lighthouse-sign-up.md)Microsoft 365 Lighthouse。</span><span class="sxs-lookup"><span data-stu-id="79f36-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="79f36-106">Microsoft 365 Lighthouseは、Managed Service Providers (MSP) が中小企業 (SMB) のお客様に対して大規模なデバイス、データ、およびユーザーのセキュリティ保護と管理を行うのに役立つ管理ポータルです。</span><span class="sxs-lookup"><span data-stu-id="79f36-106">Microsoft 365 Lighthouse is an admin portal that helps Managed Service Providers (MSPs) secure and manage devices, data, and users at scale for small- and medium-sized business (SMB) customers.</span></span>  

<span data-ttu-id="79f36-107">MSP を使用するには、クラウド ソリューション プロバイダー (CSP) プログラムに間接リセラーまたは直接請求パートナーとして登録するMicrosoft 365 Lighthouse。</span><span class="sxs-lookup"><span data-stu-id="79f36-107">MSPs must be enrolled in the Cloud Solution Provider (CSP) program as an Indirect Reseller or Direct Bill partner to use Microsoft 365 Lighthouse.</span></span>  

<span data-ttu-id="79f36-108">さらに、各 MSP 顧客テナントは、次の要件を満Microsoft 365 Lighthouseの要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="79f36-108">In addition, each MSP customer tenant must qualify for Microsoft 365 Lighthouse by meeting the following requirements:</span></span> 
 
- <span data-ttu-id="79f36-109">MSP の委任された管理者特権 (DAP)</span><span class="sxs-lookup"><span data-stu-id="79f36-109">Delegated Admin Privileges (DAP) for the MSP</span></span> 
- <span data-ttu-id="79f36-110">少なくとも 1 つのMicrosoft 365 Business Premiumライセンス</span><span class="sxs-lookup"><span data-stu-id="79f36-110">At least one Microsoft 365 Business Premium license</span></span> 
- <span data-ttu-id="79f36-111">ライセンスユーザー数が 500 人未満</span><span class="sxs-lookup"><span data-stu-id="79f36-111">Fewer than 500 licensed users</span></span>  

## <a name="requirements-for-enablingdevice-management"></a><span data-ttu-id="79f36-112">デバイス管理を有効にする要件</span><span class="sxs-lookup"><span data-stu-id="79f36-112">Requirements for enabling device management</span></span>   

<span data-ttu-id="79f36-113">デバイス管理ページで顧客テナント デバイスを表示するには、MSP が次の条件を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79f36-113">To view customer tenant devices on the device management pages, a MSP must:</span></span>    

- <span data-ttu-id="79f36-114">すべてのお客様のデバイスを Microsoft エンドポイント マネージャー (MEM) に登録します。</span><span class="sxs-lookup"><span data-stu-id="79f36-114">Enroll all customer devices in Microsoft Endpoint Manager (MEM).</span></span><span data-ttu-id="79f36-115">詳細については、「デバイスをデバイスに[登録する」を参照Microsoft Intune。](/mem/intune/enrollment/)</span><span class="sxs-lookup"><span data-stu-id="79f36-115"> For more information, see [Enroll devices in Microsoft Intune](/mem/intune/enrollment/).</span></span>
- <span data-ttu-id="79f36-116">コンプライアンス ポリシーをすべての顧客デバイスに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="79f36-116">Assign compliance policies to all customer devices.</span></span><span data-ttu-id="79f36-117">詳細については、「コンプライアンス ポリシー[を作成する」を参照Microsoft Intune。](/mem/intune/protect/create-compliance-policy)</span><span class="sxs-lookup"><span data-stu-id="79f36-117"> For more information, see [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).</span></span> 

## <a name="requirements-for-enabling-usermanagement"></a><span data-ttu-id="79f36-118">ユーザー管理を有効にするための要件</span><span class="sxs-lookup"><span data-stu-id="79f36-118">Requirements for enabling user management</span></span> 

<span data-ttu-id="79f36-119">リスクの高いユーザー、多要素認証、パスワードのリセットなどのユーザー管理ページのレポートに顧客データを表示するには、顧客テナントが Azure Active Directory プレミアム P1 以降のライセンスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="79f36-119">For customer data to show up in reports on user management pages, including Risky users, Multifactor authentication, and Password reset, customer tenants must have licenses for Azure Active Directory Premium P1 or later.</span></span> <span data-ttu-id="79f36-120">Azure AD Premium P1は、Microsoft 365 Business Premium。</span><span class="sxs-lookup"><span data-stu-id="79f36-120">Azure AD Premium P1 is included with Microsoft 365 Business Premium.</span></span>   

## <a name="requirements-for-enablingthreat-management"></a><span data-ttu-id="79f36-121">脅威管理を有効にするための要件</span><span class="sxs-lookup"><span data-stu-id="79f36-121">Requirements for enabling threat management</span></span> 

<span data-ttu-id="79f36-122">脅威管理ページで顧客テナント デバイスと脅威を表示するには、すべての顧客テナント デバイスを Microsoft エンドポイント マネージャー (MEM) に登録し、Microsoft Defender ウイルス対策 を実行してそれらを保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79f36-122">To view customer tenant devices and threats on the threat management pages, you must enroll all customer tenant devices in Microsoft Endpoint Manager (MEM) and protect them by running Microsoft Defender Antivirus.</span></span>  

<span data-ttu-id="79f36-123">詳細については、「デバイスをデバイスに[登録する」を参照Microsoft Intune。](/mem/intune/enrollment/)</span><span class="sxs-lookup"><span data-stu-id="79f36-123">For more information, see [Enroll devices in Microsoft Intune](/mem/intune/enrollment/).</span></span>  

<span data-ttu-id="79f36-124">Microsoft Defender ウイルス対策オペレーティング システムの一部であり、Windowsを実行しているデバイスで既定で有効Windows 10。</span><span class="sxs-lookup"><span data-stu-id="79f36-124">Microsoft Defender Antivirus is part of the Windows operating system and is enabled by default on devices running Windows 10.</span></span>  

> [!NOTE] 
> <span data-ttu-id="79f36-125">Microsoft 以外のウイルス対策ソリューションを使用している場合は、Microsoft Defender ウイルス対策がMicrosoft Defender ウイルス対策無効になります。</span><span class="sxs-lookup"><span data-stu-id="79f36-125">If you're using a non-Microsoft antivirus solution and not Microsoft Defender Antivirus, Microsoft Defender Antivirus is disabled automatically.</span></span> <span data-ttu-id="79f36-126">Microsoft 以外のウイルス対策ソリューションをアンインストールすると、Microsoft Defender ウイルス対策デバイスを脅威から保護Windows自動的にアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="79f36-126">When you uninstall the non-Microsoft antivirus solution, Microsoft Defender Antivirus is activated automatically to protect your Windows devices from threats.</span></span>    

## <a name="related-content"></a><span data-ttu-id="79f36-127">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="79f36-127">Related content</span></span>   

<span data-ttu-id="79f36-128">[ポータル Microsoft 365 Lighthouseの構成](m365-lighthouse-configure-portal-security.md)(記事)</span><span class="sxs-lookup"><span data-stu-id="79f36-128">[Configure Microsoft 365 Lighthouse portal security](m365-lighthouse-configure-portal-security.md) (article)</span></span>\
<span data-ttu-id="79f36-129">[Microsoft 365 Lighthouse コンプライアンス ページの概要](m365-lighthouse-device-compliance-page-overview.md)(記事)</span><span class="sxs-lookup"><span data-stu-id="79f36-129">[Microsoft 365 Lighthouse Device compliance page overview](m365-lighthouse-device-compliance-page-overview.md) (article)</span></span>\
<span data-ttu-id="79f36-130">[Microsoft 365 Lighthouse ユーザー ページの概要](m365-lighthouse-users-page-overview.md)(記事)</span><span class="sxs-lookup"><span data-stu-id="79f36-130">[Microsoft 365 Lighthouse Users page overview](m365-lighthouse-users-page-overview.md) (article)</span></span>\
<span data-ttu-id="79f36-131">[Microsoft 365 Lighthouseの管理ページの概要](m365-lighthouse-threat-management-page-overview.md)(記事)</span><span class="sxs-lookup"><span data-stu-id="79f36-131">[Microsoft 365 Lighthouse Threat management page overview](m365-lighthouse-threat-management-page-overview.md) (article)</span></span>\
<span data-ttu-id="79f36-132">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml)  (記事)</span><span class="sxs-lookup"><span data-stu-id="79f36-132">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>

