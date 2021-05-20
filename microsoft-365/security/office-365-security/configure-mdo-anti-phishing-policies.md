---
title: Microsoft Defender でフィッシング対策ポリシーを構成Office 365
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
description: 管理者は、Microsoft Defender を使用している組織で利用可能な高度なフィッシング対策ポリシーを作成、変更、および削除する方法をOffice 365。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3660b9574f4faf4ee9c0602ac23b36f8634650dc
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537909"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="c1479-103">Microsoft Defender でフィッシング対策ポリシーを構成Office 365</span><span class="sxs-lookup"><span data-stu-id="c1479-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c1479-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="c1479-104">**Applies to**</span></span>
- [<span data-ttu-id="c1479-105">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="c1479-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c1479-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c1479-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="c1479-107">[Microsoft Defender for Office 365](defender-for-office-365.md)のフィッシング対策ポリシーは、悪意のある偽装ベースのフィッシング攻撃や他の種類のフィッシング攻撃から組織を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c1479-107">Anti-phishing policies in [Microsoft Defender for Office 365](defender-for-office-365.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="c1479-108">Exchange Online Protection (EOP) のフィッシング対策ポリシーと microsoft Defender for Office 365 のフィッシング対策ポリシーの違いの詳細については、「フィッシング対策保護」を参照[してください](anti-phishing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="c1479-108">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="c1479-109">管理者は、既定のフィッシング対策ポリシーを表示、編集、および構成できます (ただし、削除はされません)。</span><span class="sxs-lookup"><span data-stu-id="c1479-109">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="c1479-110">さらに細分化するために、組織内の特定のユーザー、グループ、またはドメインに適用されるカスタムフィッシング対策ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="c1479-110">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="c1479-111">カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (実行順序) を変更できます。</span><span class="sxs-lookup"><span data-stu-id="c1479-111">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="c1479-112">フィッシング対策ポリシーは、セキュリティ コンプライアンス センターまたは PowerShell &構成Exchange Onlineできます。</span><span class="sxs-lookup"><span data-stu-id="c1479-112">You can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="c1479-113">Exchange Online Protection 組織 (つまり、Office 365 用 Microsoft Defender のない組織) で利用可能なフィッシング対策ポリシーの構成の詳細については[、「EOP](configure-anti-phishing-policies-eop.md)でフィッシング対策ポリシーを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1479-113">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, organizations without Microsoft Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="c1479-114">フィッシング対策ポリシーの基本的な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c1479-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="c1479-115">**フィッシング対策ポリシー**: 有効または無効にするフィッシング保護と、オプションを適用するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="c1479-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="c1479-116">**フィッシング対策ルール**: フィッシング対策ポリシーの優先度と受信者フィルター (ポリシーが適用されるユーザー) を指定します。</span><span class="sxs-lookup"><span data-stu-id="c1479-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="c1479-117">これらの 2 つの要素の違いは、セキュリティ コンプライアンス センターでフィッシング対策ポリシーを管理&ではありません。</span><span class="sxs-lookup"><span data-stu-id="c1479-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="c1479-118">ポリシーを作成すると、実際には両方に同じ名前を使用して、フィッシング対策ルールと関連付けられたフィッシング対策ポリシーを同時に作成します。</span><span class="sxs-lookup"><span data-stu-id="c1479-118">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="c1479-119">ポリシーを変更すると、名前、優先度、有効または無効、受信者フィルターに関連する設定によってフィッシング対策ルールが変更されます。</span><span class="sxs-lookup"><span data-stu-id="c1479-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="c1479-120">その他の設定はすべて、関連付けられたフィッシング対策ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="c1479-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="c1479-121">ポリシーを削除すると、フィッシング対策ルールと関連付けられたフィッシング対策ポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="c1479-121">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="c1479-122">PowerShell Exchange Onlineでは、ポリシーとルールを個別に管理します。</span><span class="sxs-lookup"><span data-stu-id="c1479-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="c1479-123">詳細については、この記事の後半Exchange Online「Microsoft Defender for Office 365フィッシング対策ポリシーを構成するために[PowerShell](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365)を使用する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1479-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) section later in this article.</span></span>

<span data-ttu-id="c1479-124">すべての Microsoft Defender for Office 365には、次のプロパティを持つ Office365 AntiPhish Default という名前のフィッシング対策ポリシーが組み込みされています。</span><span class="sxs-lookup"><span data-stu-id="c1479-124">Every Microsoft Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="c1479-125">ポリシーは、ポリシーに関連付けられたフィッシング対策ルール (受信者フィルター) がない場合でも、組織内のすべての受信者に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c1479-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="c1479-126">ポリシーにはカスタムの優先順位の値 **Lowest** が設定されており、変更することはできません (このポリシーは常に最後に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="c1479-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="c1479-127">作成するどのカスタム ポリシーも、より高い優先順位を持ちます。</span><span class="sxs-lookup"><span data-stu-id="c1479-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="c1479-128">ポリシーは既定のポリシー (**IsDefault** のプロパティが `True` の値になっている) であり、既定のポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="c1479-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="c1479-129">Office 365 の Microsoft Defender でのフィッシング対策保護の有効性を高めるには、特定のユーザーまたはユーザー グループに適用されるより厳密な設定でカスタムフィッシング対策ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c1479-129">To increase the effectiveness of anti-phishing protection in Microsoft Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c1479-130">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="c1479-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c1479-131"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="c1479-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="c1479-132">フィッシング対策ページに直接 **移動するには** 、 を使用します <https://protection.office.com/antiphishing> 。</span><span class="sxs-lookup"><span data-stu-id="c1479-132">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="c1479-133">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1479-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="c1479-134">この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1479-134">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="c1479-135">フィッシング対策ポリシーを追加、変更、削除するには、組織の管理役割グループまたはセキュリティ管理者役割グループのメンバー **である** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1479-135">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="c1479-136">フィッシング対策ポリシーへの読み取り専用アクセスには、グローバル リーダーまたはセキュリティ リーダーの役割グループのメンバー **である** 必要があります <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="c1479-136">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="c1479-137">詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1479-137">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="c1479-138">**注**:</span><span class="sxs-lookup"><span data-stu-id="c1479-138">**Notes**:</span></span>

  - <span data-ttu-id="c1479-139">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="c1479-139">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="c1479-140">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1479-140">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="c1479-141">[**組織の管理の表示のみ**][](/Exchange/permissions-exo/permissions-exo#role-groups)役割グループは、Exchange Online機能への読み取り専用アクセスも提供します <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="c1479-141">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="c1479-142"><sup>\*</sup> セキュリティ コンプライアンス センター&読み取り専用アクセスを使用すると、ユーザーはカスタムフィッシング対策ポリシーの設定を表示できます。</span><span class="sxs-lookup"><span data-stu-id="c1479-142"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="c1479-143">読み取り専用のユーザーは、既定のフィッシング対策ポリシーの設定を表示できます。</span><span class="sxs-lookup"><span data-stu-id="c1479-143">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="c1479-144">Microsoft Defender for microsoft Defender for Office 365のフィッシング対策ポリシーに関する推奨設定については、「Defender for Office 365 設定」[を参照してください](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="c1479-144">For our recommended settings for anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="c1479-145">新しいポリシーまたは更新されたポリシーを適用するには、最大 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="c1479-145">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="c1479-146">フィルター 処理パイプラインでフィッシング対策ポリシーが適用される場所については、「メール保護の順序と優先順位」 [を参照してください](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="c1479-146">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="c1479-147">セキュリティ コンプライアンス センター&使用して、Microsoft Defender でフィッシング対策ポリシーを作成Office 365</span><span class="sxs-lookup"><span data-stu-id="c1479-147">Use the Security & Compliance Center to create anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="c1479-148">セキュリティ & コンプライアンス センターでカスタムフィッシング対策ポリシーを作成すると、両方に同じ名前を使用して、フィッシング対策ルールと関連付けられたフィッシング対策ポリシーが同時に作成されます。</span><span class="sxs-lookup"><span data-stu-id="c1479-148">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="c1479-149">フィッシング対策ポリシーを作成する場合、ポリシーの名前、説明、およびポリシーが適用されるユーザーを識別する受信者フィルターのみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c1479-149">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="c1479-150">ポリシーを作成した後、ポリシーを変更して、既定のフィッシング対策設定を変更または確認できます。</span><span class="sxs-lookup"><span data-stu-id="c1479-150">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="c1479-151">[セキュリティ & コンプライアンス センター] で、[**脅威管理ポリシー** のフィッシング \>  \> **対策] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="c1479-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="c1479-152">[フィッシング **対策] ページで、[作成** ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="c1479-152">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="c1479-153">[ **新しいフィッシング対策ポリシーの作成] ウィザードが** 開きます。</span><span class="sxs-lookup"><span data-stu-id="c1479-153">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="c1479-154">[ポリシーに **名前を付け] ページ** で、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="c1479-154">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="c1479-155">**[名前]**: わかりやすい一意のポリシー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="c1479-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="c1479-156">**[説明]**: ポリシーについての説明を入力します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="c1479-156">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="c1479-157">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1479-157">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="c1479-158">表示される **[適用先]** ページで、ポリシーが適用される内部受信者を特定します。</span><span class="sxs-lookup"><span data-stu-id="c1479-158">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="c1479-159">各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c1479-159">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="c1479-160">同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="c1479-160">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="c1479-161">a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="c1479-161">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="c1479-162">[条件 **の追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c1479-162">Click **Add a condition**.</span></span> <span data-ttu-id="c1479-163">表示されるドロップダウンで、[適用する場合] で条件 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c1479-163">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="c1479-164">**受信者は:** 組織内の 1 つ以上のメールボックス、メール ユーザー、またはメール連絡先を指定します。</span><span class="sxs-lookup"><span data-stu-id="c1479-164">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="c1479-165">**受信者は: のメンバーです**。組織内の 1 つ以上のグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="c1479-165">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="c1479-166">**受信者ドメインは:** 組織内で構成されている 1 つ以上の受け入れ済みドメインの受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="c1479-166">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="c1479-167">条件を選択すると、対応するドロップダウンが [Any of **these] ボックスと一緒に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="c1479-167">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="c1479-168">ボックス内をクリックし、値の一覧をスクロールして選択します。</span><span class="sxs-lookup"><span data-stu-id="c1479-168">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="c1479-169">ボックス内をクリックし、入力を開始してリストをフィルター処理し、値を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1479-169">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="c1479-170">追加の値を追加するには、ボックス内の空の領域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1479-170">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="c1479-171">個々のエントリを削除するには、値 **の [削除]** ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1479-171">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="c1479-172">条件全体を削除するには、条件 **の [削除]** ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1479-172">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="c1479-173">追加の条件を追加するには、[条件の追加] **をクリックし** 、[適用する場合] で残りの値 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c1479-173">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="c1479-174">例外を追加するには、[条件の追加] **をクリックし** 、[条件を除く] で例外 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c1479-174">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="c1479-175">設定と動作は、条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="c1479-175">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="c1479-176">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1479-176">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="c1479-177">表示される **[設定の確認]** ページで、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="c1479-177">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="c1479-178">各設定で **[編集]** をクリックして変更できます。</span><span class="sxs-lookup"><span data-stu-id="c1479-178">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="c1479-179">完了したら、[このポリシーの作成 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c1479-179">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="c1479-180">表示 **される確認ダイアログで [OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1479-180">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="c1479-181">これらの一般的な設定を使用してフィッシング対策ポリシーを作成した後、次のセクションの手順を使用して、ポリシーの保護設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="c1479-181">After you create the anti-phishing policy with these general settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="c1479-182">コンプライアンス センターのセキュリティ &を使用して、Microsoft Defender のフィッシング対策ポリシーを変更Office 365</span><span class="sxs-lookup"><span data-stu-id="c1479-182">Use the Security & Compliance Center to modify anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="c1479-183">フィッシング対策ポリシー (作成した新しいポリシー、または既にカスタマイズした既存のポリシー) を変更するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="c1479-183">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="c1479-184">まだインストールされていない場合は、セキュリティ & コンプライアンス センターを開き、[脅威管理ポリシーのフィッシング対策] \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="c1479-184">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="c1479-185">変更するカスタムフィッシング対策ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c1479-185">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="c1479-186">既に選択されている場合は、選択を解除してもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="c1479-186">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="c1479-187">[**ポリシーの編集 \<name\> ] フライ** アウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1479-187">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="c1479-188">任意の **セクションで [** 編集] をクリックすると、そのセクションの設定にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c1479-188">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="c1479-189">次の手順は、セクションが表示される順序で示されますが、順番に表示されません (任意の順序でセクションを選択および変更できます)。</span><span class="sxs-lookup"><span data-stu-id="c1479-189">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="c1479-190">セクションで[編集] をクリックすると、使用可能な設定はウィザード形式で表示されますが、任意の順序でページ内に移動できます。任意のページで [保存]  ( ![ ](../../media/scc-remove-icon.png) **\<name\>** または [キャンセル] または [閉じる] アイコンをクリックして [ポリシーの編集] ページに戻ります (ウィザードの最後のページにアクセスして保存または終了する必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="c1479-190">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="c1479-191">**ポリシー設定**: [ **編集]** をクリックして、前のセクションでポリシーを作成した場合と同じ [設定を変更](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) します。</span><span class="sxs-lookup"><span data-stu-id="c1479-191">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) in the previous section:</span></span>

   - <span data-ttu-id="c1479-192">**名前**</span><span class="sxs-lookup"><span data-stu-id="c1479-192">**Name**</span></span>
   - <span data-ttu-id="c1479-193">**説明**</span><span class="sxs-lookup"><span data-stu-id="c1479-193">**Description**</span></span>
   - <span data-ttu-id="c1479-194">**適用先**</span><span class="sxs-lookup"><span data-stu-id="c1479-194">**Applied to**</span></span>
   - <span data-ttu-id="c1479-195">**設定を確認する**</span><span class="sxs-lookup"><span data-stu-id="c1479-195">**Review your settings**</span></span>

   <span data-ttu-id="c1479-196">完了したら、任意のページで **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1479-196">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="c1479-197">**偽装 :**[ **編集]** をクリックして、ポリシー内の保護された送信者と保護された送信者ドメインを変更します。</span><span class="sxs-lookup"><span data-stu-id="c1479-197">**Impersonation**: Click **Edit** to modify the protected senders and protected sender domains in the policy.</span></span> <span data-ttu-id="c1479-198">これらの設定は、受信メッセージの差出人アドレスで特定の送信者が (個別に、またはドメインによって) 検索するポリシーの条件です。</span><span class="sxs-lookup"><span data-stu-id="c1479-198">These settings are a condition for the policy that identifies specific senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="c1479-199">詳細については、「Microsoft Defender for Office 365」の「フィッシング対策ポリシーの偽装[設定」を参照してください](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="c1479-199">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="c1479-200">**保護するユーザーを追加する**: 既定値は Off **トグル** ![ オフです ](../../media/scc-toggle-off.png) 。</span><span class="sxs-lookup"><span data-stu-id="c1479-200">**Add users to protect**: The default value is **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span> <span data-ttu-id="c1479-201">オンにするには、トグルを [オン] にスライドし、表示される [ユーザーの追加 ![ ] ](../../media/scc-toggle-on.png) ボタンをクリックします。 </span><span class="sxs-lookup"><span data-stu-id="c1479-201">To turn it on, slide the toggle to **On** ![Toggle On](../../media/scc-toggle-on.png), and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="c1479-202">表示される **[ユーザーの追加** ] フライアウトで、次の値を構成します。</span><span class="sxs-lookup"><span data-stu-id="c1479-202">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="c1479-203">**電子メール アドレス**:</span><span class="sxs-lookup"><span data-stu-id="c1479-203">**Email address**:</span></span>

       - <span data-ttu-id="c1479-204">ボックス内をクリックし、選択するユーザーの一覧をスクロールします。</span><span class="sxs-lookup"><span data-stu-id="c1479-204">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="c1479-205">ボックス内をクリックし、入力を開始してリストをフィルター処理し、ユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c1479-205">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="c1479-206">エントリを削除するには、ユーザーの **[削除]** ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1479-206">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="c1479-207">**名前**: この値は、選択した電子メール アドレスに基づいて設定されますが、変更できます。</span><span class="sxs-lookup"><span data-stu-id="c1479-207">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="c1479-208">完了したら、任意のページで **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1479-208">When you're finished, click **Save** on any page.</span></span>

     <span data-ttu-id="c1479-209">既存のエントリを編集するには、リストで保護されたユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c1479-209">To edit an existing entry, select the protected user in the list.</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="c1479-210">各フィッシング対策ポリシーでは、最大 60 人の保護されたユーザー (送信者の電子メール アドレス) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c1479-210">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="c1479-211">複数のポリシーで同じ保護されたユーザーを指定できない。</span><span class="sxs-lookup"><span data-stu-id="c1479-211">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="c1479-212">送信者と受信者が以前に電子メールで通信した場合、ユーザー偽装保護は機能しません。</span><span class="sxs-lookup"><span data-stu-id="c1479-212">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="c1479-213">送信者と受信者がメールで通信したことがない場合、メッセージは偽装の試みとして識別されます。</span><span class="sxs-lookup"><span data-stu-id="c1479-213">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

   - <span data-ttu-id="c1479-214">**保護するドメインを追加する**: 次の設定の一方または両方を構成します。</span><span class="sxs-lookup"><span data-stu-id="c1479-214">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="c1479-215">**所有するドメインを自動的に含める**: 既定値は **Off トグル** ![ オフです ](../../media/scc-toggle-off.png) 。</span><span class="sxs-lookup"><span data-stu-id="c1479-215">**Automatically include the domains I own**: The default value is **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span> <span data-ttu-id="c1479-216">オンにするには、トグルを [オン] トグル **オンにスライド** ![ します ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="c1479-216">To turn it on, slide the toggle to **On** ![Toggle On](../../media/scc-toggle-on.png).</span></span>

       <span data-ttu-id="c1479-217">所有しているドメインを表示するには、[所有する **ドメインの表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c1479-217">To view the domains that you own, select **View domains I own**.</span></span>

     - <span data-ttu-id="c1479-218">**カスタム ドメインを含める**: 既定値は Off **トグル** ![ オフです ](../../media/scc-toggle-off.png) 。</span><span class="sxs-lookup"><span data-stu-id="c1479-218">**Include custom domains**: The default value is **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span> <span data-ttu-id="c1479-219">オンにするには、トグルを **[** オン] にスライドし、[ドメインの追加] ボックスにドメイン名 (contoso.com など) を入力し ![ ](../../media/scc-toggle-on.png) 、Enterキーを押し、必要に応じて繰り返します。</span><span class="sxs-lookup"><span data-stu-id="c1479-219">To turn it on, slide the toggle to **On** ![Toggle On](../../media/scc-toggle-on.png), and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

     > [!NOTE]
     > <span data-ttu-id="c1479-220">すべてのフィッシング対策ポリシーに最大 50 のドメインを設定できます。</span><span class="sxs-lookup"><span data-stu-id="c1479-220">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

   - <span data-ttu-id="c1479-221">**アクション**: [編集] **をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="c1479-221">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="c1479-222">**偽装ユーザーによって** 電子メールが送信される場合: [保護するユーザーの追加] で指定した保護されたユーザーの 1 つが送信者であるメッセージに対して、次のいずれかのアクション **を構成します**。</span><span class="sxs-lookup"><span data-stu-id="c1479-222">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="c1479-223">**アクションを適用しない**</span><span class="sxs-lookup"><span data-stu-id="c1479-223">**Don't apply any action**</span></span>
       - <span data-ttu-id="c1479-224">**メッセージを他の電子メール アドレスにリダイレクトする**</span><span class="sxs-lookup"><span data-stu-id="c1479-224">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="c1479-225">**受信者の迷惑メール フォルダーにメッセージを移動する**</span><span class="sxs-lookup"><span data-stu-id="c1479-225">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="c1479-226">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="c1479-226">**Quarantine the message**</span></span>
       - <span data-ttu-id="c1479-227">**メッセージを配信し、他のアドレスを Bcc 行に追加する**</span><span class="sxs-lookup"><span data-stu-id="c1479-227">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="c1479-228">**配信前にメッセージを削除する**</span><span class="sxs-lookup"><span data-stu-id="c1479-228">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="c1479-229">**偽装ドメインから** 電子メールが送信される場合: [保護するドメインの追加] で指定した保護されたドメインの 1 つで送信者のドメインがあるメッセージに対して、次のいずれかのアクションを構成 **します**。</span><span class="sxs-lookup"><span data-stu-id="c1479-229">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the sender's domain is in one of the protected domains you specified in **Add domains to protect**:</span></span>

       - <span data-ttu-id="c1479-230">**アクションを適用しない**</span><span class="sxs-lookup"><span data-stu-id="c1479-230">**Don't apply any action**</span></span>
       - <span data-ttu-id="c1479-231">**メッセージを他の電子メール アドレスにリダイレクトする**</span><span class="sxs-lookup"><span data-stu-id="c1479-231">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="c1479-232">**受信者の迷惑メール フォルダーにメッセージを移動する**</span><span class="sxs-lookup"><span data-stu-id="c1479-232">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="c1479-233">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="c1479-233">**Quarantine the message**</span></span>
       - <span data-ttu-id="c1479-234">**メッセージを配信し、他のアドレスを Bcc 行に追加する**</span><span class="sxs-lookup"><span data-stu-id="c1479-234">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="c1479-235">**配信前にメッセージを削除する**</span><span class="sxs-lookup"><span data-stu-id="c1479-235">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="c1479-236">[ **偽装の安全ヒントを有効にする] をクリック** し、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="c1479-236">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="c1479-237">**偽装ユーザーのヒントを表示する**</span><span class="sxs-lookup"><span data-stu-id="c1479-237">**Show tip for impersonated users**</span></span>
     - <span data-ttu-id="c1479-238">**偽装ドメインのヒントを表示する**</span><span class="sxs-lookup"><span data-stu-id="c1479-238">**Show tip for impersonated domains**</span></span>
     - <span data-ttu-id="c1479-239">**異常な文字のヒントを表示する**</span><span class="sxs-lookup"><span data-stu-id="c1479-239">**Show tip for unusual characters**</span></span>

     <span data-ttu-id="c1479-240">すべてのヒントの既定値は Off **トグル オフ** ![ です ](../../media/scc-toggle-off.png) 。</span><span class="sxs-lookup"><span data-stu-id="c1479-240">The default value for all tips is **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span> <span data-ttu-id="c1479-241">オンに設定するには、トグルを [オン]に[スライドします](../../media/scc-toggle-on.png)。</span><span class="sxs-lookup"><span data-stu-id="c1479-241">To turn any of them on, slide the toggle to **On** [Toggle On](../../media/scc-toggle-on.png).</span></span>

     <span data-ttu-id="c1479-242">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1479-242">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="c1479-243">**メールボックス インテリジェンス**:</span><span class="sxs-lookup"><span data-stu-id="c1479-243">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="c1479-244">**メールボックス インテリジェンスを有効にする:** 既定値は **On Toggle** [On です](../../media/scc-toggle-on.png)。</span><span class="sxs-lookup"><span data-stu-id="c1479-244">**Enable mailbox intelligence?**: The default value is **On** [Toggle On](../../media/scc-toggle-on.png).</span></span> <span data-ttu-id="c1479-245">オフにする場合は、トグルを Off トグル **オフにスライド** ![ します ](../../media/scc-toggle-off.png) 。</span><span class="sxs-lookup"><span data-stu-id="c1479-245">To turn it off, slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span>

     - <span data-ttu-id="c1479-246">**メールボックス インテリジェンス ベースの偽装保護を有効にする:** この設定は、[メールボックス インテリジェンスを有効にする] が **[オン**] の **場合にのみ** 使用できます。</span><span class="sxs-lookup"><span data-stu-id="c1479-246">**Enable mailbox intelligence based impersonation protection?**: This setting is available only if **Enable mailbox intelligence?** is **On**.</span></span> <span data-ttu-id="c1479-247">この設定をオンにすると、メールボックス インテリジェンス結果からの偽装検出のメッセージに対して実行するアクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c1479-247">Turn on this setting to specify the action to take on messages for impersonation detections from mailbox intelligence results.</span></span>

       <span data-ttu-id="c1479-248">[ **偽装ユーザーによって** 電子メールが送信される場合は、次のいずれかのアクション (保護されたユーザーと保護されたドメインで使用できるアクションと同じアクション) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c1479-248">In **If email is sent by an impersonated user**, you can specify one of the following actions (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="c1479-249">**アクションを適用** しない : この値は、[メールボックス インテリジェンスを有効にする]をオンにした場合と同じ結果になりますが、[メールボックス インテリジェンスベースの偽装保護を有効にする] をオフ **にしてください。**</span><span class="sxs-lookup"><span data-stu-id="c1479-249">**Don't apply any action**: Note that this value has the same result as turning on **Enable mailbox intelligence?** but turning off **Enable mailbox intelligence based impersonation protection?**.</span></span>
       - <span data-ttu-id="c1479-250">**メッセージを他の電子メール アドレスにリダイレクトする**</span><span class="sxs-lookup"><span data-stu-id="c1479-250">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="c1479-251">**受信者の迷惑メール フォルダーにメッセージを移動する**</span><span class="sxs-lookup"><span data-stu-id="c1479-251">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="c1479-252">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="c1479-252">**Quarantine the message**</span></span>
       - <span data-ttu-id="c1479-253">**メッセージを配信し、他のアドレスを Bcc 行に追加する**</span><span class="sxs-lookup"><span data-stu-id="c1479-253">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="c1479-254">**配信前にメッセージを削除する**</span><span class="sxs-lookup"><span data-stu-id="c1479-254">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="c1479-255">**信頼できる送信者とドメインを追加する**: ポリシーの例外を指定します。</span><span class="sxs-lookup"><span data-stu-id="c1479-255">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="c1479-256">**信頼できる送信者**:</span><span class="sxs-lookup"><span data-stu-id="c1479-256">**Trusted senders**:</span></span>

       - <span data-ttu-id="c1479-257">ボックス内をクリックし、選択するユーザーの一覧をスクロールします。</span><span class="sxs-lookup"><span data-stu-id="c1479-257">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="c1479-258">ボックス内をクリックし、入力を開始してリストをフィルター処理し、ユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c1479-258">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="c1479-259">エントリを削除するには、ユーザーの **[削除]** ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1479-259">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="c1479-260">**信頼済みドメイン**: ドメイン名 (たとえば、contoso.com)を入力し、Enter キーを押して、必要に応じて繰り返します。</span><span class="sxs-lookup"><span data-stu-id="c1479-260">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="c1479-261">**設定を確認する**: 個々の手順をクリックする代わりに、設定が概要に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1479-261">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="c1479-262">各セクションで **[編集]** をクリックすると、関連するページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="c1479-262">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="c1479-263">このページでは、次の設定 **をオン** または **オフに** 直接切り替えます。</span><span class="sxs-lookup"><span data-stu-id="c1479-263">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="c1479-264">**保護されたユーザー**</span><span class="sxs-lookup"><span data-stu-id="c1479-264">**Protected users**</span></span>
       - <span data-ttu-id="c1479-265">**保護されたドメイン** \>**所有するドメインを含める**</span><span class="sxs-lookup"><span data-stu-id="c1479-265">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="c1479-266">**保護されたドメイン** \>**保護されたドメイン**(カスタム ドメイン)</span><span class="sxs-lookup"><span data-stu-id="c1479-266">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="c1479-267">**メールボックス インテリジェンス**</span><span class="sxs-lookup"><span data-stu-id="c1479-267">**Mailbox intelligence**</span></span>

   <span data-ttu-id="c1479-268">完了したら、任意のページで **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1479-268">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="c1479-269">**ス** プーフィング : [編集] をクリックしてスプーフィング インテリジェンスをオンまたはオフにし、Outlook で認証されていない送信者 ID をオンまたはオフにし、ブロックされたスプーフィングされた送信者からのメッセージに適用するアクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="c1479-269">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="c1479-270">これらの設定の詳細については、「フィッシング対策ポリシー [のスプーフィング設定」を参照してください](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="c1479-270">For more information about these settings, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="c1479-271">これらの同じ設定は、EOP のフィッシング対策ポリシーでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="c1479-271">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="c1479-272">**スプーフィング フィルター設定**: スプーフィング **インテリジェンスを** 有効または無効にするには、[スプーフィング インテリジェンスを有効にする] 設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="c1479-272">**Spoofing filter settings**: Use the **Enable spoof intelligence?** setting to turn spoof intelligence on or off.</span></span> <span data-ttu-id="c1479-273">既定値は **On で**、オンのままにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c1479-273">The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="c1479-274">オフにする場合は、トグルを Off トグル **オフにスライド** ![ します ](../../media/scc-toggle-off.png) 。</span><span class="sxs-lookup"><span data-stu-id="c1479-274">To turn it off, slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span>

     > [!NOTE]
     > <span data-ttu-id="c1479-275">MX レコードがスプーフィング対策保護をオフにする必要Microsoft 365。代わりに、コネクタの拡張フィルターを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="c1479-275">You don't need to turn off anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="c1479-276">手順については、「拡張フィルタリング[for Connectors in Exchange Online」 を参照してください](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="c1479-276">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="c1479-277">**認証されていない送信者の設定**: 次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="c1479-277">**Unauthenticated sender settings**: You can configure the following settings:</span></span>
     - <span data-ttu-id="c1479-278">認証されていない送信者の疑問符 **(?)** 記号を有効にする: メッセージが SPF または DKIM チェックに合格しない場合に、メッセージが DMARC または複合認証に合格しない場合は、Outlook の [[](email-validation-and-authentication.md#composite-authentication)差出人] ボックスで送信者の写真に疑問符を追加します。</span><span class="sxs-lookup"><span data-stu-id="c1479-278">**Enable unauthenticated sender question mark (?) symbol?**: Add a question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span> <span data-ttu-id="c1479-279">既定値は [**オン**] です。</span><span class="sxs-lookup"><span data-stu-id="c1479-279">The default value is **On**.</span></span> <span data-ttu-id="c1479-280">オフにする場合は、トグルを Off トグル **オフにスライド** ![ します ](../../media/scc-toggle-off.png) 。</span><span class="sxs-lookup"><span data-stu-id="c1479-280">To turn it off, slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span>
     - <span data-ttu-id="c1479-281">**"via"** タグを有効にする: [From] ボックスの電子メール アドレスが DKIM 署名または **MAIL FROM** アドレスのドメインと異なる場合は、via タグ (chris@contoso.com 経由で fabrikam.com) を追加します。</span><span class="sxs-lookup"><span data-stu-id="c1479-281">**Enable "via" tag?**: Add the via tag (chris@contoso.com via fabrikam.com) if the email address in the From box is different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span> <span data-ttu-id="c1479-282">既定値は [**オン**] です。</span><span class="sxs-lookup"><span data-stu-id="c1479-282">The default value is **On**.</span></span> <span data-ttu-id="c1479-283">オフにする場合は、トグルを Off トグル **オフにスライド** ![ します ](../../media/scc-toggle-off.png) 。</span><span class="sxs-lookup"><span data-stu-id="c1479-283">To turn it off, slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="c1479-284">**アクション**: ブロックされたスプーフィングされた送信者からのメッセージに対して実行するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="c1479-284">**Actions**: Specify the action to take on messages from blocked spoofed senders:</span></span>

     <span data-ttu-id="c1479-285">**ドメインのスプーフィングが許可されていない** ユーザーからメールが送信された場合:</span><span class="sxs-lookup"><span data-stu-id="c1479-285">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="c1479-286">**受信者の迷惑メール フォルダーにメッセージを移動する**</span><span class="sxs-lookup"><span data-stu-id="c1479-286">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="c1479-287">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="c1479-287">**Quarantine the message**</span></span>

   - <span data-ttu-id="c1479-288">**設定を確認する**: 個々の手順をクリックする代わりに、設定が概要に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1479-288">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="c1479-289">各セクションで **[編集]** をクリックすると、関連するページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="c1479-289">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="c1479-290">このページでは、次の設定 **をオン** または **オフに** 直接切り替えます。</span><span class="sxs-lookup"><span data-stu-id="c1479-290">You can toggle the following settings **On** or **Off** directly on this page:</span></span>
       - <span data-ttu-id="c1479-291">**スプーフィング フィルターの設定**</span><span class="sxs-lookup"><span data-stu-id="c1479-291">**Spoof filter settings**</span></span>
       - <span data-ttu-id="c1479-292">**認証されていない送信者の設定**</span><span class="sxs-lookup"><span data-stu-id="c1479-292">**Unauthenticated sender settings**</span></span>
       - <span data-ttu-id="c1479-293">**Actions**</span><span class="sxs-lookup"><span data-stu-id="c1479-293">**Actions**</span></span>

   <span data-ttu-id="c1479-294">完了したら、任意のページで **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1479-294">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="c1479-295">**詳細設定:**[編集] **をクリック** して、高度なフィッシングしきい値を構成します。</span><span class="sxs-lookup"><span data-stu-id="c1479-295">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="c1479-296">詳細については、「Microsoft Defender for Office 365」の「フィッシング対策ポリシーの高度[なフィッシングのしきい値」を参照してください](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="c1479-296">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="c1479-297">**高度なフィッシングのしきい値**: 次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1479-297">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="c1479-298">**1 - Standard** (既定値です)。</span><span class="sxs-lookup"><span data-stu-id="c1479-298">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="c1479-299">**2 - アグレッシブ**</span><span class="sxs-lookup"><span data-stu-id="c1479-299">**2 - Aggressive**</span></span>
   - <span data-ttu-id="c1479-300">**3 - より積極的**</span><span class="sxs-lookup"><span data-stu-id="c1479-300">**3 - More aggressive**</span></span>
   - <span data-ttu-id="c1479-301">**4 - 最も積極的**</span><span class="sxs-lookup"><span data-stu-id="c1479-301">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="c1479-302">**設定を確認する**: [ **編集] を** クリックして、[高度なフィッシングのしきい値 **] ページに戻** ります。</span><span class="sxs-lookup"><span data-stu-id="c1479-302">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="c1479-303">完了したら、いずれかのページで [ **保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1479-303">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="c1479-304">[ポリシーの編集 **] \<Name\> ページに戻り**、設定を確認し、[閉じる] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="c1479-304">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a><span data-ttu-id="c1479-305">セキュリティ コンプライアンス センター&使用して、Microsoft Defender の既定のフィッシング対策ポリシーを変更Office 365</span><span class="sxs-lookup"><span data-stu-id="c1479-305">Use the Security & Compliance Center to modify the default anti-phishing policy in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="c1479-306">microsoft Defender for Office 365 の既定のフィッシング対策ポリシーは Office365 AntiPhish Default という名前で、ポリシーの一覧には表示されません。</span><span class="sxs-lookup"><span data-stu-id="c1479-306">The default anti-phishing policy in Microsoft Defender for Office 365 is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="c1479-307">既定のフィッシング対策ポリシーを変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c1479-307">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="c1479-308">[セキュリティ & コンプライアンス センター] で、[**脅威管理ポリシー** のフィッシング \>  \> **対策] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="c1479-308">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="c1479-309">[フィッシング **対策] ページで、[** 既定のポリシー] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c1479-309">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="c1479-310">[ **ポリシーの編集] [Office365 AntiPhish Default] ページ** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1479-310">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="c1479-311">次のセクションを使用できます。カスタム ポリシーを変更する場合と同じ [設定が含まれます](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="c1479-311">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span></span>

   - <span data-ttu-id="c1479-312">**偽装**</span><span class="sxs-lookup"><span data-stu-id="c1479-312">**Impersonation**</span></span>
   - <span data-ttu-id="c1479-313">**スプーフィング**</span><span class="sxs-lookup"><span data-stu-id="c1479-313">**Spoof**</span></span>
   - <span data-ttu-id="c1479-314">**詳細設定**</span><span class="sxs-lookup"><span data-stu-id="c1479-314">**Advanced settings**</span></span>

   <span data-ttu-id="c1479-315">既定のポリシーを変更すると、次の設定を使用できません。</span><span class="sxs-lookup"><span data-stu-id="c1479-315">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="c1479-316">[ポリシーの設定] セクションと値を確認できますが、[編集]リンクはないので、設定 (ポリシー名、説明、ポリシーが適用されるユーザー (すべての受信者に適用されます) を変更できます)。</span><span class="sxs-lookup"><span data-stu-id="c1479-316">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="c1479-317">既定のポリシーを削除できない。</span><span class="sxs-lookup"><span data-stu-id="c1479-317">You can't delete the default policy.</span></span>
   - <span data-ttu-id="c1479-318">既定のポリシーの優先度は変更できない (常に最後に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="c1479-318">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="c1479-319">[ポリシー **の編集] [Office365 AntiPhish Default]** ページで、設定を確認し、[閉じる] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="c1479-319">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="c1479-320">Microsoft Defender でユーザー設定のフィッシング対策ポリシーを有効または無効にOffice 365</span><span class="sxs-lookup"><span data-stu-id="c1479-320">Enable or disable custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="c1479-321">[セキュリティ & コンプライアンス センター] で、[**脅威管理ポリシー** のフィッシング \>  \> **対策] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="c1479-321">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="c1479-322">[状態] 列の値 **に注意** してください。</span><span class="sxs-lookup"><span data-stu-id="c1479-322">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="c1479-323">トグルを [オフ] に **スライドして** ![ 、 ](../../media/scc-toggle-off.png) ポリシーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="c1479-323">Slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png) to disable the policy.</span></span>

   - <span data-ttu-id="c1479-324">トグルを [オン] **に** ![ スライドして ](../../media/scc-toggle-on.png) 、ポリシーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="c1479-324">Slide the toggle to **On** ![Toggle On](../../media/scc-toggle-on.png) to enable the policy.</span></span>

<span data-ttu-id="c1479-325">既定のフィッシング対策ポリシーを無効にできない。</span><span class="sxs-lookup"><span data-stu-id="c1479-325">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="c1479-326">Microsoft Defender でユーザー設定のフィッシング対策ポリシーの優先度を設定Office 365</span><span class="sxs-lookup"><span data-stu-id="c1479-326">Set the priority of custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="c1479-327">既定では、フィッシング対策ポリシーには、作成された順序に基づく優先度が与えられる (新しいポリシーは、以前のポリシーよりも優先度が低くなります)。</span><span class="sxs-lookup"><span data-stu-id="c1479-327">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="c1479-328">優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。</span><span class="sxs-lookup"><span data-stu-id="c1479-328">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="c1479-329">2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。</span><span class="sxs-lookup"><span data-stu-id="c1479-329">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="c1479-330">優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1479-330">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="c1479-331">カスタムフィッシング対策ポリシーは、処理順に表示されます (最初のポリシーの **優先度** は 0 です)。</span><span class="sxs-lookup"><span data-stu-id="c1479-331">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="c1479-332">Office365 AntiPhish Default という名前の既定のフィッシング対策ポリシーには、カスタム優先度の値 **が [** 最低] であり、変更できない。</span><span class="sxs-lookup"><span data-stu-id="c1479-332">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="c1479-333">**注**: セキュリティ & コンプライアンス センターでは、フィッシング対策ポリシーを作成した後にのみ優先度を変更できます。</span><span class="sxs-lookup"><span data-stu-id="c1479-333">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="c1479-334">PowerShell では、フィッシング対策ルールを作成するときに既定の優先度を上書きできます (既存のルールの優先度に影響を与える可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="c1479-334">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="c1479-335">ポリシーの優先度を変更するには、ポリシーのプロパティで [優先度の引き上げ] または [優先度の下げ]をクリックします (セキュリティ & コンプライアンス センターで優先度番号を直接変更することはできません)。 </span><span class="sxs-lookup"><span data-stu-id="c1479-335">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="c1479-336">ポリシーの優先度を変更すると、複数のポリシーがある場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="c1479-336">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="c1479-337">[セキュリティ & コンプライアンス センター] で、[**脅威管理ポリシー** のフィッシング \>  \> **対策] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="c1479-337">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="c1479-338">変更するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c1479-338">Select the policy that you want to modify.</span></span> <span data-ttu-id="c1479-339">既に選択されている場合は、選択を解除してもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="c1479-339">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="c1479-340">[**ポリシーの編集 \<name\> ] フライ** アウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1479-340">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="c1479-341">優先度の値が **0** のカスタムフィッシング対策ポリシーには、[優先度の下がり]**ボタンしか** 使用できません。</span><span class="sxs-lookup"><span data-stu-id="c1479-341">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="c1479-342">優先度の値が最も低いカスタムフィッシング対策ポリシー (**たとえば、3)** には、[優先度の引き上げ]**ボタン** しか使用できません。</span><span class="sxs-lookup"><span data-stu-id="c1479-342">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="c1479-343">3 つ以上のカスタムフィッシング対策ポリシーがある場合、優先度の最も高い値と最も低い値の間のポリシーには、[優先度の引き上げ] ボタンと [優先度の下げ] ボタンの **両方が用意** されています。</span><span class="sxs-lookup"><span data-stu-id="c1479-343">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="c1479-344">[優先度 **の増加] または** **[優先度の下げ** ] をクリックして、 **優先度の値を変更** します。</span><span class="sxs-lookup"><span data-stu-id="c1479-344">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="c1479-345">完了したら、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1479-345">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="c1479-346">セキュリティ コンプライアンス センター&使用して、Microsoft Defender のフィッシング対策ポリシーを表示Office 365</span><span class="sxs-lookup"><span data-stu-id="c1479-346">Use the Security & Compliance Center to view anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="c1479-347">[セキュリティ & コンプライアンス センター] で、[脅威 **管理ポリシー** のフィッシング対策 \>  \> **] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="c1479-347">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="c1479-348">次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c1479-348">Do one of the following steps:</span></span>

   - <span data-ttu-id="c1479-349">表示するカスタムフィッシング対策ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c1479-349">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="c1479-350">既に選択されている場合は、選択を解除してもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="c1479-350">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="c1479-351">[既定 **のポリシー]** をクリックして、既定のフィッシング対策ポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="c1479-351">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="c1479-352">[**ポリシーの編集 \<name\> ] フライ** アウトが表示され、設定と値を表示できます。</span><span class="sxs-lookup"><span data-stu-id="c1479-352">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="c1479-353">セキュリティ コンプライアンス センター&使用して、Microsoft Defender のフィッシング対策ポリシーを削除Office 365</span><span class="sxs-lookup"><span data-stu-id="c1479-353">Use the Security & Compliance Center to remove anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="c1479-354">[セキュリティ & コンプライアンス センター] で、[**脅威管理ポリシー** のフィッシング \>  \> **対策] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="c1479-354">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="c1479-355">削除するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c1479-355">Select the policy that you want to remove.</span></span> <span data-ttu-id="c1479-356">既に選択されている場合は、選択を解除してもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="c1479-356">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="c1479-357">表示される **[ポリシー \<name\> の編集]** フライアウトで、[ポリシーの削除] をクリックし、表示される警告ダイアログで [**は** い] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1479-357">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="c1479-358">既定のポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="c1479-358">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="c1479-359">PowerShell Exchange Onlineを使用して、Microsoft Defender でフィッシング対策ポリシーを構成Office 365</span><span class="sxs-lookup"><span data-stu-id="c1479-359">Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="c1479-360">前述したように、スパム対策ポリシーはフィッシング対策ポリシーとフィッシング対策ルールで構成されています。</span><span class="sxs-lookup"><span data-stu-id="c1479-360">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="c1479-361">PowerShell Exchange Online、フィッシング対策ポリシーとフィッシング対策ルールの違いは明らかです。</span><span class="sxs-lookup"><span data-stu-id="c1479-361">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="c1479-362">-AntiPhishPolicy コマンドレットを使用してフィッシング対策ポリシーを管理し **\* 、-AntiPhishRule** コマンドレットを使用してフィッシング対策ルールを管理します。 **\***</span><span class="sxs-lookup"><span data-stu-id="c1479-362">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="c1479-363">PowerShell では、最初にフィッシング対策ポリシーを作成してから、そのルールが適用されるポリシーを識別するフィッシング対策ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="c1479-363">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="c1479-364">PowerShell では、フィッシング対策ポリシーとフィッシング対策ルールの設定を個別に変更します。</span><span class="sxs-lookup"><span data-stu-id="c1479-364">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="c1479-365">PowerShell からフィッシング対策ポリシーを削除すると、対応するフィッシング対策ルールは自動的には削除されません。その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="c1479-365">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="c1479-366">PowerShell を使用してフィッシング対策ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="c1479-366">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="c1479-367">PowerShell でフィッシング対策ポリシーを作成するには、次の 2 つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c1479-367">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="c1479-368">フィッシング対策ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c1479-368">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="c1479-369">ルールが適用されるフィッシング対策ポリシーを指定するフィッシング対策ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="c1479-369">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="c1479-370">**注**:</span><span class="sxs-lookup"><span data-stu-id="c1479-370">**Notes**:</span></span>

- <span data-ttu-id="c1479-371">新しいフィッシング対策ルールを作成し、関連付けされていない既存のフィッシング対策ポリシーを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="c1479-371">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="c1479-372">フィッシング対策ルールを複数のフィッシング対策ポリシーに関連付けできない。</span><span class="sxs-lookup"><span data-stu-id="c1479-372">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="c1479-373">ポリシーを作成するまで、セキュリティ & コンプライアンス センターで使用できない PowerShell の新しいフィッシング対策ポリシーで、次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="c1479-373">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="c1479-374">無効として新しいポリシーを作成 _します_ `$false` **(New-AntiPhishRule コマンドレットで有効** )。</span><span class="sxs-lookup"><span data-stu-id="c1479-374">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="c1479-375"> _\<Number\>_ **New-AntiPhishRule** コマンドレットの作成時にポリシーの優先度 (優先度) を設定します。</span><span class="sxs-lookup"><span data-stu-id="c1479-375">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="c1479-376">PowerShell で作成した新しいフィッシング対策ポリシーは、ポリシーをフィッシング対策ルールに割り当てるまで、セキュリティ & コンプライアンス センターには表示されません。</span><span class="sxs-lookup"><span data-stu-id="c1479-376">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="c1479-377">手順 1: PowerShell を使用してフィッシング対策ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="c1479-377">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="c1479-378">フィッシング対策ポリシーを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c1479-378">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="c1479-379">この例では、次の設定を使用して、Research Quarantine という名前のフィッシング対策ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c1479-379">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="c1479-380">ポリシーが有効になっています (Enabled パラメーターは使用していないので、既定値はです `$true` )。</span><span class="sxs-lookup"><span data-stu-id="c1479-380">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="c1479-381">説明は、調査部門のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="c1479-381">The description is: Research department policy.</span></span>
- <span data-ttu-id="c1479-382">すべての受け入れドメインに対する組織のドメイン保護と、ドメインの保護を対象 fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="c1479-382">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="c1479-383">偽装から保護するユーザーとして Mai Fujito (mfujito@fabrikam.com) を指定します。</span><span class="sxs-lookup"><span data-stu-id="c1479-383">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="c1479-384">メールボックスのインテリジェンスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="c1479-384">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="c1479-385">メールボックス インテリジェンス保護を有効にし、検疫アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="c1479-385">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="c1479-386">安全に関するヒントを有効にする。</span><span class="sxs-lookup"><span data-stu-id="c1479-386">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="c1479-387">構文とパラメーターの詳細については [、「New-AntiPhishPolicy」を参照してください](/powershell/module/exchange/New-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="c1479-387">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="c1479-388">手順 2: PowerShell を使用してフィッシング対策ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="c1479-388">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="c1479-389">フィッシング対策ルールを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c1479-389">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="c1479-390">この例では、次の条件を使用して、Research Department という名前のフィッシング対策ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="c1479-390">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="c1479-391">ルールは、Research Quarantine という名前のフィッシング対策ポリシーに関連付けられている。</span><span class="sxs-lookup"><span data-stu-id="c1479-391">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="c1479-392">ルールは Research Department という名前のグループのメンバーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="c1479-392">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="c1479-393">Priority パラメーターを使用していないので _、既定_ の優先度が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c1479-393">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="c1479-394">構文とパラメーターの詳細については [、「New-AntiPhishRule」を参照してください](/powershell/module/exchange/New-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="c1479-394">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="c1479-395">PowerShell を使用してフィッシング対策ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="c1479-395">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="c1479-396">既存のフィッシング対策ポリシーを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c1479-396">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="c1479-397">次の使用例は、指定したプロパティと共に、すべてのフィッシング対策ポリシーの概要リストを返します。</span><span class="sxs-lookup"><span data-stu-id="c1479-397">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="c1479-398">この例では、Executives という名前のフィッシング対策ポリシーのすべてのプロパティ値を返します。</span><span class="sxs-lookup"><span data-stu-id="c1479-398">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="c1479-399">構文とパラメーターの詳細については [、「Get-AntiPhishPolicy」を参照してください](/powershell/module/exchange/Get-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="c1479-399">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="c1479-400">PowerShell を使用してフィッシング対策ルールを表示する</span><span class="sxs-lookup"><span data-stu-id="c1479-400">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="c1479-401">既存のフィッシング対策ルールを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c1479-401">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="c1479-402">この例では、指定したプロパティと共に、すべてのフィッシング対策ルールの概要リストを返します。</span><span class="sxs-lookup"><span data-stu-id="c1479-402">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="c1479-403">ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c1479-403">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="c1479-404">この例では、Contoso Executives という名前のフィッシング対策ルールのすべてのプロパティ値を返します。</span><span class="sxs-lookup"><span data-stu-id="c1479-404">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="c1479-405">構文とパラメーターの詳細については [、「Get-AntiPhishRule」を参照してください](/powershell/module/exchange/Get-AntiPhishrule)。</span><span class="sxs-lookup"><span data-stu-id="c1479-405">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="c1479-406">PowerShell を使用してフィッシング対策ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="c1479-406">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="c1479-407">次の項目以外にも、「手順 [1: PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) を使用してフィッシング対策ポリシーを作成する」セクションで説明したように、PowerShell でフィッシング対策ポリシーを変更する場合と同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c1479-407">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this article.</span></span>

- <span data-ttu-id="c1479-408">指定したポリシーを既定のポリシーに変換する _MakeDefault_ スイッチ (すべてのユーザーに適用され、常に優先度が最も低く、削除できません) は、PowerShell でフィッシング対策ポリシーを変更する場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c1479-408">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="c1479-409">フィッシング対策ポリシーの名前を変更することはできません **(Set-AntiPhishPolicy** コマンドレットには _Name_ パラメーターはありません)。</span><span class="sxs-lookup"><span data-stu-id="c1479-409">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="c1479-410">セキュリティ & コンプライアンス センターでフィッシング対策ポリシーの名前を変更すると、フィッシング対策ルールの名前が変更 _されます_。</span><span class="sxs-lookup"><span data-stu-id="c1479-410">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="c1479-411">フィッシング対策ポリシーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c1479-411">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="c1479-412">構文とパラメーターの詳細については [、「Set-AntiPhishPolicy」を参照してください](/powershell/module/exchange/Set-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="c1479-412">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="c1479-413">PowerShell を使用してフィッシング対策ルールを変更する</span><span class="sxs-lookup"><span data-stu-id="c1479-413">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="c1479-414">PowerShell でフィッシング対策ルールを変更するときに使用できない唯一の設定は、無効なルールを作成できる _Enabled_ パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="c1479-414">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="c1479-415">既存のフィッシング対策ルールを有効または無効にするには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1479-415">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="c1479-416">それ以外の場合は、PowerShell でフィッシング対策ルールを変更するときに追加の設定を使用できません。</span><span class="sxs-lookup"><span data-stu-id="c1479-416">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="c1479-417">この記事の「手順 [2: PowerShell](#step-2-use-powershell-to-create-an-anti-phish-rule) を使用してフィッシング対策ルールを作成する」セクションで説明したように、ルールを作成するときにも同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c1479-417">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="c1479-418">フィッシング対策ルールを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c1479-418">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="c1479-419">構文とパラメーターの詳細については [、「Set-AntiPhishRule」を参照してください](/powershell/module/exchange/set-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="c1479-419">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="c1479-420">PowerShell を使用してフィッシング対策ルールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="c1479-420">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="c1479-421">PowerShell でフィッシング対策ルールを有効または無効にすると、フィッシング対策ポリシー (フィッシング対策ルールと割り当てられたフィッシング対策ポリシー) 全体が有効または無効となります。</span><span class="sxs-lookup"><span data-stu-id="c1479-421">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="c1479-422">既定のフィッシング対策ポリシーを有効または無効にできない (すべての受信者に常に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="c1479-422">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="c1479-423">PowerShell でフィッシング対策ルールを有効または無効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c1479-423">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="c1479-424">この例では、Marketing Department という名前のフィッシング対策ルールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="c1479-424">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="c1479-425">この例では、同じルールを有効化します。</span><span class="sxs-lookup"><span data-stu-id="c1479-425">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="c1479-426">構文とパラメーターの詳細については [、「Enable-AntiPhishRule」](/powershell/module/exchange/enable-antiphishrule) および [「Disable-AntiPhishRule」を参照してください](/powershell/module/exchange/disable-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="c1479-426">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="c1479-427">PowerShell を使用してフィッシング対策ルールの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="c1479-427">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="c1479-428">ルールに設定できる優先度の最高値値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="c1479-428">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="c1479-429">設定できる最低値はルールの数に依存します。</span><span class="sxs-lookup"><span data-stu-id="c1479-429">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="c1479-430">たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。</span><span class="sxs-lookup"><span data-stu-id="c1479-430">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="c1479-431">既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。</span><span class="sxs-lookup"><span data-stu-id="c1479-431">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="c1479-432">たとえば、カスタム ルールが 5 つあって (優先度 0 から 4)、1 つのルールの優先度を 2 に変更した場合には、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。</span><span class="sxs-lookup"><span data-stu-id="c1479-432">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="c1479-433">PowerShell でフィッシング対策ルールの優先度を設定するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c1479-433">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="c1479-p148">この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。</span><span class="sxs-lookup"><span data-stu-id="c1479-p148">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="c1479-436">**注**:</span><span class="sxs-lookup"><span data-stu-id="c1479-436">**Notes**:</span></span>

- <span data-ttu-id="c1479-437">新しいルールを作成するときに優先度を設定するには、代わりに **New-AntiPhishRule** コマンドレットの Priority パラメーターを使用します。 </span><span class="sxs-lookup"><span data-stu-id="c1479-437">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="c1479-438">既定のフィッシング対策ポリシーには、対応するフィッシング対策ルールが設定されていないので、常に変更できない優先度の値が **[最低**] です。</span><span class="sxs-lookup"><span data-stu-id="c1479-438">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="c1479-439">PowerShell を使用してフィッシング対策ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="c1479-439">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="c1479-440">PowerShell を使用してフィッシング対策ポリシーを削除すると、対応するフィッシング対策ルールは削除されません。</span><span class="sxs-lookup"><span data-stu-id="c1479-440">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="c1479-441">PowerShell でフィッシング対策ポリシーを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c1479-441">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="c1479-442">この例では、Marketing Department という名前のフィッシング対策ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="c1479-442">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="c1479-443">構文とパラメーターの詳細については [、「Remove-AntiPhishPolicy」を参照してください](/powershell/module/exchange/Remove-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="c1479-443">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="c1479-444">PowerShell を使用してフィッシング対策ルールを削除する</span><span class="sxs-lookup"><span data-stu-id="c1479-444">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="c1479-445">PowerShell を使用してフィッシング対策ルールを削除すると、対応するフィッシング対策ポリシーは削除されません。</span><span class="sxs-lookup"><span data-stu-id="c1479-445">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="c1479-446">PowerShell でフィッシング対策ルールを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c1479-446">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="c1479-447">この例では、Marketing Department という名前のフィッシング対策ルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="c1479-447">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="c1479-448">構文とパラメーターの詳細については [、「Remove-AntiPhishRule」を参照してください](/powershell/module/exchange/Remove-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="c1479-448">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="c1479-449">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="c1479-449">How do you know these procedures worked?</span></span>

<span data-ttu-id="c1479-450">Microsoft Defender でフィッシング対策ポリシーが正常に構成されたことを確認するには、次Office 365手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c1479-450">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="c1479-451">[セキュリティ & コンプライアンス センター] で、[**脅威管理ポリシー** のフィッシング \>  \> **対策] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="c1479-451">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="c1479-452">ポリシー、その状態の値、および **優先度** の値の一覧を **確認** します。</span><span class="sxs-lookup"><span data-stu-id="c1479-452">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="c1479-453">詳細を表示するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c1479-453">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="c1479-454">一覧からポリシーを選択し、詳細をフライアウトで表示します。</span><span class="sxs-lookup"><span data-stu-id="c1479-454">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="c1479-455">[既定 **のポリシー] を** クリックし、詳細をフライアウトで表示します。</span><span class="sxs-lookup"><span data-stu-id="c1479-455">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="c1479-456">PowerShell Exchange Online、ポリシーまたはルールの名前に置き換え、次のコマンドを \<Name\> 実行して設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="c1479-456">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```