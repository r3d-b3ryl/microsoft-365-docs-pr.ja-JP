---
title: ニュージーランド政府機関向けクラウド コンピューティングのセキュリティとプライバシーに関する考慮事項
description: Microsoft NZ では、ニュージーランド クラウド コンピューティング フレームワークで公開された質問に対して対して対して対して回答しています。
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
ms.openlocfilehash: 99e7d28bea37ec282bd6358b5af81a3078dfdd38
ms.sourcegitcommit: b7f4f1e04b27519b818d4255022b28f99fbe54af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2020
ms.locfileid: "46852503"
---
# <a name="new-zealand-government-cloud-computing-security-and-privacy-considerations"></a><span data-ttu-id="a5004-104">ニュージーランド政府機関向けクラウド コンピューティングのセキュリティとプライバシーに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="a5004-104">New Zealand Government Cloud Computing Security and Privacy Considerations</span></span>

## <a name="new-zealand-government-cloud-computing-security-and-privacy-overview"></a><span data-ttu-id="a5004-105">ニュージーランドの政府機関向けクラウド コンピューティングのセキュリティとプライバシーの概要</span><span class="sxs-lookup"><span data-stu-id="a5004-105">New Zealand Government Cloud Computing Security and Privacy overview</span></span>

<span data-ttu-id="a5004-106">2015 年 10 月に、ニュージーランド Government は、公衆機関全体で情報テクノロジを使用する場合の「クラウド フォーマット」ポリシーを再確認する、変更を行ってきたオールー政府機関向け ICT 戦略を終了しました。</span><span class="sxs-lookup"><span data-stu-id="a5004-106">In October 2015, the New Zealand Government endorsed a revised all-government ICT strategy that reaffirmed its “cloud first” policy on using information technology across the public sector.</span></span> <span data-ttu-id="a5004-107">変更戦略では、NZ Government Chief Information Officer (GCIO) の当該当権に基して開発および実装された「クラウド コンピューティングのリスクおよび管理のフレームワーク」を引き続き使用しています。</span><span class="sxs-lookup"><span data-stu-id="a5004-107">The revised strategy retains the “Cloud Computing Risk and Assurance Framework” that was developed and implemented under the authority of the NZ Government Chief Information Officer (GCIO).</span></span>

<span data-ttu-id="a5004-108">政府機関は、クラウド サービスの評価と導入時に、すべてのニュージーランドの都道府県サービス機関がこのフレームワークの範囲内で機能すると予測しています。</span><span class="sxs-lookup"><span data-stu-id="a5004-108">The government expects all New Zealand State Service agencies to work within this framework when assessing and adopting cloud services.</span></span> <span data-ttu-id="a5004-109">「クラウド コンピューティングの要件」では、クラウド サービスを導入するときに行う必要がある機関の概要と、政府機関のクラウド ポリシーの履歴の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="a5004-109">“Requirements for Cloud Computing” outlines what agencies must do when adopting cloud services along with an overview of the history of the government’s cloud policy.</span></span>

<span data-ttu-id="a5004-110">潜在的なクラウド ソリューションに関する一貫性のある保守の期限で一貫性のある堅牢性を持つ NZ 政府機関の支援を行うために、GCIO は「クラウド コンピューティング: 情報セキュリティとプライバシーに関する考慮事項」(「クラウド コンピューティング ISPC」) を公開しました。</span><span class="sxs-lookup"><span data-stu-id="a5004-110">To assist NZ government agencies in conducting consistent and robust due diligence on potential cloud solutions, the GCIO has published “Cloud Computing: Information Security and Privacy Considerations” (the “Cloud Computing ISPC”).</span></span> <span data-ttu-id="a5004-111">このドキュメントでは、データの保護、プライバシー、セキュリティ、ガバナンス、機密性、データの整合性、可用性、インシデントへの対応と管理に重点を置き、100 を超える質問を説明しています。</span><span class="sxs-lookup"><span data-stu-id="a5004-111">This document contains more than 100 questions focused on data sovereignty, privacy, security, governance, confidentiality, data integrity, availability, and incident response and management.</span></span> <span data-ttu-id="a5004-112">「クラウド コンピューティング IPSC」では、クラウド サービス プロバイダーがどこから一定の形式のコンプライアンスを示す必要があるかを照合する NZ 政府の基準は定義されていないので注意してください。</span><span class="sxs-lookup"><span data-stu-id="a5004-112">Note that “Cloud Computing IPSC” does not define a NZ government standard against which cloud service providers must demonstrate formal compliance.</span></span> <span data-ttu-id="a5004-113">ドキュメントに設定される質問の多くは、クラウド サービス プロバイダーが、幅広い基準にどのように準拠しているかを理解するうえで重要です。</span><span class="sxs-lookup"><span data-stu-id="a5004-113">Many of the questions set out in the document do, however, point toward the importance of understanding how cloud service providers comply with a wide array of relevant standards.</span></span>

<span data-ttu-id="a5004-114">Microsoft とニュージーランド Government のクラウド コンピューティングのセキュリティとプライバシーに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="a5004-114">Microsoft and New Zealand Government Cloud Computing Security and Privacy Considerations</span></span>

<span data-ttu-id="a5004-115">機関が Microsoft エンタープライズ クラウド サービスの分析と評価を行う際の役立つとして、Microsoft New Zealand は、Microsoft クラウド サービスの認定基準に関連付け、エンタープライズ クラウド サービスが "クラウド コンピューティング ISPC" で設定された質問にどのように対応するかを示す一連のドキュメントを作成しました。</span><span class="sxs-lookup"><span data-stu-id="a5004-115">To help agencies undertake their analysis and evaluation of Microsoft enterprise cloud services, Microsoft New Zealand has produced a series of documents showing how its enterprise cloud services address the questions set out in the “Cloud Computing ISPC” by linking them to the standards against which Microsoft cloud services are certified.</span></span> <span data-ttu-id="a5004-116">これらの認定は、プライバシーとセキュリティのリスクを効果的に軽減し、データ保護上の問題に対処するために、どのようにプライバシーとセキュリティのリスクを軽減し、データ保護上の問題に対処できるかを、公衆および国内のお客様がどのように提供しているかを Microsoft がどのように提供しているかを中立つ中です。</span><span class="sxs-lookup"><span data-stu-id="a5004-116">These certifications are central to how Microsoft assures both public and private sector customers that its cloud services are designed, built, and operated to effectively mitigate privacy and security risks and address data sovereignty concerns.</span></span>

<span data-ttu-id="a5004-117">Azure のセキュリティとコンプライアンスのブループリントを使用して NZ CC Framework の展開を高スリーン化する方法を [説明します。NZ CC Framework への Azure 応答をダウンロードする](https://gallery.technet.microsoft.com/Response-to-GCIO-Cloud-e117bbb9)</span><span class="sxs-lookup"><span data-stu-id="a5004-117">Learn how to accelerate your NZ CC Framework deployment with our Azure Security and Compliance Blueprint: [Download Azure response to the NZ CC Framework](https://gallery.technet.microsoft.com/Response-to-GCIO-Cloud-e117bbb9)</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="a5004-118">対象となる Microsoft のクラウド サービス</span><span class="sxs-lookup"><span data-stu-id="a5004-118">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="a5004-119">Azure および Azure Government</span><span class="sxs-lookup"><span data-stu-id="a5004-119">Azure and Azure Government</span></span>](https://aka.ms/AzureCompliance)
- [<span data-ttu-id="a5004-120">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="a5004-120">Dynamics 365</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="a5004-121">Intune</span><span class="sxs-lookup"><span data-stu-id="a5004-121">Intune</span></span>
- <span data-ttu-id="a5004-122">Power BI クラウド サービス (スタンドアロン サービス、または Office 365 ブランド プランあるいはスイートに搭載されているサービス)</span><span class="sxs-lookup"><span data-stu-id="a5004-122">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- [<span data-ttu-id="a5004-123">Office 365</span><span class="sxs-lookup"><span data-stu-id="a5004-123">Office 365</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- <span data-ttu-id="a5004-124">Exchange Online、SharePoint Online、および Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="a5004-124">Exchange Online, SharePoint Online, and Microsoft Teams.</span></span> <span data-ttu-id="a5004-125">Microsoft NZ は GCIO チームと連同して、Exchange Online と SEEMail を統合するための基準アーキテクチャを開発しました。</span><span class="sxs-lookup"><span data-stu-id="a5004-125">Microsoft NZ has worked with the GCIO team to develop a reference architecture for integrating Exchange Online and SEEMail.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="a5004-126">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="a5004-126">Frequently asked questions</span></span>

<span data-ttu-id="a5004-127">**フレームワークは誰に適用されるのでしょうか?**</span><span class="sxs-lookup"><span data-stu-id="a5004-127">**To whom does the framework apply?**</span></span>

<span data-ttu-id="a5004-128">GCIO の適用にかかわる組織 (公的および非公的サービス部門、20 学分ヘルス ボード、および 7 つの Crown entities) は、クラウド サービスの使用を選択する際に、フレームワークに順応する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5004-128">Organizations that fall under the GCIO mandate — the public and non-public service departments, the 20 district health boards, and seven Crown entities — must adhere to the framework when they are deciding on the use of a cloud service.</span></span>

<span data-ttu-id="a5004-129">**ICT システムの認定プロセスで、このフレームワークへの Microsoft の対応を使用できますか?**</span><span class="sxs-lookup"><span data-stu-id="a5004-129">**Can my agency use Microsoft’s responses to this framework in the certification process of our ICT systems?**</span></span>

<span data-ttu-id="a5004-130">機関が ICT システムの New [Zealand Information Security Manual](https://go.microsoft.com/fwlink/p/?linkid=2099496)(ニュージーランド情報セキュリティ マニュアル) で認定と認定を受け取るために必要な場合は、分析の一部として、その応答を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a5004-130">If your agency is required to undertake certification and accreditation of its ICT system under the [New Zealand Information Security Manual](https://go.microsoft.com/fwlink/p/?linkid=2099496), then you can use these responses as part of your analysis.</span></span>

## <a name="resources"></a><span data-ttu-id="a5004-131">リソース</span><span class="sxs-lookup"><span data-stu-id="a5004-131">Resources</span></span>

- [<span data-ttu-id="a5004-132">ホストされているホストされたサービスの損Officeセキュリティ要件: Office 365 のコンプライアンスへのOffice ガイド</span><span class="sxs-lookup"><span data-stu-id="a5004-132">Security requirements for offshore hosted Office productivity services: conformance guide for Office 365</span></span>](https://aka.ms/o365-gcio-conformance-guidance)
- [<span data-ttu-id="a5004-133">ニュージーランドのセキュリティとプライバシー要件に準拠する Microsoft Azure コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="a5004-133">Microsoft Azure compliance in the context of New Zealand security and privacy requirements</span></span>](https://aka.ms/azurecompliancenewzealand)
- [<span data-ttu-id="a5004-134">NZ Government ICT Strategy 2015</span><span class="sxs-lookup"><span data-stu-id="a5004-134">NZ Government ICT Strategy 2015</span></span>](https://www.ict.govt.nz/strategy-and-action-plan/strategy/)
- [<span data-ttu-id="a5004-135">クラウド コンピューティングの NZ 政府機関の要件</span><span class="sxs-lookup"><span data-stu-id="a5004-135">NZ Government requirements for cloud computing</span></span>](https://aka.ms/NZ-Cloud-Requirements)
- [<span data-ttu-id="a5004-136">クラウド コンピューティング: 情報セキュリティとプライバシーに関する考慮事項 (ISPC)</span><span class="sxs-lookup"><span data-stu-id="a5004-136">Cloud Computing: Information Security and Privacy Considerations (ISPC)</span></span>](https://www.digital.govt.nz/standards-and-guidance/technology-and-architecture/cloud-services/)
- [<span data-ttu-id="a5004-137">Microsoft オンライン サービス条件</span><span class="sxs-lookup"><span data-stu-id="a5004-137">Microsoft Online Services Terms</span></span>](https://aka.ms/Online-Services-Terms)
- <span data-ttu-id="a5004-138">[Office 365: SEEMail の統合と参照アーキテクチャ](https://download.microsoft.com/download/8/5/9/859CDCEE-D293-47D8-9B6A-670B108B48E1/Microsoft_Office_365_white_paper_EN_US.pdf) (クラウド サービスの導入に関するその他の Microsoft NZ ガイダンス)</span><span class="sxs-lookup"><span data-stu-id="a5004-138">[Office 365: SEEMail Integration and Reference Architecture](https://download.microsoft.com/download/8/5/9/859CDCEE-D293-47D8-9B6A-670B108B48E1/Microsoft_Office_365_white_paper_EN_US.pdf) (additional Microsoft NZ guidance on cloud service adoption)</span></span>
- [<span data-ttu-id="a5004-139">Microsoft Trust Center のコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="a5004-139">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="microsoft-responses-to-cloud-computing-ipsc"></a><span data-ttu-id="a5004-140">マイクロソフトは、「クラウド コンピューティングの IPSC」への対応</span><span class="sxs-lookup"><span data-stu-id="a5004-140">Microsoft responses to 'Cloud Computing IPSC'</span></span>

- [<span data-ttu-id="a5004-141">Azure</span><span class="sxs-lookup"><span data-stu-id="a5004-141">Azure</span></span>](https://aka.ms/Azure-NZ-response)
- [<span data-ttu-id="a5004-142">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="a5004-142">Dynamics 365</span></span>](https://aka.ms/d365-nz-response)
- [<span data-ttu-id="a5004-143">Intune</span><span class="sxs-lookup"><span data-stu-id="a5004-143">Intune</span></span>](https://aka.ms/Intune-NZ-response)
- [<span data-ttu-id="a5004-144">Office 365</span><span class="sxs-lookup"><span data-stu-id="a5004-144">Office 365</span></span>](https://aka.ms/O365-NZ-Response)
- [<span data-ttu-id="a5004-145">Power BI</span><span class="sxs-lookup"><span data-stu-id="a5004-145">Power BI</span></span>](https://download.microsoft.com/download/5/1/7/51726B9B-2E76-49C4-9D4F-A36BF025CB93/Response-to-GCIO-105-questions-Power-BI.pdf)
