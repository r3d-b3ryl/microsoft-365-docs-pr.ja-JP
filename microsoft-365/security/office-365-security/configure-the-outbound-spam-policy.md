---
title: 送信スパム フィルターを構成する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、電子メール (EOP) で送信スパム ポリシーを表示、作成、変更、および削除するExchange Online Protectionできます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9ebff0a93acd505532773fbf5d714268df220c9a
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822011"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="24106-103">EOP で送信スパム フィルターを構成する</span><span class="sxs-lookup"><span data-stu-id="24106-103">Configure outbound spam filtering in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="24106-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="24106-104">**Applies to**</span></span>
- [<span data-ttu-id="24106-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="24106-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="24106-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="24106-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="24106-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="24106-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="24106-108">Microsoft 365 Exchange Online またはスタンドアロン Exchange Online Protection (EOP) 組織に Exchange Online メールボックスがない組織では、EOP を介して送信される送信電子メール メッセージが自動的にスパムや異常な送信アクティビティをチェックされます。</span><span class="sxs-lookup"><span data-stu-id="24106-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="24106-109">通常、組織内のユーザーからの送信スパムは、侵害されたアカウントを示します。</span><span class="sxs-lookup"><span data-stu-id="24106-109">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="24106-110">不審な送信メッセージはスパム (スパム信頼レベルまたは SCL に関係なく) としてマークされ、サービス[](high-risk-delivery-pool-for-outbound-messages.md)の評判を保護するために危険度の高い配信プールを経由してルーティングされます (つまり、Microsoft 365 送信元電子メール サーバーを IP ブロック リストからオフにします)。</span><span class="sxs-lookup"><span data-stu-id="24106-110">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="24106-111">管理者は、警告ポリシーを介して、不審な送信メール アクティビティとブロックされたユーザーに自動的 [に通知されます](../../compliance/alert-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="24106-111">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="24106-112">EOP は、スパムに対する組織の全体的な防御の一環として、送信スパム ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="24106-112">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="24106-113">詳細については、「[スパム対策保護](anti-spam-protection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24106-113">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="24106-114">管理者は、既定の送信スパム ポリシーを表示、編集、および構成できます (ただし、削除はされません)。</span><span class="sxs-lookup"><span data-stu-id="24106-114">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="24106-115">さらに細分化するために、組織内の特定のユーザー、グループ、またはドメインに適用されるカスタム送信スパム ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="24106-115">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="24106-116">カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (実行順序) を変更できます。</span><span class="sxs-lookup"><span data-stu-id="24106-116">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="24106-117">送信スパム ポリシーは、Microsoft 365 セキュリティ センターまたは PowerShell (Exchange Online のメールボックスを持つ Microsoft 365 組織の Exchange Online PowerShell、Exchange Online メールボックスのない組織のスタンドアロン EOP PowerShell) で構成できます。</span><span class="sxs-lookup"><span data-stu-id="24106-117">You can configure outbound spam policies in the Microsoft 365 security center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="24106-118">EOP の送信スパム ポリシーの基本的な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="24106-118">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="24106-119">**送信スパム フィルター ポリシー**: 送信スパム フィルターの評決と通知オプションのアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="24106-119">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="24106-120">**送信スパム フィルター ルール**: 送信スパム フィルター ポリシーの優先度と受信者フィルター (ポリシーが適用されるユーザー) を指定します。</span><span class="sxs-lookup"><span data-stu-id="24106-120">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="24106-121">セキュリティ センターで送信スパム ポリシーを管理する場合、これら 2 つの要素の違いは明らかではありません。</span><span class="sxs-lookup"><span data-stu-id="24106-121">The difference between these two elements isn't obvious when you manage outbound spam polices in the security center:</span></span>

- <span data-ttu-id="24106-122">ポリシーを作成すると、両方に同じ名前を使用して、実際に送信スパム フィルター ルールと関連付けられた送信スパム フィルター ポリシーを同時に作成します。</span><span class="sxs-lookup"><span data-stu-id="24106-122">When you create a policy, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="24106-123">ポリシーを変更すると、名前、優先度、有効または無効、および受信者フィルターに関連する設定によって、送信スパム フィルター ルールが変更されます。</span><span class="sxs-lookup"><span data-stu-id="24106-123">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="24106-124">その他の設定はすべて、関連付けられた送信スパム フィルター ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="24106-124">All other settings modify the associated outbound spam filter policy.</span></span>
- <span data-ttu-id="24106-125">ポリシーを削除すると、送信スパム フィルター ルールと関連付けられた送信スパム フィルター ポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="24106-125">When you remove a policy, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="24106-126">Exchange Online PowerShell またはスタンドアロン EOP PowerShell では、ポリシーとルールを個別に管理します。</span><span class="sxs-lookup"><span data-stu-id="24106-126">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="24106-127">詳細については、この記事の後半[Exchange Online「PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies)またはスタンドアロン EOP PowerShell を使用して送信スパム ポリシーを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24106-127">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) section later in this article.</span></span>

<span data-ttu-id="24106-128">すべての組織には、次のプロパティを持つ Default という名前の組み込みの送信スパム ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="24106-128">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="24106-129">ポリシーは、ポリシーに関連付けられた送信スパム フィルター ルール (受信者フィルター) がない場合でも、組織内のすべての受信者に適用されます。</span><span class="sxs-lookup"><span data-stu-id="24106-129">The policy is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="24106-130">ポリシーにはカスタムの優先順位の値 **Lowest** が設定されており、変更することはできません (このポリシーは常に最後に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="24106-130">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="24106-131">作成するどのカスタム ポリシーも、Default という名前のポリシーより高い優先順位を持ちます。</span><span class="sxs-lookup"><span data-stu-id="24106-131">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>
- <span data-ttu-id="24106-132">ポリシーは既定のポリシー (**IsDefault** のプロパティが `True` の値になっている) であり、既定のポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="24106-132">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="24106-133">送信スパム フィルターの効果を高めるには、特定のユーザーまたはユーザー グループに適用されるより厳密な設定で、カスタムの送信スパム ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="24106-133">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="24106-134">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="24106-134">What do you need to know before you begin?</span></span>

- <span data-ttu-id="24106-135"><https://security.microsoft.com> でセキュリティ センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="24106-135">You open the security center at <https://security.microsoft.com>.</span></span> <span data-ttu-id="24106-136">**[スパム対策の設定]** ページに直接移動するには、<https://security.microsoft.com/antispam> を使用します。</span><span class="sxs-lookup"><span data-stu-id="24106-136">To go directly to the **Anti-spam settings** page, use <https://security.microsoft.com/antispam>.</span></span>

- <span data-ttu-id="24106-137">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24106-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="24106-138">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24106-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="24106-139">この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="24106-139">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="24106-140">送信スパム ポリシーを追加、変更、および削除するには、組織の管理役割グループまたはセキュリティ管理者役割グループの **メンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="24106-140">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="24106-141">送信スパム ポリシーへの読み取り専用アクセスでは、グローバル リーダーまたはセキュリティ リーダーの役割グループの **メンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="24106-141">For read-only access to outbound spam policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="24106-142">詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24106-142">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="24106-143">**注**:</span><span class="sxs-lookup"><span data-stu-id="24106-143">**Notes**:</span></span>

  - <span data-ttu-id="24106-144">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="24106-144">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="24106-145">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24106-145">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="24106-146">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。</span><span class="sxs-lookup"><span data-stu-id="24106-146">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="24106-147">送信スパム ポリシーの推奨設定については、「EOP 送信スパム フィルター ポリシー [設定」を参照してください](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="24106-147">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="24106-148">[メール送信制限]という名前の既定のアラートポリシーが超過し、疑わしいメール送信パターンが検出され、ユーザーが既にメールを送信し、送信スパムによる異常な送信メール アクティビティとブロックされたユーザーに関する **TenantAdmins** **(グローバル** 管理者) グループのメンバーに電子メール通知を送信できません。 [](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="24106-148">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="24106-149">詳細については、「制限付きユーザー [のアラート設定を確認する」を参照してください](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。</span><span class="sxs-lookup"><span data-stu-id="24106-149">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="24106-150">送信スパム ポリシーの通知オプションの代わりに、これらのアラート ポリシーを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="24106-150">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security-center-to-create-outbound-spam-policies"></a><span data-ttu-id="24106-151">セキュリティ センターを使用して送信スパム ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="24106-151">Use the security center to create outbound spam policies</span></span>

<span data-ttu-id="24106-152">セキュリティ センターにカスタム送信スパム ポリシーを作成すると、両方に同じ名前を使用して、スパム フィルター ルールと関連付けられたスパム フィルター ポリシーが同時に作成されます。</span><span class="sxs-lookup"><span data-stu-id="24106-152">Creating a custom outbound spam policy in the security center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="24106-153">セキュリティ センターで、**[メールとコラボレーション]**、\>**[ポリシーとルール]**、\>**[驚異ポリシー]**、\>**[ポリシー]**[セクション]\> **[スパム対策]**.の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="24106-153">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="24106-154">[スパム対策 **ポリシー] ページで、[** ポリシーの作成] アイコンをクリックし、ドロップダウン リストから [送信 ![ ] ](../../media/m365-cc-sc-create-icon.png) を選択します。 </span><span class="sxs-lookup"><span data-stu-id="24106-154">On the **Anti-spam policies** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create policy** and then select **Outbound** from the drop down list.</span></span>

3. <span data-ttu-id="24106-155">ポリシー ウィザードが開きます。</span><span class="sxs-lookup"><span data-stu-id="24106-155">The policy wizard opens.</span></span> <span data-ttu-id="24106-156">**［ポリシーの名前を設定する］ ページ** で、以下の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="24106-156">On the **Name your policy page**, configure these settings:</span></span>
   - <span data-ttu-id="24106-157">**[名前]**: わかりやすい一意のポリシー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="24106-157">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="24106-158">**[説明]**: ポリシーについての説明を入力します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="24106-158">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="24106-159">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24106-159">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="24106-160">表示される **ユーザー、グループ、およびドメイン** ページで、ポリシーを適用する内部の受信者を特定します (受信者条件)。</span><span class="sxs-lookup"><span data-stu-id="24106-160">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="24106-161">**ユーザー**: 組織内で指定された 1 つ以上のメールボックス、メール ユーザー、またはメール連絡先。</span><span class="sxs-lookup"><span data-stu-id="24106-161">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="24106-162">**グループ**: 組織内で指定された配布グループ、メール対応セキュリティ グループ、または Microsoft 365 グループ。</span><span class="sxs-lookup"><span data-stu-id="24106-162">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="24106-163">**ドメイン**: 組織内で指定された [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)のすべての受信者。</span><span class="sxs-lookup"><span data-stu-id="24106-163">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="24106-164">適正なボックスをクリックし、値の入力を開始し、結果で希望する値を選択します。</span><span class="sxs-lookup"><span data-stu-id="24106-164">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="24106-165">必要な回数だけこの処理を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="24106-165">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="24106-166">既存の値を削除するには、削除をクリックします</span><span class="sxs-lookup"><span data-stu-id="24106-166">To remove an existing value, click remove</span></span> ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="24106-168">値の隣。</span><span class="sxs-lookup"><span data-stu-id="24106-168">next to the value.</span></span>

   <span data-ttu-id="24106-169">ユーザーやグループには、ほとんどの識別子 (名前、表示名、エイリアス、メールアドレス、アカウント名など) を使用できますが、対応する表示名が結果に表示されます。</span><span class="sxs-lookup"><span data-stu-id="24106-169">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="24106-170">ユーザーの場合、アスタリスク (\*) を単独で入力すると、使用可能なすべての値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="24106-170">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="24106-171">同じ条件に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="24106-171">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="24106-172">別の条件では、AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) を使用します。</span><span class="sxs-lookup"><span data-stu-id="24106-172">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="24106-173">**これらのユーザー、グループ、およびドメインを除外する**: ポリシーが適用される内部の受信者に関する例外 (受信者の例外) を追加するには、このオプションを選択して例外を構成します。</span><span class="sxs-lookup"><span data-stu-id="24106-173">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="24106-174">設定と動作は、条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="24106-174">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="24106-175">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24106-175">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="24106-176">開く **[保護の設定]** ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="24106-176">On the **Protection settings** page that opens, configure the following settings:</span></span>
   - <span data-ttu-id="24106-177">**メッセージの制限**: このセクションの設定では、メールボックスからの送信電子メール メッセージのExchange Online構成します。</span><span class="sxs-lookup"><span data-stu-id="24106-177">**Message limits**: The settings in this section configure the limits for outbound email messages from **Exchange Online** mailboxes:</span></span>
     - <span data-ttu-id="24106-178">**外部メッセージの制限を設定する**: 1 時間あたりの外部受信者の最大数。</span><span class="sxs-lookup"><span data-stu-id="24106-178">**Set an external message limit**: The maximum number of external recipients per hour.</span></span>
     - <span data-ttu-id="24106-179">**内部メッセージの制限を設定する**: 1 時間あたりの内部受信者の最大数。</span><span class="sxs-lookup"><span data-stu-id="24106-179">**Set an internal message limit**: The maximum number of internal recipients per hour.</span></span>
     - <span data-ttu-id="24106-180">**1 日のメッセージ制限を設定** する: 1 日あたりの受信者の最大数。</span><span class="sxs-lookup"><span data-stu-id="24106-180">**Set a daily message limit**: The maximum total number of recipients per day.</span></span>

     <span data-ttu-id="24106-181">有効な値は 0 ~ 10000 です。</span><span class="sxs-lookup"><span data-stu-id="24106-181">A valid value is 0 to 10000.</span></span> <span data-ttu-id="24106-182">既定値は 0 で、サービスの既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="24106-182">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="24106-183">詳細については、「送信制限 [」を参照してください](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)。</span><span class="sxs-lookup"><span data-stu-id="24106-183">For more information, see [Sending limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

    <span data-ttu-id="24106-184">ボックスに値を入力するか、ボックスの矢印を使用します。</span><span class="sxs-lookup"><span data-stu-id="24106-184">Enter a value in the box, or use the increase/decrease arrows on the box.</span></span>

   - <span data-ttu-id="24106-185">**メッセージの制限に達した** ユーザーに対する制限 : [保護の設定] セクションの制限を超えた場合に、ドロップダウン リストからアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="24106-185">**Restriction placed on users who reach the message limit**: Select an action from the drop down list when any of the limits in the **Protection settings** section are exceeded.</span></span>

     <span data-ttu-id="24106-186">すべてのアクションに対して **、User** で指定された受信者は、電子メール通知ポリシーの送信を制限します(また、冗長な [このページで送信スパムの送信のために送信者がブロックされている場合は、これらのユーザーとグループに通知する] で) 電子メール通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="24106-186">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify these users and groups if a sender is blocked due to sending outbound spam** setting later on this page) receive email notifications.</span></span>

     - <span data-ttu-id="24106-187">**ユーザーがメールを送信する日を次** の日まで制限します。これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="24106-187">**Restrict the user from sending mail until the following day**: This is the default value.</span></span> <span data-ttu-id="24106-188">電子メール通知が送信され、ユーザーは UTC 時間に基づいて、次の日までそれ以上メッセージを送信できません。</span><span class="sxs-lookup"><span data-stu-id="24106-188">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="24106-189">管理者がこのブロックを上書きする方法はありません。</span><span class="sxs-lookup"><span data-stu-id="24106-189">There is no way for the admin to override this block.</span></span>
       - <span data-ttu-id="24106-190">ユーザーという名前の **アクティビティ アラートは、** メールの送信を制限され、管理者に通知します (電子メールと [通知の表示 **] ページ** )。</span><span class="sxs-lookup"><span data-stu-id="24106-190">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>
       - <span data-ttu-id="24106-191">ポリシーの送信スパム **の送信設定** によって送信者がブロックされた場合は、特定のユーザーに通知するで指定された受信者も通知されます。</span><span class="sxs-lookup"><span data-stu-id="24106-191">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>
       - <span data-ttu-id="24106-192">ユーザーは、UTC 時間に基づいて、次の日までメッセージを送信できません。</span><span class="sxs-lookup"><span data-stu-id="24106-192">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="24106-193">管理者がこのブロックを上書きする方法はありません。</span><span class="sxs-lookup"><span data-stu-id="24106-193">There is no way for the admin to override this block.</span></span>
     - <span data-ttu-id="24106-194">**ユーザーによるメール** の送信を制限する : 電子メール通知が送信され、ユーザーがセキュリティ センターの制限付きユーザーに追加され、管理者によって制限付きユーザーから削除されるまで、ユーザーは電子メールを送信 <https://security.microsoft.com/restrictedusers> できません。管理者がリストからユーザーを削除した後、その日のユーザーは再び制限されません。</span><span class="sxs-lookup"><span data-stu-id="24106-194">**Restrict the user from sending mail**: Email notifications are sent, the user is added to **Restricted users** <https://security.microsoft.com/restrictedusers> in the security center, and the user can't send email until they're removed from **Restricted users** by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="24106-195">手順については、「迷惑メールの送信後に制限付きユーザー ポータルからユーザーを削除 [する」を参照してください](removing-user-from-restricted-users-portal-after-spam.md)。</span><span class="sxs-lookup"><span data-stu-id="24106-195">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>
     - <span data-ttu-id="24106-196">**アクションなし、アラートのみ**: 電子メール通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="24106-196">**No action, alert only**: Email notifications are sent.</span></span>

   - <span data-ttu-id="24106-197">**転送ルール**: このセクションの設定を使用して、メールボックスから外部送信者へのExchange Online **メール** の自動転送を制御します。</span><span class="sxs-lookup"><span data-stu-id="24106-197">**Forwarding rules**: Use the settings in this section to control automatic email forwarding by **Exchange Online mailboxes** to external senders.</span></span> <span data-ttu-id="24106-198">詳細については、「Control automatic external email forwarding in Microsoft 365 」[を参照してください](external-email-forwarding.md)。</span><span class="sxs-lookup"><span data-stu-id="24106-198">For more information, see [Control automatic external email forwarding in Microsoft 365](external-email-forwarding.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="24106-199">自動転送が無効になっている場合、外部の送信者が転送を行っているメールボックスに電子メールを送信した場合、受信者は配信不可レポート (NDR またはバウンス メッセージとも呼ばれる) を受信します。</span><span class="sxs-lookup"><span data-stu-id="24106-199">When automatic forwarding is disabled, the recipient will receive a non-delivery report (also known as an NDR or bounce message) if external senders send email to a mailbox that has forwarding in place.</span></span> <span data-ttu-id="24106-200">メッセージが内部送信者によって送信され、転送方法がメールボックス転送 [](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)_(SMTP_ 転送とも呼ばれる) の場合、内部送信者は NDR を取得します。</span><span class="sxs-lookup"><span data-stu-id="24106-200">If the message is sent by an internal sender **and** the forwarding method is [mailbox forwarding](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_), the internal sender will get the NDR.</span></span> <span data-ttu-id="24106-201">受信トレイ ルールが原因で転送が発生した場合、内部送信者は NDR を取得されません。</span><span class="sxs-lookup"><span data-stu-id="24106-201">The internal sender does not get an NDR if the forwarding occurred due to an inbox rule.</span></span>

     <span data-ttu-id="24106-202">[自動転送ルール] ドロップダウン リストから次のいずれかの **アクション** を選択します。</span><span class="sxs-lookup"><span data-stu-id="24106-202">Select one of the following actions from the **Automatic forwarding rules** drop down list:</span></span>

     - <span data-ttu-id="24106-203">**自動 - システム制御**: 送信スパム フィルターを使用して、外部メールの自動転送を制御できます。</span><span class="sxs-lookup"><span data-stu-id="24106-203">**Automatic - System-controlled**: Allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="24106-204">これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="24106-204">This is the default value.</span></span>
     - <span data-ttu-id="24106-205">**On**: ポリシーによって外部メールの自動転送は無効にされません。</span><span class="sxs-lookup"><span data-stu-id="24106-205">**On**: Automatic external email forwarding is not disabled by the policy.</span></span>
     - <span data-ttu-id="24106-206">**オフ**: ポリシーによってすべての自動外部メール転送が無効になります。</span><span class="sxs-lookup"><span data-stu-id="24106-206">**Off**: All automatic external email forwarding is disabled by the policy.</span></span>

   - <span data-ttu-id="24106-207">**通知**: セクションの設定を使用して、不審な送信メール メッセージのコピーと通知を受け取る必要がある追加の受信者を構成します。</span><span class="sxs-lookup"><span data-stu-id="24106-207">**Notifications**: Use the settings in the section to configure additional recipients who should receive copies and notifications of suspicious outbound email messages:</span></span>

     - <span data-ttu-id="24106-208">**これらのユーザーおよびグループに** 対して、これらの制限を超える疑わしい送信のコピーを送信する : この設定では、指定した受信者を不審な送信メッセージの BCC フィールドに追加します。</span><span class="sxs-lookup"><span data-stu-id="24106-208">**Send a copy of suspicious outbound that exceed these limits to these users and groups**: This setting adds the specified recipients to the Bcc field of suspicious outbound messages.</span></span>

       > [!NOTE]
       > <span data-ttu-id="24106-209">この設定は、既定の送信スパム ポリシーでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="24106-209">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="24106-210">作成したカスタム送信スパム ポリシーでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="24106-210">It doesn't work in custom outbound spam policies that you create.</span></span>

       <span data-ttu-id="24106-211">この設定を有効にするには、チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="24106-211">To enable this setting, select the check box.</span></span> <span data-ttu-id="24106-212">表示されるボックスで、ボックス内をクリックし、有効なメール アドレスを入力し、Enter キーを押するか、ボックスの下に表示される完全な値を選択します。</span><span class="sxs-lookup"><span data-stu-id="24106-212">In the box that appears, click in the box, enter a valid email address, and then press Enter or select the complete value that's displayed below the box.</span></span>

       <span data-ttu-id="24106-213">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="24106-213">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="24106-214">既存の値を削除するには、削除をクリックします</span><span class="sxs-lookup"><span data-stu-id="24106-214">To remove an existing value, click remove</span></span> ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="24106-216">値の隣。</span><span class="sxs-lookup"><span data-stu-id="24106-216">next to the value.</span></span>

   - <span data-ttu-id="24106-217">**送信スパムの送信によって送信者がブロックされた場合、これらのユーザーとグループに通知する**</span><span class="sxs-lookup"><span data-stu-id="24106-217">**Notify these users and groups if a sender is blocked due to sending outbound spam**</span></span>

     > [!IMPORTANT]
     >
     > - <span data-ttu-id="24106-218">この設定は、送信スパム ポリシーから廃止される過程です。</span><span class="sxs-lookup"><span data-stu-id="24106-218">This setting is in the process of being deprecated from outbound spam policies.</span></span>
     >
     > - <span data-ttu-id="24106-219">[受信者 [](../../compliance/alert-policies.md)の制限]セクションの制限を超えてユーザーがブロックされた場合、ユーザーが電子メールの送信を制限された既定のアラート ポリシーは **、TenantAdmins** ( Global  **admins**) グループのメンバーに電子メール通知を既に送信します。</span><span class="sxs-lookup"><span data-stu-id="24106-219">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="24106-220">**送信スパム ポリシーでこの** 設定ではなく、アラート ポリシーを使用して管理者や他のユーザーに通知することを強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="24106-220">**We strongly recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users**.</span></span> <span data-ttu-id="24106-221">手順については、「制限付き [ユーザーのアラート設定を確認する」を参照してください](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。</span><span class="sxs-lookup"><span data-stu-id="24106-221">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

   <span data-ttu-id="24106-222">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24106-222">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="24106-223">表示された **[レビュー]** ページで、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="24106-223">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="24106-224">各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="24106-224">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="24106-225">または、[戻る] **をクリック** するか、ウィザードで特定のページを選択します。</span><span class="sxs-lookup"><span data-stu-id="24106-225">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="24106-226">完了したら、**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24106-226">When you're finished, click **Create**.</span></span>

7. <span data-ttu-id="24106-227">表示された [確認]ページで、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24106-227">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-security-center-to-view-outbound-spam-policies"></a><span data-ttu-id="24106-228">セキュリティ センターを使用して送信スパム ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="24106-228">Use the security center to view outbound spam policies</span></span>

1. <span data-ttu-id="24106-229">セキュリティ センターで、**[メールとコラボレーション]**、\>**[ポリシーとルール]**、\>**[驚異ポリシー]**、\>**[ポリシー]**[セクション]\> **[スパム対策]**.の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="24106-229">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="24106-230">**[スパム対策ポリシー]** ページで、以下のいずれかの値を探します。</span><span class="sxs-lookup"><span data-stu-id="24106-230">On the **Anti-spam policies** page, look for one of the following values:</span></span>
   - <span data-ttu-id="24106-231">Type **値は** 、 **ユーザー設定の送信スパム ポリシーです。**</span><span class="sxs-lookup"><span data-stu-id="24106-231">The **Type** value is **Custom outbound spam policy**</span></span>
   - <span data-ttu-id="24106-232">Name **値** はスパム **対策送信ポリシーです (既定)**</span><span class="sxs-lookup"><span data-stu-id="24106-232">The **Name** value is **Anti-spam outbound policy (Default)**</span></span>

   <span data-ttu-id="24106-233">迷惑メール対策ポリシーの一覧には、以下のプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="24106-233">The following properties are displayed in the list of anti-spam policies:</span></span>

   - <span data-ttu-id="24106-234">**名前**</span><span class="sxs-lookup"><span data-stu-id="24106-234">**Name**</span></span>
   - <span data-ttu-id="24106-235">**状態**</span><span class="sxs-lookup"><span data-stu-id="24106-235">**Status**</span></span>
   - <span data-ttu-id="24106-236">**優先度**</span><span class="sxs-lookup"><span data-stu-id="24106-236">**Priority**</span></span>
   - <span data-ttu-id="24106-237">**種類**</span><span class="sxs-lookup"><span data-stu-id="24106-237">**Type**</span></span>

3. <span data-ttu-id="24106-238">名前をクリックして送信スパム ポリシーを選択すると、ポリシー設定がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="24106-238">When you select an outbound spam policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-security-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="24106-239">セキュリティ センターを使用して送信スパム ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="24106-239">Use the security center to modify outbound spam policies</span></span>

1. <span data-ttu-id="24106-240">セキュリティ センターで、**[メールとコラボレーション]**、\>**[ポリシーとルール]**、\>**[驚異ポリシー]**、\>**[ポリシー]**[セクション]\> **[スパム対策]**.の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="24106-240">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="24106-241">[スパム **対策ポリシー] ページ** で、名前をクリックして一覧から送信スパム ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="24106-241">On the **Anti-spam policies** page, select an outbound spam policy from the list by clicking on the name:</span></span>
   - <span data-ttu-id="24106-242">[種類] 列の値が [カスタム送信スパム ポリシー] であるカスタム **ポリシーを作成しました**。</span><span class="sxs-lookup"><span data-stu-id="24106-242">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>
   - <span data-ttu-id="24106-243">スパム対策送信ポリシー **(Default) という名前の既定のポリシー** です。</span><span class="sxs-lookup"><span data-stu-id="24106-243">The default policy named **Anti-spam outbound policy (Default)**.</span></span>

3. <span data-ttu-id="24106-244">表示されるポリシーの詳細ポップアップで、各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="24106-244">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="24106-245">設定の詳細については、この記事の「セキュリティ センターを使用して送信 [スパム](#use-the-security-center-to-create-outbound-spam-policies) ポリシーを作成する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="24106-245">For more information about the settings, see the previous [Use the security center to create outbound spam policies](#use-the-security-center-to-create-outbound-spam-policies) section in this article.</span></span>

   <span data-ttu-id="24106-246">既定の送信スパム ポリシーの場合、[適用対象] セクションは使用できません (ポリシーはすべてのユーザーに適用されます)、ポリシーの名前を変更できません。</span><span class="sxs-lookup"><span data-stu-id="24106-246">For the default outbound spam policy, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="24106-247">ポリシーを有効または無効にするには、ポリシーの優先順位を設定するか、またはエンドユーザーの検疫通知を構成します。後続の各セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="24106-247">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-custom-outbound-spam-policies"></a><span data-ttu-id="24106-248">カスタム送信スパム ポリシーを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="24106-248">Enable or disable custom outbound spam policies</span></span>

<span data-ttu-id="24106-249">既定の送信スパム ポリシーを無効にできない。</span><span class="sxs-lookup"><span data-stu-id="24106-249">You can't disable the default outbound spam policy.</span></span>

1. <span data-ttu-id="24106-250">セキュリティ センターで、**[メールとコラボレーション]**、\>**[ポリシーとルール]**、\>**[驚異ポリシー]**、\>**[ポリシー]**[セクション]\> **[スパム対策]**.の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="24106-250">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="24106-251">[スパム **対策ポリシー]** ページで、名前をクリックして、リストから[カスタム送信スパム ポリシーの種類] 値を持つポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="24106-251">On the **Anti-spam policies** page, select a policy with the **Type value** of **Custom  outbound spam policy** from the list by clicking on the name.</span></span>

3. <span data-ttu-id="24106-252">表示されるポリシーの詳細ポップアップの上部には、以下のいずれかの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="24106-252">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="24106-253">**ポリシー オフ**: ポリシーをオンにするには、![[アイコンをオンにする]](../../media/m365-cc-sc-turn-on-off-icon.png)、**[オンにする]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="24106-253">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="24106-254">**ポリシー オン**: ポリシーをオフにするには、![[アイコンをオフにする]](../../media/m365-cc-sc-turn-on-off-icon.png)、**[オフにする]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="24106-254">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="24106-255">確認ダイアログ ボックスが表示されたら、**[オンにする]** または **[オフにする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24106-255">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="24106-256">ポリシーの詳細ポップアップで **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24106-256">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="24106-257">ポリシーのメイン ページに戻ると、ポリシーの **[状態]** の値が **[オン]** または **[オフ]** になります。</span><span class="sxs-lookup"><span data-stu-id="24106-257">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="24106-258">カスタム送信スパム ポリシーの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="24106-258">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="24106-259">既定では、送信スパム ポリシーには、作成された順序に基づく優先度が与えられる (新しいポリシーは、古いポリシーよりも優先度が低くなります)。</span><span class="sxs-lookup"><span data-stu-id="24106-259">By default, outbound spam policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="24106-260">優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。</span><span class="sxs-lookup"><span data-stu-id="24106-260">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="24106-261">2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。</span><span class="sxs-lookup"><span data-stu-id="24106-261">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="24106-262">ポリシーの優先度を変更するには、ポリシーのプロパティで **[優先度を上げる]** または **[優先度を下げる]** をクリックします (セキュリティ センターの **[優先度]** の数値を直接変更することはできません)。</span><span class="sxs-lookup"><span data-stu-id="24106-262">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the security center).</span></span> <span data-ttu-id="24106-263">ポリシーの優先度を変更することは、複数のポリシーを所有している場合にのみ意味があります。</span><span class="sxs-lookup"><span data-stu-id="24106-263">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="24106-264">**注意**:</span><span class="sxs-lookup"><span data-stu-id="24106-264">**Notes**:</span></span>

- <span data-ttu-id="24106-265">セキュリティ センターでは、送信スパム ポリシーを作成した後にのみ、送信スパム ポリシーの優先度を変更できます。</span><span class="sxs-lookup"><span data-stu-id="24106-265">In the security center, you can only change the priority of the outbound spam policy after you create it.</span></span> <span data-ttu-id="24106-266">PowerShell では、スパム フィルター ルールの作成時に既定の優先度を上書きできます (この上書きが既存のルールの優先度に影響を与えることがあります)。</span><span class="sxs-lookup"><span data-stu-id="24106-266">In PowerShell, you can override the default priority when you create the spam filter rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="24106-267">送信スパム ポリシーは、表示順に処理されます (最初のポリシーの **優先度** は 0 です)。</span><span class="sxs-lookup"><span data-stu-id="24106-267">Outbound spam policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="24106-268">既定の送信スパム ポリシーの優先度の値は **[最低**] で、変更は行ないます。</span><span class="sxs-lookup"><span data-stu-id="24106-268">The default outbound spam policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="24106-269">セキュリティ センターで、**[メールとコラボレーション]**、\>**[ポリシーとルール]**、\>**[驚異ポリシー]**、\>**[ポリシー]**[セクション]\> **[スパム対策]**.の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="24106-269">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="24106-270">[スパム **対策ポリシー]** ページで、名前をクリックして、リストから[カスタム送信スパム ポリシーの種類] 値を持つポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="24106-270">On the **Anti-spam policies** page, select a select a policy with the **Type value** of **Custom outbound spam policy** from the list by clicking on the name.</span></span>

3. <span data-ttu-id="24106-271">表示されるポリシーの詳細ポップアップの上部には、現在の優先度の値とカスタム ポリシーの数に基づいて、**[優先度を上げる]** または **[優先度を下げる]** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="24106-271">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="24106-272">優先度の値が **0** の送信スパム **ポリシー** には、[優先度の下がり]**オプション** しか使用できません。</span><span class="sxs-lookup"><span data-stu-id="24106-272">The outbound spam policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="24106-273">優先度の値が最も低い送信スパム ポリシー (**たとえば、3)** には、[優先度の引き上げ]**オプション** しか使用できません。</span><span class="sxs-lookup"><span data-stu-id="24106-273">The outbound spam policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="24106-274">3 つ以上の送信スパム ポリシーがある場合、優先度の高い値と最も低い優先度の値の間のポリシーには、[優先度の引き上げ] オプションと [優先度の下げ] の両方 **のオプションがあります**。</span><span class="sxs-lookup"><span data-stu-id="24106-274">If you have three or more outbound spam policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="24106-275">![[優先度を上げる] アイコン](../../media/m365-cc-sc-increase-icon.png)、**[優先度を上げる]** の順にクリックするか、または ![[優先度を下げる] アイコン](../../media/m365-cc-sc-decrease-icon.png)、**[優先度を下げる]** の順にクリックして、**優先度** 値を変更します。</span><span class="sxs-lookup"><span data-stu-id="24106-275">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="24106-276">完了したら、ポリシーの詳細ポップアップで **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24106-276">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-security-center-to-remove-custom-outbound-spam-policies"></a><span data-ttu-id="24106-277">セキュリティ センターを使用してカスタム送信スパム ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="24106-277">Use the security center to remove custom outbound spam policies</span></span>

<span data-ttu-id="24106-278">セキュリティ センターを使用してカスタム送信スパム ポリシーを削除すると、スパム フィルター ルールと対応するスパム フィルター ポリシーの両方が削除されます。</span><span class="sxs-lookup"><span data-stu-id="24106-278">When you use the security center to remove a custom outbound spam policy, the spam filter rule and the corresponding spam filter policy are both deleted.</span></span> <span data-ttu-id="24106-279">既定の送信スパム ポリシーを削除できない。</span><span class="sxs-lookup"><span data-stu-id="24106-279">You can't remove the default outbound spam policy.</span></span>

1. <span data-ttu-id="24106-280">セキュリティ センターで、**[メールとコラボレーション]**、\>**[ポリシーとルール]**、\>**[驚異ポリシー]**、\>**[ポリシー]**[セクション]\> **[スパム対策]**.の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="24106-280">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="24106-281">[スパム **対策ポリシー]** ページで、名前をクリックして、リストから[カスタム送信スパム ポリシーの種類] 値を持つポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="24106-281">On the **Anti-spam policies** page, select a policy with the **Type value** of **Custom outbound spam policy** from the list by clicking on the name.</span></span> <span data-ttu-id="24106-282">表示されるポリシーの詳細ポップアウトの上部で、![[その他の操作] アイコン](../../media/m365-cc-sc-more-actions-icon.png)、**[その他の操作]** \>、![[ポリシーの削除] アイコン](../../media/m365-cc-sc-delete-icon.png)、**[ポリシーの削除]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="24106-282">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="24106-283">確認ダイアログ ボックスが表示されたら、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24106-283">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="24106-284">PowerShell Exchange Onlineスタンドアロン EOP PowerShell を使用して送信スパム ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="24106-284">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

<span data-ttu-id="24106-285">前述したように、送信スパム ポリシーは、送信スパム フィルター ポリシーと送信スパム フィルター ルールで構成されます。</span><span class="sxs-lookup"><span data-stu-id="24106-285">As previously described, an outbound spam policy consists of an outbound spam filter policy and an outbound spam filter rule.</span></span>

<span data-ttu-id="24106-286">PowerShell Exchange Onlineスタンドアロン EOP PowerShell では、送信スパム フィルター ポリシーと送信スパム フィルター ルールの違いが明らかです。</span><span class="sxs-lookup"><span data-stu-id="24106-286">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="24106-287">**\* -HostedOutboundSpamFilterPolicy** コマンドレットを使用して送信スパム フィルター ポリシーを管理し **\* 、-HostedOutboundSpamFilterRule** コマンドレットを使用して送信スパム フィルター ルールを管理します。</span><span class="sxs-lookup"><span data-stu-id="24106-287">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="24106-288">PowerShell では、最初に送信スパム フィルター ポリシーを作成してから、ルールが適用されるポリシーを識別する送信スパム フィルター ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="24106-288">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="24106-289">PowerShell では、送信スパム フィルター ポリシーの設定と送信スパム フィルター ルールを個別に変更します。</span><span class="sxs-lookup"><span data-stu-id="24106-289">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>
- <span data-ttu-id="24106-290">PowerShell から送信スパム フィルター ポリシーを削除すると、対応する送信スパム フィルター ルールは自動的には削除されません。その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="24106-290">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="24106-291">PowerShell を使用して送信スパム ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="24106-291">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="24106-292">PowerShell で送信スパム ポリシーを作成するには、次の 2 つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="24106-292">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="24106-293">送信スパム フィルター ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="24106-293">Create the outbound spam filter policy.</span></span>
2. <span data-ttu-id="24106-294">ルールが適用される送信スパム フィルター ポリシーを指定する送信スパム フィルター ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="24106-294">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

   <span data-ttu-id="24106-295">**注**:</span><span class="sxs-lookup"><span data-stu-id="24106-295">**Notes**:</span></span>

   - <span data-ttu-id="24106-296">新しい送信スパム フィルター ルールを作成し、関連付けされていない既存の送信スパム フィルター ポリシーを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="24106-296">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="24106-297">送信スパム フィルター ルールを複数の送信スパム フィルター ポリシーに関連付けできない。</span><span class="sxs-lookup"><span data-stu-id="24106-297">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>
   - <span data-ttu-id="24106-298">ポリシーを作成するまで、セキュリティ センターで使用できない PowerShell の新しい送信スパム フィルター ポリシーに対して、次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="24106-298">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the security center until after you create the policy:</span></span>
     - <span data-ttu-id="24106-299">無効として新しいポリシーを作成 _します_ `$false` **(New-HostedOutboundSpamFilterRule コマンドレットで有効** )。</span><span class="sxs-lookup"><span data-stu-id="24106-299">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
     - <span data-ttu-id="24106-300"> _\<Number\>_ **New-HostedOutboundSpamFilterRule** コマンドレットの作成時のポリシーの優先度 (優先度) を設定します。</span><span class="sxs-lookup"><span data-stu-id="24106-300">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
   - <span data-ttu-id="24106-301">PowerShell で作成した新しい送信スパム フィルター ポリシーは、ポリシーを送信スパム フィルター ルールに割り当てるまで、セキュリティ センターに表示されません。</span><span class="sxs-lookup"><span data-stu-id="24106-301">A new outbound spam filter policy that you create in PowerShell isn't visible in the security center until you assign the policy to an outbound spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="24106-302">手順 1: PowerShell を使用して送信スパム フィルター ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="24106-302">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="24106-303">送信スパム フィルター ポリシーを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="24106-303">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="24106-304">この例では、Contoso Executives という名前の新しい送信スパム フィルター ポリシーを次の設定で作成します。</span><span class="sxs-lookup"><span data-stu-id="24106-304">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="24106-305">受信者レートの制限は、既定値の小さい値に制限されます。</span><span class="sxs-lookup"><span data-stu-id="24106-305">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="24106-306">詳細については[、「Sending limits across Microsoft 365」 を参照してください](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)。</span><span class="sxs-lookup"><span data-stu-id="24106-306">For more information, see [Sending limits across Microsoft 365 options](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="24106-307">制限の 1 つに達すると、ユーザーはメッセージを送信できません。</span><span class="sxs-lookup"><span data-stu-id="24106-307">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="24106-308">構文とパラメーターの詳細については [、「New-HostedOutboundSpamFilterPolicy」を参照してください](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="24106-308">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="24106-309">手順 2: PowerShell を使用して送信スパム フィルター ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="24106-309">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="24106-310">送信スパム フィルター ルールを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="24106-310">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="24106-311">この例では、Contoso Executives という名前の新しい送信スパム フィルター ルールを次の設定で作成します。</span><span class="sxs-lookup"><span data-stu-id="24106-311">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="24106-312">Contoso Executives という名前の送信スパム フィルター ポリシーがルールに関連付けられている。</span><span class="sxs-lookup"><span data-stu-id="24106-312">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>
- <span data-ttu-id="24106-313">ルールは Contoso Executives Group という名前のグループのメンバーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="24106-313">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -FromMemberOf "Contoso Executives Group"
```

<span data-ttu-id="24106-314">構文とパラメーターの詳細については [、「New-HostedOutboundSpamFilterRule」を参照してください](/powershell/module/exchange/new-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="24106-314">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="24106-315">PowerShell を使用して送信スパム フィルター ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="24106-315">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="24106-316">すべての送信スパム フィルター ポリシーの概要リストを取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="24106-316">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="24106-317">特定の送信スパム フィルター ポリシーに関する詳細情報を取得するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="24106-317">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="24106-318">この例では、Executives という名前の送信スパム フィルター ポリシーのすべてのプロパティ値を返します。</span><span class="sxs-lookup"><span data-stu-id="24106-318">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="24106-319">構文とパラメーターの詳細については [、「Get-HostedOutboundSpamFilterPolicy」を参照してください](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="24106-319">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="24106-320">PowerShell を使用して送信スパム フィルター ルールを表示する</span><span class="sxs-lookup"><span data-stu-id="24106-320">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="24106-321">既存の送信スパム フィルター ルールを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="24106-321">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

<span data-ttu-id="24106-322">すべての送信スパム フィルター ルールの概要リストを取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="24106-322">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="24106-323">ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="24106-323">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="24106-324">特定の送信スパム フィルター ルールに関する詳細情報を取得するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="24106-324">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="24106-325">この例では、Contoso Executives という名前の送信スパム フィルター ルールのすべてのプロパティ値を返します。</span><span class="sxs-lookup"><span data-stu-id="24106-325">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="24106-326">構文とパラメーターの詳細については [、「Get-HostedOutboundSpamFilterRule」を参照してください](/powershell/module/exchange/get-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="24106-326">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="24106-327">PowerShell を使用して送信スパム フィルター ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="24106-327">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="24106-328">この記事の「手順 [1: PowerShell](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) を使用して送信スパム フィルター ポリシーを作成する」で説明したように、PowerShell でマルウェア フィルター ポリシーを変更する場合と同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="24106-328">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="24106-329">送信スパム フィルター ポリシーの名前を変更することはできません **(Set-HostedOutboundSpamFilterPolicy** コマンドレットには _Name_ パラメーターはありません)。</span><span class="sxs-lookup"><span data-stu-id="24106-329">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="24106-330">セキュリティ センターで送信スパム ポリシーの名前を変更する場合は、送信スパム フィルター ルールの名前を変更 _する_ のみです。</span><span class="sxs-lookup"><span data-stu-id="24106-330">When you rename an outbound spam policy in the security center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="24106-331">送信スパム フィルター ポリシーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="24106-331">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="24106-332">構文とパラメーターの詳細については [、「Set-HostedOutboundSpamFilterPolicy」を参照してください](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="24106-332">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="24106-333">PowerShell を使用して送信スパム フィルター ルールを変更する</span><span class="sxs-lookup"><span data-stu-id="24106-333">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="24106-334">PowerShell で送信スパム フィルター ルールを変更するときに使用できない唯一の設定は、無効なルールを作成できる _Enabled_ パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="24106-334">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="24106-335">既存の送信スパム フィルター ルールを有効または無効にするには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="24106-335">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="24106-336">それ以外の場合は、PowerShell で送信スパム フィルター ルールを変更するときに追加の設定を使用できません。</span><span class="sxs-lookup"><span data-stu-id="24106-336">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="24106-337">この記事の「手順 [2: PowerShell](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) を使用して送信スパム フィルター ルールを作成する」セクションで説明したように、ルールを作成する場合も同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="24106-337">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this article.</span></span>

<span data-ttu-id="24106-338">送信スパム フィルター ルールを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="24106-338">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="24106-339">構文とパラメーターの詳細については [、「Set-HostedOutboundSpamFilterRule」を参照してください](/powershell/module/exchange/set-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="24106-339">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="24106-340">PowerShell を使用して送信スパム フィルター ルールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="24106-340">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="24106-341">PowerShell で送信スパム フィルター ルールを有効または無効にすると、送信スパム ポリシー全体 (送信スパム フィルター ルールと割り当てられた送信スパム フィルター ポリシー) が有効または無効となります。</span><span class="sxs-lookup"><span data-stu-id="24106-341">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="24106-342">既定の送信スパム ポリシーを有効または無効にできない (常にすべての受信者に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="24106-342">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="24106-343">PowerShell で送信スパム フィルター ルールを有効または無効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="24106-343">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="24106-344">この例では、マーケティング部門という名前の送信スパム フィルター ルールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="24106-344">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="24106-345">この例では、同じルールを有効化します。</span><span class="sxs-lookup"><span data-stu-id="24106-345">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="24106-346">構文とパラメーターの詳細については [、「Enable-HostedOutboundSpamFilterRule」](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) および [「Disable-HostedOutboundSpamFilterRule」を参照してください](/powershell/module/exchange/disable-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="24106-346">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="24106-347">PowerShell を使用して送信スパム フィルター ルールの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="24106-347">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="24106-p142">ルールに設定できる優先度の最高値値は 0 です。設定できる最低値はルールの数に依存します。たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。たとえば、カスタム ルールが五つある場合 (優先度 0 から 4) に、一つのルールの優先度を 2 に変更した場合、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。</span><span class="sxs-lookup"><span data-stu-id="24106-p142">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="24106-353">PowerShell で送信スパム フィルター ルールの優先度を設定するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="24106-353">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="24106-p143">この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。</span><span class="sxs-lookup"><span data-stu-id="24106-p143">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="24106-356">**注**:</span><span class="sxs-lookup"><span data-stu-id="24106-356">**Notes**:</span></span>

- <span data-ttu-id="24106-357">新しいルールを作成するときに優先度を設定するには、代わりに **New-HostedOutboundSpamFilterRule** コマンドレットの Priority パラメーターを使用します。 </span><span class="sxs-lookup"><span data-stu-id="24106-357">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
- <span data-ttu-id="24106-358">送信の既定のスパム フィルター ポリシーには、対応するスパム フィルター ルールが含めず、常に変更できない優先度の値が **最低です**。</span><span class="sxs-lookup"><span data-stu-id="24106-358">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="24106-359">PowerShell を使用して送信スパム フィルター ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="24106-359">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="24106-360">PowerShell を使用して送信スパム フィルター ポリシーを削除すると、対応する送信スパム フィルター ルールは削除されません。</span><span class="sxs-lookup"><span data-stu-id="24106-360">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="24106-361">PowerShell で送信スパム フィルター ポリシーを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="24106-361">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="24106-362">この例では、Marketing Department という名前の送信スパム フィルター ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="24106-362">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="24106-363">構文とパラメーターの詳細については [、「Remove-HostedOutboundSpamFilterPolicy」を参照してください](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="24106-363">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="24106-364">PowerShell を使用して送信スパム フィルター ルールを削除する</span><span class="sxs-lookup"><span data-stu-id="24106-364">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="24106-365">PowerShell を使用して送信スパム フィルター ルールを削除すると、対応する送信スパム フィルター ポリシーは削除されません。</span><span class="sxs-lookup"><span data-stu-id="24106-365">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="24106-366">PowerShell で送信スパム フィルター ルールを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="24106-366">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="24106-367">この例では、Marketing Department という名前の送信スパム フィルター ルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="24106-367">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="24106-368">構文とパラメーターの詳細については [、「Remove-HostedOutboundSpamFilterRule」を参照してください](/powershell/module/exchange/remove-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="24106-368">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="24106-369">詳細情報</span><span class="sxs-lookup"><span data-stu-id="24106-369">For more information</span></span>

[<span data-ttu-id="24106-370">制限されたユーザー ポータルからブロックされたユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="24106-370">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="24106-371">送信メッセージにおける危険度の高い配信プール</span><span class="sxs-lookup"><span data-stu-id="24106-371">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="24106-372">スパム対策保護に関してよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="24106-372">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.yml)

[<span data-ttu-id="24106-373">自動転送済みメッセージレポート</span><span class="sxs-lookup"><span data-stu-id="24106-373">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)
