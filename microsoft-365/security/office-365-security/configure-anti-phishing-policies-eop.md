---
title: EOP でのスパム対策ポリシーの構成
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
description: 管理者は、Exchange Online Protection (EOP) 組織で使用できるフィッシング対策ポリシーを作成、変更、および削除する方法について説明します(Exchange Online メールボックスを使用する場合と使用しない場合)。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f074596f0391e98735b07d17390cd058fd6fcafe
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793018"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="61b1c-103">EOP でのスパム対策ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="61b1c-103">Configure anti-phishing policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="61b1c-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="61b1c-104">**Applies to**</span></span>
- [<span data-ttu-id="61b1c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="61b1c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="61b1c-106">Exchange Online Microsoft 365 またはスタンドアロン Exchange Online Protection (EOP) 組織に Exchange Online メールボックスがない Microsoft 365 組織では、既定で有効になっているスプーフィング対策機能の数が制限されている既定のフィッシング対策ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="61b1c-106">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="61b1c-107">詳細については、「[フィッシング詐欺対策ポリシーでのなりすまし設定](set-up-anti-phishing-policies.md#spoof-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61b1c-107">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="61b1c-108">管理者は、既定のフィッシング対策ポリシーを表示、編集、および構成できます (ただし、削除はされません)。</span><span class="sxs-lookup"><span data-stu-id="61b1c-108">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="61b1c-109">さらに細分化するために、組織内の特定のユーザー、グループ、またはドメインに適用されるカスタムフィッシング対策ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-109">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="61b1c-110">カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (実行順序) を変更できます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-110">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="61b1c-111">メールボックスがExchange Online組織は、セキュリティ センターまたは PowerShell でフィッシングMicrosoft 365ポリシーをExchange Onlineできます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-111">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Microsoft 365 security center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="61b1c-112">スタンドアロン EOP 組織は、セキュリティ センターのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-112">Standalone EOP organizations can only use the security center.</span></span>

<span data-ttu-id="61b1c-113">microsoft Defender for Office 365 で使用できる、より高度なフィッシング対策ポリシーを作成および変更する方法については[、「Configure anti-フィッシング](configure-atp-anti-phishing-policies.md)ポリシー in Microsoft Defender for Office 365」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61b1c-113">For information about creating and modifying the more advanced anti-phishing policies that are available in Microsoft Defender for Office 365, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

<span data-ttu-id="61b1c-114">フィッシング対策ポリシーの基本的な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="61b1c-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="61b1c-115">**フィッシング対策ポリシー**: 有効または無効にするフィッシング保護と、オプションを適用するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="61b1c-116">**フィッシング対策ルール**: フィッシング対策ポリシーの優先度と受信者フィルター (ポリシーが適用されるユーザー) を指定します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="61b1c-117">セキュリティ センターでフィッシング対策ポリシーを管理する場合、これら 2 つの要素の違いは明らかではありません。</span><span class="sxs-lookup"><span data-stu-id="61b1c-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the security center:</span></span>

- <span data-ttu-id="61b1c-118">フィッシング対策ポリシーを作成する場合は、両方に同じ名前を使用して、実際にフィッシング対策ルールと関連付けられたフィッシング対策ポリシーを同時に作成します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-118">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="61b1c-119">フィッシング対策ポリシーを変更すると、名前、優先度、有効または無効、および受信者フィルターに関連する設定によって、フィッシング対策ルールが変更されます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-119">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="61b1c-120">その他の設定はすべて、関連付けられたフィッシング対策ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="61b1c-121">フィッシング対策ポリシーを削除すると、フィッシング対策ルールと関連付けられたフィッシング対策ポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-121">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="61b1c-122">PowerShell Exchange Onlineでは、ポリシーとルールを個別に管理します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="61b1c-123">詳細については、この記事の[後半Exchange Online「PowerShell](#use-exchange-online-powershell-to-configure-anti-phishing-policies)を使用してフィッシング対策ポリシーを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61b1c-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="61b1c-124">すべての組織には、次のプロパティを持つ Office365 AntiPhish Default という名前の組み込みのフィッシング対策ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="61b1c-124">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="61b1c-125">ポリシーは、ポリシーに関連付けられたフィッシング対策ルール (受信者フィルター) がない場合でも、組織内のすべての受信者に適用されます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="61b1c-126">ポリシーにはカスタムの優先順位の値 **Lowest** が設定されており、変更することはできません (このポリシーは常に最後に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="61b1c-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="61b1c-127">作成するどのカスタム ポリシーも、より高い優先順位を持ちます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="61b1c-128">ポリシーは既定のポリシー (**IsDefault** のプロパティが `True` の値になっている) であり、既定のポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="61b1c-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="61b1c-129">フィッシング対策保護の効果を高めるには、特定のユーザーまたはユーザー グループに適用されるより厳しい設定で、カスタムのフィッシング対策ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-129">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="61b1c-130">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="61b1c-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="61b1c-131"><https://security.microsoft.com/> でセキュリティ センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-131">You open the security center at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="61b1c-132">フィッシング対策ページに直接 **移動するには** 、 を使用します <https://security.microsoft.com/antiphishing> 。</span><span class="sxs-lookup"><span data-stu-id="61b1c-132">To go directly to the **Anti-phishing** page, use <https://security.microsoft.com/antiphishing>.</span></span>

- <span data-ttu-id="61b1c-133">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61b1c-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="61b1c-134">スタンドアロン EOP PowerShell ではフィッシング対策ポリシーを管理できない。</span><span class="sxs-lookup"><span data-stu-id="61b1c-134">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="61b1c-135">この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="61b1c-135">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="61b1c-136">フィッシング対策ポリシーを追加、変更、削除するには、組織の管理役割グループまたはセキュリティ管理者役割グループのメンバー **である** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="61b1c-136">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="61b1c-137">フィッシング対策ポリシーへの読み取り専用アクセスには、グローバル リーダーまたはセキュリティ リーダーの役割グループの **メンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="61b1c-137">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="61b1c-138">詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61b1c-138">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="61b1c-139">**注**:</span><span class="sxs-lookup"><span data-stu-id="61b1c-139">**Notes**:</span></span>

  - <span data-ttu-id="61b1c-140">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-140">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="61b1c-141">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61b1c-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="61b1c-142">[**組織の管理の表示のみ**][](/Exchange/permissions-exo/permissions-exo#role-groups)役割グループは、Exchange Online機能への読み取り専用アクセスも提供します <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="61b1c-142">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>

- <span data-ttu-id="61b1c-143">フィッシング対策ポリシーの推奨設定については、「EOP フィッシング対策ポリシー設定」 [を参照してください](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="61b1c-143">For our recommended settings for anti-phishing policies, see [EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="61b1c-144">更新されたポリシーを適用するには、最大 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="61b1c-144">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="61b1c-145">フィルター 処理パイプラインでフィッシング対策ポリシーが適用される場所については、「メール保護の順序と優先順位」 [を参照してください](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="61b1c-145">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security-center-to-create-anti-phishing-policies"></a><span data-ttu-id="61b1c-146">セキュリティ センターを使用してフィッシング対策ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="61b1c-146">Use the security center to create anti-phishing policies</span></span>

<span data-ttu-id="61b1c-147">セキュリティ センターでカスタムフィッシング対策ポリシーを作成すると、両方に同じ名前を使用して、フィッシング対策ルールと関連付けられたフィッシング対策ポリシーが同時に作成されます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-147">Creating a custom anti-phishing policy in the security center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="61b1c-148">セキュリティ センターで、[メールの送信] **&[&** ポリシー] セクションの [フィッシング対策] \>  \>  \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="61b1c-148">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="61b1c-149">[フィッシング対策 **] ページで、[** 作成] アイコン [作成] ![ を ](../../media/m365-cc-sc-create-icon.png) **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="61b1c-149">On the **Anti-phishing** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="61b1c-150">ポリシー ウィザードが開きます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-150">The policy wizard opens.</span></span> <span data-ttu-id="61b1c-151">[ポリシー名 **] ページで** 、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-151">On the **Policy name** page, configure these settings:</span></span>
   - <span data-ttu-id="61b1c-152">**[名前]**: わかりやすい一意のポリシー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="61b1c-153">**[説明]**: ポリシーについての説明を入力します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="61b1c-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="61b1c-154">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="61b1c-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="61b1c-155">表示される **ユーザー、グループ、およびドメイン** ページで、ポリシーを適用する内部の受信者を特定します (受信者条件)。</span><span class="sxs-lookup"><span data-stu-id="61b1c-155">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="61b1c-156">**ユーザー**: 組織内で指定された 1 つ以上のメールボックス、メール ユーザー、またはメール連絡先。</span><span class="sxs-lookup"><span data-stu-id="61b1c-156">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="61b1c-157">**グループ**: 組織内で指定された配布グループ、メール対応セキュリティ グループ、または Microsoft 365 グループ。</span><span class="sxs-lookup"><span data-stu-id="61b1c-157">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="61b1c-158">**ドメイン**: 組織内で指定された [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)のすべての受信者。</span><span class="sxs-lookup"><span data-stu-id="61b1c-158">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="61b1c-159">適正なボックスをクリックし、値の入力を開始し、結果で希望する値を選択します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-159">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="61b1c-160">必要な回数だけこの処理を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-160">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="61b1c-161">既存の値を削除するには、削除をクリックします</span><span class="sxs-lookup"><span data-stu-id="61b1c-161">To remove an existing value, click remove</span></span> ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="61b1c-163">値の隣。</span><span class="sxs-lookup"><span data-stu-id="61b1c-163">next to the value.</span></span>

   <span data-ttu-id="61b1c-164">ユーザーやグループには、ほとんどの識別子 (名前、表示名、エイリアス、メールアドレス、アカウント名など) を使用できますが、対応する表示名が結果に表示されます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-164">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="61b1c-165">ユーザーの場合、アスタリスク (\*) を単独で入力すると、使用可能なすべての値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-165">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="61b1c-166">同じ条件に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-166">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="61b1c-167">別の条件では、AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) を使用します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-167">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="61b1c-168">**これらのユーザー、グループ、およびドメインを除外する**: ポリシーが適用される内部の受信者に関する例外 (受信者の例外) を追加するには、このオプションを選択して例外を構成します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-168">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="61b1c-169">設定と動作は、条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="61b1c-169">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="61b1c-170">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="61b1c-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="61b1c-171">表示される **[フィッシング&の** しきい値] ページで、[スプーフィング インテリジェンスを有効にする] チェック ボックスを使用してスプーフィング インテリジェンスのオンとオフを切り替えます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-171">On the **Phishing threshold & protection** page that appears, use the **Enable spoof intelligence** check box to turn spoof intelligence on or off.</span></span> <span data-ttu-id="61b1c-172">既定値はオン (選択) であり、オンのままにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="61b1c-172">The default value is on (selected), and we recommend that you leave it on.</span></span> <span data-ttu-id="61b1c-173">次のページで、ブロックされたスプーフィングされたメッセージに対して実行するアクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-173">You configure the action to take on blocked spoofed messages on the next page.</span></span>

   <span data-ttu-id="61b1c-174">スプーフィング インテリジェンスをオフにするには、チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="61b1c-174">To turn off spoof intelligence, clear the check box.</span></span>

   > [!NOTE]
   > <span data-ttu-id="61b1c-175">MX レコードがスプーフィング対策保護をオフにする必要Microsoft 365。代わりに、コネクタの拡張フィルターを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-175">You don't need to turn off anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="61b1c-176">手順については、「拡張フィルタリング[for Connectors in Exchange Online」 を参照してください](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="61b1c-176">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   <span data-ttu-id="61b1c-177">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="61b1c-177">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="61b1c-178">**[アクション]** ページが表示されたら、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-178">On the **Actions** page that appears, configure the following settings:</span></span>
   - <span data-ttu-id="61b1c-179">**メッセージがスプーフィングとして検出された** 場合: この設定は、前のページで [スプーフィング インテリジェンスを有効にする] を選択した場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-179">**If message is detected as spoof**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="61b1c-180">ブロックされたスプーフィングされた送信者からのメッセージについては、ドロップダウン リストで次のいずれかのアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-180">Select one of the following actions in the drop down list for messages from blocked spoofed senders:</span></span>
     - <span data-ttu-id="61b1c-181">**受信者の迷惑メール フォルダーにメッセージを移動する**</span><span class="sxs-lookup"><span data-stu-id="61b1c-181">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="61b1c-182">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="61b1c-182">**Quarantine the message**</span></span>

   - <span data-ttu-id="61b1c-183">**安全上&ヒント**: この設定は、前のページで [スプーフィング インテリジェンスを有効にする] を選択した場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-183">**Safety tips & indicators**: This setting is available only if you selected **Enable spoof intelligence** on the previous page:</span></span>
     - <span data-ttu-id="61b1c-184">スプーフィングの認証されていない送信者に対して **(?)** を表示する : メッセージが SPF または DKIM チェックに合格しない場合に、メッセージが DMARCまたは複合認証に合格しない場合、Outlook [](email-validation-and-authentication.md#composite-authentication)の [差出人] ボックスに送信者の写真に疑問符を追加します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-184">**Show (?) for unauthenticated senders for spoof**: Adds a question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span>
     - <span data-ttu-id="61b1c-185">**"via"** タグを表示する: DKIM 署名または **MAIL FROM** アドレスのドメインと異なる場合は、from アドレスに via タグ (chris@contoso.com 経由で fabrikam.com) を追加します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-185">**Show "via" tag**: Adds a via tag (chris@contoso.com via fabrikam.com) to the From address if it's different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span>

       > [!NOTE]
       > <span data-ttu-id="61b1c-186">現在、すべての **組織で ["via" タグ** を表示する] 設定は使用できません。</span><span class="sxs-lookup"><span data-stu-id="61b1c-186">Currently, the **Show "via" tag** setting is not available in all organizations.</span></span> <span data-ttu-id="61b1c-187">**"via"** タグを表示する設定が設定されていない場合、組織内のスプーフィング設定の認証されていない送信者に対して、疑問符と via タグの両方が Show **(?)** によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-187">If you don't have the **Show "via" tag** setting, the the question mark **and** the via tag are both controlled by the **Show (?) for unauthenticated senders for spoof** setting in your organization.</span></span>

     <span data-ttu-id="61b1c-188">設定を有効にする場合は、チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="61b1c-188">To turn on a setting, select the check box.</span></span> <span data-ttu-id="61b1c-189">オフにする場合は、チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="61b1c-189">To turn it off, clear the check box.</span></span>

   <span data-ttu-id="61b1c-190">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="61b1c-190">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="61b1c-191">表示された **[レビュー]** ページで、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-191">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="61b1c-192">各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-192">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="61b1c-193">または、[戻る] **をクリック** するか、ウィザードで特定のページを選択します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-193">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="61b1c-194">完了したら、[送信] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="61b1c-194">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="61b1c-195">表示された [確認]ページで、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="61b1c-195">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-security-center-to-view-anti-phishing-policies"></a><span data-ttu-id="61b1c-196">セキュリティ センターを使用してフィッシング対策ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="61b1c-196">Use the security center to view anti-phishing policies</span></span>

1. <span data-ttu-id="61b1c-197">セキュリティ センターで、[メールの送信] **&[&** ポリシー] セクションの [フィッシング対策] \>  \>  \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="61b1c-197">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="61b1c-198">[フィッシング **対策] ページ** では、フィッシング対策ポリシーの一覧に次のプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-198">On the **Anti-phishing** page, the following properties are displayed in the list of anti-phishing policies:</span></span>

   - <span data-ttu-id="61b1c-199">**名前**</span><span class="sxs-lookup"><span data-stu-id="61b1c-199">**Name**</span></span>
   - <span data-ttu-id="61b1c-200">**状態**</span><span class="sxs-lookup"><span data-stu-id="61b1c-200">**Status**</span></span>
   - <span data-ttu-id="61b1c-201">**優先度**</span><span class="sxs-lookup"><span data-stu-id="61b1c-201">**Priority**</span></span>
   - <span data-ttu-id="61b1c-202">**最終更新日時**</span><span class="sxs-lookup"><span data-stu-id="61b1c-202">**Last modified**</span></span>

3. <span data-ttu-id="61b1c-203">名前をクリックしてポリシーを選択すると、ポリシー設定がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-203">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-security-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="61b1c-204">セキュリティ センターを使用してフィッシング対策ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="61b1c-204">Use the security center to modify anti-phishing policies</span></span>

1. <span data-ttu-id="61b1c-205">セキュリティ センターで、[メールの送信] **&[&** ポリシー] セクションの [フィッシング対策] \>  \>  \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="61b1c-205">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="61b1c-206">[フィッシング **対策] ページで** 、名前をクリックして一覧からポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-206">On the **Anti-phishing** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="61b1c-207">表示されるポリシーの詳細ポップアップで、各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-207">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="61b1c-208">設定の詳細については、この記事の「[](#use-the-security-center-to-create-anti-phishing-policies)セキュリティ センターを使用してフィッシング対策ポリシーを作成する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="61b1c-208">For more information about the settings, see the [Use the security center to create anti-phishing policies](#use-the-security-center-to-create-anti-phishing-policies) section earlier in this article.</span></span>  

   <span data-ttu-id="61b1c-209">既定のフィッシング対策ポリシーでは、[ユーザー、グループ、ドメイン] セクションは使用できません (ポリシーはすべてのユーザーに適用されます)、ポリシーの名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="61b1c-209">For the default anti-phishing policy, the **Users, groups, and domains** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="61b1c-210">ポリシーを有効または無効にするか、ポリシーの優先順位を設定するには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="61b1c-210">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="61b1c-211">カスタムフィッシング対策ポリシーを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="61b1c-211">Enable or disable custom anti-phishing policies</span></span>

<span data-ttu-id="61b1c-212">既定のフィッシング対策ポリシーを無効にできない。</span><span class="sxs-lookup"><span data-stu-id="61b1c-212">You can't disable the default anti-phishing policy.</span></span>

1. <span data-ttu-id="61b1c-213">セキュリティ センターで、[メールの送信] **&[&** ポリシー] セクションの [フィッシング対策] \>  \>  \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="61b1c-213">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="61b1c-214">[フィッシング **対策] ページで** 、名前をクリックしてリストからカスタム ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-214">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="61b1c-215">表示されるポリシーの詳細ポップアップの上部には、以下のいずれかの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-215">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="61b1c-216">**ポリシー オフ**: ポリシーをオンにするには、![[アイコンをオンにする]](../../media/m365-cc-sc-turn-on-off-icon.png)、**[オンにする]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="61b1c-216">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="61b1c-217">**ポリシー オン**: ポリシーをオフにするには、![[アイコンをオフにする]](../../media/m365-cc-sc-turn-on-off-icon.png)、**[オフにする]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="61b1c-217">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="61b1c-218">確認ダイアログ ボックスが表示されたら、**[オンにする]** または **[オフにする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="61b1c-218">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="61b1c-219">ポリシーの詳細ポップアップで **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="61b1c-219">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="61b1c-220">ポリシーのメイン ページに戻ると、ポリシーの **[状態]** の値が **[オン]** または **[オフ]** になります。</span><span class="sxs-lookup"><span data-stu-id="61b1c-220">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="61b1c-221">カスタムフィッシング対策ポリシーの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="61b1c-221">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="61b1c-222">既定では、フィッシング対策ポリシーには、作成された順序に基づく優先度が与えられる (新しいポリシーは、以前のポリシーよりも優先度が低くなります)。</span><span class="sxs-lookup"><span data-stu-id="61b1c-222">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="61b1c-223">優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。</span><span class="sxs-lookup"><span data-stu-id="61b1c-223">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="61b1c-224">2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-224">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="61b1c-225">ポリシーの優先度を変更するには、ポリシーのプロパティで **[優先度を上げる]** または **[優先度を下げる]** をクリックします (セキュリティ センターの **[優先度]** の数値を直接変更することはできません)。</span><span class="sxs-lookup"><span data-stu-id="61b1c-225">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the security center).</span></span> <span data-ttu-id="61b1c-226">ポリシーの優先度を変更することは、複数のポリシーを所有している場合にのみ意味があります。</span><span class="sxs-lookup"><span data-stu-id="61b1c-226">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="61b1c-227">**注意**:</span><span class="sxs-lookup"><span data-stu-id="61b1c-227">**Notes**:</span></span>

- <span data-ttu-id="61b1c-228">セキュリティ センターでは、フィッシング対策ポリシーを作成した後にのみ、優先度を変更できます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-228">In the security center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="61b1c-229">PowerShell では、フィッシング対策ルールを作成するときに既定の優先度を上書きできます (既存のルールの優先度に影響を与える可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="61b1c-229">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="61b1c-230">フィッシング対策ポリシーは、表示順に処理されます (最初のポリシーの **優先度** は 0 です)。</span><span class="sxs-lookup"><span data-stu-id="61b1c-230">Anti-phishing policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="61b1c-231">既定のフィッシング対策ポリシーの優先度の値は **[最低**] で、変更は行えなくないます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-231">The default anti-phishing policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="61b1c-232">セキュリティ センターで、[メールの送信] **&[&** ポリシー] セクションの [フィッシング対策] \>  \>  \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="61b1c-232">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="61b1c-233">[フィッシング **対策] ページで** 、名前をクリックしてリストからカスタム ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-233">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="61b1c-234">表示されるポリシーの詳細ポップアップの上部には、現在の優先度の値とカスタム ポリシーの数に基づいて、**[優先度を上げる]** または **[優先度を下げる]** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-234">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="61b1c-235">優先度の値が **0** のフィッシング対策ポリシーには、[優先度の下がり]**オプション** しか使用できません。</span><span class="sxs-lookup"><span data-stu-id="61b1c-235">The anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="61b1c-236">優先度の値が最も低いフィッシング対策ポリシー (**たとえば、3)** には、[優先度の引き上げ]**オプション** しか使用できません。</span><span class="sxs-lookup"><span data-stu-id="61b1c-236">The anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="61b1c-237">3 つ以上のフィッシング対策ポリシーがある場合、優先度の高い値と最も低い優先度の値の間のポリシーには、[優先度の引き上げ] オプションと [優先度の下 **げ]** の両方 **のオプションがあります** 。</span><span class="sxs-lookup"><span data-stu-id="61b1c-237">If you have three or more anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="61b1c-238">![[優先度を上げる] アイコン](../../media/m365-cc-sc-increase-icon.png)、**[優先度を上げる]** の順にクリックするか、または ![[優先度を下げる] アイコン](../../media/m365-cc-sc-decrease-icon.png)、**[優先度を下げる]** の順にクリックして、**優先度** 値を変更します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-238">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="61b1c-239">完了したら、ポリシーの詳細ポップアップで **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="61b1c-239">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-security-center-to-remove-custom-anti-phishing-policies"></a><span data-ttu-id="61b1c-240">セキュリティ センターを使用してカスタムフィッシング対策ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="61b1c-240">Use the security center to remove custom anti-phishing policies</span></span>

<span data-ttu-id="61b1c-241">セキュリティ センターを使用してカスタムフィッシング対策ポリシーを削除すると、フィッシング対策ルールと対応するフィッシング対策ポリシーの両方が削除されます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-241">When you use the security center to remove a custom anti-phishing policy, the anti-phish rule and the corresponding anti-phish policy are both deleted.</span></span> <span data-ttu-id="61b1c-242">既定のフィッシング対策ポリシーを削除できない。</span><span class="sxs-lookup"><span data-stu-id="61b1c-242">You can't remove the default anti-phishing policy.</span></span>

1. <span data-ttu-id="61b1c-243">セキュリティ センターで、[メールの送信] **&[&** ポリシー] セクションの [フィッシング対策] \>  \>  \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="61b1c-243">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="61b1c-244">ポリシーの名前をクリックして、リストからカスタム ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-244">Select a custom policy from the list by clicking on the name of the policy.</span></span> <span data-ttu-id="61b1c-245">表示されるポリシーの詳細ポップアウトの上部で、![[その他の操作] アイコン](../../media/m365-cc-sc-more-actions-icon.png)、**[その他の操作]** \>、![[ポリシーの削除] アイコン](../../media/m365-cc-sc-delete-icon.png)、**[ポリシーの削除]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="61b1c-245">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="61b1c-246">確認ダイアログ ボックスが表示されたら、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="61b1c-246">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="61b1c-247">PowerShell Exchange Onlineを使用してフィッシング対策ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="61b1c-247">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="61b1c-248">前述したように、フィッシング対策ポリシーは、フィッシング対策ポリシーとフィッシング対策ルールで構成されています。</span><span class="sxs-lookup"><span data-stu-id="61b1c-248">As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="61b1c-249">PowerShell Exchange Online、フィッシング対策ポリシーとフィッシング対策ルールの違いは明らかです。</span><span class="sxs-lookup"><span data-stu-id="61b1c-249">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="61b1c-250">-AntiPhishPolicy コマンドレットを使用してフィッシング対策ポリシーを管理し **\* 、-AntiPhishRule** コマンドレットを使用してフィッシング対策ルールを管理します。 **\***</span><span class="sxs-lookup"><span data-stu-id="61b1c-250">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="61b1c-251">PowerShell では、最初にフィッシング対策ポリシーを作成してから、そのルールが適用されるポリシーを識別するフィッシング対策ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-251">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="61b1c-252">PowerShell では、フィッシング対策ポリシーとフィッシング対策ルールの設定を個別に変更します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-252">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="61b1c-253">PowerShell からフィッシング対策ポリシーを削除すると、対応するフィッシング対策ルールは自動的には削除されません。その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="61b1c-253">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="61b1c-254">次の PowerShell 手順は、PowerShell を使用してスタンドアロンの EOP 組織ではExchange Online Protectionできません。</span><span class="sxs-lookup"><span data-stu-id="61b1c-254">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="61b1c-255">PowerShell を使用してフィッシング対策ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="61b1c-255">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="61b1c-256">PowerShell でフィッシング対策ポリシーを作成するには、次の 2 つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-256">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="61b1c-257">フィッシング対策ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-257">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="61b1c-258">ルールが適用されるフィッシング対策ポリシーを指定するフィッシング対策ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-258">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="61b1c-259">**注**:</span><span class="sxs-lookup"><span data-stu-id="61b1c-259">**Notes**:</span></span>

- <span data-ttu-id="61b1c-260">新しいフィッシング対策ルールを作成し、関連付けされていない既存のフィッシング対策ポリシーを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-260">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="61b1c-261">フィッシング対策ルールを複数のフィッシング対策ポリシーに関連付けできない。</span><span class="sxs-lookup"><span data-stu-id="61b1c-261">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="61b1c-262">ポリシーを作成するまで、セキュリティ センターで使用できない PowerShell の新しいフィッシング対策ポリシーで次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-262">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the security center until after you create the policy:</span></span>

  - <span data-ttu-id="61b1c-263">無効として新しいポリシーを作成 _します_ `$false` **(New-AntiPhishRule コマンドレットで有効** )。</span><span class="sxs-lookup"><span data-stu-id="61b1c-263">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="61b1c-264"> _\<Number\>_ **New-AntiPhishRule** コマンドレットの作成時にポリシーの優先度 (優先度) を設定します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-264">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="61b1c-265">PowerShell で作成した新しいフィッシング対策ポリシーは、ポリシーをフィッシング対策ルールに割り当てるまで、セキュリティ センターに表示されません。</span><span class="sxs-lookup"><span data-stu-id="61b1c-265">A new anti-phish policy that you create in PowerShell isn't visible in the security center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="61b1c-266">手順 1: PowerShell を使用してフィッシング対策ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="61b1c-266">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="61b1c-267">フィッシング対策ポリシーを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-267">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>] [-EnableViaTag <$true | $false>]
```

<span data-ttu-id="61b1c-268">この例では、次の設定を使用して、Research Quarantine という名前のフィッシング対策ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-268">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="61b1c-269">説明は、調査部門のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="61b1c-269">The description is: Research department policy.</span></span>
- <span data-ttu-id="61b1c-270">スプーフィングの既定のアクションを [検疫] に変更します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-270">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="61b1c-271">構文とパラメーターの詳細については [、「New-AntiPhishPolicy」を参照してください](/powershell/module/exchange/New-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="61b1c-271">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="61b1c-272">手順 2: PowerShell を使用してフィッシング対策ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="61b1c-272">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="61b1c-273">フィッシング対策ルールを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-273">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="61b1c-274">この例では、次の条件を使用して、Research Department という名前のフィッシング対策ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-274">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="61b1c-275">ルールは、Research Quarantine という名前のフィッシング対策ポリシーに関連付けられている。</span><span class="sxs-lookup"><span data-stu-id="61b1c-275">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="61b1c-276">ルールは Research Department という名前のグループのメンバーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-276">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="61b1c-277">Priority パラメーターを使用していないので _、既定_ の優先度が使用されます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-277">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="61b1c-278">構文とパラメーターの詳細については [、「New-AntiPhishRule」を参照してください](/powershell/module/exchange/New-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="61b1c-278">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="61b1c-279">PowerShell を使用してフィッシング対策ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="61b1c-279">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="61b1c-280">既存のフィッシング対策ポリシーを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-280">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="61b1c-281">次の使用例は、指定したプロパティと共に、すべてのフィッシング対策ポリシーの概要リストを返します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-281">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="61b1c-282">この例では、Executives という名前のフィッシング対策ポリシーのすべてのプロパティ値を返します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-282">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="61b1c-283">構文とパラメーターの詳細については [、「Get-AntiPhishPolicy」を参照してください](/powershell/module/exchange/Get-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="61b1c-283">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="61b1c-284">PowerShell を使用してフィッシング対策ルールを表示する</span><span class="sxs-lookup"><span data-stu-id="61b1c-284">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="61b1c-285">既存のフィッシング対策ルールを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-285">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="61b1c-286">この例では、指定したプロパティと共に、すべてのフィッシング対策ルールの概要リストを返します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-286">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="61b1c-287">ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-287">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="61b1c-288">この例では、Contoso Executives という名前のフィッシング対策ルールのすべてのプロパティ値を返します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-288">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="61b1c-289">構文とパラメーターの詳細については [、「Get-AntiPhishRule」を参照してください](/powershell/module/exchange/Get-AntiPhishrule)。</span><span class="sxs-lookup"><span data-stu-id="61b1c-289">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="61b1c-290">PowerShell を使用してフィッシング対策ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="61b1c-290">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="61b1c-291">次の項目以外にも、「手順 [1: PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) を使用してフィッシング対策ポリシーを作成する」で説明したように、PowerShell でフィッシング対策ポリシーを変更する場合と同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-291">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="61b1c-292">指定したポリシーを既定のポリシーに変換する _MakeDefault_ スイッチ (すべてのユーザーに適用され、常に優先度が最も低く、削除できません) は、PowerShell でフィッシング対策ポリシーを変更する場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-292">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>
- <span data-ttu-id="61b1c-293">フィッシング対策ポリシーの名前を変更することはできません **(Set-AntiPhishPolicy** コマンドレットには _Name_ パラメーターはありません)。</span><span class="sxs-lookup"><span data-stu-id="61b1c-293">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="61b1c-294">セキュリティ センターでフィッシング対策ポリシーの名前を変更する場合は、フィッシング対策ルールの名前を変更 _する_ のみです。</span><span class="sxs-lookup"><span data-stu-id="61b1c-294">When you rename an anti-phishing policy in the security center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="61b1c-295">フィッシング対策ポリシーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-295">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="61b1c-296">構文とパラメーターの詳細については [、「Set-AntiPhishPolicy」を参照してください](/powershell/module/exchange/Set-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="61b1c-296">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="61b1c-297">PowerShell を使用してフィッシング対策ルールを変更する</span><span class="sxs-lookup"><span data-stu-id="61b1c-297">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="61b1c-298">PowerShell でフィッシング対策ルールを変更するときに使用できない唯一の設定は、無効なルールを作成できる _Enabled_ パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="61b1c-298">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="61b1c-299">既存のフィッシング対策ルールを有効または無効にするには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="61b1c-299">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="61b1c-300">それ以外の場合は、「手順 [2: PowerShell](#step-2-use-powershell-to-create-an-anti-phish-rule) を使用してフィッシング対策ルールを作成する」セクションで説明したように、ルールを作成するときに同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-300">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="61b1c-301">フィッシング対策ルールを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-301">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="61b1c-302">構文とパラメーターの詳細については [、「Set-AntiPhishRule」を参照してください](/powershell/module/exchange/set-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="61b1c-302">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="61b1c-303">PowerShell を使用してフィッシング対策ルールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="61b1c-303">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="61b1c-304">PowerShell でフィッシング対策ルールを有効または無効にすると、フィッシング対策ポリシー (フィッシング対策ルールと割り当てられたフィッシング対策ポリシー) 全体が有効または無効となります。</span><span class="sxs-lookup"><span data-stu-id="61b1c-304">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="61b1c-305">既定のフィッシング対策ポリシーを有効または無効にできない (すべての受信者に常に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="61b1c-305">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="61b1c-306">PowerShell でフィッシング対策ルールを有効または無効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-306">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="61b1c-307">この例では、Marketing Department という名前のフィッシング対策ルールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="61b1c-307">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="61b1c-308">この例では、同じルールを有効化します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-308">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="61b1c-309">構文とパラメーターの詳細については [、「Enable-AntiPhishRule」](/powershell/module/exchange/enable-antiphishrule) および [「Disable-AntiPhishRule」を参照してください](/powershell/module/exchange/disable-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="61b1c-309">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="61b1c-310">PowerShell を使用してフィッシング対策ルールの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="61b1c-310">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="61b1c-p132">ルールに設定できる優先度の最高値値は 0 です。設定できる最低値はルールの数に依存します。たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。たとえば、カスタム ルールが五つある場合 (優先度 0 から 4) に、一つのルールの優先度を 2 に変更した場合、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。</span><span class="sxs-lookup"><span data-stu-id="61b1c-p132">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="61b1c-316">PowerShell でフィッシング対策ルールの優先度を設定するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-316">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="61b1c-p133">この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。</span><span class="sxs-lookup"><span data-stu-id="61b1c-p133">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="61b1c-319">**注**:</span><span class="sxs-lookup"><span data-stu-id="61b1c-319">**Notes**:</span></span>

- <span data-ttu-id="61b1c-320">新しいルールを作成するときに優先度を設定するには、代わりに **New-AntiPhishRule** コマンドレットの Priority パラメーターを使用します。 </span><span class="sxs-lookup"><span data-stu-id="61b1c-320">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>
- <span data-ttu-id="61b1c-321">既定のフィッシング対策ポリシーには、対応するフィッシング対策ルールが設定されていないので、常に変更できない優先度の値が **[最低**] です。</span><span class="sxs-lookup"><span data-stu-id="61b1c-321">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="61b1c-322">PowerShell を使用してフィッシング対策ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="61b1c-322">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="61b1c-323">PowerShell を使用してフィッシング対策ポリシーを削除すると、対応するフィッシング対策ルールは削除されません。</span><span class="sxs-lookup"><span data-stu-id="61b1c-323">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="61b1c-324">PowerShell でフィッシング対策ポリシーを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-324">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="61b1c-325">この例では、Marketing Department という名前のフィッシング対策ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-325">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="61b1c-326">構文とパラメーターの詳細については [、「Remove-AntiPhishPolicy」を参照してください](/powershell/module/exchange/Remove-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="61b1c-326">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="61b1c-327">PowerShell を使用してフィッシング対策ルールを削除する</span><span class="sxs-lookup"><span data-stu-id="61b1c-327">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="61b1c-328">PowerShell を使用してフィッシング対策ルールを削除すると、対応するフィッシング対策ポリシーは削除されません。</span><span class="sxs-lookup"><span data-stu-id="61b1c-328">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="61b1c-329">PowerShell でフィッシング対策ルールを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-329">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="61b1c-330">この例では、Marketing Department という名前のフィッシング対策ルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-330">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="61b1c-331">構文とパラメーターの詳細については [、「Remove-AntiPhishRule」を参照してください](/powershell/module/exchange/Remove-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="61b1c-331">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="61b1c-332">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="61b1c-332">How do you know these procedures worked?</span></span>

<span data-ttu-id="61b1c-333">EOP でフィッシング対策ポリシーが正常に構成されたことを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-333">To verify that you've successfully configured anti-phishing policies in EOP, do any of the following steps:</span></span>

- <span data-ttu-id="61b1c-334">セキュリティ センターで、[メールの送信] **&[&** ポリシー] セクションの [フィッシング対策] \>  \>  \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="61b1c-334">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span> <span data-ttu-id="61b1c-335">ポリシー、その状態の値、および **優先度** の値の一覧を **確認** します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-335">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="61b1c-336">詳細を表示するには、名前をクリックして表示されるフライアウトの詳細を表示して、一覧からポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-336">To view more details, select the policy from the list by clicking on the name and viewing the details in the flyout that appears.</span></span>

- <span data-ttu-id="61b1c-337">PowerShell Exchange Online、ポリシーまたはルールの名前に置き換え、次のコマンドを実行 \<Name\> し、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="61b1c-337">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
