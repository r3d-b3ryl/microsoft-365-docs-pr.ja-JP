---
title: Contoso Corporation の情報保護
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 社が Microsoft 365 Enterprise の情報保護機能を使用して、クラウドのデジタル資産をセキュリティで保護する方法について説明します。
ms.openlocfilehash: f0869dfd661ae4dbaed74fdfd660c863deb20175
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32276118"
---
# <a name="information-protection-for-the-contoso-corporation"></a><span data-ttu-id="2a056-103">Contoso Corporation の情報保護</span><span class="sxs-lookup"><span data-stu-id="2a056-103">Information protection for the Contoso Corporation</span></span>

<span data-ttu-id="2a056-104">**概要:** Contoso 社が Microsoft 365 Enterprise の情報保護機能を使用して、クラウドのデジタル資産をセキュリティで保護する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2a056-104">**Summary:** Understand how Contoso uses information protection features in Microsoft 365 Enterprise to secure their digital assets in the cloud.</span></span>

<span data-ttu-id="2a056-p101">Contoso 社では、情報のセキュリティと保護を重視しています。たとえば、製品のデザインや独自の製造技術を説明する知的財産の漏洩や破壊は、それらを競争面で不利な立場に置くことになります。</span><span class="sxs-lookup"><span data-stu-id="2a056-p101">Contoso is serious about their information security and protection. For example, leakage or destruction of their intellectual property describing product designs and proprietary manufacturing techniques would place them at a competitive disadvantage.</span></span>

<span data-ttu-id="2a056-107">機密性が高く、最も価値の高いデジタル資産をクラウドに移行する前に、Contoso 社ではオンプレミスの情報分類と保護の要件が Microsoft 365 Enterprise のクラウドベースのサービスでサポートされ、実装されていることを確認しました。</span><span class="sxs-lookup"><span data-stu-id="2a056-107">Before moving their sensitive and most valuable digital assets to the cloud, they made sure that their on-premises information classification and protection requirements were supported and implemented in the cloud-based services of Microsoft 365 Enterprise.</span></span>

## <a name="contosos-data-security-classification"></a><span data-ttu-id="2a056-108">Contoso 社のデータ セキュリティの分類</span><span class="sxs-lookup"><span data-stu-id="2a056-108">Contoso's data security classification</span></span>

<span data-ttu-id="2a056-109">Contoso 社では自社のデータの分析を行い、次に示すレベルを決定しました。</span><span class="sxs-lookup"><span data-stu-id="2a056-109">Contoso performed an analysis of their data and determined the following levels.</span></span>

||||
|:-------|:-----|:-----|
| <span data-ttu-id="2a056-110">**レベル 1: ベースライン**</span><span class="sxs-lookup"><span data-stu-id="2a056-110">**Level 1: Baseline**</span></span> | <span data-ttu-id="2a056-111">**レベル 2: 機密**</span><span class="sxs-lookup"><span data-stu-id="2a056-111">**Level 2: Sensitive**</span></span> | <span data-ttu-id="2a056-112">**レベル 3: 厳しく規制**</span><span class="sxs-lookup"><span data-stu-id="2a056-112">**Level 3: Highly regulated**</span></span> |
| <span data-ttu-id="2a056-113">データは暗号化され、認証されたユーザーのみが使用できる</span><span class="sxs-lookup"><span data-stu-id="2a056-113">Data is encrypted and available only to authenticated users</span></span> <BR> <BR> <span data-ttu-id="2a056-p102">オンプレミスとクラウドベースのストレージとワークロード (Office 365 など) に格納されているすべてのデータに提供されます。データは、サービス内に存在している間、およびサービスとクライアント デバイス間の転送中は暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="2a056-p102">Provided for all data stored on premises and in cloud-based storage and workloads, such as Office 365. Data is encrypted while it resides in the service and in transit between the service and client devices.</span></span> <BR><BR> <span data-ttu-id="2a056-116">レベル 1 のデータの例には、通常のビジネス通信 (電子メール) や、管理、販売、およびサポート ワーカー用のファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="2a056-116">Examples of Level 1 data are normal business communications (email) and files for administrative, sales, and support workers.</span></span> | <span data-ttu-id="2a056-117">レベル 1 以上の強力な認証とデータ損失保護。</span><span class="sxs-lookup"><span data-stu-id="2a056-117">Level 1 plus strong authentication and data loss protection:</span></span> <BR> <BR> <span data-ttu-id="2a056-p103">強力な認証には、SMS 検証を使用した多要素認証が含まれています。データ損失の防止により、機密情報または重要な情報がオンプレミス ネットワークの外部に漏出しないようにします。</span><span class="sxs-lookup"><span data-stu-id="2a056-p103">Strong authentication includes multi-factor authentication with SMS validation. Data loss prevention ensures that sensitive or critical information does not travel outside the on-premises network.</span></span> <BR><BR> <span data-ttu-id="2a056-120">レベル 2 のデータの例には、財務情報や法的情報、新製品の研究開発データがあります。</span><span class="sxs-lookup"><span data-stu-id="2a056-120">Examples of Level 2 data are financial and legal information and research and development data for new products.</span></span> | <span data-ttu-id="2a056-121">レベル 2 以上の最高レベルの暗号化、認証、監査。</span><span class="sxs-lookup"><span data-stu-id="2a056-121">Level 2 plus the highest levels of encryption, authentication, and auditing.</span></span> <BR> <BR>  <span data-ttu-id="2a056-122">保存データおよびクラウド内のデータに対する最高レベルの暗号化。地域の規制に準拠し、スマート カードや詳細な監査と警告を使用する多要素認証と組み合わされています。</span><span class="sxs-lookup"><span data-stu-id="2a056-122">The highest levels of encryption for data at rest and in the cloud, compliant with regional regulations, combined with multi-factor authentication with smart cards and granular auditing and alerting.</span></span> <BR> <BR> <span data-ttu-id="2a056-123">レベル 3 のデータの例には、顧客およびパートナーの個人を特定できる情報、製品のエンジニアリング仕様、および独自の製造技術があります。</span><span class="sxs-lookup"><span data-stu-id="2a056-123">Examples of Level 3 data are customer and partner personally identifiable information, product engineering specifications, and proprietary manufacturing techniques.</span></span>  |
||||

## <a name="contosos-information-policies"></a><span data-ttu-id="2a056-124">Contoso 社の情報ポリシー</span><span class="sxs-lookup"><span data-stu-id="2a056-124">Contoso's information policies</span></span>
<span data-ttu-id="2a056-125">次の表に、Contoso 社の情報ポリシーを示します。</span><span class="sxs-lookup"><span data-stu-id="2a056-125">The following table lists Contoso's information policies.</span></span>

|||||
|:-------|:-----|:-----|:-----|
|  | <span data-ttu-id="2a056-126">**Access**</span><span class="sxs-lookup"><span data-stu-id="2a056-126">**Access**</span></span> | <span data-ttu-id="2a056-127">**データ保存期間**</span><span class="sxs-lookup"><span data-stu-id="2a056-127">**Data retention**</span></span> | <span data-ttu-id="2a056-128">**情報保護**</span><span class="sxs-lookup"><span data-stu-id="2a056-128">**Information protection**</span></span> |
| <span data-ttu-id="2a056-129">低いビジネス価値 (レベル 1: ベースライン)</span><span class="sxs-lookup"><span data-stu-id="2a056-129">Low business value (Level 1: Baseline)</span></span> | <span data-ttu-id="2a056-130">すべてのユーザーに対してアクセスを許可</span><span class="sxs-lookup"><span data-stu-id="2a056-130">Allow access to all</span></span>  | <span data-ttu-id="2a056-131">6 か月</span><span class="sxs-lookup"><span data-stu-id="2a056-131">6 months</span></span> | <span data-ttu-id="2a056-132">暗号化を使用</span><span class="sxs-lookup"><span data-stu-id="2a056-132">Use encryption</span></span> |
| <span data-ttu-id="2a056-133">中程度のビジネス価値 (レベル 2: 機密)</span><span class="sxs-lookup"><span data-stu-id="2a056-133">Medium business value (Level 2: Sensitive)</span></span> | <span data-ttu-id="2a056-134">Contoso 社の従業員、下請業者、パートナーに対してアクセスを許可</span><span class="sxs-lookup"><span data-stu-id="2a056-134">Allow access to Contoso employees, subcontractors, and partners</span></span> <BR> <BR> <span data-ttu-id="2a056-135">多要素認証 (MFA)、トランスポート層セキュリティ (TLS)、およびモバイル アプリケーション管理 (MAM) を使用</span><span class="sxs-lookup"><span data-stu-id="2a056-135">Use multi-factor authentication (MFA), Transport Layer Security (TLS), and Mobile Application Management (MAM)</span></span> | <span data-ttu-id="2a056-136">2 年</span><span class="sxs-lookup"><span data-stu-id="2a056-136">2 years</span></span>  | <span data-ttu-id="2a056-137">データ整合性のためにハッシュ値を使用</span><span class="sxs-lookup"><span data-stu-id="2a056-137">Use hash values for data integrity</span></span>  |
| <span data-ttu-id="2a056-138">高度なビジネス価値 (レベル 3: 厳しく規制)</span><span class="sxs-lookup"><span data-stu-id="2a056-138">High business value (Level 3: Highly regulated)</span></span> | <span data-ttu-id="2a056-139">エグゼクティブ、およびエンジニアリングと製造の潜在顧客に対してアクセスを許可</span><span class="sxs-lookup"><span data-stu-id="2a056-139">Allow access to executives and leads in engineering and manufacturing</span></span> <BR> <BR> <span data-ttu-id="2a056-140">管理されたネットワーク デバイスのみの Rights Management System (RMS)</span><span class="sxs-lookup"><span data-stu-id="2a056-140">Rights Management System (RMS) with managed network devices only</span></span>  | <span data-ttu-id="2a056-141">7 年</span><span class="sxs-lookup"><span data-stu-id="2a056-141">7 years</span></span>  | <span data-ttu-id="2a056-142">否認防止のためにデジタル署名を使用</span><span class="sxs-lookup"><span data-stu-id="2a056-142">Use digital signatures for non-repudiation</span></span>  |
|||||

## <a name="contosos-path-to-information-protection-with-microsoft-365-enterprise"></a><span data-ttu-id="2a056-143">Contoso 社の Microsoft 365 Enterprise を使用した情報保護への道のり</span><span class="sxs-lookup"><span data-stu-id="2a056-143">Contoso’s path to information protection with Microsoft 365 Enterprise</span></span>

<span data-ttu-id="2a056-144">Contoso 社は、次の手順を使用して、自社の情報保護の要件に対応する Microsoft 365 Enterprise を準備しました。</span><span class="sxs-lookup"><span data-stu-id="2a056-144">Contoso used the following steps to prepare Microsoft 365 Enterprise for their information protection requirements:</span></span>

1. <span data-ttu-id="2a056-145">保護する情報を特定した</span><span class="sxs-lookup"><span data-stu-id="2a056-145">Identified what information to protect</span></span>

   <span data-ttu-id="2a056-146">Contoso 社は、オンプレミスの SharePoint サイトとファイル共有にある既存のデジタル資産を広範囲にわたって再調査して、それぞれを分類しました。</span><span class="sxs-lookup"><span data-stu-id="2a056-146">Contoso did an extensive review of their existing digital assets located on on-premises SharePoint sites and file shares and classified each one.</span></span>

2. <span data-ttu-id="2a056-147">各データ レベルに応じてアクセス ポリシー、保持ポリシー、情報保護ポリシーを決定した</span><span class="sxs-lookup"><span data-stu-id="2a056-147">Determined access, retention, and information protection policies for data levels</span></span>

   <span data-ttu-id="2a056-148">データ レベルに基づいて、Contoso 社は詳細なポリシー要件を決定しました。この要件は、クラウドへの移行時に既存のデジタル資産を保護するために使用されました。</span><span class="sxs-lookup"><span data-stu-id="2a056-148">Based on the data levels, Contoso determined detailed policy requirements, which were used to protect existing digital assets as they were moved to the cloud.</span></span>

3. <span data-ttu-id="2a056-149">さまざまな情報のレベルに応じた機密ラベルとその設定を作成した</span><span class="sxs-lookup"><span data-stu-id="2a056-149">Created Azure Information Protection labels and their settings for the different levels of information</span></span>

   <span data-ttu-id="2a056-150">Contoso 社では、データのレベルに応じた機密ラベルを作成しました。「機密」や「厳しく規制」のラベルで、暗号化、アクセス許可、透かしなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2a056-150">Contoso created sensitivity labels for their data levels, with sensitive and highly regulated label including encryption, permissions, and watermarks.</span></span>

4. <span data-ttu-id="2a056-151">アクセスをロックするアクセス許可を使用して機密データと厳しく規制されたデータに対応する保護された SharePoint Online サイトを作成した</span><span class="sxs-lookup"><span data-stu-id="2a056-151">Created protected SharePoint Online sites for sensitive and highly regulated data with permissions that lock down access</span></span>

   <span data-ttu-id="2a056-152">機密サイトと厳しく制限されたサイトは、どちらも[分離したサイト](https://docs.microsoft.com/office365/enterprise/isolated-sharepoint-online-team-sites)として構成しました。これらのサイトでは、既定の SharePoint Online チーム サイトのアクセス許可が Azure Active Directory (Azure AD) グループにカスタマイズされています。</span><span class="sxs-lookup"><span data-stu-id="2a056-152">Both sensitive and highly regulated sites were configured as [isolated sites](https://docs.microsoft.com/office365/enterprise/isolated-sharepoint-online-team-sites), in which the default SharePoint Online team site permissions were customized to Azure Active Directory (Azure AD) groups.</span></span> <span data-ttu-id="2a056-153">「機密」および「厳しく規制」の SharePoint Online サイトは、対応する保持ラベルを使用して構成されています。</span><span class="sxs-lookup"><span data-stu-id="2a056-153">Sensitive and highly regulated SharePoint Online sites were also configured with a corrresponding retention label.</span></span> <span data-ttu-id="2a056-154">「厳しく規制」の SharePoint Online サイトに保存されているファイルは、「厳しく規制」の機密ラベルで保護されています。</span><span class="sxs-lookup"><span data-stu-id="2a056-154">Files stored in highly regulated SharePoint Online sites are protected with the Highly Regulated sensitivity label.</span></span> <span data-ttu-id="2a056-155">詳細については、「[Microsoft Teams および SharePoint Online サイトで高度な規制データを扱うには](teams-sharepoint-online-sites-highly-regulated-data.md)」のシナリオを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a056-155">For more information, see the [Microsoft Teams and SharePoint Online sites for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md) scenario.</span></span>

5.  <span data-ttu-id="2a056-156">オンプレミスの SharePoint サイトとファイル共有のデータを新しい SharePoint Online サイトに移動した</span><span class="sxs-lookup"><span data-stu-id="2a056-156">Moved data from on-premises SharePoint sites and file shares to their new SharePoint Online sites</span></span>

    <span data-ttu-id="2a056-157">新しい SharePoint Online サイトに移行したファイルには、そのサイトに割り当てられた既定の保持ラベルを継承させました。</span><span class="sxs-lookup"><span data-stu-id="2a056-157">The files migrated to the new SharePoint Online sites inherited the default Office 365 labels assigned to the site.</span></span>

6.  <span data-ttu-id="2a056-158">新しいドキュメントに機密ラベルを使用する方法、新しい SharePoint Online サイトの作成時に Contoso 社の IT 部門と応対する方法、およびデジタル資産は必ず SharePoint Online サイトに保管することについて従業員を教育しました</span><span class="sxs-lookup"><span data-stu-id="2a056-158">Trained employees on how to use Azure Information Protection labels for new documents, how to interact with Contoso IT when creating new SharePoint Online sites, and to always store digital assets on SharePoint Online sites</span></span>

    <span data-ttu-id="2a056-159">クラウドに向けた情報保護の変化で最も難しい部分であると考えられることから、Contoso 社の IT 部門と経営陣は、クラウド上のデジタル資産には必ずラベルを付けて保存し、オンプレミスのファイル共有を控え、サード パーティのクラウド ストレージ サービスや USB ドライブは決して使用しないように、組織の従業員の情報保管に関する悪習慣を改めることが必要でした。</span><span class="sxs-lookup"><span data-stu-id="2a056-159">Considered the hardest part of the information protection transition for the cloud, Contoso IT and management needed to change the bad information storage habits of the organization’s employees to always store and label their digital assets in the cloud, refrain from using on-premises file shares, and never use third-party cloud storage services or USB drives.</span></span>

## <a name="conditional-access-policies-for-information-protection"></a><span data-ttu-id="2a056-160">情報保護のための条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="2a056-160">Conditional access policies for information protection</span></span>

<span data-ttu-id="2a056-161">ID とモバイル デバイスの管理インフラストラクチャと共に、Exchange Online と SharePoint Online のロールアウトの一環として、Contoso 社は、次に示す条件付きアクセス ポリシーのセットを構成して、そのポリシーを該当する Azure AD グループに適用しました。</span><span class="sxs-lookup"><span data-stu-id="2a056-161">In conjunction with their identity and mobile device management infrastructure and as part of their rollout of Exchange Online and SharePoint Online, Contoso configured the following set of conditional access policies and applied them to the appropriate Azure AD groups:</span></span>

- [<span data-ttu-id="2a056-162">デバイスで管理されるアプリケーション アクセスと管理されないアプリケーション アクセスのポリシー</span><span class="sxs-lookup"><span data-stu-id="2a056-162">Managed and unmanaged application access on devices policies</span></span>](identity-access-policies.md)
- [<span data-ttu-id="2a056-163">Exchange Online アクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="2a056-163">Exchange Online access policies</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="2a056-164">SharePoint Online アクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="2a056-164">SharePoint Online access policies</span></span>](sharepoint-file-access-policies.md)

<span data-ttu-id="2a056-165">図 1 は、Contoso 社の情報保護に応じた結果としてのポリシーのセットです。</span><span class="sxs-lookup"><span data-stu-id="2a056-165">Figure 1 shows Contoso's resulting set of policies for information protection.</span></span>

![](./media/contoso-info-protect/contoso-info-protect-fig1.png)

<span data-ttu-id="2a056-166">**図 1: デバイス、Exchange Online、および SharePoint Online の条件付きアクセス ポリシー**</span><span class="sxs-lookup"><span data-stu-id="2a056-166">**Figure 1: Device, Exchange Online, and SharePoint Online conditional access policies**</span></span>
 
>[!Note]
><span data-ttu-id="2a056-p105">Contoso 社は、ID とサインイン用に追加の条件付きアクセス ポリシーも構成しました。「[Contoso 社の ID](contoso-identity.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a056-p105">Contoso also configured additional conditional access policies for identity and sign-in. See [Identity for the Contoso Corporation](contoso-identity.md).</span></span>
>

<span data-ttu-id="2a056-169">これらのポリシーでは、次のことを確実にします。</span><span class="sxs-lookup"><span data-stu-id="2a056-169">These policies ensure that:</span></span>

- <span data-ttu-id="2a056-170">許可されるアプリと、そのアプリで組織のデータに対して実行できる操作は、アプリ保護ポリシーによって定義される。</span><span class="sxs-lookup"><span data-stu-id="2a056-170">Apps are allowed and the actions they can take with your organization data are defined by app protection policies.</span></span>
- <span data-ttu-id="2a056-171">PC とモバイル デバイスが必ず準拠している。</span><span class="sxs-lookup"><span data-stu-id="2a056-171">PCs and mobile devices must be compliant.</span></span>
- <span data-ttu-id="2a056-172">Exchange Online は、Exchange Online に対応した Office 365 メッセージ暗号化を使用する。</span><span class="sxs-lookup"><span data-stu-id="2a056-172">Exchange Online uses Office 365 message encryption for Exchange Online.</span></span>
- <span data-ttu-id="2a056-173">SharePoint Online は、アプリによって適用される制限を使用する。</span><span class="sxs-lookup"><span data-stu-id="2a056-173">SharePoint Online uses app enforced restrictions.</span></span>
- <span data-ttu-id="2a056-174">SharePoint Online は、ブラウザー専用のアクセスにアクセス制御ポリシーを使用して、管理されていないデバイスのアクセスはブロックする。</span><span class="sxs-lookup"><span data-stu-id="2a056-174">SharePoint Online uses access control policies for browser-only access and to block access for unmanaged devices.</span></span>

## <a name="mapping-microsoft-365-enterprise-features-to-contosos-data-levels"></a><span data-ttu-id="2a056-175">Contoso 社のデータ レベルへの Microsoft 365 Enterprise 機能のマッピング</span><span class="sxs-lookup"><span data-stu-id="2a056-175">Mapping Microsoft 365 Enterprise features to Contoso's data levels</span></span>

<span data-ttu-id="2a056-176">次の表は、Microsoft 365 Enterprise の情報保護機能への Contoso 社のデータ レベルのマッピングを示しています。</span><span class="sxs-lookup"><span data-stu-id="2a056-176">The following table shows the mapping the Contoso's data levels to information protection features in Microsoft 365 Enterprise.</span></span>

|||||
|:-------|:-----|:-----|:-----|
| | <span data-ttu-id="2a056-177">**Office 365**</span><span class="sxs-lookup"><span data-stu-id="2a056-177">**Office 365**</span></span> | <span data-ttu-id="2a056-178">**Windows 10 および Office 365 ProPlus**</span><span class="sxs-lookup"><span data-stu-id="2a056-178">**Windows 10 and Office 365 ProPlus**</span></span> | <span data-ttu-id="2a056-179">**EMS**</span><span class="sxs-lookup"><span data-stu-id="2a056-179">**EMS**</span></span> |
| <span data-ttu-id="2a056-180">レベル 1: ベースライン</span><span class="sxs-lookup"><span data-stu-id="2a056-180">Level 1: Baseline</span></span>  | <span data-ttu-id="2a056-181">SharePoint Online および Exchange Online の条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="2a056-181">SharePoint Online and Exchange Online conditional access policies</span></span> <BR> <span data-ttu-id="2a056-182">SharePoint Online サイトのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="2a056-182">Permissions on SharePoint Online sites</span></span> | <span data-ttu-id="2a056-183">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="2a056-183">Sensitivity labels</span></span> <BR> <span data-ttu-id="2a056-184">BitLocker</span><span class="sxs-lookup"><span data-stu-id="2a056-184">BitLocker</span></span> <BR> <span data-ttu-id="2a056-185">Windows 情報保護</span><span class="sxs-lookup"><span data-stu-id="2a056-185">Windows Information Protection</span></span> | <span data-ttu-id="2a056-186">デバイスの条件付きアクセス ポリシーとモバイル アプリケーション管理ポリシー</span><span class="sxs-lookup"><span data-stu-id="2a056-186">Device conditional access policies and Mobile Application Management policies</span></span> |
| <span data-ttu-id="2a056-187">レベル 2: 機密</span><span class="sxs-lookup"><span data-stu-id="2a056-187">Level 2: Sensitive</span></span> | <span data-ttu-id="2a056-188">レベル 1 プラス:</span><span class="sxs-lookup"><span data-stu-id="2a056-188">Level 1: Baseline plus:</span></span> <BR> <BR> <span data-ttu-id="2a056-189">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="2a056-189">Sensitivity labels</span></span> <BR> <span data-ttu-id="2a056-190">SharePoint Online サイトの Office 365 ラベル</span><span class="sxs-lookup"><span data-stu-id="2a056-190">Office 365 labels on SharePoint Online sites</span></span> <BR> <span data-ttu-id="2a056-191">SharePoint Online および Exchange Online 用の Office 365 データ損失防止</span><span class="sxs-lookup"><span data-stu-id="2a056-191">Office 365 Data Loss Prevention for SharePoint Online and Exchange Online</span></span> <BR> <span data-ttu-id="2a056-192">分離した SharePoint Online サイト</span><span class="sxs-lookup"><span data-stu-id="2a056-192">Isolated SharePoint Online sites</span></span>  | <span data-ttu-id="2a056-193">レベル 1 プラス:</span><span class="sxs-lookup"><span data-stu-id="2a056-193">Level 1: Baseline plus:</span></span> <BR> <BR> <span data-ttu-id="2a056-194">デジタル資産の機密ラベル</span><span class="sxs-lookup"><span data-stu-id="2a056-194">Sensitivity labels on digital assets</span></span> <BR> <span data-ttu-id="2a056-195">Office 365 アドバンスト データ ガバナンス</span><span class="sxs-lookup"><span data-stu-id="2a056-195">Office 365 Advanced Data Governance</span></span> | <span data-ttu-id="2a056-196">レベル 1</span><span class="sxs-lookup"><span data-stu-id="2a056-196">Level 1 – Yellow</span></span> |
| <span data-ttu-id="2a056-197">レベル 3: 厳しく規制</span><span class="sxs-lookup"><span data-stu-id="2a056-197">Level 3: Highly regulated</span></span> | <span data-ttu-id="2a056-198">レベル 2 プラス:</span><span class="sxs-lookup"><span data-stu-id="2a056-198">Level 2: Highly sensitive plus:</span></span> <BR><BR> <span data-ttu-id="2a056-199">営業秘密情報の BYOK (Bring Your Own Key) 暗号化と保護</span><span class="sxs-lookup"><span data-stu-id="2a056-199">Bring Your Own Key (BYOK) encryption and protection for trade secret information</span></span> <BR> <span data-ttu-id="2a056-200">Office 365 サービスと対話する基幹業務アプリケーションの Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="2a056-200">Azure Key Vault for line of business applications that interact with Office 365 services</span></span> | <span data-ttu-id="2a056-201">レベル 2</span><span class="sxs-lookup"><span data-stu-id="2a056-201">Level: 2</span></span> | <span data-ttu-id="2a056-202">レベル 1</span><span class="sxs-lookup"><span data-stu-id="2a056-202">Level 1 – Yellow</span></span> |
|||||


## <a name="next-step"></a><span data-ttu-id="2a056-203">次の手順</span><span class="sxs-lookup"><span data-stu-id="2a056-203">Next step</span></span>

<span data-ttu-id="2a056-204">ID とアクセスの管理、脅威の防止、情報の保護、およびセキュリティの管理に Contoso 社がどのように Microsoft 365 Enterprise のセキュリティ機能を使用しているかについて[確認してください](contoso-security-summary.md)。</span><span class="sxs-lookup"><span data-stu-id="2a056-204">[See](contoso-security-summary.md) how Contoso has used the security features across Microsoft 365 Enterprise for identity and access management, threat protection, information protection, and security management.</span></span>

## <a name="see-also"></a><span data-ttu-id="2a056-205">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a056-205">See also</span></span>

[<span data-ttu-id="2a056-206">Microsoft 365 Enterprise の情報保護</span><span class="sxs-lookup"><span data-stu-id="2a056-206">Information protection for Microsoft 365 Enterprise</span></span>](infoprotect-infrastructure.md)

[<span data-ttu-id="2a056-207">展開ガイド</span><span class="sxs-lookup"><span data-stu-id="2a056-207">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="2a056-208">テスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="2a056-208">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)


