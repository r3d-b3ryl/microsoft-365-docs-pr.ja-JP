---
title: '手順 2: 環境の分類を構成する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 組織内のデータを分類するさまざまな方法について理解し、構成します。
ms.openlocfilehash: bee0885eb3f8899560532895d1558723b281ab02
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869197"
---
# <a name="step-2-configure-classification-for-your-environment"></a><span data-ttu-id="ad0e0-103">手順 2: 環境の分類を構成する</span><span class="sxs-lookup"><span data-stu-id="ad0e0-103">Step 2: Configure classification for your environment</span></span>

<span data-ttu-id="ad0e0-104">*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="ad0e0-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="ad0e0-105">この手順では、法務/コンプライアンス チームと連携して組織のデータの分類方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="ad0e0-105">In Step 3, you work with your legal and compliance teams to define a classification scheme for your organization’s data.</span></span>

## <a name="microsoft-classifications"></a><span data-ttu-id="ad0e0-106">Microsoft の分類方法</span><span class="sxs-lookup"><span data-stu-id="ad0e0-106">Microsoft classifications</span></span>

<span data-ttu-id="ad0e0-107">Microsoft 365 には、次の 3 種類の分類方法があります。</span><span class="sxs-lookup"><span data-stu-id="ad0e0-107">Microsoft 365 includes three types of classification:</span></span>

- <span data-ttu-id="ad0e0-108">Office 365 の機密情報タイプ</span><span class="sxs-lookup"><span data-stu-id="ad0e0-108">Sensitive information types for Office 365</span></span>
- <span data-ttu-id="ad0e0-109">Office 365 のラベル</span><span class="sxs-lookup"><span data-stu-id="ad0e0-109">Office 365 labels</span></span>
- <span data-ttu-id="ad0e0-110">Azure Information Protection のラベルと保護</span><span class="sxs-lookup"><span data-stu-id="ad0e0-110">Azure Information Protection labels and protection</span></span>

### <a name="sensitive-information-types-for-office-365"></a><span data-ttu-id="ad0e0-111">Office 365 の機密情報タイプ</span><span class="sxs-lookup"><span data-stu-id="ad0e0-111">Sensitive information types for Office 365</span></span>

<span data-ttu-id="ad0e0-p101">Office 365 の機密情報タイプでは、検索などの自動プロセスで特定の種類の情報 (医療サービス番号、クレジットカード番号など) を認識する方法が定義されます。機密情報タイプを使用して、機密データを検出し、データ損失防止ルールおよびポリシーを適用してこのデータを保護します。詳細については、「[データ損失防止ポリシーの概要](https://support.office.com/article/overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e)」を参照してください。たとえば、機密情報タイプは、一般データ保護規則 (GDPR) などのコンプライアンスや規制の要件に準拠する際に特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ad0e0-p101">Sensitive information types for Office 365 define how automated processes such as search recognize specific information types such as health service numbers and credit card numbers. You use sensitive information types to find sensitive data and apply data loss prevention rules and policies to protect this data. For more information, see [Overview of data loss prevention policies](https://support.office.com/article/overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e). For example, sensitive information types are especially helpful for meeting compliance and regulation requirements, such as for the General Data Protection Regulation (GDPR).</span></span>

### <a name="office-365-labels"></a><span data-ttu-id="ad0e0-116">Office 365 のラベル</span><span class="sxs-lookup"><span data-stu-id="ad0e0-116">Office 365 labels</span></span>
<span data-ttu-id="ad0e0-p102">個人データや、SharePoint Online と OneDrive for Business に保存されている高度な規制を実施する企業秘密ファイルには、Office 365 のラベルを使用できます。ラベルの作成方法などの詳細については、「[ラベルの概要](https://support.office.com/article/overview-of-labels-af398293-c69d-465e-a249-d74561552d30)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad0e0-p102">You can use Office 365 labels for personal data and for highly regulated and trade secret files stored in SharePoint Online and OneDrive for Business. For more information, including how to create them, see [Overview of labels](https://support.office.com/article/overview-of-labels-af398293-c69d-465e-a249-d74561552d30).</span></span>

<span data-ttu-id="ad0e0-p103">Office 365 のラベルを使用する場合は、保護レベルごとに 1 つ以上のラベルを構成する必要があります。たとえば、以下の 3 種類のラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="ad0e0-p103">If you decide to use Office 365 labels, you should configure at least one for each level of protection. For example, create three labels for:</span></span>

- <span data-ttu-id="ad0e0-121">基準</span><span class="sxs-lookup"><span data-stu-id="ad0e0-121">Baseline</span></span>
- <span data-ttu-id="ad0e0-122">機密</span><span class="sxs-lookup"><span data-stu-id="ad0e0-122">Sensitive</span></span>
- <span data-ttu-id="ad0e0-123">高度な規制</span><span class="sxs-lookup"><span data-stu-id="ad0e0-123">Highly regulated</span></span>

### <a name="azure-information-protection-labels-and-protection"></a><span data-ttu-id="ad0e0-124">Azure Information Protection のラベルと保護</span><span class="sxs-lookup"><span data-stu-id="ad0e0-124">Azure Information Protection labels and protection</span></span>

<span data-ttu-id="ad0e0-p104">Azure Information Protection のラベルを使用して、組織内の文書やメールを分類し、オプションで保護できます。これらのラベルは、Office 365 外部に保存されている文書にも適用できます。管理者がルールや条件を定義してラベルを自動的に適用するか、ユーザーがラベルを手動で適用するか、あるいは推奨される場合はこれらを組み合わせて適用できます。</span><span class="sxs-lookup"><span data-stu-id="ad0e0-p104">You can use Azure Information Protection labels to classify, and optionally protect, your organization’s documents and emails. These labels can apply to documents that are stored outside of Office 365. These labels can be applied automatically by administrators who define rules and conditions, manually by users, or a combination where users are given recommendations.</span></span>

<span data-ttu-id="ad0e0-128">Azure Information Protection のラベルと保護を計画および展開するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ad0e0-128">To plan and deploy Azure Information Protection labels and protection, do the following:</span></span>

1. <span data-ttu-id="ad0e0-129">[Azure Information Protection の要件](https://docs.microsoft.com/information-protection/get-started/requirements)を確認します。</span><span class="sxs-lookup"><span data-stu-id="ad0e0-129">Review the [requirements for Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span></span>
2. <span data-ttu-id="ad0e0-130">「[分類、ラベル付け、保護のデプロイ ロードマップ](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection)」に従います。</span><span class="sxs-lookup"><span data-stu-id="ad0e0-130">Follow the [deployment roadmap for classification, labeling, and protection](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span></span>

<span data-ttu-id="ad0e0-131">詳細については、「[Azure Information Protection のドキュメント](https://docs.microsoft.com/information-protection/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad0e0-131">For more information, see the [library of Azure Information Protection documentation](https://docs.microsoft.com/information-protection/).</span></span>

## <a name="classification-for-gdpr"></a><span data-ttu-id="ad0e0-132">GDPR の分類</span><span class="sxs-lookup"><span data-stu-id="ad0e0-132">Classification for GDPR</span></span>

<span data-ttu-id="ad0e0-133">GDPR の個人データを含む分類方法の例については、「[個人データの分類スキーマを設計する](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad0e0-133">For an example classification scheme that includes personal data for GDPR, see [Architect a classification schema for personal data](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span></span>

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="ad0e0-135">テスト ラボ ガイド: データの分類</span><span class="sxs-lookup"><span data-stu-id="ad0e0-135">Test Lab Guide: Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="ad0e0-136">中間チェックポイントとして、この手順に対応する[終了条件](infoprotect-exit-criteria.md#crit-infoprotect-step3)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="ad0e0-136">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step3) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="ad0e0-137">次の手順</span><span class="sxs-lookup"><span data-stu-id="ad0e0-137">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="ad0e0-138">Office 365 のセキュリティ強化を構成する</span><span class="sxs-lookup"><span data-stu-id="ad0e0-138">Configure increased security for Office 365</span></span>](infoprotect-configure-increased-security-office-365.md)|

