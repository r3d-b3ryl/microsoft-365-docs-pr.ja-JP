---
title: Contoso Corporation の情報保護
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 社が Microsoft 365 の情報保護機能を使用して、クラウド内のデジタルアセットをセキュリティで保護する方法について説明します。
ms.openlocfilehash: 1966fdec3de246ca54fd99ab018485b9ee817281
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399243"
---
# <a name="information-protection-for-the-contoso-corporation"></a><span data-ttu-id="61f32-103">Contoso Corporation の情報保護</span><span class="sxs-lookup"><span data-stu-id="61f32-103">Information protection for the Contoso Corporation</span></span>

<span data-ttu-id="61f32-p101">Contoso 社では、情報のセキュリティと保護を重視しています。たとえば、製品のデザインや独自の製造技術を説明する知的財産の漏洩や破壊は、それらを競争面で不利な立場に置くことになります。</span><span class="sxs-lookup"><span data-stu-id="61f32-p101">Contoso is serious about their information security and protection. For example, leakage or destruction of their intellectual property describing product designs and proprietary manufacturing techniques would place them at a competitive disadvantage.</span></span>

<span data-ttu-id="61f32-106">機密扱いの最も貴重なデジタル資産をクラウドに移行する前に、社内の情報の分類と保護要件がサポートされており、Microsoft 365 for enterprise のクラウドベースのサービスに実装されていることを確認しました。</span><span class="sxs-lookup"><span data-stu-id="61f32-106">Before moving their sensitive and most valuable digital assets to the cloud, they made sure that their on-premises information classification and protection requirements were supported and implemented in the cloud-based services of Microsoft 365 for enterprise.</span></span>

## <a name="contosos-data-security-classification"></a><span data-ttu-id="61f32-107">Contoso 社のデータ セキュリティの分類</span><span class="sxs-lookup"><span data-stu-id="61f32-107">Contoso's data security classification</span></span>

<span data-ttu-id="61f32-108">Contoso 社では自社のデータの分析を行い、次に示すレベルを決定しました。</span><span class="sxs-lookup"><span data-stu-id="61f32-108">Contoso performed an analysis of their data and determined the following levels.</span></span>

| <span data-ttu-id="61f32-109">レベル 1: ベースライン</span><span class="sxs-lookup"><span data-stu-id="61f32-109">Level 1: Baseline</span></span> | <span data-ttu-id="61f32-110">レベル 2: 機密</span><span class="sxs-lookup"><span data-stu-id="61f32-110">Level 2: Sensitive</span></span> | <span data-ttu-id="61f32-111">レベル 3: 厳しく規制</span><span class="sxs-lookup"><span data-stu-id="61f32-111">Level 3: Highly regulated</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="61f32-112">データは暗号化され、認証されたユーザーのみが使用できます。</span><span class="sxs-lookup"><span data-stu-id="61f32-112">Data is encrypted and available only to authenticated users.</span></span> <BR> <BR> <span data-ttu-id="61f32-p102">オンプレミスとクラウドベースのストレージおよびワークロードに格納されているすべてのデータに対して提供されます。データは、サービス内に存在し、サービスとクライアントデバイス間で転送される間は暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="61f32-p102">Provided for all data stored on-premises and in cloud-based storage and workloads. Data is encrypted while it resides in the service and in transit between the service and client devices.</span></span> <BR><BR> <span data-ttu-id="61f32-115">レベル 1 のデータの例には、通常のビジネス通信 (電子メール) や、管理、販売、およびサポート ワーカー用のファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="61f32-115">Examples of Level 1 data are normal business communications (email) and files for administrative, sales, and support workers.</span></span> | <span data-ttu-id="61f32-116">レベル 1 以上の強力な認証とデータ損失保護。</span><span class="sxs-lookup"><span data-stu-id="61f32-116">Level 1 plus strong authentication and data loss protection.</span></span> <BR> <BR> <span data-ttu-id="61f32-117">強力な認証には、SMS 検証を使用した Azure 多要素認証 (MFA) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="61f32-117">Strong authentication includes Azure Multi-Factor Authentication (MFA) with SMS validation.</span></span> <span data-ttu-id="61f32-118">データ損失の防止により、機密情報または重要な情報が Microsoft クラウドの外部に漏出しないようにします。</span><span class="sxs-lookup"><span data-stu-id="61f32-118">Data loss prevention ensures that sensitive or critical information does not travel outside the Microsoft cloud.</span></span> <BR><BR> <span data-ttu-id="61f32-119">レベル 2 のデータの例には、財務情報や法的情報、新製品の研究開発データがあります。</span><span class="sxs-lookup"><span data-stu-id="61f32-119">Examples of Level 2 data are financial and legal information and research and development data for new products.</span></span> | <span data-ttu-id="61f32-120">レベル 2 以上の最高レベルの暗号化、認証、監査。</span><span class="sxs-lookup"><span data-stu-id="61f32-120">Level 2 plus the highest levels of encryption, authentication, and auditing.</span></span> <BR> <BR>  <span data-ttu-id="61f32-121">保存データおよびクラウド内のデータに対する最高レベルの暗号化。地域の規制に準拠し、スマート カードや詳細な監査と警告を使用する MFA と組み合わされています。</span><span class="sxs-lookup"><span data-stu-id="61f32-121">The highest levels of encryption for data at rest and in the cloud, compliant with regional regulations, combined with MFA with smart cards and granular auditing and alerting.</span></span> <BR> <BR> <span data-ttu-id="61f32-122">レベル 3 のデータの例には、顧客およびパートナーの個人を特定できる情報、製品のエンジニアリング仕様、および独自の製造技術があります。</span><span class="sxs-lookup"><span data-stu-id="61f32-122">Examples of Level 3 data are customer and partner personally identifiable information, product engineering specifications, and proprietary manufacturing techniques.</span></span>  |
||||

## <a name="contosos-information-policies"></a><span data-ttu-id="61f32-123">Contoso 社の情報ポリシー</span><span class="sxs-lookup"><span data-stu-id="61f32-123">Contoso's information policies</span></span>
<span data-ttu-id="61f32-124">次の表に、Contoso 社の情報ポリシーを示します。</span><span class="sxs-lookup"><span data-stu-id="61f32-124">The following table lists Contoso's information policies.</span></span>


| <span data-ttu-id="61f32-125">値</span><span class="sxs-lookup"><span data-stu-id="61f32-125">Value</span></span> | <span data-ttu-id="61f32-126">Access</span><span class="sxs-lookup"><span data-stu-id="61f32-126">Access</span></span> | <span data-ttu-id="61f32-127">データ保存期間</span><span class="sxs-lookup"><span data-stu-id="61f32-127">Data retention</span></span> | <span data-ttu-id="61f32-128">情報保護</span><span class="sxs-lookup"><span data-stu-id="61f32-128">Information protection</span></span> |
|:-------|:-----|:-----|:-----|
| <span data-ttu-id="61f32-129">低いビジネス価値 (レベル 1: ベースライン)</span><span class="sxs-lookup"><span data-stu-id="61f32-129">Low business value (Level 1: Baseline)</span></span> | <span data-ttu-id="61f32-130">すべてのユーザーに対してアクセスを許可</span><span class="sxs-lookup"><span data-stu-id="61f32-130">Allow access to all</span></span>  | <span data-ttu-id="61f32-131">6 か月</span><span class="sxs-lookup"><span data-stu-id="61f32-131">6 months</span></span> | <span data-ttu-id="61f32-132">暗号化を使用します。</span><span class="sxs-lookup"><span data-stu-id="61f32-132">Use encryption.</span></span> |
| <span data-ttu-id="61f32-133">中程度のビジネス価値 (レベル 2: 機密)</span><span class="sxs-lookup"><span data-stu-id="61f32-133">Medium business value (Level 2: Sensitive)</span></span> | <span data-ttu-id="61f32-134">Contoso 社の従業員、下請業者、パートナーに対してアクセスを許可</span><span class="sxs-lookup"><span data-stu-id="61f32-134">Allow access to Contoso employees, subcontractors, and partners</span></span> <BR> <BR> <span data-ttu-id="61f32-135">MFA、トランスポート層セキュリティ (TLS)、およびモバイル アプリケーション管理 (MAM) を使用します。</span><span class="sxs-lookup"><span data-stu-id="61f32-135">Use MFA, Transport Layer Security (TLS), and Mobile Application Management (MAM).</span></span> | <span data-ttu-id="61f32-136">2 年</span><span class="sxs-lookup"><span data-stu-id="61f32-136">2 years</span></span>  | <span data-ttu-id="61f32-137">データ整合性のためにハッシュ値を使用します。</span><span class="sxs-lookup"><span data-stu-id="61f32-137">Use hash values for data integrity.</span></span>  |
| <span data-ttu-id="61f32-138">高度なビジネス価値 (レベル 3: 厳しく規制)</span><span class="sxs-lookup"><span data-stu-id="61f32-138">High business value (Level 3: Highly regulated)</span></span> | <span data-ttu-id="61f32-139">エグゼクティブ、およびエンジニアリングと製造の潜在顧客に対してアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="61f32-139">Allow access to executives and leads in engineering and manufacturing.</span></span> <BR> <BR> <span data-ttu-id="61f32-140">管理されたネットワーク デバイスのみの Rights Management System (RMS) です。</span><span class="sxs-lookup"><span data-stu-id="61f32-140">Rights Management System (RMS) with managed network devices only.</span></span>  | <span data-ttu-id="61f32-141">7 年</span><span class="sxs-lookup"><span data-stu-id="61f32-141">7 years</span></span>  | <span data-ttu-id="61f32-142">否認防止のためにデジタル署名を使用します。</span><span class="sxs-lookup"><span data-stu-id="61f32-142">Use digital signatures for non-repudiation.</span></span>  |
|||||

## <a name="contosos-path-to-information-protection-with-microsoft-365-for-enterprise"></a><span data-ttu-id="61f32-143">Microsoft 365 for enterprise を使用した Contoso 社の情報保護へのパス</span><span class="sxs-lookup"><span data-stu-id="61f32-143">Contoso’s path to information protection with Microsoft 365 for enterprise</span></span>

<span data-ttu-id="61f32-144">Contoso 社は、次の手順を使用して、情報保護要件に応じて Microsoft 365 for enterprise を準備していました。</span><span class="sxs-lookup"><span data-stu-id="61f32-144">Contoso used the following steps to prepare Microsoft 365 for enterprise for their information protection requirements:</span></span>

1. <span data-ttu-id="61f32-145">保護する情報を特定した</span><span class="sxs-lookup"><span data-stu-id="61f32-145">Identified what information to protect</span></span>

   <span data-ttu-id="61f32-146">Contoso 社は、オンプレミスの SharePoint サイトとファイル共有にある既存のデジタル資産を広範囲にわたって再調査して、それぞれを分類しました。</span><span class="sxs-lookup"><span data-stu-id="61f32-146">Contoso did an extensive review of their existing digital assets located on on-premises SharePoint sites and file shares and classified each one.</span></span>

2. <span data-ttu-id="61f32-147">各データ レベルに応じてアクセス ポリシー、保持ポリシー、情報保護ポリシーを決定した</span><span class="sxs-lookup"><span data-stu-id="61f32-147">Determined access, retention, and information protection policies for data levels</span></span>

   <span data-ttu-id="61f32-148">データ レベルに基づいて、Contoso 社は詳細なポリシー要件を決定しました。この要件は、クラウドへの移行時に既存のデジタル資産を保護するために使用されました。</span><span class="sxs-lookup"><span data-stu-id="61f32-148">Based on the data levels, Contoso determined detailed policy requirements, which were used to protect existing digital assets as they were moved to the cloud.</span></span>

3. <span data-ttu-id="61f32-149">さまざまな情報のレベルに応じた機密ラベルとその設定を作成した</span><span class="sxs-lookup"><span data-stu-id="61f32-149">Created sensitivity labels and their settings for the different levels of information</span></span>

   <span data-ttu-id="61f32-150">Contoso 社では、データのレベルに応じた機密ラベルを作成しました。「厳しく規制」のラベルで、暗号化、アクセス許可、透かしなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="61f32-150">Contoso created sensitivity labels for their data levels, with their highly regulated label that includes encryption, permissions, and watermarks.</span></span>

4.  <span data-ttu-id="61f32-151">オンプレミスの SharePoint サイトとファイル共有のデータを新しい SharePoint サイトに移動した</span><span class="sxs-lookup"><span data-stu-id="61f32-151">Moved data from on-premises SharePoint sites and file shares to their new SharePoint sites</span></span>

    <span data-ttu-id="61f32-152">新しい SharePoint サイトに移行したファイルには、そのサイトに割り当てられた既定の保持ラベルを継承させました。</span><span class="sxs-lookup"><span data-stu-id="61f32-152">The files migrated to the new SharePoint sites inherited the default retention labels assigned to the site.</span></span>

5.  <span data-ttu-id="61f32-153">新しいドキュメントに機密ラベルを使用する方法、新しい SharePoint サイトの作成時に Contoso 社の IT 部門と応対する方法、およびデジタル資産は必ず SharePoint サイトに保管することについて従業員を教育しました</span><span class="sxs-lookup"><span data-stu-id="61f32-153">Trained employees on how to use sensitivity labels for new documents, how to interact with Contoso IT when creating new SharePoint sites, and to always store digital assets on SharePoint sites</span></span>

    <span data-ttu-id="61f32-154">クラウドに向けた情報保護の変化で最も難しい部分であると考えられることから、Contoso 社の IT 部門と経営陣は、クラウド上のデジタル資産には必ずラベルを付けて保存し、オンプレミスのファイル共有を控え、サード パーティのクラウド ストレージ サービスや USB ドライブは決して使用しないように、組織の従業員の情報保管に関する悪習慣を改めることが必要でした。</span><span class="sxs-lookup"><span data-stu-id="61f32-154">Considered the hardest part of the information protection transition for the cloud, Contoso IT and management needed to change the bad information storage habits of the organization’s employees to always label and store their digital assets in the cloud, refrain from using on-premises file shares, and never use third-party cloud storage services or USB drives.</span></span>

## <a name="conditional-access-policies-for-information-protection"></a><span data-ttu-id="61f32-155">情報保護のための条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="61f32-155">Conditional Access policies for information protection</span></span>

<span data-ttu-id="61f32-156">ID とモバイル デバイスの管理インフラストラクチャと共に、Exchange Online と SharePoint のロールアウトの一環として、Contoso 社は、次に示す条件付きアクセス ポリシーのセットを構成して、そのポリシーを該当するグループに適用しました。</span><span class="sxs-lookup"><span data-stu-id="61f32-156">In conjunction with their identity and mobile device management infrastructure and as part of their rollout of Exchange Online and SharePoint, Contoso configured the following set of Conditional Access policies and applied them to the appropriate groups:</span></span>

- [<span data-ttu-id="61f32-157">デバイスで管理されるアプリケーション アクセスと管理されないアプリケーション アクセスのポリシー</span><span class="sxs-lookup"><span data-stu-id="61f32-157">Managed and unmanaged application access on devices policies</span></span>](../security/office-365-security/identity-access-policies.md)
- [<span data-ttu-id="61f32-158">Exchange Online アクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="61f32-158">Exchange Online access policies</span></span>](../security/office-365-security/secure-email-recommended-policies.md)
- [<span data-ttu-id="61f32-159">SharePoint アクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="61f32-159">SharePoint access policies</span></span>](../security/office-365-security/sharepoint-file-access-policies.md)

<span data-ttu-id="61f32-160">以下は、Contoso 社の情報保護に応じた結果としてのポリシーのセットです。</span><span class="sxs-lookup"><span data-stu-id="61f32-160">Here is Contoso's resulting set of policies for information protection.</span></span>

![デバイス、Exchange Online、および SharePoint の条件付きアクセス ポリシー](../media/contoso-info-protect/contoso-info-protect-fig1.png)

>[!Note]
><span data-ttu-id="61f32-162">Contoso 社は、ID とサインイン用に追加の条件付きアクセス ポリシーも構成しました。</span><span class="sxs-lookup"><span data-stu-id="61f32-162">Contoso also configured additional Conditional Access policies for identity and sign-in.</span></span> <span data-ttu-id="61f32-163">「[Contoso 社の ID](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61f32-163">See [Identity for the Contoso Corporation](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span></span>
>

<span data-ttu-id="61f32-164">これらのポリシーでは、次のことを確実にします。</span><span class="sxs-lookup"><span data-stu-id="61f32-164">These policies ensure that:</span></span>

- <span data-ttu-id="61f32-165">許可されるアプリと、そのアプリで組織のデータに対して実行できる操作は、アプリ保護ポリシーによって定義される。</span><span class="sxs-lookup"><span data-stu-id="61f32-165">Apps are allowed and the actions they can take with your organization data are defined by app protection policies.</span></span>
- <span data-ttu-id="61f32-166">PC とモバイル デバイスが必ず準拠している。</span><span class="sxs-lookup"><span data-stu-id="61f32-166">PCs and mobile devices must be compliant.</span></span>
- <span data-ttu-id="61f32-167">Exchange Online では、Exchange Online の Office 365 message encryption (OME) を使用します。</span><span class="sxs-lookup"><span data-stu-id="61f32-167">Exchange Online uses Office 365 message encryption (OME) for Exchange Online.</span></span>
- <span data-ttu-id="61f32-168">SharePoint は、アプリによって適用される制限を使用する。</span><span class="sxs-lookup"><span data-stu-id="61f32-168">SharePoint uses app enforced restrictions.</span></span>
- <span data-ttu-id="61f32-169">SharePoint は、ブラウザー専用のアクセスにアクセス制御ポリシーを使用して、管理されていないデバイスのアクセスはブロックする。</span><span class="sxs-lookup"><span data-stu-id="61f32-169">SharePoint uses access control policies for browser-only access and to block access for unmanaged devices.</span></span>

## <a name="mapping-microsoft-365-for-enterprise-features-to-contosos-data-levels"></a><span data-ttu-id="61f32-170">エンタープライズ機能に関する Microsoft 365 の Contoso 社のデータレベルへのマッピング</span><span class="sxs-lookup"><span data-stu-id="61f32-170">Mapping Microsoft 365 for enterprise features to Contoso's data levels</span></span>

<span data-ttu-id="61f32-171">次の表では、Contoso 社のデータレベルを、Microsoft 365 for enterprise の情報保護機能にマッピングします。</span><span class="sxs-lookup"><span data-stu-id="61f32-171">The following table maps Contoso's data levels to information protection features in Microsoft 365 for enterprise.</span></span>

| <span data-ttu-id="61f32-172">レベル</span><span class="sxs-lookup"><span data-stu-id="61f32-172">Level</span></span> | <span data-ttu-id="61f32-173">Microsoft 365 クラウドサービス</span><span class="sxs-lookup"><span data-stu-id="61f32-173">Microsoft 365 cloud services</span></span> | <span data-ttu-id="61f32-174">Windows 10 および Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="61f32-174">Windows 10 and Microsoft 365 Apps for enterprise</span></span> | <span data-ttu-id="61f32-175">セキュリティとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="61f32-175">Security and compliance</span></span> |
|:-------|:-----|:-----|:-----|
| <span data-ttu-id="61f32-176">レベル 1: ベースライン</span><span class="sxs-lookup"><span data-stu-id="61f32-176">Level 1: Baseline</span></span>  | <span data-ttu-id="61f32-177">SharePoint および Exchange Online の条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="61f32-177">SharePoint and Exchange Online Conditional Access policies</span></span> <BR> <span data-ttu-id="61f32-178">SharePoint サイトのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="61f32-178">Permissions on SharePoint sites</span></span> | <span data-ttu-id="61f32-179">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="61f32-179">Sensitivity labels</span></span> <BR> <span data-ttu-id="61f32-180">BitLocker</span><span class="sxs-lookup"><span data-stu-id="61f32-180">BitLocker</span></span> <BR> <span data-ttu-id="61f32-181">Windows 情報保護</span><span class="sxs-lookup"><span data-stu-id="61f32-181">Windows Information Protection</span></span> | <span data-ttu-id="61f32-182">デバイスの条件付きアクセス ポリシーとモバイル アプリケーション管理ポリシー</span><span class="sxs-lookup"><span data-stu-id="61f32-182">Device Conditional Access policies and Mobile Application Management policies</span></span> |
| <span data-ttu-id="61f32-183">レベル 2: 機密</span><span class="sxs-lookup"><span data-stu-id="61f32-183">Level 2: Sensitive</span></span> | <span data-ttu-id="61f32-184">レベル 1 プラス:</span><span class="sxs-lookup"><span data-stu-id="61f32-184">Level 1 plus:</span></span> <BR> <BR> <span data-ttu-id="61f32-185">秘密度ラベル</span><span class="sxs-lookup"><span data-stu-id="61f32-185">Sensitivity labels</span></span> <BR> <span data-ttu-id="61f32-186">SharePoint サイトの Microsoft 365 保持ラベル</span><span class="sxs-lookup"><span data-stu-id="61f32-186">Microsoft 365 retention labels on SharePoint sites</span></span> <BR> <span data-ttu-id="61f32-187">SharePoint および Exchange Online 用のデータ損失防止</span><span class="sxs-lookup"><span data-stu-id="61f32-187">Data Loss Prevention for SharePoint and Exchange Online</span></span> <BR> <span data-ttu-id="61f32-188">分離した SharePoint サイト</span><span class="sxs-lookup"><span data-stu-id="61f32-188">Isolated SharePoint sites</span></span>  | <span data-ttu-id="61f32-189">レベル 1 プラス:</span><span class="sxs-lookup"><span data-stu-id="61f32-189">Level 1 plus:</span></span> <BR> <BR> <span data-ttu-id="61f32-190">デジタル資産の機密ラベル</span><span class="sxs-lookup"><span data-stu-id="61f32-190">Sensitivity labels on digital assets</span></span>  | <span data-ttu-id="61f32-191">レベル 1</span><span class="sxs-lookup"><span data-stu-id="61f32-191">Level 1</span></span> |
| <span data-ttu-id="61f32-192">レベル 3: 厳しく規制</span><span class="sxs-lookup"><span data-stu-id="61f32-192">Level 3: Highly regulated</span></span> | <span data-ttu-id="61f32-193">レベル 2 プラス:</span><span class="sxs-lookup"><span data-stu-id="61f32-193">Level 2 plus:</span></span> <BR><BR> <span data-ttu-id="61f32-194">営業秘密情報の BYOK (Bring Your Own Key) 暗号化と保護</span><span class="sxs-lookup"><span data-stu-id="61f32-194">Bring Your Own Key (BYOK) encryption and protection for trade secret information</span></span> <BR> <span data-ttu-id="61f32-195">Microsoft 365 サービスと対話する基幹業務アプリケーションの Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="61f32-195">Azure Key Vault for line of business applications that interact with Microsoft 365 services</span></span> | <span data-ttu-id="61f32-196">レベル 2</span><span class="sxs-lookup"><span data-stu-id="61f32-196">Level 2</span></span> | <span data-ttu-id="61f32-197">レベル 1</span><span class="sxs-lookup"><span data-stu-id="61f32-197">Level 1</span></span> |
|||||

<span data-ttu-id="61f32-198">以下は、Contoso 社の結果として得られる情報保護構成です。</span><span class="sxs-lookup"><span data-stu-id="61f32-198">Here is Contoso's resulting information protection configuration.</span></span>

![Contoso 社の結果として得られる情報保護構成](../media/contoso-info-protect/contoso-info-protect-fig2.png)

## <a name="next-step"></a><span data-ttu-id="61f32-200">次の手順</span><span class="sxs-lookup"><span data-stu-id="61f32-200">Next step</span></span>

<span data-ttu-id="61f32-201">Id およびアクセス管理、脅威保護、情報保護、およびセキュリティ管理については、「Contoso 社が Microsoft 365 のセキュリティ機能を使用する方法[」を参照してください](contoso-security-summary.md)。</span><span class="sxs-lookup"><span data-stu-id="61f32-201">[See](contoso-security-summary.md) how Contoso has used the security features across Microsoft 365 for enterprise for identity and access management, threat protection, information protection, and security management.</span></span>

## <a name="see-also"></a><span data-ttu-id="61f32-202">関連項目</span><span class="sxs-lookup"><span data-stu-id="61f32-202">See also</span></span>

[<span data-ttu-id="61f32-203">セキュリティのロードマップ</span><span class="sxs-lookup"><span data-stu-id="61f32-203">Security roadmap</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)

[<span data-ttu-id="61f32-204">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="61f32-204">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="61f32-205">テスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="61f32-205">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)


