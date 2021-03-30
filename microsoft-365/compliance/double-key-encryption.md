---
title: 二重キー暗号化 (DKE)
description: DKE を使用すると、キーを完全に制御しながら、機密性の高いデータを保護できます。
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
ms.openlocfilehash: 746f1345b47694f4a4122edc5d89cc924441ea81
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408178"
---
# <a name="double-key-encryption-for-microsoft-365"></a><span data-ttu-id="bd404-103">Microsoft 365 のダブル キー暗号化</span><span class="sxs-lookup"><span data-stu-id="bd404-103">Double Key Encryption for Microsoft 365</span></span>

> <span data-ttu-id="bd404-104">*適用対象: Microsoft 365 のダブル キー暗号化 [、Microsoft 365 コンプライアンス](https://www.microsoft.com/microsoft-365/business/compliance-management)[、Azure 情報保護](https://azure.microsoft.com/pricing/details/information-protection)*</span><span class="sxs-lookup"><span data-stu-id="bd404-104">*Applies to: Double Key Encryption for Microsoft 365, [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="bd404-105">*手順: [Azure Information Protection 統合ラベル 付けクライアント for Windows](/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span><span class="sxs-lookup"><span data-stu-id="bd404-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="bd404-106">*サービスの説明: [Microsoft 365 コンプライアンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="bd404-106">*Service description for: [Microsoft 365 Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="bd404-107">ダブル キー暗号化 (DKE) では、2 つのキーを一緒に使用して保護されたコンテンツにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="bd404-107">Double Key Encryption (DKE) uses two keys together to access protected content.</span></span> <span data-ttu-id="bd404-108">Microsoft は 1 つのキーを Microsoft Azure に保存し、もう一方のキーを保持します。</span><span class="sxs-lookup"><span data-stu-id="bd404-108">Microsoft stores one key in Microsoft Azure, and you hold the other key.</span></span> <span data-ttu-id="bd404-109">ダブル キー暗号化サービスを使用して、キーの 1 つを完全に制御します。</span><span class="sxs-lookup"><span data-stu-id="bd404-109">You maintain full control of one of your keys using the Double Key Encryption service.</span></span> <span data-ttu-id="bd404-110">機密性の高いコンテンツには、Azure Information Protection 統合ラベル付けクライアントを使用して保護を適用します。</span><span class="sxs-lookup"><span data-stu-id="bd404-110">You apply protection using The Azure Information Protection unified labeling client to your highly sensitive content.</span></span>

<span data-ttu-id="bd404-111">ダブル キー暗号化は、クラウドとオンプレミスの両方の展開をサポートします。</span><span class="sxs-lookup"><span data-stu-id="bd404-111">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="bd404-112">これらの展開は、保護されたデータを保存する場所を問い合っても、暗号化されたデータが不透明な状態を維持するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bd404-112">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="bd404-113">既定のクラウドベースのテナント ルート キーの詳細については、「Azure Information Protection テナント キーの計画と [実装」を参照してください](/azure/information-protection/plan-implement-tenant-key)。</span><span class="sxs-lookup"><span data-stu-id="bd404-113">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](/azure/information-protection/plan-implement-tenant-key).</span></span>

## <a name="when-your-organization-should-adopt-dke"></a><span data-ttu-id="bd404-114">組織で DKE を採用する必要が生じ</span><span class="sxs-lookup"><span data-stu-id="bd404-114">When your organization should adopt DKE</span></span>

<span data-ttu-id="bd404-115">ダブル キー暗号化は、最も厳密な保護要件の対象となる最も機密性の高いデータを対象とします。</span><span class="sxs-lookup"><span data-stu-id="bd404-115">Double Key Encryption is intended for your most sensitive data that is subject to the strictest protection requirements.</span></span> <span data-ttu-id="bd404-116">DKE は、すべてのデータを対象としているのではありません。</span><span class="sxs-lookup"><span data-stu-id="bd404-116">DKE is not intended for all data.</span></span> <span data-ttu-id="bd404-117">一般に、Double Key Encryption を使用して、全体的なデータの一部のみを保護します。</span><span class="sxs-lookup"><span data-stu-id="bd404-117">In general, you'll be using Double Key Encryption to protect only a small part of your overall data.</span></span> <span data-ttu-id="bd404-118">展開する前に、このソリューションでカバーする適切なデータを特定するためのデューデリジェンスを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd404-118">You should do due diligence in identifying the right data to cover with this solution before you deploy.</span></span> <span data-ttu-id="bd404-119">場合によっては、Microsoft が管理するキーを使用した Microsoft Information Protection や BYOK などのほとんどのデータに対して、スコープを絞り込み、他のソリューションを利用する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="bd404-119">In some cases, you might need to narrow your scope and make use of other solutions for most your data such as Microsoft Information Protection with Microsoft-managed keys or BYOK.</span></span> <span data-ttu-id="bd404-120">これらのソリューションは、強化された保護と規制要件の対象とされないドキュメントでは十分です。</span><span class="sxs-lookup"><span data-stu-id="bd404-120">These solutions are sufficient for documents that aren't subject to enhanced protections and regulatory requirements.</span></span> <span data-ttu-id="bd404-121">また、これらのソリューションを使用すると、365 サービスで最も強力Office使用できます。DKE で暗号化されたコンテンツでは使用できないサービス。</span><span class="sxs-lookup"><span data-stu-id="bd404-121">Also, these solutions enable you to use the most powerful Office 365 services; services that you can't use with DKE encrypted content.</span></span> <span data-ttu-id="bd404-122">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bd404-122">For example:</span></span>

- <span data-ttu-id="bd404-123">添付ファイルを表示する必要があるマルウェア対策やスパムなどのトランスポート ルール</span><span class="sxs-lookup"><span data-stu-id="bd404-123">Transport rules including anti-malware and spam that require visibility into the attachment</span></span>
- <span data-ttu-id="bd404-124">Microsoft Delve</span><span class="sxs-lookup"><span data-stu-id="bd404-124">Microsoft Delve</span></span>
- <span data-ttu-id="bd404-125">電子情報開示</span><span class="sxs-lookup"><span data-stu-id="bd404-125">eDiscovery</span></span>
- <span data-ttu-id="bd404-126">コンテンツ検索とインデックス作成</span><span class="sxs-lookup"><span data-stu-id="bd404-126">Content search and indexing</span></span>
- <span data-ttu-id="bd404-127">Office機能を含む Web アプリ</span><span class="sxs-lookup"><span data-stu-id="bd404-127">Office Web Apps including coauthoring functionality</span></span>

<span data-ttu-id="bd404-128">MIP SDK を介して DKE と統合されていない外部アプリケーションまたはサービスは、暗号化されたデータに対してアクションを実行できません。</span><span class="sxs-lookup"><span data-stu-id="bd404-128">Any external applications or services that are not integrated with DKE through the MIP SDK will be unable to perform actions on the encrypted data.</span></span>

<span data-ttu-id="bd404-129">Microsoft Information Protection SDK 1.7+ では、ダブル キー暗号化がサポートされています。SDK と統合するアプリケーションは、十分なアクセス許可と統合を行って、このデータを理由付けできます。</span><span class="sxs-lookup"><span data-stu-id="bd404-129">The Microsoft Information Protection SDK 1.7+ supports Double Key Encryption; applications that integrate with our SDK will be able to reason over this data with sufficient permissions and integrations in place.</span></span>

<span data-ttu-id="bd404-130">組織では、機密データの大部分を保護するために Microsoft Information Protection 機能 (分類とラベル付け) を使用し、ミッション クリティカルなデータにのみ DKE を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bd404-130">We recommend organizations use Microsoft Information protection capabilities (classification and labeling) to protect most of their sensitive data and only use DKE for their mission-critical data.</span></span> <span data-ttu-id="bd404-131">ダブル キー暗号化は、金融サービスやヘルスケアなどの規制の厳しい業界の機密データに関連します。</span><span class="sxs-lookup"><span data-stu-id="bd404-131">Double Key Encryption is relevant for sensitive data in highly regulated industries such as Financial services and Healthcare.</span></span>

<span data-ttu-id="bd404-132">組織に次の要件がある場合は、DKE を使用してコンテンツをセキュリティで保護できます。</span><span class="sxs-lookup"><span data-stu-id="bd404-132">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="bd404-133">すべての状況下で *、保護* されたコンテンツを解読できるのは自分だけである必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd404-133">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="bd404-134">Microsoft が独自に保護されたデータにアクセスする必要はない。</span><span class="sxs-lookup"><span data-stu-id="bd404-134">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="bd404-135">地理的境界内にキーを保持する規制要件があります。</span><span class="sxs-lookup"><span data-stu-id="bd404-135">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="bd404-136">データの暗号化と暗号化解除のために保持するキーはすべて、データ センターで保持されます。</span><span class="sxs-lookup"><span data-stu-id="bd404-136">All of the keys that you hold for data encryption and decryption are maintained in your data center.</span></span>

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="bd404-137">DKE のシステム要件とライセンス要件</span><span class="sxs-lookup"><span data-stu-id="bd404-137">System and licensing requirements for DKE</span></span>

<span data-ttu-id="bd404-138">**Microsoft 365 のダブル キー暗号化には** 、Microsoft 365 E5 が付属しています。</span><span class="sxs-lookup"><span data-stu-id="bd404-138">**Double Key Encryption for Microsoft 365** comes with Microsoft 365 E5.</span></span> <span data-ttu-id="bd404-139">Microsoft 365 E5 ライセンスをお持ちでない場合は、試用版にサインアップ [できます](https://aka.ms/M365E5ComplianceTrial)。</span><span class="sxs-lookup"><span data-stu-id="bd404-139">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="bd404-140">これらのライセンスの詳細については [、「Microsoft 36 & 5](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)ライセンス ガイダンス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd404-140">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="bd404-141">**Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="bd404-141">**Azure Information Protection**.</span></span> <span data-ttu-id="bd404-142">DKE は、感度ラベルで動作し、Azure Information Protection が必要です。</span><span class="sxs-lookup"><span data-stu-id="bd404-142">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

<span data-ttu-id="bd404-143">DKE の感度ラベルは、デスクトップ アプリの感度リボンを使用してエンド Office使用できます。</span><span class="sxs-lookup"><span data-stu-id="bd404-143">DKE sensitivity labels are made available to end users through the sensitivity ribbon in Office Desktop Apps.</span></span> <span data-ttu-id="bd404-144">保護されたドキュメントを保護および使用する各クライアント コンピューターに、これらの前提条件をインストールします。</span><span class="sxs-lookup"><span data-stu-id="bd404-144">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="bd404-145">**Microsoft Office Windows** のエンタープライズ バージョン 2009 以降 (デスクトップ バージョンの Word、PowerPoint、および Excel) 用のアプリ。</span><span class="sxs-lookup"><span data-stu-id="bd404-145">**Microsoft Office Apps for enterprise** version 2009 or later (Desktop versions of Word, PowerPoint, and Excel) on Windows.</span></span>

<span data-ttu-id="bd404-146">**Azure Information Protection Unified Labeling クライアント** バージョン 2.7.93.0 以降。</span><span class="sxs-lookup"><span data-stu-id="bd404-146">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="bd404-147">Microsoft ダウンロード センターから Unified Labeling クライアントをダウンロード [してインストールします](https://www.microsoft.com/download/details.aspx?id=53018)。</span><span class="sxs-lookup"><span data-stu-id="bd404-147">Download and install the Unified Labeling client from the [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="bd404-148">DKE で保護されたコンテンツを格納および表示するためのサポートされている環境</span><span class="sxs-lookup"><span data-stu-id="bd404-148">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="bd404-149">**サポートされているアプリケーション**。</span><span class="sxs-lookup"><span data-stu-id="bd404-149">**Supported applications**.</span></span> <span data-ttu-id="bd404-150">Word、Excel、PowerPoint など、Windows 上のエンタープライズ クライアント向け Microsoft [365](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product)アプリ。</span><span class="sxs-lookup"><span data-stu-id="bd404-150">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="bd404-151">**オンライン コンテンツのサポート**。</span><span class="sxs-lookup"><span data-stu-id="bd404-151">**Online content support**.</span></span> <span data-ttu-id="bd404-152">Microsoft SharePoint と OneDrive for Business の両方で、ダブル キー暗号化で保護されたドキュメントとファイルをオンラインで保存できます。</span><span class="sxs-lookup"><span data-stu-id="bd404-152">You can store documents and files protected with Double Key Encryption online in both Microsoft SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="bd404-153">これらの場所にアップロードする前に、サポートされているアプリケーションによって DKE を使用してドキュメントとファイルにラベルを付け、保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd404-153">You must label and protect documents and files with DKE by supported applications before you upload to these locations.</span></span> <span data-ttu-id="bd404-154">暗号化されたコンテンツは電子メールで共有できますが、暗号化されたドキュメントやファイルをオンラインで表示できません。</span><span class="sxs-lookup"><span data-stu-id="bd404-154">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="bd404-155">代わりに、ローカル コンピューターでサポートされているデスクトップ アプリケーションとクライアントを使用して保護されたコンテンツを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd404-155">Instead, you must view protected content using the supported desktop applications and clients on your local computer.</span></span>

## <a name="overview-of-deploying-dke"></a><span data-ttu-id="bd404-156">DKE の展開の概要</span><span class="sxs-lookup"><span data-stu-id="bd404-156">Overview of deploying DKE</span></span>

<span data-ttu-id="bd404-157">次の一般的な手順に従って、DKE を設定します。</span><span class="sxs-lookup"><span data-stu-id="bd404-157">You'll follow these general steps to set up DKE.</span></span> <span data-ttu-id="bd404-158">これらの手順を完了すると、エンド ユーザーは、機密性の高いデータをダブル キー暗号化で保護できます。</span><span class="sxs-lookup"><span data-stu-id="bd404-158">Once you've completed these steps, your end users will can protect your highly sensitive data with Double Key Encryption.</span></span>

1. <span data-ttu-id="bd404-159">この記事の説明に従って、DKE サービスを展開します。</span><span class="sxs-lookup"><span data-stu-id="bd404-159">Deploy the DKE service as described in this article.</span></span>

2. <span data-ttu-id="bd404-160">二重キー暗号化を使用してラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="bd404-160">Create a label with Double Key Encryption.</span></span> <span data-ttu-id="bd404-161">[Microsoft 365](https://compliance.microsoft.com)コンプライアンス センターの [情報保護] に移動し、ダブル キー暗号化を使用して新しいラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="bd404-161">Navigate to Information protection under the [Microsoft 365 compliance center](https://compliance.microsoft.com) and create a new label with Double Key Encryption.</span></span> <span data-ttu-id="bd404-162">「暗号化 [を適用するために感度ラベルを使用してコンテンツへのアクセスを制限する」を参照してください](./encryption-sensitivity-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="bd404-162">See [Restrict access to content by using sensitivity labels to apply encryption](./encryption-sensitivity-labels.md).</span></span>

3. <span data-ttu-id="bd404-163">二重キー暗号化ラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="bd404-163">Use Double Key Encryption labels.</span></span> <span data-ttu-id="bd404-164">[データの暗号化] リボンで [ダブル キー暗号化] ラベルを選択して、データをMicrosoft Office。</span><span class="sxs-lookup"><span data-stu-id="bd404-164">Protect data by selecting the Double Key Encrypted label from the Sensitivity ribbon in Microsoft Office.</span></span>

<span data-ttu-id="bd404-165">二重キー暗号化を展開する手順の一部を実行するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="bd404-165">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="bd404-166">この記事では、経験の少ない管理者がサービスを正常に展開できるよう、詳細な手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="bd404-166">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="bd404-167">この方法が快適な場合は、独自のメソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bd404-167">If you're comfortable doing so, you can choose to use your own methods.</span></span>

## <a name="deploy-dke"></a><span data-ttu-id="bd404-168">DKE の展開</span><span class="sxs-lookup"><span data-stu-id="bd404-168">Deploy DKE</span></span>

<span data-ttu-id="bd404-169">この記事と展開ビデオでは、DKE サービスの展開先として Azure を使用します。</span><span class="sxs-lookup"><span data-stu-id="bd404-169">This article and the deployment video use Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="bd404-170">別の場所に展開する場合は、独自の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd404-170">If you're deploying to another location, you'll need to provide your own values.</span></span>

<span data-ttu-id="bd404-171">この記事 [の概念の](https://youtu.be/vDWfHN_kygg) 概要については、ダブル キー暗号化の展開ビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bd404-171">Watch the [Double Key Encryption deployment video](https://youtu.be/vDWfHN_kygg) to see a step-by-step overview of the concepts in this article.</span></span> <span data-ttu-id="bd404-172">ビデオの完了には約 18 分かかります。</span><span class="sxs-lookup"><span data-stu-id="bd404-172">The video takes about 18 minutes to complete.</span></span>

<span data-ttu-id="bd404-173">次の一般的な手順に従って、組織のダブル キー暗号化を設定します。</span><span class="sxs-lookup"><span data-stu-id="bd404-173">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span>

1. [<span data-ttu-id="bd404-174">DKE サービスのソフトウェア前提条件のインストール</span><span class="sxs-lookup"><span data-stu-id="bd404-174">Install software prerequisites for the DKE service</span></span>](#install-software-prerequisites-for-the-dke-service)
1. [<span data-ttu-id="bd404-175">ダブル キー暗号化 GitHub リポジトリの複製</span><span class="sxs-lookup"><span data-stu-id="bd404-175">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="bd404-176">アプリケーション設定の変更</span><span class="sxs-lookup"><span data-stu-id="bd404-176">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="bd404-177">テスト キーの生成</span><span class="sxs-lookup"><span data-stu-id="bd404-177">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="bd404-178">プロジェクトをビルドする</span><span class="sxs-lookup"><span data-stu-id="bd404-178">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="bd404-179">DKE サービスを展開し、キー ストアを発行する</span><span class="sxs-lookup"><span data-stu-id="bd404-179">Deploy the DKE service and publish the key store</span></span>](#deploy-the-dke-service-and-publish-the-key-store)
1. [<span data-ttu-id="bd404-180">展開を検証する</span><span class="sxs-lookup"><span data-stu-id="bd404-180">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="bd404-181">キー ストアを登録する</span><span class="sxs-lookup"><span data-stu-id="bd404-181">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="bd404-182">DKE を使用して感度ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="bd404-182">Create sensitivity labels using DKE</span></span>](#create-sensitivity-labels-using-dke)
1. [<span data-ttu-id="bd404-183">クライアントで DKE を有効にする</span><span class="sxs-lookup"><span data-stu-id="bd404-183">Enable DKE in your client</span></span>](#enable-dke-in-your-client)
1. [<span data-ttu-id="bd404-184">保護されたファイルを HYOK ラベルから DKE ラベルに移行する</span><span class="sxs-lookup"><span data-stu-id="bd404-184">Migrate protected files from HYOK labels to DKE labels</span></span>](#migrate-protected-files-from-hyok-labels-to-dke-labels)

<span data-ttu-id="bd404-185">完了したら、DKE を使用してドキュメントとファイルを暗号化できます。</span><span class="sxs-lookup"><span data-stu-id="bd404-185">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="bd404-186">詳細については、「ファイルと [電子メールに](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)感度ラベルを適用する」を参照Office。</span><span class="sxs-lookup"><span data-stu-id="bd404-186">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites-for-the-dke-service"></a><span data-ttu-id="bd404-187">DKE サービスのソフトウェア前提条件のインストール</span><span class="sxs-lookup"><span data-stu-id="bd404-187">Install software prerequisites for the DKE service</span></span>

<span data-ttu-id="bd404-188">DKE サービスをインストールするコンピューターに、これらの前提条件をインストールします。</span><span class="sxs-lookup"><span data-stu-id="bd404-188">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="bd404-189">**.NET Core 3.1 SDK**.</span><span class="sxs-lookup"><span data-stu-id="bd404-189">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="bd404-190">ダウンロード [.NET Core 3.1 から SDK をダウンロードしてインストールします](https://dotnet.microsoft.com/download/dotnet-core/3.1)。</span><span class="sxs-lookup"><span data-stu-id="bd404-190">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="bd404-191">**Visual Studio コード**.</span><span class="sxs-lookup"><span data-stu-id="bd404-191">**Visual Studio Code**.</span></span> <span data-ttu-id="bd404-192">からVisual Studioコードをダウンロードします [https://code.visualstudio.com/](https://code.visualstudio.com) 。</span><span class="sxs-lookup"><span data-stu-id="bd404-192">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="bd404-193">インストールが完了したら、Visual Studioコードを実行し、[拡張機能の表示 **]** \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bd404-193">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="bd404-194">これらの拡張機能をインストールします。</span><span class="sxs-lookup"><span data-stu-id="bd404-194">Install these extensions.</span></span>

- <span data-ttu-id="bd404-195">C#コードVisual Studio</span><span class="sxs-lookup"><span data-stu-id="bd404-195">C# for Visual Studio Code</span></span>

- <span data-ttu-id="bd404-196">NuGet パッケージ マネージャー</span><span class="sxs-lookup"><span data-stu-id="bd404-196">NuGet Package Manager</span></span>

<span data-ttu-id="bd404-197">**Git リソース**.</span><span class="sxs-lookup"><span data-stu-id="bd404-197">**Git resources**.</span></span> <span data-ttu-id="bd404-198">次のいずれかをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="bd404-198">Download and install one of the following.</span></span>

- [<span data-ttu-id="bd404-199">Git</span><span class="sxs-lookup"><span data-stu-id="bd404-199">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="bd404-200">GitHub Desktop</span><span class="sxs-lookup"><span data-stu-id="bd404-200">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="bd404-201">GitHub Enterprise</span><span class="sxs-lookup"><span data-stu-id="bd404-201">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="bd404-202">**OpenSSL** DKE の展開 [後にテスト](https://slproweb.com/products/Win32OpenSSL.html) キーを [生成するには、OpenSSL](#generate-test-keys) がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd404-202">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="bd404-203">環境変数パスから正しく呼び出されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bd404-203">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="bd404-204">たとえば、詳細については、「インストール ディレクトリを PATH に追加する」 [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd404-204">For example, see "Add the installation directory to PATH" at [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) for details.</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="bd404-205">DKE GitHub リポジトリの複製</span><span class="sxs-lookup"><span data-stu-id="bd404-205">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="bd404-206">Microsoft は、GitHub リポジトリに DKE ソース ファイルを提供します。</span><span class="sxs-lookup"><span data-stu-id="bd404-206">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="bd404-207">リポジトリを複製して、組織で使用するためにプロジェクトをローカルにビルドします。</span><span class="sxs-lookup"><span data-stu-id="bd404-207">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="bd404-208">DKE GitHub リポジトリは . [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span><span class="sxs-lookup"><span data-stu-id="bd404-208">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="bd404-209">次の手順は、経験の浅い git またはコード Visual Studio向けです。</span><span class="sxs-lookup"><span data-stu-id="bd404-209">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="bd404-210">ブラウザーで、次のページに移動します [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) 。</span><span class="sxs-lookup"><span data-stu-id="bd404-210">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

2. <span data-ttu-id="bd404-211">画面の右側にある [コード] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="bd404-211">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="bd404-212">バージョンの UI に [複製] または [ダウンロード **] ボタンが表示される場合** があります。</span><span class="sxs-lookup"><span data-stu-id="bd404-212">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="bd404-213">次に、表示されるドロップダウンで、コピー アイコンを選択して URL をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="bd404-213">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="bd404-214">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bd404-214">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bd404-215">![GitHub からダブル キー暗号化サービス リポジトリを複製する](../media/dke-clone.png)</span><span class="sxs-lookup"><span data-stu-id="bd404-215">![Clone the Double Key Encryption service repository from GitHub](../media/dke-clone.png)</span></span>

3. <span data-ttu-id="bd404-216">[コードVisual Studio] で、[ **コマンド パレットの表示]** \> **を選択** し **、[Git: Clone] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bd404-216">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="bd404-217">リスト内のオプションに移動するには、入力を開始してエントリをフィルター処理し、ドロップダウン `git: clone` から選択します。</span><span class="sxs-lookup"><span data-stu-id="bd404-217">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="bd404-218">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bd404-218">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bd404-219">![Visual Studio GIT:Clone オプション](../media/dke-vscode-clone.png)</span><span class="sxs-lookup"><span data-stu-id="bd404-219">![Visual Studio Code GIT:Clone option](../media/dke-vscode-clone.png)</span></span>

4. <span data-ttu-id="bd404-220">テキスト ボックスに、Git からコピーした URL を貼り付け、[GitHub から **複製] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bd404-220">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="bd404-221">表示される **[フォルダーの** 選択] ダイアログで、リポジトリを保存する場所を参照して選択します。</span><span class="sxs-lookup"><span data-stu-id="bd404-221">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="bd404-222">プロンプトで、[開く] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="bd404-222">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="bd404-223">リポジトリが [コード] Visual Studio開き、左下に現在の Git ブランチが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd404-223">The repository opens in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="bd404-224">たとえば、ブランチは main である **必要があります**。</span><span class="sxs-lookup"><span data-stu-id="bd404-224">For example,  The branch should be **main**.</span></span> <span data-ttu-id="bd404-225">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bd404-225">For example:</span></span>

   ![メイン ブランチを表示するコードVisual Studio DKE repo のスクリーンショット](../media/dke-vscode-main-branch.jpg)

6. <span data-ttu-id="bd404-227">メイン ブランチにいない場合は、そのブランチを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd404-227">If you're not on the main branch, you'll need to select it.</span></span> <span data-ttu-id="bd404-228">[Visual Studioコード] で、ブランチを選択し、表示されるブランチの一覧から main を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd404-228">In Visual Studio Code, select the branch and choose **main** from the list of branches that displays.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="bd404-229">メイン ブランチを選択すると、プロジェクトをビルドするための適切なファイルが確実に作成されます。</span><span class="sxs-lookup"><span data-stu-id="bd404-229">Selecting the main branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="bd404-230">正しいブランチを選択しない場合、展開は失敗します。</span><span class="sxs-lookup"><span data-stu-id="bd404-230">If you don't choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="bd404-231">これで、DKE ソース リポジトリがローカルにセットアップされます。</span><span class="sxs-lookup"><span data-stu-id="bd404-231">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="bd404-232">次に [、組織のアプリケーション設定](#modify-application-settings) を変更します。</span><span class="sxs-lookup"><span data-stu-id="bd404-232">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="bd404-233">アプリケーション設定の変更</span><span class="sxs-lookup"><span data-stu-id="bd404-233">Modify application settings</span></span>

<span data-ttu-id="bd404-234">DKE サービスを展開するには、次の種類のアプリケーション設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd404-234">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="bd404-235">キー アクセス設定</span><span class="sxs-lookup"><span data-stu-id="bd404-235">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="bd404-236">テナントとキーの設定</span><span class="sxs-lookup"><span data-stu-id="bd404-236">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="bd404-237">アプリケーションの設定は、ファイルのappsettings.js変更します。</span><span class="sxs-lookup"><span data-stu-id="bd404-237">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="bd404-238">このファイルは、ローカルで複製した DoubleKeyEncryptionService リポジトリの DoubleKeyEncryptionService\src\customer-key-store にあります。</span><span class="sxs-lookup"><span data-stu-id="bd404-238">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="bd404-239">たとえば、[コード] Visual Studio、次の図に示すようにファイルを参照できます。</span><span class="sxs-lookup"><span data-stu-id="bd404-239">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

![DKE のappsettings.jsを検索します。](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a><span data-ttu-id="bd404-241">キー アクセス設定</span><span class="sxs-lookup"><span data-stu-id="bd404-241">Key access settings</span></span>

<span data-ttu-id="bd404-242">電子メールまたは役割の承認を使用するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="bd404-242">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="bd404-243">DKE では、一度にサポートされる認証方法は 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="bd404-243">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="bd404-244">**電子メールの承認**。</span><span class="sxs-lookup"><span data-stu-id="bd404-244">**Email authorization**.</span></span> <span data-ttu-id="bd404-245">組織が電子メール アドレスにのみ基づいてキーへのアクセスを承認できます。</span><span class="sxs-lookup"><span data-stu-id="bd404-245">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="bd404-246">**役割の承認**。</span><span class="sxs-lookup"><span data-stu-id="bd404-246">**Role authorization**.</span></span> <span data-ttu-id="bd404-247">組織が Active Directory グループに基づいてキーへのアクセスを承認し、Web サービスが LDAP を照会できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd404-247">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="bd404-248">**電子メール認証を使用して DKE のキー アクセス設定を設定するには**</span><span class="sxs-lookup"><span data-stu-id="bd404-248">**To set key access settings for DKE using email authorization**</span></span>

1. <span data-ttu-id="bd404-249">ファイルのappsettings.js **を開** き、設定を探 `AuthorizedEmailAddress` します。</span><span class="sxs-lookup"><span data-stu-id="bd404-249">Open the **appsettings.json** file and locate the `AuthorizedEmailAddress` setting.</span></span>

2. <span data-ttu-id="bd404-250">承認する電子メール アドレスまたはアドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="bd404-250">Add the email address or addresses that you want to authorize.</span></span> <span data-ttu-id="bd404-251">複数の電子メール アドレスを二重引用符とコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="bd404-251">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="bd404-252">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bd404-252">For example:</span></span>

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. <span data-ttu-id="bd404-253">設定を見 `LDAPPath` つけて、二重引用符の `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` 間のテキストを削除します。</span><span class="sxs-lookup"><span data-stu-id="bd404-253">Locate the `LDAPPath` setting and remove the text `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` between the double quotes.</span></span> <span data-ttu-id="bd404-254">二重引用符はそのままにしてください。</span><span class="sxs-lookup"><span data-stu-id="bd404-254">Leave the double quotes in place.</span></span> <span data-ttu-id="bd404-255">完了したら、この設定は次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd404-255">When you're finished, the setting should look like this.</span></span>

   ```json
   "LDAPPath": ""
   ```

4. <span data-ttu-id="bd404-256">設定を見 `AuthorizedRoles` つけて、行全体を削除します。</span><span class="sxs-lookup"><span data-stu-id="bd404-256">Locate the `AuthorizedRoles` setting and delete the entire line.</span></span>

<span data-ttu-id="bd404-257">次の図は、電子 **メールappsettings.js形式** のファイルに関する情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="bd404-257">This image shows the **appsettings.json** file correctly formatted for email authorization.</span></span>

   ![メールappsettings.js方法を示すファイルに関する情報](../media/dke-email-accesssetting.png)

<span data-ttu-id="bd404-259">**役割の承認を使用して DKE のキー アクセス設定を設定するには**</span><span class="sxs-lookup"><span data-stu-id="bd404-259">**To set key access settings for DKE using role authorization**</span></span>

1. <span data-ttu-id="bd404-260">ファイルのappsettings.js **を開** き、設定を探 `AuthorizedRoles` します。</span><span class="sxs-lookup"><span data-stu-id="bd404-260">Open the **appsettings.json** file and locate the `AuthorizedRoles` setting.</span></span>

2. <span data-ttu-id="bd404-261">承認する Active Directory グループ名を追加します。</span><span class="sxs-lookup"><span data-stu-id="bd404-261">Add the Active Directory group names you want to authorize.</span></span> <span data-ttu-id="bd404-262">複数のグループ名を二重引用符とコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="bd404-262">Separate multiple group names with double quotes and commas.</span></span> <span data-ttu-id="bd404-263">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bd404-263">For example:</span></span>

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. <span data-ttu-id="bd404-264">設定を見 `LDAPPath` つけて、Active Directory ドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="bd404-264">Locate the `LDAPPath` setting and add the Active Directory domain.</span></span> <span data-ttu-id="bd404-265">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bd404-265">For example:</span></span>

   ```json
   "LDAPPath": "contoso.com"
   ```

4. <span data-ttu-id="bd404-266">設定を見 `AuthorizedEmailAddress` つけて、行全体を削除します。</span><span class="sxs-lookup"><span data-stu-id="bd404-266">Locate the `AuthorizedEmailAddress` setting and delete the entire line.</span></span>

<span data-ttu-id="bd404-267">次の図は、役割の **appsettings.js形式** のファイルに関する情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="bd404-267">This image shows the **appsettings.json** file correctly formatted for role authorization.</span></span>

   ![appsettings.js承認方法を示すファイルに関する情報](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="bd404-269">テナントとキーの設定</span><span class="sxs-lookup"><span data-stu-id="bd404-269">Tenant and key settings</span></span>

<span data-ttu-id="bd404-270">DKE テナントとキー設定は、ファイルのappsettings.js **に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="bd404-270">DKE tenant and key settings are located in the **appsettings.json** file.</span></span>

<span data-ttu-id="bd404-271">**DKE のテナントとキーの設定を構成するには**</span><span class="sxs-lookup"><span data-stu-id="bd404-271">**To configure tenant and key settings for DKE**</span></span>

1. <span data-ttu-id="bd404-272">ファイルのappsettings.js **開** きます。</span><span class="sxs-lookup"><span data-stu-id="bd404-272">Open the **appsettings.json** file.</span></span>

2. <span data-ttu-id="bd404-273">設定を見 `ValidIssuers` つけて、テナント `<tenantid>` ID に置き換える。</span><span class="sxs-lookup"><span data-stu-id="bd404-273">Locate the `ValidIssuers` setting and replace `<tenantid>` with your tenant ID.</span></span> <span data-ttu-id="bd404-274">テナント ID を見つけるには、Azure portal にアクセスしてテナントのプロパティを [表示します](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。</span><span class="sxs-lookup"><span data-stu-id="bd404-274">You can locate your tenant ID by going to the Azure portal and viewing the [tenant properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="bd404-275">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bd404-275">For example:</span></span>

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```
> [!NOTE]
> <span data-ttu-id="bd404-276">キー ストアへの外部 B2B アクセスを有効にする場合は、有効な発行者のリストの一部としてこれらの外部テナントも含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd404-276">If you want to enable external B2B access to your key store, you will also need to include these external tenants as part of the valid issuers' list.</span></span>

<span data-ttu-id="bd404-277">を探します `JwtAudience` 。</span><span class="sxs-lookup"><span data-stu-id="bd404-277">Locate the `JwtAudience`.</span></span> <span data-ttu-id="bd404-278">`<yourhostname>`DKE サービスが実行されるコンピューターのホスト名に置き換える。</span><span class="sxs-lookup"><span data-stu-id="bd404-278">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span> <span data-ttu-id="bd404-279">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bd404-279">For example:</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="bd404-280">の値は `JwtAudience` 、ホストの名前と完全に一致 *する必要があります*。</span><span class="sxs-lookup"><span data-stu-id="bd404-280">The value for `JwtAudience` must match the name of your host *exactly*.</span></span> <span data-ttu-id="bd404-281">デバッグ中に **localhost:5001 を** 使用できます。</span><span class="sxs-lookup"><span data-stu-id="bd404-281">You may use **localhost:5001** while debugging.</span></span> <span data-ttu-id="bd404-282">ただし、デバッグが完了したら、この値をサーバーのホスト名に更新してください。</span><span class="sxs-lookup"><span data-stu-id="bd404-282">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="bd404-283">`TestKeys:Name`.</span><span class="sxs-lookup"><span data-stu-id="bd404-283">`TestKeys:Name`.</span></span> <span data-ttu-id="bd404-284">キーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="bd404-284">Enter a name for your key.</span></span> <span data-ttu-id="bd404-285">例: `TestKey1`</span><span class="sxs-lookup"><span data-stu-id="bd404-285">For example: `TestKey1`</span></span>
- <span data-ttu-id="bd404-286">`TestKeys:Id`.</span><span class="sxs-lookup"><span data-stu-id="bd404-286">`TestKeys:Id`.</span></span> <span data-ttu-id="bd404-287">GUID を作成し、値として入力 `TestKeys:ID` します。</span><span class="sxs-lookup"><span data-stu-id="bd404-287">Create a GUID and enter it as the `TestKeys:ID` value.</span></span> <span data-ttu-id="bd404-288">たとえば、`DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE` などです。</span><span class="sxs-lookup"><span data-stu-id="bd404-288">For example, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span></span> <span data-ttu-id="bd404-289">オンライン GUID ジェネレーターのようなサイト [を使用して、GUID](https://guidgenerator.com/) をランダムに生成できます。</span><span class="sxs-lookup"><span data-stu-id="bd404-289">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

<span data-ttu-id="bd404-290">次の図は、テナントの正しい形式とキーの設定をオンにappsettings.js **します**。</span><span class="sxs-lookup"><span data-stu-id="bd404-290">This image shows the correct format for tenant and keys settings in **appsettings.json**.</span></span> <span data-ttu-id="bd404-291">`LDAPPath` は、役割の承認用に構成されます。</span><span class="sxs-lookup"><span data-stu-id="bd404-291">`LDAPPath` is configured for role authorization.</span></span>

![DKE のテナントとキーの正しい設定をファイルのappsettings.js表示します。](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a><span data-ttu-id="bd404-293">テスト キーの生成</span><span class="sxs-lookup"><span data-stu-id="bd404-293">Generate test keys</span></span>

<span data-ttu-id="bd404-294">アプリケーション設定を定義したら、公開キーとプライベート テスト キーを生成する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="bd404-294">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="bd404-295">キーを生成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="bd404-295">To generate keys:</span></span>

1. <span data-ttu-id="bd404-296">[Windows スタート] メニューから、OpenSSL コマンド プロンプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="bd404-296">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

2. <span data-ttu-id="bd404-297">テスト キーを保存するフォルダーに変更します。</span><span class="sxs-lookup"><span data-stu-id="bd404-297">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="bd404-298">このタスクの手順を完了して作成するファイルは、同じフォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="bd404-298">The files you create by completing the steps in this task are stored in the same folder.</span></span>

3. <span data-ttu-id="bd404-299">新しいテスト キーを生成します。</span><span class="sxs-lookup"><span data-stu-id="bd404-299">Generate the new test key.</span></span>

   ```console
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

4. <span data-ttu-id="bd404-300">プライベート キーを生成します。</span><span class="sxs-lookup"><span data-stu-id="bd404-300">Generate the private key.</span></span>

   ```console
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

5. <span data-ttu-id="bd404-301">公開キーを生成します。</span><span class="sxs-lookup"><span data-stu-id="bd404-301">Generate the public key.</span></span>

   ```console
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

6. <span data-ttu-id="bd404-302">テキスト エディターで **、pubkeyonly.pem を開きます**。</span><span class="sxs-lookup"><span data-stu-id="bd404-302">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="bd404-303">**pubkeyonly.pem** ファイル内のすべてのコンテンツ (最初の行と最後の行を除く) を、ファイルのappsettings.js`PublicPem` **にコピー** します。</span><span class="sxs-lookup"><span data-stu-id="bd404-303">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the `PublicPem` section of the **appsettings.json** file.</span></span>

7. <span data-ttu-id="bd404-304">テキスト エディターで **、privkeynopass.pem を開きます**。</span><span class="sxs-lookup"><span data-stu-id="bd404-304">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="bd404-305">最初の行と最後の行を除く **、privkeynopass.pem** ファイル内のすべてのコンテンツを、appsettings.js`PrivatePem` **にコピー** します。</span><span class="sxs-lookup"><span data-stu-id="bd404-305">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the `PrivatePem` section of the **appsettings.json** file.</span></span>

8. <span data-ttu-id="bd404-306">セクションとセクションの両方のすべての空白と改行を `PublicPem` `PrivatePem` 削除します。</span><span class="sxs-lookup"><span data-stu-id="bd404-306">Remove all blank spaces and newlines in both the `PublicPem` and `PrivatePem` sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="bd404-307">このコンテンツをコピーする場合は、PEM データを削除しない。</span><span class="sxs-lookup"><span data-stu-id="bd404-307">When you copy this content, do not delete any of the PEM data.</span></span>

9. <span data-ttu-id="bd404-308">[Visual Studioコード] で **、Startup.cs ファイルを参照** します。</span><span class="sxs-lookup"><span data-stu-id="bd404-308">In Visual Studio Code, browse to the **Startup.cs** file.</span></span> <span data-ttu-id="bd404-309">このファイルは、DoubleKeyEncryptionService\src\customer-key-store\の下でローカルに複製した DoubleKeyEncryptionService リポジトリにあります。</span><span class="sxs-lookup"><span data-stu-id="bd404-309">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store\.</span></span>

10. <span data-ttu-id="bd404-310">次の行を探します。</span><span class="sxs-lookup"><span data-stu-id="bd404-310">Locate the following lines:</span></span>

    ```csharp
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
    ```

11. <span data-ttu-id="bd404-311">これらの行を次のテキストに置き換える。</span><span class="sxs-lookup"><span data-stu-id="bd404-311">Replace these lines with the following text:</span></span>

    ```csharp
    services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
    ```

    <span data-ttu-id="bd404-312">最後の結果は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="bd404-312">The end results should look similar to the following.</span></span>

    ![パブリック プレビュー用の startup.cs ファイル](../media/dke-startupcs-usetestkeys.png)

<span data-ttu-id="bd404-314">これで、DKE プロジェクト [をビルドする準備ができました](#build-the-project)。</span><span class="sxs-lookup"><span data-stu-id="bd404-314">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="bd404-315">プロジェクトをビルドする</span><span class="sxs-lookup"><span data-stu-id="bd404-315">Build the project</span></span>

<span data-ttu-id="bd404-316">DKE プロジェクトをローカルでビルドするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="bd404-316">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="bd404-317">[Visual Studioコード] の DKE サービス リポジトリで、[コマンド パレットの表示] を選択し、プロンプトに「 \> **ビルド」** と入力します。</span><span class="sxs-lookup"><span data-stu-id="bd404-317">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

2. <span data-ttu-id="bd404-318">一覧から、[タスク: ビルド **タスクの実行] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bd404-318">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="bd404-319">ビルド タスクが見つからない場合は、[ビルド タスクの構成] を **選択し、** 次のように .NET コア用に作成します。</span><span class="sxs-lookup"><span data-stu-id="bd404-319">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   ![.NET の不足しているビルド タスクを構成する](../media/dke-configurebuildtask.png)

   1. <span data-ttu-id="bd404-321">[テンプレート **からtasks.jsを作成する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bd404-321">Choose **Create tasks.json from template**.</span></span>

      ![DKE tasks.jsからファイルにファイルを作成する](../media/dke-createtasksjsonfromtemplate.png)

   2. <span data-ttu-id="bd404-323">テンプレートの種類の一覧から **、[.NET Core] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bd404-323">From the list of template types, select **.NET Core**.</span></span>

      ![DKE に適切なテンプレートを選択する](../media/dke-tasksjsontemplate.png)

   3. <span data-ttu-id="bd404-325">ビルド セクションで **、customerkeystore.csproj ファイルへのパスを見** つけます。</span><span class="sxs-lookup"><span data-stu-id="bd404-325">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="bd404-326">表示されていない場合は、次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="bd404-326">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

   4. <span data-ttu-id="bd404-327">ビルドを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="bd404-327">Run the build again.</span></span>

3. <span data-ttu-id="bd404-328">出力ウィンドウに赤いエラーが表示されません。</span><span class="sxs-lookup"><span data-stu-id="bd404-328">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="bd404-329">赤色のエラーがある場合は、コンソール出力を確認します。</span><span class="sxs-lookup"><span data-stu-id="bd404-329">If there are red errors, check the console output.</span></span> <span data-ttu-id="bd404-330">前のすべての手順が正しく完了し、正しいビルド バージョンが存在していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bd404-330">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

4. <span data-ttu-id="bd404-331">[ **デバッグ** \> **の開始] を選択** して、プロセスをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="bd404-331">Select **Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="bd404-332">環境の選択を求めるメッセージが表示されたら **、[.NET core] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bd404-332">If you're prompted to select an environment, select **.NET core**.</span></span>

   <span data-ttu-id="bd404-333">.NET コア デバッガーは通常、 に起動します `https://localhost:5001` 。</span><span class="sxs-lookup"><span data-stu-id="bd404-333">The .NET core debugger typically launches to `https://localhost:5001`.</span></span> <span data-ttu-id="bd404-334">テスト キーを表示するには、スラッシュ (/) とキーの `https://localhost:5001` 名前に移動して追加します。</span><span class="sxs-lookup"><span data-stu-id="bd404-334">To view your test key, go to `https://localhost:5001` and append a forward slash (/) and the name of your key.</span></span> <span data-ttu-id="bd404-335">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bd404-335">For example:</span></span>

   ```https
   https://localhost:5001/TestKey1
   ```

   <span data-ttu-id="bd404-336">キーは JSON 形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd404-336">The key should display in JSON format.</span></span>

<span data-ttu-id="bd404-337">これでセットアップは完了です。</span><span class="sxs-lookup"><span data-stu-id="bd404-337">Your setup is now complete.</span></span> <span data-ttu-id="bd404-338">キーストアを発行する前appsettings.jsで、JwtAudience 設定の場合は、ホスト名の値が App Service ホスト名と完全に一致するようにします。</span><span class="sxs-lookup"><span data-stu-id="bd404-338">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="bd404-339">ビルドのトラブルシューティングを行う際に localhost に変更した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bd404-339">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="deploy-the-dke-service-and-publish-the-key-store"></a><span data-ttu-id="bd404-340">DKE サービスを展開し、キー ストアを発行する</span><span class="sxs-lookup"><span data-stu-id="bd404-340">Deploy the DKE service and publish the key store</span></span>

<span data-ttu-id="bd404-341">実稼働環境の場合は、サード パーティのクラウドにサービスを展開するか、オンプレミス [システムに発行します](/aspnet/core/tutorials/publish-to-iis?preserve-view=true&tabs=netcore-cli&view=aspnetcore-3.1)。</span><span class="sxs-lookup"><span data-stu-id="bd404-341">For production deployments, deploy the service either in a third-party cloud or [publish to an on-premises system](/aspnet/core/tutorials/publish-to-iis?preserve-view=true&tabs=netcore-cli&view=aspnetcore-3.1).</span></span>

<span data-ttu-id="bd404-342">他の方法でキーを展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="bd404-342">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="bd404-343">組織に最適な方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd404-343">Select the method that works best for your organization.</span></span>

<span data-ttu-id="bd404-344">パイロット展開の場合は、Azure に展開して、すぐ開始できます。</span><span class="sxs-lookup"><span data-stu-id="bd404-344">For pilot deployments, you can deploy in Azure and get started right away.</span></span>

<span data-ttu-id="bd404-345">**DKE 展開をホストする Azure Web App インスタンスを作成するには**</span><span class="sxs-lookup"><span data-stu-id="bd404-345">**To create an Azure Web App instance to host your DKE deployment**</span></span>

<span data-ttu-id="bd404-346">キー ストアを発行するには、DKE 展開をホストする Azure App Service インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="bd404-346">To publish the key store, you'll create an Azure App Service instance to host your DKE deployment.</span></span> <span data-ttu-id="bd404-347">次に、生成されたキーを Azure に発行します。</span><span class="sxs-lookup"><span data-stu-id="bd404-347">Next, you'll publish your generated keys to Azure.</span></span>

1. <span data-ttu-id="bd404-348">ブラウザーで、Microsoft Azure portal にサインインし [、[App Services Add]](https://ms.portal.azure.com)**に移動**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="bd404-348">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

2. <span data-ttu-id="bd404-349">サブスクリプションとリソース グループを選択し、インスタンスの詳細を定義します。</span><span class="sxs-lookup"><span data-stu-id="bd404-349">Select your subscription and resource group and define your instance details.</span></span>

   - <span data-ttu-id="bd404-350">DKE サービスをインストールするコンピューターのホスト名を入力します。</span><span class="sxs-lookup"><span data-stu-id="bd404-350">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="bd404-351">ファイルの設定で JwtAudience 設定に定義されている名前と同じ名前 [**appsettings.jsしてください**](#tenant-and-key-settings) 。</span><span class="sxs-lookup"><span data-stu-id="bd404-351">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="bd404-352">名前に指定する値も WebAppInstanceName です。</span><span class="sxs-lookup"><span data-stu-id="bd404-352">The value you provide for the name is also the WebAppInstanceName.</span></span>

   - <span data-ttu-id="bd404-353">[ **発行]** で、 **コードを選択** し、[ **ランタイム スタック] で** **[.NET Core 3.1] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bd404-353">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

   <span data-ttu-id="bd404-354">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bd404-354">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bd404-355">![App Service の追加](../media/dke-azure-add-app-service.png)</span><span class="sxs-lookup"><span data-stu-id="bd404-355">![Add your App Service](../media/dke-azure-add-app-service.png)</span></span>

3. <span data-ttu-id="bd404-356">ページの下部で、[レビューと作成] を **選択** し、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="bd404-356">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

4. <span data-ttu-id="bd404-357">生成されたキーを発行するには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="bd404-357">Do one of the following to publish your generated keys:</span></span>

   - [<span data-ttu-id="bd404-358">ZipDeployUI 経由で発行する</span><span class="sxs-lookup"><span data-stu-id="bd404-358">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
   - [<span data-ttu-id="bd404-359">FTP 経由で発行する</span><span class="sxs-lookup"><span data-stu-id="bd404-359">Publish via FTP</span></span>](#publish-via-ftp)
   - [<span data-ttu-id="bd404-360">2019 以降Visual Studio発行する</span><span class="sxs-lookup"><span data-stu-id="bd404-360">Publish via Visual Studio 2019 or later</span></span>](/aspnet/core/tutorials/)

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="bd404-361">ZipDeployUI 経由で発行する</span><span class="sxs-lookup"><span data-stu-id="bd404-361">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="bd404-362">`https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI` に移動します。</span><span class="sxs-lookup"><span data-stu-id="bd404-362">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

   <span data-ttu-id="bd404-363">例: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="bd404-363">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

2. <span data-ttu-id="bd404-364">キー ストアのコードベースで **、customer-key-store\src\customer-key-store** フォルダーに移動し、このフォルダーに **customerkeystore.csproj** ファイルが含まれているか確認します。</span><span class="sxs-lookup"><span data-stu-id="bd404-364">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

3. <span data-ttu-id="bd404-365">実行: **dotnet 発行**</span><span class="sxs-lookup"><span data-stu-id="bd404-365">Run: **dotnet publish**</span></span>

   <span data-ttu-id="bd404-366">出力ウィンドウには、発行が展開されたディレクトリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd404-366">The output window displays the directory where the publish was deployed.</span></span>

   <span data-ttu-id="bd404-367">例: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="bd404-367">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

4. <span data-ttu-id="bd404-368">発行ディレクトリ内のすべてのファイルを .zip ファイルに送信します。</span><span class="sxs-lookup"><span data-stu-id="bd404-368">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="bd404-369">.zip ファイルを作成する場合は、ディレクトリ内のすべてのファイルが .zip ファイルのルート レベルに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd404-369">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

5. <span data-ttu-id="bd404-370">作成した .zip ファイルを、上記で開いた ZipDeployUI サイトにドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="bd404-370">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="bd404-371">例: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="bd404-371">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="bd404-372">DKE が展開され、作成したテスト キーを参照できます。</span><span class="sxs-lookup"><span data-stu-id="bd404-372">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="bd404-373">[次の展開 [の検証] に進](#validate-your-deployment) んでください。</span><span class="sxs-lookup"><span data-stu-id="bd404-373">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="bd404-374">FTP 経由で発行する</span><span class="sxs-lookup"><span data-stu-id="bd404-374">Publish via FTP</span></span>

1. <span data-ttu-id="bd404-375">上記で作成した App Service に [接続します](#deploy-the-dke-service-and-publish-the-key-store)。</span><span class="sxs-lookup"><span data-stu-id="bd404-375">Connect to the App Service you created [above](#deploy-the-dke-service-and-publish-the-key-store).</span></span>

   <span data-ttu-id="bd404-376">ブラウザーで **、「Azure portal** App Service Deployment Center Manual  >  **Deployment** FTP  >    >  **Dashboard」**  >  **に移動**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="bd404-376">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

2. <span data-ttu-id="bd404-377">表示された接続文字列をローカル ファイルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="bd404-377">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="bd404-378">これらの文字列を使用して Web App Service に接続し、FTP 経由でファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="bd404-378">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

   <span data-ttu-id="bd404-379">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bd404-379">For example:</span></span>

   ![FTP ダッシュボードから接続文字列をコピーする](../media/dke-ftp-dashboard.png)

3. <span data-ttu-id="bd404-381">キー ストレージのコードベースで **、customer-key-store\src\customer-key-store ディレクトリに移動します**。</span><span class="sxs-lookup"><span data-stu-id="bd404-381">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

4. <span data-ttu-id="bd404-382">このディレクトリに **customerkeystore.csproj ファイルが含まれているか確認** します。</span><span class="sxs-lookup"><span data-stu-id="bd404-382">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

5. <span data-ttu-id="bd404-383">実行: **dotnet 発行**</span><span class="sxs-lookup"><span data-stu-id="bd404-383">Run: **dotnet publish**</span></span>

   <span data-ttu-id="bd404-384">出力には、発行が展開されたディレクトリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bd404-384">The output contains the directory where the publish was deployed.</span></span>

   <span data-ttu-id="bd404-385">例: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="bd404-385">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

6. <span data-ttu-id="bd404-386">発行ディレクトリ内のすべてのファイルを zip ファイルに送信します。</span><span class="sxs-lookup"><span data-stu-id="bd404-386">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="bd404-387">.zip ファイルを作成する場合は、ディレクトリ内のすべてのファイルが .zip ファイルのルート レベルに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd404-387">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

7. <span data-ttu-id="bd404-388">FTP クライアントから、コピーした接続情報を使用して App Service に接続します。</span><span class="sxs-lookup"><span data-stu-id="bd404-388">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="bd404-389">前の手順で作成した .zip ファイルを Web アプリのルート ディレクトリにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="bd404-389">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="bd404-390">DKE が展開され、作成したテスト キーを参照できます。</span><span class="sxs-lookup"><span data-stu-id="bd404-390">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="bd404-391">次に、 [展開を検証します](#validate-your-deployment)。</span><span class="sxs-lookup"><span data-stu-id="bd404-391">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="bd404-392">展開を検証する</span><span class="sxs-lookup"><span data-stu-id="bd404-392">Validate your deployment</span></span>

<span data-ttu-id="bd404-393">上記のいずれかの方法を使用して DKE を展開した後、展開とキー ストアの設定を検証します。</span><span class="sxs-lookup"><span data-stu-id="bd404-393">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="bd404-394">次を実行します:  </span><span class="sxs-lookup"><span data-stu-id="bd404-394">Run:</span></span>

```powershell
src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey
```

<span data-ttu-id="bd404-395">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bd404-395">For example:</span></span>

```powershell
key_store_tester.ps1 https://mydkeservice.com/mykey
```

<span data-ttu-id="bd404-396">出力にエラーが表示されないか確認します。</span><span class="sxs-lookup"><span data-stu-id="bd404-396">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="bd404-397">準備ができたら、キー [ストアを登録します](#register-your-key-store)。</span><span class="sxs-lookup"><span data-stu-id="bd404-397">When you're ready, [register your key store](#register-your-key-store).</span></span>

<span data-ttu-id="bd404-398">キー名では大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="bd404-398">The key name is case sensitive.</span></span> <span data-ttu-id="bd404-399">ファイルに表示されるキー名をappsettings.jsします。</span><span class="sxs-lookup"><span data-stu-id="bd404-399">Enter the key name as it appears in the appsettings.json file.</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="bd404-400">キー ストアを登録する</span><span class="sxs-lookup"><span data-stu-id="bd404-400">Register your key store</span></span>

<span data-ttu-id="bd404-401">次の手順を実行すると、DKE サービスを登録できます。</span><span class="sxs-lookup"><span data-stu-id="bd404-401">The following steps enable you to register your DKE service.</span></span> <span data-ttu-id="bd404-402">DKE サービスの登録は、ラベルの作成を開始する前に DKE を展開する最後の手順です。</span><span class="sxs-lookup"><span data-stu-id="bd404-402">Registering your DKE service is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="bd404-403">DKE サービスを登録するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="bd404-403">To register the DKE service:</span></span>

1. <span data-ttu-id="bd404-404">ブラウザーで [、Microsoft Azure ポータルを開](https://ms.portal.azure.com/)き、[すべてのサービス ID \> **アプリの登録**] \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="bd404-404">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="bd404-405">[ **新規登録] を** 選択し、わかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="bd404-405">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="bd404-406">表示されるオプションからアカウントの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd404-406">Select an account type from the options displayed.</span></span>

   <span data-ttu-id="bd404-407">Microsoft Azure をカスタム以外のドメイン (onmicrosoft.com など)で使用している場合は、[この組織ディレクトリ内のアカウントのみ] を選択します **(Microsoft のみ - シングル テナント)。**</span><span class="sxs-lookup"><span data-stu-id="bd404-407">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

   <span data-ttu-id="bd404-408">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bd404-408">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bd404-409">![新しいアプリ登録](../media/dke-app-registration.png)</span><span class="sxs-lookup"><span data-stu-id="bd404-409">![New App Registration](../media/dke-app-registration.png)</span></span>

4. <span data-ttu-id="bd404-410">ページの下部にある [登録] **を選択** して、新しいアプリ登録を作成します。</span><span class="sxs-lookup"><span data-stu-id="bd404-410">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="bd404-411">新しいアプリ登録で、左側のウィンドウの [管理] で **、[認証**] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="bd404-411">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="bd404-412">[プラットフォーム **の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bd404-412">Select **Add a platform**.</span></span>

7. <span data-ttu-id="bd404-413">[プラットフォームの **構成] ポップアップで\*\*\*\*、[Web] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bd404-413">On the **Configure platforms** popup, select **Web**.</span></span>

8. <span data-ttu-id="bd404-414">[ **リダイレクト URI] で**、ダブル キー暗号化サービスの URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="bd404-414">Under **Redirect URIs**, enter the URI of your double key encryption service.</span></span> <span data-ttu-id="bd404-415">ホスト名とドメインの両方を含む App Service URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="bd404-415">Enter the App Service URL, including both the hostname and domain.</span></span>

   <span data-ttu-id="bd404-416">例: https://mydkeservicetest.com</span><span class="sxs-lookup"><span data-stu-id="bd404-416">For example: https://mydkeservicetest.com</span></span>

   - <span data-ttu-id="bd404-417">入力する URL は、DKE サービスが展開されているホスト名と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd404-417">The URL you enter must match the hostname where your DKE service is deployed.</span></span>
   - <span data-ttu-id="bd404-418">ローカルでテストする場合は、Visual Studioを使用します **https://localhost:5001** 。</span><span class="sxs-lookup"><span data-stu-id="bd404-418">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
   - <span data-ttu-id="bd404-419">すべての場合、スキームは https である **必要があります**。</span><span class="sxs-lookup"><span data-stu-id="bd404-419">In all cases, the scheme must be **https**.</span></span>

   <span data-ttu-id="bd404-420">ホスト名が App Service のホスト名と完全に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd404-420">Ensure the hostname exactly matches your App Service hostname.</span></span> <span data-ttu-id="bd404-421">ビルドのトラブルシューティングに変更 `localhost` した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bd404-421">You may have changed it to `localhost` to troubleshoot the build.</span></span> <span data-ttu-id="bd404-422">**[appsettings.js] では**、この値はに設定したホスト名です `JwtAudience` 。</span><span class="sxs-lookup"><span data-stu-id="bd404-422">In **appsettings.json**, this value is the hostname you set for `JwtAudience`.</span></span>

9. <span data-ttu-id="bd404-423">[**暗黙的な付与] で\*\*\*\*、[ID トークン] チェック ボックスを** オンにします。</span><span class="sxs-lookup"><span data-stu-id="bd404-423">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

10. <span data-ttu-id="bd404-424">**[保存]** を選択し、変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="bd404-424">Select **Save** to save your changes.</span></span>

11. <span data-ttu-id="bd404-425">左側のウィンドウで、[API の公開] **を選択** し、[アプリケーション ID URI] の横にある [設定] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="bd404-425">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

12. <span data-ttu-id="bd404-426">[API の **公開] ページの [この API** で定義されたスコープ] 領域で、[スコープの追加]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bd404-426">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="bd404-427">新しいスコープでは、次の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="bd404-427">In the new scope:</span></span>

    1. <span data-ttu-id="bd404-428">スコープ名を次のように **定義user_impersonation。**</span><span class="sxs-lookup"><span data-stu-id="bd404-428">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="bd404-429">同意できる管理者とユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="bd404-429">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="bd404-430">必要な残りの値を定義します。</span><span class="sxs-lookup"><span data-stu-id="bd404-430">Define any remaining values required.</span></span>

    4. <span data-ttu-id="bd404-431">**[スコープの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd404-431">Select **Add scope**.</span></span>

    5. <span data-ttu-id="bd404-432">上部の **[保存** ] を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="bd404-432">Select **Save** at the top to save your changes.</span></span>

13. <span data-ttu-id="bd404-433">[API の **公開] ページの**  [承認済みクライアント アプリケーション] 領域で、[クライアント アプリケーションの追加]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bd404-433">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="bd404-434">新しいクライアント アプリケーションで次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="bd404-434">In the new client application:</span></span>

    1. <span data-ttu-id="bd404-435">クライアント ID を次のように定義します `d3590ed6-52b3-4102-aeff-aad2292ab01c` 。</span><span class="sxs-lookup"><span data-stu-id="bd404-435">Define the Client ID as `d3590ed6-52b3-4102-aeff-aad2292ab01c`.</span></span> <span data-ttu-id="bd404-436">この値はクライアント ID Microsoft Officeであり、キー Officeアクセス トークンを取得できます。</span><span class="sxs-lookup"><span data-stu-id="bd404-436">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="bd404-437">[ **承認済みスコープ] で**、有効範囲 **user_impersonation** します。</span><span class="sxs-lookup"><span data-stu-id="bd404-437">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="bd404-438">**[アプリケーションの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd404-438">Select **Add application**.</span></span>

    4. <span data-ttu-id="bd404-439">上部の **[保存** ] を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="bd404-439">Select **Save** at the top to save your changes.</span></span>

    5. <span data-ttu-id="bd404-440">これらの手順を繰り返しますが、今回は、クライアント ID をとして定義します `c00e9d32-3c8d-4a7d-832b-029040e7db99` 。</span><span class="sxs-lookup"><span data-stu-id="bd404-440">Repeat these steps, but this time, define the client ID as `c00e9d32-3c8d-4a7d-832b-029040e7db99`.</span></span> <span data-ttu-id="bd404-441">この値は、Azure Information Protection 統合ラベル付けクライアント ID です。</span><span class="sxs-lookup"><span data-stu-id="bd404-441">This value is the Azure Information Protection unified labeling client ID.</span></span> 

<span data-ttu-id="bd404-442">これで、DKE サービスが登録されます。</span><span class="sxs-lookup"><span data-stu-id="bd404-442">Your DKE service is now registered.</span></span> <span data-ttu-id="bd404-443">[DKE を使用してラベルを作成して続行します](#create-sensitivity-labels-using-dke)。</span><span class="sxs-lookup"><span data-stu-id="bd404-443">Continue by [creating labels using DKE](#create-sensitivity-labels-using-dke).</span></span>

## <a name="create-sensitivity-labels-using-dke"></a><span data-ttu-id="bd404-444">DKE を使用して感度ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="bd404-444">Create sensitivity labels using DKE</span></span>

<span data-ttu-id="bd404-445">Microsoft 365 コンプライアンス センターで、新しい感度ラベルを作成し、それ以外の場合と同様に暗号化を適用します。</span><span class="sxs-lookup"><span data-stu-id="bd404-445">In the Microsoft 365 compliance center, create a new sensitivity label and apply encryption as you would otherwise.</span></span> <span data-ttu-id="bd404-446">[ **ダブル キー暗号化を使用する]** を選択し、キーのエンドポイント URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="bd404-446">Select **Use Double Key Encryption** and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="bd404-447">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bd404-447">For example:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bd404-448">![Microsoft 365 コンプライアンス センターで [ダブル キー暗号化を使用する] を選択します。](../media/dke-use-dke.png)</span><span class="sxs-lookup"><span data-stu-id="bd404-448">![Select Use Double Key Encryption in the Microsoft 365 compliance center](../media/dke-use-dke.png)</span></span>

<span data-ttu-id="bd404-449">追加した DKE ラベルは、Microsoft 365 Apps for enterprise の最新バージョンのユーザーに対して表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd404-449">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="bd404-450">クライアントが新しいラベルで更新するには、最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bd404-450">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="bd404-451">クライアントで DKE を有効にする</span><span class="sxs-lookup"><span data-stu-id="bd404-451">Enable DKE in your client</span></span>

<span data-ttu-id="bd404-452">Insider のユーザー Office DKE が有効になります。</span><span class="sxs-lookup"><span data-stu-id="bd404-452">If you're an Office Insider, DKE is enabled for you.</span></span> <span data-ttu-id="bd404-453">それ以外の場合は、次のレジストリ キーを追加して、クライアントの DKE を有効にします。</span><span class="sxs-lookup"><span data-stu-id="bd404-453">Otherwise, enable DKE for your client by adding the following registry keys:</span></span>

```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001

   [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001
```

## <a name="migrate-protected-files-from-hyok-labels-to-dke-labels"></a><span data-ttu-id="bd404-454">保護されたファイルを HYOK ラベルから DKE ラベルに移行する</span><span class="sxs-lookup"><span data-stu-id="bd404-454">Migrate protected files from HYOK labels to DKE labels</span></span>

<span data-ttu-id="bd404-455">必要な場合は、DKE の設定が完了したら、HYOK ラベルを使用して保護したコンテンツを DKE ラベルに移行できます。</span><span class="sxs-lookup"><span data-stu-id="bd404-455">If you want, once you're finished setting up DKE, you can migrate content that you've protected using HYOK labels to DKE labels.</span></span> <span data-ttu-id="bd404-456">移行するには、AIP スキャナーを使用します。</span><span class="sxs-lookup"><span data-stu-id="bd404-456">To migrate, you'll use the AIP scanner.</span></span> <span data-ttu-id="bd404-457">スキャナーの使用を開始するには、「Azure Information Protection 統合ラベル スキャナーとは」 [を参照してください](/azure/information-protection/deploy-aip-scanner)。</span><span class="sxs-lookup"><span data-stu-id="bd404-457">To get started using the scanner, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner).</span></span>

<span data-ttu-id="bd404-458">コンテンツを移行しない場合、HYOK で保護されたコンテンツは影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="bd404-458">If you don't migrate content, your HYOK protected content will remain unaffected.</span></span>
