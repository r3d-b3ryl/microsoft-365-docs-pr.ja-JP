---
title: '手順 2: 環境の分類を構成する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 組織内のデータを分類するさまざまな方法について理解し、構成します。
ms.openlocfilehash: e1f0a6b9bdc4b6844037e7e873ed321942e8258e
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370414"
---
# <a name="step-2-configure-classification-for-your-environment"></a><span data-ttu-id="00420-103">手順 2: 環境の分類を構成する</span><span class="sxs-lookup"><span data-stu-id="00420-103">Step 2: Configure classification for your environment</span></span>

<span data-ttu-id="00420-104">*この手順は省略可能で、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます*</span><span class="sxs-lookup"><span data-stu-id="00420-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![フェーズ 6: 情報保護](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="00420-106">この手順では、法務/コンプライアンス チームと連携して組織のデータの分類方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="00420-106">In this step, you work with your legal and compliance teams to define a classification scheme for your organization’s data.</span></span>

## <a name="microsoft-365-classification-types"></a><span data-ttu-id="00420-107">Microsoft 365 の分類の種類</span><span class="sxs-lookup"><span data-stu-id="00420-107">Microsoft 365 classification types</span></span>

<span data-ttu-id="00420-108">Microsoft 365 には、次の 4 種類の分類方法があります。</span><span class="sxs-lookup"><span data-stu-id="00420-108">Microsoft 365 includes four types of classification:</span></span>

- <span data-ttu-id="00420-109">機密情報の種類</span><span class="sxs-lookup"><span data-stu-id="00420-109">Sensitive information types</span></span>
- <span data-ttu-id="00420-110">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="00420-110">Retention labels</span></span>
- <span data-ttu-id="00420-111">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="00420-111">Sensitivity labels</span></span>
- <span data-ttu-id="00420-112">Azure Information Protection のラベルと保護</span><span class="sxs-lookup"><span data-stu-id="00420-112">Azure Information Protection labels and protection</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="00420-113">機密情報の種類</span><span class="sxs-lookup"><span data-stu-id="00420-113">Sensitive information types</span></span>

<span data-ttu-id="00420-114">Microsoft 365 の機密情報の種類は、検索などの自動化されたプロセスが特定の情報の種類を認識する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="00420-114">Sensitive information types for Microsoft 365 define how automated processes such as search recognize specific information types.</span></span> <span data-ttu-id="00420-115">この中には医療サービス番号やクレジット カード番号といった機密性の高い従業員または顧客データが含まれます。</span><span class="sxs-lookup"><span data-stu-id="00420-115">These include sensitive employee or customer data such as health service numbers and credit card numbers.</span></span> <span data-ttu-id="00420-116">機密情報の種類を使用して、機密データを検索し、データ損失防止 (DLP) ルールおよびポリシーを適用してこのデータを保護します。</span><span class="sxs-lookup"><span data-stu-id="00420-116">You use sensitive information types to find sensitive data and apply data loss prevention (DLP) rules and policies to protect this data.</span></span> <span data-ttu-id="00420-117">詳細については、[DLP ポリシーの内容](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00420-117">For more information, see [what a DLP policy contains](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains).</span></span> 

<span data-ttu-id="00420-118">機密情報の種類は、一般データ保護規制 (GDPR) のようなコンプライアンスや規制の要件を満たすために特に便利です。</span><span class="sxs-lookup"><span data-stu-id="00420-118">Sensitive information types are especially helpful for meeting compliance and regulation requirements, such as for the General Data Protection Regulation (GDPR).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="00420-119">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="00420-119">Retention labels</span></span>

<span data-ttu-id="00420-120">データ ガバナンス戦略の定義の一部は組織のポリシーと地域の規制に準拠して特定の種類のドキュメントまたは特定のコンテンツのドキュメントを保持する期間を決定することです。</span><span class="sxs-lookup"><span data-stu-id="00420-120">Part of defining a data governance strategy is deciding how long specific types of documents or documents with specific contents should be retained in compliance with organization policies and regional regulations.</span></span> <span data-ttu-id="00420-121">たとえば、一部の種類のドキュメントは一定の時間を保持した後で削除する必要があり、別の種類のドキュメントは無期限に保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00420-121">For example, some types of documents should be retained for a set amount of time and then deleted and others must be retained indefinitely.</span></span>

<span data-ttu-id="00420-122">Microsoft 365 で保存されるドキュメントに関しては、Exchange メールに保存されるドキュメントおよびデータ、SharePoint Online、OneDrive for Business、Teams チャット、チャネル メッセージに保持ラベルを定義して適用します。</span><span class="sxs-lookup"><span data-stu-id="00420-122">For documents stored in Microsoft 365, you define and apply retention labels to documents and data stored in Exchange email, SharePoint Online, OneDrive for Business, and Teams chat and channel messages.</span></span> 

<span data-ttu-id="00420-123">保持ラベルを使用する場合、保持ポリシーを適用する必要があるファイルの各カテゴリのラベルを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00420-123">If you use retention labels, you should configure a label for each category of file that needs to have a retention policy applied.</span></span> <span data-ttu-id="00420-124">保持ラベル内に以下の項目を指定できます。</span><span class="sxs-lookup"><span data-stu-id="00420-124">Within the retention label, you can specify:</span></span>

- <span data-ttu-id="00420-125">ファイルの記述子のセット (たとえば、ビジネス部門、ファイルのカテゴリ、または規制別)。</span><span class="sxs-lookup"><span data-stu-id="00420-125">A set of descriptors for the files (for example, by business department, file category, or regulation).</span></span>
- <span data-ttu-id="00420-126">保持する時間と保持する時間に到達した後の処理など、保持ラベルが添付されたファイルの保存設定。</span><span class="sxs-lookup"><span data-stu-id="00420-126">The retention settings for the files that have the retention label attached, such as retain times and behaviors after the retain time has been reached.</span></span>

<span data-ttu-id="00420-127">SharePoint Online サイトを設定することにより保持ラベルをファイルに自動適用し、サイト内のすべての新しいドキュメントに既定の保持ラベルを適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="00420-127">You can also apply a retention label to files automatically by configuring a SharePoint Online site to apply a default retention label to all new documents in the site.</span></span> 

<span data-ttu-id="00420-128">詳細については、「[保持ラベルの概要](https://docs.microsoft.com/office365/securitycompliance/labels)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="00420-128">For more information, see the [overview of retention labels](https://docs.microsoft.com/office365/securitycompliance/labels).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="00420-129">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="00420-129">Sensitivity labels</span></span>

<span data-ttu-id="00420-130">特定の種類のドキュメントまたは特定のコンテンツのドキュメントに対するセキュリティの保護と実装の一部は、追加のセキュリティを適用できるようにラベルを使用してマークすることです。</span><span class="sxs-lookup"><span data-stu-id="00420-130">Part of protecting and implementing security for specific types of documents or documents with specific contents is marking them with a label so that the additional security can be applied.</span></span> <span data-ttu-id="00420-131">Microsoft 365 の機密ラベルを使用して次のことができます。</span><span class="sxs-lookup"><span data-stu-id="00420-131">With sensitivity labels in Microsoft 365, you can:</span></span>

- <span data-ttu-id="00420-132">暗号化、アクセス許可、または透かしの追加といった保護設定を強制適用する。</span><span class="sxs-lookup"><span data-stu-id="00420-132">Enforce protection settings such as encryption, permissions, or adding a watermark.</span></span>
- <span data-ttu-id="00420-133">Windows Information Protection (WIP) Endpoint Protection を使用して、そのコンテンツがサード パーティ製アプリ (Twitter や Gmail など)、またはリムーバブル記憶域 (USB ドライブなど) にコピーされることを防止する。</span><span class="sxs-lookup"><span data-stu-id="00420-133">Use Windows Information Protection (WIP) endpoint protection to prevent that content from being copied to a third-party app, such as Twitter or Gmail, or being copied to removable storage, such as a USB drive.</span></span>
- <span data-ttu-id="00420-134">Microsoft Cloud App Security (CAS) を使用してサード パーティ製アプリおよびサービスのコンテンツを保護する。</span><span class="sxs-lookup"><span data-stu-id="00420-134">Use Microsoft Cloud App Security to protect content in third-party apps and services.</span></span> 
- <span data-ttu-id="00420-135">保護設定を使わずにコンテンツを分類する。</span><span class="sxs-lookup"><span data-stu-id="00420-135">Classify content without using any protection settings.</span></span>

<span data-ttu-id="00420-136">機密ラベルを使用する場合、セキュリティと情報保護レベルごとにラベルを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00420-136">If you use sensitivity labels, you should configure a label for each security and information protection level.</span></span> <span data-ttu-id="00420-137">たとえばの以下の 3 つの機密ラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="00420-137">For example, create three sensitivity labels for:</span></span>

- <span data-ttu-id="00420-138">基準</span><span class="sxs-lookup"><span data-stu-id="00420-138">Baseline</span></span>
- <span data-ttu-id="00420-139">機密</span><span class="sxs-lookup"><span data-stu-id="00420-139">Sensitive</span></span>
- <span data-ttu-id="00420-140">厳しく規制</span><span class="sxs-lookup"><span data-stu-id="00420-140">Highly regulated</span></span>

<span data-ttu-id="00420-141">SharePoint Online サイトに高度に規制されたデータを含むファイルを保存し、ファイルがサイトから離れる際にそれらのファイルにサイトと同じ権限を持たせるには、サイトと同じ権限を持つ追加の機密ラベルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00420-141">If you store files with highly regulated data in a SharePoint Online site and want those files to have the same permissions as the site if the files leave the site, you need to create an additional sensitivity label whose permissions are the same as the site.</span></span>

<span data-ttu-id="00420-142">詳細については、こちらの「[機密ラベルの概要](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="00420-142">For more information, see this [overview of sensitivity labels](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels).</span></span>

### <a name="azure-information-protection-labels-and-protection"></a><span data-ttu-id="00420-143">Azure Information Protection のラベルと保護</span><span class="sxs-lookup"><span data-stu-id="00420-143">Azure Information Protection labels and protection</span></span>

<span data-ttu-id="00420-144">Azure Information Protection ラベルを使用して、組織のドキュメントとメールを分類し、必要に応じて保護できます。</span><span class="sxs-lookup"><span data-stu-id="00420-144">You can use Azure Information Protection labels to classify, and optionally protect, your organization’s documents and emails.</span></span> <span data-ttu-id="00420-145">これらのラベルは、Microsoft 365 の外部に保存されているドキュメントに適用できます。</span><span class="sxs-lookup"><span data-stu-id="00420-145">These labels can apply to documents that are stored outside of Microsoft 365.</span></span> <span data-ttu-id="00420-146">これらのラベルは、ルールと条件を定義する管理者が自動で適用するか、ユーザーが手動で適用するか、それらを組み合わせユーザーに推奨事項が提示されて適用できます。</span><span class="sxs-lookup"><span data-stu-id="00420-146">These labels can be applied automatically by administrators who define rules and conditions, manually by users, or a combination where users are given recommendations.</span></span>

<span data-ttu-id="00420-147">Azure Information Protection のラベルと保護を計画および展開するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="00420-147">To plan and deploy Azure Information Protection labels and protection, do the following:</span></span>

1. <span data-ttu-id="00420-148">[Azure Information Protection の要件](https://docs.microsoft.com/information-protection/get-started/requirements)を確認します。</span><span class="sxs-lookup"><span data-stu-id="00420-148">Review the [requirements for Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span></span>
2. <span data-ttu-id="00420-149">「[分類、ラベル付け、保護のデプロイ ロードマップ](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection)」に従います。</span><span class="sxs-lookup"><span data-stu-id="00420-149">Follow the [deployment roadmap for classification, labeling, and protection](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span></span>

<span data-ttu-id="00420-150">詳細については、「[Azure Information Protection のドキュメント](https://docs.microsoft.com/information-protection/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00420-150">For more information, see the [library of Azure Information Protection documentation](https://docs.microsoft.com/information-protection/).</span></span>

<span data-ttu-id="00420-151">既存の Azure Information Protection ラベルは機密ラベルとシームレスに連動します。</span><span class="sxs-lookup"><span data-stu-id="00420-151">Existing Azure Information Protection labels work seamlessly with sensitivity labels.</span></span> <span data-ttu-id="00420-152">たとえば、既存の Azure Information Protection ラベルとドキュメントとメールに適用されるラベルを保持できます。</span><span class="sxs-lookup"><span data-stu-id="00420-152">For example, you can keep your existing Azure Information Protection labels and the labels that are applied to documents and email.</span></span>

<span data-ttu-id="00420-153">機密ラベルと Azure Information Protection ラベルの両方がある場合、[Azure Information Protection ラベルを機密ラベルに移行する](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#how-sensitivity-labels-work-with-existing-azure-information-protection-labels)必要があります。</span><span class="sxs-lookup"><span data-stu-id="00420-153">If you have both sensitivity and Azure Information Protection labels, you should [migrate your Azure Information Protection labels to sensitivity labels](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#how-sensitivity-labels-work-with-existing-azure-information-protection-labels).</span></span>

## <a name="example-classification-for-gdpr"></a><span data-ttu-id="00420-154">例: GDPR の分類</span><span class="sxs-lookup"><span data-stu-id="00420-154">Example: Classification for GDPR</span></span>

<span data-ttu-id="00420-155">GDPR の個人データを含む分類スキーマの例については、「[個人データの分類スキーマを設計する](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00420-155">For an example classification scheme that includes personal data for GDPR, see [Architect a classification schema for personal data](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span></span>

## <a name="take-it-for-a-test-drive"></a><span data-ttu-id="00420-156">体験してみる</span><span class="sxs-lookup"><span data-stu-id="00420-156">Take it for a test drive</span></span>

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="00420-158">テスト ラボ ガイド: データの分類</span><span class="sxs-lookup"><span data-stu-id="00420-158">Test Lab Guide: Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="00420-159">中間チェックポイントとして、この手順に対応する[終了条件](infoprotect-exit-criteria.md#crit-infoprotect-step2)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="00420-159">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step2) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="00420-160">次の手順</span><span class="sxs-lookup"><span data-stu-id="00420-160">Next step</span></span>

|||
|:-------|:-----|
|![手順 3](./media/stepnumbers/Step3.png)|[<span data-ttu-id="00420-162">Office 365 のセキュリティ強化を構成する</span><span class="sxs-lookup"><span data-stu-id="00420-162">Configure increased security for Office 365</span></span>](infoprotect-configure-increased-security-office-365.md)|

