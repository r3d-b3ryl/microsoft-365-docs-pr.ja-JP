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
ms.openlocfilehash: a1aa08a20d284d3a003f4a406c37f2107ce19bd1
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754607"
---
# <a name="information-protection-for-the-contoso-corporation"></a><span data-ttu-id="5d9d9-103">Contoso Corporation の情報保護</span><span class="sxs-lookup"><span data-stu-id="5d9d9-103">Information protection for the Contoso Corporation</span></span>

<span data-ttu-id="5d9d9-p101">Contoso 社は情報セキュリティに関して深刻なものです。製品設計と独自の製造手法を説明する知的財産を漏洩または破壊することによって、競合の不利になります。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-p101">Contoso is serious about their information security. Leakage or destruction of intellectual property that describes their product designs and proprietary manufacturing techniques would place them at a competitive disadvantage.</span></span>

<span data-ttu-id="5d9d9-106">機密のデジタル資産をクラウドに移行する前に、Contoso 社は社内の情報の分類と保護要件が、Microsoft 365 for enterprise のクラウドベースのサービスによってサポートされていることを確認しました。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-106">Before moving their sensitive digital assets to the cloud, Contoso made sure that their on-premises information classification and protection requirements were supported by the cloud-based services of Microsoft 365 for enterprise.</span></span>

## <a name="contoso-data-security-classification"></a><span data-ttu-id="5d9d9-107">Contoso データセキュリティの分類</span><span class="sxs-lookup"><span data-stu-id="5d9d9-107">Contoso data security classification</span></span>

<span data-ttu-id="5d9d9-108">Contoso 社は、データの分析を行い、次の分類レベルを決定しました。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-108">Contoso performed an analysis of their data and determined the following classification levels.</span></span>

| <span data-ttu-id="5d9d9-109">レベル 1: ベースライン</span><span class="sxs-lookup"><span data-stu-id="5d9d9-109">Level 1: Baseline</span></span> | <span data-ttu-id="5d9d9-110">レベル 2: 機密</span><span class="sxs-lookup"><span data-stu-id="5d9d9-110">Level 2: Sensitive</span></span> | <span data-ttu-id="5d9d9-111">レベル 3: 厳しく規制</span><span class="sxs-lookup"><span data-stu-id="5d9d9-111">Level 3: Highly regulated</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="5d9d9-112">データは暗号化され、認証されたユーザーのみが使用できます。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-112">Data is encrypted and available only to authenticated users.</span></span><BR> <BR> <span data-ttu-id="5d9d9-p102">オンプレミスとクラウドベースのストレージおよびワークロードに格納されているすべてのデータに対して提供されます。データは、サービス内に存在し、サービスとクライアントデバイス間で転送される間は暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-p102">Provided for all data stored on-premises and in cloud-based storage and workloads. Data is encrypted while it resides in the service and in transit between the service and client devices.</span></span> <BR><BR><span data-ttu-id="5d9d9-115">レベル 1 のデータの例には、通常のビジネス通信 (電子メール) や、管理、販売、およびサポート ワーカー用のファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-115">Examples of Level 1 data are normal business communications (email) and files for administrative, sales, and support workers.</span></span> | <span data-ttu-id="5d9d9-116">レベル 1 以上の強力な認証とデータ損失保護。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-116">Level 1 plus strong authentication and data loss protection.</span></span><BR> <BR> <span data-ttu-id="5d9d9-117">強力な認証には、SMS 検証を使用した Azure 多要素認証 (MFA) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-117">Strong authentication includes Azure Multi-Factor Authentication (MFA) with SMS validation.</span></span> <span data-ttu-id="5d9d9-118">データ損失防止は、機密情報または重要な情報が Microsoft クラウドの外部では転送されないようにすることを保証します。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-118">Data loss prevention ensures that sensitive or critical information doesn't travel outside the Microsoft cloud.</span></span><BR><BR><span data-ttu-id="5d9d9-119">レベル 2 のデータの例には、財務情報や法的情報、新製品の研究開発データがあります。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-119">Examples of Level 2 data are financial and legal information and research and development data for new products.</span></span> | <span data-ttu-id="5d9d9-120">レベル 2 以上の最高レベルの暗号化、認証、監査。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-120">Level 2 plus the highest levels of encryption, authentication, and auditing.</span></span><BR><BR><span data-ttu-id="5d9d9-121">保存データおよびクラウド内のデータに対する最高レベルの暗号化。地域の規制に準拠し、スマート カードや詳細な監査と警告を使用する MFA と組み合わされています。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-121">The highest levels of encryption for data at rest and in the cloud, compliant with regional regulations, combined with MFA with smart cards and granular auditing and alerting.</span></span><BR> <BR><span data-ttu-id="5d9d9-122">レベル3のデータの例としては、顧客およびパートナーの個人情報、製品エンジニアリング仕様、独自の製造技術があります。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-122">Examples of Level 3 data are customer and partner personal information, product engineering specifications, and proprietary manufacturing techniques.</span></span>  |
||||

## <a name="contoso-information-policies"></a><span data-ttu-id="5d9d9-123">Contoso 情報ポリシー</span><span class="sxs-lookup"><span data-stu-id="5d9d9-123">Contoso information policies</span></span>
<span data-ttu-id="5d9d9-124">次の表に、Contoso 社の情報ポリシーを示します。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-124">The following table lists the Contoso information policies.</span></span>


| <span data-ttu-id="5d9d9-125">値</span><span class="sxs-lookup"><span data-stu-id="5d9d9-125">Value</span></span> | <span data-ttu-id="5d9d9-126">Access</span><span class="sxs-lookup"><span data-stu-id="5d9d9-126">Access</span></span> | <span data-ttu-id="5d9d9-127">データ保存期間</span><span class="sxs-lookup"><span data-stu-id="5d9d9-127">Data retention</span></span> | <span data-ttu-id="5d9d9-128">情報保護</span><span class="sxs-lookup"><span data-stu-id="5d9d9-128">Information protection</span></span> |
|:-------|:-----|:-----|:-----|
| <span data-ttu-id="5d9d9-129">低いビジネス価値 (レベル 1: ベースライン)</span><span class="sxs-lookup"><span data-stu-id="5d9d9-129">Low business value (Level 1: Baseline)</span></span> | <span data-ttu-id="5d9d9-130">すべてへのアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-130">Allow access to all.</span></span>  | <span data-ttu-id="5d9d9-131">6 か月</span><span class="sxs-lookup"><span data-stu-id="5d9d9-131">6 months</span></span> | <span data-ttu-id="5d9d9-132">暗号化を使用します。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-132">Use encryption.</span></span> |
| <span data-ttu-id="5d9d9-133">中程度のビジネス価値 (レベル 2: 機密)</span><span class="sxs-lookup"><span data-stu-id="5d9d9-133">Medium business value (Level 2: Sensitive)</span></span> | <span data-ttu-id="5d9d9-134">Contoso 社の従業員、下請け業者、パートナーにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-134">Allow access to Contoso employees, subcontractors, and partners.</span></span> <BR><BR> <span data-ttu-id="5d9d9-135">MFA、トランスポート層セキュリティ (TLS)、およびモバイル アプリケーション管理 (MAM) を使用します。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-135">Use MFA, Transport Layer Security (TLS), and Mobile Application Management (MAM).</span></span> | <span data-ttu-id="5d9d9-136">2 年</span><span class="sxs-lookup"><span data-stu-id="5d9d9-136">2 years</span></span>  | <span data-ttu-id="5d9d9-137">データ整合性のためにハッシュ値を使用します。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-137">Use hash values for data integrity.</span></span>  |
| <span data-ttu-id="5d9d9-138">高度なビジネス価値 (レベル 3: 厳しく規制)</span><span class="sxs-lookup"><span data-stu-id="5d9d9-138">High business value (Level 3: Highly regulated)</span></span> | <span data-ttu-id="5d9d9-139">エグゼクティブ、およびエンジニアリングと製造の潜在顧客に対してアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-139">Allow access to executives and leads in engineering and manufacturing.</span></span> <BR> <BR> <span data-ttu-id="5d9d9-140">管理されたネットワーク デバイスのみの Rights Management System (RMS) です。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-140">Rights Management System (RMS) with managed network devices only.</span></span>  | <span data-ttu-id="5d9d9-141">7 年</span><span class="sxs-lookup"><span data-stu-id="5d9d9-141">7 years</span></span>  | <span data-ttu-id="5d9d9-142">否認防止のためにデジタル署名を使用します。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-142">Use digital signatures for non-repudiation.</span></span>  |
|||||

## <a name="the-contoso-path-to-information-protection-with-microsoft-365-for-enterprise"></a><span data-ttu-id="5d9d9-143">Microsoft 365 for enterprise を使用した情報保護への Contoso のパス</span><span class="sxs-lookup"><span data-stu-id="5d9d9-143">The Contoso path to information protection with Microsoft 365 for enterprise</span></span>

<span data-ttu-id="5d9d9-144">Contoso 社は、次の手順に従って、情報保護の要件に応じて Microsoft 365 for enterprise を準備します。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-144">Contoso followed these steps to prepare Microsoft 365 for enterprise for their information-protection requirements:</span></span>

1. <span data-ttu-id="5d9d9-145">保護する情報を特定する</span><span class="sxs-lookup"><span data-stu-id="5d9d9-145">Identify what information to protect</span></span>

   <span data-ttu-id="5d9d9-146">Contoso 社は、オンプレミスの SharePoint サイトとファイル共有に配置されている既存のデジタル資産を幅広くレビューし、各資産に分類しました。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-146">Contoso did an extensive review of their existing digital assets located on on-premises SharePoint sites and file shares and classified each asset.</span></span>

2. <span data-ttu-id="5d9d9-147">各データ レベルについてアクセス、保持、情報保護ポリシーを決定する</span><span class="sxs-lookup"><span data-stu-id="5d9d9-147">Determine access, retention, and information protection policies for data levels</span></span>

   <span data-ttu-id="5d9d9-148">データ レベルに基づいて、Contoso 社は詳細なポリシー要件を決定しました。この要件は、クラウドへの移行時に既存のデジタル資産を保護するために使用されました。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-148">Based on the data levels, Contoso determined detailed policy requirements, which were used to protect existing digital assets as they were moved to the cloud.</span></span>

3. <span data-ttu-id="5d9d9-149">さまざまなレベルの情報について、機密ラベルとその設定を作成する</span><span class="sxs-lookup"><span data-stu-id="5d9d9-149">Create sensitivity labels and their settings for the different levels of information</span></span>

   <span data-ttu-id="5d9d9-150">Contoso 社では、データのレベルに応じた機密ラベルを作成しました。「厳しく規制」のラベルで、暗号化、アクセス許可、透かしなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-150">Contoso created sensitivity labels for their data levels, with their highly regulated label that includes encryption, permissions, and watermarks.</span></span>

4.  <span data-ttu-id="5d9d9-151">オンプレミスの SharePoint サイトとファイル共有から新しい SharePoint サイトにデータを移動する</span><span class="sxs-lookup"><span data-stu-id="5d9d9-151">Move data from on-premises SharePoint sites and file shares to their new SharePoint sites</span></span>

    <span data-ttu-id="5d9d9-152">新しい SharePoint サイトに移行したファイルには、そのサイトに割り当てられた既定の保持ラベルを継承させました。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-152">The files migrated to the new SharePoint sites inherited the default retention labels assigned to the site.</span></span>

5.  <span data-ttu-id="5d9d9-153">従業員に新しいドキュメントの機密ラベルを使用する方法、新しい SharePoint サイトを作成するときに Contoso IT と対話する方法、および常に SharePoint サイトにデジタルアセットを格納する方法を学習します。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-153">Train employees how to use sensitivity labels for new documents, how to interact with Contoso IT when creating new SharePoint sites, and to always store digital assets on SharePoint sites</span></span>

    <span data-ttu-id="5d9d9-154">不適切なワーカー情報の変更-ストレージ習慣は、クラウドの情報保護移行の最も難しい部分と見なされることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-154">Changing bad worker information-storage habits is often considered the hardest part of the information protection transition for the cloud.</span></span> <span data-ttu-id="5d9d9-155">Contoso IT and management 従業員がデジタルアセットを常にクラウドにラベル付けして保存し、オンプレミスのファイル共有を使用しないで、サードパーティ製のクラウドストレージサービスまたは USB ドライブを使用しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-155">Contoso IT and management needed to get employees to always label and store their digital assets in the cloud, refrain from using on-premises file shares, and not use third-party cloud storage services or USB drives.</span></span>

## <a name="conditional-access-policies-for-information-protection"></a><span data-ttu-id="5d9d9-156">情報保護のための条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="5d9d9-156">Conditional Access policies for information protection</span></span>

<span data-ttu-id="5d9d9-157">Contoso 社は、Exchange Online と SharePoint の展開の一環として、次の条件付きアクセスポリシーのセットを構成し、適切なグループに適用しました。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-157">As part of their rollout of Exchange Online and SharePoint, Contoso configured the following set of Conditional Access policies and applied them to the appropriate groups:</span></span>

- [<span data-ttu-id="5d9d9-158">デバイスで管理されるアプリケーション アクセスと管理されないアプリケーション アクセスのポリシー</span><span class="sxs-lookup"><span data-stu-id="5d9d9-158">Managed and unmanaged application access on devices policies</span></span>](../security/office-365-security/identity-access-policies.md)
- [<span data-ttu-id="5d9d9-159">Exchange Online アクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="5d9d9-159">Exchange Online access policies</span></span>](../security/office-365-security/secure-email-recommended-policies.md)
- [<span data-ttu-id="5d9d9-160">SharePoint アクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="5d9d9-160">SharePoint access policies</span></span>](../security/office-365-security/sharepoint-file-access-policies.md)

<span data-ttu-id="5d9d9-161">情報保護のための Contoso ポリシーの結果として、次のようなセットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-161">Here's resulting set of Contoso policies for information protection.</span></span>

![デバイス、Exchange Online、および SharePoint の条件付きアクセス ポリシー](../media/contoso-info-protect/contoso-info-protect-fig1.png)

>[!Note]
><span data-ttu-id="5d9d9-163">Contoso 社は、ID とサインイン用に追加の条件付きアクセス ポリシーも構成しました。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-163">Contoso also configured additional Conditional Access policies for identity and sign-in.</span></span> <span data-ttu-id="5d9d9-164">「[Contoso 社の ID](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-164">See [Identity for the Contoso Corporation](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span></span>
>

<span data-ttu-id="5d9d9-165">これらのポリシーでは、次のことを確実にします。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-165">These policies ensure that:</span></span>

- <span data-ttu-id="5d9d9-166">許可されているアプリと、組織のデータによって実行できるアクションは、アプリ保護ポリシーによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-166">Apps that are allowed and the actions they can take with the organization's data are defined by app protection policies.</span></span>
- <span data-ttu-id="5d9d9-167">PC とモバイル デバイスが必ず準拠している。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-167">PCs and mobile devices must be compliant.</span></span>
- <span data-ttu-id="5d9d9-168">Exchange Online では、Exchange Online の Office 365 message encryption (OME) を使用します。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-168">Exchange Online uses Office 365 message encryption (OME) for Exchange Online.</span></span>
- <span data-ttu-id="5d9d9-169">SharePoint では、アプリ強制の制限が使用されます。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-169">SharePoint uses app-enforced restrictions.</span></span>
- <span data-ttu-id="5d9d9-170">SharePoint は、ブラウザー専用のアクセスにアクセス制御ポリシーを使用して、管理されていないデバイスのアクセスはブロックする。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-170">SharePoint uses access control policies for browser-only access and to block access for unmanaged devices.</span></span>

## <a name="mapping-microsoft-365-for-enterprise-features-to-contoso-data-levels"></a><span data-ttu-id="5d9d9-171">エンタープライズ機能に関する Microsoft 365 の Contoso データレベルへのマッピング</span><span class="sxs-lookup"><span data-stu-id="5d9d9-171">Mapping Microsoft 365 for enterprise features to Contoso data levels</span></span>

<span data-ttu-id="5d9d9-172">次の表は、Microsoft 365 for enterprise の情報保護機能への Contoso データレベルのマッピングを示しています。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-172">The following table maps Contoso data levels to information protection features in Microsoft 365 for enterprise.</span></span>

| <span data-ttu-id="5d9d9-173">レベル</span><span class="sxs-lookup"><span data-stu-id="5d9d9-173">Level</span></span> | <span data-ttu-id="5d9d9-174">Microsoft 365 クラウドサービス</span><span class="sxs-lookup"><span data-stu-id="5d9d9-174">Microsoft 365 cloud services</span></span> | <span data-ttu-id="5d9d9-175">Windows 10 および Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="5d9d9-175">Windows 10 and Microsoft 365 Apps for enterprise</span></span> | <span data-ttu-id="5d9d9-176">セキュリティとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="5d9d9-176">Security and compliance</span></span> |
|:-------|:-----|:-----|:-----|
| <span data-ttu-id="5d9d9-177">レベル 1: ベースライン</span><span class="sxs-lookup"><span data-stu-id="5d9d9-177">Level 1: Baseline</span></span>  | <span data-ttu-id="5d9d9-178">SharePoint および Exchange Online の条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="5d9d9-178">SharePoint and Exchange Online Conditional Access policies</span></span> <BR> <span data-ttu-id="5d9d9-179">SharePoint サイトのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="5d9d9-179">Permissions on SharePoint sites</span></span> | <span data-ttu-id="5d9d9-180">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="5d9d9-180">Sensitivity labels</span></span> <BR> <span data-ttu-id="5d9d9-181">BitLocker</span><span class="sxs-lookup"><span data-stu-id="5d9d9-181">BitLocker</span></span> <BR> <span data-ttu-id="5d9d9-182">Windows 情報保護</span><span class="sxs-lookup"><span data-stu-id="5d9d9-182">Windows Information Protection</span></span> | <span data-ttu-id="5d9d9-183">デバイスの条件付きアクセス ポリシーとモバイル アプリケーション管理ポリシー</span><span class="sxs-lookup"><span data-stu-id="5d9d9-183">Device Conditional Access policies and Mobile Application Management policies</span></span> |
| <span data-ttu-id="5d9d9-184">レベル 2: 機密</span><span class="sxs-lookup"><span data-stu-id="5d9d9-184">Level 2: Sensitive</span></span> | <span data-ttu-id="5d9d9-185">レベル 1 プラス:</span><span class="sxs-lookup"><span data-stu-id="5d9d9-185">Level 1 plus:</span></span> <BR> <BR> <span data-ttu-id="5d9d9-186">秘密度ラベル</span><span class="sxs-lookup"><span data-stu-id="5d9d9-186">Sensitivity labels</span></span> <BR> <span data-ttu-id="5d9d9-187">SharePoint サイトの Microsoft 365 保持ラベル</span><span class="sxs-lookup"><span data-stu-id="5d9d9-187">Microsoft 365 retention labels on SharePoint sites</span></span> <BR> <span data-ttu-id="5d9d9-188">SharePoint および Exchange Online 用のデータ損失防止</span><span class="sxs-lookup"><span data-stu-id="5d9d9-188">Data Loss Prevention for SharePoint and Exchange Online</span></span> <BR> <span data-ttu-id="5d9d9-189">分離した SharePoint サイト</span><span class="sxs-lookup"><span data-stu-id="5d9d9-189">Isolated SharePoint sites</span></span>  | <span data-ttu-id="5d9d9-190">レベル 1 プラス:</span><span class="sxs-lookup"><span data-stu-id="5d9d9-190">Level 1 plus:</span></span> <BR> <BR> <span data-ttu-id="5d9d9-191">デジタル資産の機密ラベル</span><span class="sxs-lookup"><span data-stu-id="5d9d9-191">Sensitivity labels on digital assets</span></span>  | <span data-ttu-id="5d9d9-192">レベル 1</span><span class="sxs-lookup"><span data-stu-id="5d9d9-192">Level 1</span></span> |
| <span data-ttu-id="5d9d9-193">レベル 3: 厳しく規制</span><span class="sxs-lookup"><span data-stu-id="5d9d9-193">Level 3: Highly regulated</span></span> | <span data-ttu-id="5d9d9-194">レベル 2 プラス:</span><span class="sxs-lookup"><span data-stu-id="5d9d9-194">Level 2 plus:</span></span> <BR><BR> <span data-ttu-id="5d9d9-195">秘密情報の暗号化と保護を独自のキー (BYOK) にする</span><span class="sxs-lookup"><span data-stu-id="5d9d9-195">Bring your own key (BYOK) encryption and protection for trade secret information</span></span> <BR> <span data-ttu-id="5d9d9-196">Microsoft 365 サービスと対話する基幹業務アプリケーションの Azure キーヴォールト</span><span class="sxs-lookup"><span data-stu-id="5d9d9-196">Azure Key Vault for line-of-business applications that interact with Microsoft 365 services</span></span> | <span data-ttu-id="5d9d9-197">レベル 2</span><span class="sxs-lookup"><span data-stu-id="5d9d9-197">Level 2</span></span> | <span data-ttu-id="5d9d9-198">レベル 1</span><span class="sxs-lookup"><span data-stu-id="5d9d9-198">Level 1</span></span> |
|||||

<span data-ttu-id="5d9d9-199">結果として得られる Contoso の情報保護構成を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-199">Here's the resulting Contoso information-protection configuration.</span></span>

![Contoso 社の結果として得られる情報保護構成](../media/contoso-info-protect/contoso-info-protect-fig2.png)

## <a name="next-step"></a><span data-ttu-id="5d9d9-201">次の手順</span><span class="sxs-lookup"><span data-stu-id="5d9d9-201">Next step</span></span>

<span data-ttu-id="5d9d9-202">Contoso 社が、id およびアクセス管理、脅威保護、情報保護、およびセキュリティ管理のために [Microsoft 365 for enterprise のセキュリティ機能](contoso-security-summary.md) を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5d9d9-202">Learn how Contoso uses the [security features across Microsoft 365 for enterprise](contoso-security-summary.md) for identity and access management, threat protection, information protection, and security management.</span></span>

## <a name="see-also"></a><span data-ttu-id="5d9d9-203">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d9d9-203">See also</span></span>

[<span data-ttu-id="5d9d9-204">セキュリティのロードマップ</span><span class="sxs-lookup"><span data-stu-id="5d9d9-204">Security roadmap</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)

[<span data-ttu-id="5d9d9-205">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="5d9d9-205">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="5d9d9-206">テスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="5d9d9-206">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
