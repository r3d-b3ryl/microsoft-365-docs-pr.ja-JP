---
title: 送信スパム フィルターの構成
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) の送信スパムポリシーを表示、作成、変更、および削除する方法を学習できます。
ms.openlocfilehash: e035fe26cea0fcd1f3051f7464722ae1c7a3b56f
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352001"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="d7679-103">EOP で送信スパムフィルターを構成する</span><span class="sxs-lookup"><span data-stu-id="d7679-103">Configure outbound spam filtering in EOP</span></span>

<span data-ttu-id="d7679-104">Exchange online またはスタンドアロンの Exchange Online Protection (EOP) 組織にメールボックスがあり、Exchange Online メールボックスを使用していない場合、EOP を介して送信される送信電子メールメッセージは、スパムや通常の送信アクティビティに対して自動的にチェックされます。365</span><span class="sxs-lookup"><span data-stu-id="d7679-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="d7679-105">組織内のユーザーからの送信スパムは、通常、侵害されたアカウントを示しています。</span><span class="sxs-lookup"><span data-stu-id="d7679-105">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="d7679-106">疑わしい送信メッセージは、スパムの信頼レベルまたは SCL に関係なく、スパムとしてマークされ、[高リスクの配信プール](high-risk-delivery-pool-for-outbound-messages.md)を介してルーティングされます。これは、サービスの評価を保護するため (つまり、Microsoft 365 ソースの電子メールサーバーを IP 禁止一覧に保持する) します。</span><span class="sxs-lookup"><span data-stu-id="d7679-106">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="d7679-107">管理者は、疑わしい送信電子メールアクティビティとブロックされたユーザーに対して通知[ポリシー](../../compliance/alert-policies.md)を使用して自動的に通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d7679-107">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="d7679-108">EOP では、スパムに対する組織の全体的な防衛の一環として、送信スパムポリシーを使用しています。</span><span class="sxs-lookup"><span data-stu-id="d7679-108">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="d7679-109">詳細については、「[スパム対策保護](anti-spam-protection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7679-109">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="d7679-110">管理者は、既定の送信スパムポリシーを表示、編集、および構成することはできますが、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="d7679-110">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="d7679-111">よりきめ細かく制御する場合は、組織内の特定のユーザー、グループ、またはドメインに適用するカスタムの送信スパムポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="d7679-111">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="d7679-112">カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (実行順序) を変更できます。</span><span class="sxs-lookup"><span data-stu-id="d7679-112">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="d7679-113">送信スパムポリシーは、セキュリティ & コンプライアンスセンターまたは PowerShell (exchange online のメールボックスを使用する Microsoft 365 組織の場合は exchange online PowerShell、exchange Online メールボックスがない組織の場合はスタンドアロン EOP PowerShell) で構成できます。</span><span class="sxs-lookup"><span data-stu-id="d7679-113">You can configure outbound spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="outbound-spam-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="d7679-114">セキュリティ & コンプライアンスセンター vs PowerShell の送信スパムポリシー</span><span class="sxs-lookup"><span data-stu-id="d7679-114">Outbound spam policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="d7679-115">EOP の送信スパムポリシーの基本的な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d7679-115">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="d7679-116">**送信スパムフィルターポリシー**: 送信スパムフィルター verdicts のアクションと通知オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="d7679-116">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>

- <span data-ttu-id="d7679-117">**送信スパムフィルタールール**: 送信スパムフィルターポリシーの優先順位と受信者フィルター (ポリシーが適用されるユーザー) を指定します。</span><span class="sxs-lookup"><span data-stu-id="d7679-117">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="d7679-118">セキュリティ & コンプライアンスセンターで送信スパムポリシーを管理する場合、この2つの要素の違いは明白ではありません。</span><span class="sxs-lookup"><span data-stu-id="d7679-118">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="d7679-119">セキュリティ & コンプライアンスセンターで送信スパムポリシーを作成すると、実際には、両方に同じ名前を使用して、送信スパムフィルタールールと関連する送信スパムフィルターポリシーを同時に作成しています。</span><span class="sxs-lookup"><span data-stu-id="d7679-119">When you create an outbound spam policy in the Security & Compliance Center, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="d7679-120">セキュリティ & コンプライアンスセンターで送信スパムポリシーを変更すると、名前、優先度、有効または無効に関連する設定、および受信者フィルターによって送信スパムフィルタールールが変更されます。</span><span class="sxs-lookup"><span data-stu-id="d7679-120">When you modify an outbound spam policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="d7679-121">他のすべての設定は、関連する送信スパムフィルターポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="d7679-121">All other settings modify the associated outbound spam filter policy.</span></span>

- <span data-ttu-id="d7679-122">送信スパムポリシーをセキュリティ & コンプライアンスセンターから削除すると、送信スパムフィルタールールとそれに関連付けられた送信スパムフィルターポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="d7679-122">When you remove an outbound spam policy from the Security & Compliance Center, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="d7679-123">Exchange Online PowerShell またはスタンドアロン EOP PowerShell では、送信スパムフィルターポリシーと送信スパムフィルタールールの違いが明らかです。</span><span class="sxs-lookup"><span data-stu-id="d7679-123">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="d7679-124">送信スパムフィルターポリシーを管理するには、 \*\* \* -HostedOutboundSpamFilterPolicy**コマンドレットを使用して、 \*\* \* -HostedOutboundSpamFilterRule**コマンドレットを使用して送信スパムフィルタールールを管理します。</span><span class="sxs-lookup"><span data-stu-id="d7679-124">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="d7679-125">PowerShell では、送信スパムフィルターポリシーを最初に作成してから、ルールが適用されるポリシーを識別する送信スパムフィルタールールを作成します。</span><span class="sxs-lookup"><span data-stu-id="d7679-125">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="d7679-126">PowerShell では、送信スパムフィルターポリシーと送信スパムフィルタールールの設定を個別に変更します。</span><span class="sxs-lookup"><span data-stu-id="d7679-126">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>

- <span data-ttu-id="d7679-127">送信スパムフィルターポリシーを PowerShell から削除すると、対応する送信スパムフィルタールールは自動的には削除されません。また、その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="d7679-127">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-outbound-spam-policy"></a><span data-ttu-id="d7679-128">既定の送信スパムポリシー</span><span class="sxs-lookup"><span data-stu-id="d7679-128">Default outbound spam policy</span></span>

<span data-ttu-id="d7679-129">すべての組織には、Default という名前の組み込みの送信スパムポリシーがあります。これらのプロパティは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d7679-129">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="d7679-130">Default という名前の送信スパムフィルターポリシーは、ポリシーに関連付けられた送信スパムフィルタールール (受信者フィルター) がない場合でも、組織内のすべての受信者に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d7679-130">The outbound spam filter policy named Default is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="d7679-131">Default という名前のポリシーにはカスタムの優先順位の値 **Lowest** が設定されており、変更することはできません (このポリシーは常に最後に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="d7679-131">The policy named Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="d7679-132">作成するどのカスタム ポリシーも、Default という名前のポリシーより高い優先順位を持ちます。</span><span class="sxs-lookup"><span data-stu-id="d7679-132">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>

- <span data-ttu-id="d7679-133">Default という名前のポリシーは既定のポリシー (**IsDefault** のプロパティが `True` の値になっている) であり、既定のポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="d7679-133">The policy named Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="d7679-134">送信スパムフィルター処理の有効性を高めるために、特定のユーザーまたはユーザーグループに適用される厳密な設定を使用して、カスタムの送信スパムポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="d7679-134">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d7679-135">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="d7679-135">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d7679-136"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="d7679-136">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="d7679-137">**[スパム対策の設定]** ページに直接移動するには、<https://protection.office.com/antispam> を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7679-137">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="d7679-138">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7679-138">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="d7679-139">スタンドアロンの EOP PowerShell に接続するには、「 [Exchange Online Protection の powershell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7679-139">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="d7679-140">これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7679-140">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="d7679-141">送信スパムポリシーを追加、変更、および削除するには、**組織の管理**または**セキュリティ管理者**の役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7679-141">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="d7679-142">送信スパムポリシーに対する読み取り専用アクセスでは、**セキュリティリーダー**役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7679-142">For read-only access to outbound spam policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="d7679-143">セキュリティ/コンプライアンス センターの役割グループの詳細については、「[セキュリティ/コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d7679-143">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="d7679-144">送信スパムポリシーの推奨設定については、「 [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7679-144">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="d7679-145">**電子メール送信の制限**が設定されている既定の[警告ポリシー](../../compliance/alert-policies.md) 、**疑わしい電子メール送信パターンが検出さ**れたこと、および電子メールが送信**Global admins**を拒否したことによって、電子メール通知が通常の送信電子メールアクティビティやブロックされたユーザーについて**は、送信**スパムによる**もの**であることを示します。</span><span class="sxs-lookup"><span data-stu-id="d7679-145">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="d7679-146">詳細については、「制限され[たユーザーの通知設定を確認する](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7679-146">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="d7679-147">送信スパムポリシーの通知オプションではなく、これらのアラートポリシーを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d7679-147">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="d7679-148">セキュリティ & コンプライアンスセンターを使用して送信スパムポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="d7679-148">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="d7679-149">セキュリティ & コンプライアンスセンターでカスタムの送信スパムポリシーを作成すると、両方に同じ名前を使用して、スパムフィルタールールと関連するスパムフィルターポリシーが同時に作成されます。</span><span class="sxs-lookup"><span data-stu-id="d7679-149">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="d7679-150">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="d7679-150">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="d7679-151">[**スパム対策設定**] ページで、[**送信ポリシーの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7679-151">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="d7679-152">[**送信スパムフィルターポリシー** ] が表示されたら、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="d7679-152">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="d7679-153">**[名前]**: わかりやすい一意のポリシー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="d7679-153">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="d7679-154">**[説明]**: ポリシーについての説明を入力します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="d7679-154">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="d7679-155">オプション[**通知**] セクションを展開して、疑わしい送信電子メールメッセージのコピーと通知を受信する必要がある追加のユーザーを構成します。</span><span class="sxs-lookup"><span data-stu-id="d7679-155">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="d7679-156">**疑わしい送信電子メールメッセージのコピーを特定のユーザーに送信**する: この設定を行うと、指定されたユーザーが Bcc 受信者として疑わしい送信メッセージに追加されます。</span><span class="sxs-lookup"><span data-stu-id="d7679-156">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span>

     > [!NOTE]
     > <span data-ttu-id="d7679-157">この設定は、既定の送信スパムポリシーでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="d7679-157">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="d7679-158">作成したカスタムの送信スパムポリシーでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="d7679-158">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="d7679-159">この設定を有効にするには:</span><span class="sxs-lookup"><span data-stu-id="d7679-159">To enable this setting:</span></span>

     <span data-ttu-id="d7679-160">a.</span><span class="sxs-lookup"><span data-stu-id="d7679-160">a.</span></span> <span data-ttu-id="d7679-161">チェックボックスをオンにして、設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d7679-161">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="d7679-162">b.</span><span class="sxs-lookup"><span data-stu-id="d7679-162">b.</span></span> <span data-ttu-id="d7679-163">[**ユーザーの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7679-163">Click **Add people**.</span></span> <span data-ttu-id="d7679-164">[**受信者の追加または削除**] ポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d7679-164">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="d7679-165">c.</span><span class="sxs-lookup"><span data-stu-id="d7679-165">c.</span></span> <span data-ttu-id="d7679-166">送信者の電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="d7679-166">Enter the sender's email address.</span></span> <span data-ttu-id="d7679-167">複数の電子メールアドレスをセミコロンで区切って指定できます (;)または1行に1人の受信者。</span><span class="sxs-lookup"><span data-stu-id="d7679-167">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="d7679-168">d.</span><span class="sxs-lookup"><span data-stu-id="d7679-168">d.</span></span> <span data-ttu-id="d7679-169">Click</span><span class="sxs-lookup"><span data-stu-id="d7679-169">Click</span></span> ![[追加] アイコン](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="d7679-171">受信者を追加します。</span><span class="sxs-lookup"><span data-stu-id="d7679-171">to add the recipients.</span></span>

        <span data-ttu-id="d7679-172">必要な回数だけこれらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d7679-172">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="d7679-173">追加した受信者が、フライアウトの [**受信者リスト**] セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d7679-173">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="d7679-174">受信者を削除するには、[ ![ 削除] ボタンをクリックし ](../../media/scc-remove-icon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="d7679-174">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="d7679-175">e. </span><span class="sxs-lookup"><span data-stu-id="d7679-175">e.</span></span> <span data-ttu-id="d7679-176">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7679-176">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="d7679-177">この設定を無効にするには、このチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="d7679-177">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="d7679-178">送信**スパムの送信によって送信者がブロックされた場合に、特定のユーザーに通知し**ます。</span><span class="sxs-lookup"><span data-stu-id="d7679-178">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!NOTE]
     > <span data-ttu-id="d7679-179">ユーザーが [**受信者の制限**] セクションの制限を超えたためにユーザーがブロックされた**Global admins**場合は、ユーザーによって [**送信メールが電子メール**によって制限されました] という名前の既定の[警告ポリシー](../../compliance/alert-policies.md)が、既に**tenantadmins**グループのメンバーに電子メール通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="d7679-179">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="d7679-180">送信スパムポリシーのこの設定ではなく、通知ポリシーを使用して、管理者およびその他のユーザーに通知することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d7679-180">We recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users.</span></span> <span data-ttu-id="d7679-181">手順については、「制限され[たユーザーの通知設定を確認する](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7679-181">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <br/><br/> <span data-ttu-id="d7679-182">この設定は、既定の送信スパムポリシーでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="d7679-182">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="d7679-183">作成したカスタムの送信スパムポリシーでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="d7679-183">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="d7679-184">この設定を有効にするには:</span><span class="sxs-lookup"><span data-stu-id="d7679-184">To enable this setting:</span></span>

     <span data-ttu-id="d7679-185">a.</span><span class="sxs-lookup"><span data-stu-id="d7679-185">a.</span></span> <span data-ttu-id="d7679-186">チェックボックスをオンにして、設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d7679-186">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="d7679-187">b.</span><span class="sxs-lookup"><span data-stu-id="d7679-187">b.</span></span> <span data-ttu-id="d7679-188">[**ユーザーの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7679-188">Click **Add people**.</span></span> <span data-ttu-id="d7679-189">[**受信者の追加または削除**] ポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d7679-189">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="d7679-190">c.</span><span class="sxs-lookup"><span data-stu-id="d7679-190">c.</span></span> <span data-ttu-id="d7679-191">送信者の電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="d7679-191">Enter the sender's email address.</span></span> <span data-ttu-id="d7679-192">複数の電子メールアドレスをセミコロンで区切って指定できます (;)または1行に1人の受信者。</span><span class="sxs-lookup"><span data-stu-id="d7679-192">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="d7679-193">d.</span><span class="sxs-lookup"><span data-stu-id="d7679-193">d.</span></span> <span data-ttu-id="d7679-194">Click</span><span class="sxs-lookup"><span data-stu-id="d7679-194">Click</span></span> ![[追加] アイコン](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="d7679-196">受信者を追加します。</span><span class="sxs-lookup"><span data-stu-id="d7679-196">to add the recipients.</span></span>

        <span data-ttu-id="d7679-197">必要な回数だけこれらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d7679-197">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="d7679-198">追加した受信者が、フライアウトの [**受信者リスト**] セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d7679-198">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="d7679-199">受信者を削除するには、[ ![ 削除] ボタンをクリックし ](../../media/scc-remove-icon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="d7679-199">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="d7679-200">e. </span><span class="sxs-lookup"><span data-stu-id="d7679-200">e.</span></span> <span data-ttu-id="d7679-201">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7679-201">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="d7679-202">この設定を無効にするには、このチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="d7679-202">To disable this setting, clear the check box.</span></span>

5. <span data-ttu-id="d7679-203">オプション[**受信者の制限**] セクションを展開して、疑わしい送信電子メールメッセージの制限およびアクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="d7679-203">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="d7679-204">これらの設定は、クラウドベースのメールボックスにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="d7679-204">These settings are only applicable to cloud-based mailboxes.</span></span>

   - <span data-ttu-id="d7679-205">**ユーザーあたりの最大受信者数**</span><span class="sxs-lookup"><span data-stu-id="d7679-205">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="d7679-206">有効な値は、0 ~ 1万です。</span><span class="sxs-lookup"><span data-stu-id="d7679-206">A valid value is 0 to 10000.</span></span> <span data-ttu-id="d7679-207">既定値は0です。これは、サービスの既定値が使用されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="d7679-207">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="d7679-208">詳細については、「 [Microsoft 365 のオプション全体での送信制限](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7679-208">For more information, see [Sending limits across Microsoft 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

     - <span data-ttu-id="d7679-209">**外部の時間**単位の制限: 1 時間あたりの外部受信者の最大数。</span><span class="sxs-lookup"><span data-stu-id="d7679-209">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="d7679-210">[内部最大時間**制限**数: 1 時間あたりの内部受信者の最大数。</span><span class="sxs-lookup"><span data-stu-id="d7679-210">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="d7679-211">**Daily limit**: 1 日あたりの受信者の最大合計数。</span><span class="sxs-lookup"><span data-stu-id="d7679-211">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="d7679-212">**ユーザーが上記の制限を超えた場合の対処**:**受信者の制限**のいずれかを超えた場合に実行するアクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="d7679-212">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="d7679-213">すべての操作について、ユーザーが**電子メール**通知ポリシーを送信することを制限しています (これで、送信スパムポリシーで送信スパムの設定**を送信するために送信者がブロックされている場合**は、特定のユーザーに対して特定のユーザーに指定された受信者が電子メール通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="d7679-213">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="d7679-214">**ユーザーが次の日までメールを送信**できないように制限します。これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="d7679-214">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="d7679-215">電子メール通知が送信され、ユーザーは UTC 時間に基づいて、次の日までメッセージを送信できなくなります。</span><span class="sxs-lookup"><span data-stu-id="d7679-215">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="d7679-216">管理者がこのブロックを上書きする方法はありません。</span><span class="sxs-lookup"><span data-stu-id="d7679-216">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="d7679-217">[**ユーザーが電子メールを送信**できないようにする] という名前のアクティビティアラートは、管理者に電子メールを介して通知を送信します ([通知の**表示**] ページ)。</span><span class="sxs-lookup"><span data-stu-id="d7679-217">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="d7679-218">ポリシーの送信スパム設定の**送信によって送信者がブロックされた場合**、[特定のユーザーを通知する] で指定されたすべての受信者にも通知されます。</span><span class="sxs-lookup"><span data-stu-id="d7679-218">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="d7679-219">このユーザーは、UTC 時間に基づいて、次の日まで、それ以上のメッセージを送信できなくなります。</span><span class="sxs-lookup"><span data-stu-id="d7679-219">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="d7679-220">管理者がこのブロックを上書きする方法はありません。</span><span class="sxs-lookup"><span data-stu-id="d7679-220">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="d7679-221">**ユーザーがメールを送信する**のを制限する: 電子メール通知が送信され、ユーザーはセキュリティ & コンプライアンスセンターの\*\* <https://sip.protection.office.com/restrictedusers> [制限付きユーザー]\*\* ポータルに追加され、ユーザーは管理者によって**制限付きユーザー**ポータルから削除されるまで電子メールを送信できません。管理者がリストからユーザーを削除した後は、その日に対してユーザーが再度制限されることはありません。</span><span class="sxs-lookup"><span data-stu-id="d7679-221">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="d7679-222">手順については、「[迷惑メールの送信後に制限付きユーザーポータルからユーザーを削除する](removing-user-from-restricted-users-portal-after-spam.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7679-222">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="d7679-223">**アクションなし、通知のみ**: 電子メール通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="d7679-223">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="d7679-224">要する[**適用先**] セクションを展開して、ポリシーが適用される内部送信者を特定します。</span><span class="sxs-lookup"><span data-stu-id="d7679-224">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="d7679-225">各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d7679-225">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="d7679-226">同じ条件または例外の複数の値を使用するか、ロジック (たとえば、 _ \< sender1 \> _または_ \< sender2 \> _) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7679-226">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="d7679-227">さまざまな条件や例外、およびロジック ( _ \< sender1 \> _ 、 _ \< グループ \> 1 のメンバー_など) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7679-227">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="d7679-228">使用可能なすべての条件を表示するには、**[条件の追加]** を 3 回クリックするのが最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="d7679-228">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="d7679-229">構成しない条件を削除するには、![[削除] ボタン](../../media/scc-remove-icon.png)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7679-229">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="d7679-230">**送信者ドメイン**: 構成されている1つ以上の承認済みドメインのうち、組織内の送信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="d7679-230">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in the organization.</span></span> <span data-ttu-id="d7679-231">**[タグの追加]** ボックスをクリックして、ドメインを表示および選択します。</span><span class="sxs-lookup"><span data-stu-id="d7679-231">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="d7679-232">複数のドメインが利用可能な場合は、**[タグの追加]** ボックスをもう一度クリックして、追加のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="d7679-232">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="d7679-233">**Sender is**: 組織内の1人または複数のユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="d7679-233">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="d7679-234">**[タグの追加]** をクリックして、リストをフィルター処理するための入力を始めます。</span><span class="sxs-lookup"><span data-stu-id="d7679-234">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="d7679-235">[**タグの追加**] ボックスをもう一度クリックして、追加の送信者を選択します。</span><span class="sxs-lookup"><span data-stu-id="d7679-235">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="d7679-236">**送信者が次のメンバーの場合**: 組織内の1つまたは複数のグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="d7679-236">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="d7679-237">**[タグの追加]** をクリックして、リストをフィルター処理するための入力を始めます。</span><span class="sxs-lookup"><span data-stu-id="d7679-237">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="d7679-238">[**タグの追加**] ボックスをもう一度クリックして、追加の送信者を選択します。</span><span class="sxs-lookup"><span data-stu-id="d7679-238">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="d7679-239">**次の場合を除く**: ルールの例外を追加するには、**[条件の追加]** を 3 回クリックして、使用可能なすべての例外を表示します。</span><span class="sxs-lookup"><span data-stu-id="d7679-239">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="d7679-240">設定と動作は、条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="d7679-240">The settings and behavior are exactly like the conditions.</span></span>

7. <span data-ttu-id="d7679-241">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7679-241">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="d7679-242">セキュリティ & コンプライアンスセンターを使用して、送信スパムポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="d7679-242">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="d7679-243">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="d7679-243">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="d7679-244">[**スパム対策設定**] ページで、[ ![ 展開] アイコンをクリックして、 ](../../media/scc-expand-icon.png) 送信スパムポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="d7679-244">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="d7679-245">**送信スパムフィルターポリシー**という名前の既定のポリシー。</span><span class="sxs-lookup"><span data-stu-id="d7679-245">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="d7679-246">作成したカスタムポリシーで、[**種類**] 列の値が [**カスタム送信スパムポリシー**] になっています。</span><span class="sxs-lookup"><span data-stu-id="d7679-246">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="d7679-247">ポリシー設定は、表示される拡張されたポリシーの詳細に表示されるか、[**ポリシーの編集**] をクリックできます。</span><span class="sxs-lookup"><span data-stu-id="d7679-247">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="d7679-248">セキュリティ & コンプライアンスセンターを使用して送信スパムポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="d7679-248">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="d7679-249">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="d7679-249">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="d7679-250">[**スパム対策設定**] ページで、[ ![ 展開] アイコンをクリックして、 ](../../media/scc-expand-icon.png) 送信スパムポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="d7679-250">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="d7679-251">**送信スパムフィルターポリシー**という名前の既定のポリシー。</span><span class="sxs-lookup"><span data-stu-id="d7679-251">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="d7679-252">作成したカスタムポリシーで、[**種類**] 列の値が [**カスタム送信スパムポリシー**] になっています。</span><span class="sxs-lookup"><span data-stu-id="d7679-252">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="d7679-253">**[ポリシーの編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7679-253">Click **Edit policy**.</span></span>

<span data-ttu-id="d7679-254">カスタムの送信スパムポリシーの場合、表示されるポップアップで使用可能な設定は、「[セキュリティ & コンプライアンスセンターを使用して送信スパムポリシーを作成する](#use-the-security--compliance-center-to-create-outbound-spam-policies)」セクションに記載されている設定と同じです。</span><span class="sxs-lookup"><span data-stu-id="d7679-254">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="d7679-255">"**送信スパムフィルターポリシー**" という名前の既定の送信スパムポリシーの場合、[**適用先**] セクションは利用できません (ポリシーはすべてのユーザーに適用されます)。また、ポリシーの名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="d7679-255">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="d7679-256">ポリシーを有効または無効にするには、ポリシーの優先順位を設定するか、またはエンドユーザーの検疫通知を構成します。後続の各セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d7679-256">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="d7679-257">送信スパムポリシーを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="d7679-257">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="d7679-258">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="d7679-258">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="d7679-259">[**スパム対策設定**] ページで、[ ![ 展開] アイコンをクリックして、作成した ](../../media/scc-expand-icon.png) カスタムポリシーを展開します ([**種類**] 列の値は、**カスタムの送信スパムポリシー**です)。</span><span class="sxs-lookup"><span data-stu-id="d7679-259">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="d7679-260">展開して表示されたポリシー詳細で、**[On]** 列の値をメモします。</span><span class="sxs-lookup"><span data-stu-id="d7679-260">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="d7679-261">ポリシーを無効にするには、左に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="d7679-261">Move the toggle to the left to disable the policy:</span></span> ![オフに切り替え](../../media/scc-toggle-off.png)

   <span data-ttu-id="d7679-263">ポリシーを有効にするには、右に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="d7679-263">Move the toggle to the right to enable the policy:</span></span> ![オンに切り替え](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="d7679-265">既定の送信スパムポリシーを無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d7679-265">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="d7679-266">カスタム送信スパムポリシーの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="d7679-266">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="d7679-267">既定では、送信スパムポリシーには、作成された順序に基づく優先度が与えられます (新しいポリシーは、以前のポリシーよりも優先度が低いです)。</span><span class="sxs-lookup"><span data-stu-id="d7679-267">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="d7679-268">優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。</span><span class="sxs-lookup"><span data-stu-id="d7679-268">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="d7679-269">2 つのポリシーが同じ優先度を持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="d7679-269">No two policies can have the same priority.</span></span>

<span data-ttu-id="d7679-270">カスタム送信スパムポリシーは、処理順に表示されます (最初のポリシーの**優先度**値は0です)。</span><span class="sxs-lookup"><span data-stu-id="d7679-270">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="d7679-271">"**送信スパムフィルターポリシー** " という名前の既定の送信スパムポリシーは、優先度の値が**低い**ので、これを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="d7679-271">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="d7679-272">ポリシーの優先度を変更するには、リスト内で上下に移動させます (セキュリティ/コンプライアンス センター内で直接、**優先順位**番号を変更することはできません)。</span><span class="sxs-lookup"><span data-stu-id="d7679-272">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="d7679-273">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="d7679-273">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="d7679-274">[**スパム対策設定**] ページで、[**種類**] 列の値が**カスタム送信スパムポリシー**であるポリシーを探します。</span><span class="sxs-lookup"><span data-stu-id="d7679-274">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="d7679-275">**[優先度]** 列の値に注目します。</span><span class="sxs-lookup"><span data-stu-id="d7679-275">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="d7679-276">優先度が最も高いカスタムの送信スパムポリシーには、値の ![ 下矢印アイコン ](../../media/ITPro-EAC-DownArrowIcon.png) **0**があります。</span><span class="sxs-lookup"><span data-stu-id="d7679-276">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="d7679-277">最も低い優先度を持つカスタムの送信スパムポリシーには、上矢印アイコン ![ ](../../media/ITPro-EAC-UpArrowIcon.png) **n** ( ![ 上矢印アイコン ](../../media/ITPro-EAC-UpArrowIcon.png) **3**) の値が設定されています。</span><span class="sxs-lookup"><span data-stu-id="d7679-277">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="d7679-278">ユーザー設定の送信スパムポリシーが3つ以上ある場合、最高の優先度と最も低い優先順位の間のポリシーは、上矢印アイコンの ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ 下矢印アイコン ](../../media/ITPro-EAC-DownArrowIcon.png) **n** (たとえば、 ![ 上矢印アイコンを下矢印アイコン 2) に設定し ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **2**ます。</span><span class="sxs-lookup"><span data-stu-id="d7679-278">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="d7679-279">上</span><span class="sxs-lookup"><span data-stu-id="d7679-279">Click</span></span> ![矢印アイコン](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="d7679-281">または</span><span class="sxs-lookup"><span data-stu-id="d7679-281">or</span></span> ![下矢印アイコンをクリックして](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="d7679-283">を押して、カスタムの送信スパムポリシーを優先順位一覧で上または下に移動します。</span><span class="sxs-lookup"><span data-stu-id="d7679-283">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="d7679-284">セキュリティ & コンプライアンスセンターを使用して送信スパムポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="d7679-284">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="d7679-285">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="d7679-285">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="d7679-286">[**スパム対策設定**] ページで、[ ![ 展開] アイコンをクリックして、 ](../../media/scc-expand-icon.png) 削除するカスタムポリシーを展開します ( **Type**列は**カスタム送信スパムポリシー**です)。</span><span class="sxs-lookup"><span data-stu-id="d7679-286">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="d7679-287">展開されたポリシー詳細で、**[ポリシーの削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7679-287">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="d7679-288">警告ダイアログが表示されたら、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7679-288">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="d7679-289">既定のポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="d7679-289">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="d7679-290">Exchange Online PowerShell またはスタンドアロンの EOP PowerShell を使用して送信スパムポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="d7679-290">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="d7679-291">PowerShell を使用して送信スパムポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="d7679-291">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="d7679-292">PowerShell で送信スパムポリシーを作成するには、2つの手順からなるプロセスがあります。</span><span class="sxs-lookup"><span data-stu-id="d7679-292">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="d7679-293">送信スパムフィルターポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d7679-293">Create the outbound spam filter policy.</span></span>

2. <span data-ttu-id="d7679-294">ルールを適用する送信スパムフィルターポリシーを指定する送信スパムフィルタールールを作成します。</span><span class="sxs-lookup"><span data-stu-id="d7679-294">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="d7679-295">**注**:</span><span class="sxs-lookup"><span data-stu-id="d7679-295">**Notes**:</span></span>

- <span data-ttu-id="d7679-296">新しい送信スパムフィルタールールを作成して、関連付けられていない既存の送信スパムフィルターポリシーをそれに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d7679-296">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="d7679-297">送信スパムフィルタールールは、複数の送信スパムフィルターポリシーに関連付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="d7679-297">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="d7679-298">ポリシーを作成するまでは、セキュリティ & コンプライアンスセンターでは使用できない PowerShell の新しい送信スパムフィルターポリシーに対して、次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="d7679-298">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="d7679-299">新しいポリシーを無効として_Enabled_作成し `$false` ます ( **HostedOutboundSpamFilterRule**コマンドレットでは有効)。</span><span class="sxs-lookup"><span data-stu-id="d7679-299">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

  - <span data-ttu-id="d7679-300">**HostedOutboundSpamFilterRule**コマンドレットで、作成中にポリシーの優先度を設定します (_優先度_ _ \< 番号 \> _)。</span><span class="sxs-lookup"><span data-stu-id="d7679-300">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="d7679-301">PowerShell で作成した新しい送信スパムフィルターポリシーは、そのポリシーをスパムフィルタールールに割り当てるまで、セキュリティ & コンプライアンスセンターに表示されません。</span><span class="sxs-lookup"><span data-stu-id="d7679-301">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="d7679-302">手順 1: PowerShell を使用して送信スパムフィルターポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="d7679-302">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="d7679-303">送信スパムフィルターポリシーを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7679-303">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="d7679-304">この例では、次の設定を使用して Contoso 重役という新しい送信スパムフィルターポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d7679-304">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="d7679-305">受信者数の制限は、既定値より小さい値に制限されます。</span><span class="sxs-lookup"><span data-stu-id="d7679-305">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="d7679-306">詳細については、「 [Microsoft 365 のオプション全体での送信制限](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7679-306">For more information, see [Sending limits across Microsoft 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="d7679-307">いずれかの制限に達すると、ユーザーはメッセージを送信できなくなります。</span><span class="sxs-lookup"><span data-stu-id="d7679-307">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="d7679-308">構文およびパラメーターの詳細については、「 [HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7679-308">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="d7679-309">手順 2: PowerShell を使用して送信スパムフィルタールールを作成する</span><span class="sxs-lookup"><span data-stu-id="d7679-309">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="d7679-310">送信スパムフィルタールールを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7679-310">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="d7679-311">この例では、次の設定を使用して Contoso 重役という新しい送信スパムフィルタールールを作成します。</span><span class="sxs-lookup"><span data-stu-id="d7679-311">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="d7679-312">Contoso エグゼクティブという名前の送信スパムフィルターポリシーがルールに関連付けられている。</span><span class="sxs-lookup"><span data-stu-id="d7679-312">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="d7679-313">ルールは Contoso Executives Group という名前のグループのメンバーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d7679-313">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="d7679-314">構文およびパラメーターの詳細については、「 [HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7679-314">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="d7679-315">PowerShell を使用して送信スパムフィルターポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="d7679-315">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="d7679-316">すべての送信スパムフィルターポリシーの要約リストを返すには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d7679-316">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="d7679-317">特定の送信スパムフィルターポリシーの詳細情報を戻すには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7679-317">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="d7679-318">この例では、重役という送信スパムフィルターポリシーのすべてのプロパティ値を返します。</span><span class="sxs-lookup"><span data-stu-id="d7679-318">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="d7679-319">構文およびパラメーターの詳細については、「 [HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7679-319">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="d7679-320">PowerShell を使用して送信スパムフィルタールールを表示する</span><span class="sxs-lookup"><span data-stu-id="d7679-320">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="d7679-321">既存の送信スパムフィルタールールを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7679-321">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="d7679-322">すべての送信スパムフィルタールールの要約リストを返すには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d7679-322">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="d7679-323">ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d7679-323">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="d7679-324">特定の送信スパムフィルタールールに関する詳細情報を戻すには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7679-324">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="d7679-325">この例では、Contoso 重役という送信スパムフィルタールールのすべてのプロパティ値を返します。</span><span class="sxs-lookup"><span data-stu-id="d7679-325">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="d7679-326">構文およびパラメーターの詳細については、「 [HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7679-326">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="d7679-327">PowerShell を使用して送信スパムフィルターポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="d7679-327">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="d7679-328">このトピックで前述した「[手順 1: powershell を使用して送信スパムフィルターポリシーを作成](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy)する」の説明に従って、ポリシーの作成時に powershell のマルウェアフィルターポリシーを変更する場合にも、同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d7679-328">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this topic.</span></span>

<span data-ttu-id="d7679-329">**注**: 送信スパムフィルターポリシーの名前を変更することはできません ( **HostedOutboundSpamFilterPolicy**コマンドレットに_Name_パラメーターがありません)。</span><span class="sxs-lookup"><span data-stu-id="d7679-329">**Note**: You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="d7679-330">セキュリティ & コンプライアンスセンターで送信スパムポリシーの名前を変更する場合は、送信スパムフィルター_ルール_の名前のみを変更しています。</span><span class="sxs-lookup"><span data-stu-id="d7679-330">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="d7679-331">送信スパムフィルターポリシーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7679-331">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="d7679-332">構文およびパラメーターの詳細については、「 [HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7679-332">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="d7679-333">PowerShell を使用して送信スパムフィルタールールを変更する</span><span class="sxs-lookup"><span data-stu-id="d7679-333">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="d7679-334">PowerShell で送信スパムフィルタールールを変更するときには使用できない唯一の設定は、無効にされたルールを作成できる_有効_なパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="d7679-334">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="d7679-335">既存の送信スパムフィルタールールを有効または無効にするには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7679-335">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="d7679-336">それ以外の場合は、PowerShell で送信スパムフィルタールールを変更するときに、追加の設定を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d7679-336">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="d7679-337">このトピックで前述した「[手順 2: PowerShell を使用して送信スパムフィルタールールを作成する](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule)」で説明されているように、ルールを作成する場合にも同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d7679-337">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="d7679-338">送信スパムフィルタールールを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7679-338">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="d7679-339">構文およびパラメーターの詳細については、「 [HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7679-339">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="d7679-340">PowerShell を使用して送信スパムフィルタールールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="d7679-340">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="d7679-341">PowerShell で送信スパムフィルタールールを有効または無効にすると、送信スパムポリシー全体 (送信スパムフィルタールールおよび割り当てられた送信スパムフィルターポリシー) が有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="d7679-341">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="d7679-342">既定の送信スパムポリシーを有効または無効にすることはできません (常にすべての受信者に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="d7679-342">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="d7679-343">PowerShell で送信スパムフィルタールールを有効または無効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7679-343">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="d7679-344">この例では、Marketing Department という名前の送信スパムフィルタールールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="d7679-344">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="d7679-345">この例では、同じルールを有効化します。</span><span class="sxs-lookup"><span data-stu-id="d7679-345">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="d7679-346">構文およびパラメーターの詳細については、「 [HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) 」および「 [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7679-346">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="d7679-347">PowerShell を使用して送信スパムフィルタールールの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="d7679-347">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="d7679-348">ルールに設定できる優先度の最高値値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="d7679-348">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="d7679-349">設定できる最低値はルールの数に依存します。</span><span class="sxs-lookup"><span data-stu-id="d7679-349">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="d7679-350">たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。</span><span class="sxs-lookup"><span data-stu-id="d7679-350">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="d7679-351">既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。</span><span class="sxs-lookup"><span data-stu-id="d7679-351">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="d7679-352">たとえば、カスタム ルールが 5 つあって (優先度 0 から 4)、1 つのルールの優先度を 2 に変更した場合には、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。</span><span class="sxs-lookup"><span data-stu-id="d7679-352">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="d7679-353">PowerShell で送信スパムフィルタールールの優先度を設定するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7679-353">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="d7679-p147">この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。</span><span class="sxs-lookup"><span data-stu-id="d7679-p147">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="d7679-356">**注**:</span><span class="sxs-lookup"><span data-stu-id="d7679-356">**Notes**:</span></span>

- <span data-ttu-id="d7679-357">新しいルールの作成時に優先度を設定するには、代わりに**HostedOutboundSpamFilterRule**コマンドレットで_priority_パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="d7679-357">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>

- <span data-ttu-id="d7679-358">既定の送信スパムフィルターポリシーには、対応するスパムフィルタールールがありません。また、常に、未設定の優先度の値が**最低**になっています。</span><span class="sxs-lookup"><span data-stu-id="d7679-358">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="d7679-359">PowerShell を使用して送信スパムフィルターポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="d7679-359">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="d7679-360">PowerShell を使用して送信スパムフィルターポリシーを削除しても、それに対応する送信スパムフィルタールールは削除されません。</span><span class="sxs-lookup"><span data-stu-id="d7679-360">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="d7679-361">PowerShell で送信スパムフィルターポリシーを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7679-361">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="d7679-362">この例では、Marketing Department という名前の送信スパムフィルターポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="d7679-362">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="d7679-363">構文およびパラメーターの詳細については、「 [HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7679-363">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="d7679-364">PowerShell を使用して送信スパムフィルタールールを削除する</span><span class="sxs-lookup"><span data-stu-id="d7679-364">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="d7679-365">PowerShell を使用して送信スパムフィルタールールを削除しても、対応する送信スパムフィルターポリシーは削除されません。</span><span class="sxs-lookup"><span data-stu-id="d7679-365">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="d7679-366">PowerShell で送信スパムフィルタールールを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7679-366">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="d7679-367">この例では、Marketing Department という名前の送信スパムフィルタールールを削除します。</span><span class="sxs-lookup"><span data-stu-id="d7679-367">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="d7679-368">構文およびパラメーターの詳細については、「 [HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7679-368">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="d7679-369">詳細情報</span><span class="sxs-lookup"><span data-stu-id="d7679-369">For more information</span></span>

[<span data-ttu-id="d7679-370">制限されたユーザー ポータルからブロックされたユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="d7679-370">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="d7679-371">送信メッセージにおける危険度の高い配信プール</span><span class="sxs-lookup"><span data-stu-id="d7679-371">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="d7679-372">スパム対策保護に関してよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="d7679-372">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
