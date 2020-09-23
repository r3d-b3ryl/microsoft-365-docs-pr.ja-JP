---
title: ロシアの個人データローカライズ要件
description: 個人データ、ロシア市民の個人データ記録、systematization、蓄積、保存、明確化、および抽出が、ロシアにある Microsoft サービスおよびデータベースで実行される方法について説明します。
keywords: Microsoft 365、コンプライアンス、サービス
localization_priority: None
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 29c56d525375162926d34bd298bbbd660964438d
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48208159"
---
# <a name="russian-personal-data-localization-requirements"></a><span data-ttu-id="33c52-104">ロシアの個人データローカライズ要件</span><span class="sxs-lookup"><span data-stu-id="33c52-104">Russian Personal Data Localization Requirements</span></span>

<span data-ttu-id="33c52-105">2015年9月1日時点で、個人データオペレーターと見なされる組織では、個人データを収集する際に、ロシア市民の個人データ記録、systematization、蓄積、保存、説明 (更新、変更)、および抽出がロシアにあるデータベース (「個人データのローカリゼーション要件」) によって実行されることを保証する必要があります。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="33c52-105">As of September 1, 2015, organizations that are considered personal data operators must ensure that, when collecting personal data, Russian citizens' personal data recording, systematization, accumulation, storage, clarification (updating, changing), and extraction are performed through the databases located in Russia ('personal data localization requirement').<sup>1</sup></span></span>

<span data-ttu-id="33c52-106">Microsoft Azure、Microsoft 365、Dynamics 365、および Power Platform などの個人データ処理を有効にすることを含む、組織で利用可能な microsoft Online Services (教育機関に限定されない) (hereinafter と呼ばれる) (詳細については、「 [Microsoft Trust Center](https://www.microsoft.com/trust-center)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="33c52-106">Microsoft Online Services available to organizations (including but not limited to educational institutions) (hereinafter referred to as 'customer'), including those enabling personal data processing such as Microsoft Azure, Microsoft 365, Dynamics 365, and Power Platform, are provided from data processing centers located outside of Russia (for more information visit the [Microsoft Trust Center](https://www.microsoft.com/trust-center)).</span></span>

<span data-ttu-id="33c52-107">ユーザー情報システムによって処理された情報の種類と内容に基づいて、Microsoft クラウド製品を使用しているものも含めて、個人データ情報システム (' PDIS ', ' ISPD ') と見なされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="33c52-107">Based on the type and content of information processed by customer information systems, such systems, including those using Microsoft cloud products, may be deemed a personal data information system ('PDIS', 'ISPD').</span></span> <span data-ttu-id="33c52-108">お客様が PDM として認定されているシステムで Microsoft Online Services を使用することを希望している場合は、Microsoft は、お客様に対して、次に示すその他のソリューションを検討することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="33c52-108">In cases where the customer would like to use Microsoft Online Services in a system that qualifies as PDIS through its architecture and types of information processed, Microsoft invites its customers to consider, amongst other things, available solutions specified below.</span></span> <span data-ttu-id="33c52-109">提供されているすべてのシナリオは、標準のビジネス製品に対する追加オプションとして、お客様が利用できます。</span><span class="sxs-lookup"><span data-stu-id="33c52-109">All the scenarios provided are available for customers as an additional option to standard business offerings.</span></span>

<span data-ttu-id="33c52-110">このお客様には、PDIS 個人データ事業者がコンプライアンスを担当しており、個人データローカリゼーションの適用可能な法的要件を分析して評価する必要があることに注意してください。また、独自の判断で、PDIS の個人データの処理がロシアの個人データの法則に準拠していることを確認するために十分な<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="33c52-110">It should be noted that it is the customer as personal data operator of PDIS who is in charge of compliance and shall analyze and assess applicable legal requirements for personal data localization, and at its own discretion, independently determine sufficient measures to ensure that personal data processing in PDIS complies with the Russian personal data law.<sup>2</sup></span></span>

## <a name="subscribing-to-microsoft-online-services"></a><span data-ttu-id="33c52-111">Microsoft Online Services を購読する</span><span class="sxs-lookup"><span data-stu-id="33c52-111">Subscribing to Microsoft Online Services</span></span>

### <a name="microsoft-id-management"></a><span data-ttu-id="33c52-112">Microsoft ID の管理</span><span class="sxs-lookup"><span data-stu-id="33c52-112">Microsoft ID Management</span></span>

<span data-ttu-id="33c52-113">Microsoft は、microsoft のクラウドソリューションプロバイダー (CSP) パートナー経由で microsoft Online Services (Microsoft Azure、Microsoft 365、Dynamics 365、および電源プラットフォーム) へのサブスクライブを検討することをお客様に招待しています。</span><span class="sxs-lookup"><span data-stu-id="33c52-113">Microsoft invites customers to consider subscribing to Microsoft Online Services—Microsoft Azure, Microsoft 365, Dynamics 365, and Power Platform—via a Microsoft Cloud Solution Provider (CSP) partner.</span></span> <span data-ttu-id="33c52-114">詳細については、 [CSP パートナーの一覧](https://pinpoint.microsoft.com/search?type=services&campaign=691) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33c52-114">See this [list of CSP partners](https://pinpoint.microsoft.com/search?type=services&campaign=691) for more information.</span></span>

### <a name="managing-user-identity-and-access-for-microsoft-online-services"></a><span data-ttu-id="33c52-115">Microsoft Online Services のユーザー Id とアクセス権を管理する</span><span class="sxs-lookup"><span data-stu-id="33c52-115">Managing User Identity and Access for Microsoft Online Services</span></span>

<span data-ttu-id="33c52-116">Microsoft Azure、Microsoft 365、Dynamics 365、電源プラットフォームなどの Microsoft Online Services の場合、ユーザーの確認とアクセスの管理は [Azure Active Directory (AAD)](https://azure.microsoft.com/services/active-directory/)を介して実行されます。</span><span class="sxs-lookup"><span data-stu-id="33c52-116">For Microsoft Online Services such as Microsoft Azure, Microsoft 365, Dynamics 365, and Power Platform, user verification and access management are performed through [Azure Active Directory (AAD)](https://azure.microsoft.com/services/active-directory/).</span></span> <span data-ttu-id="33c52-117">Microsoft のお客様が Microsoft クラウドサービス (Windows Server Active Directory (AD) やその他の ID 管理システムなど) に対してローカルの id 管理システムを使用している場合、お客様は Azure AD Connect を通じてこのようなシステムを Azure Active Directory (AAD) にすばやく統合することができます。</span><span class="sxs-lookup"><span data-stu-id="33c52-117">Note that cases where a Microsoft customer uses a local identification management system for Microsoft cloud services (such as the Windows Server Active Directory (AD) or any other ID management system), the customer has an opportunity to swiftly integrate such system with the Azure Active Directory (AAD) through Azure AD Connect.</span></span> <span data-ttu-id="33c52-118">詳細については、「 [AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/cloud-provisioning/) 」オプションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="33c52-118">See the [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/cloud-provisioning/) option for more information.</span></span> <span data-ttu-id="33c52-119">また、Microsoft のお客様は、サードパーティベンダーのアプリケーションやソリューションを使用してユーザーを管理し、そのローカル識別システムを Azure AD と統合することを検討することもできます。</span><span class="sxs-lookup"><span data-stu-id="33c52-119">Microsoft customers may also consider using applications and solutions of third-party vendors for managing their users and integrating their local identification system with the Azure AD.</span></span>

## <a name="use-microsoft-compliance-manager-to-assess-your-risk"></a><span data-ttu-id="33c52-120">Microsoft コンプライアンスマネージャーを使用してリスクを評価する</span><span class="sxs-lookup"><span data-stu-id="33c52-120">Use Microsoft Compliance Manager to assess your risk</span></span>

<span data-ttu-id="33c52-121">[Microsoft コンプライアンスマネージャー](compliance-manager.md) は、 [microsoft 365 コンプライアンスセンター](microsoft-365-compliance-center.md) の機能であり、組織のコンプライアンスの状況を理解し、リスクを軽減するためのアクションを実行するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="33c52-121">[Microsoft Compliance Manager](compliance-manager.md) is a feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) to help you understand your organization's compliance posture and take actions to help reduce risks.</span></span> <span data-ttu-id="33c52-122">コンプライアンスマネージャーには、この規制の評価を構築するためのプレミアムテンプレートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="33c52-122">Compliance Manager offers a premium template for building an assessment for this regulation.</span></span> <span data-ttu-id="33c52-123">[コンプライアンスマネージャー] の [ **評価テンプレート** ] ページでテンプレートを検索します。</span><span class="sxs-lookup"><span data-stu-id="33c52-123">Find the template in the **assessment templates** page in Compliance Manager.</span></span> <span data-ttu-id="33c52-124">[コンプライアンスマネージャーで評価を作成](compliance-manager-assessments.md)する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="33c52-124">Learn how to [build assessments in Compliance Manager](compliance-manager-assessments.md).</span></span>

## <a name="questions-and-support"></a><span data-ttu-id="33c52-125">質問とサポート</span><span class="sxs-lookup"><span data-stu-id="33c52-125">Questions and support</span></span>

<span data-ttu-id="33c52-126">技術的および請求に関する質問については、以下の Microsoft サポートリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="33c52-126">For technical and billing questions, refer to the Microsoft Support resources below.</span></span> <span data-ttu-id="33c52-127">その他の質問や説明については、Microsoft の [プライバシーチーム](https://support.microsoft.com/gp/privacy-page)にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="33c52-127">For additional questions or clarifications, contact the Microsoft [privacy team](https://support.microsoft.com/gp/privacy-page).</span></span>

### <a name="microsoft-azure"></a><span data-ttu-id="33c52-128">Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="33c52-128">Microsoft Azure</span></span>

- <span data-ttu-id="33c52-129">**Web サイト**: [Microsoft Azure サポート](https://aka.ms/GetAzureSupport)</span><span class="sxs-lookup"><span data-stu-id="33c52-129">**Website**: [Microsoft Azure support](https://aka.ms/GetAzureSupport)</span></span>
- <span data-ttu-id="33c52-130">**無料電話**番号: 8 800 200 8001</span><span class="sxs-lookup"><span data-stu-id="33c52-130">**Toll Free**: 8 800 200 8001</span></span>
- <span data-ttu-id="33c52-131">**ローカル通話**: 495 916 7171</span><span class="sxs-lookup"><span data-stu-id="33c52-131">**Local Call**: 495 916 7171</span></span>
- <span data-ttu-id="33c52-132">**オンラインサポート**: [Azure ポータル](https://portal.azure.com)経由でクエリを送信する</span><span class="sxs-lookup"><span data-stu-id="33c52-132">**Online support**: Submit queries via the [Azure Portal](https://portal.azure.com)</span></span>

### <a name="microsoft-365"></a><span data-ttu-id="33c52-133">Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="33c52-133">Microsoft 365</span></span>

- <span data-ttu-id="33c52-134">**無料電話**番号: 8 10 800 2548 1044</span><span class="sxs-lookup"><span data-stu-id="33c52-134">**Toll Free**: 8 10 800 2548 1044</span></span>
- <span data-ttu-id="33c52-135">**ローカル通話**: 499 922 8623</span><span class="sxs-lookup"><span data-stu-id="33c52-135">**Local Call**: 499 922 8623</span></span>
- <span data-ttu-id="33c52-136">**オンラインサポート**:[管理センター](https://portal.office.com/)からクエリを送信する</span><span class="sxs-lookup"><span data-stu-id="33c52-136">**Online support**: Submit queries via the [Admin Center](https://portal.office.com/)</span></span>

### <a name="dynamics-365"></a><span data-ttu-id="33c52-137">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="33c52-137">Dynamics 365</span></span>

- <span data-ttu-id="33c52-138">**無料電話**番号: 8 10 800 2548 1044</span><span class="sxs-lookup"><span data-stu-id="33c52-138">**Toll Free**: 8 10 800 2548 1044</span></span>
- <span data-ttu-id="33c52-139">**ローカル通話**: 499 922 8623</span><span class="sxs-lookup"><span data-stu-id="33c52-139">**Local Call**: 499 922 8623</span></span>
- <span data-ttu-id="33c52-140">**オンラインサポート**: [Dynamics サポートポータル](https://dynamics.microsoft.com/support/)でクエリを送信する</span><span class="sxs-lookup"><span data-stu-id="33c52-140">**Online support**: Submit queries via the [Dynamics Support portal](https://dynamics.microsoft.com/support/)</span></span>

### <a name="power-platform"></a><span data-ttu-id="33c52-141">電源プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="33c52-141">Power Platform</span></span>

- <span data-ttu-id="33c52-142">**無料電話**番号: 8 10 800 2548 1044</span><span class="sxs-lookup"><span data-stu-id="33c52-142">**Toll Free**: 8 10 800 2548 1044</span></span>
- <span data-ttu-id="33c52-143">**ローカル通話**: 499 922 8623</span><span class="sxs-lookup"><span data-stu-id="33c52-143">**Local Call**: 499 922 8623</span></span>
- <span data-ttu-id="33c52-144">**オンラインサポート**:[電源プラットフォームサポート](https://docs.microsoft.com/power-platform/admin/get-help-support)経由でクエリを送信する</span><span class="sxs-lookup"><span data-stu-id="33c52-144">**Online support**: Submit queries via the [Power Platform Support](https://docs.microsoft.com/power-platform/admin/get-help-support)</span></span>

> [!NOTE]
> <span data-ttu-id="33c52-145"><sup>1</sup> 連邦法はありません。</span><span class="sxs-lookup"><span data-stu-id="33c52-145"><sup>1</sup> Federal Law No.</span></span> <span data-ttu-id="33c52-146">242-FZ (edition 12.31.2014) ' は、ロシアのフェデレーションの特定の法律上の行動に対して、個人データの処理手順を明確にするための情報および電気通信ネットワークの07.21.2014</span><span class="sxs-lookup"><span data-stu-id="33c52-146">242-FZ (edition dated 12.31.2014) 'On entering amendments into certain legislative acts of the Russian Federation about clarifying the procedure for personal data processing in information and telecommunication networks' dated 07.21.2014</span></span> <br>
> <span data-ttu-id="33c52-147"><sup>2</sup> 連邦法はありません。</span><span class="sxs-lookup"><span data-stu-id="33c52-147"><sup>2</sup> Federal Law No.</span></span> <span data-ttu-id="33c52-148">07.27 の場合、個人データの 152-FZ。</span><span class="sxs-lookup"><span data-stu-id="33c52-148">152-FZ on Personal data as of 07.27.</span></span> <span data-ttu-id="33c52-149">2006</span><span class="sxs-lookup"><span data-stu-id="33c52-149">2006</span></span><br>
