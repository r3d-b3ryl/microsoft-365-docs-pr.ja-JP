---
title: グラム リーチ ブライリー法 (GLBA)
description: Microsoft は、金融サービスクライアントが対象-なる Act (GLBA) のプライバシーとセキュリティの要件に準拠していることをサポートしています。
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
ms.openlocfilehash: 7969d18bea1e8873651a1ea94e46c6b7a6b48c83
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48208399"
---
# <a name="gramm-leach-bliley-act-glba"></a><span data-ttu-id="15235-104">グラム リーチ ブライリー法 (GLBA)</span><span class="sxs-lookup"><span data-stu-id="15235-104">Gramm-Leach-Bliley Act (GLBA)</span></span>

## <a name="glba-overview"></a><span data-ttu-id="15235-105">GLBA の概要</span><span class="sxs-lookup"><span data-stu-id="15235-105">GLBA overview</span></span>

<span data-ttu-id="15235-106">グラムリーチブライ対象-なる Act (GLBA) は、金融サービス業界を再構築し、商業および投資銀行、証券会社、保険会社を統合し、消費者のプライバシー保護について考慮することを許可する米国の法律です。</span><span class="sxs-lookup"><span data-stu-id="15235-106">The Gramm-Leach-Bliley Act (GLBA) is a US law that reformed the financial services industry, allowing commercial and investment banks, securities firms, and insurance companies to consolidate, and addressed concerns about protecting consumer privacy.</span></span> <span data-ttu-id="15235-107">金融プライバシールールおよび保護ルールとして、このようなプライバシープロビジョニングに対処するための法規を実装するには、連邦取引委員会 (FTC) およびその他の金融サービス規制機関が必要でした。</span><span class="sxs-lookup"><span data-stu-id="15235-107">It required the Federal Trade Commission (FTC) and other financial services regulators to implement regulations to address such privacy provisions as the Financial Privacy Rule and the Safeguards Rule.</span></span> <span data-ttu-id="15235-108">機密消費者データを保護するための GLBA の要件ローン、投資のアドバイス、保険など、顧客に金融商品やサービスを提供する金融機関に適用されます。</span><span class="sxs-lookup"><span data-stu-id="15235-108">GLBA requirements to safeguard sensitive consumer data apply to financial institutions that offer financial products and services to consumers, such as loans, investment advice, and insurance.</span></span> <span data-ttu-id="15235-109">FTC には、コンプライアンスを適用する料金が課せられます。</span><span class="sxs-lookup"><span data-stu-id="15235-109">The FTC is charged with enforcing compliance.</span></span>

## <a name="microsoft-and-glba"></a><span data-ttu-id="15235-110">Microsoft および GLBA</span><span class="sxs-lookup"><span data-stu-id="15235-110">Microsoft and GLBA</span></span>

<span data-ttu-id="15235-111">Microsoft Azure、Microsoft Office 365、Dynamics 365、および Microsoft Power BI は、金融サービス機関にクラウドサービスを提供するための厳しい要件を満たすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="15235-111">Microsoft Azure, Microsoft Office 365, Dynamics 365, and Microsoft Power BI can help meet the stringent requirements of providing cloud services for financial services institutions.</span></span> <span data-ttu-id="15235-112">サポートの一環として、GLBA の要件に準拠するために役立つガイダンスが提供されています。これにより、セキュリティを維持し、無許可の使用を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="15235-112">As part of our support, we offer guidance to help you comply with the requirements of the GLBA by providing technical and organizational safeguards to help maintain security and prevent unauthorized usage.</span></span>

<span data-ttu-id="15235-113">Microsoft は、azure および office 365 サービスのリスク評価を効率的に行うために、 [azure](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=6b218946-c235-4234-9beb-d557e39a3f44&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides) と [office 365](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=55702ffd-c35a-4619-8722-ab71c0c02002&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides) の両方のリスク評価ツールを開発しています。</span><span class="sxs-lookup"><span data-stu-id="15235-113">Microsoft has developed risk assessment tools for both [Azure](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=6b218946-c235-4234-9beb-d557e39a3f44&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides) and [Office 365](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=55702ffd-c35a-4619-8722-ab71c0c02002&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides) to help you more efficiently conduct a risk assessment of Azure and Office 365 services.</span></span> <span data-ttu-id="15235-114">このツール (Excel スプレッドシート) は、GLBA を含む19個の情報セキュリティドメイン (セキュリティポリシー、リスク管理など) を機能させることができます (これには、Azure スプレッドシートおよび Office 365 スプレッドシートの列 R の列 R)。</span><span class="sxs-lookup"><span data-stu-id="15235-114">The tool (an Excel spreadsheet) features 19 information security domains (such as security policy and risk management) that track the requirements of financial services regulations and other relevant standards, including GLBA (in Column R in the Azure spreadsheet and Column Q in the Office 365 spreadsheet).</span></span> <span data-ttu-id="15235-115">このツールでは、Azure と Office 365 がクラウドサービスプロバイダーに適用される各要件を準拠させる方法について説明し、GLBA のセキュリティ要件を満たすために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="15235-115">The tools explain how Azure and Office 365 comply with each requirement applicable to cloud service providers and can help you meet GLBA security requirements.</span></span>

## <a name="promote-your-glba-compliance"></a><span data-ttu-id="15235-116">GLBA のコンプライアンスを促進する</span><span class="sxs-lookup"><span data-stu-id="15235-116">Promote your GLBA compliance</span></span>

- [<span data-ttu-id="15235-117">Azure 金融サービスクラウドリスク評価ツールをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="15235-117">Download the Azure Financial Services Cloud Risk Assessment Tool</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=6b218946-c235-4234-9beb-d557e39a3f44&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides)
- [<span data-ttu-id="15235-118">Office 365 Cloud リスク評価ツールをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="15235-118">Download the Office 365 Cloud Risk Assessment Tool</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=55702ffd-c35a-4619-8722-ab71c0c02002&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides)

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="15235-119">対象となる Microsoft のクラウド サービス</span><span class="sxs-lookup"><span data-stu-id="15235-119">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="15235-120">Azure</span><span class="sxs-lookup"><span data-stu-id="15235-120">Azure</span></span>](https://aka.ms/AzureCompliance)
- [<span data-ttu-id="15235-121">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="15235-121">Dynamics 365</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="15235-122">Intune</span><span class="sxs-lookup"><span data-stu-id="15235-122">Intune</span></span>
- [<span data-ttu-id="15235-123">Office 365</span><span class="sxs-lookup"><span data-stu-id="15235-123">Office 365</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- <span data-ttu-id="15235-124">Power BI クラウド サービス (スタンドアロン サービス、または Office 365 ブランド プランあるいはスイートに搭載されているサービス)</span><span class="sxs-lookup"><span data-stu-id="15235-124">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="15235-125">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="15235-125">Frequently asked questions</span></span>

<span data-ttu-id="15235-126">**金融機関が GLB Act に準拠している必要があるかどうかを確認する方法**</span><span class="sxs-lookup"><span data-stu-id="15235-126">**How do I know if my financial institution must comply with the GLB Act?**</span></span>

<span data-ttu-id="15235-127">FTC は、 [プライバシールールに含まれている](https://www.ftc.gov/tips-advice/business-center/guidance/how-comply-privacy-consumer-financial-information-rule-gramm#whois)GLB Act ページで、これを詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="15235-127">The FTC answers this in detail on its GLB Act page, [Who is covered by the privacy rule](https://www.ftc.gov/tips-advice/business-center/guidance/how-comply-privacy-consumer-financial-information-rule-gramm#whois)?</span></span>

## <a name="use-microsoft-compliance-manager-to-assess-your-risk"></a><span data-ttu-id="15235-128">Microsoft コンプライアンスマネージャーを使用してリスクを評価する</span><span class="sxs-lookup"><span data-stu-id="15235-128">Use Microsoft Compliance Manager to assess your risk</span></span>

<span data-ttu-id="15235-129">[Microsoft コンプライアンスマネージャー](compliance-manager.md) は、 [microsoft 365 コンプライアンスセンター](microsoft-365-compliance-center.md) の機能であり、組織のコンプライアンスの状況を理解し、リスクを軽減するためのアクションを実行するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="15235-129">[Microsoft Compliance Manager](compliance-manager.md) is a feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) to help you understand your organization's compliance posture and take actions to help reduce risks.</span></span> <span data-ttu-id="15235-130">コンプライアンスマネージャーには、この規制の評価を構築するためのプレミアムテンプレートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="15235-130">Compliance Manager offers a premium template for building an assessment for this regulation.</span></span> <span data-ttu-id="15235-131">[コンプライアンスマネージャー] の [ **評価テンプレート** ] ページでテンプレートを検索します。</span><span class="sxs-lookup"><span data-stu-id="15235-131">Find the template in the **assessment templates** page in Compliance Manager.</span></span> <span data-ttu-id="15235-132">[コンプライアンスマネージャーで評価を作成](compliance-manager-assessments.md)する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="15235-132">Learn how to [build assessments in Compliance Manager](compliance-manager-assessments.md).</span></span>

## <a name="resources"></a><span data-ttu-id="15235-133">リソース</span><span class="sxs-lookup"><span data-stu-id="15235-133">Resources</span></span>

- [<span data-ttu-id="15235-134">グラムリーチブライ-対象-なる Act</span><span class="sxs-lookup"><span data-stu-id="15235-134">Gramm-Leach-Bliley Act</span></span>](https://www.ftc.gov/tips-advice/business-center/privacy-and-security/gramm-leach-bliley-act)
- [<span data-ttu-id="15235-135">Azure 金融サービス クラウド リスク評価ツール</span><span class="sxs-lookup"><span data-stu-id="15235-135">Azure Financial Services Cloud Risk Assessment Tool</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=6b218946-c235-4234-9beb-d557e39a3f44&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides)
- [<span data-ttu-id="15235-136">Office 365 Cloud リスク評価ツール</span><span class="sxs-lookup"><span data-stu-id="15235-136">Office 365 Cloud Risk Assessment Tool</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=55702ffd-c35a-4619-8722-ab71c0c02002&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides)
- [<span data-ttu-id="15235-137">Microsoft Trust Center のコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="15235-137">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="other-microsoft-resources-for-financial-services"></a><span data-ttu-id="15235-138">金融サービス向けのその他の Microsoft リソース</span><span class="sxs-lookup"><span data-stu-id="15235-138">Other Microsoft resources for financial services</span></span>

- [<span data-ttu-id="15235-139">Microsoft 金融サービス コンプライアンス プログラム</span><span class="sxs-lookup"><span data-stu-id="15235-139">Microsoft Financial Services Compliance Program</span></span>](https://www.microsoft.com/download/details.aspx?id=55332)
- [<span data-ttu-id="15235-140">Azure における金融サービス コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="15235-140">Financial services compliance in Azure</span></span>](https://azure.microsoft.com/resources/videos/azurecon-2015-financial-services-compliance-in-azure/)
- [<span data-ttu-id="15235-141">Microsoft 法人向けクラウド サービスおよび金融サービス</span><span class="sxs-lookup"><span data-stu-id="15235-141">Microsoft business cloud services and financial services</span></span>](https://www.microsoft.com/trustcenter/cloudservices/financialservices)
- [<span data-ttu-id="15235-142">クラウド コンピューティングの共同責任</span><span class="sxs-lookup"><span data-stu-id="15235-142">Shared responsibilities for cloud computing</span></span>](https://aka.ms/sharedresponsibility)
