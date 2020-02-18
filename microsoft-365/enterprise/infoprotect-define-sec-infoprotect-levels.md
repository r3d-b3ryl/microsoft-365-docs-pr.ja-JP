---
title: '手順 1: セキュリティおよび情報保護のレベルを定義する'
f1.keywords:
- NOCSH
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
description: 組織のセキュリティおよび情報保護のレベルについて理解し、構成します。
ms.openlocfilehash: d3ba5f490b7aa80c9149a0451059914c78b8f2f1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067214"
---
# <a name="step-1-define-security-and-information-protection-levels"></a><span data-ttu-id="cbabc-103">手順 1: セキュリティおよび情報保護のレベルを定義する</span><span class="sxs-lookup"><span data-stu-id="cbabc-103">Step 1: Define security and information protection levels</span></span>

<span data-ttu-id="cbabc-104">*この手順は必須であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="cbabc-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![フェーズ 6: 情報保護](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="cbabc-106">この手順では、組織のセキュリティと保護のレベルを定義します。</span><span class="sxs-lookup"><span data-stu-id="cbabc-106">In this step, you'll define the levels of security and protection for your organization.</span></span> <span data-ttu-id="cbabc-107">たとえば、営業部門には必要なセキュリティ レベルは低い可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cbabc-107">For example, your sales department might only require a low security level.</span></span> <span data-ttu-id="cbabc-108">一方で研究部門とその貴重な知的財産には、ファイルを暗号化し研究員だけにアクセスを制限する高いセキュリティ レベルが必要かもしれません。</span><span class="sxs-lookup"><span data-stu-id="cbabc-108">However, your research department and its highly valuable intellectual property might require a high security level that encrypts files and limits access to only research staff.</span></span>

<span data-ttu-id="cbabc-109">独自のセキュリティ レベルを定義でき、このようなセキュリティ レベルが既に定義されていることがありますが、少なくとも 3 種類の適用可能なセキュリティおよび保護のレベルを使用する計画を策定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cbabc-109">Although you can define your own security levels and might already have some in place, Microsoft recommends that you develop a plan to use at least three different levels of security and protection that can be applied.</span></span> <span data-ttu-id="cbabc-110">作業を開始するためのリストを次に示します。</span><span class="sxs-lookup"><span data-stu-id="cbabc-110">Here is a list to get you started:</span></span> 

- <span data-ttu-id="cbabc-p103">**基準:** これは、データの保護と、データにアクセスする ID およびデバイスの最小限の標準です。基準セキュリティ/保護の推奨事項に従うと、多くの組織や部門のニーズに対応した強力な既定の保護を導入できます。</span><span class="sxs-lookup"><span data-stu-id="cbabc-p103">**Baseline:** This is a minimum standard for protecting data and for the identities and devices that access your data. You can follow baseline security and protection recommendations to provide strong default protection that meets the needs of many organizations or their departments.</span></span>
- <span data-ttu-id="cbabc-p104">**機密:** これは、基準レベルよりも高いレベルで保護する必要があるデータのサブセットに対する保護を強化します。Office 365 環境で特定のデータ セットにこの強化された保護を適用できます。機密データにアクセスする ID およびデバイスには、機密セキュリティ レベルを適用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cbabc-p104">**Sensitive:** This is additional protection for a subset of your data that must be protected beyond the baseline level. You can apply this increased protection to specific data sets in your Office 365 environment. Microsoft also recommends applying the sensitive security level to identities and devices that access sensitive data.</span></span>
- <span data-ttu-id="cbabc-p105">**高度な規制:** これは、機密性が高いごくわずかなデータ (知的財産または企業秘密として扱われるデータ)、または厳しいセキュリティ規制に準拠する必要があるデータを使用する組織のための最高保護レベルです。Microsoft 365 Enterprise には、組織がこのようなセキュリティの厳しい要件に対応できるようにする機能 (ID およびデバイスを対象とする同等の保護機能を含む) があります。</span><span class="sxs-lookup"><span data-stu-id="cbabc-p105">**Highly regulated:** This is the highest level of protection for organizations that typically have a very small amount of data that is highly classified, considered intellectual property or trade secrets, or data that must adhere to strict security regulations. Microsoft 365 Enterprise has capabilities to help organizations meet these high security requirements, including equivalent protection for identities and devices.</span></span>

<span data-ttu-id="cbabc-118">詳細については、[3 つの層による保護](microsoft-365-policies-configurations.md#three-tiers-of-protection)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbabc-118">For more information, see [Three tiers of protection](microsoft-365-policies-configurations.md#three-tiers-of-protection).</span></span>

<span data-ttu-id="cbabc-119">中間チェックポイントとして、この手順に対応する[終了条件](infoprotect-exit-criteria.md#crit-infoprotect-step1)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="cbabc-119">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step1) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="cbabc-120">次の手順</span><span class="sxs-lookup"><span data-stu-id="cbabc-120">Next step</span></span>

|||
|:-------|:-----|
|![手順 2](../media/stepnumbers/Step2.png)|[<span data-ttu-id="cbabc-122">環境のデータ分類方法を構成する</span><span class="sxs-lookup"><span data-stu-id="cbabc-122">Configure classification for your environment</span></span>](infoprotect-configure-classification.md)|
