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
ms.openlocfilehash: 1a948604f11064f2c1fefcc441adc4a9792ac918
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108441"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="c343a-103">Microsoft Defender でフィッシング対策ポリシーを構成Office 365</span><span class="sxs-lookup"><span data-stu-id="c343a-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c343a-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="c343a-104">**Applies to**</span></span>
- [<span data-ttu-id="c343a-105">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="c343a-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c343a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c343a-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="c343a-107">[Microsoft Defender for Office 365](defender-for-office-365.md)のフィッシング対策ポリシーは、悪意のある偽装ベースのフィッシング攻撃や他の種類のフィッシング攻撃から組織を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c343a-107">Anti-phishing policies in [Microsoft Defender for Office 365](defender-for-office-365.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="c343a-108">Exchange Online Protection (EOP) のフィッシング対策ポリシーと microsoft Defender for Office 365 のフィッシング対策ポリシーの違いの詳細については、「フィッシング対策保護」を参照[してください](anti-phishing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="c343a-108">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="c343a-109">管理者は、既定のフィッシング対策ポリシーを表示、編集、および構成できます (ただし、削除はされません)。</span><span class="sxs-lookup"><span data-stu-id="c343a-109">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="c343a-110">さらに細分化するために、組織内の特定のユーザー、グループ、またはドメインに適用されるカスタムフィッシング対策ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="c343a-110">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="c343a-111">カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (実行順序) を変更できます。</span><span class="sxs-lookup"><span data-stu-id="c343a-111">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="c343a-112">Defender のフィッシング対策ポリシーは、Office 365ポータルまたは PowerShell Microsoft 365 Defender構成Exchange Onlineできます。</span><span class="sxs-lookup"><span data-stu-id="c343a-112">You can configure anti-phishing policies in Defender for Office 365 in the Microsoft 365 Defender portal or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="c343a-113">Exchange Online Protection で使用できるフィッシング対策ポリシー (つまり、Office 365 の Defender を使用しない組織) の構成の詳細については[、「EOP](configure-anti-phishing-policies-eop.md)でフィッシング対策ポリシーを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c343a-113">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection (that is, organizations without Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="c343a-114">フィッシング対策ポリシーの基本的な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c343a-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="c343a-115">**フィッシング対策ポリシー**: 有効または無効にするフィッシング保護と、オプションを適用するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="c343a-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="c343a-116">**フィッシング対策ルール**: フィッシング対策ポリシーの優先度と受信者フィルター (ポリシーが適用されるユーザー) を指定します。</span><span class="sxs-lookup"><span data-stu-id="c343a-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="c343a-117">これらの 2 つの要素の違いは、フィッシング対策ポリシーを管理する際に、Microsoft 365 Defenderされません。</span><span class="sxs-lookup"><span data-stu-id="c343a-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="c343a-118">ポリシーを作成すると、実際には両方に同じ名前を使用して、フィッシング対策ルールと関連付けられたフィッシング対策ポリシーを同時に作成します。</span><span class="sxs-lookup"><span data-stu-id="c343a-118">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="c343a-119">ポリシーを変更すると、名前、優先度、有効または無効、受信者フィルターに関連する設定によってフィッシング対策ルールが変更されます。</span><span class="sxs-lookup"><span data-stu-id="c343a-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="c343a-120">その他の設定はすべて、関連付けられたフィッシング対策ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="c343a-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="c343a-121">ポリシーを削除すると、フィッシング対策ルールと関連付けられたフィッシング対策ポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="c343a-121">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="c343a-122">PowerShell Exchange Onlineでは、ポリシーとルールを個別に管理します。</span><span class="sxs-lookup"><span data-stu-id="c343a-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="c343a-123">詳細については、この記事の[後半Exchange Online「PowerShell](#use-exchange-online-powershell-to-configure-anti-phishing-policies)を使用してフィッシング対策ポリシーを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c343a-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="c343a-124">すべての Defender for Office 365には、次のプロパティを持つ Office365 AntiPhish Default という名前のフィッシング対策ポリシーが組み込みされています。</span><span class="sxs-lookup"><span data-stu-id="c343a-124">Every Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="c343a-125">ポリシーは、ポリシーに関連付けられたフィッシング対策ルール (受信者フィルター) がない場合でも、組織内のすべての受信者に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c343a-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="c343a-126">ポリシーにはカスタムの優先順位の値 **Lowest** が設定されており、変更することはできません (このポリシーは常に最後に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="c343a-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="c343a-127">作成するどのカスタム ポリシーも、より高い優先順位を持ちます。</span><span class="sxs-lookup"><span data-stu-id="c343a-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="c343a-128">ポリシーは既定のポリシー (**IsDefault** のプロパティが `True` の値になっている) であり、既定のポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="c343a-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="c343a-129">Office 365 の Defender でのフィッシング対策保護の有効性を高めるには、特定のユーザーまたはユーザー グループに適用されるより厳しい設定でカスタムフィッシング対策ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c343a-129">To increase the effectiveness of anti-phishing protection in Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c343a-130">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="c343a-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c343a-131"><https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c343a-131">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="c343a-132">フィッシング対策ページに直接 **移動するには** 、 を使用します <https://security.microsoft.com/antiphishing> 。</span><span class="sxs-lookup"><span data-stu-id="c343a-132">To go directly to the **Anti-phishing** page, use <https://security.microsoft.com/antiphishing>.</span></span>

- <span data-ttu-id="c343a-133">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c343a-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="c343a-134">この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c343a-134">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="c343a-135">フィッシング対策ポリシーを追加、変更、削除するには、組織の管理役割グループまたはセキュリティ管理者役割グループのメンバー **である** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="c343a-135">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="c343a-136">フィッシング対策ポリシーへの読み取り専用アクセスには、グローバル リーダーまたはセキュリティ リーダーの役割グループのメンバー **である** 必要があります <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="c343a-136">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="c343a-137">詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c343a-137">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="c343a-138">**注**:</span><span class="sxs-lookup"><span data-stu-id="c343a-138">**Notes**:</span></span>

  - <span data-ttu-id="c343a-139">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="c343a-139">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="c343a-140">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c343a-140">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="c343a-141">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。</span><span class="sxs-lookup"><span data-stu-id="c343a-141">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="c343a-142">Defender for Office 365 でのフィッシング対策ポリシーの推奨設定については、「Defender for Office 365 設定」[を参照してください](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="c343a-142">For our recommended settings for anti-phishing policies in Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="c343a-143">新しいポリシーまたは更新されたポリシーを適用するには、最大 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="c343a-143">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="c343a-144">フィルター 処理パイプラインでフィッシング対策ポリシーが適用される場所については、「メール保護の順序と優先順位」 [を参照してください](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="c343a-144">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies"></a><span data-ttu-id="c343a-145">フィッシング対策Microsoft 365 Defenderを作成するには、このポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="c343a-145">Use the Microsoft 365 Defender portal to create anti-phishing policies</span></span>

<span data-ttu-id="c343a-146">Microsoft 365 Defender ポータルでカスタムフィッシング対策ポリシーを作成すると、両方に同じ名前を使用して、フィッシング対策ルールと関連付けられたフィッシング対策ポリシーが同時に作成されます。</span><span class="sxs-lookup"><span data-stu-id="c343a-146">Creating a custom anti-phishing policy in the Microsoft 365 Defender portal creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="c343a-147">[メール Microsoft 365 Defender] ポータルで、[メール &**グループ**&ルールの脅威ポリシー] ページの [フィッシング対策] \>  \>  \>  \> **セクションに移動します**。</span><span class="sxs-lookup"><span data-stu-id="c343a-147">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="c343a-148">[フィッシング対策 **] ページで、[** 作成] アイコン [作成] ![ を ](../../media/m365-cc-sc-create-icon.png) **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="c343a-148">On the **Anti-phishing** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="c343a-149">ポリシー ウィザードが開きます。</span><span class="sxs-lookup"><span data-stu-id="c343a-149">The policy wizard opens.</span></span> <span data-ttu-id="c343a-150">[ポリシー名 **] ページで** 、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="c343a-150">On the **Policy name** page, configure these settings:</span></span>
   - <span data-ttu-id="c343a-151">**[名前]**: わかりやすい一意のポリシー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="c343a-151">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="c343a-152">**[説明]**: ポリシーについての説明を入力します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="c343a-152">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="c343a-153">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c343a-153">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="c343a-154">表示される **ユーザー、グループ、およびドメイン** ページで、ポリシーを適用する内部の受信者を特定します (受信者条件)。</span><span class="sxs-lookup"><span data-stu-id="c343a-154">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="c343a-155">**ユーザー**: 組織内で指定された 1 つ以上のメールボックス、メール ユーザー、またはメール連絡先。</span><span class="sxs-lookup"><span data-stu-id="c343a-155">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="c343a-156">**グループ**: 組織内で指定された配布グループ、メール対応セキュリティ グループ、または Microsoft 365 グループ。</span><span class="sxs-lookup"><span data-stu-id="c343a-156">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="c343a-157">**ドメイン**: 組織内で指定された [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)のすべての受信者。</span><span class="sxs-lookup"><span data-stu-id="c343a-157">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="c343a-158">適正なボックスをクリックし、値の入力を開始し、結果で希望する値を選択します。</span><span class="sxs-lookup"><span data-stu-id="c343a-158">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="c343a-159">必要な回数だけこの処理を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="c343a-159">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="c343a-160">既存の値を削除するには、削除をクリックします</span><span class="sxs-lookup"><span data-stu-id="c343a-160">To remove an existing value, click remove</span></span> ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="c343a-162">値の隣。</span><span class="sxs-lookup"><span data-stu-id="c343a-162">next to the value.</span></span>

   <span data-ttu-id="c343a-163">ユーザーやグループには、ほとんどの識別子 (名前、表示名、エイリアス、メールアドレス、アカウント名など) を使用できますが、対応する表示名が結果に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c343a-163">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="c343a-164">ユーザーの場合、アスタリスク (\*) を単独で入力すると、使用可能なすべての値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c343a-164">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="c343a-165">同じ条件に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="c343a-165">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="c343a-166">別の条件では、AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c343a-166">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="c343a-167">**これらのユーザー、グループ、およびドメインを除外する**: ポリシーが適用される内部の受信者に関する例外 (受信者の例外) を追加するには、このオプションを選択して例外を構成します。</span><span class="sxs-lookup"><span data-stu-id="c343a-167">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="c343a-168">設定と動作は、条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="c343a-168">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="c343a-169">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c343a-169">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="c343a-170">表示される **[フィッシング&のしきい値** ] ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="c343a-170">On the **Phishing threshold & protection** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c343a-171">**フィッシングメールのしきい値**: スライダーを使用して、次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="c343a-171">**Phishing email threshold**: Use the slider to select one of the following values:</span></span>
     - <span data-ttu-id="c343a-172">**1 - Standard** (既定値です)。</span><span class="sxs-lookup"><span data-stu-id="c343a-172">**1 - Standard** (This is the default value.)</span></span>
     - <span data-ttu-id="c343a-173">**2 - アグレッシブ**</span><span class="sxs-lookup"><span data-stu-id="c343a-173">**2 - Aggressive**</span></span>
     - <span data-ttu-id="c343a-174">**3 - より積極的**</span><span class="sxs-lookup"><span data-stu-id="c343a-174">**3 - More aggressive**</span></span>
     - <span data-ttu-id="c343a-175">**4 - 最も積極的**</span><span class="sxs-lookup"><span data-stu-id="c343a-175">**4 - Most aggressive**</span></span>

     <span data-ttu-id="c343a-176">詳細については、「Microsoft Defender for Office 365」の「フィッシング対策ポリシーの高度[なフィッシングのしきい値」を参照してください](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="c343a-176">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="c343a-177">**偽装**: これらの設定は、受信メッセージの差出人アドレスで特定の送信者が (個別に、またはドメインごとに) 検索するポリシーの条件です。</span><span class="sxs-lookup"><span data-stu-id="c343a-177">**Impersonation**: These settings are a condition for the policy that identifies specific senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="c343a-178">詳細については、「Microsoft Defender for Office 365」の「フィッシング対策ポリシーの偽装[設定」を参照してください](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="c343a-178">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="c343a-179">各フィッシング対策ポリシーでは、最大 60 人の保護されたユーザー (送信者の電子メール アドレス) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c343a-179">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="c343a-180">複数のポリシーで同じ保護されたユーザーを指定できない。</span><span class="sxs-lookup"><span data-stu-id="c343a-180">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="c343a-181">送信者と受信者が以前に電子メールで通信した場合、ユーザー偽装保護は機能しません。</span><span class="sxs-lookup"><span data-stu-id="c343a-181">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="c343a-182">送信者と受信者がメールで通信したことがない場合、メッセージは偽装の試みとして識別されます。</span><span class="sxs-lookup"><span data-stu-id="c343a-182">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

     - <span data-ttu-id="c343a-183">**ユーザーの保護を有効** にする : 既定値はオフ (選択されていない) です。</span><span class="sxs-lookup"><span data-stu-id="c343a-183">**Enable users to protect**: The default value is off (not selected).</span></span> <span data-ttu-id="c343a-184">オンにする場合は、チェック ボックスをオンにし、表示される **[送信者の管理] (nn)** リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c343a-184">To turn it on, select the check box, and then click the **Manage (nn) sender(s)** link that appears.</span></span>

       <span data-ttu-id="c343a-185">表示される **偽装保護の送信者の** 管理フライアウトで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c343a-185">In the **Manage senders for impersonation protection** flyout that appears, do the following steps:</span></span>

       - <span data-ttu-id="c343a-186">**内部送信者:**[内部の追加] アイコン [ ![ 内部の ](../../media/m365-cc-sc-add-internal-icon.png) **選択] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c343a-186">**Internal senders**: Click ![Add internal icon](../../media/m365-cc-sc-add-internal-icon.png) **Select internal**.</span></span> <span data-ttu-id="c343a-187">表示される **[内部送信者の追加]** フライアウトで、ボックス内をクリックし、一覧から内部ユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c343a-187">In the **Add internal senders** flyout that appears, click in the box and select an internal user from the list.</span></span> <span data-ttu-id="c343a-188">リストをフィルター処理するには、ユーザーを入力し、結果からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c343a-188">You can filter the list by typing the user, and then selecting the user from the results.</span></span> <span data-ttu-id="c343a-189">ほとんどの識別子 (名前、表示名、エイリアス、メール アドレス、アカウント名など) を使用できますが、対応する表示名が結果に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c343a-189">You can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span>

         <span data-ttu-id="c343a-190">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="c343a-190">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="c343a-191">既存の値を削除するには、削除をクリックします</span><span class="sxs-lookup"><span data-stu-id="c343a-191">To remove an existing value, click remove</span></span> ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="c343a-193">値の隣。</span><span class="sxs-lookup"><span data-stu-id="c343a-193">next to the value.</span></span>

         <span data-ttu-id="c343a-194">完了したら、[追加] を **クリックします。**</span><span class="sxs-lookup"><span data-stu-id="c343a-194">When you're finished, click **Add**</span></span>

       - <span data-ttu-id="c343a-195">**外部送信者: [外部の追加**] ![ アイコン [外部の ](../../media/m365-cc-sc-create-icon.png) **選択] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c343a-195">**External senders**: Click ![Add external icon](../../media/m365-cc-sc-create-icon.png) **Select external**.</span></span> <span data-ttu-id="c343a-196">表示される **[外部送信者** の追加] フライアウトで、[名前の追加]ボックスに表示名を入力し、[空きメールの追加] ボックスに電子メール アドレスを入力し、[追加] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="c343a-196">In the **Add external senders** flyout that appears, enter a display name in the **Add a name** box and an email address in the **Add a vaild email** box, and then click **Add**.</span></span>

         <span data-ttu-id="c343a-197">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="c343a-197">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="c343a-198">既存の値を削除するには、削除をクリックします</span><span class="sxs-lookup"><span data-stu-id="c343a-198">To remove an existing value, click remove</span></span> ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="c343a-200">値の隣。</span><span class="sxs-lookup"><span data-stu-id="c343a-200">next to the value.</span></span>

         <span data-ttu-id="c343a-201">完了したら、[追加] を **クリックします。**</span><span class="sxs-lookup"><span data-stu-id="c343a-201">When you're finished, click **Add**</span></span>

       <span data-ttu-id="c343a-202">[偽装の **送信者の** 管理] フライアウトに戻り、リストから 1 つ以上のエントリを選択してエントリを削除できます。</span><span class="sxs-lookup"><span data-stu-id="c343a-202">Back on the **Manage senders for impersonation** flyout, you can remove entries by selecting one or more entries from the list.</span></span> <span data-ttu-id="c343a-203">[検索] アイコンの [検索] ボックスを ![ 使用してエントリ ](../../media/m365-cc-sc-create-icon.png) **を検索** できます。</span><span class="sxs-lookup"><span data-stu-id="c343a-203">You can search for entries using the ![Search icon](../../media/m365-cc-sc-create-icon.png) **Search** box.</span></span>

       <span data-ttu-id="c343a-204">少なくとも 1 つのエントリを選択すると、[選択したユーザーの削除] アイコン [選択したユーザーの削除] アイコンが表示され、選択したエントリを ![ ](../../media/m365-cc-sc-remove-selected-users-icon.png) 削除できます。</span><span class="sxs-lookup"><span data-stu-id="c343a-204">After you select at least one entry, the ![Remove selected users icon](../../media/m365-cc-sc-remove-selected-users-icon.png) **Remove selected users** icon appears, which you can use to remove the selected entries.</span></span>

       <span data-ttu-id="c343a-205">完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c343a-205">When you're finished, click **Done**.</span></span>

     - <span data-ttu-id="c343a-206">**保護するドメインを有効** にする: 既定値はオフ (選択されていない) です。</span><span class="sxs-lookup"><span data-stu-id="c343a-206">**Enable domains to protect**: The default value is off (not selected).</span></span> <span data-ttu-id="c343a-207">オンにするには、チェック ボックスをオンにし、表示される次の設定の一方または両方を構成します。</span><span class="sxs-lookup"><span data-stu-id="c343a-207">To turn it on, select the check box, and then configure one or both of the following settings that appear:</span></span>
       - <span data-ttu-id="c343a-208">**所有するドメインを含める**: この設定を有効にする場合は、チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="c343a-208">**Include the domains I own**: To turn this setting on, select the check box.</span></span> <span data-ttu-id="c343a-209">所有しているドメインを表示するには、[自分のドメインの **表示] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c343a-209">To view the domains that you own, click **View my domains**.</span></span>
       - <span data-ttu-id="c343a-210">**カスタム ドメインを含** める : この設定を有効にする場合は、チェック ボックスをオンにして、表示される **[管理] (nn)** カスタム ドメインのリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c343a-210">**Include custom domains**: To turn this setting on, select the check box, and then click the **Manage (nn) custom domain(s)** link that appears.</span></span> <span data-ttu-id="c343a-211">表示される **偽装保護用** のカスタム ドメインの管理フライアウトで、[ドメインの追加] アイコン [ドメインの追加 ![ ](../../media/m365-cc-sc-create-icon.png) **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c343a-211">In the **Manage custom domains for impersonation protection** flyout that appears, click ![Add domains icon](../../media/m365-cc-sc-create-icon.png) **Add domains**.</span></span>

         <span data-ttu-id="c343a-212">表示される **[カスタム ドメイン** の追加] フライアウトで、[ドメイン] ボックスをクリックして値を入力し、Enter キーを押するか、ボックスの下に表示される値を選択します。</span><span class="sxs-lookup"><span data-stu-id="c343a-212">In the **Add custom domains** flyout that appears, click in the **Domain** box, enter a value, and then press Enter or select the value that's displayed below the box.</span></span> <span data-ttu-id="c343a-213">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="c343a-213">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="c343a-214">既存の値を削除するには、値の横にある ![[アイコンの削除]](../../media/m365-cc-sc-remove-selection-icon.png) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c343a-214">To remove an existing value, click remove ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to the value.</span></span>

         <span data-ttu-id="c343a-215">完了したら、[ドメインの追加] **をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="c343a-215">When you're finished, click **Add domains**</span></span>

         > [!NOTE]
         > <span data-ttu-id="c343a-216">すべてのフィッシング対策ポリシーに最大 50 のドメインを設定できます。</span><span class="sxs-lookup"><span data-stu-id="c343a-216">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

       <span data-ttu-id="c343a-217">偽装用の **カスタム ドメイン** の管理フライアウトに戻り、リストから 1 つ以上のエントリを選択してエントリを削除できます。</span><span class="sxs-lookup"><span data-stu-id="c343a-217">Back on the **Manage custom domains for impersonation** flyout, you can remove entries by selecting one or more entries from the list.</span></span> <span data-ttu-id="c343a-218">[検索] アイコンの [検索] ボックスを ![ 使用してエントリ ](../../media/m365-cc-sc-create-icon.png) **を検索** できます。</span><span class="sxs-lookup"><span data-stu-id="c343a-218">You can search for entries using the ![Search icon](../../media/m365-cc-sc-create-icon.png) **Search** box.</span></span>

       <span data-ttu-id="c343a-219">少なくとも 1 つのエントリを選択すると、[ドメインの削除] アイコンが表示され、選択したエントリを ![ ](../../media/m365-cc-sc-delete-icon.png) 削除できます。</span><span class="sxs-lookup"><span data-stu-id="c343a-219">After you select at least one entry, the ![Delete domains icon](../../media/m365-cc-sc-delete-icon.png) **Delete** icon appears, which you can use to remove the selected entries.</span></span>

   - <span data-ttu-id="c343a-220">**信頼できる送信者と** ドメインを追加する : : [管理] **(nn)** 信頼できる送信者とドメインをクリックして、ポリシーの偽装保護の例外を指定します。</span><span class="sxs-lookup"><span data-stu-id="c343a-220">**Add trusted senders and domains**: : Specify impersonation protection exceptions for the policy by clicking on **Manage (nn) trusted sender(s) and domain(s)**.</span></span> <span data-ttu-id="c343a-221">表示される **偽装保護用** のカスタム ドメインの管理フライアウトで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="c343a-221">In the **Manage custom domains for impersonation protection** flyout that appears, configure the following settings:</span></span>
      - <span data-ttu-id="c343a-222">**[送信者**] : [送信者] **タブが** 選択され、[送信者の追加] アイコン ![ をクリックします ](../../media/m365-cc-sc-create-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="c343a-222">**Senders**: Verify the **Sender** tab is selected and click ![Add senders icon](../../media/m365-cc-sc-create-icon.png).</span></span> <span data-ttu-id="c343a-223">[信頼 **できる送信者の追加]** フライアウトが表示されたら、ボックスに電子メール アドレスを入力し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="c343a-223">In the **Add trusted senders** flyout that appears, enter an email address in the box and then click **Add**.</span></span> <span data-ttu-id="c343a-224">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="c343a-224">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="c343a-225">既存のエントリを削除するには、エントリの ![ [削除] ](../../media/m365-cc-sc-close-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c343a-225">To remove an existing entry, click ![Delete icon](../../media/m365-cc-sc-close-icon.png) for the entry.</span></span>

        <span data-ttu-id="c343a-226">完了したら、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c343a-226">When you're finished, click **Add**.</span></span>

      - <span data-ttu-id="c343a-227">**ドメイン:**[ドメイン] タブ **を選択** し、[ドメインの ![ 追加] アイコンをクリックします ](../../media/m365-cc-sc-create-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="c343a-227">**Domains**: Select the **Domain** tab and click ![Add domains icon](../../media/m365-cc-sc-create-icon.png).</span></span>
  
        <span data-ttu-id="c343a-228">[信頼 **できるドメイン** の追加] フライアウトが表示されたら、[ドメイン] ボックスをクリックして値を入力し、Enter キーを押するか、ボックスの下に表示される値を選択します。</span><span class="sxs-lookup"><span data-stu-id="c343a-228">In the **Add trusted domains** flyout that appears, click in the **Domain** box, enter a value, and then press Enter or select the value that's displayed below the box.</span></span> <span data-ttu-id="c343a-229">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="c343a-229">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="c343a-230">既存の値を削除するには、値の横にある ![[アイコンの削除]](../../media/m365-cc-sc-remove-selection-icon.png) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c343a-230">To remove an existing value, click remove ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to the value.</span></span>

        <span data-ttu-id="c343a-231">完了したら、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c343a-231">When you're finished, click **Add**.</span></span>

     <span data-ttu-id="c343a-232">偽装用の **カスタム** ドメインの管理フライアウトに戻り、リストから 1つ以上のエントリを選択して、[送信者] タブと [ドメイン] タブからエントリを削除できます。</span><span class="sxs-lookup"><span data-stu-id="c343a-232">Back on the **Manage custom domains for impersonation** flyout, you can remove entries from the **Sender** and **Domain** tabs by selecting one or more entries from the list.</span></span> <span data-ttu-id="c343a-233">[検索] アイコンの [検索] ボックスを ![ 使用してエントリ ](../../media/m365-cc-sc-create-icon.png) **を検索** できます。</span><span class="sxs-lookup"><span data-stu-id="c343a-233">You can search for entries using the ![Search icon](../../media/m365-cc-sc-create-icon.png) **Search** box.</span></span>

     <span data-ttu-id="c343a-234">少なくとも 1 つのエントリを選択すると、[ **削除** ] アイコンが表示され、選択したエントリを削除できます。</span><span class="sxs-lookup"><span data-stu-id="c343a-234">After you select at least one entry, the **Delete** icon appears, which you can use to remove the selected entries.</span></span>

     <span data-ttu-id="c343a-235">完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c343a-235">When you're finished, click **Done**.</span></span>

   - <span data-ttu-id="c343a-236">**メールボックス インテリジェンスを有効** にする: 既定値はオン (選択) であり、オンのままにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c343a-236">**Enable mailbox intelligence**: The default value is on (selected), and we recommend that you leave it on.</span></span> <span data-ttu-id="c343a-237">オフにする場合は、チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="c343a-237">To turn it off, clear the check box.</span></span>

     - <span data-ttu-id="c343a-238">**インテリジェンス ベースの偽装保護を有効** にする: この設定は、[メールボックス インテリジェンスを有効にする **]** がオン (選択) の場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c343a-238">**Enable intelligence based impersonation protection**: This setting is available only if **Enable mailbox intelligence** is on (selected).</span></span> <span data-ttu-id="c343a-239">この設定では、偽装の試行として識別されるメッセージに対してメールボックス インテリジェンスがアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="c343a-239">This setting allows mailbox intelligence to take action on messages that are identified as impersonation attempts.</span></span> <span data-ttu-id="c343a-240">次のページの [メールボックスインテリジェンスが偽装ユーザーを検出する場合] の設定で実行するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="c343a-240">You specify the action to take in the **If mailbox intelligence detects an impersonated user** setting on the next page.</span></span>

       <span data-ttu-id="c343a-241">この設定は、チェック ボックスをオンにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c343a-241">We recommend that you turn this setting on by selecting the check box.</span></span> <span data-ttu-id="c343a-242">この設定をオフにするには、チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="c343a-242">To turn this setting off, clear the check box.</span></span>

   - <span data-ttu-id="c343a-243">**ス** プーフィング : このセクションでは、[ス **プーフィング** インテリジェンスを有効にする] チェック ボックスを使用して、スプーフィング インテリジェンスのオンとオフを切り替えます。</span><span class="sxs-lookup"><span data-stu-id="c343a-243">**Spoof**: In this section, use the **Enable spoof intelligence** check box to turn spoof intelligence on or off.</span></span> <span data-ttu-id="c343a-244">既定値はオン (選択) であり、オンのままにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c343a-244">The default value is on (selected), and we recommend that you leave it on.</span></span> <span data-ttu-id="c343a-245">次のページの [メッセージがスプーフィングとして検出された場合]の設定で、ブロックされたスプーフィングされた送信者からのメッセージに対して実行するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="c343a-245">You specify the action to take on messages from blocked spoofed senders in the **If message is detected as spoof** setting on the next page.</span></span>

     <span data-ttu-id="c343a-246">スプーフィング インテリジェンスをオフにするには、チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="c343a-246">To turn off spoof intelligence, clear the check box.</span></span>

     > [!NOTE]
     > <span data-ttu-id="c343a-247">MX レコードがスプーフィング対策保護をオフにする必要Microsoft 365。代わりに、コネクタの拡張フィルターを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="c343a-247">You don't need to turn off anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="c343a-248">手順については、「拡張フィルタリング[for Connectors in Exchange Online」 を参照してください](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="c343a-248">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   <span data-ttu-id="c343a-249">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c343a-249">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="c343a-250">**[アクション]** ページが表示されたら、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="c343a-250">On the **Actions** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c343a-251">**メッセージアクション**: このセクションで次のアクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="c343a-251">**Message actions**: Configure the following actions in this section:</span></span>
     - <span data-ttu-id="c343a-252">**偽装ユーザーとしてメッセージが** 検出された場合: この設定は、[前のページでユーザーを保護する] を選択した場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c343a-252">**If message is detected as an impersonated user**: This setting is available only if you selected **Enable users to protect** on the previous page.</span></span> <span data-ttu-id="c343a-253">送信者が前のページで指定した保護されたユーザーの 1 人であるメッセージのドロップダウン リストで、次のいずれかのアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c343a-253">Select one of the following actions in the drop down list for messages where the sender is one of the protected users that you specified on the previous page:</span></span>
       - <span data-ttu-id="c343a-254">**アクションを適用しない**</span><span class="sxs-lookup"><span data-stu-id="c343a-254">**Don't apply any action**</span></span>
       - <span data-ttu-id="c343a-255">**メッセージを他の電子メール アドレスにリダイレクトする**</span><span class="sxs-lookup"><span data-stu-id="c343a-255">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="c343a-256">**受信者の迷惑メール フォルダーにメッセージを移動する**</span><span class="sxs-lookup"><span data-stu-id="c343a-256">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="c343a-257">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="c343a-257">**Quarantine the message**</span></span>
       - <span data-ttu-id="c343a-258">**メッセージを配信し、他のアドレスを Bcc 行に追加する**</span><span class="sxs-lookup"><span data-stu-id="c343a-258">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="c343a-259">**配信前にメッセージを削除する**</span><span class="sxs-lookup"><span data-stu-id="c343a-259">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="c343a-260">**メッセージが偽装ドメインとして** 検出された場合: この設定は、前のページで [保護するドメインを有効にする] を選択した場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c343a-260">**If the message is detected as an impersonated domain**: This setting is available only if you selected **Enable domains to protect** on the previous page.</span></span> <span data-ttu-id="c343a-261">送信者の電子メール アドレスが前のページで指定した保護されたドメインの 1 つにあるメッセージのドロップダウン リストで、次のいずれかのアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c343a-261">Select one of the following actions in the drop down list for messages where the sender's email address is in one of the protected domains that you specified on the previous page:</span></span>
       - <span data-ttu-id="c343a-262">**アクションを適用しない**</span><span class="sxs-lookup"><span data-stu-id="c343a-262">**Don't apply any action**</span></span>
       - <span data-ttu-id="c343a-263">**メッセージを他の電子メール アドレスにリダイレクトする**</span><span class="sxs-lookup"><span data-stu-id="c343a-263">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="c343a-264">**受信者の迷惑メール フォルダーにメッセージを移動する**</span><span class="sxs-lookup"><span data-stu-id="c343a-264">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="c343a-265">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="c343a-265">**Quarantine the message**</span></span>
       - <span data-ttu-id="c343a-266">**メッセージを配信し、他のアドレスを Bcc 行に追加する**</span><span class="sxs-lookup"><span data-stu-id="c343a-266">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="c343a-267">**配信前にメッセージを削除する**</span><span class="sxs-lookup"><span data-stu-id="c343a-267">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="c343a-268">**メールボックス インテリジェンスが偽装** ユーザーを検出した場合: この設定は、前のページで [偽装保護のインテリジェンスを有効にする] を選択した場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c343a-268">**If mailbox intelligence detects an impersonated user**: This setting is available only if you selected **Enable intelligence for impersonation protection** on the previous page.</span></span> <span data-ttu-id="c343a-269">メールボックス インテリジェンスによって偽装の試行として識別されたメッセージについては、ドロップダウン リストで次のいずれかのアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c343a-269">Select one of the following actions in the drop down list for messages that were identified as impersonation attempts by mailbox intelligence:</span></span>
       - <span data-ttu-id="c343a-270">**アクションを適用しない**</span><span class="sxs-lookup"><span data-stu-id="c343a-270">**Don't apply any action**</span></span>
       - <span data-ttu-id="c343a-271">**メッセージを他の電子メール アドレスにリダイレクトする**</span><span class="sxs-lookup"><span data-stu-id="c343a-271">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="c343a-272">**受信者の迷惑メール フォルダーにメッセージを移動する**</span><span class="sxs-lookup"><span data-stu-id="c343a-272">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="c343a-273">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="c343a-273">**Quarantine the message**</span></span>
       - <span data-ttu-id="c343a-274">**メッセージを配信し、他のアドレスを Bcc 行に追加する**</span><span class="sxs-lookup"><span data-stu-id="c343a-274">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="c343a-275">**配信前にメッセージを削除する**</span><span class="sxs-lookup"><span data-stu-id="c343a-275">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="c343a-276">**メッセージがスプーフィングとして検出された** 場合: この設定は、前のページで [スプーフィング インテリジェンスを有効にする] を選択した場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c343a-276">**If message is detected as spoof**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="c343a-277">ブロックされたスプーフィングされた送信者からのメッセージについては、ドロップダウン リストで次のいずれかのアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c343a-277">Select one of the following actions in the drop down list for messages from blocked spoofed senders:</span></span>
       - <span data-ttu-id="c343a-278">**受信者の迷惑メール フォルダーにメッセージを移動する**</span><span class="sxs-lookup"><span data-stu-id="c343a-278">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="c343a-279">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="c343a-279">**Quarantine the message**</span></span>

   - <span data-ttu-id="c343a-280">**安全に関&:** 次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="c343a-280">**Safety tips & indicators**: Configure the following settings:</span></span>
     - <span data-ttu-id="c343a-281">**最初の連絡先の安全性のヒント** を表示する : 詳細については [、「First contact 安全性のヒント」 を参照してください](set-up-anti-phishing-policies.md#first-contact-safety-tip)。</span><span class="sxs-lookup"><span data-stu-id="c343a-281">**Show first contact safety tip**: For more information, see [First contact safety tip](set-up-anti-phishing-policies.md#first-contact-safety-tip).</span></span>
     - <span data-ttu-id="c343a-282">**[ユーザーの偽装** 安全性のヒントを表示する: この設定は、[前のページでユーザーを保護する] を選択 **した** 場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c343a-282">**Show user impersonation safety tip**: This setting is available only if you selected **Enable users to protect** on the previous page.</span></span>
     - <span data-ttu-id="c343a-283">**[ドメイン偽装の** 安全性のヒントを表示する] : この設定は、[前のページで保護するドメインを有効にする] を選択した場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c343a-283">**Show domain impersonation safety tip**: This setting is available only if you selected **Enable domains to protect** on the previous page.</span></span>
     - <span data-ttu-id="c343a-284">**ユーザー偽装の異常な文字を表示安全性のヒント** この設定は、[ユーザーの保護を有効にする] または [前のページで保護するドメインを有効にする] を選択 **した** 場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c343a-284">**Show user impersonation unusual characters safety tip** This setting is available only if you selected **Enable users to protect** or **Enable domains to protect** on the previous page.</span></span>
     - <span data-ttu-id="c343a-285">**スプーフィング** の認証されていない送信者に対して表示 (?) : この設定は、前のページで [スプーフィング インテリジェンスを有効にする] を選択した場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c343a-285">**Show (?) for unauthenticated senders for spoof**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="c343a-286">メッセージが SPF または DKIM チェックに合格しない場合に、メッセージが DMARC または複合認証に合格しない場合は、Outlook の [差出人] ボックスの送信者の写真に疑問符を[追加](email-validation-and-authentication.md#composite-authentication)します。</span><span class="sxs-lookup"><span data-stu-id="c343a-286">Adds a question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span>
     - <span data-ttu-id="c343a-287">**"via" タグを表示** する : この設定は、前のページで [スプーフィング インテリジェンスを有効にする] を選択した場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c343a-287">**Show "via" tag**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="c343a-288">DKIM 署名または chris@contoso.com MAIL FROM アドレスのドメインと異なる場合は、from アドレスに via タグ (fabrikam.com 経由で) を **追加** します。</span><span class="sxs-lookup"><span data-stu-id="c343a-288">Adds a via tag (chris@contoso.com via fabrikam.com) to the From address if it's different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span> <span data-ttu-id="c343a-289">既定値はオン (選択) です。</span><span class="sxs-lookup"><span data-stu-id="c343a-289">The default value is on (selected).</span></span> <span data-ttu-id="c343a-290">オフにする場合は、チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="c343a-290">To turn it off, clear the check box.</span></span>

       > [!NOTE]
       > <span data-ttu-id="c343a-291">**["via"** タグを表示する] 設定が設定されていない場合、組織内のスプーフィング設定の認証されていない送信者に対して、疑問符と via タグの両方が Show **(?)** によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="c343a-291">If you don't have the **Show "via" tag** setting, the question mark **and** the via tag are both controlled by the **Show (?) for unauthenticated senders for spoof** setting in your organization.</span></span>

     <span data-ttu-id="c343a-292">設定を有効にする場合は、チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="c343a-292">To turn on a setting, select the check box.</span></span> <span data-ttu-id="c343a-293">オフにする場合は、チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="c343a-293">To turn it off, clear the check box.</span></span>

   <span data-ttu-id="c343a-294">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c343a-294">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="c343a-295">表示された **[レビュー]** ページで、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="c343a-295">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="c343a-296">各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="c343a-296">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="c343a-297">または、**[戻る]** をクリックするか、ウィザードで特定のページを選択します。</span><span class="sxs-lookup"><span data-stu-id="c343a-297">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="c343a-298">完了したら、**[送信]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c343a-298">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="c343a-299">表示された [確認]ページで、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c343a-299">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-phishing-policies"></a><span data-ttu-id="c343a-300">フィッシング対策Microsoft 365 Defenderを表示するには、このポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="c343a-300">Use the Microsoft 365 Defender portal to view anti-phishing policies</span></span>

1. <span data-ttu-id="c343a-301">[メール Microsoft 365 Defender] ポータルで、[メール &**グループ**&ルールの脅威ポリシー] ページの [フィッシング対策] \>  \>  \>  \> **セクションに移動します**。</span><span class="sxs-lookup"><span data-stu-id="c343a-301">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="c343a-302">[フィッシング **対策] ページ** では、フィッシング対策ポリシーの一覧に次のプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c343a-302">On the **Anti-phishing** page, the following properties are displayed in the list of anti-phishing policies:</span></span>

   - <span data-ttu-id="c343a-303">**名前**</span><span class="sxs-lookup"><span data-stu-id="c343a-303">**Name**</span></span>
   - <span data-ttu-id="c343a-304">**状態**</span><span class="sxs-lookup"><span data-stu-id="c343a-304">**Status**</span></span>
   - <span data-ttu-id="c343a-305">**優先度**</span><span class="sxs-lookup"><span data-stu-id="c343a-305">**Priority**</span></span>
   - <span data-ttu-id="c343a-306">**最終更新日時**</span><span class="sxs-lookup"><span data-stu-id="c343a-306">**Last modified**</span></span>

3. <span data-ttu-id="c343a-307">名前をクリックしてポリシーを選択すると、ポリシー設定がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c343a-307">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies"></a><span data-ttu-id="c343a-308">フィッシング対策Microsoft 365 Defenderポータルを使用して変更する</span><span class="sxs-lookup"><span data-stu-id="c343a-308">Use the Microsoft 365 Defender portal to modify anti-phishing policies</span></span>

1. <span data-ttu-id="c343a-309">[メール Microsoft 365 Defender] ポータルで、[メール &**グループ**&ルールの脅威ポリシー] ページの [フィッシング対策] \>  \>  \>  \> **セクションに移動します**。</span><span class="sxs-lookup"><span data-stu-id="c343a-309">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="c343a-310">[フィッシング **対策] ページで** 、名前をクリックして一覧からポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c343a-310">On the **Anti-phishing** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="c343a-311">表示されるポリシーの詳細ポップアップで、各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="c343a-311">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="c343a-312">設定の詳細については、この記事の「[](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies)フィッシング対策ポリシーを作成Microsoft 365 Defenderを使用してフィッシング対策ポリシーを作成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c343a-312">For more information about the settings, see the [Use the Microsoft 365 Defender portal to create anti-phishing policies](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies) section earlier in this article.</span></span>  

   <span data-ttu-id="c343a-313">既定のフィッシング対策ポリシーでは、[ユーザー、グループ、ドメイン] セクションは使用できません (ポリシーはすべてのユーザーに適用されます)、ポリシーの名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="c343a-313">For the default anti-phishing policy, the **Users, groups, and domains** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="c343a-314">ポリシーを有効または無効にするか、ポリシーの優先順位を設定するには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c343a-314">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="c343a-315">カスタムフィッシング対策ポリシーを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="c343a-315">Enable or disable custom anti-phishing policies</span></span>

<span data-ttu-id="c343a-316">既定のフィッシング対策ポリシーを無効にできない。</span><span class="sxs-lookup"><span data-stu-id="c343a-316">You can't disable the default anti-phishing policy.</span></span>

1. <span data-ttu-id="c343a-317">[メール Microsoft 365 Defender] ポータルで、[メール &**グループ**&ルールの脅威ポリシー] ページの [フィッシング対策] \>  \>  \>  \> **セクションに移動します**。</span><span class="sxs-lookup"><span data-stu-id="c343a-317">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="c343a-318">[フィッシング **対策] ページで** 、名前をクリックしてリストからカスタム ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c343a-318">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="c343a-319">表示されるポリシーの詳細ポップアップの上部には、以下のいずれかの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c343a-319">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="c343a-320">**ポリシー オフ**: ポリシーをオンにするには、![[アイコンをオンにする]](../../media/m365-cc-sc-turn-on-off-icon.png)、**[オンにする]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c343a-320">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="c343a-321">**ポリシー オン**: ポリシーをオフにするには、![[アイコンをオフにする]](../../media/m365-cc-sc-turn-on-off-icon.png)、**[オフにする]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c343a-321">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="c343a-322">確認ダイアログ ボックスが表示されたら、**[オンにする]** または **[オフにする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c343a-322">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="c343a-323">ポリシーの詳細ポップアップで **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c343a-323">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="c343a-324">ポリシーのメイン ページに戻ると、ポリシーの **[状態]** の値が **[オン]** または **[オフ]** になります。</span><span class="sxs-lookup"><span data-stu-id="c343a-324">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="c343a-325">カスタムフィッシング対策ポリシーの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="c343a-325">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="c343a-326">既定では、フィッシング対策ポリシーには、作成された順序に基づく優先度が与えられる (新しいポリシーは、以前のポリシーよりも優先度が低くなります)。</span><span class="sxs-lookup"><span data-stu-id="c343a-326">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="c343a-327">優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。</span><span class="sxs-lookup"><span data-stu-id="c343a-327">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="c343a-328">2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。</span><span class="sxs-lookup"><span data-stu-id="c343a-328">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="c343a-329">ポリシーの優先度を変更するには、ポリシーのプロパティで **[優先度を上げる]** または **[優先度を下げる]** をクリックします (Microsoft 365 Defender ポータルの **[優先度]** の数値を直接変更することはできません)。</span><span class="sxs-lookup"><span data-stu-id="c343a-329">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="c343a-330">ポリシーの優先度を変更することは、複数のポリシーを所有している場合にのみ意味があります。</span><span class="sxs-lookup"><span data-stu-id="c343a-330">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="c343a-331">**注意**:</span><span class="sxs-lookup"><span data-stu-id="c343a-331">**Notes**:</span></span>

- <span data-ttu-id="c343a-332">このポータルMicrosoft 365 Defender、フィッシング対策ポリシーの優先度を変更できるのは、作成後のみです。</span><span class="sxs-lookup"><span data-stu-id="c343a-332">In the Microsoft 365 Defender portal, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="c343a-333">PowerShell では、フィッシング対策ルールを作成するときに既定の優先度を上書きできます (既存のルールの優先度に影響を与える可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="c343a-333">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="c343a-334">フィッシング対策ポリシーは、表示順に処理されます (最初のポリシーの **優先度** は 0 です)。</span><span class="sxs-lookup"><span data-stu-id="c343a-334">Anti-phishing policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="c343a-335">既定のフィッシング対策ポリシーの優先度の値は **[最低**] で、変更は行えなくないます。</span><span class="sxs-lookup"><span data-stu-id="c343a-335">The default anti-phishing policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="c343a-336">[メール Microsoft 365 Defender] ポータルで、[メール &**グループ**&ルールの脅威ポリシー] ページの [フィッシング対策] \>  \>  \>  \> **セクションに移動します**。</span><span class="sxs-lookup"><span data-stu-id="c343a-336">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="c343a-337">[フィッシング **対策] ページで** 、名前をクリックしてリストからカスタム ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c343a-337">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="c343a-338">表示されるポリシーの詳細ポップアップの上部には、現在の優先度の値とカスタム ポリシーの数に基づいて、**[優先度を上げる]** または **[優先度を下げる]** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c343a-338">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="c343a-339">優先度の値が **0** **のポリシー** には、[優先度を下にする]**オプションしか** 使用できません。</span><span class="sxs-lookup"><span data-stu-id="c343a-339">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="c343a-340">優先度の値が最も **低い** ポリシー ( **たとえば、3)** には、[優先度の引き上げ] **オプション** しか使用できません。</span><span class="sxs-lookup"><span data-stu-id="c343a-340">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="c343a-341">3 つ以上のポリシーがある場合、優先度の高い値と最も低い優先度の値の間のポリシーには、[優先度の引き上げ] オプションと [優先度の下 **げ]** の両方 **のオプションがあります** 。</span><span class="sxs-lookup"><span data-stu-id="c343a-341">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="c343a-342">![[優先度を上げる] アイコン](../../media/m365-cc-sc-increase-icon.png)、**[優先度を上げる]** の順にクリックするか、または ![[優先度を下げる] アイコン](../../media/m365-cc-sc-decrease-icon.png)、**[優先度を下げる]** の順にクリックして、**優先度** 値を変更します。</span><span class="sxs-lookup"><span data-stu-id="c343a-342">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="c343a-343">完了したら、ポリシーの詳細ポップアップで **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c343a-343">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-phishing-policies"></a><span data-ttu-id="c343a-344">カスタムフィッシングMicrosoft 365 Defenderポリシーを削除するには、このポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="c343a-344">Use the Microsoft 365 Defender portal to remove custom anti-phishing policies</span></span>

<span data-ttu-id="c343a-345">Microsoft 365 Defenderポータルを使用してカスタムフィッシング対策ポリシーを削除すると、フィッシング対策ルールと対応するフィッシング対策ポリシーの両方が削除されます。</span><span class="sxs-lookup"><span data-stu-id="c343a-345">When you use the Microsoft 365 Defender portal to remove a custom anti-phishing policy, the anti-phish rule and the corresponding anti-phish policy are both deleted.</span></span> <span data-ttu-id="c343a-346">既定のフィッシング対策ポリシーを削除できない。</span><span class="sxs-lookup"><span data-stu-id="c343a-346">You can't remove the default anti-phishing policy.</span></span>

1. <span data-ttu-id="c343a-347">[メール Microsoft 365 Defender] ポータルで、[メール &**グループ**&ルールの脅威ポリシー] ページの [フィッシング対策] \>  \>  \>  \> **セクションに移動します**。</span><span class="sxs-lookup"><span data-stu-id="c343a-347">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="c343a-348">[フィッシング **対策] ページ** で、ポリシーの名前をクリックして、リストからカスタム ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c343a-348">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name of the policy.</span></span>

3. <span data-ttu-id="c343a-349">表示されるポリシーの詳細ポップアウトの上部で、![[その他の操作] アイコン](../../media/m365-cc-sc-more-actions-icon.png)、**[その他の操作]** \>、![[ポリシーの削除] アイコン](../../media/m365-cc-sc-delete-icon.png)、**[ポリシーの削除]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c343a-349">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

4. <span data-ttu-id="c343a-350">確認ダイアログ ボックスが表示されたら、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c343a-350">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="c343a-351">PowerShell Exchange Onlineを使用してフィッシング対策ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="c343a-351">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="c343a-352">前述したように、スパム対策ポリシーはフィッシング対策ポリシーとフィッシング対策ルールで構成されています。</span><span class="sxs-lookup"><span data-stu-id="c343a-352">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="c343a-353">PowerShell Exchange Online、フィッシング対策ポリシーとフィッシング対策ルールの違いは明らかです。</span><span class="sxs-lookup"><span data-stu-id="c343a-353">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="c343a-354">-AntiPhishPolicy コマンドレットを使用してフィッシング対策ポリシーを管理し **\* 、-AntiPhishRule** コマンドレットを使用してフィッシング対策ルールを管理します。 **\***</span><span class="sxs-lookup"><span data-stu-id="c343a-354">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="c343a-355">PowerShell では、最初にフィッシング対策ポリシーを作成してから、そのルールが適用されるポリシーを識別するフィッシング対策ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="c343a-355">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="c343a-356">PowerShell では、フィッシング対策ポリシーとフィッシング対策ルールの設定を個別に変更します。</span><span class="sxs-lookup"><span data-stu-id="c343a-356">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="c343a-357">PowerShell からフィッシング対策ポリシーを削除すると、対応するフィッシング対策ルールは自動的には削除されません。その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="c343a-357">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="c343a-358">PowerShell を使用してフィッシング対策ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="c343a-358">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="c343a-359">PowerShell でフィッシング対策ポリシーを作成するには、次の 2 つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c343a-359">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="c343a-360">フィッシング対策ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c343a-360">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="c343a-361">ルールが適用されるフィッシング対策ポリシーを指定するフィッシング対策ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="c343a-361">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="c343a-362">**注**:</span><span class="sxs-lookup"><span data-stu-id="c343a-362">**Notes**:</span></span>

- <span data-ttu-id="c343a-363">新しいフィッシング対策ルールを作成し、関連付けされていない既存のフィッシング対策ポリシーを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="c343a-363">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="c343a-364">フィッシング対策ルールを複数のフィッシング対策ポリシーに関連付けできない。</span><span class="sxs-lookup"><span data-stu-id="c343a-364">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>
- <span data-ttu-id="c343a-365">ポリシーの作成後まで、Microsoft 365 Defender ポータルで使用できない PowerShell の新しいフィッシング対策ポリシーで次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="c343a-365">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
  - <span data-ttu-id="c343a-366">無効として新しいポリシーを作成 _します_ `$false` **(New-AntiPhishRule コマンドレットで有効** )。</span><span class="sxs-lookup"><span data-stu-id="c343a-366">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="c343a-367"> _\<Number\>_ **New-AntiPhishRule** コマンドレットの作成時にポリシーの優先度 (優先度) を設定します。</span><span class="sxs-lookup"><span data-stu-id="c343a-367">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>
- <span data-ttu-id="c343a-368">PowerShell で作成した新しいフィッシング対策ポリシーは、ポリシーをフィッシング対策ルールに割り当てるまで、Microsoft 365 Defender ポータルに表示されません。</span><span class="sxs-lookup"><span data-stu-id="c343a-368">A new anti-phish policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="c343a-369">手順 1: PowerShell を使用してフィッシング対策ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="c343a-369">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="c343a-370">フィッシング対策ポリシーを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c343a-370">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="c343a-371">この例では、次の設定を使用して、Research Quarantine という名前のフィッシング対策ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c343a-371">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="c343a-372">ポリシーが有効になっています (Enabled パラメーターは使用していないので、既定値はです `$true` )。</span><span class="sxs-lookup"><span data-stu-id="c343a-372">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="c343a-373">説明は、調査部門のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="c343a-373">The description is: Research department policy.</span></span>
- <span data-ttu-id="c343a-374">すべての受け入れドメインに対する組織のドメイン保護と、ドメインの保護を対象 fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="c343a-374">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="c343a-375">偽装から保護するユーザーとして Mai Fujito (mfujito@fabrikam.com) を指定します。</span><span class="sxs-lookup"><span data-stu-id="c343a-375">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="c343a-376">メールボックスのインテリジェンスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="c343a-376">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="c343a-377">メールボックス インテリジェンス保護を有効にし、検疫アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="c343a-377">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="c343a-378">安全に関するヒントを有効にする。</span><span class="sxs-lookup"><span data-stu-id="c343a-378">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="c343a-379">構文とパラメーターの詳細については [、「New-AntiPhishPolicy」を参照してください](/powershell/module/exchange/New-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="c343a-379">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="c343a-380">手順 2: PowerShell を使用してフィッシング対策ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="c343a-380">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="c343a-381">フィッシング対策ルールを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c343a-381">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="c343a-382">この例では、次の条件を使用して、Research Department という名前のフィッシング対策ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="c343a-382">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="c343a-383">ルールは、Research Quarantine という名前のフィッシング対策ポリシーに関連付けられている。</span><span class="sxs-lookup"><span data-stu-id="c343a-383">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="c343a-384">ルールは Research Department という名前のグループのメンバーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="c343a-384">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="c343a-385">Priority パラメーターを使用していないので _、既定_ の優先度が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c343a-385">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="c343a-386">構文とパラメーターの詳細については [、「New-AntiPhishRule」を参照してください](/powershell/module/exchange/New-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="c343a-386">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="c343a-387">PowerShell を使用してフィッシング対策ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="c343a-387">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="c343a-388">既存のフィッシング対策ポリシーを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c343a-388">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="c343a-389">次の使用例は、指定したプロパティと共に、すべてのフィッシング対策ポリシーの概要リストを返します。</span><span class="sxs-lookup"><span data-stu-id="c343a-389">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="c343a-390">この例では、Executives という名前のフィッシング対策ポリシーのすべてのプロパティ値を返します。</span><span class="sxs-lookup"><span data-stu-id="c343a-390">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="c343a-391">構文とパラメーターの詳細については [、「Get-AntiPhishPolicy」を参照してください](/powershell/module/exchange/Get-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="c343a-391">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="c343a-392">PowerShell を使用してフィッシング対策ルールを表示する</span><span class="sxs-lookup"><span data-stu-id="c343a-392">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="c343a-393">既存のフィッシング対策ルールを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c343a-393">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="c343a-394">この例では、指定したプロパティと共に、すべてのフィッシング対策ルールの概要リストを返します。</span><span class="sxs-lookup"><span data-stu-id="c343a-394">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="c343a-395">ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c343a-395">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="c343a-396">この例では、Contoso Executives という名前のフィッシング対策ルールのすべてのプロパティ値を返します。</span><span class="sxs-lookup"><span data-stu-id="c343a-396">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="c343a-397">構文とパラメーターの詳細については [、「Get-AntiPhishRule」を参照してください](/powershell/module/exchange/Get-AntiPhishrule)。</span><span class="sxs-lookup"><span data-stu-id="c343a-397">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="c343a-398">PowerShell を使用してフィッシング対策ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="c343a-398">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="c343a-399">次の項目以外にも、「手順 [1: PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) を使用してフィッシング対策ポリシーを作成する」セクションで説明したように、PowerShell でフィッシング対策ポリシーを変更する場合と同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c343a-399">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this article.</span></span>

- <span data-ttu-id="c343a-400">指定したポリシーを既定のポリシーに変換する _MakeDefault_ スイッチ (すべてのユーザーに適用され、常に優先度が最も低く、削除できません) は、PowerShell でフィッシング対策ポリシーを変更する場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c343a-400">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="c343a-401">フィッシング対策ポリシーの名前を変更することはできません **(Set-AntiPhishPolicy** コマンドレットには _Name_ パラメーターはありません)。</span><span class="sxs-lookup"><span data-stu-id="c343a-401">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="c343a-402">Microsoft 365 Defender ポータルでフィッシング対策ポリシーの名前を変更すると、フィッシング対策ルールの名前が変更 _されます_。</span><span class="sxs-lookup"><span data-stu-id="c343a-402">When you rename an anti-phishing policy in the Microsoft 365 Defender portal, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="c343a-403">フィッシング対策ポリシーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c343a-403">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="c343a-404">構文とパラメーターの詳細については [、「Set-AntiPhishPolicy」を参照してください](/powershell/module/exchange/Set-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="c343a-404">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="c343a-405">PowerShell を使用してフィッシング対策ルールを変更する</span><span class="sxs-lookup"><span data-stu-id="c343a-405">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="c343a-406">PowerShell でフィッシング対策ルールを変更するときに使用できない唯一の設定は、無効なルールを作成できる _Enabled_ パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="c343a-406">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="c343a-407">既存のフィッシング対策ルールを有効または無効にするには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c343a-407">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="c343a-408">それ以外の場合は、PowerShell でフィッシング対策ルールを変更するときに追加の設定を使用できません。</span><span class="sxs-lookup"><span data-stu-id="c343a-408">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="c343a-409">この記事の「手順 [2: PowerShell](#step-2-use-powershell-to-create-an-anti-phish-rule) を使用してフィッシング対策ルールを作成する」セクションで説明したように、ルールを作成するときにも同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c343a-409">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="c343a-410">フィッシング対策ルールを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c343a-410">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="c343a-411">構文とパラメーターの詳細については [、「Set-AntiPhishRule」を参照してください](/powershell/module/exchange/set-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="c343a-411">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="c343a-412">PowerShell を使用してフィッシング対策ルールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="c343a-412">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="c343a-413">PowerShell でフィッシング対策ルールを有効または無効にすると、フィッシング対策ポリシー (フィッシング対策ルールと割り当てられたフィッシング対策ポリシー) 全体が有効または無効となります。</span><span class="sxs-lookup"><span data-stu-id="c343a-413">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="c343a-414">既定のフィッシング対策ポリシーを有効または無効にできない (すべての受信者に常に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="c343a-414">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="c343a-415">PowerShell でフィッシング対策ルールを有効または無効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c343a-415">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="c343a-416">この例では、Marketing Department という名前のフィッシング対策ルールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="c343a-416">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="c343a-417">この例では、同じルールを有効化します。</span><span class="sxs-lookup"><span data-stu-id="c343a-417">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="c343a-418">構文とパラメーターの詳細については [、「Enable-AntiPhishRule」](/powershell/module/exchange/enable-antiphishrule) および [「Disable-AntiPhishRule」を参照してください](/powershell/module/exchange/disable-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="c343a-418">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="c343a-419">PowerShell を使用してフィッシング対策ルールの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="c343a-419">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="c343a-p156">ルールに設定できる優先度の最高値値は 0 です。設定できる最低値はルールの数に依存します。たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。たとえば、カスタム ルールが五つある場合 (優先度 0 から 4) に、一つのルールの優先度を 2 に変更した場合、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。</span><span class="sxs-lookup"><span data-stu-id="c343a-p156">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="c343a-425">PowerShell でフィッシング対策ルールの優先度を設定するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c343a-425">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="c343a-p157">この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。</span><span class="sxs-lookup"><span data-stu-id="c343a-p157">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="c343a-428">**注**:</span><span class="sxs-lookup"><span data-stu-id="c343a-428">**Notes**:</span></span>

- <span data-ttu-id="c343a-429">新しいルールを作成するときに優先度を設定するには、代わりに **New-AntiPhishRule** コマンドレットの Priority パラメーターを使用します。 </span><span class="sxs-lookup"><span data-stu-id="c343a-429">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="c343a-430">既定のフィッシング対策ポリシーには、対応するフィッシング対策ルールが設定されていないので、常に変更できない優先度の値が **[最低**] です。</span><span class="sxs-lookup"><span data-stu-id="c343a-430">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="c343a-431">PowerShell を使用してフィッシング対策ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="c343a-431">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="c343a-432">PowerShell を使用してフィッシング対策ポリシーを削除すると、対応するフィッシング対策ルールは削除されません。</span><span class="sxs-lookup"><span data-stu-id="c343a-432">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="c343a-433">PowerShell でフィッシング対策ポリシーを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c343a-433">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="c343a-434">この例では、Marketing Department という名前のフィッシング対策ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="c343a-434">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="c343a-435">構文とパラメーターの詳細については [、「Remove-AntiPhishPolicy」を参照してください](/powershell/module/exchange/Remove-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="c343a-435">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="c343a-436">PowerShell を使用してフィッシング対策ルールを削除する</span><span class="sxs-lookup"><span data-stu-id="c343a-436">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="c343a-437">PowerShell を使用してフィッシング対策ルールを削除すると、対応するフィッシング対策ポリシーは削除されません。</span><span class="sxs-lookup"><span data-stu-id="c343a-437">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="c343a-438">PowerShell でフィッシング対策ルールを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c343a-438">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="c343a-439">この例では、Marketing Department という名前のフィッシング対策ルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="c343a-439">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="c343a-440">構文とパラメーターの詳細については [、「Remove-AntiPhishRule」を参照してください](/powershell/module/exchange/Remove-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="c343a-440">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="c343a-441">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="c343a-441">How do you know these procedures worked?</span></span>

<span data-ttu-id="c343a-442">Defender でフィッシング対策ポリシーが正常に構成されたことを確認するには、次Office 365手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c343a-442">To verify that you've successfully configured anti-phishing policies in Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="c343a-443">[メール Microsoft 365 Defender] ポータルで、[メール &**グループ**&ルールの脅威ポリシー] ページの [フィッシング対策] \>  \>  \>  \> **セクションに移動します**。</span><span class="sxs-lookup"><span data-stu-id="c343a-443">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span> <span data-ttu-id="c343a-444">ポリシー、その状態の値、および **優先度** の値の一覧を **確認** します。</span><span class="sxs-lookup"><span data-stu-id="c343a-444">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="c343a-445">詳細を表示するには、名前をクリックして表示されるフライアウトの詳細を表示して、一覧からポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c343a-445">To view more details, select the policy from the list by clicking on the name and viewing the details in the flyout that appears.</span></span>

- <span data-ttu-id="c343a-446">PowerShell Exchange Online、ポリシーまたはルールの名前に置き換え、次のコマンドを \<Name\> 実行して設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="c343a-446">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
