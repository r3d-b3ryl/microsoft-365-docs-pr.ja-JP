---
title: ロシアの個人データローカライズ要件
description: 個人データ、ロシア市民の個人データ記録、systematization、蓄積、保存、明確化、および抽出が、ロシアにある Microsoft サービスおよびデータベースで実行される方法について説明します。
keywords: Microsoft 365、コンプライアンス、サービス
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: 70e36d4f11f7fc1a5870f41a32351cf7078bdc68
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "44065772"
---
# <a name="russian-personal-data-localization-requirements"></a><span data-ttu-id="03553-104">ロシアの個人データローカライズ要件</span><span class="sxs-lookup"><span data-stu-id="03553-104">Russian Personal Data Localization Requirements</span></span>

<span data-ttu-id="03553-105">2015年9月1日時点では、個人データオペレーターと見なされ、個人データを収集するときには、ロシア市民の個人データの記録、systematization、蓄積、ストレージ、説明 (更新、変更)、および抽出がロシアにあるデータベース (「個人データのローカリゼーション要件」) によって実行されます。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="03553-105">As of September 1, 2015, organizations, that are considered personal data operators, must ensure when collecting personal data, that Russian citizens’ personal data recording, systematization, accumulation, storage, clarification (updating, changing) and extraction are performed through the databases located in Russia ('personal data localization requirement').<sup>1</sup></span></span>

<span data-ttu-id="03553-106">Microsoft Online Services (教育機関に限定されているが、教育機関に限定されるものではありません) (hereinafter とも呼ばれます)。個人データ処理 (Microsoft Azure、Microsoft 365、Dynamics 365、電源プラットフォームなど) が、ロシア外のデータ処理センターから提供されます (詳細については、「 [Microsoft Trust Center」](https://www.microsoft.com/trust-center)を参照</span><span class="sxs-lookup"><span data-stu-id="03553-106">Microsoft Online Services, available to the organizations (including but not limited to educational institutions) (hereinafter referred to as 'customer'), including those enabling personal data processing, – such as Microsoft Azure, Microsoft 365, Dynamics 365, and Power Platform – are provided from data processing centers, located outside of Russia (for more information visit the [Microsoft Trust Center](https://www.microsoft.com/trust-center)).</span></span>

<span data-ttu-id="03553-107">ユーザー情報システムによって処理された情報の種類と内容に基づいて、たとえば、Microsoft クラウド製品を使用しているものも含め、個人データ情報システム (' PDIS ', ' ISPD ') と見なされることがあります。</span><span class="sxs-lookup"><span data-stu-id="03553-107">Based on the type and content of information, processed by customer information systems, such systems, including those using Microsoft cloud products, may be deemed a personal data information system ('PDIS', 'ISPD').</span></span> <span data-ttu-id="03553-108">お客様が、Microsoft Online Services をシステムで使用することを希望している場合は、そのアーキテクチャおよび処理される情報の種類を通じて、そのお客様に対して、次に示す使用可能なソリューションを検討することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="03553-108">In cases where the customer would like to use Microsoft Online Services, in a system, that qualifies as PDIS through its architecture and types of information processed, Microsoft invites its customers to consider amongst other things available solutions, specified below.</span></span> <span data-ttu-id="03553-109">以下に示すすべてのシナリオは、標準のビジネスサービスに対する追加オプションとして、お客様に提供されています。</span><span class="sxs-lookup"><span data-stu-id="03553-109">All the scenarios provided below are available for customers as an additional option to standard business offerings.</span></span>

<span data-ttu-id="03553-110">このお客様には、pdis 個人データオペレーターが、コンプライアンスを担当しており、個人データのローカライズに関する適用可能な法的要件を分析して評価する必要があります。また、独自の判断で、PDIS の個人データの処理がロシアの個人データの法則に準拠していることを確認してください。<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="03553-110">It should be noted, that it is the customer, as personal data operator of PDIS, who is in charge of compliance and shall analyze and assess applicable legal requirements for personal data localization and, at its own discretion, independently determine sufficient measures to ensure, that personal data processing in PDIS complies with the Russian personal data law.<sup>2</sup></span></span>

## <a name="subscribing-to-microsoft-online-services"></a><span data-ttu-id="03553-111">Microsoft Online Services を購読する</span><span class="sxs-lookup"><span data-stu-id="03553-111">Subscribing to Microsoft Online Services</span></span>

### <a name="microsoft-id-management"></a><span data-ttu-id="03553-112">Microsoft ID の管理</span><span class="sxs-lookup"><span data-stu-id="03553-112">Microsoft ID Management</span></span>

<span data-ttu-id="03553-113">Microsoft は、microsoft のクラウドソリューションプロバイダー (CSP) パートナー経由で Microsoft Online Services-Microsoft Azure、microsoft 365、Dynamics 365、および電源プラットフォームへのサブスクライブを検討することをお客様に招待しています。</span><span class="sxs-lookup"><span data-stu-id="03553-113">Microsoft invites customers to consider subscribing to Microsoft Online Services – Microsoft Azure, Microsoft 365, Dynamics 365, and Power Platform – via a Microsoft Cloud Solution Provider (CSP) partner.</span></span> <span data-ttu-id="03553-114">詳細については、 [CSP パートナーの一覧](https://pinpoint.microsoft.com/search?type=services&campaign=691)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03553-114">See this [list of CSP partners](https://pinpoint.microsoft.com/search?type=services&campaign=691) for more information.</span></span>

### <a name="managing-user-identity-and-access-for-microsoft-online-services"></a><span data-ttu-id="03553-115">Microsoft Online Services のユーザー Id とアクセス権を管理する</span><span class="sxs-lookup"><span data-stu-id="03553-115">Managing User Identity and Access for Microsoft Online Services</span></span>

<span data-ttu-id="03553-116">Microsoft Azure などの Microsoft Online Services の場合、Microsoft 365、Dynamics 365、およびパワープラットフォームユーザーの確認とアクセス管理は、 [Azure Active Directory (AAD)](https://azure.microsoft.com/services/active-directory/)によって実行されます。</span><span class="sxs-lookup"><span data-stu-id="03553-116">For Microsoft Online Services such as Microsoft Azure, Microsoft 365, Dynamics 365 and Power Platform user verification and access management are performed through [Azure Active Directory (AAD)](https://azure.microsoft.com/services/active-directory/).</span></span> <span data-ttu-id="03553-117">Microsoft のお客様が Microsoft クラウドサービス (Windows Server Active Directory (AD) やその他の ID 管理システムなど) に対してローカルの id 管理システムを使用している場合、お客様は Azure AD Connect を通じてこのようなシステムを Azure Active Directory (AAD) にすばやく統合することができます。</span><span class="sxs-lookup"><span data-stu-id="03553-117">Note that cases where a Microsoft customer uses a local identification management system for Microsoft cloud services (such as the Windows Server Active Directory (AD) or any other ID management system), the customer has an opportunity to swiftly integrate such system with the Azure Active Directory (AAD) through Azure AD Connect.</span></span> <span data-ttu-id="03553-118">詳細については、「 [AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/cloud-provisioning/) 」オプションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="03553-118">See the [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/cloud-provisioning/) option for more information.</span></span> <span data-ttu-id="03553-119">また、Microsoft のお客様は、サードパーティベンダーのアプリケーションとソリューションを使用してユーザーを管理し、そのローカル識別システムを Azure AD と統合することを検討することもできます。</span><span class="sxs-lookup"><span data-stu-id="03553-119">Microsoft customers may also consider using applications and solutions of third-party vendors for managing their users and integrate their local identification system with the Azure AD.</span></span>

## <a name="questions-and-support"></a><span data-ttu-id="03553-120">質問とサポート</span><span class="sxs-lookup"><span data-stu-id="03553-120">Questions and support</span></span>

<span data-ttu-id="03553-121">技術的および請求に関する質問については、以下の Microsoft サポートリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="03553-121">For technical and billing questions, refer to the Microsoft Support resources below.</span></span> <span data-ttu-id="03553-122">詳細な質問や説明については、Microsoft の[プライバシーチーム](https://support.microsoft.com/gp/privacy-page)にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="03553-122">For additional questions or clarifications contact the Microsoft [privacy team](https://support.microsoft.com/gp/privacy-page).</span></span>

### <a name="microsoft-azure"></a><span data-ttu-id="03553-123">Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="03553-123">Microsoft Azure</span></span>

- <span data-ttu-id="03553-124">**Web サイト**: [Microsoft Azure サポート](https://aka.ms/GetAzureSupport)</span><span class="sxs-lookup"><span data-stu-id="03553-124">**Website**: [Microsoft Azure support](https://aka.ms/GetAzureSupport)</span></span>
- <span data-ttu-id="03553-125">**無料電話**番号: 8 800 200 8001</span><span class="sxs-lookup"><span data-stu-id="03553-125">**Toll Free**: 8 800 200 8001</span></span>
- <span data-ttu-id="03553-126">**ローカル通話**: 495 916 7171</span><span class="sxs-lookup"><span data-stu-id="03553-126">**Local Call**: 495 916 7171</span></span>
- <span data-ttu-id="03553-127">**オンラインサポート**: [Azure Portal](https://portal.azure.com)を使用してクエリを送信する</span><span class="sxs-lookup"><span data-stu-id="03553-127">**Online support**: Submit queries via [Azure Portal](https://portal.azure.com)</span></span>

### <a name="microsoft-365"></a><span data-ttu-id="03553-128">Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="03553-128">Microsoft 365</span></span>

- <span data-ttu-id="03553-129">**無料電話**番号: 8 10 800 2548 1044</span><span class="sxs-lookup"><span data-stu-id="03553-129">**Toll Free**: 8 10 800 2548 1044</span></span>
- <span data-ttu-id="03553-130">**ローカル通話**: 499 922 8623</span><span class="sxs-lookup"><span data-stu-id="03553-130">**Local Call**: 499 922 8623</span></span>
- <span data-ttu-id="03553-131">**オンラインサポート**:[管理センター](https://portal.office.com/)からクエリを送信する</span><span class="sxs-lookup"><span data-stu-id="03553-131">**Online support**: Submit queries via [Admin Center](https://portal.office.com/)</span></span>

### <a name="dynamics-365"></a><span data-ttu-id="03553-132">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="03553-132">Dynamics 365</span></span>

- <span data-ttu-id="03553-133">**無料電話**番号: 8 10 800 2548 1044</span><span class="sxs-lookup"><span data-stu-id="03553-133">**Toll Free**: 8 10 800 2548 1044</span></span>
- <span data-ttu-id="03553-134">**ローカル通話**: 499 922 8623</span><span class="sxs-lookup"><span data-stu-id="03553-134">**Local Call**: 499 922 8623</span></span>
- <span data-ttu-id="03553-135">**オンラインサポート**: [Dynamics support ポータル](https://dynamics.microsoft.com/support/)を使用してクエリを送信する</span><span class="sxs-lookup"><span data-stu-id="03553-135">**Online support**: Submit queries via [Dynamics Support portal](https://dynamics.microsoft.com/support/)</span></span>

### <a name="power-platform"></a><span data-ttu-id="03553-136">電源プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="03553-136">Power Platform</span></span>

- <span data-ttu-id="03553-137">**無料電話**番号: 8 10 800 2548 1044</span><span class="sxs-lookup"><span data-stu-id="03553-137">**Toll Free**: 8 10 800 2548 1044</span></span>
- <span data-ttu-id="03553-138">**ローカル通話**: 499 922 8623</span><span class="sxs-lookup"><span data-stu-id="03553-138">**Local Call**: 499 922 8623</span></span>
- <span data-ttu-id="03553-139">**オンラインサポート**:[パワープラットフォームサポート](https://docs.microsoft.com/power-platform/admin/get-help-support)によるクエリの送信</span><span class="sxs-lookup"><span data-stu-id="03553-139">**Online support**: Submit queries via [Power Platform Support](https://docs.microsoft.com/power-platform/admin/get-help-support)</span></span>

> [!NOTE]
> <span data-ttu-id="03553-140"><sup>1</sup>連邦法はありません。</span><span class="sxs-lookup"><span data-stu-id="03553-140"><sup>1</sup> Federal Law No.</span></span> <span data-ttu-id="03553-141">242-FZ (edition 12.31.2014) ' は、ロシアのフェデレーションの特定の法律上の行動に対して、個人データの処理手順を明確にするための情報および電気通信ネットワークの07.21.2014</span><span class="sxs-lookup"><span data-stu-id="03553-141">242-FZ (edition dated 12.31.2014) 'On entering amendments into certain legislative acts of the Russian Federation about clarifying the procedure for personal data processing in information and telecommunication networks' dated 07.21.2014</span></span> <br>
> <span data-ttu-id="03553-142"><sup>2</sup>連邦法はありません。</span><span class="sxs-lookup"><span data-stu-id="03553-142"><sup>2</sup> Federal Law No.</span></span> <span data-ttu-id="03553-143">07.27 の場合、個人データの 152-FZ。</span><span class="sxs-lookup"><span data-stu-id="03553-143">152-FZ on Personal data as of 07.27.</span></span> <span data-ttu-id="03553-144">2006</span><span class="sxs-lookup"><span data-stu-id="03553-144">2006</span></span><br>
