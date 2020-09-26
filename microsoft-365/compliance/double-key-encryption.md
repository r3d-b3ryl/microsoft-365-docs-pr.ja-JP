---
title: 二重キー暗号化 (DKE)
description: DKE を使用すると、キーのフルコントロールを維持しながら、機密性の高いデータを保護することができます。
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 09/22/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 39d7933014f1dc71f8c94e467954d36ede4fb451
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277537"
---
# <a name="double-key-encryption-for-microsoft-365"></a><span data-ttu-id="3d26b-103">Microsoft 365 の二重キー暗号化</span><span class="sxs-lookup"><span data-stu-id="3d26b-103">Double Key Encryption for Microsoft 365</span></span>

> <span data-ttu-id="3d26b-104">*適用対象: Microsoft 365、 [microsoft 365 コンプライアンス](https://www.microsoft.com/microsoft-365/business/compliance-management)、 [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)の二重キー暗号化*</span><span class="sxs-lookup"><span data-stu-id="3d26b-104">*Applies to: Double Key Encryption for Microsoft 365, [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="3d26b-105">*手順: [Azure Information Protection を使用した Windows 用の統一されたラベル付けクライアント](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span><span class="sxs-lookup"><span data-stu-id="3d26b-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="3d26b-106">*サービスの説明: [Microsoft 365 コンプライアンス](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="3d26b-106">*Service description for: [Microsoft 365 Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="3d26b-107">二重キー暗号化 (DKE) は、2つのキーを一緒に使用して、保護されたコンテンツにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="3d26b-107">Double Key Encryption (DKE) uses two keys together to access protected content.</span></span> <span data-ttu-id="3d26b-108">Microsoft は Microsoft Azure に1つのキーを格納し、もう1つのキーを保持します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-108">Microsoft stores one key in Microsoft Azure, and you hold the other key.</span></span> <span data-ttu-id="3d26b-109">キーの1つの完全な制御は、二重キー暗号化サービスを使用して管理します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-109">You maintain full control of one of your keys using the Double Key Encryption service.</span></span> <span data-ttu-id="3d26b-110">機密性の高いコンテンツに対して Azure Information Protection のユニファイドラベルクライアントを使用して保護を適用します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-110">You apply protection using The Azure Information Protection unified labeling client to your highly sensitive content.</span></span>

<span data-ttu-id="3d26b-111">二重キー暗号化は、クラウドとオンプレミスの両方の展開をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3d26b-111">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="3d26b-112">これらの展開は、保護されたデータを格納する際に、暗号化されたデータが透過的であるようにするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-112">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="3d26b-113">既定のクラウドベースのテナントルートキーの詳細については、「 [Azure Information Protection のテナントキーを計画および実装](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d26b-113">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span></span>

## <a name="when-your-organization-should-adopt-dke"></a><span data-ttu-id="3d26b-114">組織で DKE を導入する必要がある場合</span><span class="sxs-lookup"><span data-stu-id="3d26b-114">When your organization should adopt DKE</span></span>

<span data-ttu-id="3d26b-115">二重キー暗号化は、最も機密性の高いデータを対象としたもので、最も厳しい保護要件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-115">Double Key Encryption is intended for your most sensitive data that is subject to the strictest protection requirements.</span></span> <span data-ttu-id="3d26b-116">DKE は、すべてのデータを対象としたものではありません。</span><span class="sxs-lookup"><span data-stu-id="3d26b-116">DKE is not intended for all data.</span></span> <span data-ttu-id="3d26b-117">一般的には、データ全体を保護するために、2つのキー暗号化を使用します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-117">In general, you'll be using Double Key Encryption to protect only a very small part of your overall data.</span></span> <span data-ttu-id="3d26b-118">を展開する前に、このソリューションでカバーする適切なデータを特定することによって慎重に行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d26b-118">You should do due diligence in identifying the right data to cover with this solution before you deploy.</span></span> <span data-ttu-id="3d26b-119">場合によっては、microsoft の管理キーや BYOK による Microsoft 情報保護など、データの大部分について、スコープの絞り込みと他のソリューションの利用が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="3d26b-119">In some cases, you might need to narrow your scope and make use of other solutions for the majority of your data such as Microsoft Information Protection with Microsoft-managed keys or BYOK.</span></span> <span data-ttu-id="3d26b-120">これらのソリューションは、強化された保護と規制の要件を満たしていないドキュメントに十分です。</span><span class="sxs-lookup"><span data-stu-id="3d26b-120">These solutions are sufficient for documents that aren't subject to enhanced protections and regulatory requirements.</span></span> <span data-ttu-id="3d26b-121">また、これらのソリューションにより、最も強力な Office 365 サービスを使用できます。DKE 暗号化されたコンテンツでは使用できないサービス。</span><span class="sxs-lookup"><span data-stu-id="3d26b-121">Also, these solutions enable you to use the most powerful Office 365 services; services that you can't use with DKE encrypted content.</span></span> <span data-ttu-id="3d26b-122">例:</span><span class="sxs-lookup"><span data-stu-id="3d26b-122">For example:</span></span>

- <span data-ttu-id="3d26b-123">添付ファイルの表示が必要なマルウェア対策およびスパムを含むトランスポートルール</span><span class="sxs-lookup"><span data-stu-id="3d26b-123">Transport rules including anti-malware and spam that require visibility into the attachment</span></span>
- <span data-ttu-id="3d26b-124">Microsoft Delve</span><span class="sxs-lookup"><span data-stu-id="3d26b-124">Microsoft Delve</span></span>
- <span data-ttu-id="3d26b-125">電子情報開示</span><span class="sxs-lookup"><span data-stu-id="3d26b-125">eDiscovery</span></span>
- <span data-ttu-id="3d26b-126">コンテンツ検索とインデックス作成</span><span class="sxs-lookup"><span data-stu-id="3d26b-126">Content search and indexing</span></span>
- <span data-ttu-id="3d26b-127">共同編集機能を含む Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="3d26b-127">Office Web Apps including co-authoring functionality</span></span>

<span data-ttu-id="3d26b-128">MIP SDK を介して DKE に統合されていない外部アプリケーションまたはサービスは、暗号化されたデータに対してアクションを実行できません。</span><span class="sxs-lookup"><span data-stu-id="3d26b-128">Any external applications or services that are not integrated with DKE through the MIP SDK will be unable to perform actions on the encrypted data.</span></span>

<span data-ttu-id="3d26b-129">Microsoft Information Protection SDK 1.7 以降では、2倍のキー暗号化がサポートされています。SDK と統合されたアプリケーションは、十分なアクセス許可と統合によって、このデータを理由にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-129">The Microsoft Information Protection SDK 1.7+ supports Double Key Encryption; applications that integrate with our SDK will be able to reason over this data with sufficient permissions and integrations in place.</span></span>

<span data-ttu-id="3d26b-130">Microsoft の情報保護機能 (分類とラベル付け) を使用して、機密データの大部分を保護し、ミッションクリティカルなデータに対して DKE のみを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3d26b-130">We recommend organizations use Microsoft Information protection capabilities (classification and labeling) to protect most of their sensitive data and only use DKE for their mission-critical data.</span></span> <span data-ttu-id="3d26b-131">二重キー暗号化は、金融サービスや医療などの高度に規制された業界の非常に機密性の高いデータに特に関連しています。</span><span class="sxs-lookup"><span data-stu-id="3d26b-131">Double Key Encryption is particularly relevant for extremely sensitive data in highly regulated industries such as Financial services and Healthcare.</span></span>

<span data-ttu-id="3d26b-132">組織に次の要件がある場合は、DKE を使用してコンテンツをセキュリティで保護できます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-132">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="3d26b-133">すべての状況で保護されたコンテンツの暗号化を *解除できるよう* にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d26b-133">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="3d26b-134">保護されたデータへのアクセス権を Microsoft に付与しないようにします。</span><span class="sxs-lookup"><span data-stu-id="3d26b-134">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="3d26b-135">地理的な境界内にキーを保持する規制要件があります。</span><span class="sxs-lookup"><span data-stu-id="3d26b-135">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="3d26b-136">データの暗号化と復号化に使用するすべてのキーは、データセンターに保持されます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-136">All of the keys that you hold for data encryption and decryption are maintained in your data center.</span></span>

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="3d26b-137">DKE のシステムおよびライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="3d26b-137">System and licensing requirements for DKE</span></span>

<span data-ttu-id="3d26b-138">**Microsoft 365 の二重キー暗号化には** 、Microsoft 365 E5 および Office 365 E5 が付属しています。</span><span class="sxs-lookup"><span data-stu-id="3d26b-138">**Double Key Encryption for Microsoft 365** comes with Microsoft 365 E5 and Office 365 E5.</span></span> <span data-ttu-id="3d26b-139">Microsoft 365 E5 ライセンスを持っていない場合は、 [試用版](https://aka.ms/M365E5ComplianceTrial)にサインアップできます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-139">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="3d26b-140">これらのライセンスの詳細については、「 [Microsoft 365 licensing ガイダンス for security & 法令遵守](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d26b-140">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="3d26b-141">**Azure Information Protection**。</span><span class="sxs-lookup"><span data-stu-id="3d26b-141">**Azure Information Protection**.</span></span> <span data-ttu-id="3d26b-142">DKE は機密ラベルを使用し、Azure Information Protection を必要とします。</span><span class="sxs-lookup"><span data-stu-id="3d26b-142">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

<span data-ttu-id="3d26b-143">DKE 機密ラベルをエンドユーザーが使用できるようにするには、Office デスクトップアプリの [秘密度リボンを使用する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d26b-143">DKE sensitivity labels are made available to end-users through the sensitivity ribbon in Office Desktop Apps.</span></span> <span data-ttu-id="3d26b-144">保護されたドキュメントを保護して使用する各クライアントコンピューターにこれらの必須コンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3d26b-144">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="3d26b-145">**Microsoft Office Apps for enterprise** バージョン \* 12711 以降 (デスクトップ版の Word、PowerPoint、Excel) (Windows)。</span><span class="sxs-lookup"><span data-stu-id="3d26b-145">**Microsoft Office Apps for enterprise** version \*.12711 or later (Desktop versions of Word, PowerPoint, and Excel) on Windows.</span></span>

<span data-ttu-id="3d26b-146">**Azure Information Protection クライアント** バージョン2.7.93.0 またはそれ以降のラベルを統合しています。</span><span class="sxs-lookup"><span data-stu-id="3d26b-146">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="3d26b-147">[Microsoft ダウンロードセンター](https://www.microsoft.com/download/details.aspx?id=53018)から、統合されたラベル付けクライアントをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="3d26b-147">Download and install the Unified Labeling client from the [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="3d26b-148">DKE で保護されたコンテンツを保存および表示するためにサポートされている環境</span><span class="sxs-lookup"><span data-stu-id="3d26b-148">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="3d26b-149">**サポートされるアプリケーション**。</span><span class="sxs-lookup"><span data-stu-id="3d26b-149">**Supported applications**.</span></span> <span data-ttu-id="3d26b-150">Word、Excel、PowerPoint など、Windows の[エンタープライズクライアント用の Microsoft 365 アプリ](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product)。</span><span class="sxs-lookup"><span data-stu-id="3d26b-150">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="3d26b-151">**オンラインコンテンツのサポート**。</span><span class="sxs-lookup"><span data-stu-id="3d26b-151">**Online content support**.</span></span> <span data-ttu-id="3d26b-152">Microsoft SharePoint と OneDrive for business の両方でオンラインで格納されたドキュメントやファイルはサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3d26b-152">Documents and files stored online in both Microsoft SharePoint and OneDrive for Business are supported.</span></span> <span data-ttu-id="3d26b-153">暗号化されたコンテンツを電子メールで共有することはできますが、暗号化されたドキュメントやファイルをオンラインで表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="3d26b-153">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="3d26b-154">代わりに、ローカルコンピューターのデスクトップアプリを使用して、保護されたコンテンツを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d26b-154">Instead, you must view protected content using the desktop apps on your local computer.</span></span>

## <a name="overview-of-deploying-dke"></a><span data-ttu-id="3d26b-155">DKE の展開の概要</span><span class="sxs-lookup"><span data-stu-id="3d26b-155">Overview of deploying DKE</span></span>

<span data-ttu-id="3d26b-156">DKE をセットアップするには、次の一般的な手順に従います。</span><span class="sxs-lookup"><span data-stu-id="3d26b-156">You'll follow these general steps to set up DKE.</span></span> <span data-ttu-id="3d26b-157">これらの手順を完了すると、エンドユーザーは二重のキー暗号化を使用して機密性の高いデータを保護できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3d26b-157">Once you've completed these steps, your end users will be able to protect your highly sensitive data with Double Key Encryption.</span></span>

1. <span data-ttu-id="3d26b-158">この記事で説明されているように、DKE サービスを展開します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-158">Deploy the DKE service as described in this article.</span></span>

2. <span data-ttu-id="3d26b-159">二重のキー暗号化を使用してラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-159">Create a label with Double Key Encryption.</span></span> <span data-ttu-id="3d26b-160">[Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com)の [情報保護] に移動し、2重のキー暗号化を使用して新しいラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-160">Navigate to Information protection under the [Microsoft 365 compliance center](https://compliance.microsoft.com) and create a new label with Double Key Encryption.</span></span> <span data-ttu-id="3d26b-161">[暗号化を適用するには、「機密ラベルを使用してコンテンツへのアクセスを制限する」を](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d26b-161">See [Restrict access to content by using sensitivity labels to apply encryption](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels).</span></span>

3. <span data-ttu-id="3d26b-162">二重キーの暗号化ラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-162">Use Double Key Encryption labels.</span></span> <span data-ttu-id="3d26b-163">Microsoft Office の [秘密度] リボンから [二重キー暗号化] ラベルを選択して、データを保護します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-163">Protect data by selecting the Double Key Encrypted label from the Sensitivity ribbon in Microsoft Office.</span></span>

<span data-ttu-id="3d26b-164">二重キー暗号化を展開するための手順のいくつかを実行するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="3d26b-164">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="3d26b-165">この記事では、より熟練していない管理者がサービスを正常に展開するための詳細な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-165">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="3d26b-166">使いやすい場合は、独自のメソッドを使用することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-166">If you're comfortable doing so, you can choose to use your own methods.</span></span>

## <a name="deploy-dke"></a><span data-ttu-id="3d26b-167">DKE の展開</span><span class="sxs-lookup"><span data-stu-id="3d26b-167">Deploy DKE</span></span>

<span data-ttu-id="3d26b-168">この記事と展開ビデオでは、DKE サービスの展開先として Azure を使用します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-168">This article and the deployment video use Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="3d26b-169">別の場所に展開している場合は、独自の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d26b-169">If you're deploying to another location, you'll need to provide your own values.</span></span>

<span data-ttu-id="3d26b-170">この記事で説明した概念の詳細な手順については、「 [キー暗号化の展開](https://youtu.be/vDWfHN_kygg) に関するダブルポイント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d26b-170">Watch the [Double Key Encryption deployment video](https://youtu.be/vDWfHN_kygg) to see a step-by-step overview of the concepts in this article.</span></span> <span data-ttu-id="3d26b-171">ビデオの完了に約18分かかります。</span><span class="sxs-lookup"><span data-stu-id="3d26b-171">The video takes about 18 minutes to complete.</span></span>

<span data-ttu-id="3d26b-172">次の一般的な手順に従って、組織のために二重キー暗号化を設定します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-172">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span>

1. [<span data-ttu-id="3d26b-173">DKE サービスの前提条件となるソフトウェアをインストールする</span><span class="sxs-lookup"><span data-stu-id="3d26b-173">Install software prerequisites for the DKE service</span></span>](#install-software-prerequisites-for-the-dke-service)
1. [<span data-ttu-id="3d26b-174">二重キー暗号化 GitHub リポジトリのクローンを作成する</span><span class="sxs-lookup"><span data-stu-id="3d26b-174">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="3d26b-175">アプリケーションの設定を変更する</span><span class="sxs-lookup"><span data-stu-id="3d26b-175">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="3d26b-176">テストキーを生成する</span><span class="sxs-lookup"><span data-stu-id="3d26b-176">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="3d26b-177">プロジェクトをビルドする</span><span class="sxs-lookup"><span data-stu-id="3d26b-177">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="3d26b-178">DKE サービスを展開し、キーストアを発行する</span><span class="sxs-lookup"><span data-stu-id="3d26b-178">Deploy the DKE service and publish the key store</span></span>](#deploy-the-dke-service-and-publish-the-key-store)
1. [<span data-ttu-id="3d26b-179">展開を検証する</span><span class="sxs-lookup"><span data-stu-id="3d26b-179">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="3d26b-180">キーストアを登録する</span><span class="sxs-lookup"><span data-stu-id="3d26b-180">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="3d26b-181">DKE を使用して機密ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="3d26b-181">Create sensitivity labels using DKE</span></span>](#create-sensitivity-labels-using-dke)
1. [<span data-ttu-id="3d26b-182">クライアントで DKE を有効にする</span><span class="sxs-lookup"><span data-stu-id="3d26b-182">Enable DKE in your client</span></span>](#enable-dke-in-your-client)
1. [<span data-ttu-id="3d26b-183">保護されたファイルを HYOK ラベルから DKE ラベルに移行する</span><span class="sxs-lookup"><span data-stu-id="3d26b-183">Migrate protected files from HYOK labels to DKE labels</span></span>](#migrate-protected-files-from-hyok-labels-to-dke-labels)

<span data-ttu-id="3d26b-184">完了すると、DKE を使用してドキュメントやファイルを暗号化できます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-184">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="3d26b-185">詳細については、「 [Office のファイルと電子メールに機密ラベルを適用する](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d26b-185">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites-for-the-dke-service"></a><span data-ttu-id="3d26b-186">DKE サービスの前提条件となるソフトウェアをインストールする</span><span class="sxs-lookup"><span data-stu-id="3d26b-186">Install software prerequisites for the DKE service</span></span>

<span data-ttu-id="3d26b-187">これらの必須コンポーネントを、DKE サービスをインストールするコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="3d26b-187">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="3d26b-188">**.Net Core 3.1 SDK**。</span><span class="sxs-lookup"><span data-stu-id="3d26b-188">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="3d26b-189">SDK をダウンロードしてインストールします。 [.Net Core 3.1 をダウンロード](https://dotnet.microsoft.com/download/dotnet-core/3.1)します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-189">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="3d26b-190">**Visual Studio Code**。</span><span class="sxs-lookup"><span data-stu-id="3d26b-190">**Visual Studio Code**.</span></span> <span data-ttu-id="3d26b-191">から Visual Studio コードをダウンロード [https://code.visualstudio.com/](https://code.visualstudio.com) します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-191">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="3d26b-192">インストールされたら、Visual Studio Code を実行し、[**ビュー**拡張] を選択し \> **Extensions**ます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-192">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="3d26b-193">これらの拡張機能をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3d26b-193">Install these extensions.</span></span>

- <span data-ttu-id="3d26b-194">Visual Studio Code の C#</span><span class="sxs-lookup"><span data-stu-id="3d26b-194">C# for Visual Studio Code</span></span>

- <span data-ttu-id="3d26b-195">NuGet パッケージマネージャー</span><span class="sxs-lookup"><span data-stu-id="3d26b-195">NuGet Package Manager</span></span>

<span data-ttu-id="3d26b-196">**Git リソース**。</span><span class="sxs-lookup"><span data-stu-id="3d26b-196">**Git resources**.</span></span> <span data-ttu-id="3d26b-197">次のいずれかをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="3d26b-197">Download and install one of the following.</span></span>

- [<span data-ttu-id="3d26b-198">Git</span><span class="sxs-lookup"><span data-stu-id="3d26b-198">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="3d26b-199">GitHub デスクトップ</span><span class="sxs-lookup"><span data-stu-id="3d26b-199">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="3d26b-200">GitHub Enterprise</span><span class="sxs-lookup"><span data-stu-id="3d26b-200">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="3d26b-201">**OpenSSL**DKE の展開後に[テストキーを生成](#generate-test-keys)するには、 [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html)がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d26b-201">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="3d26b-202">環境変数のパスから適切に呼び出していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3d26b-202">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="3d26b-203">たとえば、詳細については、「」の「インストールディレクトリをパスに追加する」を参照してください [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) 。</span><span class="sxs-lookup"><span data-stu-id="3d26b-203">For example, see "Add the installation directory to PATH" at [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) for details.</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="3d26b-204">DKE GitHub リポジトリのクローンを作成する</span><span class="sxs-lookup"><span data-stu-id="3d26b-204">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="3d26b-205">Microsoft は、GitHub リポジトリに DKE ソースファイルを提供しています。</span><span class="sxs-lookup"><span data-stu-id="3d26b-205">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="3d26b-206">リポジトリを複製して、組織の使用に合わせてプロジェクトをローカルに構築します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-206">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="3d26b-207">DKE GitHub リポジトリは、にあり [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) ます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-207">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="3d26b-208">次の手順は、経験のない git または Visual Studio Code ユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="3d26b-208">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="3d26b-209">ブラウザーで、に移動 [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-209">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

2. <span data-ttu-id="3d26b-210">画面の右側にある [ **コード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-210">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="3d26b-211">使用しているバージョンの UI には、[ **クローン] または [ダウンロード** ] ボタンが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="3d26b-211">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="3d26b-212">次に、表示されたドロップダウンで、[コピー] アイコンを選択して、URL をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="3d26b-212">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="3d26b-213">例:</span><span class="sxs-lookup"><span data-stu-id="3d26b-213">For example:</span></span>

   ![GitHub から二重キー暗号化サービスリポジトリを複製する](../media/dke-clone.png)

3. <span data-ttu-id="3d26b-215">Visual Studio Code で、[ **View** \> **Command Palette** ] を選択し、[ **Git: Clone**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-215">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="3d26b-216">一覧のオプションに移動するには、入力を開始して `git: clone` エントリをフィルター処理し、ドロップダウンから選択します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-216">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="3d26b-217">例:</span><span class="sxs-lookup"><span data-stu-id="3d26b-217">For example:</span></span>

   ![Visual Studio Code GIT: Clone オプション](../media/dke-vscode-clone.png)

4. <span data-ttu-id="3d26b-219">テキストボックスに、Git からコピーした URL を貼り付けて、[ **GitHub から複製**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-219">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="3d26b-220">表示される **[フォルダーの選択** ] ダイアログで、リポジトリを格納する場所を参照して選択します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-220">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="3d26b-221">プロンプトで、[ **開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-221">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="3d26b-222">リポジトリが Visual Studio Code で開き、左下に現在の Git ブランチが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-222">The repository opens in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="3d26b-223">ブランチは **master**である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d26b-223">The branch should be **master**.</span></span>

    <span data-ttu-id="3d26b-224">例:</span><span class="sxs-lookup"><span data-stu-id="3d26b-224">For example:</span></span>

   ![Visual Studio Code master 分岐](../media/dke-vscode-master.png)

6. <span data-ttu-id="3d26b-226">ブランチのリストから [単語 **マスター** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-226">Select the word **master** from the list of branches.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="3d26b-227">マスター分岐を選択すると、プロジェクトをビルドするための適切なファイルがあることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-227">Selecting the master branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="3d26b-228">適切なブランチを選択しない場合、展開は失敗します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-228">If you do not choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="3d26b-229">これで、DKE ソースリポジトリがローカルに設定されました。</span><span class="sxs-lookup"><span data-stu-id="3d26b-229">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="3d26b-230">次に、組織の [アプリケーション設定を変更](#modify-application-settings) します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-230">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="3d26b-231">アプリケーションの設定を変更する</span><span class="sxs-lookup"><span data-stu-id="3d26b-231">Modify application settings</span></span>

<span data-ttu-id="3d26b-232">DKE サービスを展開するには、次の種類のアプリケーション設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d26b-232">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="3d26b-233">キーアクセス設定</span><span class="sxs-lookup"><span data-stu-id="3d26b-233">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="3d26b-234">テナントとキーの設定</span><span class="sxs-lookup"><span data-stu-id="3d26b-234">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="3d26b-235">[ファイル] の appsettings.jsで、アプリケーションの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-235">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="3d26b-236">このファイルは、DoubleKeyEncryptionService\src\customer-key-store. でローカルに複製した DoubleKeyEncryptionService リポジトリにあります。</span><span class="sxs-lookup"><span data-stu-id="3d26b-236">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="3d26b-237">たとえば、次の図に示すように、Visual Studio Code でファイルを参照できます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-237">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

![DKE のファイルの appsettings.jsを検索します。](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a><span data-ttu-id="3d26b-239">キーアクセス設定</span><span class="sxs-lookup"><span data-stu-id="3d26b-239">Key access settings</span></span>

<span data-ttu-id="3d26b-240">メールまたはロールの承認を使用するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-240">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="3d26b-241">DKE は、一度に1つの認証方法のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="3d26b-241">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="3d26b-242">**電子メールの承認**。</span><span class="sxs-lookup"><span data-stu-id="3d26b-242">**Email authorization**.</span></span> <span data-ttu-id="3d26b-243">組織は、電子メールアドレスのみに基づいてキーへのアクセスを承認できます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-243">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="3d26b-244">**役割の承認**。</span><span class="sxs-lookup"><span data-stu-id="3d26b-244">**Role authorization**.</span></span> <span data-ttu-id="3d26b-245">組織は、Active Directory グループに基づいてキーへのアクセスを承認でき、web サービスが LDAP を照会できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d26b-245">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="3d26b-246">**電子メール認証を使用して DKE のキーアクセス設定を設定するには**</span><span class="sxs-lookup"><span data-stu-id="3d26b-246">**To set key access settings for DKE using email authorization**</span></span>

1. <span data-ttu-id="3d26b-247">ファイル \*\* でappsettings.js\*\* を開き、設定を探し `AuthorizedEmailAddress` ます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-247">Open the **appsettings.json** file and locate the `AuthorizedEmailAddress` setting.</span></span>

2. <span data-ttu-id="3d26b-248">承認するメールアドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-248">Add the email address or addresses that you want to authorize.</span></span> <span data-ttu-id="3d26b-249">複数の電子メールアドレスは、二重引用符とコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="3d26b-249">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="3d26b-250">例:</span><span class="sxs-lookup"><span data-stu-id="3d26b-250">For example:</span></span>

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. <span data-ttu-id="3d26b-251">設定を検索 `LDAPPath` し、 `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` 二重引用符の間のテキストを削除します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-251">Locate the `LDAPPath` setting and remove the text `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` between the double quotes.</span></span> <span data-ttu-id="3d26b-252">二重引用符はそのままにします。</span><span class="sxs-lookup"><span data-stu-id="3d26b-252">Leave the double quotes in place.</span></span> <span data-ttu-id="3d26b-253">完了すると、設定は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3d26b-253">When you're finished, the setting should look like this.</span></span>

   ```json
   "LDAPPath": ""
   ```

4. <span data-ttu-id="3d26b-254">設定を検索 `AuthorizedRoles` し、行全体を削除します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-254">Locate the `AuthorizedRoles` setting and delete the entire line.</span></span>

<span data-ttu-id="3d26b-255">このイメージは、電子メールの承認用に正しく書式設定されたファイル \*\* のappsettings.js\*\* を示しています。</span><span class="sxs-lookup"><span data-stu-id="3d26b-255">This image shows the **appsettings.json** file correctly formatted for email authorization.</span></span>

   ![電子メール認証方法が表示されているファイルの appsettings.js](../media/dke-email-accesssetting.png)

<span data-ttu-id="3d26b-257">**ロール認証を使用して DKE のキーアクセス設定を設定するには**</span><span class="sxs-lookup"><span data-stu-id="3d26b-257">**To set key access settings for DKE using role authorization**</span></span>

1. <span data-ttu-id="3d26b-258">ファイル \*\* でappsettings.js\*\* を開き、設定を探し `AuthorizedRoles` ます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-258">Open the **appsettings.json** file and locate the `AuthorizedRoles` setting.</span></span>

2. <span data-ttu-id="3d26b-259">承認する Active Directory グループ名を追加します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-259">Add the Active Directory group names you want to authorize.</span></span> <span data-ttu-id="3d26b-260">複数のグループ名は、二重引用符とコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="3d26b-260">Separate multiple group names with double quotes and commas.</span></span> <span data-ttu-id="3d26b-261">例:</span><span class="sxs-lookup"><span data-stu-id="3d26b-261">For example:</span></span>

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. <span data-ttu-id="3d26b-262">`LDAPPath`設定を見つけて、Active Directory ドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-262">Locate the `LDAPPath` setting and add the Active Directory domain.</span></span> <span data-ttu-id="3d26b-263">例:</span><span class="sxs-lookup"><span data-stu-id="3d26b-263">For example:</span></span>

   ```json
   "LDAPPath": "contoso.com"
   ```

4. <span data-ttu-id="3d26b-264">設定を検索 `AuthorizedEmailAddress` し、行全体を削除します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-264">Locate the `AuthorizedEmailAddress` setting and delete the entire line.</span></span>

<span data-ttu-id="3d26b-265">このイメージは、役割承認用に正しく書式設定されたファイル \*\* のappsettings.js\*\* を示しています。</span><span class="sxs-lookup"><span data-stu-id="3d26b-265">This image shows the **appsettings.json** file correctly formatted for role authorization.</span></span>

   ![ロール認証方法が表示されているファイルの appsettings.js](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="3d26b-267">テナントとキーの設定</span><span class="sxs-lookup"><span data-stu-id="3d26b-267">Tenant and key settings</span></span>

<span data-ttu-id="3d26b-268">DKE テナントとキー設定は、ファイルの **appsettings.js** にあります。</span><span class="sxs-lookup"><span data-stu-id="3d26b-268">DKE tenant and key settings are located in the **appsettings.json** file.</span></span>

<span data-ttu-id="3d26b-269">**DKE のテナントとキー設定を構成するには**</span><span class="sxs-lookup"><span data-stu-id="3d26b-269">**To configure tenant and key settings for DKE**</span></span>

1. <span data-ttu-id="3d26b-270">ファイル \*\* でappsettings.js\*\* を開きます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-270">Open the **appsettings.json** file.</span></span>

2. <span data-ttu-id="3d26b-271">`ValidIssuers`設定を見つけて、 `<tenantid>` テナント ID に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-271">Locate the `ValidIssuers` setting and replace `<tenantid>` with your tenant ID.</span></span> <span data-ttu-id="3d26b-272">Azure ポータルに移動して、 [テナントのプロパティ](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)を表示することによって、テナント ID を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-272">You can locate your tenant ID by going to the Azure portal and viewing the [tenant properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="3d26b-273">例:</span><span class="sxs-lookup"><span data-stu-id="3d26b-273">For example:</span></span>

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

<span data-ttu-id="3d26b-274">を探し `JwtAudience` ます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-274">Locate the `JwtAudience`.</span></span> <span data-ttu-id="3d26b-275">を、 `<yourhostname>` DKE サービスが実行されるコンピューターのホスト名に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-275">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span> <span data-ttu-id="3d26b-276">例:</span><span class="sxs-lookup"><span data-stu-id="3d26b-276">For example:</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="3d26b-277">の値は、 `JwtAudience` ホストの名前と *正確*に一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d26b-277">The value for `JwtAudience` must match the name of your host *exactly*.</span></span> <span data-ttu-id="3d26b-278">デバッグ中に **localhost: 5001** を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-278">You may use **localhost:5001** while debugging.</span></span> <span data-ttu-id="3d26b-279">ただし、デバッグを完了したら、この値をサーバーのホスト名に更新するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="3d26b-279">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="3d26b-280">`TestKeys:Name`.</span><span class="sxs-lookup"><span data-stu-id="3d26b-280">`TestKeys:Name`.</span></span> <span data-ttu-id="3d26b-281">キーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-281">Enter a name for your key.</span></span> <span data-ttu-id="3d26b-282">例: `TestKey1`</span><span class="sxs-lookup"><span data-stu-id="3d26b-282">For example: `TestKey1`</span></span>
- <span data-ttu-id="3d26b-283">`TestKeys:Id`.</span><span class="sxs-lookup"><span data-stu-id="3d26b-283">`TestKeys:Id`.</span></span> <span data-ttu-id="3d26b-284">GUID を作成し、値として入力し `TestKeys:ID` ます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-284">Create a GUID and enter it as the `TestKeys:ID` value.</span></span> <span data-ttu-id="3d26b-285">たとえば、`DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE` などです。</span><span class="sxs-lookup"><span data-stu-id="3d26b-285">For example, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span></span> <span data-ttu-id="3d26b-286">[ONLINE Guid ジェネレーター](https://guidgenerator.com/)のようなサイトを使用して、guid をランダムに生成することができます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-286">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

<span data-ttu-id="3d26b-287">この画像 \*\* にはappsettings.js\*\*のテナントとキーの設定の正しい形式が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-287">This image shows the correct format for tenant and keys settings in **appsettings.json**.</span></span> <span data-ttu-id="3d26b-288">`LDAPPath` は、ロールの承認のために構成されています。</span><span class="sxs-lookup"><span data-stu-id="3d26b-288">`LDAPPath` is configured for role authorization.</span></span>

![ファイルの appsettings.jsの DKE の正しいテナントとキー設定を示します。](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a><span data-ttu-id="3d26b-290">テストキーを生成する</span><span class="sxs-lookup"><span data-stu-id="3d26b-290">Generate test keys</span></span>

<span data-ttu-id="3d26b-291">アプリケーション設定を定義したら、パブリックおよびプライベートのテストキーを生成する準備ができています。</span><span class="sxs-lookup"><span data-stu-id="3d26b-291">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="3d26b-292">キーを生成するには</span><span class="sxs-lookup"><span data-stu-id="3d26b-292">To generate keys:</span></span>

1. <span data-ttu-id="3d26b-293">Windows の [スタート] メニューから、OpenSSL コマンドプロンプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-293">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

2. <span data-ttu-id="3d26b-294">テストキーを保存するフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-294">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="3d26b-295">このタスクの手順を完了することによって作成したファイルは、同じフォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-295">The files you create by completing the steps in this task are stored in the same folder.</span></span>

3. <span data-ttu-id="3d26b-296">新しいテストキーを生成します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-296">Generate the new test key.</span></span>

   ```dos
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

4. <span data-ttu-id="3d26b-297">秘密キーを生成します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-297">Generate the private key.</span></span>

   ```dos
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

5. <span data-ttu-id="3d26b-298">公開キーを生成します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-298">Generate the public key.</span></span>

   ```dos
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

6. <span data-ttu-id="3d26b-299">テキストエディターで、 **pubkeyonly**を開きます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-299">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="3d26b-300">最初と最後の行を除く、 **pubkeyonly** のすべてのコンテンツを `PublicPem` ファイルの **appsettings.js** のセクションにコピーします。</span><span class="sxs-lookup"><span data-stu-id="3d26b-300">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the `PublicPem` section of the **appsettings.json** file.</span></span>

7. <span data-ttu-id="3d26b-301">テキストエディターで、 **privkeynopass pem**を開きます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-301">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="3d26b-302">最初の行と最後の行を除いて、 **privkeynopass** のすべてのコンテンツを `PrivatePem` ファイルの **appsettings.js** のセクションにコピーします。</span><span class="sxs-lookup"><span data-stu-id="3d26b-302">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the `PrivatePem` section of the **appsettings.json** file.</span></span>

8. <span data-ttu-id="3d26b-303">セクションとセクションの両方で空白スペースと改行を削除し `PublicPem` `PrivatePem` ます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-303">Remove all blank spaces and newlines in both the `PublicPem` and `PrivatePem` sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="3d26b-304">このコンテンツをコピーする場合は、PEM データを削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="3d26b-304">When you copy this content, do not delete any of the PEM data.</span></span>

9. <span data-ttu-id="3d26b-305">Visual Studio Code で、 **Startup.cs** ファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-305">In Visual Studio Code, browse to the **Startup.cs** file.</span></span> <span data-ttu-id="3d26b-306">このファイルは、DoubleKeyEncryptionService\src\customer-key-store\. でローカルに複製した DoubleKeyEncryptionService リポジトリにあります。</span><span class="sxs-lookup"><span data-stu-id="3d26b-306">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store\.</span></span>

10. <span data-ttu-id="3d26b-307">次の行を見つけます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-307">Locate the following lines:</span></span>

   ```c#
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
   ```

11. <span data-ttu-id="3d26b-308">これらの行を次のテキストに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-308">Replace these lines with the following text:</span></span>

   ```csharp
   services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
   ```

   <span data-ttu-id="3d26b-309">最終結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3d26b-309">The end results should look similar to the following.</span></span>

   ![パブリックプレビュー用の startup.cs ファイル](../media/dke-startupcs-usetestkeys.png)

<span data-ttu-id="3d26b-311">これで [、DKE プロジェクトを構築](#build-the-project)する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="3d26b-311">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="3d26b-312">プロジェクトをビルドする</span><span class="sxs-lookup"><span data-stu-id="3d26b-312">Build the project</span></span>

<span data-ttu-id="3d26b-313">次の手順を使用して、ローカルに DKE プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="3d26b-313">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="3d26b-314">Visual Studio Code の dke サービスリポジトリで、[コマンドパレットの**表示**] を選択し、 \> **Command Palette**プロンプトで「 **build** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-314">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

2. <span data-ttu-id="3d26b-315">リストから、[ **タスク: ビルドタスクの実行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-315">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="3d26b-316">ビルドタスクが見つからない場合は、[ **ビルドタスクの構成** ] を選択し、次のように .net コア用のタスクを作成します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-316">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   ![.NET の不明なビルドタスクを構成する](../media/dke-configurebuildtask.png)

   1. <span data-ttu-id="3d26b-318">[ **テンプレートから tasks.jsを作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-318">Choose **Create tasks.json from template**.</span></span>

      ![DKE テンプレートからファイルに tasks.jsを作成する](../media/dke-createtasksjsonfromtemplate.png)

   2. <span data-ttu-id="3d26b-320">テンプレートの種類の一覧から [ **.Net Core**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-320">From the list of template types, select **.NET Core**.</span></span>

      ![DKE の正しいテンプレートを選択する](../media/dke-tasksjsontemplate.png)

   3. <span data-ttu-id="3d26b-322">[ビルド] セクションで、 **顧客キーストア** ファイルへのパスを見つけます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-322">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="3d26b-323">存在しない場合は、次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-323">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

   4. <span data-ttu-id="3d26b-324">ビルドを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-324">Run the build again.</span></span>

3. <span data-ttu-id="3d26b-325">出力ウィンドウに赤のエラーが表示されないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-325">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="3d26b-326">赤のエラーがある場合は、コンソール出力を確認します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-326">If there are red errors, check the console output.</span></span> <span data-ttu-id="3d26b-327">上記の手順がすべて正常に完了し、適切なビルドバージョンが存在することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3d26b-327">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

4. <span data-ttu-id="3d26b-328">[ **実行** \> **開始デバッグ** ] を選択してプロセスをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="3d26b-328">Select **Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="3d26b-329">環境を選択するように求めるメッセージが表示されたら、[ **.net core**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-329">If you're prompted to select an environment, select **.NET core**.</span></span>

<span data-ttu-id="3d26b-330">.NET コアデバッガーは通常、に起動し `https://localhost:5001` ます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-330">The .NET core debugger typically launches to `https://localhost:5001`.</span></span> <span data-ttu-id="3d26b-331">テストキーを表示するには、に移動して、 `https://localhost:5001` スラッシュ (/) とキーの名前を追加します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-331">To view your test key, go to `https://localhost:5001` and append a forward slash (/) and the name of your key.</span></span> <span data-ttu-id="3d26b-332">例:</span><span class="sxs-lookup"><span data-stu-id="3d26b-332">For example:</span></span>

```https
https://localhost:5001/TestKey1
```

<span data-ttu-id="3d26b-333">キーは JSON 形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-333">The key should display in JSON format.</span></span>

<span data-ttu-id="3d26b-334">セットアップが完了しました。</span><span class="sxs-lookup"><span data-stu-id="3d26b-334">Your setup is now complete.</span></span> <span data-ttu-id="3d26b-335">キーストアを発行する前に、JwtAudience の設定 appsettings.jsで、[] 設定で、[ホスト名] の値が App Service ホスト名と正確に一致していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3d26b-335">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="3d26b-336">ビルドのトラブルシューティングを行うために、localhost に変更した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3d26b-336">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="deploy-the-dke-service-and-publish-the-key-store"></a><span data-ttu-id="3d26b-337">DKE サービスを展開し、キーストアを発行する</span><span class="sxs-lookup"><span data-stu-id="3d26b-337">Deploy the DKE service and publish the key store</span></span>

<span data-ttu-id="3d26b-338">運用環境の展開では、サービスをサードパーティ製のクラウドに展開するか、 [オンプレミスのシステムに発行](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&preserve-view=true&tabs=netcore-cli)します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-338">For production deployments, deploy the service either in a third-party cloud or [publish to an on-premises system](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&preserve-view=true&tabs=netcore-cli).</span></span>

<span data-ttu-id="3d26b-339">他の方法でキーを展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-339">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="3d26b-340">組織に最も適した方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-340">Select the method that works best for your organization.</span></span>

<span data-ttu-id="3d26b-341">パイロット展開の場合は、Azure に展開し、すぐに作業を開始できます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-341">For pilot deployments, you can deploy in Azure and get started right away.</span></span>

<span data-ttu-id="3d26b-342">**DKE 展開をホストするための Azure Web App インスタンスを作成するには**</span><span class="sxs-lookup"><span data-stu-id="3d26b-342">**To create an Azure Web App instance to host your DKE deployment**</span></span>

<span data-ttu-id="3d26b-343">キーストアを発行するには、DKE 展開をホストする Azure App Service インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-343">To publish the key store, you'll create an Azure App Service instance to host your DKE deployment.</span></span> <span data-ttu-id="3d26b-344">次に、生成されたキーを Azure に発行します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-344">Next, you'll publish your generated keys to Azure.</span></span>

1. <span data-ttu-id="3d26b-345">ブラウザーで、 [Microsoft Azure ポータル](https://ms.portal.azure.com)にサインインし、[ **App Services**追加] に移動し  >  **Add**ます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-345">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

2. <span data-ttu-id="3d26b-346">サブスクリプションとリソースグループを選択し、インスタンスの詳細を定義します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-346">Select your subscription and resource group and define your instance details.</span></span>

    - <span data-ttu-id="3d26b-347">DKE サービスをインストールするコンピューターのホスト名を入力します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-347">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="3d26b-348">[ファイルのappsettings.js] の [\*\* [\*\*](#tenant-and-key-settings) JwtAudience] 設定に定義されている名前と同じ名前であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3d26b-348">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="3d26b-349">名前に指定する値は WebAppInstanceName でもあります。</span><span class="sxs-lookup"><span data-stu-id="3d26b-349">The value you provide for the name is also the WebAppInstanceName.</span></span>

    - <span data-ttu-id="3d26b-350">[ **発行**] で、[ **コード**] を選択し、[ **ランタイムスタック**] で [ **.net Core 3.1**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-350">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

    <span data-ttu-id="3d26b-351">例:</span><span class="sxs-lookup"><span data-stu-id="3d26b-351">For example:</span></span>

   ![アプリサービスを追加する](../media/dke-azure-add-app-service.png)

3. <span data-ttu-id="3d26b-353">ページの下部にある [ **レビュー + 作成**] を選択し、[ **追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-353">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

4. <span data-ttu-id="3d26b-354">生成されたキーを公開するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3d26b-354">Do one of the following to publish your generated keys:</span></span>

    - [<span data-ttu-id="3d26b-355">ZipDeployUI を使用して発行する</span><span class="sxs-lookup"><span data-stu-id="3d26b-355">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
    - [<span data-ttu-id="3d26b-356">FTP を使用した発行</span><span class="sxs-lookup"><span data-stu-id="3d26b-356">Publish via FTP</span></span>](#publish-via-ftp)
    - [<span data-ttu-id="3d26b-357">Visual Studio 2019 以降での発行</span><span class="sxs-lookup"><span data-stu-id="3d26b-357">Publish via Visual Studio 2019 or later</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/)

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="3d26b-358">ZipDeployUI を使用して発行する</span><span class="sxs-lookup"><span data-stu-id="3d26b-358">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="3d26b-359">`https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI` に移動します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-359">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

    <span data-ttu-id="3d26b-360">例: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="3d26b-360">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

2. <span data-ttu-id="3d26b-361">キーストアのコードベースで、 **customer-key-store\src\customer-key-store** フォルダーに移動し、このフォルダーに **顧客キーストア** ファイルが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-361">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

3. <span data-ttu-id="3d26b-362">実行: **dotnet publish**</span><span class="sxs-lookup"><span data-stu-id="3d26b-362">Run: **dotnet publish**</span></span>

     <span data-ttu-id="3d26b-363">[出力] ウィンドウには、発行が展開されたディレクトリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-363">The output window displays the directory where the publish was deployed.</span></span>

    <span data-ttu-id="3d26b-364">例: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="3d26b-364">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

4. <span data-ttu-id="3d26b-365">Publish ディレクトリ内のすべてのファイルを .zip ファイルに送信します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-365">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="3d26b-366">.Zip ファイルを作成するときは、ディレクトリ内のすべてのファイルが .zip ファイルのルートレベルにあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3d26b-366">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

5. <span data-ttu-id="3d26b-367">先ほど開いた ZipDeployUI サイトに、作成した .zip ファイルをドラッグアンドドロップします。</span><span class="sxs-lookup"><span data-stu-id="3d26b-367">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="3d26b-368">例: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="3d26b-368">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="3d26b-369">DKE が展開されており、作成したテストキーを参照することができます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-369">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="3d26b-370">引き続き「 [展開を検証](#validate-your-deployment) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d26b-370">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="3d26b-371">FTP を使用した発行</span><span class="sxs-lookup"><span data-stu-id="3d26b-371">Publish via FTP</span></span>

1. <span data-ttu-id="3d26b-372">[上記の手順](#deploy-the-dke-service-and-publish-the-key-store)で作成した App Service に接続します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-372">Connect to the App Service you created [above](#deploy-the-dke-service-and-publish-the-key-store).</span></span>

    <span data-ttu-id="3d26b-373">ブラウザーで、「 **Azure portal**  >  **App Service**  >  **Deployment Center**  >  **Manual Deployment**  >  **FTP**  >  **Dashboard**」に移動します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-373">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

2. <span data-ttu-id="3d26b-374">ローカルファイルに表示される接続文字列をコピーします。</span><span class="sxs-lookup"><span data-stu-id="3d26b-374">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="3d26b-375">これらの文字列を使用して Web App サービスに接続し、FTP を使用してファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="3d26b-375">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

    <span data-ttu-id="3d26b-376">例:</span><span class="sxs-lookup"><span data-stu-id="3d26b-376">For example:</span></span>

   ![FTP ダッシュボードから接続文字列をコピーする](../media/dke-ftp-dashboard.png)

3. <span data-ttu-id="3d26b-378">キーの格納用のコードベースで、 **customer-key-store\src\customer-key-store ディレクトリ**に移動します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-378">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

4. <span data-ttu-id="3d26b-379">このディレクトリに、 **顧客キーストアの .csproj** ファイルが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-379">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

5. <span data-ttu-id="3d26b-380">実行: **dotnet publish**</span><span class="sxs-lookup"><span data-stu-id="3d26b-380">Run: **dotnet publish**</span></span>

    <span data-ttu-id="3d26b-381">この出力には、発行が展開されたディレクトリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3d26b-381">The output contains the directory where the publish was deployed.</span></span>

    <span data-ttu-id="3d26b-382">例: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="3d26b-382">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

6. <span data-ttu-id="3d26b-383">発行ディレクトリ内のすべてのファイルを zip ファイルに送信します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-383">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="3d26b-384">.Zip ファイルを作成するときは、ディレクトリ内のすべてのファイルが .zip ファイルのルートレベルにあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3d26b-384">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

7. <span data-ttu-id="3d26b-385">FTP クライアントから、コピーした接続情報を使用して App Service に接続します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-385">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="3d26b-386">前の手順で作成した .zip ファイルを Web アプリのルートディレクトリにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="3d26b-386">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="3d26b-387">DKE が展開されており、作成したテストキーを参照することができます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-387">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="3d26b-388">次に、 [展開を検証](#validate-your-deployment)します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-388">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="3d26b-389">展開を検証する</span><span class="sxs-lookup"><span data-stu-id="3d26b-389">Validate your deployment</span></span>

<span data-ttu-id="3d26b-390">前述の方法のいずれかを使用して DKE を展開した後、展開とキーストアの設定を検証します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-390">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="3d26b-391">実行</span><span class="sxs-lookup"><span data-stu-id="3d26b-391">Run:</span></span>

<span data-ttu-id="3d26b-392">src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey</span><span class="sxs-lookup"><span data-stu-id="3d26b-392">src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey</span></span>

<span data-ttu-id="3d26b-393">例:</span><span class="sxs-lookup"><span data-stu-id="3d26b-393">For example:</span></span>

<span data-ttu-id="3d26b-394">key_store_tester.ps1 https://mydkeservice.com/mykey</span><span class="sxs-lookup"><span data-stu-id="3d26b-394">key_store_tester.ps1 https://mydkeservice.com/mykey</span></span>

<span data-ttu-id="3d26b-395">出力にエラーが表示されないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-395">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="3d26b-396">準備が整ったら、 [キーストアを登録](#register-your-key-store)します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-396">When you're ready, [register your key store](#register-your-key-store).</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="3d26b-397">キーストアを登録する</span><span class="sxs-lookup"><span data-stu-id="3d26b-397">Register your key store</span></span>

<span data-ttu-id="3d26b-398">次の手順に従って、DKE サービスを登録できます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-398">The following steps enable you to register your DKE service.</span></span> <span data-ttu-id="3d26b-399">Dke サービスの登録は、ラベルの作成を開始する前に DKE を展開するための最後の手順です。</span><span class="sxs-lookup"><span data-stu-id="3d26b-399">Registering your DKE service is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="3d26b-400">DKE サービスを登録するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="3d26b-400">To register the DKE service:</span></span>

1. <span data-ttu-id="3d26b-401">ブラウザーで、 [Microsoft Azure portal](https://ms.portal.azure.com/)を開き、[ **すべてのサービス** \> **id** \> **アプリの登録**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-401">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="3d26b-402">[ **新しい登録**] を選択し、わかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-402">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="3d26b-403">表示されているオプションから、アカウントの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-403">Select an account type from the options displayed.</span></span>

    <span data-ttu-id="3d26b-404">**Onmicrosoft.com**などの非ユーザー設定ドメインを使用して Microsoft Azure を使用している場合は、[**この組織ディレクトリ内のアカウントのみ (microsoft のみ)** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-404">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

    <span data-ttu-id="3d26b-405">例:</span><span class="sxs-lookup"><span data-stu-id="3d26b-405">For example:</span></span>

   ![新しいアプリの登録](../media/dke-app-registration.png)

4. <span data-ttu-id="3d26b-407">ページの下部にある [ **登録** ] を選択して、新しいアプリの登録を作成します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-407">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="3d26b-408">新しいアプリの登録で、左側のウィンドウの [ **管理**] で [ **認証**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-408">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="3d26b-409">[ **プラットフォームの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-409">Select **Add a platform**.</span></span>

7. <span data-ttu-id="3d26b-410">[ **プラットフォームの構成** ] ポップアップで、[ **Web**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-410">On the **Configure platforms** popup, select **Web**.</span></span>

8. <span data-ttu-id="3d26b-411">[ **リダイレクト uri**] で、二重キー暗号化サービスの URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-411">Under **Redirect URIs**, enter the URI of your double key encryption service.</span></span> <span data-ttu-id="3d26b-412">ホスト名とドメインの両方を含む、App Service の URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-412">Enter the App Service URL, including both the hostname and domain.</span></span>

    <span data-ttu-id="3d26b-413">例: https://mydkeservicetest.com</span><span class="sxs-lookup"><span data-stu-id="3d26b-413">For example: https://mydkeservicetest.com</span></span>

    - <span data-ttu-id="3d26b-414">入力する URL は、DKE サービスが展開されているホスト名と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d26b-414">The URL you enter must match the hostname where your DKE service is deployed.</span></span>
    - <span data-ttu-id="3d26b-415">Visual Studio を使用してローカルでテストしている場合は、を使用 **https://localhost:5001** します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-415">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
    - <span data-ttu-id="3d26b-416">すべての場合において、スキームは **https**である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d26b-416">In all cases, the scheme must be **https**.</span></span>

    <span data-ttu-id="3d26b-417">ホスト名が App Service ホスト名と正確に一致していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-417">Ensure the hostname exactly matches your App Service hostname.</span></span> <span data-ttu-id="3d26b-418">ビルドをトラブルシューティングするために、に変更した可能性があり `localhost` ます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-418">You may have changed it to `localhost` to troubleshoot the build.</span></span> <span data-ttu-id="3d26b-419">**appsettings.js**の場合、この値は、に設定したホスト名です `JwtAudience` 。</span><span class="sxs-lookup"><span data-stu-id="3d26b-419">In **appsettings.json**, this value is the hostname you set for `JwtAudience`.</span></span>

9. <span data-ttu-id="3d26b-420">[ **暗黙的な付与**] で、[ **ID トークン** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3d26b-420">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

10. <span data-ttu-id="3d26b-421">**[保存]** を選択し、変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-421">Select **Save** to save your changes.</span></span>

11. <span data-ttu-id="3d26b-422">左側のウィンドウで、[ **API の公開**] を選択し、[アプリケーション ID URI] の横にある [ **設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-422">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

12. <span data-ttu-id="3d26b-423">引き続き [ **api の公開** ] ページで、[ **この api によって定義されるスコープ** ] 領域の [ **範囲の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-423">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="3d26b-424">新しい範囲の場合:</span><span class="sxs-lookup"><span data-stu-id="3d26b-424">In the new scope:</span></span>

    1. <span data-ttu-id="3d26b-425">スコープ名を **user_impersonation**として定義します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-425">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="3d26b-426">同意できる管理者とユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-426">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="3d26b-427">残りの必要な値を定義します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-427">Define any remaining values required.</span></span>

    4. <span data-ttu-id="3d26b-428">**[スコープの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-428">Select **Add scope**.</span></span>

    5. <span data-ttu-id="3d26b-429">上部にある [ **保存** ] を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-429">Select **Save** at the top to save your changes.</span></span>

13. <span data-ttu-id="3d26b-430">引き続き [ **API の公開** ] ページの [承認された **クライアントアプリケーション** ] 領域で、[ **クライアントアプリケーションの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-430">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="3d26b-431">新しいクライアントアプリケーションの場合:</span><span class="sxs-lookup"><span data-stu-id="3d26b-431">In the new client application:</span></span>

    1. <span data-ttu-id="3d26b-432">クライアント ID を **d3590ed6-52b3-4102-aeff-aad2292ab01c**として定義します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-432">Define the Client ID as **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span></span> <span data-ttu-id="3d26b-433">この値は Microsoft Office クライアント ID であり、Office はキーストアのアクセストークンを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-433">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="3d26b-434">[ **承認**されたスコープ] で、 **user_impersonation** スコープを選択します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-434">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="3d26b-435">**[アプリケーションの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-435">Select **Add application**.</span></span>

    4. <span data-ttu-id="3d26b-436">上部にある [ **保存** ] を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-436">Select **Save** at the top to save your changes.</span></span>

<span data-ttu-id="3d26b-437">これで、DKE サービスが登録されました。</span><span class="sxs-lookup"><span data-stu-id="3d26b-437">Your DKE service is now registered.</span></span> <span data-ttu-id="3d26b-438">引き続き、 [DKE を使用してラベルを作成](#create-sensitivity-labels-using-dke)します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-438">Continue by [creating labels using DKE](#create-sensitivity-labels-using-dke).</span></span>

## <a name="create-sensitivity-labels-using-dke"></a><span data-ttu-id="3d26b-439">DKE を使用して機密ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="3d26b-439">Create sensitivity labels using DKE</span></span>

<span data-ttu-id="3d26b-440">Microsoft 365 コンプライアンスセンターで、別の方法として、新しい機密ラベルを作成し、暗号化を適用します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-440">In the Microsoft 365 compliance center, create a new sensitivity label and apply encryption as you would otherwise.</span></span> <span data-ttu-id="3d26b-441">[ **2 重のキー暗号化を使用する** ] を選択し、キーのエンドポイント URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-441">Select **Use Double Key Encryption** and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="3d26b-442">例:</span><span class="sxs-lookup"><span data-stu-id="3d26b-442">For example:</span></span>

![Microsoft 365 コンプライアンスセンターで [二重のキー暗号化を使用する] を選択します。](../media/dke-use-dke.png)

<span data-ttu-id="3d26b-444">追加した DKE ラベルは、Microsoft 365 Apps for enterprise の最新バージョンのユーザーに対して表示され始めます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-444">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="3d26b-445">クライアントが新しいラベルで更新されるまで、最大24時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3d26b-445">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="3d26b-446">クライアントで DKE を有効にする</span><span class="sxs-lookup"><span data-stu-id="3d26b-446">Enable DKE in your client</span></span>

<span data-ttu-id="3d26b-447">Office Insider を使用している場合は、DKE が有効になります。</span><span class="sxs-lookup"><span data-stu-id="3d26b-447">If you're an Office Insider, DKE is enabled for you.</span></span> <span data-ttu-id="3d26b-448">それ以外の場合は、次のレジストリキーを追加して、クライアントに対して DKE を有効にします。</span><span class="sxs-lookup"><span data-stu-id="3d26b-448">Otherwise, enable DKE for your client by adding the following registry keys:</span></span>

```properties
    [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001
```

## <a name="migrate-protected-files-from-hyok-labels-to-dke-labels"></a><span data-ttu-id="3d26b-449">保護されたファイルを HYOK ラベルから DKE ラベルに移行する</span><span class="sxs-lookup"><span data-stu-id="3d26b-449">Migrate protected files from HYOK labels to DKE labels</span></span>

<span data-ttu-id="3d26b-450">必要に応じて、DKE の設定を終了すると、HYOK labels を使用して保護したコンテンツを DKE ラベルに移行できます。</span><span class="sxs-lookup"><span data-stu-id="3d26b-450">If you want, once you're finished setting up DKE, you can migrate content that you've protected using HYOK labels to DKE labels.</span></span> <span data-ttu-id="3d26b-451">移行するには、AIP スキャナーを使用します。</span><span class="sxs-lookup"><span data-stu-id="3d26b-451">To migrate, you'll use the AIP scanner.</span></span> <span data-ttu-id="3d26b-452">スキャナーの使用を開始するには、「 [Azure Information Protection の統合ラベル付けされたスキャナーとは](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d26b-452">To get started using the scanner, see [What is the Azure Information Protection unified labeling scanner?](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner).</span></span>

<span data-ttu-id="3d26b-453">コンテンツを移行しない場合、HYOK の保護されたコンテンツは影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="3d26b-453">If you don't migrate content, your HYOK protected content will remain unaffected.</span></span>
