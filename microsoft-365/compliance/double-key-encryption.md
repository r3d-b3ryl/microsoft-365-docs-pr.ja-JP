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
ms.openlocfilehash: 47fc4bc47831970ef7a7f2087cf6c86b6fefb8c2
ms.sourcegitcommit: fe20f5ed07f38786c63df0f73659ca472e69e478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "45201727"
---
# <a name="double-key-encryption-dke"></a><span data-ttu-id="9651d-103">二重キー暗号化 (DKE)</span><span class="sxs-lookup"><span data-stu-id="9651d-103">Double Key Encryption (DKE)</span></span>

> <span data-ttu-id="9651d-104">*適用対象: [Microsoft 365 コンプライアンス](https://www.microsoft.com/microsoft-365/business/compliance-management)、 [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span><span class="sxs-lookup"><span data-stu-id="9651d-104">*Applies to: [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="9651d-105">*手順: [Azure Information Protection を使用した Windows 用の統一されたラベル付けクライアント](https://docs.microsoft.com/azure/information-protection/faqs.md#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span><span class="sxs-lookup"><span data-stu-id="9651d-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](https://docs.microsoft.com/azure/information-protection/faqs.md#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="9651d-106">*サービスの説明: [Microsoft 365 コンプライアンス](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="9651d-106">*Service description for: [Microsoft 365 Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="9651d-107">このパブリックプレビューバージョンの Double キー暗号化 (DKE) により、Azure Information Protection のユニファイドラベルクライアントを使用して、キーのフルコントロールを維持しながら、機密性の高いコンテンツを保護することができます。</span><span class="sxs-lookup"><span data-stu-id="9651d-107">This public preview version of Double Key Encryption (DKE) enables you to use the Azure Information Protection Unified Labeling Client to protect highly sensitive content while maintaining full control of your key.</span></span>

<span data-ttu-id="9651d-108">二重キー暗号化では、保護されたコンテンツにアクセスするために2つのキーを併用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9651d-108">Double Key Encryption requires two keys, used together, to access protected content.</span></span> <span data-ttu-id="9651d-109">Microsoft Azure には1つのキーを保存し、もう一方のキーは保持します。</span><span class="sxs-lookup"><span data-stu-id="9651d-109">You store one key in Microsoft Azure, and you hold the other key.</span></span>

<span data-ttu-id="9651d-110">二重キー暗号化は、クラウドとオンプレミスの両方の展開をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="9651d-110">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="9651d-111">これらの展開は、保護されたデータを格納する際に、暗号化されたデータが透過的であるようにするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9651d-111">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="9651d-112">既定のクラウドベースのテナントルートキーの詳細については、「 [Azure Information Protection のテナントキーを計画および実装](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9651d-112">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span></span>

<span data-ttu-id="9651d-113">二重キー暗号化は、アクセスを取得するために、銀行キーと顧客キーの両方が必要なセーフティ預入ボックスに似ています。</span><span class="sxs-lookup"><span data-stu-id="9651d-113">Double Key Encryption is similar to a safety deposit box that requires both a bank key and a customer key to gain access.</span></span> <span data-ttu-id="9651d-114">保護されたコンテンツの暗号化を解除するには、Microsoft マネージキーとお客様が管理するキーの両方を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9651d-114">To decrypt protected content, you must use both the Microsoft managed key and the customer-held key.</span></span>

<span data-ttu-id="9651d-115">次のビデオは、二重のキー暗号化がコンテンツをセキュリティで保護するしくみを示しています。</span><span class="sxs-lookup"><span data-stu-id="9651d-115">The following video shows how Double Key Encryption works to secure your content.</span></span>

<span data-ttu-id="9651d-116">組織に次の要件がある場合は、DKE を使用してコンテンツをセキュリティで保護できます。</span><span class="sxs-lookup"><span data-stu-id="9651d-116">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="9651d-117">すべての状況で保護されたコンテンツの暗号化を*解除できるよう*にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9651d-117">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="9651d-118">保護されたデータへのアクセス権を Microsoft に付与しないようにします。</span><span class="sxs-lookup"><span data-stu-id="9651d-118">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="9651d-119">地理的な境界内にキーを保持する規制要件があります。</span><span class="sxs-lookup"><span data-stu-id="9651d-119">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="9651d-120">データの暗号化と復号化に使用するすべてのお客様が開催するキーは、データセンターに保持されます。</span><span class="sxs-lookup"><span data-stu-id="9651d-120">All customer-held keys for data encryption and decryption are maintained in your data center.</span></span>

> [!VIDEO https://msit.microsoftstream.com/embed/video/f466a1ff-0400-a936-221c-f1eab45dc756]

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="9651d-121">DKE のシステムおよびライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="9651d-121">System and licensing requirements for DKE</span></span>

<span data-ttu-id="9651d-122">このパブリックプレビューリリースでは、Microsoft 365 に対する二重キー暗号化が、Microsoft 365 E5 および Office 365 E5 の一部として提供されています。</span><span class="sxs-lookup"><span data-stu-id="9651d-122">This public preview release of Double Key Encryption for Microsoft 365 is available as part of Microsoft 365 E5 and Office 365 E5.</span></span> <span data-ttu-id="9651d-123">Microsoft 365 E5 ライセンスを持っていない場合は、[試用版](https://aka.ms/M365E5ComplianceTrial)にサインアップできます。</span><span class="sxs-lookup"><span data-stu-id="9651d-123">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="9651d-124">これらのライセンスの詳細については、「 [Microsoft 365 licensing ガイダンス for security & 法令遵守](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9651d-124">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="9651d-125">**Office Insider**パブリックプレビューを使用するには、Office Insider プログラムのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9651d-125">**Office Insider** To use the public preview, you must be a member of the Office Insider program.</span></span> <span data-ttu-id="9651d-126">Office Insider に参加するには、にアクセス [https://insider.office.com](https://insider.office.com) してください。</span><span class="sxs-lookup"><span data-stu-id="9651d-126">To join Office Insider, go to [https://insider.office.com](https://insider.office.com).</span></span> <span data-ttu-id="9651d-127">メンバーになったら、組織に適した展開方法を選択して、Office Insider ビルドを展開するための環境を準備します。</span><span class="sxs-lookup"><span data-stu-id="9651d-127">Once you're a member, prepare your environment to deploy Office Insider builds by choosing the right deployment method for your organization.</span></span> <span data-ttu-id="9651d-128">手順については、「 [Office Insider ビルドの展開の](https://insider.office.com/business/deploy)概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9651d-128">For instructions, see [Getting started on deploying Office Insider builds](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="9651d-129">**Azure Information Protection**。</span><span class="sxs-lookup"><span data-stu-id="9651d-129">**Azure Information Protection**.</span></span> <span data-ttu-id="9651d-130">DKE は機密ラベルを使用し、Azure Information Protection を必要とします。</span><span class="sxs-lookup"><span data-stu-id="9651d-130">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="9651d-131">DKE で保護されたコンテンツを保存および表示するためにサポートされている環境</span><span class="sxs-lookup"><span data-stu-id="9651d-131">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="9651d-132">**サポートされるアプリケーション**。</span><span class="sxs-lookup"><span data-stu-id="9651d-132">**Supported applications**.</span></span> <span data-ttu-id="9651d-133">Word、Excel、PowerPoint など、Windows の[エンタープライズクライアント用の Microsoft 365 アプリ](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product)。</span><span class="sxs-lookup"><span data-stu-id="9651d-133">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="9651d-134">**オンラインコンテンツのサポート**。</span><span class="sxs-lookup"><span data-stu-id="9651d-134">**Online content support**.</span></span> <span data-ttu-id="9651d-135">Microsoft SharePoint と OneDrive for business の両方でオンラインで格納されたドキュメントやファイルはサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9651d-135">Documents and files stored online in both Microsoft SharePoint and OneDrive for Business are supported.</span></span> <span data-ttu-id="9651d-136">暗号化されたコンテンツを電子メールで共有することはできますが、暗号化されたドキュメントやファイルをオンラインで表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="9651d-136">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="9651d-137">代わりに、ローカルコンピューターのデスクトップアプリを使用して、保護されたコンテンツを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9651d-137">Instead, you must view protected content using the desktop apps on your local computer.</span></span>

## <a name="about-this-public-preview-article"></a><span data-ttu-id="9651d-138">このパブリックプレビューの記事について</span><span class="sxs-lookup"><span data-stu-id="9651d-138">About this public preview article</span></span>

<span data-ttu-id="9651d-139">二重キー暗号化を展開するための手順のいくつかを実行するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="9651d-139">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="9651d-140">この記事では、より熟練していない管理者がサービスを正常に展開するための詳細な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="9651d-140">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="9651d-141">この記事で説明されている展開方法によって共有されている、git などの一般的なテクノロジを使用している場合は、独自のメソッドを使用することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="9651d-141">If you're experienced with the common technologies, such as git, shared by the deployment methods described in this article, you can choose to use your own methods.</span></span>

<span data-ttu-id="9651d-142">パブリックプレビューでは、2重のキー暗号化サービスを Azure に展開する方法について、手順を追って説明してきました。</span><span class="sxs-lookup"><span data-stu-id="9651d-142">For public preview, we've included step-by-step instructions on how to deploy the Double Key Encryption service to Azure.</span></span> <span data-ttu-id="9651d-143">このシナリオは、運用環境での可能性があるものではありません。</span><span class="sxs-lookup"><span data-stu-id="9651d-143">This scenario isn't something you'd likely do in production.</span></span> <span data-ttu-id="9651d-144">Azure を使用したパブリックプレビューでは、すぐに二重キー暗号化を使い始めることができるように、簡単に展開できます。</span><span class="sxs-lookup"><span data-stu-id="9651d-144">For public preview using Azure is a quick way to deploy that lets you get started using Double Key Encryption right away.</span></span>

<span data-ttu-id="9651d-145">ネットワーク上でローカルに展開する場合も、別のプロバイダーを使用している場合でも、任意の場所にサービスを展開することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="9651d-145">You can choose to deploy the service wherever you want, whether it's locally on your network or with another provider.</span></span> <span data-ttu-id="9651d-146">その場所に適したメソッドを使用してキーストアを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9651d-146">You'll need to publish the key store using methods appropriate for that location.</span></span>

## <a name="deploy-double-key-encryption"></a><span data-ttu-id="9651d-147">二重キー暗号化の展開</span><span class="sxs-lookup"><span data-stu-id="9651d-147">Deploy Double Key Encryption</span></span>

<span data-ttu-id="9651d-148">次の一般的な手順に従って、組織のために二重キー暗号化を設定します。</span><span class="sxs-lookup"><span data-stu-id="9651d-148">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span> <span data-ttu-id="9651d-149">この記事の例では、DKE サービスの展開先として Azure を使用します。</span><span class="sxs-lookup"><span data-stu-id="9651d-149">The example in this article uses Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="9651d-150">別の場所に展開している場合は、独自の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9651d-150">If you're deploying to another location, you'll need to provide your own values.</span></span>

1. [<span data-ttu-id="9651d-151">必要なソフトウェアをインストールする</span><span class="sxs-lookup"><span data-stu-id="9651d-151">Install software prerequisites</span></span>](#install-software-prerequisites)
1. [<span data-ttu-id="9651d-152">二重キー暗号化 GitHub リポジトリのクローンを作成する</span><span class="sxs-lookup"><span data-stu-id="9651d-152">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="9651d-153">アプリケーションの設定を変更する</span><span class="sxs-lookup"><span data-stu-id="9651d-153">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="9651d-154">テストキーを生成する</span><span class="sxs-lookup"><span data-stu-id="9651d-154">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="9651d-155">プロジェクトをビルドする</span><span class="sxs-lookup"><span data-stu-id="9651d-155">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="9651d-156">キーストアを発行する</span><span class="sxs-lookup"><span data-stu-id="9651d-156">Publish the key store</span></span>](#publish-the-key-store)
1. [<span data-ttu-id="9651d-157">展開を検証する</span><span class="sxs-lookup"><span data-stu-id="9651d-157">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="9651d-158">キーストアを登録する</span><span class="sxs-lookup"><span data-stu-id="9651d-158">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="9651d-159">秘密度ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="9651d-159">Create sensitivity labels</span></span>](#create-labels-using-dke)

<span data-ttu-id="9651d-160">完了すると、DKE を使用してドキュメントやファイルを暗号化できます。</span><span class="sxs-lookup"><span data-stu-id="9651d-160">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="9651d-161">詳細については、「 [Office のファイルと電子メールに機密ラベルを適用する](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9651d-161">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites"></a><span data-ttu-id="9651d-162">必要なソフトウェアをインストールする</span><span class="sxs-lookup"><span data-stu-id="9651d-162">Install software prerequisites</span></span>

<span data-ttu-id="9651d-163">二重キー暗号化の前提条件となるソフトウェアは2種類あります。</span><span class="sxs-lookup"><span data-stu-id="9651d-163">There are two types of software prerequisites for Double Key Encryption</span></span>

- [<span data-ttu-id="9651d-164">二重キー暗号化サービスの前提条件</span><span class="sxs-lookup"><span data-stu-id="9651d-164">Double Key Encryption service prerequisites</span></span>](#double-key-encryption-service-prerequisites)
- [<span data-ttu-id="9651d-165">クライアントコンピューターの二重キー暗号化の前提条件</span><span class="sxs-lookup"><span data-stu-id="9651d-165">Double Key Encryption prerequisites for client computers</span></span>](#double-key-encryption-prerequisites-for-client-computers)

#### <a name="double-key-encryption-service-prerequisites"></a><span data-ttu-id="9651d-166">二重キー暗号化サービスの前提条件</span><span class="sxs-lookup"><span data-stu-id="9651d-166">Double Key Encryption service prerequisites</span></span>

<span data-ttu-id="9651d-167">これらの必須コンポーネントを、DKE サービスをインストールするコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="9651d-167">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="9651d-168">**.Net Core 3.1 SDK**。</span><span class="sxs-lookup"><span data-stu-id="9651d-168">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="9651d-169">SDK をダウンロードしてインストールします。 [.Net Core 3.1 をダウンロード](https://dotnet.microsoft.com/download/dotnet-core/3.1)します。</span><span class="sxs-lookup"><span data-stu-id="9651d-169">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="9651d-170">**Visual Studio Code**。</span><span class="sxs-lookup"><span data-stu-id="9651d-170">**Visual Studio Code**.</span></span> <span data-ttu-id="9651d-171">から Visual Studio コードをダウンロード [https://code.visualstudio.com/](https://code.visualstudio.com) します。</span><span class="sxs-lookup"><span data-stu-id="9651d-171">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="9651d-172">インストールされたら、Visual Studio Code を実行し、[**ビュー**拡張] を選択し \> **Extensions**ます。</span><span class="sxs-lookup"><span data-stu-id="9651d-172">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="9651d-173">これらの拡張機能をインストールします。</span><span class="sxs-lookup"><span data-stu-id="9651d-173">Install these extensions.</span></span>

- <span data-ttu-id="9651d-174">Visual Studio Code の C#</span><span class="sxs-lookup"><span data-stu-id="9651d-174">C# for Visual Studio Code</span></span>

- <span data-ttu-id="9651d-175">NuGet パッケージマネージャー</span><span class="sxs-lookup"><span data-stu-id="9651d-175">NuGet Package Manager</span></span>

<span data-ttu-id="9651d-176">**Microsoft Office Insider**。</span><span class="sxs-lookup"><span data-stu-id="9651d-176">**Microsoft Office Insider**.</span></span> <span data-ttu-id="9651d-177">少なくとも1つの[展開方法](https://insider.office.com/business/deploy)を設定します。</span><span class="sxs-lookup"><span data-stu-id="9651d-177">Set up at least one [deployment method](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="9651d-178">**Git リソース**。</span><span class="sxs-lookup"><span data-stu-id="9651d-178">**Git resources**.</span></span> <span data-ttu-id="9651d-179">次のいずれかをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="9651d-179">Download and install one of the following.</span></span>

- [<span data-ttu-id="9651d-180">Git</span><span class="sxs-lookup"><span data-stu-id="9651d-180">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="9651d-181">GitHub デスクトップ</span><span class="sxs-lookup"><span data-stu-id="9651d-181">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="9651d-182">GitHub Enterprise</span><span class="sxs-lookup"><span data-stu-id="9651d-182">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="9651d-183">**OpenSSL**DKE の展開後に[テストキーを生成](#generate-test-keys)するには、 [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html)がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9651d-183">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="9651d-184">環境変数のパスから適切に呼び出していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9651d-184">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="9651d-185">たとえば、詳細については、「」の「インストールディレクトリをパスに追加する」を参照してください https://www.osradar.com/install-openssl-windows/ 。</span><span class="sxs-lookup"><span data-stu-id="9651d-185">For example, see "Add the installation directory to PATH" at https://www.osradar.com/install-openssl-windows/ for details.</span></span>

#### <a name="double-key-encryption-prerequisites-for-client-computers"></a><span data-ttu-id="9651d-186">クライアントコンピューターの二重キー暗号化の前提条件</span><span class="sxs-lookup"><span data-stu-id="9651d-186">Double Key Encryption prerequisites for client computers</span></span>

<span data-ttu-id="9651d-187">保護されたドキュメントを保護して使用する各クライアントコンピューターにこれらの必須コンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="9651d-187">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="9651d-188">**Microsoft Office**バージョン \* 12711 以降。</span><span class="sxs-lookup"><span data-stu-id="9651d-188">**Microsoft Office** version \*.12711 or later.</span></span>

<span data-ttu-id="9651d-189">**Azure Information Protection クライアント**バージョン2.7.93.0 またはそれ以降のラベルを統合しています。</span><span class="sxs-lookup"><span data-stu-id="9651d-189">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="9651d-190">[Microsoft](https://www.microsoft.com/download/details.aspx?id=53018)から統合ラベルクライアントをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="9651d-190">Download and install the Unified Labeling client from [Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="9651d-191">DKE GitHub リポジトリのクローンを作成する</span><span class="sxs-lookup"><span data-stu-id="9651d-191">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="9651d-192">Microsoft は、GitHub リポジトリに DKE ソースファイルを提供しています。</span><span class="sxs-lookup"><span data-stu-id="9651d-192">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="9651d-193">リポジトリを複製して、組織の使用に合わせてプロジェクトをローカルに構築します。</span><span class="sxs-lookup"><span data-stu-id="9651d-193">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="9651d-194">DKE GitHub リポジトリは、にあり [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) ます。</span><span class="sxs-lookup"><span data-stu-id="9651d-194">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="9651d-195">次の手順は、経験のない git または Visual Studio Code ユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="9651d-195">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="9651d-196">ブラウザーで、次のように移動します。[https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span><span class="sxs-lookup"><span data-stu-id="9651d-196">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span></span>

1. <span data-ttu-id="9651d-197">画面の右側にある [**コード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9651d-197">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="9651d-198">使用しているバージョンの UI には、[**クローン] または [ダウンロード**] ボタンが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="9651d-198">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="9651d-199">次に、表示されたドロップダウンで、[コピー] アイコンを選択して、URL をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="9651d-199">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="9651d-200">例:</span><span class="sxs-lookup"><span data-stu-id="9651d-200">For example:</span></span>

    :::image type="content" source="../media/dke-clone.png" alt-text="GitHub から二重キー暗号化サービスリポジトリを複製する":::

3. <span data-ttu-id="9651d-202">Visual Studio Code で、[ **View** \> **Command Palette** ] を選択し、[ **Git: Clone**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9651d-202">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="9651d-203">一覧のオプションに移動するには、入力を開始して `git: clone` エントリをフィルター処理し、ドロップダウンから選択します。</span><span class="sxs-lookup"><span data-stu-id="9651d-203">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="9651d-204">例:</span><span class="sxs-lookup"><span data-stu-id="9651d-204">For example:</span></span>

    :::image type="content" source="../media/dke-vscode-clone.png" alt-text="Visual Studio Code GIT: Clone オプション":::

4. <span data-ttu-id="9651d-206">テキストボックスに、Git からコピーした URL を貼り付けて、[ **GitHub から複製**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9651d-206">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="9651d-207">表示される **[フォルダーの選択**] ダイアログで、リポジトリを格納する場所を参照して選択します。</span><span class="sxs-lookup"><span data-stu-id="9651d-207">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="9651d-208">プロンプトで、[**開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9651d-208">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="9651d-209">リポジトリは Visual Studio Code で開かれ、左下に現在の Git ブランチが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9651d-209">The repository is opened in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="9651d-210">現在の分岐は**マスター**である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9651d-210">Your current branch should be **master**.</span></span>

    <span data-ttu-id="9651d-211">例:</span><span class="sxs-lookup"><span data-stu-id="9651d-211">For example:</span></span>

    :::image type="content" source="../media/dke-vscode-master.png" alt-text="Visual Studio Code master 分岐":::

6. <span data-ttu-id="9651d-213">[単語**マスター** ] を選択し、分岐の一覧から [ **public_preview** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9651d-213">Select the word **master,** and then select **public_preview** from the list of branches.</span></span> 

   > [!IMPORTANT]
   > <span data-ttu-id="9651d-214">Public_preview ブランチを選択すると、プロジェクトをビルドするための適切なファイルがあることが確認されます。</span><span class="sxs-lookup"><span data-stu-id="9651d-214">Selecting the public_preview branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="9651d-215">適切なブランチを選択しない場合、展開は失敗します。</span><span class="sxs-lookup"><span data-stu-id="9651d-215">If you do not choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="9651d-216">これで、DKE ソースリポジトリがローカルに設定されました。</span><span class="sxs-lookup"><span data-stu-id="9651d-216">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="9651d-217">次に、組織の[アプリケーション設定を変更](#modify-application-settings)します。</span><span class="sxs-lookup"><span data-stu-id="9651d-217">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="9651d-218">アプリケーションの設定を変更する</span><span class="sxs-lookup"><span data-stu-id="9651d-218">Modify application settings</span></span>

<span data-ttu-id="9651d-219">DKE サービスを展開するには、次の種類のアプリケーション設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9651d-219">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="9651d-220">キーアクセス設定</span><span class="sxs-lookup"><span data-stu-id="9651d-220">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="9651d-221">テナントとキーの設定</span><span class="sxs-lookup"><span data-stu-id="9651d-221">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="9651d-222">[ファイル] の appsettings.jsで、アプリケーションの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="9651d-222">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="9651d-223">このファイルは、DoubleKeyEncryptionService\src\customer-key-store. でローカルに複製した DoubleKeyEncryptionService リポジトリにあります。</span><span class="sxs-lookup"><span data-stu-id="9651d-223">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="9651d-224">たとえば、次の図に示すように、Visual Studio Code でファイルを参照できます。</span><span class="sxs-lookup"><span data-stu-id="9651d-224">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

:::image type="content" source="../media/dke-appsettingsjson.png" alt-text="DKE のファイルの appsettings.jsを検索します。":::

#### <a name="key-access-settings"></a><span data-ttu-id="9651d-226">キーアクセス設定</span><span class="sxs-lookup"><span data-stu-id="9651d-226">Key access settings</span></span>

<span data-ttu-id="9651d-227">メールまたはロールの承認を使用するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="9651d-227">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="9651d-228">DKE は、一度に1つの認証方法のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="9651d-228">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="9651d-229">**電子メールの承認**。</span><span class="sxs-lookup"><span data-stu-id="9651d-229">**Email authorization**.</span></span> <span data-ttu-id="9651d-230">組織は、電子メールアドレスのみに基づいてキーへのアクセスを承認できます。</span><span class="sxs-lookup"><span data-stu-id="9651d-230">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="9651d-231">**役割の承認**。</span><span class="sxs-lookup"><span data-stu-id="9651d-231">**Role authorization**.</span></span> <span data-ttu-id="9651d-232">組織は、Active Directory グループに基づいてキーへのアクセスを承認でき、web サービスが LDAP を照会できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9651d-232">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="9651d-233">DKE のキーアクセス設定を設定するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="9651d-233">To set key access settings for DKE:</span></span>

1. <span data-ttu-id="9651d-234">[ファイルの**appsettings.js**で、次のいずれかの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="9651d-234">In the **appsettings.json** file, define only one of these settings:</span></span>

   - <span data-ttu-id="9651d-235">電子メール認証の場合は、[ **Authorizedemailaddresses** ] 設定を探します。</span><span class="sxs-lookup"><span data-stu-id="9651d-235">For email authorization, locate the **AuthorizedEmailAddresses** setting.</span></span> <span data-ttu-id="9651d-236">承認する電子メールアドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="9651d-236">Add the email address that you want to authorize.</span></span> <span data-ttu-id="9651d-237">複数の電子メールアドレスは、二重引用符とコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="9651d-237">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="9651d-238">例: **"" Authorizedemailaddresses ": [" email1@company.com "," email2@company.com ", email3@company.com]**</span><span class="sxs-lookup"><span data-stu-id="9651d-238">For example: **" ‘AuthorizedEmailAddresses’ ": ["email1@company.com", "email2@company.com ", email3@company.com]**</span></span>

   :::image type="content" source="../media/dke-email-accesssetting.png" alt-text="電子メールの承認方法が表示されているファイルのappsettings.js":::

   - <span data-ttu-id="9651d-240">役割の承認の場合は、[ **Authorizedroles** ] 設定を探します。</span><span class="sxs-lookup"><span data-stu-id="9651d-240">For role authorization, locate the **AuthorizedRoles** setting.</span></span> <span data-ttu-id="9651d-241">承認する ActiveDirectory グループ名を定義します。</span><span class="sxs-lookup"><span data-stu-id="9651d-241">Define with the ActiveDirectory group names you want to authorize.</span></span> <span data-ttu-id="9651d-242">例: **"Authorizedroles": ["group1", "group2", "group3"]**</span><span class="sxs-lookup"><span data-stu-id="9651d-242">For example: **"AuthorizedRoles": ["group1", "group2", "group3"]**</span></span>

   :::image type="content" source="../media/dke-role-accesssetting.png" alt-text="ロール認証方法が表示されているファイルのappsettings.js":::

2. <span data-ttu-id="9651d-244">選択した認証方法に関係のない設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="9651d-244">Remove the setting that isn't relevant for your chosen authorization method.</span></span>

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="9651d-245">テナントとキーの設定</span><span class="sxs-lookup"><span data-stu-id="9651d-245">Tenant and key settings</span></span>

<span data-ttu-id="9651d-246">DKE テナントおよびキーの設定は、 **appsettings.js**ファイルと**startup.cs**ファイルにあります。</span><span class="sxs-lookup"><span data-stu-id="9651d-246">DKE tenant and key settings are located in the **appsettings.json** file and the **startup.cs** file.</span></span>

<span data-ttu-id="9651d-247">[ファイル**のappsettings.js**で、次の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="9651d-247">In the **appsettings.json** file, modify the following values:</span></span>

- <span data-ttu-id="9651d-248">**ValidIssuers**。</span><span class="sxs-lookup"><span data-stu-id="9651d-248">**ValidIssuers**.</span></span> <span data-ttu-id="9651d-249">`<tenantid>`をテナント GUID に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="9651d-249">Replace `<tenantid>` with your tenant GUID.</span></span>
- <span data-ttu-id="9651d-250">**JwtAudience**。</span><span class="sxs-lookup"><span data-stu-id="9651d-250">**JwtAudience**.</span></span> <span data-ttu-id="9651d-251">を、 `<yourhostname>` DKE サービスが実行されるコンピューターのホスト名に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="9651d-251">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="9651d-252">JwtAudience の値は、ホストの名前と*正確*に一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="9651d-252">The value for JwtAudience must match the name of your host *exactly*.</span></span> <span data-ttu-id="9651d-253">デバッグ時に**localhost: 5000**を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="9651d-253">You may use **localhost:5000** while debugging.</span></span> <span data-ttu-id="9651d-254">ただし、デバッグを完了したら、この値をサーバーのホスト名に更新するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="9651d-254">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="9651d-255">**LDAPPath**。</span><span class="sxs-lookup"><span data-stu-id="9651d-255">**LDAPPath**.</span></span> <span data-ttu-id="9651d-256">値を次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="9651d-256">Set the value as follows:</span></span>

  - <span data-ttu-id="9651d-257">役割認証を使用している場合は、LDAP ドメインを入力します。</span><span class="sxs-lookup"><span data-stu-id="9651d-257">If you're using role authorization, enter the LDAP domain.</span></span>
  - <span data-ttu-id="9651d-258">電子メール認証を使用している場合は、この値を空のままにします。</span><span class="sxs-lookup"><span data-stu-id="9651d-258">If you're using email authorization, leave this value empty.</span></span>

   <span data-ttu-id="9651d-259">詳細については、「[キーアクセスの設定](#key-access-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9651d-259">For more information, see [Key access settings](#key-access-settings).</span></span>

- <span data-ttu-id="9651d-260">**Testkeys: Name**。</span><span class="sxs-lookup"><span data-stu-id="9651d-260">**TestKeys:Name**.</span></span> <span data-ttu-id="9651d-261">キーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="9651d-261">Enter a name for your key.</span></span> <span data-ttu-id="9651d-262">例: **TestKey1**</span><span class="sxs-lookup"><span data-stu-id="9651d-262">Example: **TestKey1**</span></span>
- <span data-ttu-id="9651d-263">**Testkeys: Id**。GUID を作成し、 **Testkeys: ID**値として入力します。</span><span class="sxs-lookup"><span data-stu-id="9651d-263">**TestKeys:Id**. Create a GUID and enter it as the **TestKeys:ID** value.</span></span> <span data-ttu-id="9651d-264">たとえば、 **DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE**のようになります。</span><span class="sxs-lookup"><span data-stu-id="9651d-264">For example, **DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE**.</span></span> <span data-ttu-id="9651d-265">[ONLINE Guid ジェネレーター](https://guidgenerator.com/)のようなサイトを使用して、guid をランダムに生成することができます。</span><span class="sxs-lookup"><span data-stu-id="9651d-265">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

### <a name="generate-test-keys"></a><span data-ttu-id="9651d-266">テストキーを生成する</span><span class="sxs-lookup"><span data-stu-id="9651d-266">Generate test keys</span></span>

<span data-ttu-id="9651d-267">アプリケーション設定を定義したら、パブリックおよびプライベートのテストキーを生成する準備ができています。</span><span class="sxs-lookup"><span data-stu-id="9651d-267">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="9651d-268">キーを生成するには</span><span class="sxs-lookup"><span data-stu-id="9651d-268">To generate keys:</span></span>

1. <span data-ttu-id="9651d-269">Windows の [スタート] メニューから、OpenSSL コマンドプロンプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="9651d-269">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

1. <span data-ttu-id="9651d-270">テストキーを保存するフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="9651d-270">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="9651d-271">このタスクの手順を完了することによって作成したファイルは、同じフォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="9651d-271">The files you create by completing the steps in this task are stored in the same folder.</span></span>

1. <span data-ttu-id="9651d-272">新しいテストキーを生成します。</span><span class="sxs-lookup"><span data-stu-id="9651d-272">Generate the new test key.</span></span>

   ```dos
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

2. <span data-ttu-id="9651d-273">秘密キーを生成します。</span><span class="sxs-lookup"><span data-stu-id="9651d-273">Generate the private key.</span></span>

   ```dos
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

1. <span data-ttu-id="9651d-274">公開キーを生成します。</span><span class="sxs-lookup"><span data-stu-id="9651d-274">Generate the public key.</span></span>

   ```dos
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

1. <span data-ttu-id="9651d-275">テキストエディターで、 **pubkeyonly**を開きます。</span><span class="sxs-lookup"><span data-stu-id="9651d-275">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="9651d-276">最初と最後の行を除く、 **pubkeyonly pem**ファイル内のすべてのコンテンツを、 **appsettings.js**ファイルの**publicpem**セクションにコピーします。</span><span class="sxs-lookup"><span data-stu-id="9651d-276">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the **PublicPem** section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="9651d-277">テキストエディターで、 **privkeynopass pem**を開きます。</span><span class="sxs-lookup"><span data-stu-id="9651d-277">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="9651d-278">最初と最後の行を除く、 **privkeynopass. pem**ファイルのすべてのコンテンツを、appsettings.jsファイルの **[** **privatepem** ] セクションにコピーします。</span><span class="sxs-lookup"><span data-stu-id="9651d-278">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the **PrivatePem** section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="9651d-279">**Publicpem**セクションと**privatepem**セクションの両方で空白スペースと改行を削除します。</span><span class="sxs-lookup"><span data-stu-id="9651d-279">Remove all blank spaces and newlines in both the **PublicPem** and **PrivatePem** sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="9651d-280">このコンテンツをコピーする場合は、PEM データを削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="9651d-280">When you copy this content, do not delete any of the PEM data.</span></span>

1. <span data-ttu-id="9651d-281">**Startup.cs**ファイルを開き、次の行を探します。</span><span class="sxs-lookup"><span data-stu-id="9651d-281">Open the **Startup.cs** file, and locate the following lines:</span></span>

   ```c#
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE  FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
   ```

1. <span data-ttu-id="9651d-282">これらの行を次のテキストに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="9651d-282">Replace these lines with the following text:</span></span>

   ```csharp
   services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
   ```

   <span data-ttu-id="9651d-283">最終結果は次の図のようになります。</span><span class="sxs-lookup"><span data-stu-id="9651d-283">The end results should look similar to the following picture.</span></span>

   :::image type="content" source="../media/dke-startupcs-usetestkeys.png" alt-text="パブリックプレビュー用の startup.cs ファイル":::

<span data-ttu-id="9651d-285">これで[、DKE プロジェクトを構築](#build-the-project)する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="9651d-285">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="9651d-286">プロジェクトをビルドする</span><span class="sxs-lookup"><span data-stu-id="9651d-286">Build the project</span></span>

<span data-ttu-id="9651d-287">次の手順を使用して、ローカルに DKE プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="9651d-287">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="9651d-288">Visual Studio Code の dke サービスリポジトリで、[コマンドパレットの**表示**] を選択し、 \> **Command Palette**プロンプトで「 **build** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="9651d-288">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

1. <span data-ttu-id="9651d-289">リストから、[**タスク: ビルドタスクの実行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9651d-289">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="9651d-290">ビルドタスクが見つからない場合は、[**ビルドタスクの構成**] を選択し、次のように .net コア用のタスクを作成します。</span><span class="sxs-lookup"><span data-stu-id="9651d-290">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   :::image type="content" source="../media/dke-configurebuildtask.png" alt-text=".NET の不明なビルドタスクを構成する":::

   1. <span data-ttu-id="9651d-292">[**テンプレートから tasks.jsを作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9651d-292">Choose **Create tasks.json from template**.</span></span>

   :::image type="content" source="../media/dke-createtasksjsonfromtemplate.png" alt-text="DKE テンプレートからファイルに tasks.jsを作成する":::

   2. <span data-ttu-id="9651d-294">テンプレートの種類の一覧から [ **.Net Core**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9651d-294">From the list of template types, select **.NET Core**.</span></span>

   :::image type="content" source="../media/dke-tasksjsontemplate.png" alt-text="DKE テンプレートからファイルに tasks.jsを作成する":::

   3. <span data-ttu-id="9651d-296">[ビルド] セクションで、**顧客キーストア**ファイルへのパスを見つけます。</span><span class="sxs-lookup"><span data-stu-id="9651d-296">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="9651d-297">存在しない場合は、次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="9651d-297">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

  4. <span data-ttu-id="9651d-298">ビルドを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="9651d-298">Run the build again.</span></span>

1. <span data-ttu-id="9651d-299">出力ウィンドウに赤のエラーが表示されないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9651d-299">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="9651d-300">赤のエラーがある場合は、コンソール出力を確認します。</span><span class="sxs-lookup"><span data-stu-id="9651d-300">If there are red errors, check the console output.</span></span> <span data-ttu-id="9651d-301">上記の手順がすべて正常に完了し、適切なビルドバージョンが存在することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9651d-301">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

1. <span data-ttu-id="9651d-302">**実行** \>**デバッグを開始**してプロセスをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="9651d-302">**Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="9651d-303">環境を選択するように求めるメッセージが表示されたら、[ **.net core**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9651d-303">If you're prompted to select an environment, select **.NET core**.</span></span>

<span data-ttu-id="9651d-304">.NET コアデバッガーは通常、に起動し **https://localhost:5001** ます。</span><span class="sxs-lookup"><span data-stu-id="9651d-304">The .NET core debugger typically launches to **https://localhost:5001**.</span></span> <span data-ttu-id="9651d-305">テストキーを表示するには、に移動して、 **https://localhost:5001** スラッシュ (/) とキーの名前を追加します。</span><span class="sxs-lookup"><span data-stu-id="9651d-305">To view your test key, go to **https://localhost:5001**, and append a forward slash (/) and the name of your key.</span></span>

<span data-ttu-id="9651d-306">例えば：**https://localhost:5001/TestKey1**</span><span class="sxs-lookup"><span data-stu-id="9651d-306">For example: **https://localhost:5001/TestKey1**</span></span>

<span data-ttu-id="9651d-307">キーは JSON 形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="9651d-307">The key should display in JSON format.</span></span>

<span data-ttu-id="9651d-308">セットアップが完了しました。</span><span class="sxs-lookup"><span data-stu-id="9651d-308">Your setup is now complete.</span></span> <span data-ttu-id="9651d-309">キーストアを発行する前に、JwtAudience の設定 appsettings.jsで、[] 設定で、[ホスト名] の値が App Service ホスト名と正確に一致していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9651d-309">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="9651d-310">ビルドのトラブルシューティングを行うために、localhost に変更した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9651d-310">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="publish-the-key-store"></a><span data-ttu-id="9651d-311">キーストアを発行する</span><span class="sxs-lookup"><span data-stu-id="9651d-311">Publish the key store</span></span>

<span data-ttu-id="9651d-312">次の手順では、DKE 展開をホストする Azure App Service インスタンスを作成する方法と、生成されたキーを Azure に公開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9651d-312">The following steps describe how to create an Azure App Service instance to host your DKE deployment, and how to publish your generated keys to Azure.</span></span>

<span data-ttu-id="9651d-313">DKE 展開をホストするための Azure Web App インスタンスを作成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="9651d-313">To create an Azure Web App instance to host your DKE deployment:</span></span>

1. <span data-ttu-id="9651d-314">ブラウザーで、 [Microsoft Azure ポータル](https://ms.portal.azure.com)にサインインし、[ **App Services**追加] に移動し  >  **Add**ます。</span><span class="sxs-lookup"><span data-stu-id="9651d-314">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

1. <span data-ttu-id="9651d-315">サブスクリプションとリソースグループを選択し、インスタンスの詳細を定義します。</span><span class="sxs-lookup"><span data-stu-id="9651d-315">Select your subscription and resource group and define your instance details.</span></span>

    - <span data-ttu-id="9651d-316">DKE サービスをインストールするコンピューターのホスト名を入力します。</span><span class="sxs-lookup"><span data-stu-id="9651d-316">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="9651d-317">[ファイルのappsettings.js] の[**[**](#tenant-and-key-settings) JwtAudience] 設定に定義されている名前と同じ名前であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9651d-317">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="9651d-318">名前に指定する値は WebAppInstanceName でもあります。</span><span class="sxs-lookup"><span data-stu-id="9651d-318">The value you provide for the name is also the WebAppInstanceName.</span></span>

    - <span data-ttu-id="9651d-319">[**発行**] で、[**コード**] を選択し、[**ランタイムスタック**] で [ **.net Core 3.1**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9651d-319">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

    <span data-ttu-id="9651d-320">例:</span><span class="sxs-lookup"><span data-stu-id="9651d-320">For example:</span></span>

    :::image type="content" source="../media/dke-azure-add-app-service.png" alt-text="アプリサービスを追加する":::

1. <span data-ttu-id="9651d-322">ページの下部にある [**レビュー + 作成**] を選択し、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9651d-322">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

1. <span data-ttu-id="9651d-323">生成されたキーを Azure に公開するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9651d-323">Do one of the following to publish your generated keys to Azure:</span></span>

    - [<span data-ttu-id="9651d-324">ZipDeployUI を使用して発行する</span><span class="sxs-lookup"><span data-stu-id="9651d-324">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
    - [<span data-ttu-id="9651d-325">FTP を使用した発行</span><span class="sxs-lookup"><span data-stu-id="9651d-325">Publish via FTP</span></span>](#publish-via-ftp)
    - [<span data-ttu-id="9651d-326">Visual Studio 2019 以降での発行</span><span class="sxs-lookup"><span data-stu-id="9651d-326">Publish via Visual Studio 2019 or later</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/)
    - [<span data-ttu-id="9651d-327">オンプレミスのシステムに発行する</span><span class="sxs-lookup"><span data-stu-id="9651d-327">Publish to an on-premises system</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli)

    > [!NOTE]
    > <span data-ttu-id="9651d-328">他の方法でキーを展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="9651d-328">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="9651d-329">組織に最も適した方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="9651d-329">Select the method that works best for your organization.</span></span>

    > [!TIP]
    > <span data-ttu-id="9651d-330">[Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/)と[オンプレミスシステム](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli)への発行については、 [ASP .net ドキュメント](https://docs.microsoft.com/aspnet/core/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9651d-330">[Publishing via Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/) and to an [on-premises system](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) is described in the [ASP .NET documentation](https://docs.microsoft.com/aspnet/core/).</span></span> <span data-ttu-id="9651d-331">これらの方法のいずれかを使用する場合は、操作が完了したら簡単に戻ることができるように、別のタブで手順を開きます。</span><span class="sxs-lookup"><span data-stu-id="9651d-331">If you use one of these methods, open the instructions in a separate tab so that you can return here easily when you're done.</span></span>

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="9651d-332">ZipDeployUI を使用して発行する</span><span class="sxs-lookup"><span data-stu-id="9651d-332">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="9651d-333">`https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI` に移動します。</span><span class="sxs-lookup"><span data-stu-id="9651d-333">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

    <span data-ttu-id="9651d-334">例: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="9651d-334">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

1. <span data-ttu-id="9651d-335">キーストアのコードベースで、 **customer-key-store\src\customer-key-store**フォルダーに移動し、このフォルダーに**顧客キーストア**ファイルが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9651d-335">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="9651d-336">実行: **dotnet publish**</span><span class="sxs-lookup"><span data-stu-id="9651d-336">Run: **dotnet publish**</span></span>

     <span data-ttu-id="9651d-337">[出力] ウィンドウには、発行が展開されたディレクトリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9651d-337">The output window displays the directory where the publish was deployed.</span></span>

    <span data-ttu-id="9651d-338">例: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="9651d-338">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="9651d-339">Publish ディレクトリ内のすべてのファイルを .zip ファイルに送信します。</span><span class="sxs-lookup"><span data-stu-id="9651d-339">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="9651d-340">.Zip ファイルを作成するときは、ディレクトリ内のすべてのファイルが .zip ファイルのルートレベルにあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9651d-340">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="9651d-341">先ほど開いた ZipDeployUI サイトに、作成した .zip ファイルをドラッグアンドドロップします。</span><span class="sxs-lookup"><span data-stu-id="9651d-341">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="9651d-342">例: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="9651d-342">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="9651d-343">DKE が展開されており、作成したテストキーを参照することができます。</span><span class="sxs-lookup"><span data-stu-id="9651d-343">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="9651d-344">引き続き「[展開を検証](#validate-your-deployment)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9651d-344">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="9651d-345">FTP を使用した発行</span><span class="sxs-lookup"><span data-stu-id="9651d-345">Publish via FTP</span></span>

1. <span data-ttu-id="9651d-346">[上記の手順](#publish-the-key-store)で作成した App Service に接続します。</span><span class="sxs-lookup"><span data-stu-id="9651d-346">Connect to the App Service you created [above](#publish-the-key-store).</span></span>

    <span data-ttu-id="9651d-347">ブラウザーで、「 **Azure portal**  >  **App Service**  >  **Deployment Center**  >  **Manual Deployment**  >  **FTP**  >  **Dashboard**」に移動します。</span><span class="sxs-lookup"><span data-stu-id="9651d-347">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

1. <span data-ttu-id="9651d-348">ローカルファイルに表示される接続文字列をコピーします。</span><span class="sxs-lookup"><span data-stu-id="9651d-348">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="9651d-349">これらの文字列を使用して Web App サービスに接続し、FTP を使用してファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="9651d-349">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

    <span data-ttu-id="9651d-350">例:</span><span class="sxs-lookup"><span data-stu-id="9651d-350">For example:</span></span>

    :::image type="content" source="../media/dke-ftp-dashboard.png" alt-text="FTP ダッシュボードから接続文字列をコピーする":::

1. <span data-ttu-id="9651d-352">キーの格納用のコードベースで、 **customer-key-store\src\customer-key-store ディレクトリ**に移動します。</span><span class="sxs-lookup"><span data-stu-id="9651d-352">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

1. <span data-ttu-id="9651d-353">このディレクトリに、**顧客キーストアの .csproj**ファイルが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9651d-353">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="9651d-354">実行: **dotnet publish**</span><span class="sxs-lookup"><span data-stu-id="9651d-354">Run: **dotnet publish**</span></span>

    <span data-ttu-id="9651d-355">この出力には、発行が展開されたディレクトリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9651d-355">The output contains the directory where the publish was deployed.</span></span>

    <span data-ttu-id="9651d-356">例: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="9651d-356">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="9651d-357">発行ディレクトリ内のすべてのファイルを zip ファイルに送信します。</span><span class="sxs-lookup"><span data-stu-id="9651d-357">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="9651d-358">.Zip ファイルを作成するときは、ディレクトリ内のすべてのファイルが .zip ファイルのルートレベルにあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9651d-358">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="9651d-359">FTP クライアントから、コピーした接続情報を使用して App Service に接続します。</span><span class="sxs-lookup"><span data-stu-id="9651d-359">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="9651d-360">前の手順で作成した .zip ファイルを Web アプリのルートディレクトリにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="9651d-360">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="9651d-361">DKE が展開されており、作成したテストキーを参照することができます。</span><span class="sxs-lookup"><span data-stu-id="9651d-361">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="9651d-362">次に、[展開を検証](#validate-your-deployment)します。</span><span class="sxs-lookup"><span data-stu-id="9651d-362">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="9651d-363">展開を検証する</span><span class="sxs-lookup"><span data-stu-id="9651d-363">Validate your deployment</span></span>

<span data-ttu-id="9651d-364">前述の方法のいずれかを使用して DKE を展開した後、展開とキーストアの設定を検証します。</span><span class="sxs-lookup"><span data-stu-id="9651d-364">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="9651d-365">実行</span><span class="sxs-lookup"><span data-stu-id="9651d-365">Run:</span></span>

<span data-ttu-id="9651d-366">src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/mykey</span><span class="sxs-lookup"><span data-stu-id="9651d-366">src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/mykey</span></span>

<span data-ttu-id="9651d-367">例:</span><span class="sxs-lookup"><span data-stu-id="9651d-367">For example:</span></span>

<span data-ttu-id="9651d-368">key_store_tester.ps1https://mycustomerkeystore.com/mykey</span><span class="sxs-lookup"><span data-stu-id="9651d-368">key_store_tester.ps1 https://mycustomerkeystore.com/mykey</span></span>

<span data-ttu-id="9651d-369">出力にエラーが表示されないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9651d-369">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="9651d-370">準備が整ったら、[キーストアを登録](#register-your-key-store)します。</span><span class="sxs-lookup"><span data-stu-id="9651d-370">When you're ready, [register your key store](#register-your-key-store).</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="9651d-371">キーストアを登録する</span><span class="sxs-lookup"><span data-stu-id="9651d-371">Register your key store</span></span>

<span data-ttu-id="9651d-372">次の手順を実行すると、キーストアを登録できるようになります。</span><span class="sxs-lookup"><span data-stu-id="9651d-372">The following steps enable you to register your key store.</span></span> <span data-ttu-id="9651d-373">ラベルの作成を開始する前に、DKE を展開するための最後の手順として、キーストアの登録が必要になります。</span><span class="sxs-lookup"><span data-stu-id="9651d-373">Registering your key store is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="9651d-374">キーストアを登録するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="9651d-374">To register your key store:</span></span>

1. <span data-ttu-id="9651d-375">ブラウザーで、 [Microsoft Azure portal](https://ms.portal.azure.com/)を開き、[**すべてのサービス** \> **id** \> **アプリの登録**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="9651d-375">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="9651d-376">[**新しい登録**] を選択し、わかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="9651d-376">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="9651d-377">表示されているオプションから、アカウントの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="9651d-377">Select an account type from the options displayed.</span></span>

    <span data-ttu-id="9651d-378">**Onmicrosoft.com**などの非ユーザー設定ドメインを使用して Microsoft Azure を使用している場合は、[**この組織ディレクトリ内のアカウントのみ (microsoft のみ)** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9651d-378">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

    <span data-ttu-id="9651d-379">例:</span><span class="sxs-lookup"><span data-stu-id="9651d-379">For example:</span></span>

    :::image type="content" source="../media/dke-app-registration.png" alt-text="新しいアプリの登録":::

4. <span data-ttu-id="9651d-381">ページの下部にある [**登録**] を選択して、新しいアプリの登録を作成します。</span><span class="sxs-lookup"><span data-stu-id="9651d-381">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="9651d-382">新しいアプリの登録で、左側のウィンドウの [**管理**] で [**認証**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9651d-382">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="9651d-383">[**プラットフォームの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9651d-383">Select **Add a platform**.</span></span>
 
7. <span data-ttu-id="9651d-384">[**プラットフォームの構成**] ポップアップで [ **Web**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9651d-384">On the **Configure platforms** popup select **Web**.</span></span>
 
8. <span data-ttu-id="9651d-385">[**リダイレクト uri** ] で、二重キー暗号化サービスの URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="9651d-385">Under **Redirect URIs** enter the URI of your double key encryption service.</span></span> <span data-ttu-id="9651d-386">ホスト名とドメインの両方を含む、App Service の URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="9651d-386">Enter the App Service URL, including both the hostname and domain.</span></span>

    <span data-ttu-id="9651d-387">例: https://mycustomerkeystoretest.com</span><span class="sxs-lookup"><span data-stu-id="9651d-387">For example: https://mycustomerkeystoretest.com</span></span>

    - <span data-ttu-id="9651d-388">入力する URL は、キーストアが展開されているホスト名と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="9651d-388">The URL you enter must match the hostname where your key store is deployed.</span></span>
    - <span data-ttu-id="9651d-389">Visual Studio を使用してローカルでテストしている場合は、を使用 **https://localhost:5001** します。</span><span class="sxs-lookup"><span data-stu-id="9651d-389">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
    - <span data-ttu-id="9651d-390">すべての場合において、スキームは**https**である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9651d-390">In all cases, the scheme must be **https**.</span></span>

    <span data-ttu-id="9651d-391">ホスト名が App Service ホスト名と正確に一致していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9651d-391">Ensure the hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="9651d-392">ビルドのトラブルシューティングを行うために、localhost に変更した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9651d-392">You may have changed it to localhost to troubleshoot the build.</span></span> <span data-ttu-id="9651d-393">appsettings.jsの場合、これは JwtAudience の設定値として識別されたホスト名です。</span><span class="sxs-lookup"><span data-stu-id="9651d-393">In appsettings.json, this is the hostname you identified as the value for the JwtAudience setting.</span></span>

6. <span data-ttu-id="9651d-394">[**暗黙的な付与**] で、[ **ID トークン**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="9651d-394">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

1. <span data-ttu-id="9651d-395">**[保存]** を選択し、変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="9651d-395">Select **Save** to save your changes.</span></span>

7. <span data-ttu-id="9651d-396">左側のウィンドウで、[ **API の公開**] を選択し、[アプリケーション ID URI] の横にある [**設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9651d-396">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

9. <span data-ttu-id="9651d-397">引き続き [ **api の公開**] ページで、[**この api によって定義されるスコープ**] 領域の [**範囲の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9651d-397">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="9651d-398">新しい範囲の場合:</span><span class="sxs-lookup"><span data-stu-id="9651d-398">In the new scope:</span></span>

    1. <span data-ttu-id="9651d-399">スコープ名を**user_impersonation**として定義します。</span><span class="sxs-lookup"><span data-stu-id="9651d-399">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="9651d-400">同意できる管理者とユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="9651d-400">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="9651d-401">残りの必要な値を定義します。</span><span class="sxs-lookup"><span data-stu-id="9651d-401">Define any remaining values required.</span></span>

    4. <span data-ttu-id="9651d-402">[**スコープの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9651d-402">Select **Add scope.**</span></span>

    <span data-ttu-id="9651d-403">上部にある [**保存**] を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="9651d-403">Select **Save** at the top to save your changes.</span></span>

10. <span data-ttu-id="9651d-404">引き続き [ **API の公開**] ページの [承認された**クライアントアプリケーション**] 領域で、[**クライアントアプリケーションの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9651d-404">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="9651d-405">新しいクライアントアプリケーションの場合:</span><span class="sxs-lookup"><span data-stu-id="9651d-405">In the new client application:</span></span>

    1. <span data-ttu-id="9651d-406">クライアント ID を**d3590ed6-52b3-4102-aeff-aad2292ab01c**として定義します。</span><span class="sxs-lookup"><span data-stu-id="9651d-406">Define the Client ID as **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span></span> <span data-ttu-id="9651d-407">この値は Microsoft Office クライアント ID であり、Office はキーストアのアクセストークンを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="9651d-407">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="9651d-408">[**承認**されたスコープ] で、 **user_impersonation**スコープを選択します。</span><span class="sxs-lookup"><span data-stu-id="9651d-408">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="9651d-409">**[アプリケーションの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9651d-409">Select **Add application**.</span></span>

    4. <span data-ttu-id="9651d-410">上部にある [**保存**] を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="9651d-410">Select **Save** at the top to save your changes.</span></span>

<span data-ttu-id="9651d-411">これで、DKE キーストアが登録されました。</span><span class="sxs-lookup"><span data-stu-id="9651d-411">Your DKE key store is now registered.</span></span> <span data-ttu-id="9651d-412">引き続き、 [DKE を使用してラベルを作成](#create-labels-using-dke)します。</span><span class="sxs-lookup"><span data-stu-id="9651d-412">Continue  by [creating labels using DKE](#create-labels-using-dke).</span></span>

## <a name="create-labels-using-dke"></a><span data-ttu-id="9651d-413">DKE を使用してラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="9651d-413">Create labels using DKE</span></span>

<span data-ttu-id="9651d-414">キーストアを登録したら、Microsoft 365 コンプライアンスセンターで機密ラベルを設定し、これらのラベルに二重のキー暗号化を適用します。</span><span class="sxs-lookup"><span data-stu-id="9651d-414">Once you've registered your key store, set up sensitivity labels in the Microsoft 365 compliance center and apply double key encryption to those labels.</span></span>

<span data-ttu-id="9651d-415">ラベル作成 UI で、[二重の**キー暗号化を使用する**] オプションを選択し、キーのエンドポイント URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="9651d-415">In the label creation UI, select the **Use Double Key Encryption** option and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="9651d-416">例:</span><span class="sxs-lookup"><span data-stu-id="9651d-416">For example:</span></span>

:::image type="content" source="../media/dke-use-dke.png" alt-text="Microsoft 365 コンプライアンスセンターで [二重のキー暗号化を使用する] を選択します。":::

<span data-ttu-id="9651d-418">追加した DKE ラベルは、Microsoft 365 Apps for enterprise の最新バージョンのユーザーに対して表示され始めます。</span><span class="sxs-lookup"><span data-stu-id="9651d-418">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="9651d-419">クライアントが新しいラベルで更新されるまで、最大24時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9651d-419">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="9651d-420">クライアントで DKE を有効にする</span><span class="sxs-lookup"><span data-stu-id="9651d-420">Enable DKE in your client</span></span>

<span data-ttu-id="9651d-421">Microsoft Office の [感度] リボンの下に DKE ラベルが表示されない場合、クライアントの DKE が有効になっていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9651d-421">If your DKE labels don't appear under the Sensitivity ribbon in Microsoft Office, your client may not have DKE enabled.</span></span>

<span data-ttu-id="9651d-422">次のレジストリキーを追加して、クライアントに対して DKE を有効にします。</span><span class="sxs-lookup"><span data-stu-id="9651d-422">Enable DKE for your client by adding the following registry keys:</span></span>

```ini
    [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001
```
