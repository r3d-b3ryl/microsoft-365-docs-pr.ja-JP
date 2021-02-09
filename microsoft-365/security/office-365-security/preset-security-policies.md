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
description: 管理者は、Exchange Online Protection (EOP) と Microsoft Defender for Office 365 の保護機能に対して標準ポリシー設定と厳密ポリシー設定を適用する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f57b388716eca02741ba48b3e6b47b7cf9f28884
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150093"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="3af58-103">EOP と Microsoft Defender のセキュリティ ポリシーを Office 365 用に事前に設定する</span><span class="sxs-lookup"><span data-stu-id="3af58-103">Preset security policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3af58-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="3af58-104">**Applies to**</span></span>
- [<span data-ttu-id="3af58-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3af58-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="3af58-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="3af58-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="3af58-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3af58-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="3af58-108">事前設定されたセキュリティ ポリシーは、推奨されるスパム、マルウェア、およびフィッシング ポリシーを一度にユーザーに適用する一元的な場所を提供します。</span><span class="sxs-lookup"><span data-stu-id="3af58-108">Preset security policies provide a centralized location for applying all of the recommended spam, malware, and phishing policies to users at once.</span></span> <span data-ttu-id="3af58-109">ポリシー設定は構成できません。</span><span class="sxs-lookup"><span data-stu-id="3af58-109">The policy settings are not configurable.</span></span> <span data-ttu-id="3af58-110">代わりに、ユーザーは弊社が設定し、作業を中断することなく有害なコンテンツをユーザーから遠近に保つ間のバランスを取るデータセンターでの観察とエクスペリエンスに基づいて行われます。</span><span class="sxs-lookup"><span data-stu-id="3af58-110">Instead, they are set by us and are based on our observations and experiences in the datacenters for a balance between keeping harmful content away from users without disrupting their work.</span></span>

<span data-ttu-id="3af58-111">このトピックの残りの部分では、事前設定されたセキュリティ ポリシーと、その構成方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3af58-111">The rest of this topic describes preset security policies and how to configure them.</span></span>

## <a name="what-preset-security-policies-are-made-of"></a><span data-ttu-id="3af58-112">事前設定されたセキュリティ ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="3af58-112">What preset security policies are made of</span></span>

<span data-ttu-id="3af58-113">事前設定されたセキュリティ ポリシーは、次の要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="3af58-113">Preset security policies consist of the following elements:</span></span>

- <span data-ttu-id="3af58-114">プロファイル</span><span class="sxs-lookup"><span data-stu-id="3af58-114">Profiles</span></span>
- <span data-ttu-id="3af58-115">Policies</span><span class="sxs-lookup"><span data-stu-id="3af58-115">Policies</span></span>
- <span data-ttu-id="3af58-116">ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="3af58-116">Policy settings</span></span>

<span data-ttu-id="3af58-117">また、複数の事前設定されたセキュリティ ポリシーと他のポリシーが同じユーザーに適用される場合は、優先順位が重要です。</span><span class="sxs-lookup"><span data-stu-id="3af58-117">In addition, the order of precedence is important if multiple preset security policies and other policies apply to the same person.</span></span>

### <a name="profiles-in-preset-security-policies"></a><span data-ttu-id="3af58-118">事前設定されたセキュリティ ポリシーのプロファイル</span><span class="sxs-lookup"><span data-stu-id="3af58-118">Profiles in preset security policies</span></span>

<span data-ttu-id="3af58-119">プロファイルは、保護のレベルを決定します。</span><span class="sxs-lookup"><span data-stu-id="3af58-119">A profile determines the level of protection.</span></span> <span data-ttu-id="3af58-120">次のプロファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3af58-120">The following profiles are available:</span></span>

- <span data-ttu-id="3af58-121">**標準保護**: ほとんどのユーザーに適したベースライン保護プロファイルです。</span><span class="sxs-lookup"><span data-stu-id="3af58-121">**Standard protection**: A baseline protection profile that's suitable for most users.</span></span>
- <span data-ttu-id="3af58-122">**厳密な** 保護 : 選択したユーザー (高い値のターゲットまたは優先度のユーザー) に対して、より積極的な保護プロファイル。</span><span class="sxs-lookup"><span data-stu-id="3af58-122">**Strict protection**: A more aggressive protection profile for selected users (high value targets or priority users).</span></span>

<span data-ttu-id="3af58-123">プロファイルが適用されるユーザーまたは適用されていないユーザーを決定する条件と例外でルールを使用します。</span><span class="sxs-lookup"><span data-stu-id="3af58-123">You use rules with conditions and exceptions that determine who the profiles are or are not applied to.</span></span>

<span data-ttu-id="3af58-124">各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3af58-124">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="3af58-125">同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="3af58-125">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="3af58-126">a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="3af58-126">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

<span data-ttu-id="3af58-127">使用可能な条件と例外は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3af58-127">The available conditions and exceptions are:</span></span>

- <span data-ttu-id="3af58-128">**受信者は、** 組織内のメールボックス、メール ユーザー、またはメール連絡先です。</span><span class="sxs-lookup"><span data-stu-id="3af58-128">**The recipients are**: Mailboxes, mail users, or mail contacts in your organization.</span></span>
- <span data-ttu-id="3af58-129">**受信者は、組織内の** グループのメンバーです。</span><span class="sxs-lookup"><span data-stu-id="3af58-129">**The recipients are members of**: Groups in your organization.</span></span>
- <span data-ttu-id="3af58-130">**受信者のドメインは、Microsoft** 365 で構成されている承認されたドメインです。</span><span class="sxs-lookup"><span data-stu-id="3af58-130">**The recipient domains are**: Accepted domains that are configured in Microsoft 365.</span></span>

### <a name="policies-in-preset-security-policies"></a><span data-ttu-id="3af58-131">事前設定されたセキュリティ ポリシーのポリシー</span><span class="sxs-lookup"><span data-stu-id="3af58-131">Policies in preset security policies</span></span>

<span data-ttu-id="3af58-132">事前設定されたセキュリティ ポリシーでは、EOP と Microsoft Defender for Office 365 のさまざまな保護機能の対応するポリシーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="3af58-132">Preset security policies use the corresponding policies from the various protection features in EOP and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="3af58-133">これらのポリシーは、Standard Protection _または_ **Strict Protection** の事前設定されたセキュリティ ポリシーをユーザーに割り当てる **と** 作成されます。</span><span class="sxs-lookup"><span data-stu-id="3af58-133">These policies are created _after_ you assign the **Standard protection** or **Strict protection** preset security policies to users.</span></span> <span data-ttu-id="3af58-134">これらのポリシーは変更できない。</span><span class="sxs-lookup"><span data-stu-id="3af58-134">You can't modify these policies.</span></span>

- <span data-ttu-id="3af58-135">**Exchange Online Protection (EOP)** ポリシー : これには、Exchange Online メールボックスを持つ Microsoft 365 組織と、Exchange Online メールボックスのないスタンドアロン EOP 組織が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3af58-135">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="3af58-136">[Standard](configure-your-spam-filter-policies.md) Preset Security Policy および Strict **Preset Security Policy という** 名前 **のスパム対策ポリシー**。</span><span class="sxs-lookup"><span data-stu-id="3af58-136">[Anti-spam policies](configure-your-spam-filter-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="3af58-137">[Standard](configure-anti-malware-policies.md) Preset Security Policy and Strict Preset Security **Policy** という名前の **マルウェア対策ポリシー**。</span><span class="sxs-lookup"><span data-stu-id="3af58-137">[Anti-malware policies](configure-anti-malware-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="3af58-138">Standard Preset Security Policy および Strict Preset **Security** **Policy** (spoof settings) という名前の [EOP](set-up-anti-phishing-policies.md#spoof-settings)フィッシング対策ポリシー。</span><span class="sxs-lookup"><span data-stu-id="3af58-138">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings) named **Standard Preset Security Policy** and **Strict Preset Security Policy** (spoof settings).</span></span>

- <span data-ttu-id="3af58-139">**Microsoft Defender for Office 365** ポリシー: これには、Microsoft 365 E5 または Defender for Office 365 アドオン サブスクリプションを持つ組織が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3af58-139">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="3af58-140">Microsoft Defender の Office 365 のフィッシング対策ポリシーには、Standard **Preset Security Policy** と Strict **Preset Security Policy** という名前が付けされています。次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3af58-140">Anti-phishing policies in Microsoft Defender for Office 365 named **Standard Preset Security Policy** and **Strict Preset Security Policy**, which include:</span></span>

    - <span data-ttu-id="3af58-141">EOP [フィッシング詐欺](set-up-anti-phishing-policies.md#spoof-settings) 対策ポリシーで使用可能なスプーフィング設定と同じ。</span><span class="sxs-lookup"><span data-stu-id="3af58-141">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="3af58-142">偽装設定</span><span class="sxs-lookup"><span data-stu-id="3af58-142">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="3af58-143">高度なフィッシングのしきい値</span><span class="sxs-lookup"><span data-stu-id="3af58-143">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="3af58-144">[Standard Preset Security Policy および](set-up-atp-safe-links-policies.md)Strict Preset Security Policy **という\*\*\*\*名前の安全なリンク ポリシー**。</span><span class="sxs-lookup"><span data-stu-id="3af58-144">[Safe Links policies](set-up-atp-safe-links-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

  - <span data-ttu-id="3af58-145">[Standard Preset Security Policy and](set-up-atp-safe-attachments-policies.md) Strict Preset Security **Policy** という **名前の安全な添付ファイル ポリシー**。</span><span class="sxs-lookup"><span data-stu-id="3af58-145">[Safe Attachments policies](set-up-atp-safe-attachments-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

<span data-ttu-id="3af58-146">EOP 保護は、Microsoft Defender とは異なるユーザーに適用して、365 Office適用できます。</span><span class="sxs-lookup"><span data-stu-id="3af58-146">Note that you can apply EOP protections to different users than Microsoft Defender for Office 365 protections.</span></span>

### <a name="policy-settings-in-preset-security-policies"></a><span data-ttu-id="3af58-147">事前設定されたセキュリティ ポリシーのポリシー設定</span><span class="sxs-lookup"><span data-stu-id="3af58-147">Policy settings in preset security policies</span></span>

<span data-ttu-id="3af58-148">保護プロファイルのポリシー設定は変更できない。</span><span class="sxs-lookup"><span data-stu-id="3af58-148">You can't modify the policy settings in the protection profiles.</span></span> <span data-ttu-id="3af58-149">Standard **および Strict** ポリシー **設定** の値については [、「365](recommended-settings-for-eop-and-office365-atp.md)セキュリティのための EOP と Microsoft Defender の推奨Office説明されています。</span><span class="sxs-lookup"><span data-stu-id="3af58-149">The **Standard** and **Strict** policy setting values are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a><span data-ttu-id="3af58-150">事前設定されたセキュリティ ポリシーおよび他のポリシーの優先順位</span><span class="sxs-lookup"><span data-stu-id="3af58-150">Order of precedence for preset security policies and other policies</span></span>

<span data-ttu-id="3af58-151">ユーザーに複数のポリシーが適用されると、次の順序が最高の優先度から最も低い優先度に適用されます。</span><span class="sxs-lookup"><span data-stu-id="3af58-151">When multiple policies are applied to a user, the following order is applied from highest priority to lowest priority:</span></span>

1. <span data-ttu-id="3af58-152">**厳密な保護の** 事前設定のセキュリティ ポリシー</span><span class="sxs-lookup"><span data-stu-id="3af58-152">**Strict protection** preset security policy</span></span>
2. <span data-ttu-id="3af58-153">**標準の保護の** 事前設定セキュリティ ポリシー</span><span class="sxs-lookup"><span data-stu-id="3af58-153">**Standard protection** preset security policy</span></span>
3. <span data-ttu-id="3af58-154">カスタム セキュリティ ポリシー</span><span class="sxs-lookup"><span data-stu-id="3af58-154">Custom security policies</span></span>
4. <span data-ttu-id="3af58-155">既定のセキュリティ ポリシー</span><span class="sxs-lookup"><span data-stu-id="3af58-155">Default security policies</span></span>

<span data-ttu-id="3af58-156">つまり **、Strict** 保護ポリシーの設定は Standard 保護ポリシーの設定より優先され、カスタム ポリシーの設定は上書きされ、既定のポリシーの設定は上書きされます。</span><span class="sxs-lookup"><span data-stu-id="3af58-156">In other words, the settings of the **Strict protection** policy override the settings of the **Standard protection** policy, which overrides the settings from a custom policy, which overrides the settings from the default policy.</span></span>

## <a name="assign-preset-security-policies-to-users"></a><span data-ttu-id="3af58-157">ユーザーに事前設定されたセキュリティ ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="3af58-157">Assign preset security policies to users</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3af58-158">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="3af58-158">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3af58-159"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="3af58-159">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="3af58-160">[事前設定されたセキュリティ ポリシー **] ページに直接移動するには、次** の値を使用します <https://protection.office.com/presetSecurityPolicies> 。</span><span class="sxs-lookup"><span data-stu-id="3af58-160">To go directly to the **Preset security policies** page, use <https://protection.office.com/presetSecurityPolicies>.</span></span>

- <span data-ttu-id="3af58-161">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3af58-161">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="3af58-162">この記事に記載の手順を行うには、セキュリティ/コンプライアンス センターのアクセス許可が割り当てられている必要があります:</span><span class="sxs-lookup"><span data-stu-id="3af58-162">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="3af58-163">事前設定されたセキュリティ ポリシーを構成するには、組織の管理役割グループまたはセキュリティ管理者役割グループのメンバー **である** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="3af58-163">To configure preset security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="3af58-164">事前に設定されたセキュリティ ポリシーへの読み取り専用アクセスの場合は、グローバル 閲覧者役割グループのメンバー **である** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="3af58-164">For read-only access to preset security policies, you need to be a member of the **Global Reader** role group.</span></span>

  <span data-ttu-id="3af58-165">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3af58-165">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="3af58-166">**注**: Microsoft 365 管理センターで対応する Azure Active Directory ロールにユーザーを追加すると、セキュリティ & コンプライアンスセンターで必要なアクセス許可と、Microsoft 365 の他の機能に対するアクセス許可がユーザーに付与されます。</span><span class="sxs-lookup"><span data-stu-id="3af58-166">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="3af58-167">詳細については、「[管理者の役割について](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3af58-167">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a><span data-ttu-id="3af58-168">セキュリティ/コンプライアンス センター&使用して、ユーザーに事前設定されたセキュリティ ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="3af58-168">Use the Security & Compliance Center to assign preset security policies to users</span></span>

1. <span data-ttu-id="3af58-169">セキュリティ & コンプライアンス センターで、[脅威の管理 **ポリシーの** 事前設定] セキュリティ ポリシー \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="3af58-169">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Preset security policies**.</span></span>

2. <span data-ttu-id="3af58-170">[**標準の保護] または [\*\*\*\*厳密な保護] で、[** 編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="3af58-170">Under **Standard protection** or **Strict protection**, click **Edit**.</span></span>

3. <span data-ttu-id="3af58-171">[**標準保護の適用] または [\*\*\*\*厳密な保護の適用] ウィザード** が起動します。</span><span class="sxs-lookup"><span data-stu-id="3af58-171">The **Apply Standard protection** or **Apply Strict protection** wizard starts.</span></span> <span data-ttu-id="3af58-172">**EOP 保護が手順に適用** される場合は [、EOP](#policies-in-preset-security-policies)保護が適用される内部受信者を特定します。</span><span class="sxs-lookup"><span data-stu-id="3af58-172">On the **EOP protections apply to** step, identify the internal recipients that the [EOP protections](#policies-in-preset-security-policies) apply to:</span></span>

   1. <span data-ttu-id="3af58-173">[条件 **の追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3af58-173">Click **Add a condition**.</span></span> <span data-ttu-id="3af58-174">表示されるドロップダウンで、[適用] の下の条件を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3af58-174">In the dropdown that appears, select a condition under **Applied if**:</span></span>

      - <span data-ttu-id="3af58-175">**受信者が次の場合**</span><span class="sxs-lookup"><span data-stu-id="3af58-175">**The recipients are**</span></span>
      - <span data-ttu-id="3af58-176">**受信者は次のメンバーです。**</span><span class="sxs-lookup"><span data-stu-id="3af58-176">**The recipients are members of**</span></span>
      - <span data-ttu-id="3af58-177">**受信者のドメインは次のとおりです。**</span><span class="sxs-lookup"><span data-stu-id="3af58-177">**The recipient domains are**</span></span>

      <span data-ttu-id="3af58-178">条件は 1 回しか使用できますが、条件に複数の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="3af58-178">You can only use a condition once, but you can specify multiple values for the condition.</span></span> <span data-ttu-id="3af58-179">同じ条件の複数の値は、OR ロジック (または) を使用 _\<recipient1\>_ します _\<recipient2\>_ 。</span><span class="sxs-lookup"><span data-stu-id="3af58-179">Multiple values of the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span>

   2. <span data-ttu-id="3af58-180">選択した条件は、影付きのセクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3af58-180">The condition that you selected appears in a shaded section.</span></span> <span data-ttu-id="3af58-181">このセクションで、[Any of **these] ボックスをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="3af58-181">In that section, click in the **Any of these** box.</span></span> <span data-ttu-id="3af58-182">しばらく待つ場合は、値を選択できるようリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3af58-182">If you wait a moment, a list will appear so you can select a value.</span></span> <span data-ttu-id="3af58-183">または、リストをフィルター処理して値を選択する値の入力を開始できます。</span><span class="sxs-lookup"><span data-stu-id="3af58-183">Or, you can start typing a value to filter the list and select a value.</span></span> <span data-ttu-id="3af58-184">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="3af58-184">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="3af58-185">個々の値を削除するには、値の **[削除]** ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3af58-185">To remove an individual value, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span> <span data-ttu-id="3af58-186">条件全体を削除するには、条件の **[削除**] ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3af58-186">To remove the entire condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   3. <span data-ttu-id="3af58-187">別の条件を追加するには、[条件の **追加] をクリック** し、残りの条件から選択します。</span><span class="sxs-lookup"><span data-stu-id="3af58-187">To add another condition, click **Add a condition** and select from the remaining conditions.</span></span> <span data-ttu-id="3af58-188">条件が異なると、AND ロジック (たとえば、and) が _\<recipient1\>_ 使用されます _\<member of group 1\>_ 。</span><span class="sxs-lookup"><span data-stu-id="3af58-188">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

      <span data-ttu-id="3af58-189">前の手順を繰り返して条件に値を追加し、必要な回数、または条件が足りないまでこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="3af58-189">Repeat the previous step to add values to the condition, and repeat this step as many times as necessary or until you run out of conditions.</span></span>

   4. <span data-ttu-id="3af58-190">例外を追加するには、[条件の追加 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3af58-190">To add an exception, click **Add a condition**.</span></span> <span data-ttu-id="3af58-191">表示されるドロップダウンで、[次の場合を除く] **で条件を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3af58-191">In the dropdown that appears, select a condition under **Except when**.</span></span> <span data-ttu-id="3af58-192">設定と動作は、条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="3af58-192">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="3af58-193">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3af58-193">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="3af58-194">組織に Office 365 用 Microsoft Defender がある場合は **、ATP** 保護が適用される手順に進み [、Microsoft Defender for Office 365](#policies-in-preset-security-policies) の保護が適用される内部受信者を特定します。</span><span class="sxs-lookup"><span data-stu-id="3af58-194">If your organization has Microsoft Defender for Office 365, you're taken to the **ATP protections apply to** step to identify the internal recipients that the [Microsoft Defender for Office 365 protections](#policies-in-preset-security-policies) apply to.</span></span>

   <span data-ttu-id="3af58-195">設定と動作は **、EOP 保護が手順に適用されるのとまったく同** じになります。</span><span class="sxs-lookup"><span data-stu-id="3af58-195">The settings and behavior are exactly like the **EOP protections apply to** step.</span></span>

   <span data-ttu-id="3af58-196">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3af58-196">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="3af58-197">[確認 **] の** 手順で、選択内容を確認し、[確認] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="3af58-197">On the **Confirm** step, verify your selections, and then click **Confirm**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a><span data-ttu-id="3af58-198">セキュリティ/コンプライアンス センター&使用して、事前設定されたセキュリティ ポリシーの割り当てを変更する</span><span class="sxs-lookup"><span data-stu-id="3af58-198">Use the Security & Compliance Center to modify the assignments of preset security policies</span></span>

<span data-ttu-id="3af58-199">Standard Protection または **Strict** **Protection** セキュリティ ポリシーの割り当てを変更する手順は、事前設定されたセキュリティ ポリシーをユーザーに最初に割り当てた場合 [と同じです](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users)。</span><span class="sxs-lookup"><span data-stu-id="3af58-199">The steps to modify the assignment of the **Standard protection** or **Strict protection** security policy are the same as when you initially [assigned the preset security policies to users](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users).</span></span>

<span data-ttu-id="3af58-200">既存の条件 **と例外を** 保持しながら、標準保護または **厳密** な保護のセキュリティ ポリシーを無効にするには、トグルを [無効] にスライド **します**。</span><span class="sxs-lookup"><span data-stu-id="3af58-200">To disable the **Standard protection** or **Strict protection** security policies while still preserving the existing conditions and exceptions, slide the toggle to **Disabled**.</span></span> <span data-ttu-id="3af58-201">ポリシーを有効にするには、トグルを [有効] に **スライドします**。</span><span class="sxs-lookup"><span data-stu-id="3af58-201">To enable the policies, slide the toggle to **Enabled**.</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="3af58-202">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="3af58-202">How do you know these procedures worked?</span></span>

<span data-ttu-id="3af58-203">標準の保護または厳密な保護のセキュリティ ポリシーがユーザーに正常に割り当てられたか確認するには、既定値が [標準] 保護設定とは異なる保護設定を使用します。これは[**厳密** な保護] 設定とは異なります。 </span><span class="sxs-lookup"><span data-stu-id="3af58-203">To verify that you've successfully assigned the **Standard protection** or **Strict protection** security policy to a user, use a protection setting where the default value is different than the **Standard protection** setting, which is different that the **Strict protection** setting.</span></span>

<span data-ttu-id="3af58-204">たとえば、スパムとして検出された (信頼度の高いスパムではない) メールの場合、メッセージが **Standard Protection** ユーザーの迷惑メール フォルダーに配信され **、Strict 保護** ユーザーに対して検疫済みである必要があります。</span><span class="sxs-lookup"><span data-stu-id="3af58-204">For example, for email that's detected as spam (not high confidence spam) verify that the message is delivered to the Junk Email folder for **Standard protection** users, and quarantined for **Strict protection** users.</span></span>

<span data-ttu-id="3af58-205">または、バルク [](bulk-complaint-level-values.md)メールの場合は、BCL 値 6 以上が **Standard Protection** ユーザーの迷惑メール フォルダーにメッセージを配信し、BCL 値 4 以上が **Strict** 保護ユーザーのメッセージを検疫します。</span><span class="sxs-lookup"><span data-stu-id="3af58-205">Or, for [bulk email](bulk-complaint-level-values.md), verify that the BCL value 6 or higher delivers the message to the Junk Email folder for **Standard protection** users, and the BCL value 4 or higher quarantines the message for **Strict protection** users.</span></span>
