---
title: Windows 10 コンピューターをセキュリティで保護する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- TRN_SMB
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Microsoft 365 Business Premium のセットアップ後に Windows 10 Pc をセキュリティで保護する方法について説明します。
ms.openlocfilehash: a70fcd330fe6ef330fac08512aded4d8913313d5
ms.sourcegitcommit: 1780359234abdf081097c8064438d415da92fb85
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778386"
---
# <a name="secure-windows-10-computers"></a><span data-ttu-id="f38cf-103">Windows 10 コンピューターをセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="f38cf-103">Secure Windows 10 computers</span></span>

<span data-ttu-id="f38cf-104">この記事は、Microsoft 365 Business Premium に適用されます。</span><span class="sxs-lookup"><span data-stu-id="f38cf-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="f38cf-105">Microsoft 365 Business Premium を [セットアップ](set-up.md) した後は、組織内の Windows 10 コンピューターを盗難から保護し、ウイルスやマルウェアのような悪意のある脅威から保護することができます。</span><span class="sxs-lookup"><span data-stu-id="f38cf-105">After you have [set up](set-up.md) Microsoft 365 Business Premium, it is time to protect the Windows 10 computers in your org from theft, and malicious threats like viruses and malware.</span></span>

## <a name="to-secure-your-windows-10-pcs"></a><span data-ttu-id="f38cf-106">Windows 10 Pc をセキュリティで保護するには</span><span class="sxs-lookup"><span data-stu-id="f38cf-106">To secure your Windows 10 PCs</span></span>

1. <span data-ttu-id="f38cf-107">グローバル管理者の資格情報を使用して、[Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="f38cf-107">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 
2. <span data-ttu-id="f38cf-108">左側のナビゲーションで、[ **セットアップ** ] を選択し、[ **サインインとセキュリティ**] で [ **Windows 10 コンピューターのセキュリティ保護**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f38cf-108">On the left nav, select **Setup** and then, under **Sign-in and security**, choose **Secure your Windows 10 computers**.</span></span> <span data-ttu-id="f38cf-109">[ **表示** ] を選んで開始します。</span><span class="sxs-lookup"><span data-stu-id="f38cf-109">Choose **View** to get started.</span></span>
3. <span data-ttu-id="f38cf-110">[ **Windows 10 コンピューターのセキュリティ保護** ] ページで、有効にする内容と、ユーザーへの影響について理解するためのすべての情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="f38cf-110">On the **Secure your Windows 10 computers** page, read all the information to understand what you are turning on, and what the user impact is.</span></span>

    <span data-ttu-id="f38cf-111">ページの上部にある [ **はじめ**に] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f38cf-111">On the top of the page, choose **Get started**.</span></span>

4. <span data-ttu-id="f38cf-112">[ **Windows 10 コンピューターをセキュリティで保護** する] ウィンドウで、有効にするオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="f38cf-112">On the **Secure your Windows 10 computers** pane, select the options you want to turn on.</span></span> <span data-ttu-id="f38cf-113">設定の詳細については、「 [Windows 10 デバイスをセキュリティで保護](secure-windows-10-devices.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f38cf-113">For more information about the settings, see [Secure Windows 10 devices](secure-windows-10-devices.md).</span></span> 
    
    <span data-ttu-id="f38cf-114">ほとんどの組織では、ここに示すオプションは高いレベルのセキュリティを提供していますが、組織でセキュリティのニーズが複雑な場合は、定義済みのセキュリティ基準を使用して Windows 10 デバイスをセキュリティで保護することもできます。</span><span class="sxs-lookup"><span data-stu-id="f38cf-114">For most organizations, the options here offer a good level of security, however, if your organization has more complex security needs, you can also use pre-defined security baselines to secure  your Windows 10 devices.</span></span> <span data-ttu-id="f38cf-115">詳細については、「 [Windows 10 デバイスのセキュリティベースライン](https://docs.microsoft.com/mem/intune/protect/security-baselines)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f38cf-115">For more information, see [security baselines for Windows 10 devices](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>   

1. <span data-ttu-id="f38cf-116">[ **設定の適用**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f38cf-116">Choose **Apply settings**.</span></span>

    <span data-ttu-id="f38cf-117">これらの設定は、組織内のすべてのユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="f38cf-117">These settings will apply to all users in your organization.</span></span> <span data-ttu-id="f38cf-118">さまざまなセキュリティグループに対して異なるポリシーを設定するには、「 [Windows 10 pc のデバイス保護設定を設定](protection-settings-for-windows-10-pcs.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f38cf-118">To set up different policies for different security groups, see [Set device protection settings for Windows 10 PCs](protection-settings-for-windows-10-pcs.md).</span></span>