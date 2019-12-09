---
title: Web Content Accessibility Guidelines 2.1
description: Microsoft は、完全な製品またはサービス、または個別にインストールできる製品の一部を反映した WCAG 2.1 AA レポートを公開しています。
keywords: Microsoft 365、コンプライアンス、サービス
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
ms.openlocfilehash: a1887bd2b6c04836ebb11d224fcc59debcd88e55
ms.sourcegitcommit: eb0f255baff1f2856621cbc64a3f34a04be37be3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "39859447"
---
# <a name="web-content-accessibility-guidelines-21"></a><span data-ttu-id="36a4f-104">Web Content Accessibility Guidelines 2.1</span><span class="sxs-lookup"><span data-stu-id="36a4f-104">Web Content Accessibility Guidelines 2.1</span></span>

## <a name="about-wcag-21"></a><span data-ttu-id="36a4f-105">WCAG 2.1 について</span><span class="sxs-lookup"><span data-stu-id="36a4f-105">About WCAG 2.1</span></span>

<span data-ttu-id="36a4f-106">WCAG 2.1 は、障碍のある方や、グラフィック性能が限られているデバイスの利用者のアクセシビリティを改善する Web コンテンツを作成するためのフレームワークを提供します。</span><span class="sxs-lookup"><span data-stu-id="36a4f-106">WCAG 2.1 provides a framework for developing web content that improves accessibility for people with disabilities, in addition to users of devices with limited graphical abilities.</span></span> <span data-ttu-id="36a4f-107">WCAG 2.0 は、2008 年に、Web 標準を策定する専門の国際組織である World Wide Web Consortium (W3C) によって発行され、2018 年 6 月に WCAG 2.1 に更新されました。</span><span class="sxs-lookup"><span data-stu-id="36a4f-107">WCAG 2.0 was published in 2008 by the World Wide Web Consortium (W3C), an international organization dedicated to creating web standards, and updated to WCAG 2.1 in June 2018.</span></span> <span data-ttu-id="36a4f-108">2012 年には、WCAG 2.0 も ISO/IEC 40500:2012 として、国際標準化機構 (ISO) によって発行されました。</span><span class="sxs-lookup"><span data-stu-id="36a4f-108">In 2012, WCAG 2.0 was also published by the International Organization for Standardization (ISO) as ISO/IEC 40500:2012.</span></span>  
  
<span data-ttu-id="36a4f-109">WCAG 2.1 に適合するコンテンツは、WCAG 2.0 にも適合しています。</span><span class="sxs-lookup"><span data-stu-id="36a4f-109">Content that conforms to WCAG 2.1 also conforms to WCAG 2.0.</span></span> <span data-ttu-id="36a4f-110">WCAG 2.0 への適合を必要とするポリシーの場合、WCAG 2.1 は代替の適合手段を提供できます。</span><span class="sxs-lookup"><span data-stu-id="36a4f-110">For policies requiring conformance to WCAG 2.0, WCAG 2.1 can provide an alternate means of conformance.</span></span>  
  
<span data-ttu-id="36a4f-111">各ガイドラインの適合要件は、A、AA、AAA の 3 レベルで評価されます。</span><span class="sxs-lookup"><span data-stu-id="36a4f-111">Conformance requirements for each guideline are measured in three levels: A, AA, and AAA.</span></span> <span data-ttu-id="36a4f-112">Microsoft は、世界中の州および政府に対する主要なソフトウェアおよびクラウド サービス プロバイダーであるため、関連するすべての[国際標準およびコンプライアンス管理](https://go.microsoft.com/fwlink/p/?linkid=2052226)の遵守に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="36a4f-112">Because Microsoft is a major software and cloud-services provider to states and governments around the world, it is committed to complying with all relevant [international standards and compliance controls](https://go.microsoft.com/fwlink/p/?linkid=2052226).</span></span> <span data-ttu-id="36a4f-113">これらの広範囲にわたるアクセシビリティ規格に忠実であることで、Microsoft では、政府内外両方のすべての顧客が Microsoft サービスおよび製品を使用できることを保証します。</span><span class="sxs-lookup"><span data-stu-id="36a4f-113">By adhering to these wide-ranging accessibility standards, Microsoft ensures that all customers — both inside and outside of government — can use Microsoft services and products.</span></span>  

## <a name="microsoft-and-wcag-21"></a><span data-ttu-id="36a4f-114">Microsoft と WCAG 2.1</span><span class="sxs-lookup"><span data-stu-id="36a4f-114">Microsoft and WCAG 2.1</span></span>

<span data-ttu-id="36a4f-115">Microsoft が WCAG 2.1 (ISO/IEC 40500) 標準を順守していることは、すべての顧客がテクノロジーとデータにアクセスできるようにするという責任を示しています。</span><span class="sxs-lookup"><span data-stu-id="36a4f-115">Microsoft’s adherence to the WCAG 2.1 (ISO/IEC 40500) standard points to its commitment to making technology and data accessible for all customers.</span></span> <span data-ttu-id="36a4f-116">WCAG 2.1 (ISO/IEC 40500) は、EN 301 549 (ヨーロッパ) およびセクション 508 (米国) を補完する国際的なアクセシビリティ要件です。</span><span class="sxs-lookup"><span data-stu-id="36a4f-116">WCAG 2.1 (ISO/IEC 40500) is the international accessibility requirement that complements EN 301 549 (Europe) and Section 508 (U.S.).</span></span>  
  
<span data-ttu-id="36a4f-117">Microsoft は、製品またはサービス全体を表す WCAG 2.1 レポートを発行しています。</span><span class="sxs-lookup"><span data-stu-id="36a4f-117">Microsoft publishes WCAG 2.1 reports that reflect the complete product or service.</span></span> <span data-ttu-id="36a4f-118">通常、個々の機能またはコンポーネントのレポートは作成されません。</span><span class="sxs-lookup"><span data-stu-id="36a4f-118">It generally does not create reports for individual features or components.</span></span> <span data-ttu-id="36a4f-119">Microsoft は、既存の製品の新しいコンポーネントや、既存のコンポーネントの新しいバージョンをリリースし、そのコンポーネントをユーザーが個別にインストールできる場合は、そのコンポーネントについての WCAG 2.1 レポートを発行する場合があります。</span><span class="sxs-lookup"><span data-stu-id="36a4f-119">Sometimes, Microsoft might release a new component for an existing product, or a new version of an existing component, which users can choose to install separately, and Microsoft might also publish a WCAG 2.1 report for that component.</span></span>  
  
[<span data-ttu-id="36a4f-120">WCAG 2.1 (ISO/IEC 40500) アクセシビリティ標準をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="36a4f-120">Download the WCAG 2.1 (ISO/IEC 40500) accessibility standards</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2052226)

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="36a4f-121">対象となる Microsoft のクラウド サービス</span><span class="sxs-lookup"><span data-stu-id="36a4f-121">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="36a4f-122">Azure および Azure Government</span><span class="sxs-lookup"><span data-stu-id="36a4f-122">Azure and Azure Government</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2051569)
- <span data-ttu-id="36a4f-123">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="36a4f-123">Azure DevOps Services</span></span>
- <span data-ttu-id="36a4f-124">Dynamics 365、Dynamics 365 米国政府</span><span class="sxs-lookup"><span data-stu-id="36a4f-124">Dynamics 365 and Dynamics 365 U.S. Government</span></span>
- <span data-ttu-id="36a4f-125">Intune</span><span class="sxs-lookup"><span data-stu-id="36a4f-125">Intune</span></span>
- <span data-ttu-id="36a4f-126">Office 365 および Office 365 米国政府</span><span class="sxs-lookup"><span data-stu-id="36a4f-126">Office 365 and Office 365 U.S. Government</span></span>
- <span data-ttu-id="36a4f-127">Office 365 米国防総省</span><span class="sxs-lookup"><span data-stu-id="36a4f-127">Office 365 U.S. Government Defense</span></span>
- <span data-ttu-id="36a4f-128">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="36a4f-128">Windows Server 2016</span></span>

## <a name="microsoft-accessibility-conformance-reports"></a><span data-ttu-id="36a4f-129">Microsoft アクセシビリティ適合レポート</span><span class="sxs-lookup"><span data-stu-id="36a4f-129">Microsoft accessibility conformance reports</span></span>

<span data-ttu-id="36a4f-130">すべての製品およびサービスの WCAG レポートを検索します。</span><span class="sxs-lookup"><span data-stu-id="36a4f-130">Find WCAG reports for all our products and services.</span></span>

[<span data-ttu-id="36a4f-131">**詳細情報**</span><span class="sxs-lookup"><span data-stu-id="36a4f-131">**Learn more**</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2050974)

## <a name="resources"></a><span data-ttu-id="36a4f-132">リソース</span><span class="sxs-lookup"><span data-stu-id="36a4f-132">Resources</span></span>

<span data-ttu-id="36a4f-133">Microsoft アクセシビリティ サイト — アクセシビリティ機能の使用に関する情報を取得して、すべてのユーザーがもっと多くのことを達成するために Microsoft ではどのような革新が行われているのかを理解します。</span><span class="sxs-lookup"><span data-stu-id="36a4f-133">[Microsoft accessibility site — Get information on using accessibility features and explore the ways Microsoft innovates to help everyone achieve more.</span></span>

[<span data-ttu-id="36a4f-134">Office 365 アクセシビリティ センター</span><span class="sxs-lookup"><span data-stu-id="36a4f-134">Office 365 Accessibility Center</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2051801)
    - <span data-ttu-id="36a4f-135">身体に障害のある方向けの Office 365 リソース</span><span class="sxs-lookup"><span data-stu-id="36a4f-135">Office 365 resources for people with disabilities.</span></span>

[<span data-ttu-id="36a4f-136">Enterprise Disability Answer Desk</span><span class="sxs-lookup"><span data-stu-id="36a4f-136">Enterprise Disability Answer Desk</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2050890)
    - <span data-ttu-id="36a4f-137">製品およびサービス、またはコンプライアンスについて、アクセシビリティに関する質問のあるエンタープライズのお客様専用のサポートです。</span><span class="sxs-lookup"><span data-stu-id="36a4f-137">Dedicated support for enterprise customers with accessibility questions about our products and services or compliance.</span></span>

[<span data-ttu-id="36a4f-138">Microsoft トラスト センターのコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="36a4f-138">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="36a4f-139">サービスの背景資料をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="36a4f-139">Download the offering backgrounder</span></span>

<span data-ttu-id="36a4f-140">このサービスに関する背景資料が必要ですか?</span><span class="sxs-lookup"><span data-stu-id="36a4f-140">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="36a4f-141">[PDF](https://download.microsoft.com/download/3/E/1/3E10CC43-036D-4DB5-ACBA-8665A752C8F7/Accessibility-Compliance.pdf) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="36a4f-141">Download the [PDF](https://download.microsoft.com/download/3/E/1/3E10CC43-036D-4DB5-ACBA-8665A752C8F7/Accessibility-Compliance.pdf).</span></span>
