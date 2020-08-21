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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online Protection (EOP) および Office 365 Advanced Threat Protection (ATP) の保護機能に対して標準および制限のポリシー設定を適用する方法について学習できます。
ms.openlocfilehash: a2f0472d8dd44c90fd5db14e71d2db0d5d323b50
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825259"
---
# <a name="preset-security-policies-in-eop-and-office-365-atp"></a><span data-ttu-id="84df1-103">EOP と Office 365 ATP での事前セキュリティ ポリシー</span><span class="sxs-lookup"><span data-stu-id="84df1-103">Preset security policies in EOP and Office 365 ATP</span></span>

<span data-ttu-id="84df1-104">事前設定済みのセキュリティ ポリシーは、推奨されるすべてのスパム、マルウェア、およびフィッシング ポリシーを一度にユーザーに適用するための一元的な場所を提供します。</span><span class="sxs-lookup"><span data-stu-id="84df1-104">Preset security policies provide a centralized location for applying all of the recommended spam, malware, and phishing policies to users at once.</span></span> <span data-ttu-id="84df1-105">ポリシー設定は構成できません。</span><span class="sxs-lookup"><span data-stu-id="84df1-105">The policy settings are not configurable.</span></span> <span data-ttu-id="84df1-106">むしろ、ユーザーが作業を中断することなく、ユーザーから問題のあるコンテンツを切り分けずにバランスアップするために、Microsoft によって設定され、データセンター内の観測とエクスペリエンスに基づいています。</span><span class="sxs-lookup"><span data-stu-id="84df1-106">Instead, they are set by us and are based on our observations and experiences in the datacenters for a balance between keeping harmful content away from users without disrupting their work.</span></span>

<span data-ttu-id="84df1-107">このトピックの残りの部分では、事前に設定されたセキュリティ ポリシーと、その構成方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="84df1-107">The rest of this topic describes preset security policies and how to configure them.</span></span>

## <a name="what-preset-security-policies-are-made-of"></a><span data-ttu-id="84df1-108">作成される事前設定のセキュリティ ポリシー</span><span class="sxs-lookup"><span data-stu-id="84df1-108">What preset security policies are made of</span></span>

<span data-ttu-id="84df1-109">事前設定済みのセキュリティ ポリシーは、次の要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="84df1-109">Preset security policies consist of the following elements:</span></span>

- <span data-ttu-id="84df1-110">プロファイル</span><span class="sxs-lookup"><span data-stu-id="84df1-110">Profiles</span></span>
- <span data-ttu-id="84df1-111">ポリシー</span><span class="sxs-lookup"><span data-stu-id="84df1-111">Policies</span></span>
- <span data-ttu-id="84df1-112">ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="84df1-112">Policy settings</span></span>

<span data-ttu-id="84df1-113">さらに、複数の事前に設定されたセキュリティ ポリシーとその他のポリシーが同じ人物に適用される場合は、優先順位が重要になります。</span><span class="sxs-lookup"><span data-stu-id="84df1-113">In addition, the order of precedence is important if multiple preset security policies and other policies apply to the same person.</span></span>

### <a name="profiles-in-preset-security-policies"></a><span data-ttu-id="84df1-114">事前設定されたセキュリティ ポリシーのプロファイル</span><span class="sxs-lookup"><span data-stu-id="84df1-114">Profiles in preset security policies</span></span>

<span data-ttu-id="84df1-115">プロファイルは保護レベルを決定します。</span><span class="sxs-lookup"><span data-stu-id="84df1-115">A profile determines the level of protection.</span></span> <span data-ttu-id="84df1-116">使用可能なプロファイルは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="84df1-116">The following profiles are available:</span></span>

- <span data-ttu-id="84df1-117">**標準的**な保護: ほとんどのユーザーに適したベースライン保護プロファイルです。</span><span class="sxs-lookup"><span data-stu-id="84df1-117">**Standard protection**: A baseline protection profile that's suitable for most users.</span></span>
- <span data-ttu-id="84df1-118">**高い保護:** 選択されたユーザーに対してより、より総した保護プロファイル (高いターゲット、または優先ユーザー)。</span><span class="sxs-lookup"><span data-stu-id="84df1-118">**Strict protection**: A more aggressive protection profile for selected users (high value targets or priority users).</span></span>

<span data-ttu-id="84df1-119">プロファイルが適用される対象ユーザーと適用対象でないユーザーを決定する条件と例外をルールに使用します。</span><span class="sxs-lookup"><span data-stu-id="84df1-119">You use rules with conditions and exceptions that determine who the profiles are or are not applied to.</span></span>

<span data-ttu-id="84df1-120">各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="84df1-120">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="84df1-121">同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="84df1-121">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="84df1-122">a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="84df1-122">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

<span data-ttu-id="84df1-123">使用できる条件と例外は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="84df1-123">The available conditions and exceptions are:</span></span>

- <span data-ttu-id="84df1-124">**受信者は、** 組織内のメールボックス、メール ユーザー、メール連絡先です。</span><span class="sxs-lookup"><span data-stu-id="84df1-124">**The recipients are**: Mailboxes, mail users, or mail contacts in your organization.</span></span>
- <span data-ttu-id="84df1-125">**受信者は組織内の**: グループのメンバーです。</span><span class="sxs-lookup"><span data-stu-id="84df1-125">**The recipients are members of**: Groups in your organization.</span></span>
- <span data-ttu-id="84df1-126">**受信者のドメインは、Microsoft**365 で構成されている承認済みドメインです。</span><span class="sxs-lookup"><span data-stu-id="84df1-126">**The recipient domains are**: Accepted domains that are configured in Microsoft 365.</span></span>

### <a name="policies-in-preset-security-policies"></a><span data-ttu-id="84df1-127">事前設定されたセキュリティ ポリシーのポリシー</span><span class="sxs-lookup"><span data-stu-id="84df1-127">Policies in preset security policies</span></span>

<span data-ttu-id="84df1-128">事前設定されたセキュリティ ポリシーは、EOP および 365 ATP のさまざまな保護機能からの対応Officeを使用します。</span><span class="sxs-lookup"><span data-stu-id="84df1-128">Preset security policies use the corresponding policies from the various protection features in EOP and Office 365 ATP.</span></span> <span data-ttu-id="84df1-129">これらのポリシーは、標準_保護または_制限付き**のセキュリティ ポリシー\*\*\*\*をユーザーに割り**当てた後に作成されます。</span><span class="sxs-lookup"><span data-stu-id="84df1-129">These policies are created _after_ you assign the **Standard protection** or **Strict protection** preset security policies to users.</span></span> <span data-ttu-id="84df1-130">これらのポリシーは変更できません。</span><span class="sxs-lookup"><span data-stu-id="84df1-130">You can't modify these policies.</span></span>

- <span data-ttu-id="84df1-131">**Exchange Online Protection (EOP) ポリシー**: これには、Exchange Online メールボックスを使用している Microsoft 365 組織と Exchange Online メールボックスを持つスタンドアロン EOP 組織が含まれます。</span><span class="sxs-lookup"><span data-stu-id="84df1-131">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="84df1-132">Standard [Preset Security Policy](configure-your-spam-filter-policies.md)および**Strict Preset Security Policy という名前のスパム対策ポリシー**。 **Standard Preset Security Policy**</span><span class="sxs-lookup"><span data-stu-id="84df1-132">[Anti-spam policies](configure-your-spam-filter-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="84df1-133">[標準のプセットの](configure-anti-malware-policies.md)**セキュリティ ポリシーおよび Strict** **Preset Security Policy という名前のマルウェア対策ポリシー**。</span><span class="sxs-lookup"><span data-stu-id="84df1-133">[Anti-malware policies](configure-anti-malware-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="84df1-134">[標準プレセット セキュリティ ポリシーおよび](set-up-anti-phishing-policies.md#spoof-settings) **Standard Preset Security Policy** **Strict Preset Security Policy (Spoof** settings) という名前の EOP フィッシング対策ポリシー。</span><span class="sxs-lookup"><span data-stu-id="84df1-134">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings) named **Standard Preset Security Policy** and **Strict Preset Security Policy** (spoof settings).</span></span>

- <span data-ttu-id="84df1-135">**Office 365 Advanced Threat Protection (ATP) ポリシー**: これには、Microsoft 365 E5 または Office 365 の ATP アドオン サブスクリプションを持つ組織が含まれます。</span><span class="sxs-lookup"><span data-stu-id="84df1-135">**Office 365 Advanced Threat Protection (ATP) policies**: This includes organizations with Microsoft 365 E5 or Office 365 ATP add-on subscriptions:</span></span>

  - <span data-ttu-id="84df1-136">標準プレセットセキュリティ ポリシーと Strict **Preset Security Policy** という名前の ATP **フィッシング対策ポリシー。次**のポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="84df1-136">ATP anti-phishing policies named **Standard Preset Security Policy** and **Strict Preset Security Policy**, which include:</span></span>

    - <span data-ttu-id="84df1-137">EOP フ [ィッシング](set-up-anti-phishing-policies.md#spoof-settings) 対策ポリシーで使用できるのと同じスプーフィング設定。</span><span class="sxs-lookup"><span data-stu-id="84df1-137">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="84df1-138">偽装の設定</span><span class="sxs-lookup"><span data-stu-id="84df1-138">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [<span data-ttu-id="84df1-139">高度なフィッシングしきい値</span><span class="sxs-lookup"><span data-stu-id="84df1-139">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - <span data-ttu-id="84df1-140">[標準のプレセット](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users)のセキュリティ ポリシーおよび**Strict Preset Security Policy (標準のプレセット セキュリティ ポリシー) という名前の安全なリンク ポリシー**。 **Standard Preset Security Policy**</span><span class="sxs-lookup"><span data-stu-id="84df1-140">[Safe Links policies](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

  - <span data-ttu-id="84df1-141">[「標準のプセットの](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users)**セキュリティ ポリシー」と「Strict** **Preset Security Policy」という名前の安全な添付ファイル ポリシー**。</span><span class="sxs-lookup"><span data-stu-id="84df1-141">[Safe Attachments policies](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

<span data-ttu-id="84df1-142">EOP 保護は、ATP 保護とは異なるユーザーに適用できる点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="84df1-142">Note that you can apply EOP protections to different users than ATP protections.</span></span>

### <a name="policy-settings-in-preset-security-policies"></a><span data-ttu-id="84df1-143">事前設定されたセキュリティ ポリシーのポリシー設定</span><span class="sxs-lookup"><span data-stu-id="84df1-143">Policy settings in preset security policies</span></span>

<span data-ttu-id="84df1-144">保護プロファイルのポリシー設定は変更できません。</span><span class="sxs-lookup"><span data-stu-id="84df1-144">You can't modify the policy settings in the protection profiles.</span></span> <span data-ttu-id="84df1-145">**Standard および** **Strict のポリシー**設定値は、EOP と ATP セキュリティの[推奨設定Office説明されています](recommended-settings-for-eop-and-office365-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="84df1-145">The **Standard** and **Strict** policy setting values are described in [Recommended settings for EOP and Office 365 ATP security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a><span data-ttu-id="84df1-146">事前に設定されたセキュリティ ポリシーおよびその他のポリシーの優先順位</span><span class="sxs-lookup"><span data-stu-id="84df1-146">Order of precedence for preset security policies and other policies</span></span>

<span data-ttu-id="84df1-147">複数のポリシーがユーザーに適用されている場合は、次の順序が最高の優先度から最低の優先度の順に適用されます。</span><span class="sxs-lookup"><span data-stu-id="84df1-147">When multiple policies are applied to a user, the following order is applied from highest priority to lowest priority:</span></span>

1. <span data-ttu-id="84df1-148">**高い保護プレセット** のセキュリティ ポリシー</span><span class="sxs-lookup"><span data-stu-id="84df1-148">**Strict protection** preset security policy</span></span>
2. <span data-ttu-id="84df1-149">**標準保護** プレセット セキュリティ ポリシー</span><span class="sxs-lookup"><span data-stu-id="84df1-149">**Standard protection** preset security policy</span></span>
3. <span data-ttu-id="84df1-150">カスタム セキュリティ ポリシー</span><span class="sxs-lookup"><span data-stu-id="84df1-150">Custom security policies</span></span>
4. <span data-ttu-id="84df1-151">既定のセキュリティ ポリシー</span><span class="sxs-lookup"><span data-stu-id="84df1-151">Default security policies</span></span>

<span data-ttu-id="84df1-152">つまり、高い保護ポリシーの設定は **、標準** 保護ポリシーの設定より優先されます。 **これは** 、カスタム ポリシーからの設定を上書きします。これは、既定のポリシーからの設定を上書きします。</span><span class="sxs-lookup"><span data-stu-id="84df1-152">In other words, the settings of the **Strict protection** policy override the settings of the **Standard protection** policy, which overrides the settings from a custom policy, which overrides the settings from the default policy.</span></span>

## <a name="assign-preset-security-policies-to-users"></a><span data-ttu-id="84df1-153">事前設定したセキュリティ ポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="84df1-153">Assign preset security policies to users</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="84df1-154">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="84df1-154">What do you need to know before you begin?</span></span>

- <span data-ttu-id="84df1-155"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="84df1-155">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="84df1-156">[設定済みのセキュリティ ポリシー **] ページに直接移動するには**、. <https://protection.office.com/presetSecurityPolicies></span><span class="sxs-lookup"><span data-stu-id="84df1-156">To go directly to the **Preset security policies** page, use <https://protection.office.com/presetSecurityPolicies>.</span></span>

- <span data-ttu-id="84df1-157">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84df1-157">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="84df1-158">このトピックの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="84df1-158">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="84df1-159">事前設定されたセキュリティ ポリシーを構成するには、次の役割グループのいずれかのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="84df1-159">To configure preset security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="84df1-160">**組織の管理**または[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ管理者**。</span><span class="sxs-lookup"><span data-stu-id="84df1-160">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="84df1-161">**組織の管理**または [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**検疫管理**。</span><span class="sxs-lookup"><span data-stu-id="84df1-161">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="84df1-162">事前に設定されたセキュリティ ポリシーに読み取り専用アクセスするには、次の役割グループのいずれかのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="84df1-162">For read-only access to preset security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="84df1-163">[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ閲覧者**。</span><span class="sxs-lookup"><span data-stu-id="84df1-163">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="84df1-164">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**表示限定の組織管理**。</span><span class="sxs-lookup"><span data-stu-id="84df1-164">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a><span data-ttu-id="84df1-165">セキュリティ/コンプライアンス センターを&、事前設定のセキュリティ ポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="84df1-165">Use the Security & Compliance Center to assign preset security policies to users</span></span>

1. <span data-ttu-id="84df1-166">セキュリティ コンプライアンス センターから&、脅威管理**ポリシーの** \> **Policy** \> **プレセットのセキュリティ ポリシーに移動します**。</span><span class="sxs-lookup"><span data-stu-id="84df1-166">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Preset security policies**.</span></span>

2. <span data-ttu-id="84df1-167">[Standard **protection]** (保護または **[ Strict Protection)] で、[Edit]** を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="84df1-167">Under **Standard protection** or **Strict protection**, click **Edit**.</span></span>

3. <span data-ttu-id="84df1-168">標準**保護の適用ウィザードまたは\*\*\*\*高い取り消し保護ウィザード**が開始します。</span><span class="sxs-lookup"><span data-stu-id="84df1-168">The **Apply Standard protection** or **Apply Strict protection** wizard starts.</span></span> <span data-ttu-id="84df1-169">EOP 保護 **が適用されるには、EOP** 保護が適用される内部の [受信者を](#policies-in-preset-security-policies) 特定します。</span><span class="sxs-lookup"><span data-stu-id="84df1-169">On the **EOP protections apply to** step, identify the internal recipients that the [EOP protections](#policies-in-preset-security-policies) apply to:</span></span>

   1. <span data-ttu-id="84df1-170">[条件 **の追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="84df1-170">Click **Add a condition**.</span></span> <span data-ttu-id="84df1-171">表示されるドロップダウンで、[適用する条件: **Applied if**</span><span class="sxs-lookup"><span data-stu-id="84df1-171">In the dropdown that appears, select a condition under **Applied if**:</span></span>

      - <span data-ttu-id="84df1-172">**受信者が次の場合**</span><span class="sxs-lookup"><span data-stu-id="84df1-172">**The recipients are**</span></span>
      - <span data-ttu-id="84df1-173">**受信者が次のメンバーの場合**</span><span class="sxs-lookup"><span data-stu-id="84df1-173">**The recipients are members of**</span></span>
      - <span data-ttu-id="84df1-174">**受信者のドメインが**</span><span class="sxs-lookup"><span data-stu-id="84df1-174">**The recipient domains are**</span></span>

      <span data-ttu-id="84df1-175">一度に使用できる条件は 1 つのみですが、条件には複数の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="84df1-175">You can only use a condition once, but you can specify multiple values for the condition.</span></span> <span data-ttu-id="84df1-176">同じ条件に複数の値がある場合、OR ロジック (例、 _\<recipient1\>_ など) が使用されます _\<recipient2\>_ 。</span><span class="sxs-lookup"><span data-stu-id="84df1-176">Multiple values of the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span>

   2. <span data-ttu-id="84df1-177">選択した条件が、シェード セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="84df1-177">The condition that you selected appears in a shaded section.</span></span> <span data-ttu-id="84df1-178">そのセクションで、以下のボックス **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="84df1-178">In that section, click in the **Any of these** box.</span></span> <span data-ttu-id="84df1-179">しばらく待つと、一覧が表示され、値を選択できます。</span><span class="sxs-lookup"><span data-stu-id="84df1-179">If you wait a moment, a list will appear so you can select a value.</span></span> <span data-ttu-id="84df1-180">または、値を入力してリストにフィルターを適用し、値を選択できます。</span><span class="sxs-lookup"><span data-stu-id="84df1-180">Or, you can start typing a value to filter the list and select a value.</span></span> <span data-ttu-id="84df1-181">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="84df1-181">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="84df1-182">個別の値を削除するには、値の \*\*[削除\*\* ![ ] ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="84df1-182">To remove an individual value, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span> <span data-ttu-id="84df1-183">条件全体を削除するには、条件の [ **削除** ![ ] ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="84df1-183">To remove the entire condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   3. <span data-ttu-id="84df1-184">別の条件を追加するには、[ **条件を追加] をクリック** し、残りの条件から選択します。</span><span class="sxs-lookup"><span data-stu-id="84df1-184">To add another condition, click **Add a condition** and select from the remaining conditions.</span></span> <span data-ttu-id="84df1-185">さまざまな条件では AND ロジック (およびなど) が _\<recipient1\>_ 使います _\<member of group 1\>_ 。</span><span class="sxs-lookup"><span data-stu-id="84df1-185">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

      <span data-ttu-id="84df1-186">上記の手順を繰り返して条件に値を追加し、条件が満たないか、不足するまでこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="84df1-186">Repeat the previous step to add values to the condition, and repeat this step as many times as necessary or until you run out of conditions.</span></span>

   4. <span data-ttu-id="84df1-187">例外を追加するには、[条件の **追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="84df1-187">To add an exception, click **Add a condition**.</span></span> <span data-ttu-id="84df1-188">表示されるドロップダウンで、[いつ次の場合を除く" の下に条件 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="84df1-188">In the dropdown that appears, select a condition under **Except when**.</span></span> <span data-ttu-id="84df1-189">設定と動作は、条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="84df1-189">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="84df1-190">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84df1-190">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="84df1-191">組織が Office 365 ATP を使用している場合は、Office 365 **ATP** 保護が適用される内部の [受信者を特定するための手順に従う](#policies-in-preset-security-policies) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="84df1-191">If your organization has Office 365 ATP, you're taken to the **ATP protections apply to** step to identify the internal recipients that the [Office 365 ATP protections](#policies-in-preset-security-policies) apply to.</span></span>

   <span data-ttu-id="84df1-192">設定と動作は、EOP 保護が手順 **に適用されるのとまったく同** じです。</span><span class="sxs-lookup"><span data-stu-id="84df1-192">The settings and behavior are exactly like the **EOP protections apply to** step.</span></span>

   <span data-ttu-id="84df1-193">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84df1-193">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="84df1-194">[確認 **] の** 手順で選択した内容を確認し、[確認] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="84df1-194">On the **Confirm** step, verify your selections, and then click **Confirm**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a><span data-ttu-id="84df1-195">セキュリティ コンプライアンス センターを&、既定のセキュリティ ポリシーの割り当てを変更する</span><span class="sxs-lookup"><span data-stu-id="84df1-195">Use the Security & Compliance Center to modify the assignments of preset security policies</span></span>

<span data-ttu-id="84df1-196">標準保護または高い保護のセキュリティ**Standard protection**ポリシーを割り当てて変更する**手順**は、事前に設定されたセキュリティ ポリシーをユーザーに最初に割り[当ててから行う手順と同じです](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users)。</span><span class="sxs-lookup"><span data-stu-id="84df1-196">The steps to modify the assignment of the **Standard protection** or **Strict protection** security policy are the same as when you initially [assigned the preset security policies to users](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users).</span></span>

<span data-ttu-id="84df1-197">既存の条件**と例外を保持\*\*\*\*したままで、** 標準の保護または制限付き保護セキュリティ ポリシーを無効にするには、トグルを **[Disabled]** にスライドします。</span><span class="sxs-lookup"><span data-stu-id="84df1-197">To disable the **Standard protection** or **Strict protection** security policies while still preserving the existing conditions and exceptions, slide the toggle to **Disabled**.</span></span> <span data-ttu-id="84df1-198">ポリシーを有効にするには、トグルを有効に切り替 **えて有効にします**。</span><span class="sxs-lookup"><span data-stu-id="84df1-198">To enable the policies, slide the toggle to **Enabled**.</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="84df1-199">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="84df1-199">How do you know these procedures worked?</span></span>

<span data-ttu-id="84df1-200">標準保護または制限の保護のセキュリティ**ポリシー\*\*\*\*がユーザー**に正常に割り当てられたことを確認するには、既定値が標準の保護設定と**異なる保護**設定を使用します。これは **、[制限する保護] 設定とは異**なります。</span><span class="sxs-lookup"><span data-stu-id="84df1-200">To verify that you've successfully assigned the **Standard protection** or **Strict protection** security policy to a user, use a protection setting where the default value is different than the **Standard protection** setting, which is different that the **Strict protection** setting.</span></span>

<span data-ttu-id="84df1-201">たとえば、(信頼度の高いスパムでない) 電子メールの場合は、メッセージが標準保護ユーザーの [迷惑メール] フォルダー **に配信され** 、厳密に **保護ユーザーの場合は検疫** されます。</span><span class="sxs-lookup"><span data-stu-id="84df1-201">For example, for email that's detected as spam (not high confidence spam) verify that the message is delivered to the Junk Email folder for **Standard protection** users, and quarantined for **Strict protection** users.</span></span>

<span data-ttu-id="84df1-202">または、バ [ルク メールの場合](bulk-complaint-level-values.md)は、BCL 値 6 以上が標準保護ユーザー用迷惑メール フォルダー **にメッセージを配信し** 、BCL 値 4 以上で厳密な保護ユーザーに向け **、メッセージを検疫したことを確認** します。</span><span class="sxs-lookup"><span data-stu-id="84df1-202">Or, for [bulk email](bulk-complaint-level-values.md), verify that the BCL value 6 or higher delivers the message to the Junk Email folder for **Standard protection** users, and the BCL value 4 or higher quarantines the message for **Strict protection** users.</span></span>
