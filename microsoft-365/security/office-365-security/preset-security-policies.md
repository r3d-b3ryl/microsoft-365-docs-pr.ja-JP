---
title: 事前設定されたセキュリティ ポリシー
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理者は、標準ポリシーと厳密なポリシー設定を、Exchange Online Protection (EOP) と Microsoft Defender の保護機能全体に適用する方法をOffice 365
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 61166c78f31a86882ef0e2dc2a79683aea794040
ms.sourcegitcommit: 233989a02a3fc6db33c995ad06b1f820f08f8f0a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53383464"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="9aea0-103">EOP と Microsoft Defender でセキュリティ ポリシーを事前に設定Office 365</span><span class="sxs-lookup"><span data-stu-id="9aea0-103">Preset security policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9aea0-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="9aea0-104">**Applies to**</span></span>
- [<span data-ttu-id="9aea0-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9aea0-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9aea0-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="9aea0-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="9aea0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9aea0-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="9aea0-108">事前設定されたセキュリティ ポリシーは、推奨されるスパム、マルウェア、およびフィッシング ポリシーを一度にユーザーに適用する一元的な場所を提供します。</span><span class="sxs-lookup"><span data-stu-id="9aea0-108">Preset security policies provide a centralized location for applying all of the recommended spam, malware, and phishing policies to users at once.</span></span> <span data-ttu-id="9aea0-109">ポリシー設定は構成できません。</span><span class="sxs-lookup"><span data-stu-id="9aea0-109">The policy settings are not configurable.</span></span> <span data-ttu-id="9aea0-110">代わりに、それらは弊社によって設定され、有害なコンテンツをユーザーから遠く離し、不必要な中断を回避するバランスを取るデータセンターでの観察と経験に基づいて行われます。</span><span class="sxs-lookup"><span data-stu-id="9aea0-110">Instead, they are set by us and are based on our observations and experiences in the datacenters for a balance between keeping harmful content away from users and avoiding unnecessary disruptions.</span></span>

<span data-ttu-id="9aea0-111">この記事の残りの部分では、事前設定されたセキュリティ ポリシーと、それらを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9aea0-111">The rest of this article describes preset security policies and how to configure them.</span></span>

## <a name="what-preset-security-policies-are-made-of"></a><span data-ttu-id="9aea0-112">事前設定されたセキュリティ ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="9aea0-112">What preset security policies are made of</span></span>

<span data-ttu-id="9aea0-113">事前設定されたセキュリティ ポリシーは、次の要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="9aea0-113">Preset security policies consist of the following elements:</span></span>

- <span data-ttu-id="9aea0-114">プロファイル</span><span class="sxs-lookup"><span data-stu-id="9aea0-114">Profiles</span></span>
- <span data-ttu-id="9aea0-115">ポリシー</span><span class="sxs-lookup"><span data-stu-id="9aea0-115">Policies</span></span>
- <span data-ttu-id="9aea0-116">ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="9aea0-116">Policy settings</span></span>

<span data-ttu-id="9aea0-117">さらに、複数の事前設定されたセキュリティ ポリシーや他のポリシーが同じユーザーに適用される場合は、優先順位が重要です。</span><span class="sxs-lookup"><span data-stu-id="9aea0-117">In addition, the order of precedence is important if multiple preset security policies and other policies apply to the same person.</span></span>

### <a name="profiles-in-preset-security-policies"></a><span data-ttu-id="9aea0-118">事前設定されたセキュリティ ポリシーのプロファイル</span><span class="sxs-lookup"><span data-stu-id="9aea0-118">Profiles in preset security policies</span></span>

<span data-ttu-id="9aea0-119">プロファイルは、保護のレベルを決定します。</span><span class="sxs-lookup"><span data-stu-id="9aea0-119">A profile determines the level of protection.</span></span> <span data-ttu-id="9aea0-120">次のプロファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9aea0-120">The following profiles are available:</span></span>

- <span data-ttu-id="9aea0-121">**標準保護**: ほとんどのユーザーに適したベースライン保護プロファイル。</span><span class="sxs-lookup"><span data-stu-id="9aea0-121">**Standard protection**: A baseline protection profile that's suitable for most users.</span></span>
- <span data-ttu-id="9aea0-122">**厳密な保護**: 選択したユーザー (高価値のターゲットまたは優先度の高いユーザー) に対して、より積極的な保護プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="9aea0-122">**Strict protection**: A more aggressive protection profile for selected users (high value targets or priority users).</span></span>

<span data-ttu-id="9aea0-123">プロファイルが適用されるユーザーまたは適用されないユーザーを決定する条件と例外を含むルールを使用します。</span><span class="sxs-lookup"><span data-stu-id="9aea0-123">You use rules with conditions and exceptions that determine who the profiles are or are not applied to.</span></span>

<span data-ttu-id="9aea0-124">使用可能な条件と例外は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9aea0-124">The available conditions and exceptions are:</span></span>

- <span data-ttu-id="9aea0-125">**ユーザー**: 組織内で指定された 1 つ以上のメールボックス、メール ユーザー、またはメール連絡先。</span><span class="sxs-lookup"><span data-stu-id="9aea0-125">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
- <span data-ttu-id="9aea0-126">**グループ**: 組織内で指定された配布グループ、メール対応セキュリティ グループ、または Microsoft 365 グループ。</span><span class="sxs-lookup"><span data-stu-id="9aea0-126">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
- <span data-ttu-id="9aea0-127">**ドメイン**: 組織内で指定された [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)のすべての受信者。</span><span class="sxs-lookup"><span data-stu-id="9aea0-127">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

<span data-ttu-id="9aea0-128">各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9aea0-128">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="9aea0-129">同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="9aea0-129">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="9aea0-130">a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="9aea0-130">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

### <a name="policies-in-preset-security-policies"></a><span data-ttu-id="9aea0-131">事前設定されたセキュリティ ポリシーのポリシー</span><span class="sxs-lookup"><span data-stu-id="9aea0-131">Policies in preset security policies</span></span>

<span data-ttu-id="9aea0-132">事前設定されたセキュリティ ポリシーでは、EOP および Microsoft Defender の各種保護機能の対応するポリシーを使用Office 365。</span><span class="sxs-lookup"><span data-stu-id="9aea0-132">Preset security policies use the corresponding policies from the various protection features in EOP and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="9aea0-133">これらのポリシーは、Standard Protection _または_ **Strict Protection** の事前設定されたセキュリティ ポリシーを **ユーザー** に割り当てると作成されます。</span><span class="sxs-lookup"><span data-stu-id="9aea0-133">These policies are created _after_ you assign the **Standard protection** or **Strict protection** preset security policies to users.</span></span> <span data-ttu-id="9aea0-134">これらのポリシーは変更できない。</span><span class="sxs-lookup"><span data-stu-id="9aea0-134">You can't modify these policies.</span></span>

- <span data-ttu-id="9aea0-135">**Exchange Online Protection (EOP)** ポリシー : これには、Microsoft 365メールボックスを持Exchange Onlineスタンドアロンの EOP 組織が含Exchange Onlineされます。</span><span class="sxs-lookup"><span data-stu-id="9aea0-135">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="9aea0-136">[Standard](configure-your-spam-filter-policies.md) Preset Security Policy と **Strict Preset Security Policy という** 名前の **スパム対策ポリシー**。</span><span class="sxs-lookup"><span data-stu-id="9aea0-136">[Anti-spam policies](configure-your-spam-filter-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="9aea0-137">[Standard](configure-anti-malware-policies.md) Preset Security Policy と **Strict Preset Security Policy という** 名前の **マルウェア対策ポリシー**。</span><span class="sxs-lookup"><span data-stu-id="9aea0-137">[Anti-malware policies](configure-anti-malware-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="9aea0-138">[標準プリセット セキュリティ ポリシーと](set-up-anti-phishing-policies.md#spoof-settings)厳密な事前設定セキュリティ ポリシー (スプーフィング設定) という EOP フィッシング **対策** ポリシー。</span><span class="sxs-lookup"><span data-stu-id="9aea0-138">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings) named **Standard Preset Security Policy** and **Strict Preset Security Policy** (spoof settings).</span></span>

- <span data-ttu-id="9aea0-139">**Microsoft Defender for Office 365 ポリシー**: これには、アドオン サブスクリプションの Microsoft 365 E5または Defender をOffice 365組織が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9aea0-139">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="9aea0-140">Microsoft Defender のフィッシング対策ポリシーは、標準Office 365セキュリティポリシーと厳密な事前設定セキュリティ ポリシーと呼び、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9aea0-140">Anti-phishing policies in Microsoft Defender for Office 365 named **Standard Preset Security Policy** and **Strict Preset Security Policy**, which include:</span></span>

    - <span data-ttu-id="9aea0-141">EOP [フィッシング対策](set-up-anti-phishing-policies.md#spoof-settings) ポリシーで使用できるスプーフィング設定と同じです。</span><span class="sxs-lookup"><span data-stu-id="9aea0-141">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="9aea0-142">偽装設定</span><span class="sxs-lookup"><span data-stu-id="9aea0-142">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="9aea0-143">高度なフィッシングのしきい値</span><span class="sxs-lookup"><span data-stu-id="9aea0-143">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="9aea0-144">[セーフセキュリティ ポリシーと](set-up-safe-links-policies.md)厳密 **な** 事前設定セキュリティ ポリシーという名前 **のリンク ポリシー**。</span><span class="sxs-lookup"><span data-stu-id="9aea0-144">[Safe Links policies](set-up-safe-links-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

  - <span data-ttu-id="9aea0-145">[セーフセキュリティ ポリシーと](set-up-safe-attachments-policies.md)**厳密な** 事前設定セキュリティ ポリシーという名前の **添付ファイル ポリシー**。</span><span class="sxs-lookup"><span data-stu-id="9aea0-145">[Safe Attachments policies](set-up-safe-attachments-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

<span data-ttu-id="9aea0-146">EOP 保護は、Microsoft Defender 以外のユーザーに適用して、保護Office 365注意してください。</span><span class="sxs-lookup"><span data-stu-id="9aea0-146">Note that you can apply EOP protections to different users than Microsoft Defender for Office 365 protections.</span></span>

### <a name="policy-settings-in-preset-security-policies"></a><span data-ttu-id="9aea0-147">事前設定されたセキュリティ ポリシーのポリシー設定</span><span class="sxs-lookup"><span data-stu-id="9aea0-147">Policy settings in preset security policies</span></span>

<span data-ttu-id="9aea0-148">保護プロファイルでポリシー設定を変更できない。</span><span class="sxs-lookup"><span data-stu-id="9aea0-148">You can't modify the policy settings in the protection profiles.</span></span> <span data-ttu-id="9aea0-149">標準 **ポリシーと\*\*\*\*厳密なポリシー設定** の値については [、「EOP](recommended-settings-for-eop-and-office365.md)および Microsoft Defender のセキュリティに関する推奨設定Office 365説明されています。</span><span class="sxs-lookup"><span data-stu-id="9aea0-149">The **Standard** and **Strict** policy setting values are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365.md).</span></span>

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a><span data-ttu-id="9aea0-150">事前設定されたセキュリティ ポリシーおよび他のポリシーの優先順位</span><span class="sxs-lookup"><span data-stu-id="9aea0-150">Order of precedence for preset security policies and other policies</span></span>

<span data-ttu-id="9aea0-151">複数のポリシーがユーザーに適用される場合、次の順序が優先度の高い順から優先度の低い順に適用されます。</span><span class="sxs-lookup"><span data-stu-id="9aea0-151">When multiple policies are applied to a user, the following order is applied from highest priority to lowest priority:</span></span>

1. <span data-ttu-id="9aea0-152">**厳密な保護事前** 設定のセキュリティ ポリシー</span><span class="sxs-lookup"><span data-stu-id="9aea0-152">**Strict protection** preset security policy</span></span>
2. <span data-ttu-id="9aea0-153">**標準の保護の** 事前設定されたセキュリティ ポリシー</span><span class="sxs-lookup"><span data-stu-id="9aea0-153">**Standard protection** preset security policy</span></span>
3. <span data-ttu-id="9aea0-154">カスタム セキュリティ ポリシー</span><span class="sxs-lookup"><span data-stu-id="9aea0-154">Custom security policies</span></span>
4. <span data-ttu-id="9aea0-155">既定のセキュリティ ポリシー</span><span class="sxs-lookup"><span data-stu-id="9aea0-155">Default security policies</span></span>

<span data-ttu-id="9aea0-156">つまり、厳密な保護ポリシーの設定は、既定のポリシーの設定を上書きするカスタム ポリシーの設定を上書きする標準保護ポリシーの設定を上書きします。</span><span class="sxs-lookup"><span data-stu-id="9aea0-156">In other words, the settings of the **Strict protection** policy override the settings of the **Standard protection** policy, which overrides the settings from a custom policy, which overrides the settings from the default policy.</span></span> 

<span data-ttu-id="9aea0-157">たとえば、標準保護にセキュリティ設定が存在し、管理者がユーザーの標準保護を有効にしている場合、標準保護設定は、カスタム ポリシーまたは既定のポリシー (同じユーザーの場合) の設定に対して構成されている設定の代わりに適用されます。 </span><span class="sxs-lookup"><span data-stu-id="9aea0-157">For example, if a security setting exists in **Standard protection** and an admin has enabled the **Standard protection** for a user, then the **Standard protection** setting will be applied instead of what is configured for that setting in a custom policy or in the default policy (for the same user).</span></span> <span data-ttu-id="9aea0-158">特定のニーズを満たすために組織内の他のユーザーにカスタム ポリシーを適用する際に、標準または厳密な保護ポリシーのみを適用する組織の一部が所属している場合があります。</span><span class="sxs-lookup"><span data-stu-id="9aea0-158">Note that you might have some portion of your organization to whom you want to apply only the **Standard** or **Strict protection** policy while applying a custom policy to other users in your organization to meet specific needs.</span></span>

## <a name="assign-preset-security-policies-to-users"></a><span data-ttu-id="9aea0-159">ユーザーに事前設定されたセキュリティ ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="9aea0-159">Assign preset security policies to users</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9aea0-160">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="9aea0-160">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9aea0-161"><https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。</span><span class="sxs-lookup"><span data-stu-id="9aea0-161">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="9aea0-162">[事前設定されたセキュリティ ポリシー] **ページに直接移動するには** 、 を使用します <https://security.microsoft.com/presetSecurityPolicies> 。</span><span class="sxs-lookup"><span data-stu-id="9aea0-162">To go directly to the **Preset security policies** page, use <https://security.microsoft.com/presetSecurityPolicies>.</span></span>

- <span data-ttu-id="9aea0-163">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9aea0-163">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="9aea0-164">この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9aea0-164">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="9aea0-165">事前設定されたセキュリティ ポリシーを構成するには、組織の管理またはセキュリティ管理者の役割グループ **のメンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="9aea0-165">To configure preset security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="9aea0-166">事前設定されたセキュリティ ポリシーへの読み取り専用アクセスでは、グローバル リーダー役割グループの **メンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="9aea0-166">For read-only access to preset security policies, you need to be a member of the **Global Reader** role group.</span></span>

  <span data-ttu-id="9aea0-167">詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9aea0-167">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="9aea0-168">**注**: Azure Active Directory の対応する Azure Active Directory ロールにユーザーを追加すると、Microsoft 365 管理センター 内の他の機能に必要なアクセス許可とアクセス許可がユーザーに付与Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="9aea0-168">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="9aea0-169">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9aea0-169">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

### <a name="use-the-microsoft-365-defender-portal-to-assign-preset-security-policies-to-users"></a><span data-ttu-id="9aea0-170">ユーザーに事前Microsoft 365 Defenderポリシーを割り当てるには、このポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="9aea0-170">Use the Microsoft 365 Defender portal to assign preset security policies to users</span></span>

1. <span data-ttu-id="9aea0-171">[セキュリティ ポリシー Microsoft 365 Defender] ポータルで、[メール &**グループ**&ルールの脅威ポリシー] ページの [事前設定されたセキュリティ ポリシー] セクション \>  \>  \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="9aea0-171">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Templated policies** section \> **Preset Security Policies**.</span></span>

2. <span data-ttu-id="9aea0-172">[標準 **保護] または [\*\*\*\*厳密な保護] で、[** 編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="9aea0-172">Under **Standard protection** or **Strict protection**, click **Edit**.</span></span>

3. <span data-ttu-id="9aea0-173">[ **標準保護の適用] または** **[厳密な保護の適用] ウィザードが** 起動します。</span><span class="sxs-lookup"><span data-stu-id="9aea0-173">The **Apply Standard protection** or **Apply Strict protection** wizard starts.</span></span> <span data-ttu-id="9aea0-174">**[EOP 保護] ページで**[、EOP](#policies-in-preset-security-policies)保護が適用される内部受信者 (受信者の条件) を特定します。</span><span class="sxs-lookup"><span data-stu-id="9aea0-174">On the **EOP protections apply to** page, identify the internal recipients that the [EOP protections](#policies-in-preset-security-policies) apply to (recipient conditions):</span></span>
   - <span data-ttu-id="9aea0-175">**Users**</span><span class="sxs-lookup"><span data-stu-id="9aea0-175">**Users**</span></span>
   - <span data-ttu-id="9aea0-176">**Groups**</span><span class="sxs-lookup"><span data-stu-id="9aea0-176">**Groups**</span></span>
   - <span data-ttu-id="9aea0-177">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="9aea0-177">**Domains**</span></span>

   <span data-ttu-id="9aea0-178">適正なボックスをクリックし、値の入力を開始し、結果で希望する値を選択します。</span><span class="sxs-lookup"><span data-stu-id="9aea0-178">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="9aea0-179">必要な回数だけこの処理を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="9aea0-179">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="9aea0-180">既存の値を削除するには、削除をクリックします</span><span class="sxs-lookup"><span data-stu-id="9aea0-180">To remove an existing value, click remove</span></span> ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="9aea0-182">値の隣。</span><span class="sxs-lookup"><span data-stu-id="9aea0-182">next to the value.</span></span>

   <span data-ttu-id="9aea0-183">ユーザーやグループには、ほとんどの識別子 (名前、表示名、エイリアス、メールアドレス、アカウント名など) を使用できますが、対応する表示名が結果に表示されます。</span><span class="sxs-lookup"><span data-stu-id="9aea0-183">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="9aea0-184">ユーザーの場合、アスタリスク (\*) を単独で入力すると、使用可能なすべての値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9aea0-184">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   - <span data-ttu-id="9aea0-185">**これらのユーザー、グループ、およびドメインを除外する**: ポリシーが適用される内部の受信者に関する例外 (受信者の例外) を追加するには、このオプションを選択して例外を構成します。</span><span class="sxs-lookup"><span data-stu-id="9aea0-185">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recipient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="9aea0-186">設定と動作は、条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="9aea0-186">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="9aea0-187">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9aea0-187">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="9aea0-188">microsoft Defender for Office 365 組織では **、Office 365** 保護が適用されるページに対して Defender に連れて行き [、microsoft Defender](#policies-in-preset-security-policies) for Office 365 保護が適用される内部受信者 (受信者の条件) を特定します。</span><span class="sxs-lookup"><span data-stu-id="9aea0-188">In Microsoft Defender for Office 365 organizations, you're taken to the **Defender for Office 365 protections apply to** page to identify the internal recipients that the [Microsoft Defender for Office 365 protections](#policies-in-preset-security-policies) apply to (recipient conditions).</span></span>

   <span data-ttu-id="9aea0-189">設定と動作は **、EOP 保護がページに適用されるのとまったく同** じです。</span><span class="sxs-lookup"><span data-stu-id="9aea0-189">The settings and behavior are exactly like the **EOP protections apply to** page.</span></span>

   <span data-ttu-id="9aea0-190">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9aea0-190">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="9aea0-191">[変更 **の確認と確認] ページで** 、選択内容を確認し、[確認] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="9aea0-191">On the **Review and confirm your changes** page, verify your selections, and then click **Confirm**.</span></span>

### <a name="use-the-microsoft-365-defender-portal-to-modify-the-assignments-of-preset-security-policies"></a><span data-ttu-id="9aea0-192">事前設定されたMicrosoft 365 Defender割り当てを変更するには、このポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="9aea0-192">Use the Microsoft 365 Defender portal to modify the assignments of preset security policies</span></span>

<span data-ttu-id="9aea0-193">Standard Protection または **Strict** **Protection** セキュリティ ポリシーの割り当てを変更する手順は、事前設定されたセキュリティ ポリシーをユーザーに最初に割り当てた場合と [同じです](#use-the-microsoft-365-defender-portal-to-assign-preset-security-policies-to-users)。</span><span class="sxs-lookup"><span data-stu-id="9aea0-193">The steps to modify the assignment of the **Standard protection** or **Strict protection** security policy are the same as when you initially [assigned the preset security policies to users](#use-the-microsoft-365-defender-portal-to-assign-preset-security-policies-to-users).</span></span>

<span data-ttu-id="9aea0-194">既存の条件と例外 **を** 維持しながら標準保護ポリシーまたは **厳密** な保護セキュリティ ポリシーを無効にするには、トグルを [無効] トグル オフ **に** ![ スライドします ](../../media/scc-toggle-off.png) 。</span><span class="sxs-lookup"><span data-stu-id="9aea0-194">To disable the **Standard protection** or **Strict protection** security policies while still preserving the existing conditions and exceptions, slide the toggle to **Disabled** ![Toggle Off](../../media/scc-toggle-off.png).</span></span> <span data-ttu-id="9aea0-195">ポリシーを有効にするには、トグルを [有効] トグル **オンにスライド** ![ します ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="9aea0-195">To enable the policies, slide the toggle to **Enabled** ![Toggle On](../../media/scc-toggle-on.png).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="9aea0-196">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="9aea0-196">How do you know these procedures worked?</span></span>

<span data-ttu-id="9aea0-197">標準保護または厳密な保護セキュリティ ポリシーがユーザーに正常に割り当てられているか確認するには、既定値が標準保護設定とは異なる保護設定を使用します。これは、厳密な保護設定とは異なります。</span><span class="sxs-lookup"><span data-stu-id="9aea0-197">To verify that you've successfully assigned the **Standard protection** or **Strict protection** security policy to a user, use a protection setting where the default value is different than the **Standard protection** setting, which is different that the **Strict protection** setting.</span></span>

<span data-ttu-id="9aea0-198">たとえば、スパムとして検出された (信頼度の高いスパムではない) 電子メールの場合、メッセージが標準保護ユーザーの迷惑メールフォルダーに配信され、厳密な保護ユーザーに対して検疫済みである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9aea0-198">For example, for email that's detected as spam (not high confidence spam) verify that the message is delivered to the Junk Email folder for **Standard protection** users, and quarantined for **Strict protection** users.</span></span>

<span data-ttu-id="9aea0-199">または、バルク メールの場合は、BCL 値 6 以上が標準保護ユーザーの迷惑メールフォルダーにメッセージを配信し、BCL 値 4 以上が厳密な保護ユーザーのメッセージを検疫します。 [](bulk-complaint-level-values.md)</span><span class="sxs-lookup"><span data-stu-id="9aea0-199">Or, for [bulk mail](bulk-complaint-level-values.md), verify that the BCL value 6 or higher delivers the message to the Junk Email folder for **Standard protection** users, and the BCL value 4 or higher quarantines the message for **Strict protection** users.</span></span>
