---
title: '手順 1: セキュリティおよび情報保護のレベルを定義する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 組織のセキュリティおよび情報保護のレベルについて理解し、構成します。
ms.openlocfilehash: bc55fab7b450685268ae89648ae18292e5494ce8
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869240"
---
# <a name="step-1-define-security-and-information-protection-levels"></a><span data-ttu-id="2557c-103">手順 1: セキュリティおよび情報保護のレベルを定義する</span><span class="sxs-lookup"><span data-stu-id="2557c-103">Step 1: Define security and information protection levels</span></span>

<span data-ttu-id="2557c-104">*この手順は必須であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="2557c-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="2557c-p101">この手順では、組織のセキュリティと保護のレベルを定義します。たとえば、営業部門に必要なセキュリティ レベルは低く、研究部門とその貴重な知的財産には、ファイルを暗号化して研究員だけにアクセスを制限する高いセキュリティ レベルが必要かもしれません。</span><span class="sxs-lookup"><span data-stu-id="2557c-p101">In Step 1, you'll define the levels of security and protection for your organization. For example, your sales department might only require a low security level, However, your research department and its highly valuable intellectual property might require a high security level that encrypts files and limits access to only research staff.</span></span>

<span data-ttu-id="2557c-p102">独自のセキュリティ レベルを定義でき、またこのようなセキュリティ レベルが既に定義されていることがありますが、少なくとも 3 種類の適用可能なセキュリティ/保護レベルを使用する計画を策定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2557c-p102">Although you can define your own security levels and might already have some in place, Microsoft recommendations that you develop a plan to use at least three different levels of security and protection that can be applied. Here is a list to get you started:</span></span> 

- <span data-ttu-id="2557c-p103">**基準:** これは、データの保護と、データにアクセスする ID およびデバイスの最小限の標準です。基準セキュリティ/保護の推奨事項に従うと、多くの組織や部門のニーズに対応した強力な既定の保護を導入できます。</span><span class="sxs-lookup"><span data-stu-id="2557c-p103">**Baseline:** This is a minimum standard for protecting data and for the identities and devices that access your data. You can follow baseline security and protection recommendations to provide strong default protection that meets the needs of many organizations or their departments.</span></span>
- <span data-ttu-id="2557c-p104">**機密:** これは、基準レベルよりも高いレベルで保護する必要があるデータのサブセットに対する保護を強化します。Office 365 環境で特定のデータ セットにこの強化された保護を適用できます。機密データにアクセスする ID およびデバイスには、機密セキュリティ レベルを適用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2557c-p104">**Sensitive:** This is additional protection for a subset of your data that must be protected beyond the baseline level. You can apply this increased protection to specific data sets in your Office 365 environment. Microsoft also recommends applying the sensitive security level to identities and devices that access sensitive data.</span></span>
- <span data-ttu-id="2557c-p105">**高度な規制:** これは、機密性が高いごくわずかなデータ (知的財産または企業秘密として扱われるデータ)、または厳しいセキュリティ規制に準拠する必要があるデータを使用する組織のための最高保護レベルです。Microsoft 365 Enterprise には、組織がこのようなセキュリティの厳しい要件に対応できるようにする機能 (ID およびデバイスを対象とする同等の保護機能を含む) があります。</span><span class="sxs-lookup"><span data-stu-id="2557c-p105">**Highly regulated:** This is the highest level of protection for organizations that typically have a very small amount of data that is highly classified, considered intellectual property or trade secrets, or data that must adhere to strict security regulations. Microsoft 365 Enterprise has capabilities to help organizations meet these high security requirements, including equivalent protection for identities and devices.</span></span>

<span data-ttu-id="2557c-116">詳細については、[3 つの層による保護](microsoft-365-policies-configurations.md#three-tiers-of-protection)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2557c-116">For more information, see [Three tiers of protection](microsoft-365-policies-configurations.md#three-tiers-of-protection).</span></span>

<span data-ttu-id="2557c-117">この結果として、セキュリティと情報保護のレベルが決定します。</span><span class="sxs-lookup"><span data-stu-id="2557c-117">The result is a determination of your security and information protection levels.</span></span>

<span data-ttu-id="2557c-118">中間チェックポイントとして、この手順に対応する[終了条件](infoprotect-exit-criteria.md#crit-infoprotect-step1)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="2557c-118">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step1) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="2557c-119">次の手順</span><span class="sxs-lookup"><span data-stu-id="2557c-119">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)|[<span data-ttu-id="2557c-120">環境のデータ分類方法を構成する</span><span class="sxs-lookup"><span data-stu-id="2557c-120">Configure classification for your environment</span></span>](infoprotect-configure-classification.md)|
