---
title: 二重キー暗号化 (DKE)
description: DKE を使用すると、キーのフルコントロールを維持しながら、機密性の高いデータを保護することができます。
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 07/21/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: f36eeeb1f228bff48088cbbf3241d6866d0b3a21
ms.sourcegitcommit: 234726a1795d984c4659da68f852d30a4dda5711
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "46794166"
---
# <a name="double-key-encryption-dke"></a><span data-ttu-id="8cf5c-103">二重キー暗号化 (DKE)</span><span class="sxs-lookup"><span data-stu-id="8cf5c-103">Double Key Encryption (DKE)</span></span>

> <span data-ttu-id="8cf5c-104">*適用対象: Microsoft 365 パブリックプレビュー、 [microsoft 365 コンプライアンス](https://www.microsoft.com/microsoft-365/business/compliance-management)、 [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)の二重キー暗号化*</span><span class="sxs-lookup"><span data-stu-id="8cf5c-104">*Applies to: Double Key Encryption for Microsoft 365 public preview, [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="8cf5c-105">*手順: [Azure Information Protection を使用した Windows 用の統一されたラベル付けクライアント](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span><span class="sxs-lookup"><span data-stu-id="8cf5c-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="8cf5c-106">*サービスの説明: [Microsoft 365 コンプライアンス](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="8cf5c-106">*Service description for: [Microsoft 365 Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="8cf5c-107">二重キー暗号化 (DKE) は、2つのキーを一緒に使用して、保護されたコンテンツにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-107">Double Key Encryption (DKE) uses two keys together to access protected content.</span></span> <span data-ttu-id="8cf5c-108">Microsoft Azure には1つのキーを保存し、もう一方のキーは保持します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-108">You store one key in Microsoft Azure, and you hold the other key.</span></span> <span data-ttu-id="8cf5c-109">Azure Information Protection の統合されたラベルクライアントは、キーの1つのフルコントロールを維持しながら、機密性の高いコンテンツを保護します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-109">The Azure Information Protection unified labeling client protects highly sensitive content while you maintain full control of one of your keys.</span></span>

<span data-ttu-id="8cf5c-110">二重キー暗号化は、クラウドとオンプレミスの両方の展開をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-110">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="8cf5c-111">これらの展開は、保護されたデータを格納する際に、暗号化されたデータが透過的であるようにするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-111">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="8cf5c-112">既定のクラウドベースのテナントルートキーの詳細については、「 [Azure Information Protection のテナントキーを計画および実装](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-112">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span></span>

<!--
The following video shows how Double Key Encryption works to secure your content.

> [!VIDEO https://msit.microsoftstream.com/embed/video/f466a1ff-0400-a936-221c-f1eab45dc756]
-->

<span data-ttu-id="8cf5c-113">組織に次の要件がある場合は、DKE を使用してコンテンツをセキュリティで保護できます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-113">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="8cf5c-114">すべての状況で保護されたコンテンツの暗号化を *解除できるよう* にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-114">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="8cf5c-115">保護されたデータへのアクセス権を Microsoft に付与しないようにします。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-115">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="8cf5c-116">地理的な境界内にキーを保持する規制要件があります。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-116">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="8cf5c-117">データの暗号化と復号化に使用するすべてのキーは、データセンターに保持されます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-117">All of the keys that you hold for data encryption and decryption are maintained in your data center.</span></span>

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="8cf5c-118">DKE のシステムおよびライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="8cf5c-118">System and licensing requirements for DKE</span></span>

<span data-ttu-id="8cf5c-119">Microsoft 365 の二重キー暗号化には、Microsoft 365 E5 および Office 365 E5 が付属しています。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-119">Double Key Encryption for Microsoft 365 comes with Microsoft 365 E5 and Office 365 E5.</span></span> <span data-ttu-id="8cf5c-120">Microsoft 365 E5 ライセンスを持っていない場合は、 [試用版](https://aka.ms/M365E5ComplianceTrial)にサインアップできます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-120">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="8cf5c-121">これらのライセンスの詳細については、「 [Microsoft 365 licensing ガイダンス for security & 法令遵守](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-121">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="8cf5c-122">**Office Insider** パブリックプレビューを使用するには、Office Insider プログラムのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-122">**Office Insider** To use the public preview, you must be a member of the Office Insider program.</span></span> <span data-ttu-id="8cf5c-123">Office Insider に参加するには、にアクセス [https://insider.office.com](https://insider.office.com) してください。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-123">To join Office Insider, go to [https://insider.office.com](https://insider.office.com).</span></span> <span data-ttu-id="8cf5c-124">メンバーになったら、組織に適した展開方法を選択して、Office Insider ビルドを展開するための環境を準備します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-124">Once you're a member, prepare your environment to deploy Office Insider builds by choosing the right deployment method for your organization.</span></span> <span data-ttu-id="8cf5c-125">手順については、「 [Office Insider ビルドの展開の](https://insider.office.com/business/deploy)概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-125">For instructions, see [Getting started on deploying Office Insider builds](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="8cf5c-126">**Azure Information Protection**。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-126">**Azure Information Protection**.</span></span> <span data-ttu-id="8cf5c-127">DKE は機密ラベルを使用し、Azure Information Protection を必要とします。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-127">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="8cf5c-128">DKE で保護されたコンテンツを保存および表示するためにサポートされている環境</span><span class="sxs-lookup"><span data-stu-id="8cf5c-128">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="8cf5c-129">**サポートされるアプリケーション**。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-129">**Supported applications**.</span></span> <span data-ttu-id="8cf5c-130">Word、Excel、PowerPoint など、Windows の[エンタープライズクライアント用の Microsoft 365 アプリ](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product)。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-130">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="8cf5c-131">**オンラインコンテンツのサポート**。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-131">**Online content support**.</span></span> <span data-ttu-id="8cf5c-132">Microsoft SharePoint と OneDrive for business の両方でオンラインで格納されたドキュメントやファイルはサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-132">Documents and files stored online in both Microsoft SharePoint and OneDrive for Business are supported.</span></span> <span data-ttu-id="8cf5c-133">暗号化されたコンテンツを電子メールで共有することはできますが、暗号化されたドキュメントやファイルをオンラインで表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-133">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="8cf5c-134">代わりに、ローカルコンピューターのデスクトップアプリを使用して、保護されたコンテンツを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-134">Instead, you must view protected content using the desktop apps on your local computer.</span></span>

## <a name="about-this-public-preview-article"></a><span data-ttu-id="8cf5c-135">このパブリックプレビューの記事について</span><span class="sxs-lookup"><span data-stu-id="8cf5c-135">About this public preview article</span></span>

<span data-ttu-id="8cf5c-136">二重キー暗号化を展開するための手順のいくつかを実行するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-136">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="8cf5c-137">この記事では、より熟練していない管理者がサービスを正常に展開するための詳細な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-137">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="8cf5c-138">使いやすい場合は、独自のメソッドを使用することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-138">If you're comfortable doing so, you can choose to use your own methods.</span></span>

<span data-ttu-id="8cf5c-139">この記事では、2重のキー暗号化サービスを Azure に展開する方法について手順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-139">This article includes step-by-step instructions on how to deploy the Double Key Encryption service to Azure.</span></span> <span data-ttu-id="8cf5c-140">このシナリオは、運用環境での可能性があるものではありません。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-140">This scenario isn't something you'd likely do in production.</span></span> <span data-ttu-id="8cf5c-141">パブリックプレビューの場合、Azure を使用することで DKE を簡単に展開できます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-141">For public preview, using Azure is a quick way to deploy DKE.</span></span> <span data-ttu-id="8cf5c-142">Azure に展開すると、すぐに二重キー暗号化を使い始めることができます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-142">Deploying to Azure lets you get started using Double Key Encryption right away.</span></span>

<span data-ttu-id="8cf5c-143">ネットワーク上または別のプロバイダーを使用して、サービスをローカルに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-143">You can deploy the service locally on your network or with another provider.</span></span> <span data-ttu-id="8cf5c-144">キーストアは、その場所に適したメソッドを使用して公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-144">You'll need to publish the key store using methods that are appropriate for that location.</span></span>

## <a name="deploy-double-key-encryption"></a><span data-ttu-id="8cf5c-145">二重キー暗号化の展開</span><span class="sxs-lookup"><span data-stu-id="8cf5c-145">Deploy Double Key Encryption</span></span>

<span data-ttu-id="8cf5c-146">この記事と展開ビデオでは、DKE サービスの展開先として Azure を使用します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-146">This article and the deployment video use Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="8cf5c-147">別の場所に展開している場合は、独自の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-147">If you're deploying to another location, you'll need to provide your own values.</span></span>

<span data-ttu-id="8cf5c-148">この記事で説明する概念の詳細な手順については、「 [二重キー暗号化展開ビデオ](https://youtu.be/vDWfHN_kygg) 」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-148">Watch the [Double Key Encryption deployment video](https://youtu.be/vDWfHN_kygg) to see step-by-step overview of concepts in the article.</span></span> <span data-ttu-id="8cf5c-149">ビデオの完了に約18分かかります。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-149">The video takes about 18 minutes to complete.</span></span>

<span data-ttu-id="8cf5c-150">次の一般的な手順に従って、組織のために二重キー暗号化を設定します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-150">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span>

1. [<span data-ttu-id="8cf5c-151">必要なソフトウェアをインストールする</span><span class="sxs-lookup"><span data-stu-id="8cf5c-151">Install software prerequisites</span></span>](#install-software-prerequisites)
1. [<span data-ttu-id="8cf5c-152">二重キー暗号化 GitHub リポジトリのクローンを作成する</span><span class="sxs-lookup"><span data-stu-id="8cf5c-152">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="8cf5c-153">アプリケーションの設定を変更する</span><span class="sxs-lookup"><span data-stu-id="8cf5c-153">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="8cf5c-154">テストキーを生成する</span><span class="sxs-lookup"><span data-stu-id="8cf5c-154">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="8cf5c-155">プロジェクトをビルドする</span><span class="sxs-lookup"><span data-stu-id="8cf5c-155">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="8cf5c-156">キーストアを発行する</span><span class="sxs-lookup"><span data-stu-id="8cf5c-156">Publish the key store</span></span>](#publish-the-key-store)
1. [<span data-ttu-id="8cf5c-157">展開を検証する</span><span class="sxs-lookup"><span data-stu-id="8cf5c-157">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="8cf5c-158">キーストアを登録する</span><span class="sxs-lookup"><span data-stu-id="8cf5c-158">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="8cf5c-159">秘密度ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="8cf5c-159">Create sensitivity labels</span></span>](#create-labels-using-dke)

<span data-ttu-id="8cf5c-160">完了すると、DKE を使用してドキュメントやファイルを暗号化できます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-160">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="8cf5c-161">詳細については、「 [Office のファイルと電子メールに機密ラベルを適用する](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-161">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites"></a><span data-ttu-id="8cf5c-162">必要なソフトウェアをインストールする</span><span class="sxs-lookup"><span data-stu-id="8cf5c-162">Install software prerequisites</span></span>

<span data-ttu-id="8cf5c-163">二重キー暗号化の前提条件となるソフトウェアは2種類あります。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-163">There are two types of software prerequisites for Double Key Encryption</span></span>

- [<span data-ttu-id="8cf5c-164">二重キー暗号化サービスの前提条件</span><span class="sxs-lookup"><span data-stu-id="8cf5c-164">Double Key Encryption service prerequisites</span></span>](#double-key-encryption-service-prerequisites)
- [<span data-ttu-id="8cf5c-165">クライアントコンピューターの二重キー暗号化の前提条件</span><span class="sxs-lookup"><span data-stu-id="8cf5c-165">Double Key Encryption prerequisites for client computers</span></span>](#double-key-encryption-prerequisites-for-client-computers)

#### <a name="double-key-encryption-service-prerequisites"></a><span data-ttu-id="8cf5c-166">二重キー暗号化サービスの前提条件</span><span class="sxs-lookup"><span data-stu-id="8cf5c-166">Double Key Encryption service prerequisites</span></span>

<span data-ttu-id="8cf5c-167">これらの必須コンポーネントを、DKE サービスをインストールするコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-167">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="8cf5c-168">**.Net Core 3.1 SDK**。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-168">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="8cf5c-169">SDK をダウンロードしてインストールします。 [.Net Core 3.1 をダウンロード](https://dotnet.microsoft.com/download/dotnet-core/3.1)します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-169">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="8cf5c-170">**Visual Studio Code**。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-170">**Visual Studio Code**.</span></span> <span data-ttu-id="8cf5c-171">から Visual Studio コードをダウンロード [https://code.visualstudio.com/](https://code.visualstudio.com) します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-171">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="8cf5c-172">インストールされたら、Visual Studio Code を実行し、[**ビュー**拡張] を選択し \> **Extensions**ます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-172">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="8cf5c-173">これらの拡張機能をインストールします。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-173">Install these extensions.</span></span>

- <span data-ttu-id="8cf5c-174">Visual Studio Code の C#</span><span class="sxs-lookup"><span data-stu-id="8cf5c-174">C# for Visual Studio Code</span></span>

- <span data-ttu-id="8cf5c-175">NuGet パッケージマネージャー</span><span class="sxs-lookup"><span data-stu-id="8cf5c-175">NuGet Package Manager</span></span>

<span data-ttu-id="8cf5c-176">**Microsoft Office Insider**。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-176">**Microsoft Office Insider**.</span></span> <span data-ttu-id="8cf5c-177">少なくとも1つの [展開方法](https://insider.office.com/business/deploy)を設定します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-177">Set up at least one [deployment method](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="8cf5c-178">**Git リソース**。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-178">**Git resources**.</span></span> <span data-ttu-id="8cf5c-179">次のいずれかをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-179">Download and install one of the following.</span></span>

- [<span data-ttu-id="8cf5c-180">Git</span><span class="sxs-lookup"><span data-stu-id="8cf5c-180">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="8cf5c-181">GitHub デスクトップ</span><span class="sxs-lookup"><span data-stu-id="8cf5c-181">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="8cf5c-182">GitHub Enterprise</span><span class="sxs-lookup"><span data-stu-id="8cf5c-182">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="8cf5c-183">**OpenSSL**DKE の展開後に[テストキーを生成](#generate-test-keys)するには、 [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html)がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-183">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="8cf5c-184">環境変数のパスから適切に呼び出していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-184">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="8cf5c-185">たとえば、詳細については、「」の「インストールディレクトリをパスに追加する」を参照してください https://www.osradar.com/install-openssl-windows/ 。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-185">For example, see "Add the installation directory to PATH" at https://www.osradar.com/install-openssl-windows/ for details.</span></span>

#### <a name="double-key-encryption-prerequisites-for-client-computers"></a><span data-ttu-id="8cf5c-186">クライアントコンピューターの二重キー暗号化の前提条件</span><span class="sxs-lookup"><span data-stu-id="8cf5c-186">Double Key Encryption prerequisites for client computers</span></span>

<span data-ttu-id="8cf5c-187">保護されたドキュメントを保護して使用する各クライアントコンピューターにこれらの必須コンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-187">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="8cf5c-188">**Microsoft Office** バージョン \* 12711 以降。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-188">**Microsoft Office** version \*.12711 or later.</span></span>

<span data-ttu-id="8cf5c-189">**Azure Information Protection クライアント** バージョン2.7.93.0 またはそれ以降のラベルを統合しています。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-189">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="8cf5c-190">[Microsoft](https://www.microsoft.com/download/details.aspx?id=53018)から統合ラベルクライアントをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-190">Download and install the Unified Labeling client from [Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="8cf5c-191">DKE GitHub リポジトリのクローンを作成する</span><span class="sxs-lookup"><span data-stu-id="8cf5c-191">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="8cf5c-192">Microsoft は、GitHub リポジトリに DKE ソースファイルを提供しています。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-192">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="8cf5c-193">リポジトリを複製して、組織の使用に合わせてプロジェクトをローカルに構築します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-193">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="8cf5c-194">DKE GitHub リポジトリは、にあり [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) ます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-194">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="8cf5c-195">次の手順は、経験のない git または Visual Studio Code ユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-195">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="8cf5c-196">ブラウザーで、次のように移動します。 [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span><span class="sxs-lookup"><span data-stu-id="8cf5c-196">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span></span>

1. <span data-ttu-id="8cf5c-197">画面の右側にある [ **コード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-197">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="8cf5c-198">使用しているバージョンの UI には、[ **クローン] または [ダウンロード** ] ボタンが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-198">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="8cf5c-199">次に、表示されたドロップダウンで、[コピー] アイコンを選択して、URL をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-199">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="8cf5c-200">例:</span><span class="sxs-lookup"><span data-stu-id="8cf5c-200">For example:</span></span>

   ![GitHub から二重キー暗号化サービスリポジトリを複製する](../media/dke-clone.png)

3. <span data-ttu-id="8cf5c-202">Visual Studio Code で、[ **View** \> **Command Palette** ] を選択し、[ **Git: Clone**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-202">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="8cf5c-203">一覧のオプションに移動するには、入力を開始して `git: clone` エントリをフィルター処理し、ドロップダウンから選択します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-203">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="8cf5c-204">例:</span><span class="sxs-lookup"><span data-stu-id="8cf5c-204">For example:</span></span>

   ![Visual Studio Code GIT: Clone オプション](../media/dke-vscode-clone.png)

4. <span data-ttu-id="8cf5c-206">テキストボックスに、Git からコピーした URL を貼り付けて、[ **GitHub から複製**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-206">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="8cf5c-207">表示される **[フォルダーの選択** ] ダイアログで、リポジトリを格納する場所を参照して選択します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-207">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="8cf5c-208">プロンプトで、[ **開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-208">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="8cf5c-209">リポジトリは Visual Studio Code で開かれ、左下に現在の Git ブランチが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-209">The repository is opened in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="8cf5c-210">ブランチは **master**である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-210">The branch should be **master**.</span></span>

    <span data-ttu-id="8cf5c-211">例:</span><span class="sxs-lookup"><span data-stu-id="8cf5c-211">For example:</span></span>

   ![Visual Studio Code master 分岐](../media/dke-vscode-master.png)

6. <span data-ttu-id="8cf5c-213">[単語 **マスター** ] を選択し、分岐の一覧から [ **public_preview** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-213">Select the word **master,** and then select **public_preview** from the list of branches.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="8cf5c-214">Public_preview ブランチを選択すると、プロジェクトをビルドするための適切なファイルがあることが確認されます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-214">Selecting the public_preview branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="8cf5c-215">適切なブランチを選択しない場合、展開は失敗します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-215">If you do not choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="8cf5c-216">これで、DKE ソースリポジトリがローカルに設定されました。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-216">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="8cf5c-217">次に、組織の [アプリケーション設定を変更](#modify-application-settings) します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-217">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="8cf5c-218">アプリケーションの設定を変更する</span><span class="sxs-lookup"><span data-stu-id="8cf5c-218">Modify application settings</span></span>

<span data-ttu-id="8cf5c-219">DKE サービスを展開するには、次の種類のアプリケーション設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-219">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="8cf5c-220">キーアクセス設定</span><span class="sxs-lookup"><span data-stu-id="8cf5c-220">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="8cf5c-221">テナントとキーの設定</span><span class="sxs-lookup"><span data-stu-id="8cf5c-221">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="8cf5c-222">[ファイル] の appsettings.jsで、アプリケーションの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-222">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="8cf5c-223">このファイルは、DoubleKeyEncryptionService\src\customer-key-store. でローカルに複製した DoubleKeyEncryptionService リポジトリにあります。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-223">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="8cf5c-224">たとえば、次の図に示すように、Visual Studio Code でファイルを参照できます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-224">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

![DKE のファイルの appsettings.jsを検索します。](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a><span data-ttu-id="8cf5c-226">キーアクセス設定</span><span class="sxs-lookup"><span data-stu-id="8cf5c-226">Key access settings</span></span>

<span data-ttu-id="8cf5c-227">メールまたはロールの承認を使用するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-227">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="8cf5c-228">DKE は、一度に1つの認証方法のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-228">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="8cf5c-229">**電子メールの承認**。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-229">**Email authorization**.</span></span> <span data-ttu-id="8cf5c-230">組織は、電子メールアドレスのみに基づいてキーへのアクセスを承認できます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-230">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="8cf5c-231">**役割の承認**。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-231">**Role authorization**.</span></span> <span data-ttu-id="8cf5c-232">組織は、Active Directory グループに基づいてキーへのアクセスを承認でき、web サービスが LDAP を照会できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-232">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="8cf5c-233">**電子メール認証を使用して DKE のキーアクセス設定を設定するには**</span><span class="sxs-lookup"><span data-stu-id="8cf5c-233">**To set key access settings for DKE using email authorization**</span></span>

1. <span data-ttu-id="8cf5c-234">ファイル \*\* でappsettings.js\*\* を開き、設定を探し `AuthorizedEmailAddress` ます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-234">Open the **appsettings.json** file and locate the `AuthorizedEmailAddress` setting.</span></span>

2. <span data-ttu-id="8cf5c-235">承認するメールアドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-235">Add the email address or addresses that you want to authorize.</span></span> <span data-ttu-id="8cf5c-236">複数の電子メールアドレスは、二重引用符とコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-236">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="8cf5c-237">例:</span><span class="sxs-lookup"><span data-stu-id="8cf5c-237">For example:</span></span>

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. <span data-ttu-id="8cf5c-238">設定を検索 `LDAPPath` し、 `If role authorization is used then this is the LDAP path` 二重引用符の間のテキストを削除します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-238">Locate the `LDAPPath` setting and remove the text `If role authorization is used then this is the LDAP path` between the double quotes.</span></span> <span data-ttu-id="8cf5c-239">二重引用符はそのままにします。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-239">Leave the double quotes in place.</span></span> <span data-ttu-id="8cf5c-240">完了すると、設定は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-240">When you're finished, the setting should look like this.</span></span>

   ```json
   "LDAPPath": ""
   ```

4. <span data-ttu-id="8cf5c-241">設定を検索 `AuthorizedRoles` し、行全体を削除します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-241">Locate the `AuthorizedRoles` setting and delete the entire line.</span></span>

<span data-ttu-id="8cf5c-242">このイメージは、電子メールの承認用に正しく書式設定されたファイル \*\* のappsettings.js\*\* を示しています。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-242">This image shows the **appsettings.json** file correctly formatted for email authorization.</span></span>

   ![電子メール認証方法が表示されているファイルの appsettings.js](../media/dke-email-accesssetting.png)

<span data-ttu-id="8cf5c-244">**ロール認証を使用して DKE のキーアクセス設定を設定するには**</span><span class="sxs-lookup"><span data-stu-id="8cf5c-244">**To set key access settings for DKE using role authorization**</span></span>

1. <span data-ttu-id="8cf5c-245">ファイル \*\* でappsettings.js\*\* を開き、設定を探し `AuthorizedRoles` ます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-245">Open the **appsettings.json** file and locate the `AuthorizedRoles` setting.</span></span>

2. <span data-ttu-id="8cf5c-246">承認する Active Directory グループ名を追加します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-246">Add the Active Directory group names you want to authorize.</span></span> <span data-ttu-id="8cf5c-247">複数のグループ名は、二重引用符とコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-247">Separate multiple group names with double quotes and commas.</span></span> <span data-ttu-id="8cf5c-248">例:</span><span class="sxs-lookup"><span data-stu-id="8cf5c-248">For example:</span></span>

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. <span data-ttu-id="8cf5c-249">`LDAPPath`設定を見つけて、Active Directory ドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-249">Locate the `LDAPPath` setting and add the Active Directory domain.</span></span> <span data-ttu-id="8cf5c-250">例:</span><span class="sxs-lookup"><span data-stu-id="8cf5c-250">For example:</span></span>

   ```json
   "LDAPPath": "contoso.com"
   ```

4. <span data-ttu-id="8cf5c-251">設定を検索 `AuthorizedEmailAddress` し、行全体を削除します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-251">Locate the `AuthorizedEmailAddress` setting and delete the entire line.</span></span>

<span data-ttu-id="8cf5c-252">このイメージは、役割承認用に正しく書式設定されたファイル \*\* のappsettings.js\*\* を示しています。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-252">This image shows the **appsettings.json** file correctly formatted for role authorization.</span></span>

   ![ロール認証方法が表示されているファイルの appsettings.js](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="8cf5c-254">テナントとキーの設定</span><span class="sxs-lookup"><span data-stu-id="8cf5c-254">Tenant and key settings</span></span>

<span data-ttu-id="8cf5c-255">DKE テナントとキー設定は、ファイルの **appsettings.js** にあります。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-255">DKE tenant and key settings are located in the **appsettings.json** file.</span></span>

<span data-ttu-id="8cf5c-256">**DKE のテナントとキー設定を構成するには**</span><span class="sxs-lookup"><span data-stu-id="8cf5c-256">**To configure tenant and key settings for DKE**</span></span>

1. <span data-ttu-id="8cf5c-257">ファイル \*\* でappsettings.js\*\* を開きます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-257">Open the **appsettings.json** file.</span></span>

2. <span data-ttu-id="8cf5c-258">`ValidIssuers`設定を見つけて、 `<tenantid>` テナント ID に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-258">Locate the `ValidIssuers` setting and replace `<tenantid>` with your tenant ID.</span></span> <span data-ttu-id="8cf5c-259">Azure ポータルに移動して、 [テナントのプロパティ](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)を表示することによって、テナント ID を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-259">You can locate your tenant ID by going to the Azure portal and viewing the [tenant properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="8cf5c-260">例:</span><span class="sxs-lookup"><span data-stu-id="8cf5c-260">For example:</span></span>

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

<span data-ttu-id="8cf5c-261">を探し `JwtAudience` ます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-261">Locate the `JwtAudience`.</span></span> <span data-ttu-id="8cf5c-262">を、 `<yourhostname>` DKE サービスが実行されるコンピューターのホスト名に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-262">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span> <span data-ttu-id="8cf5c-263">例:</span><span class="sxs-lookup"><span data-stu-id="8cf5c-263">For example:</span></span>



  > [!IMPORTANT]
  > <span data-ttu-id="8cf5c-264">の値は、 `JwtAudience` ホストの名前と *正確*に一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-264">The value for `JwtAudience` must match the name of your host *exactly*.</span></span> <span data-ttu-id="8cf5c-265">デバッグ中に **localhost: 5001** を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-265">You may use **localhost:5001** while debugging.</span></span> <span data-ttu-id="8cf5c-266">ただし、デバッグを完了したら、この値をサーバーのホスト名に更新するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-266">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="8cf5c-267">`TestKeys:Name`.</span><span class="sxs-lookup"><span data-stu-id="8cf5c-267">`TestKeys:Name`.</span></span> <span data-ttu-id="8cf5c-268">キーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-268">Enter a name for your key.</span></span> <span data-ttu-id="8cf5c-269">例: `TestKey1`</span><span class="sxs-lookup"><span data-stu-id="8cf5c-269">For example: `TestKey1`</span></span>
- <span data-ttu-id="8cf5c-270">`TestKeys:Id`.</span><span class="sxs-lookup"><span data-stu-id="8cf5c-270">`TestKeys:Id`.</span></span> <span data-ttu-id="8cf5c-271">GUID を作成し、値として入力し `TestKeys:ID` ます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-271">Create a GUID and enter it as the `TestKeys:ID` value.</span></span> <span data-ttu-id="8cf5c-272">たとえば、`DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE` などです。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-272">For example, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span></span> <span data-ttu-id="8cf5c-273">[ONLINE Guid ジェネレーター](https://guidgenerator.com/)のようなサイトを使用して、guid をランダムに生成することができます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-273">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

<span data-ttu-id="8cf5c-274">この画像 \*\* にはappsettings.js\*\*のテナントとキーの設定の正しい形式が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-274">This image shows the correct format for tenant and keys settings in **appsettings.json**.</span></span> <span data-ttu-id="8cf5c-275">`LDAPPath` は、ロールの承認のために構成されています。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-275">`LDAPPath` is configured for role authorization.</span></span>

![ファイルの appsettings.jsの DKE の正しいテナントとキー設定を示します。](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a><span data-ttu-id="8cf5c-277">テストキーを生成する</span><span class="sxs-lookup"><span data-stu-id="8cf5c-277">Generate test keys</span></span>

<span data-ttu-id="8cf5c-278">アプリケーション設定を定義したら、パブリックおよびプライベートのテストキーを生成する準備ができています。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-278">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="8cf5c-279">キーを生成するには</span><span class="sxs-lookup"><span data-stu-id="8cf5c-279">To generate keys:</span></span>

1. <span data-ttu-id="8cf5c-280">Windows の [スタート] メニューから、OpenSSL コマンドプロンプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-280">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

1. <span data-ttu-id="8cf5c-281">テストキーを保存するフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-281">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="8cf5c-282">このタスクの手順を完了することによって作成したファイルは、同じフォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-282">The files you create by completing the steps in this task are stored in the same folder.</span></span>

1. <span data-ttu-id="8cf5c-283">新しいテストキーを生成します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-283">Generate the new test key.</span></span>

   ```dos
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

2. <span data-ttu-id="8cf5c-284">秘密キーを生成します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-284">Generate the private key.</span></span>

   ```dos
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

1. <span data-ttu-id="8cf5c-285">公開キーを生成します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-285">Generate the public key.</span></span>

   ```dos
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

1. <span data-ttu-id="8cf5c-286">テキストエディターで、 **pubkeyonly**を開きます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-286">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="8cf5c-287">最初と最後の行を除く、 **pubkeyonly** のすべてのコンテンツを `PublicPem` ファイルの **appsettings.js** のセクションにコピーします。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-287">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the `PublicPem` section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="8cf5c-288">テキストエディターで、 **privkeynopass pem**を開きます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-288">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="8cf5c-289">最初の行と最後の行を除いて、 **privkeynopass** のすべてのコンテンツを `PrivatePem` ファイルの **appsettings.js** のセクションにコピーします。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-289">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the `PrivatePem` section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="8cf5c-290">セクションとセクションの両方で空白スペースと改行を削除し `PublicPem` `PrivatePem` ます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-290">Remove all blank spaces and newlines in both the `PublicPem` and `PrivatePem` sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="8cf5c-291">このコンテンツをコピーする場合は、PEM データを削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-291">When you copy this content, do not delete any of the PEM data.</span></span>

1. <span data-ttu-id="8cf5c-292">Visual Studio Code で、 **Startup.cs** ファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-292">In Visual Studio Code, browse to the **Startup.cs** file.</span></span> <span data-ttu-id="8cf5c-293">このファイルは、DoubleKeyEncryptionService\src\customer-key-store\. でローカルに複製した DoubleKeyEncryptionService リポジトリにあります。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-293">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store\.</span></span>

2. <span data-ttu-id="8cf5c-294">次の行を見つけます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-294">Locate the following lines:</span></span>

   ```c#
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE  FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
   ```

3. <span data-ttu-id="8cf5c-295">これらの行を次のテキストに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-295">Replace these lines with the following text:</span></span>

   ```csharp
   services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
   ```

   <span data-ttu-id="8cf5c-296">最終結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-296">The end results should look similar to the following.</span></span>

   ![パブリックプレビュー用の startup.cs ファイル](../media/dke-startupcs-usetestkeys.png)

<span data-ttu-id="8cf5c-298">これで [、DKE プロジェクトを構築](#build-the-project)する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-298">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="8cf5c-299">プロジェクトをビルドする</span><span class="sxs-lookup"><span data-stu-id="8cf5c-299">Build the project</span></span>

<span data-ttu-id="8cf5c-300">次の手順を使用して、ローカルに DKE プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-300">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="8cf5c-301">Visual Studio Code の dke サービスリポジトリで、[コマンドパレットの**表示**] を選択し、 \> **Command Palette**プロンプトで「 **build** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-301">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

1. <span data-ttu-id="8cf5c-302">リストから、[ **タスク: ビルドタスクの実行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-302">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="8cf5c-303">ビルドタスクが見つからない場合は、[ **ビルドタスクの構成** ] を選択し、次のように .net コア用のタスクを作成します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-303">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   ![.NET の不明なビルドタスクを構成する](../media/dke-configurebuildtask.png)

   1. <span data-ttu-id="8cf5c-305">[ **テンプレートから tasks.jsを作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-305">Choose **Create tasks.json from template**.</span></span>

   ![DKE テンプレートからファイルに tasks.jsを作成する](../media/dke-createtasksjsonfromtemplate.png)

   2. <span data-ttu-id="8cf5c-307">テンプレートの種類の一覧から [ **.Net Core**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-307">From the list of template types, select **.NET Core**.</span></span>

   ![DKE テンプレートからファイルに tasks.jsを作成する](../media/dke-tasksjsontemplate.png)

   3. <span data-ttu-id="8cf5c-309">[ビルド] セクションで、 **顧客キーストア** ファイルへのパスを見つけます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-309">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="8cf5c-310">存在しない場合は、次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-310">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

  4. <span data-ttu-id="8cf5c-311">ビルドを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-311">Run the build again.</span></span>

1. <span data-ttu-id="8cf5c-312">出力ウィンドウに赤のエラーが表示されないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-312">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="8cf5c-313">赤のエラーがある場合は、コンソール出力を確認します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-313">If there are red errors, check the console output.</span></span> <span data-ttu-id="8cf5c-314">上記の手順がすべて正常に完了し、適切なビルドバージョンが存在することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-314">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

2. <span data-ttu-id="8cf5c-315">[ **実行** \> **開始デバッグ** ] を選択してプロセスをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-315">Select **Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="8cf5c-316">環境を選択するように求めるメッセージが表示されたら、[ **.net core**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-316">If you're prompted to select an environment, select **.NET core**.</span></span>

<span data-ttu-id="8cf5c-317">通常、.net コアデバッガーは ' ' ' に起動 https://localhost:5001 `. To view your test key, go to ` https://localhost:5001 し、スラッシュ (/) とキーの名前を追加します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-317">The .NET core debugger typically launches to \`\`https://localhost:5001`. To view your test key, go to `https://localhost:5001\` and append a forward slash (/) and the name of your key.</span></span> <span data-ttu-id="8cf5c-318">例:</span><span class="sxs-lookup"><span data-stu-id="8cf5c-318">For example:</span></span>

```https
https://localhost:5001/TestKey1
```

<span data-ttu-id="8cf5c-319">キーは JSON 形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-319">The key should display in JSON format.</span></span>

<span data-ttu-id="8cf5c-320">セットアップが完了しました。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-320">Your setup is now complete.</span></span> <span data-ttu-id="8cf5c-321">キーストアを発行する前に、JwtAudience の設定 appsettings.jsで、[] 設定で、[ホスト名] の値が App Service ホスト名と正確に一致していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-321">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="8cf5c-322">ビルドのトラブルシューティングを行うために、localhost に変更した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-322">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="publish-the-key-store"></a><span data-ttu-id="8cf5c-323">キーストアを発行する</span><span class="sxs-lookup"><span data-stu-id="8cf5c-323">Publish the key store</span></span>

<span data-ttu-id="8cf5c-324">キーストアを発行するには、DKE 展開をホストする Azure App Service インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-324">To publish the key store, you'll create an Azure App Service instance to host your DKE deployment.</span></span> <span data-ttu-id="8cf5c-325">次に、生成されたキーを Azure に発行します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-325">Next, you'll publish your generated keys to Azure.</span></span>

<span data-ttu-id="8cf5c-326">**DKE 展開をホストするための Azure Web App インスタンスを作成するには**</span><span class="sxs-lookup"><span data-stu-id="8cf5c-326">**To create an Azure Web App instance to host your DKE deployment**</span></span>

1. <span data-ttu-id="8cf5c-327">ブラウザーで、 [Microsoft Azure ポータル](https://ms.portal.azure.com)にサインインし、[ **App Services**追加] に移動し  >  **Add**ます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-327">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

1. <span data-ttu-id="8cf5c-328">サブスクリプションとリソースグループを選択し、インスタンスの詳細を定義します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-328">Select your subscription and resource group and define your instance details.</span></span>

    - <span data-ttu-id="8cf5c-329">DKE サービスをインストールするコンピューターのホスト名を入力します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-329">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="8cf5c-330">[ファイルのappsettings.js] の [\*\* [\*\*](#tenant-and-key-settings) JwtAudience] 設定に定義されている名前と同じ名前であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-330">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="8cf5c-331">名前に指定する値は WebAppInstanceName でもあります。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-331">The value you provide for the name is also the WebAppInstanceName.</span></span>

    - <span data-ttu-id="8cf5c-332">[ **発行**] で、[ **コード**] を選択し、[ **ランタイムスタック**] で [ **.net Core 3.1**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-332">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

    <span data-ttu-id="8cf5c-333">例:</span><span class="sxs-lookup"><span data-stu-id="8cf5c-333">For example:</span></span>

   ![アプリサービスを追加する](../media/dke-azure-add-app-service.png)

1. <span data-ttu-id="8cf5c-335">ページの下部にある [ **レビュー + 作成**] を選択し、[ **追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-335">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

1. <span data-ttu-id="8cf5c-336">生成されたキーを Azure に公開するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-336">Do one of the following to publish your generated keys to Azure:</span></span>

    - [<span data-ttu-id="8cf5c-337">ZipDeployUI を使用して発行する</span><span class="sxs-lookup"><span data-stu-id="8cf5c-337">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
    - [<span data-ttu-id="8cf5c-338">FTP を使用した発行</span><span class="sxs-lookup"><span data-stu-id="8cf5c-338">Publish via FTP</span></span>](#publish-via-ftp)
    - [<span data-ttu-id="8cf5c-339">Visual Studio 2019 以降での発行</span><span class="sxs-lookup"><span data-stu-id="8cf5c-339">Publish via Visual Studio 2019 or later</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/)
    - [<span data-ttu-id="8cf5c-340">オンプレミスのシステムに発行する</span><span class="sxs-lookup"><span data-stu-id="8cf5c-340">Publish to an on-premises system</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli)

    > [!NOTE]
    > <span data-ttu-id="8cf5c-341">他の方法でキーを展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-341">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="8cf5c-342">組織に最も適した方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-342">Select the method that works best for your organization.</span></span>

    > [!TIP]
    > <span data-ttu-id="8cf5c-343">[Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/) と [オンプレミスシステム](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) への発行については、 [ASP .net ドキュメント](https://docs.microsoft.com/aspnet/core/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-343">[Publishing via Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/) and to an [on-premises system](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) is described in the [ASP .NET documentation](https://docs.microsoft.com/aspnet/core/).</span></span> <span data-ttu-id="8cf5c-344">これらの方法のいずれかを使用する場合は、操作が完了したら簡単に戻ることができるように、別のタブで手順を開きます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-344">If you use one of these methods, open the instructions in a separate tab so that you can return here easily when you're done.</span></span>

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="8cf5c-345">ZipDeployUI を使用して発行する</span><span class="sxs-lookup"><span data-stu-id="8cf5c-345">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="8cf5c-346">`https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI` に移動します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-346">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

    <span data-ttu-id="8cf5c-347">例: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="8cf5c-347">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

1. <span data-ttu-id="8cf5c-348">キーストアのコードベースで、 **customer-key-store\src\customer-key-store** フォルダーに移動し、このフォルダーに **顧客キーストア** ファイルが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-348">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="8cf5c-349">実行: **dotnet publish**</span><span class="sxs-lookup"><span data-stu-id="8cf5c-349">Run: **dotnet publish**</span></span>

     <span data-ttu-id="8cf5c-350">[出力] ウィンドウには、発行が展開されたディレクトリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-350">The output window displays the directory where the publish was deployed.</span></span>

    <span data-ttu-id="8cf5c-351">例: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="8cf5c-351">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="8cf5c-352">Publish ディレクトリ内のすべてのファイルを .zip ファイルに送信します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-352">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="8cf5c-353">.Zip ファイルを作成するときは、ディレクトリ内のすべてのファイルが .zip ファイルのルートレベルにあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-353">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="8cf5c-354">先ほど開いた ZipDeployUI サイトに、作成した .zip ファイルをドラッグアンドドロップします。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-354">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="8cf5c-355">例: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="8cf5c-355">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="8cf5c-356">DKE が展開されており、作成したテストキーを参照することができます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-356">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="8cf5c-357">引き続き「 [展開を検証](#validate-your-deployment) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-357">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="8cf5c-358">FTP を使用した発行</span><span class="sxs-lookup"><span data-stu-id="8cf5c-358">Publish via FTP</span></span>

1. <span data-ttu-id="8cf5c-359">[上記の手順](#publish-the-key-store)で作成した App Service に接続します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-359">Connect to the App Service you created [above](#publish-the-key-store).</span></span>

    <span data-ttu-id="8cf5c-360">ブラウザーで、「 **Azure portal**  >  **App Service**  >  **Deployment Center**  >  **Manual Deployment**  >  **FTP**  >  **Dashboard**」に移動します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-360">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

1. <span data-ttu-id="8cf5c-361">ローカルファイルに表示される接続文字列をコピーします。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-361">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="8cf5c-362">これらの文字列を使用して Web App サービスに接続し、FTP を使用してファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-362">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

    <span data-ttu-id="8cf5c-363">例:</span><span class="sxs-lookup"><span data-stu-id="8cf5c-363">For example:</span></span>

   ![FTP ダッシュボードから接続文字列をコピーする](../media/dke-ftp-dashboard.png)

1. <span data-ttu-id="8cf5c-365">キーの格納用のコードベースで、 **customer-key-store\src\customer-key-store ディレクトリ**に移動します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-365">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

1. <span data-ttu-id="8cf5c-366">このディレクトリに、 **顧客キーストアの .csproj** ファイルが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-366">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="8cf5c-367">実行: **dotnet publish**</span><span class="sxs-lookup"><span data-stu-id="8cf5c-367">Run: **dotnet publish**</span></span>

    <span data-ttu-id="8cf5c-368">この出力には、発行が展開されたディレクトリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-368">The output contains the directory where the publish was deployed.</span></span>

    <span data-ttu-id="8cf5c-369">例: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="8cf5c-369">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="8cf5c-370">発行ディレクトリ内のすべてのファイルを zip ファイルに送信します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-370">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="8cf5c-371">.Zip ファイルを作成するときは、ディレクトリ内のすべてのファイルが .zip ファイルのルートレベルにあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-371">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="8cf5c-372">FTP クライアントから、コピーした接続情報を使用して App Service に接続します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-372">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="8cf5c-373">前の手順で作成した .zip ファイルを Web アプリのルートディレクトリにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-373">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="8cf5c-374">DKE が展開されており、作成したテストキーを参照することができます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-374">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="8cf5c-375">次に、 [展開を検証](#validate-your-deployment)します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-375">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="8cf5c-376">展開を検証する</span><span class="sxs-lookup"><span data-stu-id="8cf5c-376">Validate your deployment</span></span>

<span data-ttu-id="8cf5c-377">前述の方法のいずれかを使用して DKE を展開した後、展開とキーストアの設定を検証します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-377">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="8cf5c-378">次を実行します:  </span><span class="sxs-lookup"><span data-stu-id="8cf5c-378">Run:</span></span>

<span data-ttu-id="8cf5c-379">src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/mykey</span><span class="sxs-lookup"><span data-stu-id="8cf5c-379">src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/mykey</span></span>

<span data-ttu-id="8cf5c-380">例:</span><span class="sxs-lookup"><span data-stu-id="8cf5c-380">For example:</span></span>

<span data-ttu-id="8cf5c-381">key_store_tester.ps1 https://mycustomerkeystore.com/mykey</span><span class="sxs-lookup"><span data-stu-id="8cf5c-381">key_store_tester.ps1 https://mycustomerkeystore.com/mykey</span></span>

<span data-ttu-id="8cf5c-382">出力にエラーが表示されないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-382">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="8cf5c-383">準備が整ったら、 [キーストアを登録](#register-your-key-store)します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-383">When you're ready, [register your key store](#register-your-key-store).</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="8cf5c-384">キーストアを登録する</span><span class="sxs-lookup"><span data-stu-id="8cf5c-384">Register your key store</span></span>

<span data-ttu-id="8cf5c-385">次の手順を実行すると、キーストアを登録できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-385">The following steps enable you to register your key store.</span></span> <span data-ttu-id="8cf5c-386">ラベルの作成を開始する前に、DKE を展開するための最後の手順として、キーストアの登録が必要になります。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-386">Registering your key store is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="8cf5c-387">キーストアを登録するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-387">To register your key store:</span></span>

1. <span data-ttu-id="8cf5c-388">ブラウザーで、 [Microsoft Azure portal](https://ms.portal.azure.com/)を開き、[ **すべてのサービス** \> **id** \> **アプリの登録**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-388">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="8cf5c-389">[ **新しい登録**] を選択し、わかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-389">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="8cf5c-390">表示されているオプションから、アカウントの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-390">Select an account type from the options displayed.</span></span>

    <span data-ttu-id="8cf5c-391">**Onmicrosoft.com**などの非ユーザー設定ドメインを使用して Microsoft Azure を使用している場合は、[**この組織ディレクトリ内のアカウントのみ (microsoft のみ)** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-391">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

    <span data-ttu-id="8cf5c-392">例:</span><span class="sxs-lookup"><span data-stu-id="8cf5c-392">For example:</span></span>

   ![新しいアプリの登録](../media/dke-app-registration.png)

4. <span data-ttu-id="8cf5c-394">ページの下部にある [ **登録** ] を選択して、新しいアプリの登録を作成します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-394">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="8cf5c-395">新しいアプリの登録で、左側のウィンドウの [ **管理**] で [ **認証**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-395">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="8cf5c-396">[ **プラットフォームの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-396">Select **Add a platform**.</span></span>
 
7. <span data-ttu-id="8cf5c-397">[ **プラットフォームの構成** ] ポップアップで、[ **Web**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-397">On the **Configure platforms** popup, select **Web**.</span></span>
 
8. <span data-ttu-id="8cf5c-398">[ **リダイレクト uri**] で、二重キー暗号化サービスの URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-398">Under **Redirect URIs**, enter the URI of your double key encryption service.</span></span> <span data-ttu-id="8cf5c-399">ホスト名とドメインの両方を含む、App Service の URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-399">Enter the App Service URL, including both the hostname and domain.</span></span>

    <span data-ttu-id="8cf5c-400">例: https://mycustomerkeystoretest.com</span><span class="sxs-lookup"><span data-stu-id="8cf5c-400">For example: https://mycustomerkeystoretest.com</span></span>

    - <span data-ttu-id="8cf5c-401">入力する URL は、キーストアが展開されているホスト名と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-401">The URL you enter must match the hostname where your key store is deployed.</span></span>
    - <span data-ttu-id="8cf5c-402">Visual Studio を使用してローカルでテストしている場合は、を使用 **https://localhost:5001** します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-402">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
    - <span data-ttu-id="8cf5c-403">すべての場合において、スキームは **https**である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-403">In all cases, the scheme must be **https**.</span></span>

    <span data-ttu-id="8cf5c-404">ホスト名が App Service ホスト名と正確に一致していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-404">Ensure the hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="8cf5c-405">ビルドをトラブルシューティングするために、に変更した可能性があり `localhost` ます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-405">You may have changed it to `localhost` to troubleshoot the build.</span></span> <span data-ttu-id="8cf5c-406">**appsettings.js**の場合、この値は、に設定したホスト名です `JwtAudience` 。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-406">In **appsettings.json**, this value is the hostname you set for `JwtAudience`.</span></span>

6. <span data-ttu-id="8cf5c-407">[ **暗黙的な付与**] で、[ **ID トークン** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-407">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

1. <span data-ttu-id="8cf5c-408">**[保存]** を選択し、変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-408">Select **Save** to save your changes.</span></span>

7. <span data-ttu-id="8cf5c-409">左側のウィンドウで、[ **API の公開**] を選択し、[アプリケーション ID URI] の横にある [ **設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-409">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

9. <span data-ttu-id="8cf5c-410">引き続き [ **api の公開** ] ページで、[ **この api によって定義されるスコープ** ] 領域の [ **範囲の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-410">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="8cf5c-411">新しい範囲の場合:</span><span class="sxs-lookup"><span data-stu-id="8cf5c-411">In the new scope:</span></span>

    1. <span data-ttu-id="8cf5c-412">スコープ名を **user_impersonation**として定義します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-412">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="8cf5c-413">同意できる管理者とユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-413">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="8cf5c-414">残りの必要な値を定義します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-414">Define any remaining values required.</span></span>

    4. <span data-ttu-id="8cf5c-415">[**スコープの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-415">Select **Add scope.**</span></span>

    <span data-ttu-id="8cf5c-416">上部にある [ **保存** ] を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-416">Select **Save** at the top to save your changes.</span></span>

10. <span data-ttu-id="8cf5c-417">引き続き [ **API の公開** ] ページの [承認された **クライアントアプリケーション** ] 領域で、[ **クライアントアプリケーションの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-417">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="8cf5c-418">新しいクライアントアプリケーションの場合:</span><span class="sxs-lookup"><span data-stu-id="8cf5c-418">In the new client application:</span></span>

    1. <span data-ttu-id="8cf5c-419">クライアント ID を **d3590ed6-52b3-4102-aeff-aad2292ab01c**として定義します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-419">Define the Client ID as **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span></span> <span data-ttu-id="8cf5c-420">この値は Microsoft Office クライアント ID であり、Office はキーストアのアクセストークンを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-420">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="8cf5c-421">[ **承認**されたスコープ] で、 **user_impersonation** スコープを選択します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-421">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="8cf5c-422">**[アプリケーションの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-422">Select **Add application**.</span></span>

    4. <span data-ttu-id="8cf5c-423">上部にある [ **保存** ] を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-423">Select **Save** at the top to save your changes.</span></span>

<span data-ttu-id="8cf5c-424">これで、DKE キーストアが登録されました。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-424">Your DKE key store is now registered.</span></span> <span data-ttu-id="8cf5c-425">引き続き、 [DKE を使用してラベルを作成](#create-labels-using-dke)します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-425">Continue by [creating labels using DKE](#create-labels-using-dke).</span></span>

## <a name="create-labels-using-dke"></a><span data-ttu-id="8cf5c-426">DKE を使用してラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="8cf5c-426">Create labels using DKE</span></span>

<span data-ttu-id="8cf5c-427">Microsoft 365 コンプライアンスセンターで、別の方法として、新しい機密ラベルを作成し、暗号化を適用します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-427">In the Microsoft 365 compliance center, create a new sensitivity label and apply encryption as you would otherwise.</span></span> <span data-ttu-id="8cf5c-428">[ **2 重のキー暗号化を使用する** ] を選択し、キーのエンドポイント URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-428">Select **Use Double Key Encryption** and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="8cf5c-429">例:</span><span class="sxs-lookup"><span data-stu-id="8cf5c-429">For example:</span></span>

![Microsoft 365 コンプライアンスセンターで [二重のキー暗号化を使用する] を選択します。](../media/dke-use-dke.png)

<span data-ttu-id="8cf5c-431">追加した DKE ラベルは、Microsoft 365 Apps for enterprise の最新バージョンのユーザーに対して表示され始めます。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-431">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="8cf5c-432">クライアントが新しいラベルで更新されるまで、最大24時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-432">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="8cf5c-433">クライアントで DKE を有効にする</span><span class="sxs-lookup"><span data-stu-id="8cf5c-433">Enable DKE in your client</span></span>

<span data-ttu-id="8cf5c-434">次のレジストリキーを追加して、クライアントに対して DKE を有効にします。</span><span class="sxs-lookup"><span data-stu-id="8cf5c-434">Enable DKE for your client by adding the following registry keys:</span></span>

```properties
    [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001
```
