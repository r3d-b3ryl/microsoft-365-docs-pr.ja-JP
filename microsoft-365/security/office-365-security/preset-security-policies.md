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
description: 管理者は、Exchange Online Protection (EOP) および Microsoft Defender for Office 365 の保護機能において標準ポリシー設定と厳密なポリシー設定を適用する方法を学習できます。
ms.openlocfilehash: e968f7ea768ac8a0b402c28f3830a52b44afa342
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572779"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="0fdb0-103">EOP および Microsoft Defender for Office 365 の事前設定されたセキュリティポリシー</span><span class="sxs-lookup"><span data-stu-id="0fdb0-103">Preset security policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="0fdb0-104">事前設定されたセキュリティポリシーにより、すべての推奨されるスパム、マルウェア、およびフィッシングポリシーをユーザーに一度に適用するための一元的な場所が提供されます。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-104">Preset security policies provide a centralized location for applying all of the recommended spam, malware, and phishing policies to users at once.</span></span> <span data-ttu-id="0fdb0-105">ポリシー設定は構成できません。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-105">The policy settings are not configurable.</span></span> <span data-ttu-id="0fdb0-106">その代わりに、ユーザーは microsoft によって設定され、問題のあるコンテンツをユーザーに保持していなくても、作業を中断することなくバランスを取るために、データセンターの観察とエクスペリエンスに基づいています。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-106">Instead, they are set by us and are based on our observations and experiences in the datacenters for a balance between keeping harmful content away from users without disrupting their work.</span></span>

<span data-ttu-id="0fdb0-107">このトピックの残りの部分では、事前設定されたセキュリティポリシーとそれらを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-107">The rest of this topic describes preset security policies and how to configure them.</span></span>

## <a name="what-preset-security-policies-are-made-of"></a><span data-ttu-id="0fdb0-108">事前設定されたセキュリティポリシーの内容</span><span class="sxs-lookup"><span data-stu-id="0fdb0-108">What preset security policies are made of</span></span>

<span data-ttu-id="0fdb0-109">事前設定されたセキュリティポリシーは、次の要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-109">Preset security policies consist of the following elements:</span></span>

- <span data-ttu-id="0fdb0-110">プロファイル</span><span class="sxs-lookup"><span data-stu-id="0fdb0-110">Profiles</span></span>
- <span data-ttu-id="0fdb0-111">Policies</span><span class="sxs-lookup"><span data-stu-id="0fdb0-111">Policies</span></span>
- <span data-ttu-id="0fdb0-112">ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="0fdb0-112">Policy settings</span></span>

<span data-ttu-id="0fdb0-113">また、複数の事前設定されたセキュリティポリシーやその他のポリシーが同じユーザーに適用される場合は、優先順位が重要です。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-113">In addition, the order of precedence is important if multiple preset security policies and other policies apply to the same person.</span></span>

### <a name="profiles-in-preset-security-policies"></a><span data-ttu-id="0fdb0-114">事前設定されるセキュリティポリシーのプロファイル</span><span class="sxs-lookup"><span data-stu-id="0fdb0-114">Profiles in preset security policies</span></span>

<span data-ttu-id="0fdb0-115">プロファイルは、保護レベルを決定します。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-115">A profile determines the level of protection.</span></span> <span data-ttu-id="0fdb0-116">次のプロファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-116">The following profiles are available:</span></span>

- <span data-ttu-id="0fdb0-117">**標準保護**: ほとんどのユーザーに適したベースライン保護プロファイル。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-117">**Standard protection**: A baseline protection profile that's suitable for most users.</span></span>
- <span data-ttu-id="0fdb0-118">**厳重な保護**: 選択したユーザーのために、より厳しい保護プロファイルを使用します (高価値のターゲットまたは優先度の高いユーザー)。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-118">**Strict protection**: A more aggressive protection profile for selected users (high value targets or priority users).</span></span>

<span data-ttu-id="0fdb0-119">ルールは、プロファイルが適用されているかどうかを決定する条件と例外を指定して使用します。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-119">You use rules with conditions and exceptions that determine who the profiles are or are not applied to.</span></span>

<span data-ttu-id="0fdb0-120">各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-120">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="0fdb0-121">同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-121">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="0fdb0-122">a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-122">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

<span data-ttu-id="0fdb0-123">使用可能な条件と例外は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-123">The available conditions and exceptions are:</span></span>

- <span data-ttu-id="0fdb0-124">**受信者は**、組織内のメールボックス、メールユーザー、またはメール連絡先です。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-124">**The recipients are**: Mailboxes, mail users, or mail contacts in your organization.</span></span>
- <span data-ttu-id="0fdb0-125">**受信者が** 組織内のグループのメンバーである。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-125">**The recipients are members of**: Groups in your organization.</span></span>
- <span data-ttu-id="0fdb0-126">**受信者のドメインは、** Microsoft 365 で構成されている承認済みドメインです。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-126">**The recipient domains are**: Accepted domains that are configured in Microsoft 365.</span></span>

### <a name="policies-in-preset-security-policies"></a><span data-ttu-id="0fdb0-127">事前設定されるセキュリティポリシーのポリシー</span><span class="sxs-lookup"><span data-stu-id="0fdb0-127">Policies in preset security policies</span></span>

<span data-ttu-id="0fdb0-128">事前設定されたセキュリティポリシーでは、EOP のさまざまな保護機能と Microsoft Defender for Office 365 の対応するポリシーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-128">Preset security policies use the corresponding policies from the various protection features in EOP and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="0fdb0-129">これらのポリシーは、**標準保護** または厳格な **保護** の事前設定のセキュリティポリシーをユーザーに割り当てた _後_ に作成されます。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-129">These policies are created _after_ you assign the **Standard protection** or **Strict protection** preset security policies to users.</span></span> <span data-ttu-id="0fdb0-130">これらのポリシーを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-130">You can't modify these policies.</span></span>

- <span data-ttu-id="0fdb0-131">**Exchange Online Protection (EOP) ポリシー**: これには、exchange online メールボックスを使用する Microsoft 365 組織と、exchange online メールボックスを持たないスタンドアロン EOP 組織が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-131">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="0fdb0-132">**標準の事前設定** されたセキュリティポリシーと **厳密な事前設定セキュリティポリシー** という名前 [のスパム対策ポリシー](configure-your-spam-filter-policies.md) 。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-132">[Anti-spam policies](configure-your-spam-filter-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="0fdb0-133">**標準の事前設定** されたセキュリティポリシーと **厳密な事前設定セキュリティポリシー** という名前 [のマルウェア対策ポリシー](configure-anti-malware-policies.md) 。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-133">[Anti-malware policies](configure-anti-malware-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>
  - <span data-ttu-id="0fdb0-134">EOP の **既定のセキュリティポリシー** および厳密な事前設定された **セキュリティポリシー** (スプーフィング設定) という名前の [フィッシング対策ポリシー](set-up-anti-phishing-policies.md#spoof-settings)を設定します。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-134">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings) named **Standard Preset Security Policy** and **Strict Preset Security Policy** (spoof settings).</span></span>

- <span data-ttu-id="0fdb0-135">**Microsoft Defender For office 365 ポリシー**: これには、office 365 アドオンサブスクリプションの Microsoft 365 E5 または Defender を使用する組織が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-135">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="0fdb0-136">Microsoft Defender のマルウェア対策ポリシー Office 365 の場合は、 **標準の事前設定** されたセキュリティポリシーと、次のような **厳格な事前設定セキュリティポリシー** が指定されています。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-136">Anti-phishing policies in Microsoft Defender for Office 365 named **Standard Preset Security Policy** and **Strict Preset Security Policy**, which include:</span></span>

    - <span data-ttu-id="0fdb0-137">EOP のフィッシング対策ポリシーで使用可能なものと同じ [スプーフィング設定](set-up-anti-phishing-policies.md#spoof-settings) 。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-137">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="0fdb0-138">偽装設定</span><span class="sxs-lookup"><span data-stu-id="0fdb0-138">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="0fdb0-139">高度なフィッシングしきい値</span><span class="sxs-lookup"><span data-stu-id="0fdb0-139">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="0fdb0-140">[安全なリンク]**標準の事前設定** されたセキュリティポリシーと **厳密な事前設定セキュリティポリシー** という名前の [ポリシー](set-up-atp-safe-links-policies.md) 。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-140">[Safe Links policies](set-up-atp-safe-links-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

  - <span data-ttu-id="0fdb0-141">[[安全な添付ファイル](set-up-atp-safe-attachments-policies.md)]**標準の既定のセキュリティポリシー** と、厳密に設定された **セキュリティポリシー** という名前のポリシー。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-141">[Safe Attachments policies](set-up-atp-safe-attachments-policies.md) named **Standard Preset Security Policy** and **Strict Preset Security Policy**.</span></span>

<span data-ttu-id="0fdb0-142">Microsoft Defender for Office 365 の保護とは異なるユーザーに EOP 保護を適用することができることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-142">Note that you can apply EOP protections to different users than Microsoft Defender for Office 365 protections.</span></span>

### <a name="policy-settings-in-preset-security-policies"></a><span data-ttu-id="0fdb0-143">事前設定されるセキュリティポリシーのポリシー設定</span><span class="sxs-lookup"><span data-stu-id="0fdb0-143">Policy settings in preset security policies</span></span>

<span data-ttu-id="0fdb0-144">保護プロファイルでポリシー設定を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-144">You can't modify the policy settings in the protection profiles.</span></span> <span data-ttu-id="0fdb0-145">[ **標準** および **厳密** なポリシー設定] の値については、「 [EOP の推奨設定」および「office 365 のセキュリティのための Microsoft Defender](recommended-settings-for-eop-and-office365-atp.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-145">The **Standard** and **Strict** policy setting values are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a><span data-ttu-id="0fdb0-146">事前設定されたセキュリティポリシーおよびその他のポリシーの優先順位</span><span class="sxs-lookup"><span data-stu-id="0fdb0-146">Order of precedence for preset security policies and other policies</span></span>

<span data-ttu-id="0fdb0-147">ユーザーに複数のポリシーが適用されている場合、次の順序は、優先度の高いものから順に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-147">When multiple policies are applied to a user, the following order is applied from highest priority to lowest priority:</span></span>

1. <span data-ttu-id="0fdb0-148">**厳格な保護** の事前設定セキュリティポリシー</span><span class="sxs-lookup"><span data-stu-id="0fdb0-148">**Strict protection** preset security policy</span></span>
2. <span data-ttu-id="0fdb0-149">**標準保護** の事前設定セキュリティポリシー</span><span class="sxs-lookup"><span data-stu-id="0fdb0-149">**Standard protection** preset security policy</span></span>
3. <span data-ttu-id="0fdb0-150">カスタムセキュリティポリシー</span><span class="sxs-lookup"><span data-stu-id="0fdb0-150">Custom security policies</span></span>
4. <span data-ttu-id="0fdb0-151">既定のセキュリティポリシー</span><span class="sxs-lookup"><span data-stu-id="0fdb0-151">Default security policies</span></span>

<span data-ttu-id="0fdb0-152">つまり、 **厳格な保護** ポリシーの設定は、 **標準保護** ポリシーの設定を上書きします。これは、カスタムポリシーの設定を上書きします。これにより、既定のポリシーの設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-152">In other words, the settings of the **Strict protection** policy override the settings of the **Standard protection** policy, which overrides the settings from a custom policy, which overrides the settings from the default policy.</span></span>

## <a name="assign-preset-security-policies-to-users"></a><span data-ttu-id="0fdb0-153">事前設定されるセキュリティポリシーのユーザーへの割り当て</span><span class="sxs-lookup"><span data-stu-id="0fdb0-153">Assign preset security policies to users</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0fdb0-154">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="0fdb0-154">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0fdb0-155"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-155">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="0fdb0-156">[事前設定された **セキュリティポリシー** ] ページに直接移動するには、を使用 <https://protection.office.com/presetSecurityPolicies> します。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-156">To go directly to the **Preset security policies** page, use <https://protection.office.com/presetSecurityPolicies>.</span></span>

- <span data-ttu-id="0fdb0-157">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-157">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="0fdb0-158">この記事に記載されている手順を実行するには、事前にアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-158">You need to be assigned permissions before you can do the procedures in this article:</span></span>

  - <span data-ttu-id="0fdb0-159">事前設定されたセキュリティポリシーを構成するには、[セキュリティ & コンプライアンスセンター](permissions-in-the-security-and-compliance-center.md)で、**組織の管理** または **セキュリティ管理者** の役割のメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-159">To configure preset security policies, you need to be a member of the **Organization Management** or **Security Administrator** roles in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="0fdb0-160">事前設定されたセキュリティポリシーに対する読み取り専用アクセスでは、[セキュリティ & コンプライアンスセンター](permissions-in-the-security-and-compliance-center.md)の **グローバル閲覧** 者役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-160">For read-only access to preset security policies, you need to be a member of the **Global Reader** role group in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a><span data-ttu-id="0fdb0-161">セキュリティ & コンプライアンスセンターを使用して、事前に設定されたセキュリティポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="0fdb0-161">Use the Security & Compliance Center to assign preset security policies to users</span></span>

1. <span data-ttu-id="0fdb0-162">[セキュリティ & コンプライアンスセンター] で、[ **脅威管理** \> **ポリシー** ] \> **プリセットセキュリティポリシー** に移動します。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-162">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Preset security policies**.</span></span>

2. <span data-ttu-id="0fdb0-163">[ **標準保護** ] または [ **厳重な保護**] で、[ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-163">Under **Standard protection** or **Strict protection**, click **Edit**.</span></span>

3. <span data-ttu-id="0fdb0-164">[ **標準保護を適用** する] または [ **厳格な保護を適用** する] ウィザードが起動します。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-164">The **Apply Standard protection** or **Apply Strict protection** wizard starts.</span></span> <span data-ttu-id="0fdb0-165">[ **EOP 保護の適用先** ] ステップで、 [EOP 保護](#policies-in-preset-security-policies) を適用する内部の受信者を特定します。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-165">On the **EOP protections apply to** step, identify the internal recipients that the [EOP protections](#policies-in-preset-security-policies) apply to:</span></span>

   1. <span data-ttu-id="0fdb0-166">[ **条件の追加] を** クリックします。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-166">Click **Add a condition**.</span></span> <span data-ttu-id="0fdb0-167">表示されるドロップダウンで、[適用済みの **場合**] の条件を選択します。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-167">In the dropdown that appears, select a condition under **Applied if**:</span></span>

      - <span data-ttu-id="0fdb0-168">**受信者の**</span><span class="sxs-lookup"><span data-stu-id="0fdb0-168">**The recipients are**</span></span>
      - <span data-ttu-id="0fdb0-169">**受信者がメンバーである**</span><span class="sxs-lookup"><span data-stu-id="0fdb0-169">**The recipients are members of**</span></span>
      - <span data-ttu-id="0fdb0-170">**受信者のドメイン**</span><span class="sxs-lookup"><span data-stu-id="0fdb0-170">**The recipient domains are**</span></span>

      <span data-ttu-id="0fdb0-171">条件は1回だけ使用できますが、条件に複数の値を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-171">You can only use a condition once, but you can specify multiple values for the condition.</span></span> <span data-ttu-id="0fdb0-172">同じ条件の複数の値を使用するか、ロジックを指定します (例: _\<recipient1\>_ または _\<recipient2\>_ )。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-172">Multiple values of the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span>

   2. <span data-ttu-id="0fdb0-173">選択した条件が影付きのセクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-173">The condition that you selected appears in a shaded section.</span></span> <span data-ttu-id="0fdb0-174">そのセクションで、 **次のいずれか** のボックスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-174">In that section, click in the **Any of these** box.</span></span> <span data-ttu-id="0fdb0-175">少し待つと、値を選択できるようにリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-175">If you wait a moment, a list will appear so you can select a value.</span></span> <span data-ttu-id="0fdb0-176">または、値の入力を開始して、リストにフィルターを適用し、値を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-176">Or, you can start typing a value to filter the list and select a value.</span></span> <span data-ttu-id="0fdb0-177">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-177">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="0fdb0-178">個々の値を削除するには、その値の [削除] アイコン **をクリックし** ![ ](../../media/scc-remove-icon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-178">To remove an individual value, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span> <span data-ttu-id="0fdb0-179">条件全体を削除するには、条件の [削除] アイコン **をクリックし** ![ ](../../media/scc-remove-icon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-179">To remove the entire condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   3. <span data-ttu-id="0fdb0-180">別の条件を追加するには、[ **条件の追加** ] をクリックし、残りの条件から選択します。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-180">To add another condition, click **Add a condition** and select from the remaining conditions.</span></span> <span data-ttu-id="0fdb0-181">さまざまな条件とロジック (たとえば、と) が使用さ _\<recipient1\>_ _\<member of group 1\>_ れます。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-181">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

      <span data-ttu-id="0fdb0-182">前の手順を繰り返して条件に値を追加し、必要に応じて、または条件が満たされなくなるまで、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-182">Repeat the previous step to add values to the condition, and repeat this step as many times as necessary or until you run out of conditions.</span></span>

   4. <span data-ttu-id="0fdb0-183">例外を追加するには、[ **条件の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-183">To add an exception, click **Add a condition**.</span></span> <span data-ttu-id="0fdb0-184">表示されたドロップダウンで、[ **when when**] の条件を選択します。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-184">In the dropdown that appears, select a condition under **Except when**.</span></span> <span data-ttu-id="0fdb0-185">設定と動作は、条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-185">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="0fdb0-186">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-186">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="0fdb0-187">組織が Microsoft Defender for Office 365 を使用している場合は、「 **ATP の保護を適用** 」の手順に進み、 [Microsoft defender for office 365 の保護](#policies-in-preset-security-policies) が適用される内部の受信者を特定します。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-187">If your organization has Microsoft Defender for Office 365, you're taken to the **ATP protections apply to** step to identify the internal recipients that the [Microsoft Defender for Office 365 protections](#policies-in-preset-security-policies) apply to.</span></span>

   <span data-ttu-id="0fdb0-188">設定と動作は、手順 **に適用される EOP 保護** とよく似ています。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-188">The settings and behavior are exactly like the **EOP protections apply to** step.</span></span>

   <span data-ttu-id="0fdb0-189">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-189">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="0fdb0-190">[ **確認** ] 手順で選択内容を確認し、[ **確認**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-190">On the **Confirm** step, verify your selections, and then click **Confirm**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a><span data-ttu-id="0fdb0-191">セキュリティ & コンプライアンスセンターを使用して、事前設定されたセキュリティポリシーの割り当てを変更する</span><span class="sxs-lookup"><span data-stu-id="0fdb0-191">Use the Security & Compliance Center to modify the assignments of preset security policies</span></span>

<span data-ttu-id="0fdb0-192">**標準保護** または **厳密保護** のセキュリティポリシーの割り当てを変更する手順は、最初 [に事前に設定したセキュリティポリシーをユーザーに割り当て](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users)た場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-192">The steps to modify the assignment of the **Standard protection** or **Strict protection** security policy are the same as when you initially [assigned the preset security policies to users](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users).</span></span>

<span data-ttu-id="0fdb0-193">既存の条件と例外を保持したまま、 **標準保護** または **厳格な保護** のセキュリティポリシーを無効にするには、[ **無効**] に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-193">To disable the **Standard protection** or **Strict protection** security policies while still preserving the existing conditions and exceptions, slide the toggle to **Disabled**.</span></span> <span data-ttu-id="0fdb0-194">ポリシーを有効にするには、[オン] を **スライドします。**</span><span class="sxs-lookup"><span data-stu-id="0fdb0-194">To enable the policies, slide the toggle to **Enabled**.</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="0fdb0-195">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="0fdb0-195">How do you know these procedures worked?</span></span>

<span data-ttu-id="0fdb0-196">**標準保護** または **厳格な保護** セキュリティポリシーがユーザーに正常に割り当てられたことを確認するには、保護設定を使用します。既定値は **標準保護** 設定とは異なります。これは **厳密な保護** 設定とは異なります。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-196">To verify that you've successfully assigned the **Standard protection** or **Strict protection** security policy to a user, use a protection setting where the default value is different than the **Standard protection** setting, which is different that the **Strict protection** setting.</span></span>

<span data-ttu-id="0fdb0-197">たとえば、スパムとして検出された電子メール (高精度スパムではない) の場合は、メッセージが [迷惑メール]**フォルダーに配信** され **Strict protection** ていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-197">For example, for email that's detected as spam (not high confidence spam) verify that the message is delivered to the Junk Email folder for **Standard protection** users, and quarantined for **Strict protection** users.</span></span>

<span data-ttu-id="0fdb0-198">または、 [バルクメール](bulk-complaint-level-values.md)の場合は、bcl 値6以上が **標準の保護** ユーザー用の迷惑メールフォルダーにメッセージを配信していることを確認し、bcl 値4以上の検疫を使用して、 **厳正な保護** ユーザーにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="0fdb0-198">Or, for [bulk email](bulk-complaint-level-values.md), verify that the BCL value 6 or higher delivers the message to the Junk Email folder for **Standard protection** users, and the BCL value 4 or higher quarantines the message for **Strict protection** users.</span></span>
