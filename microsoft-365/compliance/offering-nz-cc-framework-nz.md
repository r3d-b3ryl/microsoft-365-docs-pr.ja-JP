---
title: ニュージーランド政府機関向けクラウドコンピューティングのセキュリティとプライバシーに関する考慮事項
description: Microsoft NZ は、ニュージーランドクラウドコンピューティングフレームワークで公開されている質問に対応しています。
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
ms.openlocfilehash: 3142ce35cdc55e32cf5f40042967ba60de789dcc
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601884"
---
# <a name="new-zealand-government-cloud-computing-security-and-privacy-considerations"></a><span data-ttu-id="4b959-104">ニュージーランド政府機関向けクラウドコンピューティングのセキュリティとプライバシーに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="4b959-104">New Zealand Government Cloud Computing Security and Privacy Considerations</span></span>

## <a name="new-zealand-government-cloud-computing-security-and-privacy-overview"></a><span data-ttu-id="4b959-105">ニュージーランド政府機関向けクラウドコンピューティングのセキュリティとプライバシーの概要</span><span class="sxs-lookup"><span data-stu-id="4b959-105">New Zealand Government Cloud Computing Security and Privacy overview</span></span>

<span data-ttu-id="4b959-106">2015年10月に、公的機関による情報技術を使用して、「クラウドファースト」ポリシーを再確定する、改訂された全行政の ICT 戦略を裏書しました。</span><span class="sxs-lookup"><span data-stu-id="4b959-106">In October 2015, the New Zealand Government endorsed a revised all-government ICT strategy that reaffirmed its “cloud first” policy on using information technology across the public sector.</span></span> <span data-ttu-id="4b959-107">改定された戦略では、"クラウドコンピューティングのリスクと保証" フレームワーク "を保持しています。これは、NZ 政府機関のチーフ情報責任者 (GCIO) の権限で開発および実装されています。</span><span class="sxs-lookup"><span data-stu-id="4b959-107">The revised strategy retains the “Cloud Computing Risk and Assurance Framework” that was developed and implemented under the authority of the NZ Government Chief Information Officer (GCIO).</span></span>

<span data-ttu-id="4b959-108">政府は、クラウドサービスを評価して採用するときに、すべてのニュージーランド状態サービスエージェンシーがこのフレームワーク内で機能することを想定しています。</span><span class="sxs-lookup"><span data-stu-id="4b959-108">The government expects all New Zealand State Service agencies to work within this framework when assessing and adopting cloud services.</span></span> <span data-ttu-id="4b959-109">「クラウドコンピューティングの要件」では、クラウドサービスを採用する際に実行する必要がある機関と、政府機関のクラウドポリシーの概要について概説します。</span><span class="sxs-lookup"><span data-stu-id="4b959-109">“Requirements for Cloud Computing” outlines what agencies must do when adopting cloud services along with an overview of the history of the government’s cloud policy.</span></span>

<span data-ttu-id="4b959-110">「クラウドコンピューティング: 情報のセキュリティとプライバシーに関する考慮事項」 (「クラウドコンピューティング ISPC」) というように、GCIO が、潜在的なクラウドソリューションに関して、一貫した堅牢なデューデリジェンスを実現できるようにするために、GCIO が公開しています。</span><span class="sxs-lookup"><span data-stu-id="4b959-110">To assist NZ government agencies in conducting consistent and robust due diligence on potential cloud solutions, the GCIO has published “Cloud Computing: Information Security and Privacy Considerations” (the “Cloud Computing ISPC”).</span></span> <span data-ttu-id="4b959-111">このドキュメントには、データ主権、プライバシー、セキュリティ、ガバナンス、機密性、データの整合性、可用性、およびインシデントの対応と管理に焦点を絞った100の質問が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b959-111">This document contains more than 100 questions focused on data sovereignty, privacy, security, governance, confidentiality, data integrity, availability, and incident response and management.</span></span> <span data-ttu-id="4b959-112">「クラウドコンピューティング IPSC」では、クラウドサービスプロバイダーが公式のコンプライアンスを実証する必要がある、NZ という標準が定義されていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4b959-112">Note that “Cloud Computing IPSC” does not define a NZ government standard against which cloud service providers must demonstrate formal compliance.</span></span> <span data-ttu-id="4b959-113">ドキュメントで設定されているいくつかの質問については、クラウドサービスプロバイダーがさまざまな関連標準に準拠する方法を理解することが重要であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="4b959-113">Many of the questions set out in the document do, however, point toward the importance of understanding how cloud service providers comply with a wide array of relevant standards.</span></span>

<span data-ttu-id="4b959-114">Microsoft およびニュージーランド政府機関向けのクラウドコンピューティングのセキュリティとプライバシーに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="4b959-114">Microsoft and New Zealand Government Cloud Computing Security and Privacy Considerations</span></span>

<span data-ttu-id="4b959-115">エージェンシーが Microsoft enterprise cloud services の分析と評価を行うのに役立つように、Microsoft ニュージーランドでは、エンタープライズクラウドサービスが「クラウドコンピューティング ISPC」で設定した質問をどのように解決するかを示す一連のドキュメントが作成されています。Microsoft cloud services が認定されている基準にそれらをリンクします。</span><span class="sxs-lookup"><span data-stu-id="4b959-115">To help agencies undertake their analysis and evaluation of Microsoft enterprise cloud services, Microsoft New Zealand has produced a series of documents showing how its enterprise cloud services address the questions set out in the “Cloud Computing ISPC” by linking them to the standards against which Microsoft cloud services are certified.</span></span> <span data-ttu-id="4b959-116">これらの認定資格は、Microsoft がクラウドサービスを設計、構築、運用することによって、プライバシーおよびセキュリティリスクを効果的に軽減し、データ主権の懸念事項を解決できるようにすることを中心としています。</span><span class="sxs-lookup"><span data-stu-id="4b959-116">These certifications are central to how Microsoft assures both public and private sector customers that its cloud services are designed, built, and operated to effectively mitigate privacy and security risks and address data sovereignty concerns.</span></span>

<span data-ttu-id="4b959-117">Microsoft Cloud での NZ CC フレームワークの利点について説明します。 [NZ cc framework backgrounder をダウンロードし](https://aka.ms/nzcc-framework-backgrounder)てください。</span><span class="sxs-lookup"><span data-stu-id="4b959-117">Learn about the benefits of NZ CC Framework on the Microsoft Cloud: [Download the NZ CC framework backgrounder](https://aka.ms/nzcc-framework-backgrounder)</span></span>

<span data-ttu-id="4b959-118">Azure セキュリティおよびコンプライアンスブループリントを使用して、NZ による [CC] フレームワークの展開を促進する方法について説明します。 [azure からの応答を nz にダウンロード](https://gallery.technet.microsoft.com/Response-to-GCIO-Cloud-e117bbb9)します。</span><span class="sxs-lookup"><span data-stu-id="4b959-118">Learn how to accelerate your NZ CC Framework deployment with our Azure Security and Compliance Blueprint: [Download Azure response to the NZ CC Framework](https://gallery.technet.microsoft.com/Response-to-GCIO-Cloud-e117bbb9)</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="4b959-119">対象となる Microsoft のクラウド サービス</span><span class="sxs-lookup"><span data-stu-id="4b959-119">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="4b959-120">Azure および Azure Government</span><span class="sxs-lookup"><span data-stu-id="4b959-120">Azure and Azure Government</span></span>](https://aka.ms/AzureCompliance)
- [<span data-ttu-id="4b959-121">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="4b959-121">Dynamics 365</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="4b959-122">Intune</span><span class="sxs-lookup"><span data-stu-id="4b959-122">Intune</span></span>
- <span data-ttu-id="4b959-123">Power BI クラウド サービス (スタンドアロン サービス、または Office 365 ブランド プランあるいはスイートに搭載されているサービス)</span><span class="sxs-lookup"><span data-stu-id="4b959-123">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- [<span data-ttu-id="4b959-124">Office 365</span><span class="sxs-lookup"><span data-stu-id="4b959-124">Office 365</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- <span data-ttu-id="4b959-125">Exchange Online、SharePoint Online、Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="4b959-125">Exchange Online, SharePoint Online, and Skype for Business Online.</span></span> <span data-ttu-id="4b959-126">Microsoft NZ は、ホワイトペーパー「 [Office outlook 365: Seemail 統合およびリファレンスアーキテクチャ](https://download.microsoft.com/download/8/5/9/859CDCEE-D293-47D8-9B6A-670B108B48E1/Microsoft_Office_365_white_paper_EN_US.pdf)」で説明されている Exchange Online と seemail を統合するためのリファレンスアーキテクチャを開発するための gcio チームと協力しています。</span><span class="sxs-lookup"><span data-stu-id="4b959-126">Microsoft NZ has worked with the GCIO team to develop a reference architecture for integrating Exchange Online and SEEMail described in the white paper [Office 365: SEEMail Integration and Reference Architecture](https://download.microsoft.com/download/8/5/9/859CDCEE-D293-47D8-9B6A-670B108B48E1/Microsoft_Office_365_white_paper_EN_US.pdf)</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="4b959-127">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="4b959-127">Frequently asked questions</span></span>

<span data-ttu-id="4b959-128">**フレームワークが適用されるユーザー**</span><span class="sxs-lookup"><span data-stu-id="4b959-128">**To whom does the framework apply?**</span></span>

<span data-ttu-id="4b959-129">「CIO の義務」の下にある組織: パブリックおよび非パブリックのサービス部門、20個の学区の健康ボード、7つのクラウンエンティティは、クラウドサービスの使用を決定する際に、フレームワークに準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b959-129">Organizations that fall under the GCIO mandate — the public and non-public service departments, the 20 district health boards, and seven Crown entities — must adhere to the framework when they are deciding on the use of a cloud service.</span></span>

<span data-ttu-id="4b959-130">**このフレームワークに対する Microsoft の対応を ICT システムの認定プロセスに使用することはできますか?**</span><span class="sxs-lookup"><span data-stu-id="4b959-130">**Can my agency use Microsoft’s responses to this framework in the certification process of our ICT systems?**</span></span>

<span data-ttu-id="4b959-131">事務局が[新ニュージーランド情報セキュリティマニュアル](https://go.microsoft.com/fwlink/p/?linkid=2099496)の下にある ICT システムの認定および認定を行う必要がある場合は、これらの応答を分析の一部として使用できます。</span><span class="sxs-lookup"><span data-stu-id="4b959-131">If your agency is required to undertake certification and accreditation of its ICT system under the [New Zealand Information Security Manual](https://go.microsoft.com/fwlink/p/?linkid=2099496), then you can use these responses as part of your analysis.</span></span>

## <a name="resources"></a><span data-ttu-id="4b959-132">リソース</span><span class="sxs-lookup"><span data-stu-id="4b959-132">Resources</span></span>

- [<span data-ttu-id="4b959-133">海外でホストされている Office プロダクティビティサービスのセキュリティ要件: Office 365 の準拠ガイド</span><span class="sxs-lookup"><span data-stu-id="4b959-133">Security requirements for offshore hosted Office productivity services: conformance guide for Office 365</span></span>](https://aka.ms/o365-gcio-conformance-guidance)
- [<span data-ttu-id="4b959-134">ニュージーランドのセキュリティおよびプライバシーに関する要件のコンテキストにおける Microsoft Azure コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="4b959-134">Microsoft Azure compliance in the context of New Zealand security and privacy requirements</span></span>](https://aka.ms/azurecompliancenewzealand)
- [<span data-ttu-id="4b959-135">NZ 政府 ICT 戦略2015</span><span class="sxs-lookup"><span data-stu-id="4b959-135">NZ Government ICT Strategy 2015</span></span>](https://www.ict.govt.nz/strategy-and-action-plan/strategy/)
- [<span data-ttu-id="4b959-136">クラウドコンピューティングのための NZ 政府の要件</span><span class="sxs-lookup"><span data-stu-id="4b959-136">NZ Government requirements for cloud computing</span></span>](https://aka.ms/NZ-Cloud-Requirements)
- [<span data-ttu-id="4b959-137">クラウドコンピューティング: 情報のセキュリティとプライバシーに関する考慮事項 (ISPC)</span><span class="sxs-lookup"><span data-stu-id="4b959-137">Cloud Computing: Information Security and Privacy Considerations (ISPC)</span></span>](https://www.digital.govt.nz/standards-and-guidance/technology-and-architecture/cloud-services/)
- [<span data-ttu-id="4b959-138">Microsoft オンライン サービス条件</span><span class="sxs-lookup"><span data-stu-id="4b959-138">Microsoft Online Services Terms</span></span>](https://aka.ms/Online-Services-Terms)
- <span data-ttu-id="4b959-139">[Office 365: SEEMail 統合と参照アーキテクチャ](https://download.microsoft.com/download/8/5/9/859CDCEE-D293-47D8-9B6A-670B108B48E1/Microsoft_Office_365_white_paper_EN_US.pdf)(クラウドサービス導入に関する Microsoft NZ の追加ガイダンス)</span><span class="sxs-lookup"><span data-stu-id="4b959-139">[Office 365: SEEMail Integration and Reference Architecture](https://download.microsoft.com/download/8/5/9/859CDCEE-D293-47D8-9B6A-670B108B48E1/Microsoft_Office_365_white_paper_EN_US.pdf) (additional Microsoft NZ guidance on cloud service adoption)</span></span>
- [<span data-ttu-id="4b959-140">Microsoft セキュリティ センターのコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="4b959-140">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="microsoft-responses-to-cloud-computing-ipsc"></a><span data-ttu-id="4b959-141">「クラウドコンピューティング IPSC」への Microsoft の応答</span><span class="sxs-lookup"><span data-stu-id="4b959-141">Microsoft responses to “Cloud Computing IPSC”</span></span>

- [<span data-ttu-id="4b959-142">Azure</span><span class="sxs-lookup"><span data-stu-id="4b959-142">Azure</span></span>](https://aka.ms/Azure-NZ-response)
- [<span data-ttu-id="4b959-143">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="4b959-143">Dynamics 365</span></span>](https://aka.ms/d365-nz-response)
- [<span data-ttu-id="4b959-144">Intune</span><span class="sxs-lookup"><span data-stu-id="4b959-144">Intune</span></span>](https://aka.ms/Intune-NZ-response)
- [<span data-ttu-id="4b959-145">Office 365</span><span class="sxs-lookup"><span data-stu-id="4b959-145">Office 365</span></span>](https://aka.ms/O365-NZ-Response)
- [<span data-ttu-id="4b959-146">Power BI</span><span class="sxs-lookup"><span data-stu-id="4b959-146">Power BI</span></span>](https://download.microsoft.com/download/5/1/7/51726B9B-2E76-49C4-9D4F-A36BF025CB93/Response-to-GCIO-105-questions-Power-BI.pdf)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="4b959-147">サービスの背景解説をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="4b959-147">Download the offering backgrounder</span></span>

<span data-ttu-id="4b959-148">このサービスに関する背景解説をご覧になりたい場合は、</span><span class="sxs-lookup"><span data-stu-id="4b959-148">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="4b959-149">[PDF](https://download.microsoft.com/download/6/6/4/664E4B6F-15C6-421E-8F74-3FA468587A47/NZ_CC_Compliance_Backgrounder.pdf) ファイルをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="4b959-149">Download the [PDF](https://download.microsoft.com/download/6/6/4/664E4B6F-15C6-421E-8F74-3FA468587A47/NZ_CC_Compliance_Backgrounder.pdf).</span></span>
