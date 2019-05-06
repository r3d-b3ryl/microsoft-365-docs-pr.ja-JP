---
title: '手順 4: Windows Information Protection の構成する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 の Windows Information Protection について理解し、展開します。
ms.openlocfilehash: ca706d49053bbc100a633afb74c7c978de2e4c5c
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2019
ms.locfileid: "33353105"
---
# <a name="step-4-configure-windows-information-protection"></a><span data-ttu-id="11296-103">手順 4: Windows Information Protection の構成する</span><span class="sxs-lookup"><span data-stu-id="11296-103">Step 4: Configure Windows Information Protection</span></span>

<span data-ttu-id="11296-104">*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="11296-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="11296-105">個人用デバイスが業務に使用されるようになったことで、アプリやデバイスによって非公開の組織データが漏えいされるリスクが高まっています。</span><span class="sxs-lookup"><span data-stu-id="11296-105">With more personal devices being used for work, there’s increased risk for apps and devices to leak private organization data.</span></span> <span data-ttu-id="11296-106">例えば、従業員はソーシャル メディア サイトに将来の製品のマーケティング計画の写真を誤って送信したり、機密性の高い情報を含むファイルをパブリック クラウド ストレージに保存したりします。</span><span class="sxs-lookup"><span data-stu-id="11296-106">For example, an employee inadvertently sends a picture of a marketing plan for a future product to a social media site or saves a file containing highly confidential information to their public cloud storage.</span></span> 

<span data-ttu-id="11296-107">Windows Information Protection (WIP) は、Windows 10 デバイス上のこのようなデータの漏えいを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="11296-107">Windows Information Protection (WIP) helps protect against these types of data leakage on Windows 10 devices.</span></span> <span data-ttu-id="11296-108">詳細については、「[WIP を使用してエンタープライズ データを保護する](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11296-108">For more information, see [Protect your enterprise data using WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).</span></span>

<span data-ttu-id="11296-109">Microsoft 365 Enterprise では、WIP は Windows 10 Enterprise と Microsoft Intune を組み合わせたもので、サブスクリプションに Enterprise Mobility + Security (EMS) と共に含まれています。</span><span class="sxs-lookup"><span data-stu-id="11296-109">In Microsoft 365 Enterprise, WIP is a combination of Windows 10 Enterprise and Microsoft Intune, which is included with Enterprise Mobility + Security (EMS) in your subscription.</span></span> 

<span data-ttu-id="11296-110">Microsoft 365 Enterprise を使用して組織に WIP を展開するには、次の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="11296-110">To deploy WIP in your organization with Microsoft 365 Enterprise:</span></span>

1. <span data-ttu-id="11296-111">Windows デバイスを Intune に登録します。</span><span class="sxs-lookup"><span data-stu-id="11296-111">Enroll your Windows devices in Intune.</span></span> <span data-ttu-id="11296-112">これは、[フェーズ 5: モバイル デバイス管理](mobility-infrastructure.md)で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11296-112">You should have done this in [Phase 5: Mobile Device Management](mobility-infrastructure.md).</span></span>
2. <span data-ttu-id="11296-113">[WIP 用の Intune ポリシー](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure)を作成します。</span><span class="sxs-lookup"><span data-stu-id="11296-113">Create an [Intune policy for WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).</span></span>
  - <span data-ttu-id="11296-114">保護アプリのリストに記入してください。</span><span class="sxs-lookup"><span data-stu-id="11296-114">Ensure that you have filled out your Protected apps list.</span></span>
  - <span data-ttu-id="11296-115">WIP の保護レベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="11296-115">Choose your WIP protection level.</span></span>

<span data-ttu-id="11296-116">[System Center Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm)と共に WIP を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="11296-116">You can also use WIP with [System Center Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm).</span></span> 

<span data-ttu-id="11296-117">詳細については、「[WIP のベスト プラクティス]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11296-117">See [WIP best practices]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip) for more information.</span></span>

<span data-ttu-id="11296-118">中間チェックポイントとして、この手順に対応する[終了条件](infoprotect-exit-criteria.md#crit-infoprotect-step4)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="11296-118">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step4) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="11296-119">次の手順</span><span class="sxs-lookup"><span data-stu-id="11296-119">Next step</span></span>


|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="11296-120">Office 365 データ損失防止を構成する</span><span class="sxs-lookup"><span data-stu-id="11296-120">Configure Office 365 Data Loss Prevention</span></span>](infoprotect-data-loss-prevention.md)|


