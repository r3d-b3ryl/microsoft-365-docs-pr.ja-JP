---
title: '手順 4: Windows Information Protection の構成する'
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
description: Microsoft 365 の Windows Information Protection について理解し、展開します。
ms.openlocfilehash: 655ff33c3fd1bba822937618d801db76b7881977
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067164"
---
# <a name="step-4-configure-windows-information-protection"></a><span data-ttu-id="2ea37-103">手順 4: Windows Information Protection の構成する</span><span class="sxs-lookup"><span data-stu-id="2ea37-103">Step 4: Configure Windows Information Protection</span></span>

<span data-ttu-id="2ea37-104">*この手順は省略可能で、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます*</span><span class="sxs-lookup"><span data-stu-id="2ea37-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![フェーズ 6: 情報保護](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="2ea37-106">個人用デバイスが業務に使用されるようになったことで、アプリやデバイスによって非公開の組織データが漏えいされるリスクが高まっています。</span><span class="sxs-lookup"><span data-stu-id="2ea37-106">With more personal devices being used for work, there’s increased risk for apps and devices to leak private organization data.</span></span> <span data-ttu-id="2ea37-107">例えば、従業員はソーシャル メディア サイトに将来の製品のマーケティング計画の写真を誤って送信したり、機密性の高い情報を含むファイルをパブリック クラウド ストレージに保存したりします。</span><span class="sxs-lookup"><span data-stu-id="2ea37-107">For example, an employee inadvertently sends a picture of a marketing plan for a future product to a social media site or saves a file containing highly confidential information to their public cloud storage.</span></span> 

<span data-ttu-id="2ea37-108">Windows Information Protection (WIP) は、Windows 10 デバイス上のこのようなデータの漏えいを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="2ea37-108">Windows Information Protection (WIP) helps protect against these types of data leakage on Windows 10 devices.</span></span> <span data-ttu-id="2ea37-109">詳細については、「[WIP を使用してエンタープライズ データを保護する](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ea37-109">For more information, see [Protect your enterprise data using WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).</span></span>

<span data-ttu-id="2ea37-110">Microsoft 365 Enterprise では、WIP は Windows 10 Enterprise と Microsoft Intune を組み合わせたもので、そしてそれは、サブスクリプションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="2ea37-110">In Microsoft 365 Enterprise, WIP is a combination of Windows 10 Enterprise and Microsoft Intune, which is included with your subscription.</span></span> 

<span data-ttu-id="2ea37-111">Microsoft 365 Enterprise を使用して組織に WIP を展開するには、次の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="2ea37-111">To deploy WIP in your organization with Microsoft 365 Enterprise:</span></span>

1. <span data-ttu-id="2ea37-112">Windows デバイスを Intune に登録します。</span><span class="sxs-lookup"><span data-stu-id="2ea37-112">Enroll your Windows devices in Intune.</span></span> <span data-ttu-id="2ea37-113">これは、[フェーズ 5: モバイル デバイス管理](mobility-infrastructure.md)で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ea37-113">You should have done this in [Phase 5: Mobile Device Management](mobility-infrastructure.md).</span></span>
2. <span data-ttu-id="2ea37-114">[WIP 用の Intune ポリシー](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure)を作成します。</span><span class="sxs-lookup"><span data-stu-id="2ea37-114">Create an [Intune policy for WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).</span></span>
  - <span data-ttu-id="2ea37-115">保護アプリのリストに記入してください。</span><span class="sxs-lookup"><span data-stu-id="2ea37-115">Ensure that you have filled out your Protected apps list.</span></span>
  - <span data-ttu-id="2ea37-116">WIP の保護レベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="2ea37-116">Choose your WIP protection level.</span></span>

<span data-ttu-id="2ea37-117">[Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm) で WIPを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="2ea37-117">You can also use WIP with [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm).</span></span> 

<span data-ttu-id="2ea37-118">詳細については、「[WIP のベスト プラクティス]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ea37-118">See [WIP best practices]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip) for more information.</span></span>

<span data-ttu-id="2ea37-119">中間チェックポイントとして、この手順に対応する[終了条件](infoprotect-exit-criteria.md#crit-infoprotect-step4)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="2ea37-119">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step4) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="2ea37-120">次の手順</span><span class="sxs-lookup"><span data-stu-id="2ea37-120">Next step</span></span>

|||
|:-------|:-----|
|![手順 5](../media/stepnumbers/Step5.png)|[<span data-ttu-id="2ea37-122">Office 365 データ損失防止を構成する</span><span class="sxs-lookup"><span data-stu-id="2ea37-122">Configure Office 365 Data Loss Prevention</span></span>](infoprotect-data-loss-prevention.md)|


