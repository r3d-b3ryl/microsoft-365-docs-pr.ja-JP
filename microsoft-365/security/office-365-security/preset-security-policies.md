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
description: 管理者は、Exchange Online Protection (EOP) と Microsoft Defender for microsoft Defender for Office 365 の保護機能全体に標準ポリシー設定と厳密なポリシー設定を適用する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b57c13517d9fd41bcafea5c9d672da0e6b581ad7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926762"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="4aa55-103">EOP および Microsoft Defender の 365 用に事前設定Officeポリシー</span><span class="sxs-lookup"><span data-stu-id="4aa55-103">Preset security policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4aa55-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="4aa55-104">**Applies to**</span></span>
- [<span data-ttu-id="4aa55-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4aa55-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="4aa55-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="4aa55-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="4aa55-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4aa55-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="4aa55-108">事前設定されたセキュリティ ポリシーは、推奨されるスパム、マルウェア、およびフィッシング ポリシーを一度にユーザーに適用する一元的な場所を提供します。</span><span class="sxs-lookup"><span data-stu-id="4aa55-108">Preset security policies provide a centralized location for applying all of the recommended spam, malware, and phishing policies to users at once.</span></span> <span data-ttu-id="4aa55-109">ポリシー設定は構成できません。</span><span class="sxs-lookup"><span data-stu-id="4aa55-109">The policy settings are not configurable.</span></span> <span data-ttu-id="4aa55-110">代わりに、それらは当社によって設定され、有害なコンテンツをユーザーから離れ、作業を中断することなく維持するバランスを取るデータセンターでの観察と経験に基づいて行われます。</span><span class="sxs-lookup"><span data-stu-id="4aa55-110">Instead, they are set by us and are based on our observations and experiences in the datacenters for a balance between keeping harmful content away from users without disrupting their work.</span></span>

<span data-ttu-id="4aa55-111">このトピックの残りの部分では、事前設定されたセキュリティ ポリシーと、それらを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4aa55-111">The rest of this topic describes preset security policies and how to configure them.</span></span>

## <a name="what-preset-security-policies-are-made-of"></a><span data-ttu-id="4aa55-112">事前設定されたセキュリティ ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="4aa55-112">What preset security policies are made of</span></span>

<span data-ttu-id="4aa55-113">事前設定されたセキュリティ ポリシーは、次の要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="4aa55-113">Preset security policies consist of the following elements:</span></span>

- <span data-ttu-id="4aa55-114">プロファイル</span><span class="sxs-lookup"><span data-stu-id="4aa55-114">Profiles</span></span>
- <span data-ttu-id="4aa55-115">Policies</span><span class="sxs-lookup"><span data-stu-id="4aa55-115">Policies</span></span>
- <span data-ttu-id="4aa55-116">ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="4aa55-116">Policy settings</span></span>

<span data-ttu-id="4aa55-117">さらに、複数の事前設定されたセキュリティ ポリシーや他のポリシーが同じユーザーに適用される場合は、優先順位が重要です。</span><span class="sxs-lookup"><span data-stu-id="4aa55-117">In addition, the order of precedence is important if multiple preset security policies and other policies apply to the same person.</span></span>

### <a name="profiles-in-preset-security-policies"></a><span data-ttu-id="4aa55-118">事前設定されたセキュリティ ポリシーのプロファイル</span><span class="sxs-lookup"><span data-stu-id="4aa55-118">Profiles in preset security policies</span></span>

<span data-ttu-id="4aa55-119">プロファイルは、保護のレベルを決定します。</span><span class="sxs-lookup"><span data-stu-id="4aa55-119">A profile determines the level of protection.</span></span> <span data-ttu-id="4aa55-120">次のプロファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4aa55-120">The following profiles are available:</span></span>

- <span data-ttu-id="4aa55-121">**標準保護**: ほとんどのユーザーに適したベースライン保護プロファイル。</span><span class="sxs-lookup"><span data-stu-id="4aa55-121">**Standard protection**: A baseline protection profile that's suitable for most users.</span></span>
- <span data-ttu-id="4aa55-122">**厳密な保護**: 選択したユーザー (高価値のターゲットまたは優先度の高いユーザー) に対して、より積極的な保護プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="4aa55-122">**Strict protection**: A more aggressive protection profile for selected users (high value targets or priority users).</span></span>

<span data-ttu-id="4aa55-123">プロファイルが適用されるユーザーまたは適用されないユーザーを決定する条件と例外を含むルールを使用します。</span><span class="sxs-lookup"><span data-stu-id="4aa55-123">You use rules with conditions and exceptions that determine who the profiles are or are not applied to.</span></span>

<span data-ttu-id="4aa55-124">各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="4aa55-124">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="4aa55-125">同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="4aa55-125">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="4aa55-126">a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="4aa55-126">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

<span data-ttu-id="4aa55-127">使用可能な条件と例外は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4aa55-127">The available conditions and exceptions are:</span></span>

- <span data-ttu-id="4aa55-128">**受信者は、組織内** のメールボックス、メール ユーザー、またはメール連絡先です。</span><span class="sxs-lookup"><span data-stu-id="4aa55-128">**The recipients are**: Mailboxes, mail users, or mail contacts in your organization.</span></span>
- <span data-ttu-id="4aa55-129">**受信者は、組織内の**: グループのメンバーです。</span><span class="sxs-lookup"><span data-stu-id="4aa55-129">**The recipients are members of**: Groups in your organization.</span></span>
- <span data-ttu-id="4aa55-130">**受信者ドメインは、Microsoft** 365 で構成されている受け入れドメインです。</span><span class="sxs-lookup"><span data-stu-id="4aa55-130">**The recipient domains are**: Accepted domains that are configured in Microsoft 365.</span></span>

### <a name="policies-in-preset-security-policies"></a><span data-ttu-id="4aa55-131">事前設定されたセキュリティ ポリシーのポリシー</span><span class="sxs-lookup"><span data-stu-id="4aa55-131">Policies in preset security policies</span></span>

<span data-ttu-id="4aa55-132">事前設定されたセキュリティ ポリシーでは、EOP および Microsoft Defender の各種保護機能の対応するポリシーを、Office使用します。</span><span class="sxs-lookup"><span data-stu-id="4aa55-132">Preset security policies use the corresponding policies from the various protection features in EOP and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="4aa55-133">これらのポリシーは、Standard Protection _または_ **Strict Protection** の事前設定されたセキュリティ ポリシーを **ユーザー** に割り当てると作成されます。</span><span class="sxs-lookup"><span data-stu-id="4aa55-133">These policies are created _after_ you assign the **Standard protection** or **Strict protection** preset security policies to users.</span></span> <span data-ttu-id="4aa55-134">これらのポリシーは変更できない。</span><span class="sxs-lookup"><span data-stu-id="4aa55-134">You can't modify these policies.</span></span>

- <span data-ttu-id="4aa55-135">**Exchange Online Protection (EOP)** ポリシー : これには、Exchange Online メールボックスを持つ Microsoft 365 組織と、Exchange Online メールボックスのないスタンドアロン EOP 組織が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4aa55-135">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="4aa55-136">[Standard](configure-your-spam-filter-policies.md) Preset Security Policy と **Strict Preset Security Policy という** 名前の **スパム対策ポリシー**。</span><span class="sxs-lookup"><span data-stu-id="4aa55-136">[Anti-spam policies](configure-your-spam-filter-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="4aa55-137">[Standard](configure-anti-malware-policies.md) Preset Security Policy と **Strict Preset Security Policy という** 名前の **マルウェア対策ポリシー**。</span><span class="sxs-lookup"><span data-stu-id="4aa55-137">[Anti-malware policies](configure-anti-malware-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="4aa55-138">[標準プリセット セキュリティ ポリシーと](set-up-anti-phishing-policies.md#spoof-settings)厳密な事前設定セキュリティ ポリシー (スプーフィング設定) という EOP フィッシング **対策** ポリシー。</span><span class="sxs-lookup"><span data-stu-id="4aa55-138">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings) named **Standard Preset Security Policy** and **Strict Preset Security Policy** (spoof settings).</span></span>

- <span data-ttu-id="4aa55-139">**Microsoft Defender for Office 365** ポリシー: これには、Microsoft 365 E5 または Defender が 365 アドオン サブスクリプションの組織Office含まれます。</span><span class="sxs-lookup"><span data-stu-id="4aa55-139">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="4aa55-140">Microsoft Defender のフィッシング対策ポリシーは、標準Officeセキュリティ ポリシーと厳密な事前設定セキュリティ ポリシーという名前の 365 を使用します。このポリシーには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4aa55-140">Anti-phishing policies in Microsoft Defender for Office 365 named **Standard Preset Security Policy** and **Strict Preset Security Policy**, which include:</span></span>

    - <span data-ttu-id="4aa55-141">EOP [フィッシング対策](set-up-anti-phishing-policies.md#spoof-settings) ポリシーで使用できるスプーフィング設定と同じです。</span><span class="sxs-lookup"><span data-stu-id="4aa55-141">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="4aa55-142">偽装設定</span><span class="sxs-lookup"><span data-stu-id="4aa55-142">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="4aa55-143">高度なフィッシングのしきい値</span><span class="sxs-lookup"><span data-stu-id="4aa55-143">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="4aa55-144">[Standard Preset Security Policy と](set-up-atp-safe-links-policies.md) Strict Preset Security Policy **という** 名前のセーフ リンク **ポリシー**。</span><span class="sxs-lookup"><span data-stu-id="4aa55-144">[Safe Links policies](set-up-atp-safe-links-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

  - <span data-ttu-id="4aa55-145">[Standard Preset Security](set-up-atp-safe-attachments-policies.md) Policy と **Strict Preset Security Policy という** 名前の **安全な添付ファイル ポリシー**。</span><span class="sxs-lookup"><span data-stu-id="4aa55-145">[Safe Attachments policies](set-up-atp-safe-attachments-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

<span data-ttu-id="4aa55-146">365 保護の場合は、Microsoft Defender とは異なるユーザーに EOP Office適用できます。</span><span class="sxs-lookup"><span data-stu-id="4aa55-146">Note that you can apply EOP protections to different users than Microsoft Defender for Office 365 protections.</span></span>

### <a name="policy-settings-in-preset-security-policies"></a><span data-ttu-id="4aa55-147">事前設定されたセキュリティ ポリシーのポリシー設定</span><span class="sxs-lookup"><span data-stu-id="4aa55-147">Policy settings in preset security policies</span></span>

<span data-ttu-id="4aa55-148">保護プロファイルでポリシー設定を変更できない。</span><span class="sxs-lookup"><span data-stu-id="4aa55-148">You can't modify the policy settings in the protection profiles.</span></span> <span data-ttu-id="4aa55-149">標準 **ポリシーと\*\*\*\*厳密なポリシー** 設定の値については、「EOP および Microsoft Defender の [365](recommended-settings-for-eop-and-office365-atp.md)セキュリティに関する推奨Office説明されています。</span><span class="sxs-lookup"><span data-stu-id="4aa55-149">The **Standard** and **Strict** policy setting values are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a><span data-ttu-id="4aa55-150">事前設定されたセキュリティ ポリシーおよび他のポリシーの優先順位</span><span class="sxs-lookup"><span data-stu-id="4aa55-150">Order of precedence for preset security policies and other policies</span></span>

<span data-ttu-id="4aa55-151">複数のポリシーがユーザーに適用される場合、次の順序が優先度の高い順から優先度の低い順に適用されます。</span><span class="sxs-lookup"><span data-stu-id="4aa55-151">When multiple policies are applied to a user, the following order is applied from highest priority to lowest priority:</span></span>

1. <span data-ttu-id="4aa55-152">**厳密な保護事前** 設定のセキュリティ ポリシー</span><span class="sxs-lookup"><span data-stu-id="4aa55-152">**Strict protection** preset security policy</span></span>
2. <span data-ttu-id="4aa55-153">**標準の保護の** 事前設定されたセキュリティ ポリシー</span><span class="sxs-lookup"><span data-stu-id="4aa55-153">**Standard protection** preset security policy</span></span>
3. <span data-ttu-id="4aa55-154">カスタム セキュリティ ポリシー</span><span class="sxs-lookup"><span data-stu-id="4aa55-154">Custom security policies</span></span>
4. <span data-ttu-id="4aa55-155">既定のセキュリティ ポリシー</span><span class="sxs-lookup"><span data-stu-id="4aa55-155">Default security policies</span></span>

<span data-ttu-id="4aa55-156">つまり、厳密な保護ポリシーの設定は、既定のポリシーの設定を上書きするカスタム ポリシーの設定を上書きする標準保護ポリシーの設定を上書きします。</span><span class="sxs-lookup"><span data-stu-id="4aa55-156">In other words, the settings of the **Strict protection** policy override the settings of the **Standard protection** policy, which overrides the settings from a custom policy, which overrides the settings from the default policy.</span></span>

## <a name="assign-preset-security-policies-to-users"></a><span data-ttu-id="4aa55-157">ユーザーに事前設定されたセキュリティ ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4aa55-157">Assign preset security policies to users</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4aa55-158">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="4aa55-158">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4aa55-159"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="4aa55-159">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="4aa55-160">[事前設定されたセキュリティ ポリシー] **ページに直接移動するには** 、 を使用します <https://protection.office.com/presetSecurityPolicies> 。</span><span class="sxs-lookup"><span data-stu-id="4aa55-160">To go directly to the **Preset security policies** page, use <https://protection.office.com/presetSecurityPolicies>.</span></span>

- <span data-ttu-id="4aa55-161">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4aa55-161">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="4aa55-162">この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4aa55-162">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="4aa55-163">事前設定されたセキュリティ ポリシーを構成するには、組織の管理またはセキュリティ管理者の役割グループ **のメンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="4aa55-163">To configure preset security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="4aa55-164">事前設定されたセキュリティ ポリシーへの読み取り専用アクセスでは、グローバル リーダー役割グループの **メンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="4aa55-164">For read-only access to preset security policies, you need to be a member of the **Global Reader** role group.</span></span>

  <span data-ttu-id="4aa55-165">詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4aa55-165">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="4aa55-166">**注**: Microsoft 365 管理センターの対応する Azure Active Directory ロールにユーザーを追加すると、Microsoft 365 の他の機能に必要なアクセス許可とアクセス許可がユーザーに付与されます。</span><span class="sxs-lookup"><span data-stu-id="4aa55-166">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="4aa55-167">詳細については、「[管理者ロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4aa55-167">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a><span data-ttu-id="4aa55-168">コンプライアンス センターのセキュリティ &を使用して、ユーザーに事前設定されたセキュリティ ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4aa55-168">Use the Security & Compliance Center to assign preset security policies to users</span></span>

1. <span data-ttu-id="4aa55-169">セキュリティ ポリシー コンプライアンス &で、[**脅威管理ポリシー** の事前設定] \>  \> **のセキュリティ ポリシーに移動します**。</span><span class="sxs-lookup"><span data-stu-id="4aa55-169">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Preset security policies**.</span></span>

2. <span data-ttu-id="4aa55-170">[標準 **保護] または [\*\*\*\*厳密な保護] で、[** 編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="4aa55-170">Under **Standard protection** or **Strict protection**, click **Edit**.</span></span>

3. <span data-ttu-id="4aa55-171">[ **標準保護の適用] または** **[厳密な保護の適用] ウィザードが** 起動します。</span><span class="sxs-lookup"><span data-stu-id="4aa55-171">The **Apply Standard protection** or **Apply Strict protection** wizard starts.</span></span> <span data-ttu-id="4aa55-172">手順に **適用される EOP** 保護で [、EOP](#policies-in-preset-security-policies) 保護が適用される内部受信者を特定します。</span><span class="sxs-lookup"><span data-stu-id="4aa55-172">On the **EOP protections apply to** step, identify the internal recipients that the [EOP protections](#policies-in-preset-security-policies) apply to:</span></span>

   1. <span data-ttu-id="4aa55-173">[条件 **の追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4aa55-173">Click **Add a condition**.</span></span> <span data-ttu-id="4aa55-174">表示されるドロップダウンで、[適用する場合] で条件 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4aa55-174">In the dropdown that appears, select a condition under **Applied if**:</span></span>

      - <span data-ttu-id="4aa55-175">**受信者は次のとおりです。**</span><span class="sxs-lookup"><span data-stu-id="4aa55-175">**The recipients are**</span></span>
      - <span data-ttu-id="4aa55-176">**受信者は、次のメンバーです。**</span><span class="sxs-lookup"><span data-stu-id="4aa55-176">**The recipients are members of**</span></span>
      - <span data-ttu-id="4aa55-177">**受信者ドメインは、次のとおりです。**</span><span class="sxs-lookup"><span data-stu-id="4aa55-177">**The recipient domains are**</span></span>

      <span data-ttu-id="4aa55-178">条件を使用できるのは 1 回のみですが、条件に複数の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="4aa55-178">You can only use a condition once, but you can specify multiple values for the condition.</span></span> <span data-ttu-id="4aa55-179">同じ条件の複数の値は、OR ロジック (たとえば、または) を _\<recipient1\>_ 使用します _\<recipient2\>_ 。</span><span class="sxs-lookup"><span data-stu-id="4aa55-179">Multiple values of the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span>

   2. <span data-ttu-id="4aa55-180">選択した条件が影付きセクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4aa55-180">The condition that you selected appears in a shaded section.</span></span> <span data-ttu-id="4aa55-181">そのセクションで、[これらの任意] **ボックスをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="4aa55-181">In that section, click in the **Any of these** box.</span></span> <span data-ttu-id="4aa55-182">しばらく待つ場合は、値を選択できるようリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4aa55-182">If you wait a moment, a list will appear so you can select a value.</span></span> <span data-ttu-id="4aa55-183">または、値の入力を開始してリストをフィルター処理し、値を選択できます。</span><span class="sxs-lookup"><span data-stu-id="4aa55-183">Or, you can start typing a value to filter the list and select a value.</span></span> <span data-ttu-id="4aa55-184">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="4aa55-184">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="4aa55-185">個々の値を削除するには、値 **の [削除]** ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4aa55-185">To remove an individual value, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span> <span data-ttu-id="4aa55-186">条件全体を削除するには、条件の **[削除]** ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4aa55-186">To remove the entire condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   3. <span data-ttu-id="4aa55-187">別の条件を追加するには、[条件の **追加] をクリックし** 、残りの条件から選択します。</span><span class="sxs-lookup"><span data-stu-id="4aa55-187">To add another condition, click **Add a condition** and select from the remaining conditions.</span></span> <span data-ttu-id="4aa55-188">条件が異なる場合は、AND ロジック (たとえば、および _\<recipient1\>_ ) を使用 _\<member of group 1\>_ します。</span><span class="sxs-lookup"><span data-stu-id="4aa55-188">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

      <span data-ttu-id="4aa55-189">前の手順を繰り返して条件に値を追加し、必要な回数、または条件が満たされるまでこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="4aa55-189">Repeat the previous step to add values to the condition, and repeat this step as many times as necessary or until you run out of conditions.</span></span>

   4. <span data-ttu-id="4aa55-190">例外を追加するには、[条件の追加 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4aa55-190">To add an exception, click **Add a condition**.</span></span> <span data-ttu-id="4aa55-191">表示されるドロップダウンで、[条件] で [条件を指定する場合を **除く] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4aa55-191">In the dropdown that appears, select a condition under **Except when**.</span></span> <span data-ttu-id="4aa55-192">設定と動作は、条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="4aa55-192">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="4aa55-193">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4aa55-193">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="4aa55-194">組織に microsoft Defender for Office 365 がある場合は **、ATP** 保護が適用される手順に進み、microsoft Defender for [Office 365](#policies-in-preset-security-policies) 保護が適用される内部受信者を特定します。</span><span class="sxs-lookup"><span data-stu-id="4aa55-194">If your organization has Microsoft Defender for Office 365, you're taken to the **ATP protections apply to** step to identify the internal recipients that the [Microsoft Defender for Office 365 protections](#policies-in-preset-security-policies) apply to.</span></span>

   <span data-ttu-id="4aa55-195">設定と動作は **、EOP 保護が手順に適用されるのとまったく同** じです。</span><span class="sxs-lookup"><span data-stu-id="4aa55-195">The settings and behavior are exactly like the **EOP protections apply to** step.</span></span>

   <span data-ttu-id="4aa55-196">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4aa55-196">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="4aa55-197">[確認 **] 手順** で、選択内容を確認し、[確認] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="4aa55-197">On the **Confirm** step, verify your selections, and then click **Confirm**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a><span data-ttu-id="4aa55-198">コンプライアンス センターのセキュリティ &使用して、事前設定されたセキュリティ ポリシーの割り当てを変更する</span><span class="sxs-lookup"><span data-stu-id="4aa55-198">Use the Security & Compliance Center to modify the assignments of preset security policies</span></span>

<span data-ttu-id="4aa55-199">Standard Protection または **Strict** **Protection** セキュリティ ポリシーの割り当てを変更する手順は、事前設定されたセキュリティ ポリシーをユーザーに最初に割り当てた場合と [同じです](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users)。</span><span class="sxs-lookup"><span data-stu-id="4aa55-199">The steps to modify the assignment of the **Standard protection** or **Strict protection** security policy are the same as when you initially [assigned the preset security policies to users](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users).</span></span>

<span data-ttu-id="4aa55-200">既存の条件と例外 **を** 維持しながら、標準保護ポリシーまたは **厳密** な保護セキュリティ ポリシーを無効にするには、トグルを [無効] に **スライドします**。</span><span class="sxs-lookup"><span data-stu-id="4aa55-200">To disable the **Standard protection** or **Strict protection** security policies while still preserving the existing conditions and exceptions, slide the toggle to **Disabled**.</span></span> <span data-ttu-id="4aa55-201">ポリシーを有効にするには、トグルを [有効] に **スライドします**。</span><span class="sxs-lookup"><span data-stu-id="4aa55-201">To enable the policies, slide the toggle to **Enabled**.</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="4aa55-202">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="4aa55-202">How do you know these procedures worked?</span></span>

<span data-ttu-id="4aa55-203">標準保護または厳密な保護セキュリティ ポリシーがユーザーに正常に割り当てられているか確認するには、既定値が標準保護設定とは異なる保護設定を使用します。これは、厳密な保護設定とは異なります。</span><span class="sxs-lookup"><span data-stu-id="4aa55-203">To verify that you've successfully assigned the **Standard protection** or **Strict protection** security policy to a user, use a protection setting where the default value is different than the **Standard protection** setting, which is different that the **Strict protection** setting.</span></span>

<span data-ttu-id="4aa55-204">たとえば、スパムとして検出された (信頼度の高いスパムではない) 電子メールの場合、メッセージが標準保護ユーザーの迷惑メールフォルダーに配信され、厳密な保護ユーザーに対して検疫済みである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4aa55-204">For example, for email that's detected as spam (not high confidence spam) verify that the message is delivered to the Junk Email folder for **Standard protection** users, and quarantined for **Strict protection** users.</span></span>

<span data-ttu-id="4aa55-205">または、バルク メールの場合は、BCL 値 6 以上が標準保護ユーザーの迷惑メールフォルダーにメッセージを配信し、BCL 値 4 以上が厳密な保護ユーザーのメッセージを検疫します。 [](bulk-complaint-level-values.md)</span><span class="sxs-lookup"><span data-stu-id="4aa55-205">Or, for [bulk email](bulk-complaint-level-values.md), verify that the BCL value 6 or higher delivers the message to the Junk Email folder for **Standard protection** users, and the BCL value 4 or higher quarantines the message for **Strict protection** users.</span></span>