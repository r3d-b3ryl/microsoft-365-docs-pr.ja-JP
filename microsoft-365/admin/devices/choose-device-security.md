---
title: さまざまなデバイスとアプリのデータ保護方法を比較する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 異なる MDM メソッドと MAM メソッドの間で選択します。
ms.openlocfilehash: c4928f272c0bdd8a7b6883f506cebf9a153e9c49
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910536"
---
# <a name="options-for-protecting-your-devices-and-app-data"></a><span data-ttu-id="4bc2b-103">デバイスとアプリ データを保護するためのオプション</span><span class="sxs-lookup"><span data-stu-id="4bc2b-103">Options for protecting your devices and app data</span></span>

<span data-ttu-id="4bc2b-104">組織のデバイスとデータを Microsoft 365 for business および enterprise で保護するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="4bc2b-104">You have several ways to secure your organizations devices and data on them with Microsoft 365 for business and enterprise.</span></span> <span data-ttu-id="4bc2b-105">次のスタンドアロン プランを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4bc2b-105">You can use the following stand-alone plans:</span></span>

- <span data-ttu-id="4bc2b-106">Intune (Microsoft エンドポイント管理の一部)</span><span class="sxs-lookup"><span data-stu-id="4bc2b-106">Intune (a part of Microsoft Endpoint Management)</span></span>
- <span data-ttu-id="4bc2b-107">Azure Active Directory Premium プラン。</span><span class="sxs-lookup"><span data-stu-id="4bc2b-107">Azure Active Directory Premium plans.</span></span>
- <span data-ttu-id="4bc2b-108">Basic Mobility and Security (ほとんどの Microsoft 365 for business and enterprise プランに含まれる) または以前のスタンドアロン プランの一部またはすべてを含むサブスクリプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="4bc2b-108">Basic Mobility and Security (included in most Microsoft 365 for business and enterprise plans) Or use the subscriptions that include some, or all of the previous standalone plans.</span></span>

- <span data-ttu-id="4bc2b-109">Microsoft 365 Business Premium サブスクリプション。これには、300 ユーザー以下の小規模ビジネス向けセキュリティと脅威保護が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4bc2b-109">A Microsoft 365 Business Premium subscription, which includes security and threat protection for small business under 300 users.</span></span>
- <span data-ttu-id="4bc2b-110">高度なセキュリティと脅威保護を含む Microsoft 365 Enterprise プラン。</span><span class="sxs-lookup"><span data-stu-id="4bc2b-110">Microsoft 365 Enterprise plans that include advanced security and threat protection.</span></span>

## <a name="device-management-options"></a><span data-ttu-id="4bc2b-111">デバイス管理オプション</span><span class="sxs-lookup"><span data-stu-id="4bc2b-111">Device management options</span></span>

- <span data-ttu-id="4bc2b-112">**基本的なモビリティとセキュリティ** は、ほとんどの Microsoft 365 プランで提供され、Microsoft 365 Business Standard および Microsoft 365 Business Basic に提供される唯一の組み込みの選択肢です。</span><span class="sxs-lookup"><span data-stu-id="4bc2b-112">**Basic Mobility and Security** is offered with most Microsoft 365 plans, and is the only built-in choice offered for Microsoft 365 Business Standard and Microsoft 365 Business Basic.</span></span> <span data-ttu-id="4bc2b-113">詳細については、「Basic [Mobility and Security の可用性」を参照してください](../basic-mobility-security/choose-between-basic-mobility-and-security-and-intune.md#availability-of-basic-mobility-and-security-and-intune)。</span><span class="sxs-lookup"><span data-stu-id="4bc2b-113">For more information, see [availability of Basic Mobility and Security](../basic-mobility-security/choose-between-basic-mobility-and-security-and-intune.md#availability-of-basic-mobility-and-security-and-intune).</span></span> 

    <span data-ttu-id="4bc2b-114">Microsoft 365 Business Basic または Microsoft 365 Business Standard のいずれかを使用している場合は、組織のセキュリティニーズが複雑な場合に Intune を購入することもできます。</span><span class="sxs-lookup"><span data-stu-id="4bc2b-114">If you have either Microsoft 365 Business Basic or Microsoft 365 Business Standard, you can also purchase Intune if your organization has more complex security needs.</span></span>
 
- <span data-ttu-id="4bc2b-115">**Microsoft Intune** は、一部の Microsoft 365 for business プランまたは Enterprise プランにも含まれるスタンドアロン プランです。</span><span class="sxs-lookup"><span data-stu-id="4bc2b-115">**Microsoft Intune** is a stand-alone plan that is also included with some Microsoft 365 for business or enterprise plans.</span></span> <span data-ttu-id="4bc2b-116">Intune をスタンドアロンまたはサブスクリプションの一部として使用している場合は、デバイスとアプリ データ管理を微調整できます。</span><span class="sxs-lookup"><span data-stu-id="4bc2b-116">If you have Intune either as a stand-alone or a part of your subscription, it provides ability to fine-tune your device and app-data management.</span></span> <span data-ttu-id="4bc2b-117">Microsoft 365 での可用性の詳細については、「Intune の可用性 [」を参照してください](../basic-mobility-security/choose-between-basic-mobility-and-security-and-intune.md#availability-of-basic-mobility-and-security-and-intune)。</span><span class="sxs-lookup"><span data-stu-id="4bc2b-117">For more information on availability with Microsoft 365, see [availability of Intune](../basic-mobility-security/choose-between-basic-mobility-and-security-and-intune.md#availability-of-basic-mobility-and-security-and-intune).</span></span>

    <span data-ttu-id="4bc2b-118">Microsoft Intune は、モバイル デバイス管理 (MDM) およびモバイル アプリケーション管理 (MAM) に重点を置いた、クラウドベースのサービスです。</span><span class="sxs-lookup"><span data-stu-id="4bc2b-118">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="4bc2b-119">携帯電話、タブレット、ラップトップなど、組織のデバイスの使用方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="4bc2b-119">You control how your organization’s devices are used, including mobile phones, tablets, and laptops.</span></span> <span data-ttu-id="4bc2b-120">特定のポリシーを構成して、アプリケーションを制御できます。</span><span class="sxs-lookup"><span data-stu-id="4bc2b-120">You can also configure specific policies to control applications.</span></span> <span data-ttu-id="4bc2b-121">詳細については [、「Microsoft Intune のドキュメント」を参照してください](/mem/intune/)。</span><span class="sxs-lookup"><span data-stu-id="4bc2b-121">For more information, see [Microsoft Intune documentation](/mem/intune/).</span></span>

- <span data-ttu-id="4bc2b-122">**Azure Active Directory (AD) Premium** プランはスタンドアロン プランであり、一部の Microsoft 365 for business および enterprise プランにも含まれます。</span><span class="sxs-lookup"><span data-stu-id="4bc2b-122">**Azure Active Directory (AD) Premium** plans are standalone plans that also come with some of the Microsoft 365 for business and enterprise plans.</span></span> <span data-ttu-id="4bc2b-123">詳細については、「Azure AD価格 [」を参照してください](https://azure.microsoft.com/pricing/details/active-directory/)。</span><span class="sxs-lookup"><span data-stu-id="4bc2b-123">For more information, see [Azure AD pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

     <span data-ttu-id="4bc2b-124">Azure AD Premium P1 と Azure AD プレミアム P2 を使用すると、条件付きアクセス機能、セルフサービス パスワードのリセットなどを設定できます。Premium プランの機能の詳細については、「Azure の価格設定 [」AD参照](https://azure.microsoft.com/pricing/details/active-directory/) してください。</span><span class="sxs-lookup"><span data-stu-id="4bc2b-124">Azure AD Premium P1 and Azure AD Premium P2 allow you to set conditional access features, self-service password reset, etc. For more information on the capabilities of the Premium plans, see [Azure AD pricing](https://azure.microsoft.com/pricing/details/active-directory/) page.</span></span>
- <span data-ttu-id="4bc2b-125">**Microsoft 365 Business Premium には** 、Intune と Azure Active Directory Premium P1 と 365 Advanced Threat Protection Officeが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4bc2b-125">**Microsoft 365 Business Premium** includes Intune and Azure Active Directory Premium P1 and Office 365 Advanced Threat Protection.</span></span> 
 
    <span data-ttu-id="4bc2b-126">Microsoft 365 Business Premium には、デバイスとアプリ データをセキュリティ保護するための一連のポリシー テンプレートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="4bc2b-126">Microsoft 365 Business Premium offers a set of policy templates for securing your devices and app data.</span></span> <span data-ttu-id="4bc2b-127">これは、300 ユーザー以下のほとんどの企業に対して、優れたレベルのセキュリティと脅威の保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="4bc2b-127">It offers a good level of security and threat protection for most businesses under 300 users.</span></span> <span data-ttu-id="4bc2b-128">詳細については、「セットアップ ウィザードでの [Microsoft 365 Business Premium](../../business/set-up.md)のセットアップ [、Windows 10](../../business/secure-win-10-pcs.md)コンピューターのセキュリティ保護 [、Microsoft 365 Business Premium](../../business/security-features.md)のセキュリティとコンプライアンス機能」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bc2b-128">For more information, see [set up Microsoft 365 Business Premium in the setup wizard](../../business/set-up.md), [secure Windows 10 computers](../../business/secure-win-10-pcs.md),  and [Microsoft 365 Business Premium security and compliance features](../../business/security-features.md).</span></span>

- <span data-ttu-id="4bc2b-129">**Microsoft 365 for enterprise** サブスクリプションには Microsoft Intune が含まれます。また、E5 には Azure ADプレミアム プラン 1 と 2 も含まれています。</span><span class="sxs-lookup"><span data-stu-id="4bc2b-129">**Microsoft 365 for enterprise** subscriptions include Microsoft Intune and E5 also includes the Azure AD premium plans 1 and 2.</span></span>

    <span data-ttu-id="4bc2b-130">Microsoft 365 E5 は、すべての Microsoft 365 サブスクリプションの最高レベルのセキュリティと脅威保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="4bc2b-130">Microsoft 365 E5 offers the highest level of security and threat protection of all the Microsoft 365 subscriptions.</span></span> <span data-ttu-id="4bc2b-131">詳細については [、「Microsoft 365 for enterprise overview」を参照してください](../../enterprise/microsoft-365-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="4bc2b-131">For more information, see [Microsoft 365 for enterprise overview](../../enterprise/microsoft-365-overview.md).</span></span>