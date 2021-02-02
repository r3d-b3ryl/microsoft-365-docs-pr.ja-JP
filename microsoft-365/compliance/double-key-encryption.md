---
title: 二重キー暗号化 (DKE)
description: DKE を使用すると、キーのフル コントロールを維持しながら、機密性の高いデータを保護できます。
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 01/29/2021
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: c10a10a5922755db2c901137c3dff8acee5b8445
ms.sourcegitcommit: c550c1b5b9e67398fd95bfb0256c4f5c7930b2be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2021
ms.locfileid: "50066860"
---
# <a name="double-key-encryption-for-microsoft-365"></a><span data-ttu-id="0f3c0-103">Microsoft 365 の二重キー暗号化</span><span class="sxs-lookup"><span data-stu-id="0f3c0-103">Double Key Encryption for Microsoft 365</span></span>

> <span data-ttu-id="0f3c0-104">*適用対象: Microsoft 365、Microsoft [365 コンプライアンス](https://www.microsoft.com/microsoft-365/business/compliance-management)[、Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)の二重キー暗号化*</span><span class="sxs-lookup"><span data-stu-id="0f3c0-104">*Applies to: Double Key Encryption for Microsoft 365, [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="0f3c0-105">*手順: [Windows 用 Azure Information Protection 統合ラベル付けクライアント](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span><span class="sxs-lookup"><span data-stu-id="0f3c0-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="0f3c0-106">*サービスの説明: [Microsoft 365 コンプライアンス](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="0f3c0-106">*Service description for: [Microsoft 365 Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="0f3c0-107">二重キー暗号化 (DKE) は、2 つのキーを一緒に使用して、保護されたコンテンツにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-107">Double Key Encryption (DKE) uses two keys together to access protected content.</span></span> <span data-ttu-id="0f3c0-108">Microsoft は 1 つのキーを Microsoft Azure に保存し、もう一方のキーを保持します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-108">Microsoft stores one key in Microsoft Azure, and you hold the other key.</span></span> <span data-ttu-id="0f3c0-109">Double Key Encryption サービスを使用して、キーの 1 つを完全に制御します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-109">You maintain full control of one of your keys using the Double Key Encryption service.</span></span> <span data-ttu-id="0f3c0-110">Azure Information Protection 統合ラベル付けクライアントを使用して、機密性の高いコンテンツに保護を適用します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-110">You apply protection using The Azure Information Protection unified labeling client to your highly sensitive content.</span></span>

<span data-ttu-id="0f3c0-111">二重キー暗号化は、クラウドとオンプレミスの両方の展開をサポートします。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-111">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="0f3c0-112">これらの展開は、保護されたデータを保存する場所で暗号化されたデータが不透明なままに維持されるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-112">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="0f3c0-113">既定のクラウドベースのテナント ルート キーの詳細については [、「Azure Information Protection](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)テナント キーの計画と実装」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-113">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span></span>

## <a name="when-your-organization-should-adopt-dke"></a><span data-ttu-id="0f3c0-114">組織が DKE を採用する必要が生じ</span><span class="sxs-lookup"><span data-stu-id="0f3c0-114">When your organization should adopt DKE</span></span>

<span data-ttu-id="0f3c0-115">二重キー暗号化は、最も厳しい保護要件の対象となる最も機密性の高いデータを対象とします。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-115">Double Key Encryption is intended for your most sensitive data that is subject to the strictest protection requirements.</span></span> <span data-ttu-id="0f3c0-116">DKE は、すべてのデータを対象としているのではありません。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-116">DKE is not intended for all data.</span></span> <span data-ttu-id="0f3c0-117">一般に、Double Key Encryption を使用して、データ全体の一部のみを保護します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-117">In general, you'll be using Double Key Encryption to protect only a small part of your overall data.</span></span> <span data-ttu-id="0f3c0-118">展開する前に、このソリューションでカバーする適切なデータを特定する上で注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-118">You should do due diligence in identifying the right data to cover with this solution before you deploy.</span></span> <span data-ttu-id="0f3c0-119">場合によっては、Microsoft が管理するキーや BYOK を使用した Microsoft Information Protection など、ほとんどのデータに対して範囲を絞り込み、その他のソリューションを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-119">In some cases, you might need to narrow your scope and make use of other solutions for most your data such as Microsoft Information Protection with Microsoft-managed keys or BYOK.</span></span> <span data-ttu-id="0f3c0-120">これらのソリューションは、強化された保護と規制要件の対象ではないドキュメントに対して十分です。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-120">These solutions are sufficient for documents that aren't subject to enhanced protections and regulatory requirements.</span></span> <span data-ttu-id="0f3c0-121">また、これらのソリューションを使用すると、最も強力な 365 Office使用できます。DKE で暗号化されたコンテンツでは使用できないサービス。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-121">Also, these solutions enable you to use the most powerful Office 365 services; services that you can't use with DKE encrypted content.</span></span> <span data-ttu-id="0f3c0-122">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-122">For example:</span></span>

- <span data-ttu-id="0f3c0-123">添付ファイルの可視性を必要とするマルウェア対策とスパムを含むトランスポート ルール</span><span class="sxs-lookup"><span data-stu-id="0f3c0-123">Transport rules including anti-malware and spam that require visibility into the attachment</span></span>
- <span data-ttu-id="0f3c0-124">Microsoft Delve</span><span class="sxs-lookup"><span data-stu-id="0f3c0-124">Microsoft Delve</span></span>
- <span data-ttu-id="0f3c0-125">電子情報開示</span><span class="sxs-lookup"><span data-stu-id="0f3c0-125">eDiscovery</span></span>
- <span data-ttu-id="0f3c0-126">コンテンツ検索とインデックス作成</span><span class="sxs-lookup"><span data-stu-id="0f3c0-126">Content search and indexing</span></span>
- <span data-ttu-id="0f3c0-127">Office機能を含む Web アプリの作成</span><span class="sxs-lookup"><span data-stu-id="0f3c0-127">Office Web Apps including coauthoring functionality</span></span>

<span data-ttu-id="0f3c0-128">MIP SDK を介して DKE と統合されていない外部アプリケーションまたはサービスは、暗号化されたデータに対してアクションを実行できません。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-128">Any external applications or services that are not integrated with DKE through the MIP SDK will be unable to perform actions on the encrypted data.</span></span>

<span data-ttu-id="0f3c0-129">Microsoft Information Protection SDK 1.7+ は、二重キー暗号化をサポートしています。SDK と統合するアプリケーションは、十分なアクセス許可と統合を適用して、このデータを理由にできます。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-129">The Microsoft Information Protection SDK 1.7+ supports Double Key Encryption; applications that integrate with our SDK will be able to reason over this data with sufficient permissions and integrations in place.</span></span>

<span data-ttu-id="0f3c0-130">組織では、Microsoft 情報保護機能 (分類とラベル付け) を使用して機密データのほとんどを保護し、ミッション クリティカルなデータにのみ DKE を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-130">We recommend organizations use Microsoft Information protection capabilities (classification and labeling) to protect most of their sensitive data and only use DKE for their mission-critical data.</span></span> <span data-ttu-id="0f3c0-131">二重キー暗号化は、金融サービスや医療などの厳しく規制された業界の機密データに関連します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-131">Double Key Encryption is relevant for sensitive data in highly regulated industries such as Financial services and Healthcare.</span></span>

<span data-ttu-id="0f3c0-132">組織に次の要件がある場合は、DKE を使用してコンテンツをセキュリティで保護できます。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-132">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="0f3c0-133">すべての状況で、 *保護* されたコンテンツの暗号化を解除できるのは自分だけである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-133">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="0f3c0-134">Microsoft が独自に保護されたデータにアクセスしたくはない。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-134">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="0f3c0-135">地理的境界内にキーを保持する規制要件があります。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-135">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="0f3c0-136">データの暗号化と暗号化解除のために保持するキーはすべて、データ センターで保持されます。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-136">All of the keys that you hold for data encryption and decryption are maintained in your data center.</span></span>

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="0f3c0-137">DKE のシステム要件とライセンス要件</span><span class="sxs-lookup"><span data-stu-id="0f3c0-137">System and licensing requirements for DKE</span></span>

<span data-ttu-id="0f3c0-138">**Microsoft 365 の二** 重キー暗号化には、Microsoft 365 E5 が付属しています。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-138">**Double Key Encryption for Microsoft 365** comes with Microsoft 365 E5.</span></span> <span data-ttu-id="0f3c0-139">Microsoft 365 E5 ライセンスをお持ちない場合は、試用版にサインアップ [できます](https://aka.ms/M365E5ComplianceTrial)。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-139">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="0f3c0-140">これらのライセンスの詳細については、セキュリティとコンプライアンスに関する [Microsoft 365 ライセンス ガイダンス&してください](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-140">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="0f3c0-141">**Azure Information Protection**。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-141">**Azure Information Protection**.</span></span> <span data-ttu-id="0f3c0-142">DKE は、区別ラベルで動作し、Azure Information Protection を必要とします。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-142">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

<span data-ttu-id="0f3c0-143">DKE の感度ラベルは、デスクトップ アプリの [Office] リボンを通じてエンド ユーザーが使用できます。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-143">DKE sensitivity labels are made available to end users through the sensitivity ribbon in Office Desktop Apps.</span></span> <span data-ttu-id="0f3c0-144">保護されたドキュメントを保護して使用する各クライアント コンピューターに、これらの前提条件をインストールします。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-144">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="0f3c0-145">**Microsoft Officeのエンタープライズ** バージョン \*.12711 以降 (デスクトップ バージョンの Word、PowerPoint、Excel) 用アプリ。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-145">**Microsoft Office Apps for enterprise** version \*.12711 or later (Desktop versions of Word, PowerPoint, and Excel) on Windows.</span></span>

<span data-ttu-id="0f3c0-146">**Azure Information Protection 統合ラベル付けクライアント** バージョン 2.7.93.0 以降。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-146">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="0f3c0-147">Microsoft ダウンロード センターから統合ラベル付けクライアントを [ダウンロードしてインストールします](https://www.microsoft.com/download/details.aspx?id=53018)。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-147">Download and install the Unified Labeling client from the [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="0f3c0-148">DKE で保護されたコンテンツを保存および表示するためのサポートされている環境</span><span class="sxs-lookup"><span data-stu-id="0f3c0-148">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="0f3c0-149">**サポートされているアプリケーション**。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-149">**Supported applications**.</span></span> <span data-ttu-id="0f3c0-150">Word、Excel、PowerPoint を含む、Windows 上の[Microsoft 365](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) Apps for enterprise クライアント。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-150">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="0f3c0-151">**オンライン コンテンツのサポート**。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-151">**Online content support**.</span></span> <span data-ttu-id="0f3c0-152">Microsoft SharePoint と OneDrive for Business の両方にオンラインで保存されているドキュメントとファイルがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-152">Documents and files stored online in both Microsoft SharePoint and OneDrive for Business are supported.</span></span> <span data-ttu-id="0f3c0-153">暗号化されたコンテンツは電子メールで共有できますが、暗号化されたドキュメントとファイルをオンラインで表示できません。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-153">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="0f3c0-154">代わりに、ローカル コンピューター上のデスクトップ アプリを使用して、保護されたコンテンツを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-154">Instead, you must view protected content using the desktop apps on your local computer.</span></span>

## <a name="overview-of-deploying-dke"></a><span data-ttu-id="0f3c0-155">DKE の展開の概要</span><span class="sxs-lookup"><span data-stu-id="0f3c0-155">Overview of deploying DKE</span></span>

<span data-ttu-id="0f3c0-156">DKE をセットアップするには、次の一般的な手順に従います。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-156">You'll follow these general steps to set up DKE.</span></span> <span data-ttu-id="0f3c0-157">これらの手順を完了すると、エンド ユーザーは、二重キー暗号化を使用して機密性の高いデータを保護できます。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-157">Once you've completed these steps, your end users will can protect your highly sensitive data with Double Key Encryption.</span></span>

1. <span data-ttu-id="0f3c0-158">この記事の説明に従って DKE サービスを展開します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-158">Deploy the DKE service as described in this article.</span></span>

2. <span data-ttu-id="0f3c0-159">二重キー暗号化を使用してラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-159">Create a label with Double Key Encryption.</span></span> <span data-ttu-id="0f3c0-160">[Microsoft 365](https://compliance.microsoft.com)コンプライアンス センターの下の情報保護に移動し、二重キー暗号化を使用して新しいラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-160">Navigate to Information protection under the [Microsoft 365 compliance center](https://compliance.microsoft.com) and create a new label with Double Key Encryption.</span></span> <span data-ttu-id="0f3c0-161">「 [暗号化を適用するために、感度ラベルを使用してコンテンツへのアクセスを制限する」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-161">See [Restrict access to content by using sensitivity labels to apply encryption](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels).</span></span>

3. <span data-ttu-id="0f3c0-162">二重キー暗号化ラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-162">Use Double Key Encryption labels.</span></span> <span data-ttu-id="0f3c0-163">データを保護するには、次のページの [Sensitivity] リボンから [Double Key Encrypted] ラベルをMicrosoft Office。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-163">Protect data by selecting the Double Key Encrypted label from the Sensitivity ribbon in Microsoft Office.</span></span>

<span data-ttu-id="0f3c0-164">二重キー暗号化を展開するには、いくつかの手順を実行する方法があります。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-164">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="0f3c0-165">この記事では、経験の少ない管理者がサービスを正常に展開できるよう、詳細な手順を示します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-165">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="0f3c0-166">この方法に問題が生じない場合は、独自の方法を選択できます。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-166">If you're comfortable doing so, you can choose to use your own methods.</span></span>

## <a name="deploy-dke"></a><span data-ttu-id="0f3c0-167">DKE の展開</span><span class="sxs-lookup"><span data-stu-id="0f3c0-167">Deploy DKE</span></span>

<span data-ttu-id="0f3c0-168">この記事と展開ビデオでは、DKE サービスの展開先として Azure を使用します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-168">This article and the deployment video use Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="0f3c0-169">別の場所に展開する場合は、独自の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-169">If you're deploying to another location, you'll need to provide your own values.</span></span>

<span data-ttu-id="0f3c0-170">二重 [キー暗号化の展開のビデオ](https://youtu.be/vDWfHN_kygg) を見て、この記事の概念の詳しい概要を確認してください。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-170">Watch the [Double Key Encryption deployment video](https://youtu.be/vDWfHN_kygg) to see a step-by-step overview of the concepts in this article.</span></span> <span data-ttu-id="0f3c0-171">ビデオが完成するのに約 18 分かかります。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-171">The video takes about 18 minutes to complete.</span></span>

<span data-ttu-id="0f3c0-172">次の一般的な手順に従って、組織の二重キー暗号化を設定します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-172">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span>

1. [<span data-ttu-id="0f3c0-173">DKE サービスの前提条件ソフトウェアをインストールする</span><span class="sxs-lookup"><span data-stu-id="0f3c0-173">Install software prerequisites for the DKE service</span></span>](#install-software-prerequisites-for-the-dke-service)
1. [<span data-ttu-id="0f3c0-174">二重キー暗号化 GitHub リポジトリを複製する</span><span class="sxs-lookup"><span data-stu-id="0f3c0-174">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="0f3c0-175">アプリケーション設定の変更</span><span class="sxs-lookup"><span data-stu-id="0f3c0-175">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="0f3c0-176">テスト キーを生成する</span><span class="sxs-lookup"><span data-stu-id="0f3c0-176">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="0f3c0-177">プロジェクトをビルドする</span><span class="sxs-lookup"><span data-stu-id="0f3c0-177">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="0f3c0-178">DKE サービスを展開し、キー ストアを発行する</span><span class="sxs-lookup"><span data-stu-id="0f3c0-178">Deploy the DKE service and publish the key store</span></span>](#deploy-the-dke-service-and-publish-the-key-store)
1. [<span data-ttu-id="0f3c0-179">展開を検証する</span><span class="sxs-lookup"><span data-stu-id="0f3c0-179">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="0f3c0-180">キー ストアを登録する</span><span class="sxs-lookup"><span data-stu-id="0f3c0-180">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="0f3c0-181">DKE を使用して感度ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="0f3c0-181">Create sensitivity labels using DKE</span></span>](#create-sensitivity-labels-using-dke)
1. [<span data-ttu-id="0f3c0-182">クライアントで DKE を有効にする</span><span class="sxs-lookup"><span data-stu-id="0f3c0-182">Enable DKE in your client</span></span>](#enable-dke-in-your-client)
1. [<span data-ttu-id="0f3c0-183">保護されたファイルを HYOK ラベルから DKE ラベルに移行する</span><span class="sxs-lookup"><span data-stu-id="0f3c0-183">Migrate protected files from HYOK labels to DKE labels</span></span>](#migrate-protected-files-from-hyok-labels-to-dke-labels)

<span data-ttu-id="0f3c0-184">完了したら、DKE を使用してドキュメントとファイルを暗号化できます。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-184">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="0f3c0-185">詳細については、「ファイルと [電子メールにラベル](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)を適用する」を参照Office。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-185">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites-for-the-dke-service"></a><span data-ttu-id="0f3c0-186">DKE サービスの前提条件ソフトウェアをインストールする</span><span class="sxs-lookup"><span data-stu-id="0f3c0-186">Install software prerequisites for the DKE service</span></span>

<span data-ttu-id="0f3c0-187">これらの前提条件を、DKE サービスをインストールするコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-187">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="0f3c0-188">**.NET Core 3.1 SDK**.</span><span class="sxs-lookup"><span data-stu-id="0f3c0-188">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="0f3c0-189">[DOWNLOAD .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)から SDK をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-189">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="0f3c0-190">**Visual Studio コード**。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-190">**Visual Studio Code**.</span></span> <span data-ttu-id="0f3c0-191">コードVisual Studioダウンロードします [https://code.visualstudio.com/](https://code.visualstudio.com) 。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-191">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="0f3c0-192">インストールが完了したら、Visual Studioコードを実行し、[拡張機能の **表示]** \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-192">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="0f3c0-193">これらの拡張機能をインストールします。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-193">Install these extensions.</span></span>

- <span data-ttu-id="0f3c0-194">C# for Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="0f3c0-194">C# for Visual Studio Code</span></span>

- <span data-ttu-id="0f3c0-195">NuGet パッケージ マネージャー</span><span class="sxs-lookup"><span data-stu-id="0f3c0-195">NuGet Package Manager</span></span>

<span data-ttu-id="0f3c0-196">**Git リソース**。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-196">**Git resources**.</span></span> <span data-ttu-id="0f3c0-197">次のいずれかをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-197">Download and install one of the following.</span></span>

- [<span data-ttu-id="0f3c0-198">Git</span><span class="sxs-lookup"><span data-stu-id="0f3c0-198">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="0f3c0-199">GitHub デスクトップ</span><span class="sxs-lookup"><span data-stu-id="0f3c0-199">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="0f3c0-200">GitHub Enterprise</span><span class="sxs-lookup"><span data-stu-id="0f3c0-200">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="0f3c0-201">**OpenSSL** DKE の展開 [後にテスト キー](https://slproweb.com/products/Win32OpenSSL.html) を [生成するには、OpenSSL](#generate-test-keys) がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-201">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="0f3c0-202">環境変数のパスから正しく呼び出されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-202">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="0f3c0-203">たとえば、詳細については、「インストール ディレクトリを PATH に追加する」 [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-203">For example, see "Add the installation directory to PATH" at [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) for details.</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="0f3c0-204">DKE GitHub リポジトリを複製する</span><span class="sxs-lookup"><span data-stu-id="0f3c0-204">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="0f3c0-205">Microsoft は、GitHub リポジトリに DKE ソース ファイルを提供しています。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-205">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="0f3c0-206">リポジトリを複製して、組織で使用するためにプロジェクトをローカルにビルドします。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-206">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="0f3c0-207">DKE GitHub リポジトリの場所は次の場所にあります [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) 。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-207">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="0f3c0-208">次の手順は、経験の浅い git またはコード Visual Studio向けです。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-208">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="0f3c0-209">ブラウザーで、次の場所に移動します [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) 。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-209">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

2. <span data-ttu-id="0f3c0-210">画面の右側で、[コード] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-210">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="0f3c0-211">バージョンの UI に [複製] または [ダウンロード] **ボタンが表示される場合** があります。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-211">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="0f3c0-212">次に、表示されるドロップダウンでコピー アイコンを選択し、URL をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-212">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="0f3c0-213">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-213">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0f3c0-214">![GitHub から Double Key Encryption サービス リポジトリを複製する](../media/dke-clone.png)</span><span class="sxs-lookup"><span data-stu-id="0f3c0-214">![Clone the Double Key Encryption service repository from GitHub](../media/dke-clone.png)</span></span>

3. <span data-ttu-id="0f3c0-215">[コードVisual Studioコマンド パレットの **表示]** \> **を** 選択し **、[Git:** Clone] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-215">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="0f3c0-216">リスト内のオプションに移動するには、入力を開始してエントリをフィルター処理し、ドロップダウン `git: clone` から選択します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-216">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="0f3c0-217">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-217">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0f3c0-218">![Visual Studio GIT:Clone オプション](../media/dke-vscode-clone.png)</span><span class="sxs-lookup"><span data-stu-id="0f3c0-218">![Visual Studio Code GIT:Clone option](../media/dke-vscode-clone.png)</span></span>

4. <span data-ttu-id="0f3c0-219">テキスト ボックスに、Git からコピーした URL を貼り付け **、GitHub から [Clone] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-219">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="0f3c0-220">表示される **[フォルダーの** 選択] ダイアログで、リポジトリを格納する場所を参照して選択します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-220">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="0f3c0-221">プロンプトで、[開く] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-221">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="0f3c0-222">リポジトリがコードVisual Studio開き、左下に現在の Git 分岐が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-222">The repository opens in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="0f3c0-223">たとえば、分岐は main である **必要があります**。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-223">For example,  The branch should be **main**.</span></span> <span data-ttu-id="0f3c0-224">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-224">For example:</span></span>

   ![メイン 分岐を表示している Visual Studioコードの DKE レポのスクリーンショット](../media/dke-vscode-main-branch.jpg)

6. <span data-ttu-id="0f3c0-226">メイン 分岐を使用していない場合は、選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-226">If you're not on the main branch, you'll need to select it.</span></span> <span data-ttu-id="0f3c0-227">コードVisual Studio、分岐を選択し、表示される分岐の一覧から main を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-227">In Visual Studio Code, select the branch and choose **main** from the list of branches that displays.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="0f3c0-228">メイン分岐を選択すると、プロジェクトをビルドするための適切なファイルが確保されます。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-228">Selecting the main branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="0f3c0-229">正しい分岐を選択しない場合、展開は失敗します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-229">If you don't choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="0f3c0-230">これで、DKE ソース リポジトリがローカルにセットアップされます。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-230">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="0f3c0-231">次に [、組織のアプリケーション設定](#modify-application-settings) を変更します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-231">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="0f3c0-232">アプリケーション設定の変更</span><span class="sxs-lookup"><span data-stu-id="0f3c0-232">Modify application settings</span></span>

<span data-ttu-id="0f3c0-233">DKE サービスを展開するには、次の種類のアプリケーション設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-233">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="0f3c0-234">キー アクセスの設定</span><span class="sxs-lookup"><span data-stu-id="0f3c0-234">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="0f3c0-235">テナントとキーの設定</span><span class="sxs-lookup"><span data-stu-id="0f3c0-235">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="0f3c0-236">アプリケーション設定は、on ファイルappsettings.js変更します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-236">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="0f3c0-237">このファイルは、DoubleKeyEncryptionService\src\customer-key-store の下にローカルに複製した DoubleKeyEncryptionService リポジトリにあります。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-237">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="0f3c0-238">たとえば、コードVisual Studio、次の図に示すようにファイルを参照できます。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-238">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

![DKE 用appsettings.jsの場所。](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a><span data-ttu-id="0f3c0-240">キー アクセスの設定</span><span class="sxs-lookup"><span data-stu-id="0f3c0-240">Key access settings</span></span>

<span data-ttu-id="0f3c0-241">電子メールまたは役割の承認を使用するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-241">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="0f3c0-242">DKE では、一度にサポートされる認証方法は 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-242">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="0f3c0-243">**電子メールの承認**。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-243">**Email authorization**.</span></span> <span data-ttu-id="0f3c0-244">電子メール アドレスにのみ基づいてキーへのアクセスを組織が承認できます。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-244">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="0f3c0-245">**役割の承認**。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-245">**Role authorization**.</span></span> <span data-ttu-id="0f3c0-246">組織が Active Directory グループに基づいてキーへのアクセスを承認し、Web サービスが LDAP を照会できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-246">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="0f3c0-247">**電子メールの承認を使用して DKE のキー アクセス設定を設定するには**</span><span class="sxs-lookup"><span data-stu-id="0f3c0-247">**To set key access settings for DKE using email authorization**</span></span>

1. <span data-ttu-id="0f3c0-248">ファイルの **appsettings.jsを開き** 、設定を探 `AuthorizedEmailAddress` します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-248">Open the **appsettings.json** file and locate the `AuthorizedEmailAddress` setting.</span></span>

2. <span data-ttu-id="0f3c0-249">承認するメール アドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-249">Add the email address or addresses that you want to authorize.</span></span> <span data-ttu-id="0f3c0-250">複数の電子メール アドレスは二重引用符とコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-250">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="0f3c0-251">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-251">For example:</span></span>

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. <span data-ttu-id="0f3c0-252">設定を `LDAPPath` 見つけて、二重引用符の `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` 間のテキストを削除します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-252">Locate the `LDAPPath` setting and remove the text `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` between the double quotes.</span></span> <span data-ttu-id="0f3c0-253">二重引用符はそのまま残します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-253">Leave the double quotes in place.</span></span> <span data-ttu-id="0f3c0-254">完了すると、設定は次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-254">When you're finished, the setting should look like this.</span></span>

   ```json
   "LDAPPath": ""
   ```

4. <span data-ttu-id="0f3c0-255">設定を `AuthorizedRoles` 見つけて、行全体を削除します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-255">Locate the `AuthorizedRoles` setting and delete the entire line.</span></span>

<span data-ttu-id="0f3c0-256">この画像は、電子 **メールのappsettings.js形式の** ファイルに関する情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-256">This image shows the **appsettings.json** file correctly formatted for email authorization.</span></span>

   ![電子appsettings.js方法を示すファイルの例](../media/dke-email-accesssetting.png)

<span data-ttu-id="0f3c0-258">**役割の承認を使用して DKE のキー アクセス設定を設定するには**</span><span class="sxs-lookup"><span data-stu-id="0f3c0-258">**To set key access settings for DKE using role authorization**</span></span>

1. <span data-ttu-id="0f3c0-259">ファイルの **appsettings.jsを開き** 、設定を探 `AuthorizedRoles` します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-259">Open the **appsettings.json** file and locate the `AuthorizedRoles` setting.</span></span>

2. <span data-ttu-id="0f3c0-260">承認する Active Directory グループ名を追加します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-260">Add the Active Directory group names you want to authorize.</span></span> <span data-ttu-id="0f3c0-261">複数のグループ名を二重引用符とコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-261">Separate multiple group names with double quotes and commas.</span></span> <span data-ttu-id="0f3c0-262">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-262">For example:</span></span>

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. <span data-ttu-id="0f3c0-263">設定を `LDAPPath` 見つけて、Active Directory ドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-263">Locate the `LDAPPath` setting and add the Active Directory domain.</span></span> <span data-ttu-id="0f3c0-264">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-264">For example:</span></span>

   ```json
   "LDAPPath": "contoso.com"
   ```

4. <span data-ttu-id="0f3c0-265">設定を `AuthorizedEmailAddress` 見つけて、行全体を削除します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-265">Locate the `AuthorizedEmailAddress` setting and delete the entire line.</span></span>

<span data-ttu-id="0f3c0-266">この画像は、ロールの **承認appsettings.js形式の** ファイルに関する情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-266">This image shows the **appsettings.json** file correctly formatted for role authorization.</span></span>

   ![appsettings.jsの承認方法を示すファイルの作成](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="0f3c0-268">テナントとキーの設定</span><span class="sxs-lookup"><span data-stu-id="0f3c0-268">Tenant and key settings</span></span>

<span data-ttu-id="0f3c0-269">DKE テナントとキーの設定は、appsettings.js **に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-269">DKE tenant and key settings are located in the **appsettings.json** file.</span></span>

<span data-ttu-id="0f3c0-270">**DKE のテナントとキーの設定を構成するには**</span><span class="sxs-lookup"><span data-stu-id="0f3c0-270">**To configure tenant and key settings for DKE**</span></span>

1. <span data-ttu-id="0f3c0-271">ファイルの **appsettings.jsを開** きます。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-271">Open the **appsettings.json** file.</span></span>

2. <span data-ttu-id="0f3c0-272">設定を `ValidIssuers` 見つけて、テナント `<tenantid>` ID に置き換える。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-272">Locate the `ValidIssuers` setting and replace `<tenantid>` with your tenant ID.</span></span> <span data-ttu-id="0f3c0-273">テナント ID を見つけるには、Azure ポータルにアクセスしてテナントのプロパティを [表示します](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-273">You can locate your tenant ID by going to the Azure portal and viewing the [tenant properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="0f3c0-274">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-274">For example:</span></span>

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

<span data-ttu-id="0f3c0-275">を探します `JwtAudience` 。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-275">Locate the `JwtAudience`.</span></span> <span data-ttu-id="0f3c0-276">`<yourhostname>`DKE サービスを実行するコンピューターのホスト名に置き換える。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-276">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span> <span data-ttu-id="0f3c0-277">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-277">For example:</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="0f3c0-278">値は、 `JwtAudience` ホストの名前と正確に一致 *する必要があります*。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-278">The value for `JwtAudience` must match the name of your host *exactly*.</span></span> <span data-ttu-id="0f3c0-279">デバッグ中に **localhost:5001** を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-279">You may use **localhost:5001** while debugging.</span></span> <span data-ttu-id="0f3c0-280">ただし、デバッグが完了したら、この値をサーバーのホスト名に更新してください。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-280">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="0f3c0-281">`TestKeys:Name`.</span><span class="sxs-lookup"><span data-stu-id="0f3c0-281">`TestKeys:Name`.</span></span> <span data-ttu-id="0f3c0-282">キーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-282">Enter a name for your key.</span></span> <span data-ttu-id="0f3c0-283">例: `TestKey1`</span><span class="sxs-lookup"><span data-stu-id="0f3c0-283">For example: `TestKey1`</span></span>
- <span data-ttu-id="0f3c0-284">`TestKeys:Id`.</span><span class="sxs-lookup"><span data-stu-id="0f3c0-284">`TestKeys:Id`.</span></span> <span data-ttu-id="0f3c0-285">GUID を作成し、値として入力 `TestKeys:ID` します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-285">Create a GUID and enter it as the `TestKeys:ID` value.</span></span> <span data-ttu-id="0f3c0-286">たとえば、`DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE` などです。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-286">For example, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span></span> <span data-ttu-id="0f3c0-287">オンライン GUID ジェネレーターのようなサイト [を使用して、GUID](https://guidgenerator.com/) をランダムに生成できます。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-287">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

<span data-ttu-id="0f3c0-288">この画像は、テナントとキーの設定の正しい形式を示appsettings.js **オンです**。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-288">This image shows the correct format for tenant and keys settings in **appsettings.json**.</span></span> <span data-ttu-id="0f3c0-289">`LDAPPath` は、役割の承認用に構成されます。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-289">`LDAPPath` is configured for role authorization.</span></span>

![ファイルに保存されている DKE の適切なテナントとappsettings.js設定を表示します。](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a><span data-ttu-id="0f3c0-291">テスト キーを生成する</span><span class="sxs-lookup"><span data-stu-id="0f3c0-291">Generate test keys</span></span>

<span data-ttu-id="0f3c0-292">アプリケーション設定を定義したら、公開キーとプライベート テスト キーを生成する準備が整います。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-292">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="0f3c0-293">キーを生成するには:</span><span class="sxs-lookup"><span data-stu-id="0f3c0-293">To generate keys:</span></span>

1. <span data-ttu-id="0f3c0-294">Windows の [スタート] メニューから、OpenSSL コマンド プロンプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-294">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

2. <span data-ttu-id="0f3c0-295">テスト キーを保存するフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-295">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="0f3c0-296">このタスクの手順を完了して作成するファイルは、同じフォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-296">The files you create by completing the steps in this task are stored in the same folder.</span></span>

3. <span data-ttu-id="0f3c0-297">新しいテスト キーを生成します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-297">Generate the new test key.</span></span>

   ```console
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

4. <span data-ttu-id="0f3c0-298">プライベート キーを生成します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-298">Generate the private key.</span></span>

   ```console
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

5. <span data-ttu-id="0f3c0-299">公開キーを生成します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-299">Generate the public key.</span></span>

   ```console
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

6. <span data-ttu-id="0f3c0-300">テキスト エディターで **、pubkeyonly.pem を開きます**。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-300">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="0f3c0-301">**pubkeyonly.pem** ファイルのすべてのコンテンツ (最初の行と最後の行を除く) を、ファイルのappsettings.js`PublicPem` **セクションにコピー** します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-301">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the `PublicPem` section of the **appsettings.json** file.</span></span>

7. <span data-ttu-id="0f3c0-302">テキスト エディターで **、prikeynopass.pem を開きます**。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-302">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="0f3c0-303">最初の行と最後の行を除く **、appsettings.js** `PrivatePem` on ファイル内のすべてのコンテンツ **をコピー** します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-303">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the `PrivatePem` section of the **appsettings.json** file.</span></span>

8. <span data-ttu-id="0f3c0-304">セクションとセクションの両方のすべての空白と改行 `PublicPem` を `PrivatePem` 削除します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-304">Remove all blank spaces and newlines in both the `PublicPem` and `PrivatePem` sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0f3c0-305">このコンテンツをコピーする場合は、PEM データを削除してください。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-305">When you copy this content, do not delete any of the PEM data.</span></span>

9. <span data-ttu-id="0f3c0-306">[Visual Studioコード] で、次のファイル **Startup.cs** します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-306">In Visual Studio Code, browse to the **Startup.cs** file.</span></span> <span data-ttu-id="0f3c0-307">このファイルは、ローカルで DoubleKeyEncryptionService\src\customer-key-store\ の下に複製した DoubleKeyEncryptionService リポジトリにあります。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-307">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store\.</span></span>

10. <span data-ttu-id="0f3c0-308">次の行を検索します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-308">Locate the following lines:</span></span>

    ```csharp
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
    ```

11. <span data-ttu-id="0f3c0-309">これらの行を次のテキストに置き換します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-309">Replace these lines with the following text:</span></span>

    ```csharp
    services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
    ```

    <span data-ttu-id="0f3c0-310">最後の結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-310">The end results should look similar to the following.</span></span>

    ![startup.csプレビュー用のファイルを作成する](../media/dke-startupcs-usetestkeys.png)

<span data-ttu-id="0f3c0-312">これで [、DKE プロジェクトをビルドする準備ができました](#build-the-project)。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-312">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="0f3c0-313">プロジェクトをビルドする</span><span class="sxs-lookup"><span data-stu-id="0f3c0-313">Build the project</span></span>

<span data-ttu-id="0f3c0-314">DKE プロジェクトをローカルにビルドするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-314">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="0f3c0-315">[Visual Studioコード] の DKE サービス リポジトリで、[コマンド パレットの表示] を選択し、プロンプトで \> **「ビルド**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-315">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

2. <span data-ttu-id="0f3c0-316">一覧から、[タスク: ビルド タスク **の実行] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-316">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="0f3c0-317">ビルド タスクが見つからない場合は、[ビルド タスクの構成] を選択し、次のように .NET コア用に作成します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-317">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   ![.NET の不足しているビルド タスクを構成する](../media/dke-configurebuildtask.png)

   1. <span data-ttu-id="0f3c0-319">Choose **Create tasks.json from template**.</span><span class="sxs-lookup"><span data-stu-id="0f3c0-319">Choose **Create tasks.json from template**.</span></span>

      ![DKE tasks.jsテンプレートからファイルに対するデータの作成](../media/dke-createtasksjsonfromtemplate.png)

   2. <span data-ttu-id="0f3c0-321">テンプレートの種類の一覧から **、[.NET Core] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-321">From the list of template types, select **.NET Core**.</span></span>

      ![DKE 用の適切なテンプレートを選択する](../media/dke-tasksjsontemplate.png)

   3. <span data-ttu-id="0f3c0-323">ビルド セクションで **、customerkeystore.csproj ファイルへのパスを見** つけます。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-323">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="0f3c0-324">表示されない場合は、次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-324">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

   4. <span data-ttu-id="0f3c0-325">ビルドを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-325">Run the build again.</span></span>

3. <span data-ttu-id="0f3c0-326">出力ウィンドウに赤いエラーが表示されません。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-326">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="0f3c0-327">赤いエラーがある場合は、コンソールの出力を確認します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-327">If there are red errors, check the console output.</span></span> <span data-ttu-id="0f3c0-328">前のすべての手順が正しく完了し、正しいビルド バージョンが存在していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-328">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

4. <span data-ttu-id="0f3c0-329">[ **デバッグの** \> **開始] を選択して** 、プロセスをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-329">Select **Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="0f3c0-330">環境を選択するように求めるメッセージが表示されたら **、.NET core を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-330">If you're prompted to select an environment, select **.NET core**.</span></span>

   <span data-ttu-id="0f3c0-331">.NET コア デバッガーは、通常起動します `https://localhost:5001` 。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-331">The .NET core debugger typically launches to `https://localhost:5001`.</span></span> <span data-ttu-id="0f3c0-332">テスト キーを表示するには、スラッシュ (/) とキーの名前に `https://localhost:5001` 移動して追加します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-332">To view your test key, go to `https://localhost:5001` and append a forward slash (/) and the name of your key.</span></span> <span data-ttu-id="0f3c0-333">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-333">For example:</span></span>

   ```https
   https://localhost:5001/TestKey1
   ```

   <span data-ttu-id="0f3c0-334">キーは JSON 形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-334">The key should display in JSON format.</span></span>

<span data-ttu-id="0f3c0-335">これでセットアップが完了しました。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-335">Your setup is now complete.</span></span> <span data-ttu-id="0f3c0-336">jwtAudience 設定の appsettings.jsを公開する前に、ホスト名の値が App Service ホスト名と正確に一致するようにします。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-336">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="0f3c0-337">ビルドのトラブルシューティングを行う際に localhost に変更した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-337">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="deploy-the-dke-service-and-publish-the-key-store"></a><span data-ttu-id="0f3c0-338">DKE サービスを展開し、キー ストアを発行する</span><span class="sxs-lookup"><span data-stu-id="0f3c0-338">Deploy the DKE service and publish the key store</span></span>

<span data-ttu-id="0f3c0-339">実稼働展開の場合は、サード パーティ製のクラウドにサービスを展開するか、オンプレミス システム [に発行します](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&preserve-view=true&tabs=netcore-cli)。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-339">For production deployments, deploy the service either in a third-party cloud or [publish to an on-premises system](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&preserve-view=true&tabs=netcore-cli).</span></span>

<span data-ttu-id="0f3c0-340">他の方法でキーを展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-340">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="0f3c0-341">組織に最適な方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-341">Select the method that works best for your organization.</span></span>

<span data-ttu-id="0f3c0-342">パイロット展開の場合は、Azure に展開して、今すぐ開始できます。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-342">For pilot deployments, you can deploy in Azure and get started right away.</span></span>

<span data-ttu-id="0f3c0-343">**DKE 展開をホストする Azure Web App インスタンスを作成するには**</span><span class="sxs-lookup"><span data-stu-id="0f3c0-343">**To create an Azure Web App instance to host your DKE deployment**</span></span>

<span data-ttu-id="0f3c0-344">キー ストアを公開するには、DKE 展開をホストする Azure App Service インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-344">To publish the key store, you'll create an Azure App Service instance to host your DKE deployment.</span></span> <span data-ttu-id="0f3c0-345">次に、生成されたキーを Azure に公開します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-345">Next, you'll publish your generated keys to Azure.</span></span>

1. <span data-ttu-id="0f3c0-346">ブラウザーで Microsoft Azure ポータルにサインインし、[[アプリ](https://ms.portal.azure.com)サービスの追加]**に移動**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-346">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

2. <span data-ttu-id="0f3c0-347">サブスクリプションとリソース グループを選択し、インスタンスの詳細を定義します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-347">Select your subscription and resource group and define your instance details.</span></span>

   - <span data-ttu-id="0f3c0-348">DKE サービスをインストールするコンピューターのホスト名を入力します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-348">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="0f3c0-349">ファイルに対するファイルの JwtAudience 設定に定義されている名前と同appsettings.js [**してください**](#tenant-and-key-settings) 。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-349">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="0f3c0-350">名前に指定する値も WebAppInstanceName です。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-350">The value you provide for the name is also the WebAppInstanceName.</span></span>

   - <span data-ttu-id="0f3c0-351">[**発行]** でコード **を選択し**、ランタイム スタックの場合は **、[.NET Core 3.1] を選択します**。 </span><span class="sxs-lookup"><span data-stu-id="0f3c0-351">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

   <span data-ttu-id="0f3c0-352">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-352">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0f3c0-353">![App Service を追加する](../media/dke-azure-add-app-service.png)</span><span class="sxs-lookup"><span data-stu-id="0f3c0-353">![Add your App Service](../media/dke-azure-add-app-service.png)</span></span>

3. <span data-ttu-id="0f3c0-354">At the bottom of the page, select **Review + create,** and then select **Add**.</span><span class="sxs-lookup"><span data-stu-id="0f3c0-354">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

4. <span data-ttu-id="0f3c0-355">生成されたキーを発行するには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-355">Do one of the following to publish your generated keys:</span></span>

   - [<span data-ttu-id="0f3c0-356">ZipDeployUI を使用して発行する</span><span class="sxs-lookup"><span data-stu-id="0f3c0-356">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
   - [<span data-ttu-id="0f3c0-357">FTP 経由で発行する</span><span class="sxs-lookup"><span data-stu-id="0f3c0-357">Publish via FTP</span></span>](#publish-via-ftp)
   - [<span data-ttu-id="0f3c0-358">Visual Studio 2019 以降で発行する</span><span class="sxs-lookup"><span data-stu-id="0f3c0-358">Publish via Visual Studio 2019 or later</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/)

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="0f3c0-359">ZipDeployUI を使用して発行する</span><span class="sxs-lookup"><span data-stu-id="0f3c0-359">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="0f3c0-360">`https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI` に移動します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-360">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

   <span data-ttu-id="0f3c0-361">例: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="0f3c0-361">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

2. <span data-ttu-id="0f3c0-362">キー ストアのコードベースで **、customer-key-store\src\customer-key-store** フォルダーに移動し、このフォルダーに **customerkeystore.csproj** ファイルが含まれているか確認します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-362">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

3. <span data-ttu-id="0f3c0-363">実行: **dotnet 発行**</span><span class="sxs-lookup"><span data-stu-id="0f3c0-363">Run: **dotnet publish**</span></span>

   <span data-ttu-id="0f3c0-364">出力ウィンドウには、発行が展開されたディレクトリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-364">The output window displays the directory where the publish was deployed.</span></span>

   <span data-ttu-id="0f3c0-365">例: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="0f3c0-365">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

4. <span data-ttu-id="0f3c0-366">発行ディレクトリ内のすべてのファイルを .zip ファイルに送信します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-366">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="0f3c0-367">.zip ファイルを作成する場合は、ディレクトリ内のすべてのファイルが .zip ファイルのルート レベルに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-367">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

5. <span data-ttu-id="0f3c0-368">作成した .zip ファイルを、上で開いた ZipDeployUI サイトにドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-368">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="0f3c0-369">例: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="0f3c0-369">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="0f3c0-370">DKE が展開され、作成したテスト キーを参照できます。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-370">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="0f3c0-371">以下の展開 [の検証に進](#validate-your-deployment) んでください。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-371">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="0f3c0-372">FTP 経由で発行する</span><span class="sxs-lookup"><span data-stu-id="0f3c0-372">Publish via FTP</span></span>

1. <span data-ttu-id="0f3c0-373">上で作成したアプリ サービスに接続 [します](#deploy-the-dke-service-and-publish-the-key-store)。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-373">Connect to the App Service you created [above](#deploy-the-dke-service-and-publish-the-key-store).</span></span>

   <span data-ttu-id="0f3c0-374">ブラウザーで **、Azure portal** App Service 展開センターの  >    >  **手動展開** FTP  >  **ダッシュボード** に  >  **移動**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-374">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

2. <span data-ttu-id="0f3c0-375">表示された接続文字列をローカル ファイルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-375">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="0f3c0-376">これらの文字列を使用して Web App Service に接続し、FTP 経由でファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-376">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

   <span data-ttu-id="0f3c0-377">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-377">For example:</span></span>

   ![FTP ダッシュボードから接続文字列をコピーする](../media/dke-ftp-dashboard.png)

3. <span data-ttu-id="0f3c0-379">キー ストレージのコードベースで **、customer-key-store\src\customer-key-store ディレクトリに移動します**。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-379">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

4. <span data-ttu-id="0f3c0-380">このディレクトリに **customerkeystore.csproj ファイルが含まれているか確認** します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-380">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

5. <span data-ttu-id="0f3c0-381">実行: **dotnet 発行**</span><span class="sxs-lookup"><span data-stu-id="0f3c0-381">Run: **dotnet publish**</span></span>

   <span data-ttu-id="0f3c0-382">出力には、発行が展開されたディレクトリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-382">The output contains the directory where the publish was deployed.</span></span>

   <span data-ttu-id="0f3c0-383">例: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="0f3c0-383">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

6. <span data-ttu-id="0f3c0-384">発行ディレクトリ内のすべてのファイルを zip ファイルに送信します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-384">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="0f3c0-385">.zip ファイルを作成する場合は、ディレクトリ内のすべてのファイルが .zip ファイルのルート レベルに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-385">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

7. <span data-ttu-id="0f3c0-386">FTP クライアントから、コピーした接続情報を使用して App Service に接続します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-386">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="0f3c0-387">前の手順で作成した .zip ファイルを Web App のルート ディレクトリにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-387">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="0f3c0-388">DKE が展開され、作成したテスト キーを参照できます。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-388">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="0f3c0-389">次に、 [展開を検証します](#validate-your-deployment)。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-389">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="0f3c0-390">展開を検証する</span><span class="sxs-lookup"><span data-stu-id="0f3c0-390">Validate your deployment</span></span>

<span data-ttu-id="0f3c0-391">上記のいずれかの方法を使用して DKE を展開した後、展開とキー ストアの設定を検証します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-391">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="0f3c0-392">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-392">Run:</span></span>

```powershell
src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey
```

<span data-ttu-id="0f3c0-393">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-393">For example:</span></span>

```powershell
key_store_tester.ps1 https://mydkeservice.com/mykey
```

<span data-ttu-id="0f3c0-394">出力にエラーが表示されないか確認します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-394">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="0f3c0-395">準備ができたら、キー [ストアを登録します](#register-your-key-store)。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-395">When you're ready, [register your key store](#register-your-key-store).</span></span>

<span data-ttu-id="0f3c0-396">キー名では大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-396">The key name is case sensitive.</span></span> <span data-ttu-id="0f3c0-397">ファイルのコピーに表示されるキー名appsettings.js入力します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-397">Enter the key name as it appears in the appsettings.json file.</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="0f3c0-398">キー ストアを登録する</span><span class="sxs-lookup"><span data-stu-id="0f3c0-398">Register your key store</span></span>

<span data-ttu-id="0f3c0-399">次の手順を実行すると、DKE サービスを登録できます。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-399">The following steps enable you to register your DKE service.</span></span> <span data-ttu-id="0f3c0-400">DKE サービスの登録は、ラベルの作成を開始する前に DKE を展開する最後の手順です。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-400">Registering your DKE service is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="0f3c0-401">DKE サービスを登録するには:</span><span class="sxs-lookup"><span data-stu-id="0f3c0-401">To register the DKE service:</span></span>

1. <span data-ttu-id="0f3c0-402">ブラウザーで [、Microsoft Azure ポータルを開](https://ms.portal.azure.com/)き、[すべての **サービス** ID アプリの登録] \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-402">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="0f3c0-403">[ **新規登録] を** 選択し、わかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-403">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="0f3c0-404">表示されるオプションからアカウントの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-404">Select an account type from the options displayed.</span></span>

   <span data-ttu-id="0f3c0-405">**onmicrosoft.com** などの非カスタム ドメインで Microsoft Azure を使用している場合は、この組織のディレクトリでのみ [アカウント] を選択します **(Microsoft のみ - シングル テナント)。**</span><span class="sxs-lookup"><span data-stu-id="0f3c0-405">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

   <span data-ttu-id="0f3c0-406">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-406">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0f3c0-407">![新しいアプリの登録](../media/dke-app-registration.png)</span><span class="sxs-lookup"><span data-stu-id="0f3c0-407">![New App Registration](../media/dke-app-registration.png)</span></span>

4. <span data-ttu-id="0f3c0-408">ページの下部にある [登録] **を選択して** 、新しいアプリ登録を作成します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-408">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="0f3c0-409">新しいアプリの登録の左側のウィンドウで、[管理] の下の **[** 認証] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-409">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="0f3c0-410">[プラットフォーム **の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-410">Select **Add a platform**.</span></span>

7. <span data-ttu-id="0f3c0-411">[プラットフォーム **の構成] ポップアップで\*\*\*\*、[Web] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-411">On the **Configure platforms** popup, select **Web**.</span></span>

8. <span data-ttu-id="0f3c0-412">[ **リダイレクト URI] で**、二重キー暗号化サービスの URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-412">Under **Redirect URIs**, enter the URI of your double key encryption service.</span></span> <span data-ttu-id="0f3c0-413">ホスト名とドメインの両方を含む、アプリ サービスの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-413">Enter the App Service URL, including both the hostname and domain.</span></span>

   <span data-ttu-id="0f3c0-414">例: https://mydkeservicetest.com</span><span class="sxs-lookup"><span data-stu-id="0f3c0-414">For example: https://mydkeservicetest.com</span></span>

   - <span data-ttu-id="0f3c0-415">入力する URL は、DKE サービスが展開されているホスト名と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-415">The URL you enter must match the hostname where your DKE service is deployed.</span></span>
   - <span data-ttu-id="0f3c0-416">If you're testing locally with Visual Studio, use **https://localhost:5001** .</span><span class="sxs-lookup"><span data-stu-id="0f3c0-416">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
   - <span data-ttu-id="0f3c0-417">すべての場合、スキームは https である **必要があります**。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-417">In all cases, the scheme must be **https**.</span></span>

   <span data-ttu-id="0f3c0-418">ホスト名が App Service のホスト名と正確に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-418">Ensure the hostname exactly matches your App Service hostname.</span></span> <span data-ttu-id="0f3c0-419">ビルドのトラブルシューティングに変更 `localhost` した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-419">You may have changed it to `localhost` to troubleshoot the build.</span></span> <span data-ttu-id="0f3c0-420">In **appsettings.json,** this value is the hostname you set for `JwtAudience` .</span><span class="sxs-lookup"><span data-stu-id="0f3c0-420">In **appsettings.json**, this value is the hostname you set for `JwtAudience`.</span></span>

9. <span data-ttu-id="0f3c0-421">[**暗黙的な許可] で\*\*\*\*、[ID トークン] チェック ボックスをオン** にします。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-421">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

10. <span data-ttu-id="0f3c0-422">**[保存]** を選択し、変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-422">Select **Save** to save your changes.</span></span>

11. <span data-ttu-id="0f3c0-423">左側のウィンドウで、[API の公開] **を選択** し、[アプリケーション ID URI] の横にある [設定] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-423">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

12. <span data-ttu-id="0f3c0-424">引き続き **[API の** 公開] ページで、この **API** 領域で定義されているスコープで、[スコープの追加 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-424">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="0f3c0-425">新しいスコープで、次の条件を実行します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-425">In the new scope:</span></span>

    1. <span data-ttu-id="0f3c0-426">スコープ名を次のように **定義user_impersonation。**</span><span class="sxs-lookup"><span data-stu-id="0f3c0-426">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="0f3c0-427">同意できる管理者とユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-427">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="0f3c0-428">必要な残りの値を定義します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-428">Define any remaining values required.</span></span>

    4. <span data-ttu-id="0f3c0-429">**[スコープの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-429">Select **Add scope**.</span></span>

    5. <span data-ttu-id="0f3c0-430">上部 **の [** 保存] を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-430">Select **Save** at the top to save your changes.</span></span>

13. <span data-ttu-id="0f3c0-431">引き続き **[API の** 公開] ページの [承認された **クライアント** アプリケーション] 領域で、[クライアント アプリケーションの追加 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-431">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="0f3c0-432">新しいクライアント アプリケーションで、次の条件を実行します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-432">In the new client application:</span></span>

    1. <span data-ttu-id="0f3c0-433">クライアント ID を **d3590ed6-52b3-4102-aeff-aad2292ab01c** として定義します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-433">Define the Client ID as **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span></span> <span data-ttu-id="0f3c0-434">この値はクライアント ID Microsoft Officeであり、キー ストアOfficeトークンを取得できます。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-434">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="0f3c0-435">[ **承認済みスコープ] で、** 有効なスコープ **user_impersonation** します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-435">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="0f3c0-436">**[アプリケーションの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-436">Select **Add application**.</span></span>

    4. <span data-ttu-id="0f3c0-437">上部 **の [** 保存] を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-437">Select **Save** at the top to save your changes.</span></span>

<span data-ttu-id="0f3c0-438">これで、DKE サービスが登録されました。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-438">Your DKE service is now registered.</span></span> <span data-ttu-id="0f3c0-439">[DKE を使用してラベルを作成します](#create-sensitivity-labels-using-dke)。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-439">Continue by [creating labels using DKE](#create-sensitivity-labels-using-dke).</span></span>

## <a name="create-sensitivity-labels-using-dke"></a><span data-ttu-id="0f3c0-440">DKE を使用して感度ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="0f3c0-440">Create sensitivity labels using DKE</span></span>

<span data-ttu-id="0f3c0-441">Microsoft 365 コンプライアンス センターで、新しい区別ラベルを作成し、それ以外の場合と同様に暗号化を適用します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-441">In the Microsoft 365 compliance center, create a new sensitivity label and apply encryption as you would otherwise.</span></span> <span data-ttu-id="0f3c0-442">[Use **Double Key Encryption] を選択** し、キーのエンドポイント URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-442">Select **Use Double Key Encryption** and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="0f3c0-443">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-443">For example:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0f3c0-444">![Microsoft 365 コンプライアンス センターで [二重キー暗号化を使用する] を選択する](../media/dke-use-dke.png)</span><span class="sxs-lookup"><span data-stu-id="0f3c0-444">![Select Use Double Key Encryption in the Microsoft 365 compliance center](../media/dke-use-dke.png)</span></span>

<span data-ttu-id="0f3c0-445">追加した DKE ラベルは、Microsoft 365 Apps for enterprise の最新バージョンのユーザーに対して表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-445">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="0f3c0-446">クライアントが新しいラベルで更新するには、最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-446">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="0f3c0-447">クライアントで DKE を有効にする</span><span class="sxs-lookup"><span data-stu-id="0f3c0-447">Enable DKE in your client</span></span>

<span data-ttu-id="0f3c0-448">Insider を使用している場合Office DKE が有効になります。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-448">If you're an Office Insider, DKE is enabled for you.</span></span> <span data-ttu-id="0f3c0-449">それ以外の場合は、次のレジストリ キーを追加して、クライアントの DKE を有効にします。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-449">Otherwise, enable DKE for your client by adding the following registry keys:</span></span>

```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001

   [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001
```

## <a name="migrate-protected-files-from-hyok-labels-to-dke-labels"></a><span data-ttu-id="0f3c0-450">保護されたファイルを HYOK ラベルから DKE ラベルに移行する</span><span class="sxs-lookup"><span data-stu-id="0f3c0-450">Migrate protected files from HYOK labels to DKE labels</span></span>

<span data-ttu-id="0f3c0-451">必要な場合は、DKE の設定が完了したら、HYOK ラベルを使用して保護したコンテンツを DKE ラベルに移行できます。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-451">If you want, once you're finished setting up DKE, you can migrate content that you've protected using HYOK labels to DKE labels.</span></span> <span data-ttu-id="0f3c0-452">移行するには、AIP スキャナーを使用します。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-452">To migrate, you'll use the AIP scanner.</span></span> <span data-ttu-id="0f3c0-453">スキャナーの使用を開始するには、「Azure Information Protection 統合ラベル付けスキャナー [とは」を参照してください](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-453">To get started using the scanner, see [What is the Azure Information Protection unified labeling scanner?](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner).</span></span>

<span data-ttu-id="0f3c0-454">コンテンツを移行しない場合、HYOK で保護されたコンテンツは影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-454">If you don't migrate content, your HYOK protected content will remain unaffected.</span></span>
