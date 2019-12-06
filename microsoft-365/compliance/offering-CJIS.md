---
title: 刑事司法 Information Services (CJIS) セキュリティポリシー
description: Microsoft government cloud service は、米国犯罪司法 Information Services セキュリティポリシーに準拠しています。
keywords: Microsoft 365、コンプライアンス、サービス
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
ms.openlocfilehash: 8d28327e4627351c27140e954c2fa26571d1689d
ms.sourcegitcommit: eb0f255baff1f2856621cbc64a3f34a04be37be3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "39860047"
---
# <a name="criminal-justice-information-services-cjis-security-policy"></a><span data-ttu-id="ec4cc-104">刑事司法 Information Services (CJIS) セキュリティポリシー</span><span class="sxs-lookup"><span data-stu-id="ec4cc-104">Criminal Justice Information Services (CJIS) Security Policy</span></span>

## <a name="cjis-overview"></a><span data-ttu-id="ec4cc-105">CJIS の概要</span><span class="sxs-lookup"><span data-stu-id="ec4cc-105">CJIS overview</span></span>

<span data-ttu-id="ec4cc-106">米国連邦政府機関の調査 (FBI) の犯罪司法情報サービス (CJIS) 部門では、州、地域、および連邦法執行機関と、犯罪司法機関が犯罪司法情報 (CJI) (指紋など) にアクセスできるようになります。レコードと犯罪履歴。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-106">The Criminal Justice Information Services (CJIS) Division of the US Federal Bureau of Investigation (FBI) gives state, local, and federal law enforcement and criminal justice agencies access to criminal justice information (CJI) — for example, fingerprint records and criminal histories.</span></span> <span data-ttu-id="ec4cc-107">米国の司法当局およびその他の政府機関は、CJI の転送、保存、処理にクラウドサービスを使用することが、CJI を保護するための最小のセキュリティ要件と制御を確立する[Cjis セキュリティポリシー](https://aka.ms/cjis-security-policy)に準拠していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-107">Law enforcement and other government agencies in the United States must ensure that their use of cloud services for the transmission, storage, or processing of CJI complies with the [CJIS Security Policy](https://aka.ms/cjis-security-policy), which establishes minimum security requirements and controls to safeguard CJI.</span></span>

<span data-ttu-id="ec4cc-108">CJIS のセキュリティポリシーには、presidential と FBI のディレクティブ、連邦法、犯罪者の勧告ポリシーボードの決定、および米国標準技術局 (NIST) のガイダンスが統合されています。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-108">The CJIS Security Policy integrates presidential and FBI directives, federal laws, and the criminal justice community’s Advisory Policy Board decisions, along with guidance from the National Institute of Standards and Technology (NIST).</span></span> <span data-ttu-id="ec4cc-109">ポリシーは定期的に更新され、セキュリティ要件の変化を反映しています。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-109">The Policy is periodically updated to reflect evolving security requirements.</span></span>

<span data-ttu-id="ec4cc-110">CJIS のセキュリティポリシーでは、クラウドサービスプロバイダーなどのプライベート請負業者が、クラウドサービスの使用を CJIS の要件と一致できるかどうかを判断するために評価する必要がある13の領域を定義します。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-110">The CJIS Security Policy defines 13 areas that private contractors such as cloud service providers must evaluate to determine if their use of cloud services can be consistent with CJIS requirements.</span></span> <span data-ttu-id="ec4cc-111">これらの領域は、NIST 800-53 に密接に対応しています。これは、連邦リスクおよび承認管理プログラム ([Fedramp](offering-FedRAMP.md)) の基礎でもあります。これは、マイクロソフトが政府機関向けクラウド製品の認定を受けているプログラムです。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-111">These areas correspond closely to NIST 800-53, which is also the basis for the Federal Risk and Authorization Management Program ([FedRAMP](offering-FedRAMP.md)), a program under which Microsoft has been certified for its Government Cloud offerings.</span></span>

<span data-ttu-id="ec4cc-112">さらに、CJI を処理するすべてのプライベート請負業者は、CJI セキュリティポリシーに必要なセキュリティと機密性を確保するために、米弁護士の一般に承認された一様な契約書である CJIS のセキュリティ補遺に署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-112">In addition, all private contractors who process CJI must sign the CJIS Security Addendum, a uniform agreement approved by the US Attorney General that helps ensure the security and confidentiality of CJI required by the Security Policy.</span></span> <span data-ttu-id="ec4cc-113">また、連邦および州の法律、規制、および標準に準拠したセキュリティプログラムを維持するために請負業者にもコミットし、CJI の使用を政府機関が提供する目的に限定します。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-113">It also commits the contractor to maintaining a security program consistent with federal and state laws, regulations, and standards, and limits the use of CJI to the purposes for which a government agency provided it.</span></span>

## <a name="microsoft-and-cjis-security-policy"></a><span data-ttu-id="ec4cc-114">Microsoft および CJIS のセキュリティポリシー</span><span class="sxs-lookup"><span data-stu-id="ec4cc-114">Microsoft and CJIS Security Policy</span></span>

<span data-ttu-id="ec4cc-115">Microsoft は、CJIS の情報契約がある状態で CJIS のセキュリティ補遺に署名します。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-115">Microsoft signs the CJIS Security Addendum in states with CJIS Information Agreements.</span></span> <span data-ttu-id="ec4cc-116">これにより、Microsoft のクラウドセキュリティ統制によって、データのライフサイクル全体を保護し、アクセス権を持つ運用担当者が適切なバックグラウンド審査を確実に行うことができるようになります。CJI.</span><span class="sxs-lookup"><span data-stu-id="ec4cc-116">These tell state law enforcement authorities responsible for compliance with CJIS Security Policy how Microsoft's cloud security controls help protect the full lifecycle of data and ensure appropriate background screening of operating personnel with access to CJI.</span></span> <span data-ttu-id="ec4cc-117">Microsoft は、州政体を使用して CJIS 情報契約に入ることを続けます。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-117">Microsoft continues to work with state governments to enter into CJIS Information Agreements.</span></span>

<span data-ttu-id="ec4cc-118">Microsoft では、microsoft Azure Government、Microsoft Office 365 米国政府、および Microsoft Dynamics 365 米国政府の運用ポリシーと手順を評価しており、FBI への対応のために該当するサービス契約での機能を証明しています。スコープ内サービスを使用するための要件。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-118">Microsoft has assessed the operational policies and procedures of Microsoft Azure Government, Microsoft Office 365 U.S. Government, and Microsoft Dynamics 365 U.S. Government, and will attest to their ability in the applicable services agreements to meet FBI requirements for the use of in-scope services.</span></span>

<span data-ttu-id="ec4cc-119">Microsoft クラウドでの CJIS セキュリティポリシーの利点について説明します。「[犯罪調査による犯罪調査のクリア](https://customers.microsoft.com/story/genetec)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-119">Learn about the benefits of CJIS Security policy on the Microsoft Cloud: [Read how Genetec cleared criminal investigations](https://customers.microsoft.com/story/genetec)</span></span>

<span data-ttu-id="ec4cc-120">Azure セキュリティおよびコンプライアンスブループリントを使用して CJIS のセキュリティポリシーを促進する方法について説明します。 [Microsoft Government Cloud Services 用の cjis 実装ガイドラインをダウンロード](https://gallery.technet.microsoft.com/CJIS-Implementation-62af7c27)する</span><span class="sxs-lookup"><span data-stu-id="ec4cc-120">Learn how to accelerate your CJIS Security policy with our Azure Security and Compliance Blueprint: [Download the CJIS implementation guidelines for Microsoft Government Cloud Services](https://gallery.technet.microsoft.com/CJIS-Implementation-62af7c27)</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="ec4cc-121">対象となる Microsoft のクラウド サービス</span><span class="sxs-lookup"><span data-stu-id="ec4cc-121">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="ec4cc-122">Azure Government</span><span class="sxs-lookup"><span data-stu-id="ec4cc-122">Azure Government</span></span>](https://aka.ms/AzureCompliance)
- [<span data-ttu-id="ec4cc-123">Dynamics 365 米国政府</span><span class="sxs-lookup"><span data-stu-id="ec4cc-123">Dynamics 365 U.S. Government</span></span>](https://aka.ms/d365-compliance-list)
- [<span data-ttu-id="ec4cc-124">Office 365 米国政府機関</span><span class="sxs-lookup"><span data-stu-id="ec4cc-124">Office 365 U.S. Government</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- <span data-ttu-id="ec4cc-125">Power BI クラウド サービス (スタンドアロン サービス、または Office 365 ブランド プランあるいはスイートに搭載されているサービス)</span><span class="sxs-lookup"><span data-stu-id="ec4cc-125">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="ec4cc-126">監査、レポート、証明書</span><span class="sxs-lookup"><span data-stu-id="ec4cc-126">Audits, reports, and certificates</span></span>

<span data-ttu-id="ec4cc-127">FBI では、CJIS 要件に対する Microsoft コンプライアンスの証明書は提供されません。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-127">The FBI does not offer certification of Microsoft compliance with CJIS requirements.</span></span> <span data-ttu-id="ec4cc-128">その代わりに、microsoft の構成証明書は、microsoft と州の CJIS の各権限、Microsoft とお客様との間の契約に含まれています。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-128">Instead, a Microsoft attestation is included in agreements between Microsoft and a state’s CJIS authority, and between Microsoft and its customers.</span></span>

[<span data-ttu-id="ec4cc-129">Microsoft CJIS のクラウドの要件</span><span class="sxs-lookup"><span data-stu-id="ec4cc-129">Microsoft CJIS Cloud Requirements</span></span>](https://aka.ms/MicrosoftCJISCloudRequirements)

## <a name="cjis-status-in-the-united-states-current-as-of-9232019"></a><span data-ttu-id="ec4cc-130">米国での CJIS の状態 (9/23/2019 の時点での現在の状態)</span><span class="sxs-lookup"><span data-stu-id="ec4cc-130">CJIS status in the United States (current as of 9/23/2019)</span></span>

<span data-ttu-id="ec4cc-131">37の状態と、管理契約を含むコロンビアの地域。グリーンのマップで強調表示されているものは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-131">37 states and the District of Columbia with management agreements, highlighted on the map in green include:</span></span>

<span data-ttu-id="ec4cc-132">Alabama、アラスカ、Arkansas、アリゾナ、カリフォルニア、コロラド、フロリダ、ジョージア、ジョージア、イリノイ、インディアナ、アイオワ、カンザス、ケンタッキー、ミシガン、ミネソタ、モンタナ、ネバダ、、北ジョージア、オクラホマ、オレゴン、、北カロライナ、、オレゴン、ペンシルバニア、ロードアイランド、サウスカロライナ、テネシー、テキサス、ユタ、バーモント、バージニア、ワシントン、ワシントン D.C.、West バージニア、ウィスコンシン。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-132">Alabama, Alaska, Arkansas, Arizona, California, Colorado, Florida, Georgia, Hawaii, Illinois, Indiana, Iowa, Kansas, Kentucky, Maine, Massachusetts, Michigan, Minnesota, Missouri, Montana, New Jersey, New York, Nevada, North Carolina, Oklahoma, Oregon, Pennsylvania, Rhode Island, South Carolina, Tennessee, Texas, Utah, Vermont, Virginia, Washington, Washington D.C., West Virginia, Wisconsin.</span></span>

<span data-ttu-id="ec4cc-133">適用可能な CJIS 規制統制に準拠した Microsoft のコミットメントにより、犯罪司法機関はクラウドベースのソリューションを実装し、CJIS Security Policy v2.0 に準拠することができます。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-133">Microsoft's commitment to meeting the applicable CJIS regulatory controls allows Criminal Justice organizations to implement cloud-based solutions and be compliant with CJIS Security Policy V5.8.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="ec4cc-134">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="ec4cc-134">Frequently asked questions</span></span>

<span data-ttu-id="ec4cc-135">**コンプライアンス情報を要求するには、どうすればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="ec4cc-135">**Where can I request compliance information?**</span></span>

<span data-ttu-id="ec4cc-136">関心がある管轄権については、Microsoft アカウント担当者にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-136">Contact your Microsoft account representative for information on the jurisdiction you are interested in.</span></span> <span data-ttu-id="ec4cc-137">現在<cjis@microsoft.com>どのサービスがどの状態で利用可能であるかについての情報を連絡します。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-137">Contact <cjis@microsoft.com> for information on which services are currently available in which states.</span></span>

<span data-ttu-id="ec4cc-138">**クラウドサービスが自分の状態の要件を満たすことができることを Microsoft がどのように示していますか?**</span><span class="sxs-lookup"><span data-stu-id="ec4cc-138">**How does Microsoft demonstrate that its cloud services enable compliance with my state’s requirements?**</span></span>

<span data-ttu-id="ec4cc-139">Microsoft は、状態 CJIS Systems Agency (CSA) を使用して、情報契約に署名します。状態の CSA からコピーを要求することができます。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-139">Microsoft signs an Information Agreement with a state CJIS Systems Agency (CSA); you may request a copy from your state’s CSA.</span></span> <span data-ttu-id="ec4cc-140">さらに、Microsoft は、お客様に詳細なセキュリティ、プライバシー、コンプライアンス情報を提供しています。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-140">In addition, Microsoft provides customers with in-depth security, privacy, and compliance information.</span></span> <span data-ttu-id="ec4cc-141">お客様は、独立した監査者によって提供されるセキュリティおよびコンプライアンスレポートを見直して、Microsoft が関連する監査範囲に適したセキュリティコントロール (ISO 27001 など) を実装しているかどうかを検証することもできます。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-141">Customers may also review security and compliance reports prepared by independent auditors so they can validate that Microsoft has implemented security controls (such as ISO 27001) appropriate to the relevant audit scope.</span></span>

<span data-ttu-id="ec4cc-142">**エージェンシーのコンプライアンスの取り組みはどこで開始しますか?**</span><span class="sxs-lookup"><span data-stu-id="ec4cc-142">**Where do I start with my agency’s compliance effort?**</span></span>

<span data-ttu-id="ec4cc-143">[Cjis セキュリティポリシー](https://aka.ms/cjis-security-policy)には、CJI を保護するためにエージェンシーが講じる必要のある対策が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-143">[CJIS Security Policy](https://aka.ms/cjis-security-policy) covers the precautions that your agency must take to protect CJI.</span></span> <span data-ttu-id="ec4cc-144">さらに、Microsoft アカウント担当者は、管轄区の要件を熟知したユーザーと連絡を取ります。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-144">In addition, your Microsoft account representative can put you in touch with those familiar with the requirements of your jurisdiction</span></span>

## <a name="resources"></a><span data-ttu-id="ec4cc-145">リソース</span><span class="sxs-lookup"><span data-stu-id="ec4cc-145">Resources</span></span>

- [<span data-ttu-id="ec4cc-146">犯罪司法情報サービス</span><span class="sxs-lookup"><span data-stu-id="ec4cc-146">Criminal Justice Information Services</span></span>](https://aka.ms/cjis)
- [<span data-ttu-id="ec4cc-147">CJIS セキュリティポリシー</span><span class="sxs-lookup"><span data-stu-id="ec4cc-147">CJIS Security Policy</span></span>](https://aka.ms/cjis-security-policy)
- [<span data-ttu-id="ec4cc-148">CJIS セキュリティポリシーバージョン 5.3 backgrounder</span><span class="sxs-lookup"><span data-stu-id="ec4cc-148">CJIS security policy version 5.3 backgrounder</span></span>](https://aka.ms/cjis-backgrounder)
- [<span data-ttu-id="ec4cc-149">Azure Government の CJIS 実装ガイドライン</span><span class="sxs-lookup"><span data-stu-id="ec4cc-149">CJIS implementation guidelines for Azure Government</span></span>](https://aka.ms/cjisimplementationguidelines)
- [<span data-ttu-id="ec4cc-150">Microsoft Common Controls Hub コンプライアンス フレームワーク</span><span class="sxs-lookup"><span data-stu-id="ec4cc-150">Microsoft Common Controls Hub Compliance Framework</span></span>](https://www.microsoft.com/trustcenter/common-controls-hub)
- [<span data-ttu-id="ec4cc-151">Microsoft Government クラウド</span><span class="sxs-lookup"><span data-stu-id="ec4cc-151">Microsoft Government Cloud</span></span>](https://go.microsoft.com/fwlink/?linkid=2087246)
- [<span data-ttu-id="ec4cc-152">Microsoft Trust Center のコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="ec4cc-152">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="ec4cc-153">サービスの背景資料をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="ec4cc-153">Download the offering backgrounder</span></span>

<span data-ttu-id="ec4cc-154">このサービスに関する背景資料が必要ですか?</span><span class="sxs-lookup"><span data-stu-id="ec4cc-154">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="ec4cc-155">[PDF](https://download.microsoft.com/download/4/D/0/4D008840-B8C4-480B-ACD1-D55CB34AD6BC/CJIS_Compliance_Backgrounder.pdf) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="ec4cc-155">Download the [PDF](https://download.microsoft.com/download/4/D/0/4D008840-B8C4-480B-ACD1-D55CB34AD6BC/CJIS_Compliance_Backgrounder.pdf).</span></span>
