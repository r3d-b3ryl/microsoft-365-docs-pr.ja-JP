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
ms.openlocfilehash: 2448bb7942f7694d2a6d6e9b98537a2b7ccb14d1
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2021
ms.locfileid: "52331672"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="c4d1c-103">EOP で送信スパム フィルターを構成する</span><span class="sxs-lookup"><span data-stu-id="c4d1c-103">Configure outbound spam filtering in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c4d1c-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="c4d1c-104">**Applies to**</span></span>
- [<span data-ttu-id="c4d1c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c4d1c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c4d1c-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="c4d1c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c4d1c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c4d1c-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="c4d1c-108">Microsoft 365 Exchange Online またはスタンドアロン Exchange Online Protection (EOP) 組織に Exchange Online メールボックスがない組織では、EOP を介して送信される送信電子メール メッセージが自動的にスパムや異常な送信アクティビティをチェックされます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="c4d1c-109">通常、組織内のユーザーからの送信スパムは、侵害されたアカウントを示します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-109">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="c4d1c-110">不審な送信メッセージはスパム (スパム信頼レベルまたは SCL に関係なく) としてマークされ、サービス[](high-risk-delivery-pool-for-outbound-messages.md)の評判を保護するために危険度の高い配信プールを経由してルーティングされます (つまり、Microsoft 365 送信元電子メール サーバーを IP ブロック リストからオフにします)。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-110">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="c4d1c-111">管理者は、警告ポリシーを介して、不審な送信メール アクティビティとブロックされたユーザーに自動的 [に通知されます](../../compliance/alert-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-111">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="c4d1c-112">EOP は、スパムに対する組織の全体的な防御の一環として、送信スパム ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-112">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="c4d1c-113">詳細については、「[スパム対策保護](anti-spam-protection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-113">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="c4d1c-114">管理者は、既定の送信スパム ポリシーを表示、編集、および構成できます (ただし、削除はされません)。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-114">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="c4d1c-115">さらに細分化するために、組織内の特定のユーザー、グループ、またはドメインに適用されるカスタム送信スパム ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-115">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="c4d1c-116">カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (実行順序) を変更できます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-116">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="c4d1c-117">送信スパム ポリシーは、セキュリティ & コンプライアンス センターまたは PowerShell (Exchange Online のメールボックスを持つ Microsoft 365 組織の Exchange Online PowerShell、Exchange Online メールボックスのない組織のスタンドアロン EOP PowerShell) で構成できます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-117">You can configure outbound spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="c4d1c-118">EOP の送信スパム ポリシーの基本的な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-118">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="c4d1c-119">**送信スパム フィルター ポリシー**: 送信スパム フィルターの評決と通知オプションのアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-119">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="c4d1c-120">**送信スパム フィルター ルール**: 送信スパム フィルター ポリシーの優先度と受信者フィルター (ポリシーが適用されるユーザー) を指定します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-120">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="c4d1c-121">これらの 2 つの要素の違いは、セキュリティ コンプライアンス センターで送信スパム ポリシーを管理&ではありません。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-121">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="c4d1c-122">ポリシーを作成すると、両方に同じ名前を使用して、実際に送信スパム フィルター ルールと関連付けられた送信スパム フィルター ポリシーを同時に作成します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-122">When you create a policy, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="c4d1c-123">ポリシーを変更すると、名前、優先度、有効または無効、および受信者フィルターに関連する設定によって、送信スパム フィルター ルールが変更されます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-123">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="c4d1c-124">その他の設定はすべて、関連付けられた送信スパム フィルター ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-124">All other settings modify the associated outbound spam filter policy.</span></span>
- <span data-ttu-id="c4d1c-125">ポリシーを削除すると、送信スパム フィルター ルールと関連付けられた送信スパム フィルター ポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-125">When you remove a policy, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="c4d1c-126">Exchange Online PowerShell またはスタンドアロン EOP PowerShell では、ポリシーとルールを個別に管理します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-126">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="c4d1c-127">詳細については、この記事の後半[Exchange Online「PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies)またはスタンドアロン EOP PowerShell を使用して送信スパム ポリシーを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-127">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) section later in this article.</span></span>

<span data-ttu-id="c4d1c-128">すべての組織には、次のプロパティを持つ Default という名前の組み込みの送信スパム ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-128">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="c4d1c-129">ポリシーは、ポリシーに関連付けられた送信スパム フィルター ルール (受信者フィルター) がない場合でも、組織内のすべての受信者に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-129">The policy is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="c4d1c-130">ポリシーにはカスタムの優先順位の値 **Lowest** が設定されており、変更することはできません (このポリシーは常に最後に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-130">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="c4d1c-131">作成するどのカスタム ポリシーも、Default という名前のポリシーより高い優先順位を持ちます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-131">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>
- <span data-ttu-id="c4d1c-132">ポリシーは既定のポリシー (**IsDefault** のプロパティが `True` の値になっている) であり、既定のポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-132">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="c4d1c-133">送信スパム フィルターの効果を高めるには、特定のユーザーまたはユーザー グループに適用されるより厳密な設定で、カスタムの送信スパム ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-133">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c4d1c-134">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="c4d1c-134">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c4d1c-135"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-135">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="c4d1c-136">**[スパム対策の設定]** ページに直接移動するには、<https://protection.office.com/antispam> を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-136">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="c4d1c-137">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="c4d1c-138">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="c4d1c-139">この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-139">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="c4d1c-140">送信スパム ポリシーを追加、変更、および削除するには、組織の管理役割グループまたはセキュリティ管理者役割グループの **メンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-140">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="c4d1c-141">送信スパム ポリシーへの読み取り専用アクセスでは、グローバル リーダーまたはセキュリティ リーダーの役割グループの **メンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-141">For read-only access to outbound spam policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="c4d1c-142">詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-142">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="c4d1c-143">**注**:</span><span class="sxs-lookup"><span data-stu-id="c4d1c-143">**Notes**:</span></span>

  - <span data-ttu-id="c4d1c-144">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-144">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="c4d1c-145">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-145">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="c4d1c-146">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-146">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="c4d1c-147">送信スパム ポリシーの推奨設定については、「EOP 送信スパム フィルター ポリシー [設定」を参照してください](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-147">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="c4d1c-148">[メール送信制限]という名前の既定のアラートポリシーが超過し、疑わしいメール送信パターンが検出され、ユーザーが既にメールを送信し、送信スパムによる異常な送信メール アクティビティとブロックされたユーザーに関する **TenantAdmins** **(グローバル** 管理者) グループのメンバーに電子メール通知を送信できません。 [](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="c4d1c-148">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="c4d1c-149">詳細については、「制限付きユーザー [のアラート設定を確認する」を参照してください](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-149">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="c4d1c-150">送信スパム ポリシーの通知オプションの代わりに、これらのアラート ポリシーを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-150">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="c4d1c-151">コンプライアンス センターのセキュリティ &を使用して送信スパム ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="c4d1c-151">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="c4d1c-152">セキュリティ & コンプライアンス センターでカスタム送信スパム ポリシーを作成すると、両方に同じ名前を使用して、スパム フィルター ルールと関連付けられたスパム フィルター ポリシーが同時に作成されます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-152">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="c4d1c-153">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="c4d1c-154">[スパム対策 **の設定] ページで** 、[送信ポリシーの作成 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-154">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="c4d1c-155">[送信 **スパム フィルター ポリシー] が開いたら、** 次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-155">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="c4d1c-156">**[名前]**: わかりやすい一意のポリシー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-156">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="c4d1c-157">**[説明]**: ポリシーについての説明を入力します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-157">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="c4d1c-158">(省略可能)[通知 **] セクションを** 展開して、不審な送信メール メッセージのコピーと通知を受け取る必要がある追加のユーザーを構成します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-158">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="c4d1c-159">**不審な送信メール メッセージの** コピーを特定のユーザーに送信する : この設定では、指定したユーザーを BCC 受信者として不審な送信メッセージに追加します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-159">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span>

     > [!NOTE]
     > <span data-ttu-id="c4d1c-160">この設定は、既定の送信スパム ポリシーでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-160">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="c4d1c-161">作成したカスタム送信スパム ポリシーでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-161">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="c4d1c-162">この設定を有効にするには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-162">To enable this setting:</span></span>

     1. <span data-ttu-id="c4d1c-163">この設定を有効にするには、チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-163">Select the check box to enable the setting.</span></span>

     1. <span data-ttu-id="c4d1c-164">[ユーザー **の追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-164">Click **Add people**.</span></span> <span data-ttu-id="c4d1c-165">表示される **[受信者の追加または削除** ] フライアウトで、次の情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-165">In the **Add or remove recipients** flyout that appears:</span></span>

     1. <span data-ttu-id="c4d1c-166">送信者の電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-166">Enter the sender's email address.</span></span> <span data-ttu-id="c4d1c-167">複数の電子メール アドレスをセミコロンで区切って指定できます (;)または 1 行に 1 人の受信者。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-167">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     1. <span data-ttu-id="c4d1c-168">Click</span><span class="sxs-lookup"><span data-stu-id="c4d1c-168">Click</span></span> ![[追加] アイコン](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="c4d1c-170">をクリックして受信者を追加します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-170">to add the recipients.</span></span>

        <span data-ttu-id="c4d1c-171">必要な回数だけこれらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-171">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="c4d1c-172">追加した受信者は、フライアウトの **[受信者一覧** ] セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-172">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="c4d1c-173">受信者を削除するには、[削除] ボタン ![ をクリックします ](../../media/scc-remove-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-173">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     1. <span data-ttu-id="c4d1c-174">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-174">When you're finished, click **Save**.</span></span>

        <span data-ttu-id="c4d1c-175">この設定を無効にするには、チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-175">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="c4d1c-176">**送信スパムの送信によって送信者が** ブロックされた場合、特定のユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-176">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!IMPORTANT]
     >
     > - <span data-ttu-id="c4d1c-177">この設定は、送信スパム ポリシーから廃止される過程です。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-177">This setting is in the process of being deprecated from outbound spam policies.</span></span>
     >
     > - <span data-ttu-id="c4d1c-178">[受信者 [](../../compliance/alert-policies.md)の制限]セクションの制限を超えてユーザーがブロックされた場合、ユーザーが電子メールの送信を制限された既定のアラート ポリシーは **、TenantAdmins** ( Global  **admins**) グループのメンバーに電子メール通知を既に送信します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-178">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="c4d1c-179">**送信スパム ポリシーでこの** 設定ではなく、アラート ポリシーを使用して管理者や他のユーザーに通知することを強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-179">**We strongly recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users**.</span></span> <span data-ttu-id="c4d1c-180">手順については、「制限付き [ユーザーのアラート設定を確認する」を参照してください](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-180">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

5. <span data-ttu-id="c4d1c-181">(省略可能)[受信者 **の制限] セクションを展開** して、不審な送信メール メッセージの制限とアクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-181">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="c4d1c-182">これらの設定は、クラウドベースのメールボックスにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-182">These settings are only applicable to cloud-based mailboxes.</span></span>

   - <span data-ttu-id="c4d1c-183">**ユーザーごとの受信者の最大数**</span><span class="sxs-lookup"><span data-stu-id="c4d1c-183">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="c4d1c-184">有効な値は 0 ~ 10000 です。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-184">A valid value is 0 to 10000.</span></span> <span data-ttu-id="c4d1c-185">既定値は 0 で、サービスの既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-185">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="c4d1c-186">詳細については、「送信制限 [」を参照してください](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-186">For more information, see [Sending limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

     - <span data-ttu-id="c4d1c-187">**外部時間制限**: 1 時間あたりの外部受信者の最大数。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-187">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="c4d1c-188">**内部時間制限**: 1 時間あたりの内部受信者の最大数。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-188">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="c4d1c-189">**1 日** の制限 : 1 日あたりの受信者の最大数。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-189">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="c4d1c-190">**ユーザーが上記の制限** を超えた場合のアクション : 受信者の制限を超えた場合に実行する **アクションを構成** します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-190">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="c4d1c-191">すべてのアクションに対して **、User** で指定された受信者は、電子メール通知ポリシーの送信を制限します(また、現在冗長な冗長な [送信スパム ポリシーの送信スパム設定によって送信者がブロックされた場合に特定のユーザーに通知する] は、電子メール通知を受信します)。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-191">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="c4d1c-192">**メールの送信を次の日までユーザーに制限します**。これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-192">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="c4d1c-193">電子メール通知が送信され、ユーザーは UTC 時間に基づいて、次の日までそれ以上メッセージを送信できません。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-193">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="c4d1c-194">管理者がこのブロックを上書きする方法はありません。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-194">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="c4d1c-195">ユーザーという名前の **アクティビティ アラートは、** メールの送信を制限され、管理者に通知します (電子メールと [通知の表示 **] ページ** )。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-195">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="c4d1c-196">ポリシーの送信スパム **の送信設定** によって送信者がブロックされた場合は、特定のユーザーに通知するで指定された受信者も通知されます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-196">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="c4d1c-197">ユーザーは、UTC 時間に基づいて、次の日までメッセージを送信できません。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-197">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="c4d1c-198">管理者がこのブロックを上書きする方法はありません。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-198">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="c4d1c-199">ユーザーによるメールの送信を制限する **:** 電子メール通知が送信され、セキュリティ & コンプライアンス センターの [制限付きユーザー **] <https://sip.protection.office.com/restrictedusers>** ポータルにユーザーが追加され、管理者が制限付きユーザー ポータルから削除されるまで、ユーザーは電子メールを送信できません。管理者がリストからユーザーを削除した後、その日のユーザーは再び制限されません。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-199">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="c4d1c-200">手順については、「迷惑メールの送信後に制限付きユーザー ポータルからユーザーを削除 [する」を参照してください](removing-user-from-restricted-users-portal-after-spam.md)。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-200">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="c4d1c-201">**アクションなし、アラートのみ**: 電子メール通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-201">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="c4d1c-202">(省略可能)[ **自動転送] セクションを** 展開して、ユーザーによる外部送信者への自動メール転送を制御します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-202">(Optional) Expand **Automatic forwarding** section to control automatic email forwarding by users to external senders.</span></span> <span data-ttu-id="c4d1c-203">詳細については [、「Microsoft 365](external-email-forwarding.md)で外部メールの自動転送を制御する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-203">For more information, see [Control automatic external email forwarding in Microsoft 365](external-email-forwarding.md).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="c4d1c-204">2020 年 9 月以前は、これらの設定は使用できますが、適用されません。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-204">Before September 2020, these settings are available but not enforced.</span></span>
   >
   > - <span data-ttu-id="c4d1c-205">これらの設定は、クラウドベースのメールボックスにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-205">These settings apply only to cloud-based mailboxes.</span></span>
   >
   > - <span data-ttu-id="c4d1c-206">自動転送が無効になっている場合、外部の送信者が転送を行っているメールボックスに電子メールを送信した場合、受信者は配信不可レポート (NDR またはバウンス メッセージとも呼ばれる) を受信します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-206">When automatic forwarding is disabled, the recipient will receive a non-delivery report (also known as an NDR or bounce message) if external senders send email to a mailbox that has forwarding in place.</span></span> <span data-ttu-id="c4d1c-207">メッセージが内部送信者によって送信され、転送方法がメールボックス転送 [](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)_(SMTP_ 転送とも呼ばれる) の場合、内部送信者は NDR を取得します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-207">If the message is sent by an internal sender **and** the forwarding method is [mailbox forwarding](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_), the internal sender will get the NDR.</span></span> <span data-ttu-id="c4d1c-208">受信トレイ ルールが原因で転送が発生した場合、内部送信者は NDR を取得されません。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-208">The internal sender does not get an NDR if the forwarding occurred due to an inbox rule.</span></span>

   <span data-ttu-id="c4d1c-209">使用できる値は次のとおりです:</span><span class="sxs-lookup"><span data-stu-id="c4d1c-209">The available values are:</span></span>

   - <span data-ttu-id="c4d1c-210">**自動 - システム制御**: 送信スパム フィルターを使用して、外部メールの自動転送を制御できます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-210">**Automatic - System-controlled**: Allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="c4d1c-211">これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-211">This is the default value.</span></span>
   - <span data-ttu-id="c4d1c-212">**On**: ポリシーによって外部メールの自動転送は無効にされません。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-212">**On**: Automatic external email forwarding is not disabled by the policy.</span></span>
   - <span data-ttu-id="c4d1c-213">**オフ**: ポリシーによってすべての自動外部メール転送が無効になります。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-213">**Off**: All automatic external email forwarding is disabled by the policy.</span></span>

7. <span data-ttu-id="c4d1c-214">(必須)[適用対象 **] セクションを** 展開して、ポリシーが適用される内部送信者を識別します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-214">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="c4d1c-215">各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-215">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="c4d1c-216">同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<sender1\>_ または _\<sender2\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-216">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="c4d1c-217">a別の条件や例外がある場合は AND ロジック (たとえば、_\<sender1\>_ かつ _\<member of group 1\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-217">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="c4d1c-218">使用可能なすべての条件を表示するには、**[条件の追加]** を 3 回クリックするのが最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-218">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="c4d1c-219">構成しない条件を削除するには、![[削除] ボタン](../../media/scc-remove-icon.png)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-219">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="c4d1c-220">**[送信者ドメイン]**: 組織内で構成されている 1 つ以上の受け入れ済みドメインの送信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-220">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in the organization.</span></span> <span data-ttu-id="c4d1c-221">**[タグの追加]** ボックスをクリックして、ドメインを表示および選択します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-221">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="c4d1c-222">複数のドメインが利用可能な場合は、**[タグの追加]** ボックスをもう一度クリックして、追加のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-222">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="c4d1c-223">**Sender is**: 組織内の 1 つ以上のユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-223">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="c4d1c-224">**[タグの追加]** をクリックして、リストをフィルター処理するための入力を始めます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-224">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="c4d1c-225">[タグの追加 **] ボックスを再度クリック** して、追加の送信者を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-225">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="c4d1c-226">**Sender はメンバーです:** 組織内の 1 つ以上のグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-226">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="c4d1c-227">**[タグの追加]** をクリックして、リストをフィルター処理するための入力を始めます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-227">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="c4d1c-228">[タグの追加 **] ボックスを再度クリック** して、追加の送信者を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-228">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="c4d1c-229">**次の場合を除く**: ルールの例外を追加するには、**[条件の追加]** を 3 回クリックして、使用可能なすべての例外を表示します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-229">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="c4d1c-230">設定と動作は、条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-230">The settings and behavior are exactly like the conditions.</span></span>

8. <span data-ttu-id="c4d1c-231">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-231">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="c4d1c-232">コンプライアンス センターのセキュリティ &を使用して送信スパム ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="c4d1c-232">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="c4d1c-233">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-233">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="c4d1c-234">[スパム対策 **の設定] ページで** 、[展開] アイコン ![ をクリック ](../../media/scc-expand-icon.png) して送信スパム ポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-234">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="c4d1c-235">[送信スパム フィルター ポリシー **] という名前の既定のポリシー** です。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-235">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="c4d1c-236">[種類] 列の値が [カスタム送信スパム ポリシー] であるカスタム **ポリシーを作成しました**。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-236">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="c4d1c-237">ポリシー設定が表示される展開されたポリシーの詳細に表示されます。または[ポリシーの編集] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-237">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="c4d1c-238">コンプライアンス センターのセキュリティ &を使用して送信スパム ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="c4d1c-238">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="c4d1c-239">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-239">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="c4d1c-240">[スパム対策 **の設定] ページで** 、[展開] アイコン ![ をクリック ](../../media/scc-expand-icon.png) して送信スパム ポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-240">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="c4d1c-241">[送信スパム フィルター ポリシー **] という名前の既定のポリシー** です。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-241">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="c4d1c-242">[種類] 列の値が [カスタム送信スパム ポリシー] であるカスタム **ポリシーを作成しました**。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-242">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="c4d1c-243">**[ポリシーの編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-243">Click **Edit policy**.</span></span>

<span data-ttu-id="c4d1c-244">カスタム送信スパム ポリシーの場合、表示されるフライアウトで使用可能な設定は、「セキュリティ & コンプライアンス センターを使用して送信スパム ポリシーを作成する」セクションで説明されている設定と[同じです。](#use-the-security--compliance-center-to-create-outbound-spam-policies)</span><span class="sxs-lookup"><span data-stu-id="c4d1c-244">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="c4d1c-245">[送信スパム フィルター ポリシー]という名前の既定の送信スパム ポリシーの場合、[適用対象] セクションは使用できません (ポリシーはすべてのユーザーに適用されます)、ポリシーの名前を変更できません。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-245">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="c4d1c-246">ポリシーを有効または無効にするには、ポリシーの優先順位を設定するか、またはエンドユーザーの検疫通知を構成します。後続の各セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-246">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="c4d1c-247">送信スパム ポリシーを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="c4d1c-247">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="c4d1c-248">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-248">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="c4d1c-249">[スパム対策 **設定]** ページで、[展開] アイコンをクリックして、作成したカスタム ポリシーを展開します ([種類] 列の値は [カスタム送信スパム ポリシー ![ ] ](../../media/scc-expand-icon.png) **です**)。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-249">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="c4d1c-250">展開して表示されたポリシー詳細で、**[On]** 列の値をメモします。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-250">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="c4d1c-251">ポリシーを無効にするには、左に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-251">Move the toggle to the left to disable the policy:</span></span> ![オフに切り替え](../../media/scc-toggle-off.png)

   <span data-ttu-id="c4d1c-253">ポリシーを有効にするには、右に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-253">Move the toggle to the right to enable the policy:</span></span> ![オンに切り替え](../../media/scc-toggle-on.png)

<span data-ttu-id="c4d1c-255">既定の送信スパム ポリシーを無効にできない。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-255">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="c4d1c-256">カスタム送信スパム ポリシーの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="c4d1c-256">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="c4d1c-257">既定では、送信スパム ポリシーには、作成された順序に基づく優先度が与えられる (新しいポリシーは、古いポリシーよりも優先度が低くなります)。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-257">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="c4d1c-258">優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-258">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="c4d1c-259">2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-259">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="c4d1c-260">カスタム送信スパム ポリシーは、処理された順序で表示されます (最初のポリシーの **優先度** の値は 0 です)。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-260">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="c4d1c-261">[送信スパム フィルター ポリシー  ] という名前の既定の送信スパムポリシーの優先度は [最低] で、変更は行えなくないます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-261">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="c4d1c-262">ポリシーの優先度を変更するには、リスト内で上下に移動させます (セキュリティ/コンプライアンス センター内で直接、**優先順位** 番号を変更することはできません)。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-262">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="c4d1c-263">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-263">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="c4d1c-264">[スパム **対策の設定] ページ** で、[種類] 列の値が[カスタム送信スパム ポリシー] のポリシー **を探します**。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-264">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="c4d1c-265">**[優先度]** 列の値に注目します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-265">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="c4d1c-266">優先度が最も高いカスタム送信スパム ポリシーの値は、下方向アイコン ![ ](../../media/ITPro-EAC-DownArrowIcon.png) **0 です**。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-266">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="c4d1c-267">優先度が最も低いカスタム送信スパム ポリシーの値は、上方向アイコン n (上矢印アイコン ![ ](../../media/ITPro-EAC-UpArrowIcon.png) 3 など) ![ ](../../media/ITPro-EAC-UpArrowIcon.png) **です**。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-267">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="c4d1c-268">3 つ以上のカスタム送信スパム ポリシーがある場合、優先度の最も高いポリシーと最も低い優先度のポリシーには、上矢印アイコンの下矢印アイコン n (たとえば、上方向アイコン下矢印アイコン ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png)  ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **2)** があります。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-268">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="c4d1c-269">上</span><span class="sxs-lookup"><span data-stu-id="c4d1c-269">Click</span></span> ![矢印アイコン](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="c4d1c-271">または</span><span class="sxs-lookup"><span data-stu-id="c4d1c-271">or</span></span> ![下矢印アイコンをクリックして](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="c4d1c-273">をクリックして、優先度リストでカスタム送信スパム ポリシーを上下に移動します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-273">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="c4d1c-274">セキュリティ コンプライアンス センターを&送信スパム ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="c4d1c-274">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="c4d1c-275">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-275">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="c4d1c-276">[スパム **対策の設定**] ページで、[展開] アイコンをクリックして、削除するカスタム ポリシーを展開します ([種類] 列は [カスタム送信スパム ポリシー] ![ ](../../media/scc-expand-icon.png) **です**)。 </span><span class="sxs-lookup"><span data-stu-id="c4d1c-276">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="c4d1c-277">展開されたポリシー詳細で、**[ポリシーの削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-277">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="c4d1c-278">警告ダイアログが表示されたら、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-278">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="c4d1c-279">既定のポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-279">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="c4d1c-280">Exchange Online PowerShell またはスタンドアロン EOP PowerShell を使用して送信スパム ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="c4d1c-280">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

<span data-ttu-id="c4d1c-281">前述したように、送信スパム ポリシーは、送信スパム フィルター ポリシーと送信スパム フィルター ルールで構成されます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-281">As previously described, an outbound spam policy consists of an outbound spam filter policy and an outbound spam filter rule.</span></span>

<span data-ttu-id="c4d1c-282">Exchange Online PowerShell またはスタンドアロン EOP PowerShell では、送信スパム フィルター ポリシーと送信スパム フィルター ルールの違いが明らかです。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-282">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="c4d1c-283">**\* -HostedOutboundSpamFilterPolicy** コマンドレットを使用して送信スパム フィルター ポリシーを管理し **\* 、-HostedOutboundSpamFilterRule** コマンドレットを使用して送信スパム フィルター ルールを管理します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-283">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="c4d1c-284">PowerShell では、最初に送信スパム フィルター ポリシーを作成してから、ルールが適用されるポリシーを識別する送信スパム フィルター ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-284">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="c4d1c-285">PowerShell では、送信スパム フィルター ポリシーの設定と送信スパム フィルター ルールを個別に変更します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-285">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>
- <span data-ttu-id="c4d1c-286">PowerShell から送信スパム フィルター ポリシーを削除すると、対応する送信スパム フィルター ルールは自動的には削除されません。その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-286">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="c4d1c-287">PowerShell を使用して送信スパム ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="c4d1c-287">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="c4d1c-288">PowerShell で送信スパム ポリシーを作成するには、次の 2 つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-288">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="c4d1c-289">送信スパム フィルター ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-289">Create the outbound spam filter policy.</span></span>
2. <span data-ttu-id="c4d1c-290">ルールが適用される送信スパム フィルター ポリシーを指定する送信スパム フィルター ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-290">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="c4d1c-291">**注**:</span><span class="sxs-lookup"><span data-stu-id="c4d1c-291">**Notes**:</span></span>

- <span data-ttu-id="c4d1c-292">新しい送信スパム フィルター ルールを作成し、関連付けされていない既存の送信スパム フィルター ポリシーを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-292">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="c4d1c-293">送信スパム フィルター ルールを複数の送信スパム フィルター ポリシーに関連付けできない。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-293">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="c4d1c-294">ポリシーを作成するまで、セキュリティ & コンプライアンス センターで使用できない PowerShell の新しい送信スパム フィルター ポリシーに対して、次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-294">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="c4d1c-295">無効として新しいポリシーを作成 _します_ `$false` **(New-HostedOutboundSpamFilterRule コマンドレットで有効** )。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-295">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
  - <span data-ttu-id="c4d1c-296"> _\<Number\>_ **New-HostedOutboundSpamFilterRule** コマンドレットの作成時のポリシーの優先度 (優先度) を設定します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-296">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="c4d1c-297">PowerShell で作成した新しい送信スパム フィルター ポリシーは、ポリシーをスパム フィルター ルールに割り当てるまで、セキュリティ & コンプライアンス センターには表示されません。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-297">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="c4d1c-298">手順 1: PowerShell を使用して送信スパム フィルター ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="c4d1c-298">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="c4d1c-299">送信スパム フィルター ポリシーを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-299">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="c4d1c-300">この例では、Contoso Executives という名前の新しい送信スパム フィルター ポリシーを次の設定で作成します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-300">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="c4d1c-301">受信者レートの制限は、既定値の小さい値に制限されます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-301">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="c4d1c-302">詳細については [、「Sending limits across Microsoft 365 options」を参照してください](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-302">For more information, see [Sending limits across Microsoft 365 options](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="c4d1c-303">制限の 1 つに達すると、ユーザーはメッセージを送信できません。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-303">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="c4d1c-304">構文とパラメーターの詳細については [、「New-HostedOutboundSpamFilterPolicy」を参照してください](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-304">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="c4d1c-305">手順 2: PowerShell を使用して送信スパム フィルター ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="c4d1c-305">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="c4d1c-306">送信スパム フィルター ルールを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-306">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="c4d1c-307">この例では、Contoso Executives という名前の新しい送信スパム フィルター ルールを次の設定で作成します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-307">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="c4d1c-308">Contoso Executives という名前の送信スパム フィルター ポリシーがルールに関連付けられている。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-308">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>
- <span data-ttu-id="c4d1c-309">ルールは Contoso Executives Group という名前のグループのメンバーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-309">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -FromMemberOf "Contoso Executives Group"
```

<span data-ttu-id="c4d1c-310">構文とパラメーターの詳細については [、「New-HostedOutboundSpamFilterRule」を参照してください](/powershell/module/exchange/new-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-310">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="c4d1c-311">PowerShell を使用して送信スパム フィルター ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="c4d1c-311">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="c4d1c-312">すべての送信スパム フィルター ポリシーの概要リストを取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-312">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="c4d1c-313">特定の送信スパム フィルター ポリシーに関する詳細情報を取得するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-313">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="c4d1c-314">この例では、Executives という名前の送信スパム フィルター ポリシーのすべてのプロパティ値を返します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-314">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="c4d1c-315">構文とパラメーターの詳細については [、「Get-HostedOutboundSpamFilterPolicy」を参照してください](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-315">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="c4d1c-316">PowerShell を使用して送信スパム フィルター ルールを表示する</span><span class="sxs-lookup"><span data-stu-id="c4d1c-316">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="c4d1c-317">既存の送信スパム フィルター ルールを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-317">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

<span data-ttu-id="c4d1c-318">すべての送信スパム フィルター ルールの概要リストを取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-318">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="c4d1c-319">ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-319">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="c4d1c-320">特定の送信スパム フィルター ルールに関する詳細情報を取得するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-320">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="c4d1c-321">この例では、Contoso Executives という名前の送信スパム フィルター ルールのすべてのプロパティ値を返します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-321">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="c4d1c-322">構文とパラメーターの詳細については [、「Get-HostedOutboundSpamFilterRule」を参照してください](/powershell/module/exchange/get-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-322">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="c4d1c-323">PowerShell を使用して送信スパム フィルター ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="c4d1c-323">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="c4d1c-324">この記事の「手順 [1: PowerShell](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) を使用して送信スパム フィルター ポリシーを作成する」で説明したように、PowerShell でマルウェア フィルター ポリシーを変更する場合と同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-324">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="c4d1c-325">送信スパム フィルター ポリシーの名前を変更することはできません **(Set-HostedOutboundSpamFilterPolicy** コマンドレットには _Name_ パラメーターはありません)。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-325">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="c4d1c-326">セキュリティ コンプライアンス センターで送信スパム ポリシーの名前を変更&、送信スパム フィルター ルールの名前を変更する _のみです_。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-326">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="c4d1c-327">送信スパム フィルター ポリシーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-327">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="c4d1c-328">構文とパラメーターの詳細については [、「Set-HostedOutboundSpamFilterPolicy」を参照してください](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-328">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="c4d1c-329">PowerShell を使用して送信スパム フィルター ルールを変更する</span><span class="sxs-lookup"><span data-stu-id="c4d1c-329">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="c4d1c-330">PowerShell で送信スパム フィルター ルールを変更するときに使用できない唯一の設定は、無効なルールを作成できる _Enabled_ パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-330">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="c4d1c-331">既存の送信スパム フィルター ルールを有効または無効にするには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-331">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="c4d1c-332">それ以外の場合は、PowerShell で送信スパム フィルター ルールを変更するときに追加の設定を使用できません。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-332">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="c4d1c-333">この記事の「手順 [2: PowerShell](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) を使用して送信スパム フィルター ルールを作成する」セクションで説明したように、ルールを作成する場合も同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-333">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this article.</span></span>

<span data-ttu-id="c4d1c-334">送信スパム フィルター ルールを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-334">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="c4d1c-335">構文とパラメーターの詳細については [、「Set-HostedOutboundSpamFilterRule」を参照してください](/powershell/module/exchange/set-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-335">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="c4d1c-336">PowerShell を使用して送信スパム フィルター ルールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="c4d1c-336">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="c4d1c-337">PowerShell で送信スパム フィルター ルールを有効または無効にすると、送信スパム ポリシー全体 (送信スパム フィルター ルールと割り当てられた送信スパム フィルター ポリシー) が有効または無効となります。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-337">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="c4d1c-338">既定の送信スパム ポリシーを有効または無効にできない (常にすべての受信者に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-338">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="c4d1c-339">PowerShell で送信スパム フィルター ルールを有効または無効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-339">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="c4d1c-340">この例では、マーケティング部門という名前の送信スパム フィルター ルールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-340">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="c4d1c-341">この例では、同じルールを有効化します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-341">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="c4d1c-342">構文とパラメーターの詳細については [、「Enable-HostedOutboundSpamFilterRule」](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) および [「Disable-HostedOutboundSpamFilterRule」を参照してください](/powershell/module/exchange/disable-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-342">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="c4d1c-343">PowerShell を使用して送信スパム フィルター ルールの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="c4d1c-343">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="c4d1c-344">ルールに設定できる優先度の最高値値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-344">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="c4d1c-345">設定できる最低値はルールの数に依存します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-345">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="c4d1c-346">たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-346">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="c4d1c-347">既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-347">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="c4d1c-348">たとえば、カスタム ルールが 5 つあって (優先度 0 から 4)、1 つのルールの優先度を 2 に変更した場合には、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-348">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="c4d1c-349">PowerShell で送信スパム フィルター ルールの優先度を設定するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-349">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="c4d1c-p141">この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-p141">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - <span data-ttu-id="c4d1c-352">新しいルールを作成するときに優先度を設定するには、代わりに **New-HostedOutboundSpamFilterRule** コマンドレットの Priority パラメーターを使用します。 </span><span class="sxs-lookup"><span data-stu-id="c4d1c-352">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
>
> - <span data-ttu-id="c4d1c-353">送信の既定のスパム フィルター ポリシーには、対応するスパム フィルター ルールが含めず、常に変更できない優先度の値が **最低です**。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-353">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="c4d1c-354">PowerShell を使用して送信スパム フィルター ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="c4d1c-354">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="c4d1c-355">PowerShell を使用して送信スパム フィルター ポリシーを削除すると、対応する送信スパム フィルター ルールは削除されません。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-355">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="c4d1c-356">PowerShell で送信スパム フィルター ポリシーを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-356">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="c4d1c-357">この例では、Marketing Department という名前の送信スパム フィルター ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-357">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="c4d1c-358">構文とパラメーターの詳細については [、「Remove-HostedOutboundSpamFilterPolicy」を参照してください](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-358">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="c4d1c-359">PowerShell を使用して送信スパム フィルター ルールを削除する</span><span class="sxs-lookup"><span data-stu-id="c4d1c-359">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="c4d1c-360">PowerShell を使用して送信スパム フィルター ルールを削除すると、対応する送信スパム フィルター ポリシーは削除されません。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-360">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="c4d1c-361">PowerShell で送信スパム フィルター ルールを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-361">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="c4d1c-362">この例では、Marketing Department という名前の送信スパム フィルター ルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-362">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="c4d1c-363">構文とパラメーターの詳細については [、「Remove-HostedOutboundSpamFilterRule」を参照してください](/powershell/module/exchange/remove-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="c4d1c-363">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="c4d1c-364">詳細情報</span><span class="sxs-lookup"><span data-stu-id="c4d1c-364">For more information</span></span>

[<span data-ttu-id="c4d1c-365">制限されたユーザー ポータルからブロックされたユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="c4d1c-365">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="c4d1c-366">送信メッセージにおける危険度の高い配信プール</span><span class="sxs-lookup"><span data-stu-id="c4d1c-366">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="c4d1c-367">スパム対策保護に関してよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="c4d1c-367">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.yml)

[<span data-ttu-id="c4d1c-368">自動転送済みメッセージレポート</span><span class="sxs-lookup"><span data-stu-id="c4d1c-368">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)