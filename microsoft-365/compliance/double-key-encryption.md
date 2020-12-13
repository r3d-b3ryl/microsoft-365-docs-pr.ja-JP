---
title: 二重キー暗号化 (DKE)
description: DKE を使用すると、キーのフル コントロールを維持しながら、機密性の高いデータを保護できます。
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
ms.openlocfilehash: 9607b095ba073229edae43c1d2f0e893db07c634
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663092"
---
# <a name="double-key-encryption-for-microsoft-365"></a><span data-ttu-id="c104e-103">Microsoft 365 の二重キー暗号化</span><span class="sxs-lookup"><span data-stu-id="c104e-103">Double Key Encryption for Microsoft 365</span></span>

> <span data-ttu-id="c104e-104">*適用対象: Microsoft 365 の二重キー暗号化 [、Microsoft 365 コンプライアンス](https://www.microsoft.com/microsoft-365/business/compliance-management)[、Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span><span class="sxs-lookup"><span data-stu-id="c104e-104">*Applies to: Double Key Encryption for Microsoft 365, [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="c104e-105">*手順: [Windows 用 Azure Information Protection 統合ラベル付けクライアント](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span><span class="sxs-lookup"><span data-stu-id="c104e-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="c104e-106">*サービスの説明: [Microsoft 365 コンプライアンス](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="c104e-106">*Service description for: [Microsoft 365 Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="c104e-107">二重キー暗号化 (DKE) では、2 つのキーを組み合わせて使用して、保護されたコンテンツにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="c104e-107">Double Key Encryption (DKE) uses two keys together to access protected content.</span></span> <span data-ttu-id="c104e-108">Microsoft は 1 つのキーを Microsoft Azure に保存し、もう一方のキーを保持します。</span><span class="sxs-lookup"><span data-stu-id="c104e-108">Microsoft stores one key in Microsoft Azure, and you hold the other key.</span></span> <span data-ttu-id="c104e-109">Double Key Encryption サービスを使用して、キーの 1 つを完全に制御します。</span><span class="sxs-lookup"><span data-stu-id="c104e-109">You maintain full control of one of your keys using the Double Key Encryption service.</span></span> <span data-ttu-id="c104e-110">Azure Information Protection 統合ラベル付けクライアントを使用して、機密性の高いコンテンツに保護を適用します。</span><span class="sxs-lookup"><span data-stu-id="c104e-110">You apply protection using The Azure Information Protection unified labeling client to your highly sensitive content.</span></span>

<span data-ttu-id="c104e-111">二重キー暗号化は、クラウドとオンプレミスの両方の展開をサポートします。</span><span class="sxs-lookup"><span data-stu-id="c104e-111">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="c104e-112">これらの展開は、保護されたデータを保存する場所で暗号化されたデータが不透明なままに維持されるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c104e-112">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="c104e-113">既定のクラウドベースのテナント ルート キーの詳細については [、「Azure Information Protection](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)テナント キーの計画と実装」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c104e-113">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span></span>

## <a name="when-your-organization-should-adopt-dke"></a><span data-ttu-id="c104e-114">組織で DKE を採用する必要が生じ</span><span class="sxs-lookup"><span data-stu-id="c104e-114">When your organization should adopt DKE</span></span>

<span data-ttu-id="c104e-115">二重キー暗号化は、最も厳しい保護要件の対象となる最も機密性の高いデータを対象とします。</span><span class="sxs-lookup"><span data-stu-id="c104e-115">Double Key Encryption is intended for your most sensitive data that is subject to the strictest protection requirements.</span></span> <span data-ttu-id="c104e-116">DKE は、すべてのデータを対象としているのではありません。</span><span class="sxs-lookup"><span data-stu-id="c104e-116">DKE is not intended for all data.</span></span> <span data-ttu-id="c104e-117">一般に、Double Key Encryption を使用して、データ全体の一部のみを保護します。</span><span class="sxs-lookup"><span data-stu-id="c104e-117">In general, you'll be using Double Key Encryption to protect only a very small part of your overall data.</span></span> <span data-ttu-id="c104e-118">展開する前に、このソリューションでカバーする適切なデータを特定する上で注意を引く必要があります。</span><span class="sxs-lookup"><span data-stu-id="c104e-118">You should do due diligence in identifying the right data to cover with this solution before you deploy.</span></span> <span data-ttu-id="c104e-119">場合によっては、Microsoft が管理するキーや BYOK を使用した Microsoft Information Protection など、データの大部分に対して範囲を絞り込み、その他のソリューションを利用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c104e-119">In some cases, you might need to narrow your scope and make use of other solutions for the majority of your data such as Microsoft Information Protection with Microsoft-managed keys or BYOK.</span></span> <span data-ttu-id="c104e-120">これらのソリューションは、強化された保護と規制要件の対象ではないドキュメントでは十分です。</span><span class="sxs-lookup"><span data-stu-id="c104e-120">These solutions are sufficient for documents that aren't subject to enhanced protections and regulatory requirements.</span></span> <span data-ttu-id="c104e-121">また、これらのソリューションを使用すると、最も強力な Office 365 サービスを使用できます。DKE で暗号化されたコンテンツでは使用できないサービス。</span><span class="sxs-lookup"><span data-stu-id="c104e-121">Also, these solutions enable you to use the most powerful Office 365 services; services that you can't use with DKE encrypted content.</span></span> <span data-ttu-id="c104e-122">例:</span><span class="sxs-lookup"><span data-stu-id="c104e-122">For example:</span></span>

- <span data-ttu-id="c104e-123">添付ファイルの可視性が必要なマルウェア対策とスパムを含むトランスポート ルール</span><span class="sxs-lookup"><span data-stu-id="c104e-123">Transport rules including anti-malware and spam that require visibility into the attachment</span></span>
- <span data-ttu-id="c104e-124">Microsoft Delve</span><span class="sxs-lookup"><span data-stu-id="c104e-124">Microsoft Delve</span></span>
- <span data-ttu-id="c104e-125">電子情報開示</span><span class="sxs-lookup"><span data-stu-id="c104e-125">eDiscovery</span></span>
- <span data-ttu-id="c104e-126">コンテンツ検索とインデックス作成</span><span class="sxs-lookup"><span data-stu-id="c104e-126">Content search and indexing</span></span>
- <span data-ttu-id="c104e-127">Office機能を含む Web アプリの作成</span><span class="sxs-lookup"><span data-stu-id="c104e-127">Office Web Apps including co-authoring functionality</span></span>

<span data-ttu-id="c104e-128">MIP SDK を介して DKE と統合されていない外部アプリケーションまたはサービスは、暗号化されたデータに対してアクションを実行できません。</span><span class="sxs-lookup"><span data-stu-id="c104e-128">Any external applications or services that are not integrated with DKE through the MIP SDK will be unable to perform actions on the encrypted data.</span></span>

<span data-ttu-id="c104e-129">Microsoft Information Protection SDK 1.7+ は、二重キー暗号化をサポートしています。SDK と統合するアプリケーションは、十分なアクセス許可と統合を適用して、このデータを理由にできます。</span><span class="sxs-lookup"><span data-stu-id="c104e-129">The Microsoft Information Protection SDK 1.7+ supports Double Key Encryption; applications that integrate with our SDK will be able to reason over this data with sufficient permissions and integrations in place.</span></span>

<span data-ttu-id="c104e-130">組織では、Microsoft 情報保護機能 (分類とラベル付け) を使用して機密データのほとんどを保護し、ミッション クリティカルなデータにのみ DKE を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c104e-130">We recommend organizations use Microsoft Information protection capabilities (classification and labeling) to protect most of their sensitive data and only use DKE for their mission-critical data.</span></span> <span data-ttu-id="c104e-131">二重キー暗号化は、金融サービスや医療などの厳しく規制された業界の非常に機密性の高いデータに特に関連します。</span><span class="sxs-lookup"><span data-stu-id="c104e-131">Double Key Encryption is particularly relevant for extremely sensitive data in highly regulated industries such as Financial services and Healthcare.</span></span>

<span data-ttu-id="c104e-132">組織に次の要件がある場合は、DKE を使用してコンテンツをセキュリティで保護できます。</span><span class="sxs-lookup"><span data-stu-id="c104e-132">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="c104e-133">すべての状況で、 *保護* されたコンテンツの暗号化を解除できるのは自分だけである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c104e-133">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="c104e-134">Microsoft が独自に保護されたデータにアクセスしたくはない。</span><span class="sxs-lookup"><span data-stu-id="c104e-134">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="c104e-135">地理的境界内にキーを保持する規制要件があります。</span><span class="sxs-lookup"><span data-stu-id="c104e-135">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="c104e-136">データの暗号化と暗号化解除のために保持するキーはすべて、データ センターで保持されます。</span><span class="sxs-lookup"><span data-stu-id="c104e-136">All of the keys that you hold for data encryption and decryption are maintained in your data center.</span></span>

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="c104e-137">DKE のシステム要件とライセンス要件</span><span class="sxs-lookup"><span data-stu-id="c104e-137">System and licensing requirements for DKE</span></span>

<span data-ttu-id="c104e-138">**Microsoft 365 の二** 重キー暗号化には、Microsoft 365 E5 が付属しています。</span><span class="sxs-lookup"><span data-stu-id="c104e-138">**Double Key Encryption for Microsoft 365** comes with Microsoft 365 E5.</span></span> <span data-ttu-id="c104e-139">Microsoft 365 E5 ライセンスをお持ちない場合は、試用版にサインアップ [できます](https://aka.ms/M365E5ComplianceTrial)。</span><span class="sxs-lookup"><span data-stu-id="c104e-139">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="c104e-140">これらのライセンスの詳細については、セキュリティとコンプライアンスに関する [Microsoft 365 ライセンス ガイダンス&してください](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="c104e-140">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="c104e-141">**Azure Information Protection**。</span><span class="sxs-lookup"><span data-stu-id="c104e-141">**Azure Information Protection**.</span></span> <span data-ttu-id="c104e-142">DKE は、区別ラベルで動作し、Azure Information Protection を必要とします。</span><span class="sxs-lookup"><span data-stu-id="c104e-142">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

<span data-ttu-id="c104e-143">DKE の感度ラベルは、デスクトップ アプリでエンド ユーザーがOfficeできます。</span><span class="sxs-lookup"><span data-stu-id="c104e-143">DKE sensitivity labels are made available to end-users through the sensitivity ribbon in Office Desktop Apps.</span></span> <span data-ttu-id="c104e-144">保護されたドキュメントを保護して使用する各クライアント コンピューターに、これらの前提条件をインストールします。</span><span class="sxs-lookup"><span data-stu-id="c104e-144">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="c104e-145">**Microsoft Office の** エンタープライズ バージョン \*.12711 以降 (デスクトップ バージョンの Word、PowerPoint、Excel) 用アプリ。</span><span class="sxs-lookup"><span data-stu-id="c104e-145">**Microsoft Office Apps for enterprise** version \*.12711 or later (Desktop versions of Word, PowerPoint, and Excel) on Windows.</span></span>

<span data-ttu-id="c104e-146">**Azure Information Protection 統合ラベル付けクライアント** バージョン 2.7.93.0 以降。</span><span class="sxs-lookup"><span data-stu-id="c104e-146">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="c104e-147">Microsoft ダウンロード センターから統合ラベル付けクライアントを [ダウンロードしてインストールします](https://www.microsoft.com/download/details.aspx?id=53018)。</span><span class="sxs-lookup"><span data-stu-id="c104e-147">Download and install the Unified Labeling client from the [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="c104e-148">DKE で保護されたコンテンツを保存および表示するためのサポートされている環境</span><span class="sxs-lookup"><span data-stu-id="c104e-148">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="c104e-149">**サポートされているアプリケーション**。</span><span class="sxs-lookup"><span data-stu-id="c104e-149">**Supported applications**.</span></span> <span data-ttu-id="c104e-150">Word、Excel、PowerPoint を含む、Windows 上の[Microsoft 365](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) Apps for enterprise クライアント。</span><span class="sxs-lookup"><span data-stu-id="c104e-150">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="c104e-151">**オンライン コンテンツのサポート**。</span><span class="sxs-lookup"><span data-stu-id="c104e-151">**Online content support**.</span></span> <span data-ttu-id="c104e-152">Microsoft SharePoint と OneDrive for Business の両方にオンラインで保存されているドキュメントとファイルがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c104e-152">Documents and files stored online in both Microsoft SharePoint and OneDrive for Business are supported.</span></span> <span data-ttu-id="c104e-153">暗号化されたコンテンツは電子メールで共有できますが、暗号化されたドキュメントやファイルをオンラインで表示できません。</span><span class="sxs-lookup"><span data-stu-id="c104e-153">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="c104e-154">代わりに、ローカル コンピューター上のデスクトップ アプリを使用して、保護されたコンテンツを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c104e-154">Instead, you must view protected content using the desktop apps on your local computer.</span></span>

## <a name="overview-of-deploying-dke"></a><span data-ttu-id="c104e-155">DKE の展開の概要</span><span class="sxs-lookup"><span data-stu-id="c104e-155">Overview of deploying DKE</span></span>

<span data-ttu-id="c104e-156">DKE をセットアップするには、次の一般的な手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c104e-156">You'll follow these general steps to set up DKE.</span></span> <span data-ttu-id="c104e-157">これらの手順を完了すると、エンド ユーザーは、二重キー暗号化を使用して機密性の高いデータを保護できます。</span><span class="sxs-lookup"><span data-stu-id="c104e-157">Once you've completed these steps, your end users will be able to protect your highly sensitive data with Double Key Encryption.</span></span>

1. <span data-ttu-id="c104e-158">この記事の説明に従って DKE サービスを展開します。</span><span class="sxs-lookup"><span data-stu-id="c104e-158">Deploy the DKE service as described in this article.</span></span>

2. <span data-ttu-id="c104e-159">二重キー暗号化を使用してラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="c104e-159">Create a label with Double Key Encryption.</span></span> <span data-ttu-id="c104e-160">[Microsoft 365](https://compliance.microsoft.com)コンプライアンス センターの下の情報保護に移動し、二重キー暗号化を使用して新しいラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="c104e-160">Navigate to Information protection under the [Microsoft 365 compliance center](https://compliance.microsoft.com) and create a new label with Double Key Encryption.</span></span> <span data-ttu-id="c104e-161">「 [コンテンツへのアクセスを制限する」を参照してください。暗号化を適用するには、区別ラベルを使用します](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="c104e-161">See [Restrict access to content by using sensitivity labels to apply encryption](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels).</span></span>

3. <span data-ttu-id="c104e-162">二重キー暗号化ラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="c104e-162">Use Double Key Encryption labels.</span></span> <span data-ttu-id="c104e-163">データを保護するには、次のページの [Sensitivity] リボンで [Double Key Encrypted] ラベルをMicrosoft Office。</span><span class="sxs-lookup"><span data-stu-id="c104e-163">Protect data by selecting the Double Key Encrypted label from the Sensitivity ribbon in Microsoft Office.</span></span>

<span data-ttu-id="c104e-164">二重キー暗号化を展開するには、いくつかの手順を実行する方法があります。</span><span class="sxs-lookup"><span data-stu-id="c104e-164">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="c104e-165">この記事では、経験の少ない管理者がサービスを正常に展開できるよう、詳細な手順を示します。</span><span class="sxs-lookup"><span data-stu-id="c104e-165">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="c104e-166">この方法に問題が生じない場合は、独自の方法を選択できます。</span><span class="sxs-lookup"><span data-stu-id="c104e-166">If you're comfortable doing so, you can choose to use your own methods.</span></span>

## <a name="deploy-dke"></a><span data-ttu-id="c104e-167">DKE の展開</span><span class="sxs-lookup"><span data-stu-id="c104e-167">Deploy DKE</span></span>

<span data-ttu-id="c104e-168">この記事と展開ビデオでは、DKE サービスの展開先として Azure を使用します。</span><span class="sxs-lookup"><span data-stu-id="c104e-168">This article and the deployment video use Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="c104e-169">別の場所に展開する場合は、独自の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c104e-169">If you're deploying to another location, you'll need to provide your own values.</span></span>

<span data-ttu-id="c104e-170">二重 [キー暗号化の展開のビデオ](https://youtu.be/vDWfHN_kygg) を見て、この記事の概念の詳しい概要を確認してください。</span><span class="sxs-lookup"><span data-stu-id="c104e-170">Watch the [Double Key Encryption deployment video](https://youtu.be/vDWfHN_kygg) to see a step-by-step overview of the concepts in this article.</span></span> <span data-ttu-id="c104e-171">ビデオが完成するのに約 18 分かかります。</span><span class="sxs-lookup"><span data-stu-id="c104e-171">The video takes about 18 minutes to complete.</span></span>

<span data-ttu-id="c104e-172">次の一般的な手順に従って、組織の二重キー暗号化を設定します。</span><span class="sxs-lookup"><span data-stu-id="c104e-172">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span>

1. [<span data-ttu-id="c104e-173">DKE サービスの前提条件ソフトウェアをインストールする</span><span class="sxs-lookup"><span data-stu-id="c104e-173">Install software prerequisites for the DKE service</span></span>](#install-software-prerequisites-for-the-dke-service)
1. [<span data-ttu-id="c104e-174">二重キー暗号化 GitHub リポジトリを複製する</span><span class="sxs-lookup"><span data-stu-id="c104e-174">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="c104e-175">アプリケーション設定の変更</span><span class="sxs-lookup"><span data-stu-id="c104e-175">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="c104e-176">テスト キーを生成する</span><span class="sxs-lookup"><span data-stu-id="c104e-176">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="c104e-177">プロジェクトをビルドする</span><span class="sxs-lookup"><span data-stu-id="c104e-177">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="c104e-178">DKE サービスを展開し、キー ストアを発行する</span><span class="sxs-lookup"><span data-stu-id="c104e-178">Deploy the DKE service and publish the key store</span></span>](#deploy-the-dke-service-and-publish-the-key-store)
1. [<span data-ttu-id="c104e-179">展開を検証する</span><span class="sxs-lookup"><span data-stu-id="c104e-179">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="c104e-180">キー ストアを登録する</span><span class="sxs-lookup"><span data-stu-id="c104e-180">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="c104e-181">DKE を使用して感度ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="c104e-181">Create sensitivity labels using DKE</span></span>](#create-sensitivity-labels-using-dke)
1. [<span data-ttu-id="c104e-182">クライアントで DKE を有効にする</span><span class="sxs-lookup"><span data-stu-id="c104e-182">Enable DKE in your client</span></span>](#enable-dke-in-your-client)
1. [<span data-ttu-id="c104e-183">保護されたファイルを HYOK ラベルから DKE ラベルに移行する</span><span class="sxs-lookup"><span data-stu-id="c104e-183">Migrate protected files from HYOK labels to DKE labels</span></span>](#migrate-protected-files-from-hyok-labels-to-dke-labels)

<span data-ttu-id="c104e-184">完了したら、DKE を使用してドキュメントとファイルを暗号化できます。</span><span class="sxs-lookup"><span data-stu-id="c104e-184">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="c104e-185">詳細については、「ファイルと [電子メールにラベル](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)を適用する」を参照Office。</span><span class="sxs-lookup"><span data-stu-id="c104e-185">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites-for-the-dke-service"></a><span data-ttu-id="c104e-186">DKE サービスの前提条件ソフトウェアをインストールする</span><span class="sxs-lookup"><span data-stu-id="c104e-186">Install software prerequisites for the DKE service</span></span>

<span data-ttu-id="c104e-187">これらの前提条件を、DKE サービスをインストールするコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="c104e-187">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="c104e-188">**.NET Core 3.1 SDK**.</span><span class="sxs-lookup"><span data-stu-id="c104e-188">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="c104e-189">[DOWNLOAD .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)から SDK をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="c104e-189">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="c104e-190">**Visual Studio コード**。</span><span class="sxs-lookup"><span data-stu-id="c104e-190">**Visual Studio Code**.</span></span> <span data-ttu-id="c104e-191">コードVisual Studioダウンロードします [https://code.visualstudio.com/](https://code.visualstudio.com) 。</span><span class="sxs-lookup"><span data-stu-id="c104e-191">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="c104e-192">インストールが完了したら、Visual Studioコードを実行し、[拡張機能の **表示]** \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c104e-192">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="c104e-193">これらの拡張機能をインストールします。</span><span class="sxs-lookup"><span data-stu-id="c104e-193">Install these extensions.</span></span>

- <span data-ttu-id="c104e-194">コードの C# Visual Studioコード</span><span class="sxs-lookup"><span data-stu-id="c104e-194">C# for Visual Studio Code</span></span>

- <span data-ttu-id="c104e-195">NuGet パッケージ マネージャー</span><span class="sxs-lookup"><span data-stu-id="c104e-195">NuGet Package Manager</span></span>

<span data-ttu-id="c104e-196">**Git リソース**。</span><span class="sxs-lookup"><span data-stu-id="c104e-196">**Git resources**.</span></span> <span data-ttu-id="c104e-197">次のいずれかをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="c104e-197">Download and install one of the following.</span></span>

- [<span data-ttu-id="c104e-198">Git</span><span class="sxs-lookup"><span data-stu-id="c104e-198">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="c104e-199">GitHub デスクトップ</span><span class="sxs-lookup"><span data-stu-id="c104e-199">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="c104e-200">GitHub Enterprise</span><span class="sxs-lookup"><span data-stu-id="c104e-200">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="c104e-201">**OpenSSL** DKE の展開 [後にテスト キー](https://slproweb.com/products/Win32OpenSSL.html) を [生成するには、OpenSSL](#generate-test-keys) がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c104e-201">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="c104e-202">環境変数パスから正しく呼び出されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c104e-202">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="c104e-203">たとえば、詳細については、「インストール ディレクトリを PATH に追加する」 [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c104e-203">For example, see "Add the installation directory to PATH" at [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) for details.</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="c104e-204">DKE GitHub リポジトリを複製する</span><span class="sxs-lookup"><span data-stu-id="c104e-204">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="c104e-205">Microsoft は、GitHub リポジトリに DKE ソース ファイルを提供しています。</span><span class="sxs-lookup"><span data-stu-id="c104e-205">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="c104e-206">リポジトリを複製して、組織で使用するためにプロジェクトをローカルにビルドします。</span><span class="sxs-lookup"><span data-stu-id="c104e-206">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="c104e-207">DKE GitHub リポジトリの場所は次の場所にあります [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) 。</span><span class="sxs-lookup"><span data-stu-id="c104e-207">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="c104e-208">次の手順は、経験の浅い git またはコード Visual Studio向けです。</span><span class="sxs-lookup"><span data-stu-id="c104e-208">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="c104e-209">ブラウザーで、次の場所に移動します [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) 。</span><span class="sxs-lookup"><span data-stu-id="c104e-209">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

2. <span data-ttu-id="c104e-210">画面の右側に移動し、[コード] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c104e-210">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="c104e-211">バージョンの UI に [複製] または [ダウンロード] **ボタンが表示される場合** があります。</span><span class="sxs-lookup"><span data-stu-id="c104e-211">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="c104e-212">次に、表示されるドロップダウンでコピー アイコンを選択し、URL をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="c104e-212">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="c104e-213">例:</span><span class="sxs-lookup"><span data-stu-id="c104e-213">For example:</span></span>

   ![GitHub から Double Key Encryption サービス リポジトリを複製する](../media/dke-clone.png)

3. <span data-ttu-id="c104e-215">[コードVisual Studioコマンド パレットの **表示]** \> **を** 選択し **、[Git:** Clone] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c104e-215">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="c104e-216">リスト内のオプションに移動するには、入力を開始してエントリをフィルター処理し、ドロップダウン `git: clone` から選択します。</span><span class="sxs-lookup"><span data-stu-id="c104e-216">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="c104e-217">例:</span><span class="sxs-lookup"><span data-stu-id="c104e-217">For example:</span></span>

   ![Visual Studio GIT:Clone オプション](../media/dke-vscode-clone.png)

4. <span data-ttu-id="c104e-219">テキスト ボックスに、Git からコピーした URL を貼り付け **、GitHub から [Clone] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c104e-219">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="c104e-220">表示される **[フォルダーの** 選択] ダイアログで、リポジトリを格納する場所を参照して選択します。</span><span class="sxs-lookup"><span data-stu-id="c104e-220">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="c104e-221">プロンプトで、[開く] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c104e-221">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="c104e-222">リポジトリがコードVisual Studio開き、左下に現在の Git 分岐が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c104e-222">The repository opens in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="c104e-223">分岐はマスター である **必要があります**。</span><span class="sxs-lookup"><span data-stu-id="c104e-223">The branch should be **master**.</span></span>

    <span data-ttu-id="c104e-224">例:</span><span class="sxs-lookup"><span data-stu-id="c104e-224">For example:</span></span>

   ![Visual Studio コード マスター分岐](../media/dke-vscode-master.png)

6. <span data-ttu-id="c104e-226">分岐の一 **覧から** 単語マスターを選択します。</span><span class="sxs-lookup"><span data-stu-id="c104e-226">Select the word **master** from the list of branches.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="c104e-227">マスター分岐を選択すると、プロジェクトをビルドするための適切なファイルが確実に作成されます。</span><span class="sxs-lookup"><span data-stu-id="c104e-227">Selecting the master branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="c104e-228">正しい分岐を選択しない場合、展開は失敗します。</span><span class="sxs-lookup"><span data-stu-id="c104e-228">If you do not choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="c104e-229">これで、DKE ソース リポジトリがローカルにセットアップされます。</span><span class="sxs-lookup"><span data-stu-id="c104e-229">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="c104e-230">次に [、組織のアプリケーション設定](#modify-application-settings) を変更します。</span><span class="sxs-lookup"><span data-stu-id="c104e-230">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="c104e-231">アプリケーション設定の変更</span><span class="sxs-lookup"><span data-stu-id="c104e-231">Modify application settings</span></span>

<span data-ttu-id="c104e-232">DKE サービスを展開するには、次の種類のアプリケーション設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c104e-232">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="c104e-233">キー アクセスの設定</span><span class="sxs-lookup"><span data-stu-id="c104e-233">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="c104e-234">テナントとキーの設定</span><span class="sxs-lookup"><span data-stu-id="c104e-234">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="c104e-235">アプリケーション設定は、ファイルのappsettings.js変更します。</span><span class="sxs-lookup"><span data-stu-id="c104e-235">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="c104e-236">このファイルは、ローカルで DoubleKeyEncryptionService\src\customer-key-store の下に複製した DoubleKeyEncryptionService リポジトリにあります。</span><span class="sxs-lookup"><span data-stu-id="c104e-236">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="c104e-237">たとえば、コードVisual Studio、次の図に示すようにファイルを参照できます。</span><span class="sxs-lookup"><span data-stu-id="c104e-237">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

![DKE 用appsettings.jsの場所。](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a><span data-ttu-id="c104e-239">キー アクセスの設定</span><span class="sxs-lookup"><span data-stu-id="c104e-239">Key access settings</span></span>

<span data-ttu-id="c104e-240">電子メールまたは役割の承認を使用するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="c104e-240">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="c104e-241">DKE では、一度にサポートされる認証方法は 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="c104e-241">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="c104e-242">**電子メールの承認**。</span><span class="sxs-lookup"><span data-stu-id="c104e-242">**Email authorization**.</span></span> <span data-ttu-id="c104e-243">電子メール アドレスにのみ基づいてキーへのアクセスを組織が承認できます。</span><span class="sxs-lookup"><span data-stu-id="c104e-243">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="c104e-244">**役割の承認**。</span><span class="sxs-lookup"><span data-stu-id="c104e-244">**Role authorization**.</span></span> <span data-ttu-id="c104e-245">組織が Active Directory グループに基づいてキーへのアクセスを承認し、Web サービスが LDAP を照会できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c104e-245">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="c104e-246">**電子メールの承認を使用して DKE のキー アクセス設定を設定するには**</span><span class="sxs-lookup"><span data-stu-id="c104e-246">**To set key access settings for DKE using email authorization**</span></span>

1. <span data-ttu-id="c104e-247">ファイルの **appsettings.jsを開き** 、設定を探 `AuthorizedEmailAddress` します。</span><span class="sxs-lookup"><span data-stu-id="c104e-247">Open the **appsettings.json** file and locate the `AuthorizedEmailAddress` setting.</span></span>

2. <span data-ttu-id="c104e-248">承認する電子メール アドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="c104e-248">Add the email address or addresses that you want to authorize.</span></span> <span data-ttu-id="c104e-249">複数の電子メール アドレスを二重引用符とコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="c104e-249">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="c104e-250">例:</span><span class="sxs-lookup"><span data-stu-id="c104e-250">For example:</span></span>

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. <span data-ttu-id="c104e-251">設定を `LDAPPath` 見つけて、二重引用符の `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` 間のテキストを削除します。</span><span class="sxs-lookup"><span data-stu-id="c104e-251">Locate the `LDAPPath` setting and remove the text `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` between the double quotes.</span></span> <span data-ttu-id="c104e-252">二重引用符はそのまま残します。</span><span class="sxs-lookup"><span data-stu-id="c104e-252">Leave the double quotes in place.</span></span> <span data-ttu-id="c104e-253">完了すると、設定は次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="c104e-253">When you're finished, the setting should look like this.</span></span>

   ```json
   "LDAPPath": ""
   ```

4. <span data-ttu-id="c104e-254">設定を `AuthorizedRoles` 見つけて、行全体を削除します。</span><span class="sxs-lookup"><span data-stu-id="c104e-254">Locate the `AuthorizedRoles` setting and delete the entire line.</span></span>

<span data-ttu-id="c104e-255">この画像は、電子 **メールのappsettings.js形式の** ファイルに関する情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="c104e-255">This image shows the **appsettings.json** file correctly formatted for email authorization.</span></span>

   ![電子appsettings.js方法を示すファイルの例](../media/dke-email-accesssetting.png)

<span data-ttu-id="c104e-257">**役割の承認を使用して DKE のキー アクセス設定を設定するには**</span><span class="sxs-lookup"><span data-stu-id="c104e-257">**To set key access settings for DKE using role authorization**</span></span>

1. <span data-ttu-id="c104e-258">ファイルの **appsettings.jsを開き** 、設定を探 `AuthorizedRoles` します。</span><span class="sxs-lookup"><span data-stu-id="c104e-258">Open the **appsettings.json** file and locate the `AuthorizedRoles` setting.</span></span>

2. <span data-ttu-id="c104e-259">承認する Active Directory グループ名を追加します。</span><span class="sxs-lookup"><span data-stu-id="c104e-259">Add the Active Directory group names you want to authorize.</span></span> <span data-ttu-id="c104e-260">複数のグループ名を二重引用符とコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="c104e-260">Separate multiple group names with double quotes and commas.</span></span> <span data-ttu-id="c104e-261">例:</span><span class="sxs-lookup"><span data-stu-id="c104e-261">For example:</span></span>

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. <span data-ttu-id="c104e-262">設定を `LDAPPath` 見つけて、Active Directory ドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="c104e-262">Locate the `LDAPPath` setting and add the Active Directory domain.</span></span> <span data-ttu-id="c104e-263">例:</span><span class="sxs-lookup"><span data-stu-id="c104e-263">For example:</span></span>

   ```json
   "LDAPPath": "contoso.com"
   ```

4. <span data-ttu-id="c104e-264">設定を `AuthorizedEmailAddress` 見つけて、行全体を削除します。</span><span class="sxs-lookup"><span data-stu-id="c104e-264">Locate the `AuthorizedEmailAddress` setting and delete the entire line.</span></span>

<span data-ttu-id="c104e-265">この画像は、ロールの **承認appsettings.js形式の** ファイルに関する情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="c104e-265">This image shows the **appsettings.json** file correctly formatted for role authorization.</span></span>

   ![appsettings.jsの承認方法を示すファイルの作成](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="c104e-267">テナントとキーの設定</span><span class="sxs-lookup"><span data-stu-id="c104e-267">Tenant and key settings</span></span>

<span data-ttu-id="c104e-268">DKE テナントとキーの設定は、appsettings.js **に保存** されます。</span><span class="sxs-lookup"><span data-stu-id="c104e-268">DKE tenant and key settings are located in the **appsettings.json** file.</span></span>

<span data-ttu-id="c104e-269">**DKE のテナントとキーの設定を構成するには**</span><span class="sxs-lookup"><span data-stu-id="c104e-269">**To configure tenant and key settings for DKE**</span></span>

1. <span data-ttu-id="c104e-270">ファイルの **appsettings.jsを開** きます。</span><span class="sxs-lookup"><span data-stu-id="c104e-270">Open the **appsettings.json** file.</span></span>

2. <span data-ttu-id="c104e-271">設定を `ValidIssuers` 見つけて、テナント `<tenantid>` ID に置き換える。</span><span class="sxs-lookup"><span data-stu-id="c104e-271">Locate the `ValidIssuers` setting and replace `<tenantid>` with your tenant ID.</span></span> <span data-ttu-id="c104e-272">テナント ID を見つけるには、Azure ポータルにアクセスしてテナントのプロパティを [表示します](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。</span><span class="sxs-lookup"><span data-stu-id="c104e-272">You can locate your tenant ID by going to the Azure portal and viewing the [tenant properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="c104e-273">例:</span><span class="sxs-lookup"><span data-stu-id="c104e-273">For example:</span></span>

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

<span data-ttu-id="c104e-274">を探します `JwtAudience` 。</span><span class="sxs-lookup"><span data-stu-id="c104e-274">Locate the `JwtAudience`.</span></span> <span data-ttu-id="c104e-275">`<yourhostname>`DKE サービスを実行するコンピューターのホスト名に置き換える。</span><span class="sxs-lookup"><span data-stu-id="c104e-275">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span> <span data-ttu-id="c104e-276">例:</span><span class="sxs-lookup"><span data-stu-id="c104e-276">For example:</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="c104e-277">値は、 `JwtAudience` ホストの名前と正確に一致 *する必要があります*。</span><span class="sxs-lookup"><span data-stu-id="c104e-277">The value for `JwtAudience` must match the name of your host *exactly*.</span></span> <span data-ttu-id="c104e-278">デバッグ中は **localhost:5001** を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c104e-278">You may use **localhost:5001** while debugging.</span></span> <span data-ttu-id="c104e-279">ただし、デバッグが完了したら、この値をサーバーのホスト名に更新してください。</span><span class="sxs-lookup"><span data-stu-id="c104e-279">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="c104e-280">`TestKeys:Name`.</span><span class="sxs-lookup"><span data-stu-id="c104e-280">`TestKeys:Name`.</span></span> <span data-ttu-id="c104e-281">キーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c104e-281">Enter a name for your key.</span></span> <span data-ttu-id="c104e-282">例: `TestKey1`</span><span class="sxs-lookup"><span data-stu-id="c104e-282">For example: `TestKey1`</span></span>
- <span data-ttu-id="c104e-283">`TestKeys:Id`.</span><span class="sxs-lookup"><span data-stu-id="c104e-283">`TestKeys:Id`.</span></span> <span data-ttu-id="c104e-284">GUID を作成し、値として入力 `TestKeys:ID` します。</span><span class="sxs-lookup"><span data-stu-id="c104e-284">Create a GUID and enter it as the `TestKeys:ID` value.</span></span> <span data-ttu-id="c104e-285">たとえば、`DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE` などです。</span><span class="sxs-lookup"><span data-stu-id="c104e-285">For example, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span></span> <span data-ttu-id="c104e-286">オンライン GUID ジェネレーターのようなサイト [を使用して、GUID](https://guidgenerator.com/) をランダムに生成できます。</span><span class="sxs-lookup"><span data-stu-id="c104e-286">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

<span data-ttu-id="c104e-287">この画像は、テナントとキーの設定の正しい形式を示appsettings.js **オンです**。</span><span class="sxs-lookup"><span data-stu-id="c104e-287">This image shows the correct format for tenant and keys settings in **appsettings.json**.</span></span> <span data-ttu-id="c104e-288">`LDAPPath` は、役割の承認用に構成されます。</span><span class="sxs-lookup"><span data-stu-id="c104e-288">`LDAPPath` is configured for role authorization.</span></span>

![ファイルのコピーに、DKE の正しいテナントとappsettings.js設定を表示します。](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a><span data-ttu-id="c104e-290">テスト キーを生成する</span><span class="sxs-lookup"><span data-stu-id="c104e-290">Generate test keys</span></span>

<span data-ttu-id="c104e-291">アプリケーション設定を定義したら、公開キーとプライベート テスト キーを生成する準備が整います。</span><span class="sxs-lookup"><span data-stu-id="c104e-291">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="c104e-292">キーを生成するには:</span><span class="sxs-lookup"><span data-stu-id="c104e-292">To generate keys:</span></span>

1. <span data-ttu-id="c104e-293">Windows の [スタート] メニューから、OpenSSL コマンド プロンプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="c104e-293">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

2. <span data-ttu-id="c104e-294">テスト キーを保存するフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="c104e-294">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="c104e-295">このタスクの手順を完了して作成するファイルは、同じフォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="c104e-295">The files you create by completing the steps in this task are stored in the same folder.</span></span>

3. <span data-ttu-id="c104e-296">新しいテスト キーを生成します。</span><span class="sxs-lookup"><span data-stu-id="c104e-296">Generate the new test key.</span></span>

   ```dos
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

4. <span data-ttu-id="c104e-297">プライベート キーを生成します。</span><span class="sxs-lookup"><span data-stu-id="c104e-297">Generate the private key.</span></span>

   ```dos
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

5. <span data-ttu-id="c104e-298">公開キーを生成します。</span><span class="sxs-lookup"><span data-stu-id="c104e-298">Generate the public key.</span></span>

   ```dos
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

6. <span data-ttu-id="c104e-299">テキスト エディターで **、pubkeyonly.pem を開きます**。</span><span class="sxs-lookup"><span data-stu-id="c104e-299">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="c104e-300">**pubkeyonly.pem** ファイルのすべてのコンテンツ (最初の行と最後の行を除く) を、ファイルのappsettings.js`PublicPem` **セクションにコピー** します。</span><span class="sxs-lookup"><span data-stu-id="c104e-300">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the `PublicPem` section of the **appsettings.json** file.</span></span>

7. <span data-ttu-id="c104e-301">テキスト エディターで **、prikeynopass.pem を開きます**。</span><span class="sxs-lookup"><span data-stu-id="c104e-301">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="c104e-302">最初の行と最後の行を除く **、appsettings.js** `PrivatePem` on ファイル内のすべてのコンテンツ **をコピー** します。</span><span class="sxs-lookup"><span data-stu-id="c104e-302">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the `PrivatePem` section of the **appsettings.json** file.</span></span>

8. <span data-ttu-id="c104e-303">セクションとセクションの両方のすべての空白と改行 `PublicPem` を `PrivatePem` 削除します。</span><span class="sxs-lookup"><span data-stu-id="c104e-303">Remove all blank spaces and newlines in both the `PublicPem` and `PrivatePem` sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c104e-304">このコンテンツをコピーする場合、PEM データは削除してください。</span><span class="sxs-lookup"><span data-stu-id="c104e-304">When you copy this content, do not delete any of the PEM data.</span></span>

9. <span data-ttu-id="c104e-305">[Visual Studioコード] で、次のファイル **Startup.cs** します。</span><span class="sxs-lookup"><span data-stu-id="c104e-305">In Visual Studio Code, browse to the **Startup.cs** file.</span></span> <span data-ttu-id="c104e-306">このファイルは、ローカルで DoubleKeyEncryptionService\src\customer-key-store\ の下に複製した DoubleKeyEncryptionService リポジトリにあります。</span><span class="sxs-lookup"><span data-stu-id="c104e-306">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store\.</span></span>

10. <span data-ttu-id="c104e-307">次の行を探します。</span><span class="sxs-lookup"><span data-stu-id="c104e-307">Locate the following lines:</span></span>

   ```c#
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
   ```

11. <span data-ttu-id="c104e-308">これらの行を次のテキストに置き換える。</span><span class="sxs-lookup"><span data-stu-id="c104e-308">Replace these lines with the following text:</span></span>

   ```csharp
   services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
   ```

   <span data-ttu-id="c104e-309">最後の結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c104e-309">The end results should look similar to the following.</span></span>

   ![startup.csプレビュー用のファイルを作成する](../media/dke-startupcs-usetestkeys.png)

<span data-ttu-id="c104e-311">これで [、DKE プロジェクトをビルドする準備ができました](#build-the-project)。</span><span class="sxs-lookup"><span data-stu-id="c104e-311">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="c104e-312">プロジェクトをビルドする</span><span class="sxs-lookup"><span data-stu-id="c104e-312">Build the project</span></span>

<span data-ttu-id="c104e-313">DKE プロジェクトをローカルにビルドするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="c104e-313">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="c104e-314">[Visual Studioコード] の DKE サービス リポジトリで、[コマンド パレットの表示] を選択し、プロンプトで \> **「ビルド**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="c104e-314">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

2. <span data-ttu-id="c104e-315">一覧から、[タスク: ビルド タスク **の実行] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c104e-315">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="c104e-316">ビルド タスクが見つからない場合は、[ビルド タスクの構成] を選択し、次のように .NET コア用に作成します。</span><span class="sxs-lookup"><span data-stu-id="c104e-316">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   ![.NET の不足しているビルド タスクを構成する](../media/dke-configurebuildtask.png)

   1. <span data-ttu-id="c104e-318">Choose **Create tasks.json from template**.</span><span class="sxs-lookup"><span data-stu-id="c104e-318">Choose **Create tasks.json from template**.</span></span>

      ![DKE tasks.jsテンプレートからファイル上にデータを作成する](../media/dke-createtasksjsonfromtemplate.png)

   2. <span data-ttu-id="c104e-320">テンプレートの種類の一覧から **、[.NET Core] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c104e-320">From the list of template types, select **.NET Core**.</span></span>

      ![DKE 用の適切なテンプレートを選択する](../media/dke-tasksjsontemplate.png)

   3. <span data-ttu-id="c104e-322">ビルド セクションで **、customerkeystore.csproj ファイルへのパスを見** つけます。</span><span class="sxs-lookup"><span data-stu-id="c104e-322">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="c104e-323">表示されない場合は、次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="c104e-323">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

   4. <span data-ttu-id="c104e-324">ビルドを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="c104e-324">Run the build again.</span></span>

3. <span data-ttu-id="c104e-325">出力ウィンドウに赤いエラーが表示されません。</span><span class="sxs-lookup"><span data-stu-id="c104e-325">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="c104e-326">赤いエラーがある場合は、コンソールの出力を確認します。</span><span class="sxs-lookup"><span data-stu-id="c104e-326">If there are red errors, check the console output.</span></span> <span data-ttu-id="c104e-327">前のすべての手順が正しく完了し、正しいビルド バージョンが存在していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c104e-327">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

4. <span data-ttu-id="c104e-328">[ **デバッグの** \> **開始] を選択して** 、プロセスをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="c104e-328">Select **Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="c104e-329">環境を選択するように求めるメッセージが表示されたら **、.NET core を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c104e-329">If you're prompted to select an environment, select **.NET core**.</span></span>

<span data-ttu-id="c104e-330">.NET コア デバッガーは、通常起動します `https://localhost:5001` 。</span><span class="sxs-lookup"><span data-stu-id="c104e-330">The .NET core debugger typically launches to `https://localhost:5001`.</span></span> <span data-ttu-id="c104e-331">テスト キーを表示するには、スラッシュ (/) とキーの名前に `https://localhost:5001` 移動して追加します。</span><span class="sxs-lookup"><span data-stu-id="c104e-331">To view your test key, go to `https://localhost:5001` and append a forward slash (/) and the name of your key.</span></span> <span data-ttu-id="c104e-332">例:</span><span class="sxs-lookup"><span data-stu-id="c104e-332">For example:</span></span>

```https
https://localhost:5001/TestKey1
```

<span data-ttu-id="c104e-333">キーは JSON 形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="c104e-333">The key should display in JSON format.</span></span>

<span data-ttu-id="c104e-334">これでセットアップが完了しました。</span><span class="sxs-lookup"><span data-stu-id="c104e-334">Your setup is now complete.</span></span> <span data-ttu-id="c104e-335">jwtAudience 設定の appsettings.jsを公開する前に、ホスト名の値が App Service ホスト名と正確に一致するようにします。</span><span class="sxs-lookup"><span data-stu-id="c104e-335">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="c104e-336">ビルドのトラブルシューティングを行う際に localhost に変更した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c104e-336">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="deploy-the-dke-service-and-publish-the-key-store"></a><span data-ttu-id="c104e-337">DKE サービスを展開し、キー ストアを発行する</span><span class="sxs-lookup"><span data-stu-id="c104e-337">Deploy the DKE service and publish the key store</span></span>

<span data-ttu-id="c104e-338">実稼働展開の場合は、サード パーティ製のクラウドにサービスを展開するか、オンプレミス システム [に発行します](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&preserve-view=true&tabs=netcore-cli)。</span><span class="sxs-lookup"><span data-stu-id="c104e-338">For production deployments, deploy the service either in a third-party cloud or [publish to an on-premises system](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&preserve-view=true&tabs=netcore-cli).</span></span>

<span data-ttu-id="c104e-339">他の方法でキーを展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="c104e-339">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="c104e-340">組織に最適な方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="c104e-340">Select the method that works best for your organization.</span></span>

<span data-ttu-id="c104e-341">パイロット展開の場合は、Azure に展開して、今すぐ開始できます。</span><span class="sxs-lookup"><span data-stu-id="c104e-341">For pilot deployments, you can deploy in Azure and get started right away.</span></span>

<span data-ttu-id="c104e-342">**DKE 展開をホストする Azure Web App インスタンスを作成するには**</span><span class="sxs-lookup"><span data-stu-id="c104e-342">**To create an Azure Web App instance to host your DKE deployment**</span></span>

<span data-ttu-id="c104e-343">キー ストアを公開するには、DKE 展開をホストする Azure App Service インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="c104e-343">To publish the key store, you'll create an Azure App Service instance to host your DKE deployment.</span></span> <span data-ttu-id="c104e-344">次に、生成されたキーを Azure に公開します。</span><span class="sxs-lookup"><span data-stu-id="c104e-344">Next, you'll publish your generated keys to Azure.</span></span>

1. <span data-ttu-id="c104e-345">ブラウザーで Microsoft Azure ポータルにサインインし、[[アプリ](https://ms.portal.azure.com)サービスの追加]**に移動**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="c104e-345">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

2. <span data-ttu-id="c104e-346">サブスクリプションとリソース グループを選択し、インスタンスの詳細を定義します。</span><span class="sxs-lookup"><span data-stu-id="c104e-346">Select your subscription and resource group and define your instance details.</span></span>

    - <span data-ttu-id="c104e-347">DKE サービスをインストールするコンピューターのホスト名を入力します。</span><span class="sxs-lookup"><span data-stu-id="c104e-347">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="c104e-348">ファイルに対するファイルの JwtAudience 設定に定義されている名前と同appsettings.js [**してください**](#tenant-and-key-settings) 。</span><span class="sxs-lookup"><span data-stu-id="c104e-348">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="c104e-349">名前に指定する値も WebAppInstanceName です。</span><span class="sxs-lookup"><span data-stu-id="c104e-349">The value you provide for the name is also the WebAppInstanceName.</span></span>

    - <span data-ttu-id="c104e-350">[**発行]** でコード **を選択し**、ランタイム スタックの場合は **、[.NET Core 3.1] を選択します**。 </span><span class="sxs-lookup"><span data-stu-id="c104e-350">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

    <span data-ttu-id="c104e-351">例:</span><span class="sxs-lookup"><span data-stu-id="c104e-351">For example:</span></span>

   ![App Service を追加する](../media/dke-azure-add-app-service.png)

3. <span data-ttu-id="c104e-353">At the bottom of the page, select **Review + create,** and then select **Add**.</span><span class="sxs-lookup"><span data-stu-id="c104e-353">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

4. <span data-ttu-id="c104e-354">生成されたキーを発行するには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="c104e-354">Do one of the following to publish your generated keys:</span></span>

    - [<span data-ttu-id="c104e-355">ZipDeployUI を使用して発行する</span><span class="sxs-lookup"><span data-stu-id="c104e-355">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
    - [<span data-ttu-id="c104e-356">FTP 経由で発行する</span><span class="sxs-lookup"><span data-stu-id="c104e-356">Publish via FTP</span></span>](#publish-via-ftp)
    - [<span data-ttu-id="c104e-357">Visual Studio 2019 以降で発行する</span><span class="sxs-lookup"><span data-stu-id="c104e-357">Publish via Visual Studio 2019 or later</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/)

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="c104e-358">ZipDeployUI を使用して発行する</span><span class="sxs-lookup"><span data-stu-id="c104e-358">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="c104e-359">`https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI` に移動します。</span><span class="sxs-lookup"><span data-stu-id="c104e-359">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

    <span data-ttu-id="c104e-360">例: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="c104e-360">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

2. <span data-ttu-id="c104e-361">キー ストアのコードベースで **、customer-key-store\src\customer-key-store** フォルダーに移動し、このフォルダーに **customerkeystore.csproj** ファイルが含まれているか確認します。</span><span class="sxs-lookup"><span data-stu-id="c104e-361">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

3. <span data-ttu-id="c104e-362">実行: **dotnet 発行**</span><span class="sxs-lookup"><span data-stu-id="c104e-362">Run: **dotnet publish**</span></span>

     <span data-ttu-id="c104e-363">出力ウィンドウには、発行が展開されたディレクトリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c104e-363">The output window displays the directory where the publish was deployed.</span></span>

    <span data-ttu-id="c104e-364">例: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="c104e-364">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

4. <span data-ttu-id="c104e-365">発行ディレクトリ内のすべてのファイルを .zip ファイルに送信します。</span><span class="sxs-lookup"><span data-stu-id="c104e-365">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="c104e-366">.zip ファイルを作成する場合は、ディレクトリ内のすべてのファイルが .zip ファイルのルート レベルに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c104e-366">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

5. <span data-ttu-id="c104e-367">作成した .zip ファイルを、上で開いた ZipDeployUI サイトにドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="c104e-367">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="c104e-368">例: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="c104e-368">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="c104e-369">DKE が展開され、作成したテスト キーを参照できます。</span><span class="sxs-lookup"><span data-stu-id="c104e-369">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="c104e-370">以下の「 [展開の検証」に進](#validate-your-deployment) んでください。</span><span class="sxs-lookup"><span data-stu-id="c104e-370">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="c104e-371">FTP 経由で発行する</span><span class="sxs-lookup"><span data-stu-id="c104e-371">Publish via FTP</span></span>

1. <span data-ttu-id="c104e-372">上で作成したアプリ サービスに接続 [します](#deploy-the-dke-service-and-publish-the-key-store)。</span><span class="sxs-lookup"><span data-stu-id="c104e-372">Connect to the App Service you created [above](#deploy-the-dke-service-and-publish-the-key-store).</span></span>

    <span data-ttu-id="c104e-373">ブラウザーで **、「Azure portal**  >  **App Service** Deployment Center Manual  >  **Deployment**  >    >  **FTP**  >  **Dashboard」** に移動します。</span><span class="sxs-lookup"><span data-stu-id="c104e-373">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

2. <span data-ttu-id="c104e-374">表示された接続文字列をローカル ファイルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="c104e-374">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="c104e-375">これらの文字列を使用して Web App Service に接続し、FTP 経由でファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="c104e-375">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

    <span data-ttu-id="c104e-376">例:</span><span class="sxs-lookup"><span data-stu-id="c104e-376">For example:</span></span>

   ![FTP ダッシュボードから接続文字列をコピーする](../media/dke-ftp-dashboard.png)

3. <span data-ttu-id="c104e-378">キー ストレージのコードベースで **、customer-key-store\src\customer-key-store ディレクトリに移動します**。</span><span class="sxs-lookup"><span data-stu-id="c104e-378">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

4. <span data-ttu-id="c104e-379">このディレクトリに **customerkeystore.csproj ファイルが含まれているか確認** します。</span><span class="sxs-lookup"><span data-stu-id="c104e-379">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

5. <span data-ttu-id="c104e-380">実行: **dotnet 発行**</span><span class="sxs-lookup"><span data-stu-id="c104e-380">Run: **dotnet publish**</span></span>

    <span data-ttu-id="c104e-381">出力には、発行が展開されたディレクトリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c104e-381">The output contains the directory where the publish was deployed.</span></span>

    <span data-ttu-id="c104e-382">例: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="c104e-382">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

6. <span data-ttu-id="c104e-383">発行ディレクトリ内のすべてのファイルを zip ファイルに送信します。</span><span class="sxs-lookup"><span data-stu-id="c104e-383">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="c104e-384">.zip ファイルを作成する場合は、ディレクトリ内のすべてのファイルが .zip ファイルのルート レベルに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c104e-384">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

7. <span data-ttu-id="c104e-385">FTP クライアントから、コピーした接続情報を使用して App Service に接続します。</span><span class="sxs-lookup"><span data-stu-id="c104e-385">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="c104e-386">前の手順で作成した .zip ファイルを Web App のルート ディレクトリにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="c104e-386">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="c104e-387">DKE が展開され、作成したテスト キーを参照できます。</span><span class="sxs-lookup"><span data-stu-id="c104e-387">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="c104e-388">次に、 [展開を検証します](#validate-your-deployment)。</span><span class="sxs-lookup"><span data-stu-id="c104e-388">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="c104e-389">展開を検証する</span><span class="sxs-lookup"><span data-stu-id="c104e-389">Validate your deployment</span></span>

<span data-ttu-id="c104e-390">上記のいずれかの方法を使用して DKE を展開した後、展開とキー ストアの設定を検証します。</span><span class="sxs-lookup"><span data-stu-id="c104e-390">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="c104e-391">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c104e-391">Run:</span></span>

<span data-ttu-id="c104e-392">src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey</span><span class="sxs-lookup"><span data-stu-id="c104e-392">src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey</span></span>

<span data-ttu-id="c104e-393">例:</span><span class="sxs-lookup"><span data-stu-id="c104e-393">For example:</span></span>

<span data-ttu-id="c104e-394">key_store_tester.ps1 https://mydkeservice.com/mykey</span><span class="sxs-lookup"><span data-stu-id="c104e-394">key_store_tester.ps1 https://mydkeservice.com/mykey</span></span>

<span data-ttu-id="c104e-395">出力にエラーが表示されないか確認します。</span><span class="sxs-lookup"><span data-stu-id="c104e-395">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="c104e-396">準備ができたら、キー [ストアを登録します](#register-your-key-store)。</span><span class="sxs-lookup"><span data-stu-id="c104e-396">When you're ready, [register your key store](#register-your-key-store).</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="c104e-397">キー ストアを登録する</span><span class="sxs-lookup"><span data-stu-id="c104e-397">Register your key store</span></span>

<span data-ttu-id="c104e-398">次の手順を実行すると、DKE サービスを登録できます。</span><span class="sxs-lookup"><span data-stu-id="c104e-398">The following steps enable you to register your DKE service.</span></span> <span data-ttu-id="c104e-399">DKE サービスの登録は、ラベルの作成を開始する前に DKE を展開する最後の手順です。</span><span class="sxs-lookup"><span data-stu-id="c104e-399">Registering your DKE service is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="c104e-400">DKE サービスを登録するには:</span><span class="sxs-lookup"><span data-stu-id="c104e-400">To register the DKE service:</span></span>

1. <span data-ttu-id="c104e-401">ブラウザーで [、Microsoft Azure ポータルを開](https://ms.portal.azure.com/)き、[すべての **サービス** ID アプリの登録] \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="c104e-401">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="c104e-402">[ **新規登録] を** 選択し、わかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c104e-402">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="c104e-403">表示されるオプションからアカウントの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="c104e-403">Select an account type from the options displayed.</span></span>

    <span data-ttu-id="c104e-404">**onmicrosoft.com** などの非カスタム ドメインで Microsoft Azure を使用している場合は、この組織のディレクトリでのみ [アカウント] を選択します **(Microsoft のみ - シングル テナント)。**</span><span class="sxs-lookup"><span data-stu-id="c104e-404">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

    <span data-ttu-id="c104e-405">例:</span><span class="sxs-lookup"><span data-stu-id="c104e-405">For example:</span></span>

   ![新しいアプリの登録](../media/dke-app-registration.png)

4. <span data-ttu-id="c104e-407">ページの下部にある [登録] **を選択して** 、新しいアプリ登録を作成します。</span><span class="sxs-lookup"><span data-stu-id="c104e-407">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="c104e-408">新しいアプリの登録の左側のウィンドウで、[管理] の [ **認証]** を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c104e-408">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="c104e-409">[プラットフォーム **の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c104e-409">Select **Add a platform**.</span></span>

7. <span data-ttu-id="c104e-410">[プラットフォーム **の構成] ポップアップで\*\*\*\*、[Web] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c104e-410">On the **Configure platforms** popup, select **Web**.</span></span>

8. <span data-ttu-id="c104e-411">[ **リダイレクト URI] で**、二重キー暗号化サービスの URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="c104e-411">Under **Redirect URIs**, enter the URI of your double key encryption service.</span></span> <span data-ttu-id="c104e-412">ホスト名とドメインの両方を含む App Service URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="c104e-412">Enter the App Service URL, including both the hostname and domain.</span></span>

    <span data-ttu-id="c104e-413">例: https://mydkeservicetest.com</span><span class="sxs-lookup"><span data-stu-id="c104e-413">For example: https://mydkeservicetest.com</span></span>

    - <span data-ttu-id="c104e-414">入力する URL は、DKE サービスが展開されているホスト名と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c104e-414">The URL you enter must match the hostname where your DKE service is deployed.</span></span>
    - <span data-ttu-id="c104e-415">If you're testing locally with Visual Studio, use **https://localhost:5001** .</span><span class="sxs-lookup"><span data-stu-id="c104e-415">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
    - <span data-ttu-id="c104e-416">すべての場合、スキームは https である **必要があります**。</span><span class="sxs-lookup"><span data-stu-id="c104e-416">In all cases, the scheme must be **https**.</span></span>

    <span data-ttu-id="c104e-417">ホスト名が App Service のホスト名と正確に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c104e-417">Ensure the hostname exactly matches your App Service hostname.</span></span> <span data-ttu-id="c104e-418">ビルドのトラブルシューティングに変更 `localhost` した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c104e-418">You may have changed it to `localhost` to troubleshoot the build.</span></span> <span data-ttu-id="c104e-419">In **appsettings.json,** this value is the hostname you set for `JwtAudience` .</span><span class="sxs-lookup"><span data-stu-id="c104e-419">In **appsettings.json**, this value is the hostname you set for `JwtAudience`.</span></span>

9. <span data-ttu-id="c104e-420">[**暗黙的な許可] で\*\*\*\*、[ID トークン] チェック ボックスをオン** にします。</span><span class="sxs-lookup"><span data-stu-id="c104e-420">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

10. <span data-ttu-id="c104e-421">**[保存]** を選択し、変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="c104e-421">Select **Save** to save your changes.</span></span>

11. <span data-ttu-id="c104e-422">左側のウィンドウで、[API の公開] **を選択** し、[アプリケーション ID URI] の横にある [設定] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="c104e-422">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

12. <span data-ttu-id="c104e-423">引き続き **[API の公開** ] ページで、この **API** 領域で定義されているスコープで、[スコープの追加 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c104e-423">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="c104e-424">新しいスコープで、次の条件を実行します。</span><span class="sxs-lookup"><span data-stu-id="c104e-424">In the new scope:</span></span>

    1. <span data-ttu-id="c104e-425">スコープ名を次のように定義 **user_impersonation。**</span><span class="sxs-lookup"><span data-stu-id="c104e-425">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="c104e-426">同意できる管理者とユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c104e-426">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="c104e-427">必要な残りの値を定義します。</span><span class="sxs-lookup"><span data-stu-id="c104e-427">Define any remaining values required.</span></span>

    4. <span data-ttu-id="c104e-428">**[スコープの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c104e-428">Select **Add scope**.</span></span>

    5. <span data-ttu-id="c104e-429">上部 **の [** 保存] を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="c104e-429">Select **Save** at the top to save your changes.</span></span>

13. <span data-ttu-id="c104e-430">引き続き **[API の** 公開] ページの [承認された **クライアント** アプリケーション] 領域で、[クライアント アプリケーションの追加 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c104e-430">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="c104e-431">新しいクライアント アプリケーションで、次の条件を実行します。</span><span class="sxs-lookup"><span data-stu-id="c104e-431">In the new client application:</span></span>

    1. <span data-ttu-id="c104e-432">クライアント ID を **d3590ed6-52b3-4102-aeff-aad2292ab01c** として定義します。</span><span class="sxs-lookup"><span data-stu-id="c104e-432">Define the Client ID as **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span></span> <span data-ttu-id="c104e-433">この値はクライアント ID Microsoft Officeであり、キー ストアOfficeトークンを取得できます。</span><span class="sxs-lookup"><span data-stu-id="c104e-433">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="c104e-434">[ **承認済みスコープ] で、** 次 **のuser_impersonationします** 。</span><span class="sxs-lookup"><span data-stu-id="c104e-434">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="c104e-435">**[アプリケーションの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c104e-435">Select **Add application**.</span></span>

    4. <span data-ttu-id="c104e-436">上部 **の [** 保存] を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="c104e-436">Select **Save** at the top to save your changes.</span></span>

<span data-ttu-id="c104e-437">これで、DKE サービスが登録されました。</span><span class="sxs-lookup"><span data-stu-id="c104e-437">Your DKE service is now registered.</span></span> <span data-ttu-id="c104e-438">[DKE を使用してラベルを作成します](#create-sensitivity-labels-using-dke)。</span><span class="sxs-lookup"><span data-stu-id="c104e-438">Continue by [creating labels using DKE](#create-sensitivity-labels-using-dke).</span></span>

## <a name="create-sensitivity-labels-using-dke"></a><span data-ttu-id="c104e-439">DKE を使用して感度ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="c104e-439">Create sensitivity labels using DKE</span></span>

<span data-ttu-id="c104e-440">Microsoft 365 コンプライアンス センターで、新しい区別ラベルを作成し、それ以外の場合と同様に暗号化を適用します。</span><span class="sxs-lookup"><span data-stu-id="c104e-440">In the Microsoft 365 compliance center, create a new sensitivity label and apply encryption as you would otherwise.</span></span> <span data-ttu-id="c104e-441">[Use **Double Key Encryption] を選択** し、キーのエンドポイント URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="c104e-441">Select **Use Double Key Encryption** and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="c104e-442">例:</span><span class="sxs-lookup"><span data-stu-id="c104e-442">For example:</span></span>

![Microsoft 365 コンプライアンス センターで [二重キー暗号化を使用する] を選択する](../media/dke-use-dke.png)

<span data-ttu-id="c104e-444">追加した DKE ラベルは、Microsoft 365 Apps for enterprise の最新バージョンのユーザーに対して表示されます。</span><span class="sxs-lookup"><span data-stu-id="c104e-444">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="c104e-445">クライアントが新しいラベルで更新するには、最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c104e-445">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="c104e-446">クライアントで DKE を有効にする</span><span class="sxs-lookup"><span data-stu-id="c104e-446">Enable DKE in your client</span></span>

<span data-ttu-id="c104e-447">Insider を使用している場合Office DKE が有効になります。</span><span class="sxs-lookup"><span data-stu-id="c104e-447">If you're an Office Insider, DKE is enabled for you.</span></span> <span data-ttu-id="c104e-448">それ以外の場合は、次のレジストリ キーを追加して、クライアントの DKE を有効にします。</span><span class="sxs-lookup"><span data-stu-id="c104e-448">Otherwise, enable DKE for your client by adding the following registry keys:</span></span>

```properties
    [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001
```

## <a name="migrate-protected-files-from-hyok-labels-to-dke-labels"></a><span data-ttu-id="c104e-449">保護されたファイルを HYOK ラベルから DKE ラベルに移行する</span><span class="sxs-lookup"><span data-stu-id="c104e-449">Migrate protected files from HYOK labels to DKE labels</span></span>

<span data-ttu-id="c104e-450">必要な場合は、DKE の設定が完了したら、HYOK ラベルを使用して保護したコンテンツを DKE ラベルに移行できます。</span><span class="sxs-lookup"><span data-stu-id="c104e-450">If you want, once you're finished setting up DKE, you can migrate content that you've protected using HYOK labels to DKE labels.</span></span> <span data-ttu-id="c104e-451">移行するには、AIP スキャナーを使用します。</span><span class="sxs-lookup"><span data-stu-id="c104e-451">To migrate, you'll use the AIP scanner.</span></span> <span data-ttu-id="c104e-452">スキャナーの使用を開始するには [、「Azure Information Protection](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)統合ラベル付けスキャナーとは」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c104e-452">To get started using the scanner, see [What is the Azure Information Protection unified labeling scanner?](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner).</span></span>

<span data-ttu-id="c104e-453">コンテンツを移行しない場合、HYOK で保護されたコンテンツは影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="c104e-453">If you don't migrate content, your HYOK protected content will remain unaffected.</span></span>
