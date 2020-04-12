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
description: 送信電子メールの送信にサービスを使用すると、送信スパムフィルターは常に有効になり、それによって、そのサービスと目的の受信者を使用して組織が保護されます。
ms.openlocfilehash: 3ac85776db5d990d46b858294acf8ef66c7f26bc
ms.sourcegitcommit: c876d58b34454f211b50ae5d06f193c1a1e5c4ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/11/2020
ms.locfileid: "43231006"
---
# <a name="configure-outbound-spam-filtering-in-office-365"></a><span data-ttu-id="1c033-103">Office 365 で送信スパムフィルターを構成する</span><span class="sxs-lookup"><span data-stu-id="1c033-103">Configure outbound spam filtering in Office 365</span></span>

<span data-ttu-id="1c033-104">Exchange Online または exchange online メールボックスを使用しないスタンドアロンの Exchange Online Protection (EOP) のお客様の場合、Office 365 をご利用のお客様は、EOP を経由して送信される送信電子メールメッセージがスパムと通常の送信アクティビティに対して自動的にチェックされます。</span><span class="sxs-lookup"><span data-stu-id="1c033-104">If you're an Office 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="1c033-105">組織内のユーザーからの送信スパムは、通常、侵害されたアカウントを示しています。</span><span class="sxs-lookup"><span data-stu-id="1c033-105">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="1c033-106">疑わしい送信メッセージは、スパムの信頼レベルまたは SCL に関係なく、スパムとしてマークされ、[高リスクの配信プール](high-risk-delivery-pool-for-outbound-messages.md)を経由してサービスの評価を保護します (つまり、Office 365 ソースの電子メールサーバーが IP 禁止一覧に保持されたままになります)。</span><span class="sxs-lookup"><span data-stu-id="1c033-106">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Office 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="1c033-107">管理者は、疑わしい送信電子メールアクティビティとブロックされたユーザーに対して通知[ポリシー](../../compliance/alert-policies.md)を使用して自動的に通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="1c033-107">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="1c033-108">EOP では、スパムに対する組織の全体的な防衛の一環として、送信スパムポリシーを使用しています。</span><span class="sxs-lookup"><span data-stu-id="1c033-108">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="1c033-109">詳細については、「[Office 365 のスパム対策保護](anti-spam-protection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c033-109">For more information, see [Anti-spam protection in Office 365](anti-spam-protection.md).</span></span>

<span data-ttu-id="1c033-110">管理者は、既定の送信スパムポリシーを表示、編集、および構成することはできますが、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="1c033-110">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="1c033-111">よりきめ細かく制御する場合は、組織内の特定のユーザー、グループ、またはドメインに適用するカスタムの送信スパムポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="1c033-111">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="1c033-112">カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (実行順序) を変更できます。</span><span class="sxs-lookup"><span data-stu-id="1c033-112">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="1c033-113">送信スパムポリシーを構成するには、Office 365 Security & コンプライアンスセンターまたは PowerShell (Office 365 お客様の場合は Exchange Online PowerShell) を使用します。Exchange Online Protection PowerShell (スタンドアロン EOP のお客様向け)。</span><span class="sxs-lookup"><span data-stu-id="1c033-113">You can configure outbound spam policies in the Office 365 Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="outbound-spam-policies-in-the-office-365-security--compliance-center-vs-exchange-online-powershell-or-exchange-online-protection-powershell"></a><span data-ttu-id="1c033-114">Office 365 セキュリティ & コンプライアンスセンター vs Exchange online PowerShell または Exchange Online Protection PowerShell の送信スパムポリシー</span><span class="sxs-lookup"><span data-stu-id="1c033-114">Outbound spam policies in the Office 365 Security & Compliance Center vs Exchange Online PowerShell or Exchange Online Protection PowerShell</span></span>

<span data-ttu-id="1c033-115">EOP の送信スパムポリシーの基本的な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1c033-115">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="1c033-116">**送信スパムフィルターポリシー**: 送信スパムフィルター verdicts のアクションと通知オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="1c033-116">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>

- <span data-ttu-id="1c033-117">**送信スパムフィルタールール**: 送信スパムフィルターポリシーの優先順位と受信者フィルター (ポリシーが適用されるユーザー) を指定します。</span><span class="sxs-lookup"><span data-stu-id="1c033-117">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="1c033-118">セキュリティ & コンプライアンスセンターで送信スパムポリシーを管理する場合、この2つの要素の違いは明白ではありません。</span><span class="sxs-lookup"><span data-stu-id="1c033-118">The difference between these two elements isn't obvious when you manage outbound spam policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="1c033-119">セキュリティ & コンプライアンスセンターで送信スパムポリシーを作成すると、実際には、両方に同じ名前を使用して、送信スパムフィルタールールと関連する送信スパムフィルターポリシーを同時に作成しています。</span><span class="sxs-lookup"><span data-stu-id="1c033-119">When you create an outbound spam policy in the Security & Compliance Center, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="1c033-120">セキュリティ & コンプライアンスセンターで送信スパムポリシーを変更すると、名前、優先度、有効または無効に関連する設定、および受信者フィルターによって送信スパムフィルタールールが変更されます。</span><span class="sxs-lookup"><span data-stu-id="1c033-120">When you modify an outbound spam policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="1c033-121">他のすべての設定は、関連する送信スパムフィルターポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="1c033-121">All other settings modify the associated outbound spam filter policy.</span></span>

- <span data-ttu-id="1c033-122">送信スパムポリシーをセキュリティ & コンプライアンスセンターから削除すると、送信スパムフィルタールールとそれに関連付けられた送信スパムフィルターポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="1c033-122">When you remove an outbound spam policy from the Security & Compliance Center, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="1c033-123">Exchange Online PowerShell またはスタンドアロンの Exchange Online Protection の PowerShell では、送信スパムフィルターポリシーと送信スパムフィルタールールの違いが明らかです。</span><span class="sxs-lookup"><span data-stu-id="1c033-123">In Exchange Online PowerShell or standalone Exchange Online Protection PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="1c033-124">送信スパムフィルターポリシーを管理するには、 \*\* \*-set-hostedcontentfilterpolicy**コマンドレットを使用して、 \*\* \*-disable-hostedcontentfilterrule**コマンドレットを使用して送信スパムフィルタールールを管理します。</span><span class="sxs-lookup"><span data-stu-id="1c033-124">You manage outbound spam filter policies by using the **\*-HostedContentFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedContentFilterRule** cmdlets.</span></span>

- <span data-ttu-id="1c033-125">PowerShell では、送信スパムフィルターポリシーを最初に作成してから、ルールが適用されるポリシーを識別する送信スパムフィルタールールを作成します。</span><span class="sxs-lookup"><span data-stu-id="1c033-125">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="1c033-126">PowerShell では、送信スパムフィルターポリシーと送信スパムフィルタールールの設定を個別に変更します。</span><span class="sxs-lookup"><span data-stu-id="1c033-126">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>

- <span data-ttu-id="1c033-127">送信スパムフィルターポリシーを PowerShell から削除すると、対応する送信スパムフィルタールールは自動的には削除されません。また、その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="1c033-127">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-outbound-spam-policy"></a><span data-ttu-id="1c033-128">既定の送信スパムポリシー</span><span class="sxs-lookup"><span data-stu-id="1c033-128">Default outbound spam policy</span></span>

<span data-ttu-id="1c033-129">すべての組織には、Default という名前の組み込みの送信スパムポリシーがあります。これらのプロパティは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1c033-129">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="1c033-130">Default という名前の送信スパムフィルターポリシーは、ポリシーに関連付けられた送信スパムフィルタールール (受信者フィルター) がない場合でも、組織内のすべての受信者に適用されます。</span><span class="sxs-lookup"><span data-stu-id="1c033-130">The outbound spam filter policy named Default is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="1c033-131">Default という名前のポリシーにはカスタムの優先順位の値 **Lowest** が設定されており、変更することはできません (このポリシーは常に最後に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="1c033-131">The policy named Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="1c033-132">作成するどのカスタム ポリシーも、Default という名前のポリシーより高い優先順位を持ちます。</span><span class="sxs-lookup"><span data-stu-id="1c033-132">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>

- <span data-ttu-id="1c033-133">Default という名前のポリシーは既定のポリシー (**IsDefault** のプロパティが `True` の値になっている) であり、既定のポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="1c033-133">The policy named Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="1c033-134">送信スパムフィルター処理の有効性を高めるために、特定のユーザーまたはユーザーグループに適用される厳密な設定を使用して、カスタムの送信スパムポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="1c033-134">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1c033-135">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="1c033-135">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1c033-136"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="1c033-136">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="1c033-137">**[スパム対策の設定]** ページに直接移動するには、<https://protection.office.com/antispam> を使用します。</span><span class="sxs-lookup"><span data-stu-id="1c033-137">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="1c033-138">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c033-138">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="1c033-139">スタンドアロンの Exchange Online Protection PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c033-139">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="1c033-140">これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c033-140">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="1c033-141">送信スパムポリシーを追加、変更、および削除するには、**組織の管理**または**セキュリティ管理者**の役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c033-141">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="1c033-142">送信スパムポリシーに対する読み取り専用アクセスでは、**セキュリティリーダー**役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c033-142">For read-only access to outbound spam policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="1c033-143">セキュリティ/コンプライアンス センターの役割グループの詳細については、「[Office 365 セキュリティ/コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1c033-143">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="1c033-144">送信スパムポリシーの推奨設定については、「 [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c033-144">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="1c033-145">**電子メール送信の制限**が設定されている既定の[警告ポリシー](../../compliance/alert-policies.md) 、**疑わしい電子メール送信パターンが検出さ**れたこと、および電子メールが送信**Global admins**を拒否したことによって、電子メール通知が通常の送信電子メールアクティビティやブロックされたユーザーについて**は、送信**スパムによる**もの**であることを示します。</span><span class="sxs-lookup"><span data-stu-id="1c033-145">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="1c033-146">詳細については、「制限され[たユーザーの通知設定を確認する](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c033-146">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="1c033-147">送信スパムポリシーの通知オプションではなく、これらのアラートポリシーを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1c033-147">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="1c033-148">セキュリティ & コンプライアンスセンターを使用して送信スパムポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="1c033-148">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="1c033-149">セキュリティ & コンプライアンスセンターでカスタムの送信スパムポリシーを作成すると、両方に同じ名前を使用して、スパムフィルタールールと関連するスパムフィルターポリシーが同時に作成されます。</span><span class="sxs-lookup"><span data-stu-id="1c033-149">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="1c033-150">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="1c033-150">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="1c033-151">[**スパム対策設定**] ページで、[**送信ポリシーの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c033-151">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="1c033-152">[**送信スパムフィルターポリシー** ] が表示されたら、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="1c033-152">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="1c033-153">**[名前]**: わかりやすい一意のポリシー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="1c033-153">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="1c033-154">**[説明]**: ポリシーについての説明を入力します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="1c033-154">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="1c033-155">オプション[**通知**] セクションを展開して、疑わしい送信電子メールメッセージのコピーと通知を受信する必要がある追加のユーザーを構成します。</span><span class="sxs-lookup"><span data-stu-id="1c033-155">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="1c033-156">**疑わしい送信電子メールメッセージのコピーを特定のユーザーに送信**する: この設定を行うと、指定されたユーザーが Bcc 受信者として疑わしい送信メッセージに追加されます。</span><span class="sxs-lookup"><span data-stu-id="1c033-156">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span> <span data-ttu-id="1c033-157">この設定を有効にするには:</span><span class="sxs-lookup"><span data-stu-id="1c033-157">To enable this setting:</span></span>

     <span data-ttu-id="1c033-158">a.</span><span class="sxs-lookup"><span data-stu-id="1c033-158">a.</span></span> <span data-ttu-id="1c033-159">チェックボックスをオンにして、設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="1c033-159">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="1c033-160">b.</span><span class="sxs-lookup"><span data-stu-id="1c033-160">b.</span></span> <span data-ttu-id="1c033-161">[**ユーザーの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c033-161">Click **Add people**.</span></span> <span data-ttu-id="1c033-162">[**受信者の追加または削除**] ポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c033-162">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="1c033-163">c.</span><span class="sxs-lookup"><span data-stu-id="1c033-163">c.</span></span> <span data-ttu-id="1c033-164">送信者の電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="1c033-164">Enter the sender's email address.</span></span> <span data-ttu-id="1c033-165">複数の電子メールアドレスをセミコロンで区切って指定できます (;)または1行に1人の受信者。</span><span class="sxs-lookup"><span data-stu-id="1c033-165">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="1c033-166">d.</span><span class="sxs-lookup"><span data-stu-id="1c033-166">d.</span></span> <span data-ttu-id="1c033-167">Click</span><span class="sxs-lookup"><span data-stu-id="1c033-167">Click</span></span> ![[追加] アイコン](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="1c033-169">受信者を追加します。</span><span class="sxs-lookup"><span data-stu-id="1c033-169">to add the recipients.</span></span>

        <span data-ttu-id="1c033-170">必要な回数だけこれらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="1c033-170">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="1c033-171">追加した受信者が、フライアウトの [**受信者リスト**] セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c033-171">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="1c033-172">受信者を削除するに![は、](../../media/scc-remove-icon.png)[削除] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c033-172">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="1c033-173">e. </span><span class="sxs-lookup"><span data-stu-id="1c033-173">e.</span></span> <span data-ttu-id="1c033-174">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c033-174">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="1c033-175">この設定を無効にするには、このチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="1c033-175">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="1c033-176">送信**スパムの送信によって送信者がブロックされた場合に、特定のユーザーに通知し**ます。</span><span class="sxs-lookup"><span data-stu-id="1c033-176">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!NOTE]
     > <span data-ttu-id="1c033-177">ユーザーが [**受信者の制限**] セクションの制限を超えたためにユーザーがブロックされた**Global admins**場合は、ユーザーによって [**送信メールが電子メール**によって制限されました] という名前の既定の[警告ポリシー](../../compliance/alert-policies.md)が、既に**tenantadmins**グループのメンバーに電子メール通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="1c033-177">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="1c033-178">送信スパムポリシーのこの設定ではなく、通知ポリシーを使用して、管理者およびその他のユーザーに通知することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1c033-178">We recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users.</span></span> <span data-ttu-id="1c033-179">手順については、「制限され[たユーザーの通知設定を確認する](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c033-179">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

     <span data-ttu-id="1c033-180">この設定を有効にするには:</span><span class="sxs-lookup"><span data-stu-id="1c033-180">To enable this setting:</span></span>

     <span data-ttu-id="1c033-181">a.</span><span class="sxs-lookup"><span data-stu-id="1c033-181">a.</span></span> <span data-ttu-id="1c033-182">チェックボックスをオンにして、設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="1c033-182">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="1c033-183">b.</span><span class="sxs-lookup"><span data-stu-id="1c033-183">b.</span></span> <span data-ttu-id="1c033-184">[**ユーザーの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c033-184">Click **Add people**.</span></span> <span data-ttu-id="1c033-185">[**受信者の追加または削除**] ポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c033-185">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="1c033-186">c.</span><span class="sxs-lookup"><span data-stu-id="1c033-186">c.</span></span> <span data-ttu-id="1c033-187">送信者の電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="1c033-187">Enter the sender's email address.</span></span> <span data-ttu-id="1c033-188">複数の電子メールアドレスをセミコロンで区切って指定できます (;)または1行に1人の受信者。</span><span class="sxs-lookup"><span data-stu-id="1c033-188">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="1c033-189">d.</span><span class="sxs-lookup"><span data-stu-id="1c033-189">d.</span></span> <span data-ttu-id="1c033-190">Click</span><span class="sxs-lookup"><span data-stu-id="1c033-190">Click</span></span> ![[追加] アイコン](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="1c033-192">受信者を追加します。</span><span class="sxs-lookup"><span data-stu-id="1c033-192">to add the recipients.</span></span>

        <span data-ttu-id="1c033-193">必要な回数だけこれらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="1c033-193">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="1c033-194">追加した受信者が、フライアウトの [**受信者リスト**] セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c033-194">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="1c033-195">受信者を削除するに![は、](../../media/scc-remove-icon.png)[削除] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c033-195">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="1c033-196">e. </span><span class="sxs-lookup"><span data-stu-id="1c033-196">e.</span></span> <span data-ttu-id="1c033-197">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c033-197">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="1c033-198">この設定を無効にするには、このチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="1c033-198">To disable this setting, clear the check box.</span></span>

5. <span data-ttu-id="1c033-199">オプション[**受信者の制限**] セクションを展開して、疑わしい送信電子メールメッセージの制限およびアクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="1c033-199">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages: ]</span></span>
   - <span data-ttu-id="1c033-200">**ユーザーあたりの最大受信者数**</span><span class="sxs-lookup"><span data-stu-id="1c033-200">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="1c033-201">有効な値は、0 ~ 1万です。</span><span class="sxs-lookup"><span data-stu-id="1c033-201">A valid value is 0 to 10000.</span></span> <span data-ttu-id="1c033-202">既定値は0です。これは、サービスの既定値が使用されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="1c033-202">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="1c033-203">詳細については、「 [Office での制限を送信365のオプション](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c033-203">For more information, see [Sending limits across Office 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

     - <span data-ttu-id="1c033-204">**外部の時間**単位の制限: 1 時間あたりの外部受信者の最大数。</span><span class="sxs-lookup"><span data-stu-id="1c033-204">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="1c033-205">[内部最大時間**制限**数: 1 時間あたりの内部受信者の最大数。</span><span class="sxs-lookup"><span data-stu-id="1c033-205">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="1c033-206">**Daily limit**: 1 日あたりの受信者の最大合計数。</span><span class="sxs-lookup"><span data-stu-id="1c033-206">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="1c033-207">**ユーザーが上記の制限を超えた場合の対処**:**受信者の制限**のいずれかを超えた場合に実行するアクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="1c033-207">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="1c033-208">すべての操作について、ユーザーが**電子メール**通知ポリシーを送信することを制限しています (これで、送信スパムポリシーで送信スパムの設定**を送信するために送信者がブロックされている場合**は、特定のユーザーに対して特定のユーザーに指定された受信者が電子メール通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="1c033-208">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="1c033-209">**ユーザーが次の日までメールを送信**できないように制限します。これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="1c033-209">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="1c033-210">電子メール通知が送信され、ユーザーは UTC 時間に基づいて、次の日までメッセージを送信できなくなります。</span><span class="sxs-lookup"><span data-stu-id="1c033-210">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="1c033-211">管理者がこのブロックを上書きする方法はありません。</span><span class="sxs-lookup"><span data-stu-id="1c033-211">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="1c033-212">[**ユーザーが電子メールを送信**できないようにする] という名前のアクティビティアラートは、管理者に電子メールを介して通知を送信します ([通知の**表示**] ページ)。</span><span class="sxs-lookup"><span data-stu-id="1c033-212">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="1c033-213">ポリシーの送信スパム設定の**送信によって送信者がブロックされた場合**、[特定のユーザーを通知する] で指定されたすべての受信者にも通知されます。</span><span class="sxs-lookup"><span data-stu-id="1c033-213">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="1c033-214">このユーザーは、UTC 時間に基づいて、次の日まで、それ以上のメッセージを送信できなくなります。</span><span class="sxs-lookup"><span data-stu-id="1c033-214">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="1c033-215">管理者がこのブロックを上書きする方法はありません。</span><span class="sxs-lookup"><span data-stu-id="1c033-215">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="1c033-216">**ユーザーがメールを送信する**のを制限する: 電子メール通知が送信され、ユーザーはセキュリティ & コンプライアンスセンターの**<https://sip.protection.office.com/restrictedusers> [制限付きユーザー]** ポータルに追加され、ユーザーは管理者によって**制限付きユーザー**ポータルから削除されるまで電子メールを送信できません。管理者がリストからユーザーを削除した後は、その日に対してユーザーが再度制限されることはありません。</span><span class="sxs-lookup"><span data-stu-id="1c033-216">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="1c033-217">手順については、「[迷惑メールの送信後に制限付きユーザーポータルからユーザーを削除する](removing-user-from-restricted-users-portal-after-spam.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c033-217">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="1c033-218">**アクションなし、通知のみ**: 電子メール通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="1c033-218">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="1c033-219">要する[**適用先**] セクションを展開して、ポリシーが適用される内部送信者を特定します。</span><span class="sxs-lookup"><span data-stu-id="1c033-219">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="1c033-220">各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1c033-220">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="1c033-221">同じ条件または例外の複数の値を使用するか、ロジック (たとえば、 _ \<sender1\> _または_ \<sender2\>_) を使用します。</span><span class="sxs-lookup"><span data-stu-id="1c033-221">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="1c033-222">さまざまな条件や例外、およびロジック ( _ \<sender1\> _ 、 _ \<グループ\>1 のメンバー_など) を使用します。</span><span class="sxs-lookup"><span data-stu-id="1c033-222">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="1c033-223">使用可能なすべての条件を表示するには、**[条件の追加]** を 3 回クリックするのが最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="1c033-223">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="1c033-224">構成しない条件を削除するには、![[削除] ボタン](../../media/scc-remove-icon.png)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c033-224">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="1c033-225">**送信者ドメイン**: 構成された1つ以上の承認済みドメインで Office 365 に送信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="1c033-225">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in Office 365.</span></span> <span data-ttu-id="1c033-226">**[タグの追加]** ボックスをクリックして、ドメインを表示および選択します。</span><span class="sxs-lookup"><span data-stu-id="1c033-226">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="1c033-227">複数のドメインが利用可能な場合は、**[タグの追加]** ボックスをもう一度クリックして、追加のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="1c033-227">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="1c033-228">**Sender is**: 組織内の1人または複数のユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="1c033-228">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="1c033-229">**[タグの追加]** をクリックして、リストをフィルター処理するための入力を始めます。</span><span class="sxs-lookup"><span data-stu-id="1c033-229">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="1c033-230">[**タグの追加**] ボックスをもう一度クリックして、追加の送信者を選択します。</span><span class="sxs-lookup"><span data-stu-id="1c033-230">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="1c033-231">**送信者が次のメンバーの場合**: 組織内の1つまたは複数のグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="1c033-231">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="1c033-232">**[タグの追加]** をクリックして、リストをフィルター処理するための入力を始めます。</span><span class="sxs-lookup"><span data-stu-id="1c033-232">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="1c033-233">[**タグの追加**] ボックスをもう一度クリックして、追加の送信者を選択します。</span><span class="sxs-lookup"><span data-stu-id="1c033-233">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="1c033-234">**次の場合を除く**: ルールの例外を追加するには、**[条件の追加]** を 3 回クリックして、使用可能なすべての例外を表示します。</span><span class="sxs-lookup"><span data-stu-id="1c033-234">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="1c033-235">設定と動作は、条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="1c033-235">The settings and behavior are exactly like the conditions.</span></span>

7. <span data-ttu-id="1c033-236">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c033-236">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="1c033-237">セキュリティ & コンプライアンスセンターを使用して、送信スパムポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="1c033-237">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="1c033-238">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="1c033-238">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="1c033-239">[**スパム対策設定**] ページで、[ ![展開]](../../media/scc-expand-icon.png)アイコンをクリックして、送信スパムポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="1c033-239">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="1c033-240">**送信スパムフィルターポリシー**という名前の既定のポリシー。</span><span class="sxs-lookup"><span data-stu-id="1c033-240">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="1c033-241">作成したカスタムポリシーで、[**種類**] 列の値が [**カスタム送信スパムポリシー**] になっています。</span><span class="sxs-lookup"><span data-stu-id="1c033-241">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="1c033-242">ポリシー設定は、表示される拡張されたポリシーの詳細に表示されるか、[**ポリシーの編集**] をクリックできます。</span><span class="sxs-lookup"><span data-stu-id="1c033-242">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="1c033-243">セキュリティ & コンプライアンスセンターを使用して送信スパムポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="1c033-243">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="1c033-244">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="1c033-244">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="1c033-245">[**スパム対策設定**] ページで、[ ![展開]](../../media/scc-expand-icon.png)アイコンをクリックして、送信スパムポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="1c033-245">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="1c033-246">**送信スパムフィルターポリシー**という名前の既定のポリシー。</span><span class="sxs-lookup"><span data-stu-id="1c033-246">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="1c033-247">作成したカスタムポリシーで、[**種類**] 列の値が [**カスタム送信スパムポリシー**] になっています。</span><span class="sxs-lookup"><span data-stu-id="1c033-247">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="1c033-248">**[ポリシーの編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c033-248">Click **Edit policy**.</span></span>

<span data-ttu-id="1c033-249">カスタムの送信スパムポリシーの場合、表示されるポップアップで使用可能な設定は、「[セキュリティ & コンプライアンスセンターを使用して送信スパムポリシーを作成する](#use-the-security--compliance-center-to-create-outbound-spam-policies)」セクションに記載されている設定と同じです。</span><span class="sxs-lookup"><span data-stu-id="1c033-249">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="1c033-250">"**送信スパムフィルターポリシー**" という名前の既定の送信スパムポリシーの場合、[**適用先**] セクションは利用できません (ポリシーはすべてのユーザーに適用されます)。また、ポリシーの名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="1c033-250">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="1c033-251">ポリシーを有効または無効にするには、ポリシーの優先順位を設定するか、またはエンドユーザーの検疫通知を構成します。後続の各セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1c033-251">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="1c033-252">送信スパムポリシーを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="1c033-252">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="1c033-253">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="1c033-253">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="1c033-254">[**スパム対策設定**] ページで、[ ![展開]](../../media/scc-expand-icon.png)アイコンをクリックして、作成したカスタムポリシーを展開します ([**種類**] 列の値は、**カスタムの送信スパムポリシー**です)。</span><span class="sxs-lookup"><span data-stu-id="1c033-254">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="1c033-255">展開して表示されたポリシー詳細で、**[On]** 列の値をメモします。</span><span class="sxs-lookup"><span data-stu-id="1c033-255">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="1c033-256">ポリシーを無効にするには、左に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="1c033-256">Move the toggle to the left to disable the policy:</span></span> ![オフに切り替え](../../media/scc-toggle-off.png)

   <span data-ttu-id="1c033-258">ポリシーを有効にするには、右に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="1c033-258">Move the toggle to the right to enable the policy:</span></span> ![オンに切り替え](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="1c033-260">既定の送信スパムポリシーを無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="1c033-260">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="1c033-261">カスタム送信スパムポリシーの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="1c033-261">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="1c033-262">既定では、送信スパムポリシーには、作成された順序に基づく優先度が与えられます (新しいポリシーは、以前のポリシーよりも優先度が低いです)。</span><span class="sxs-lookup"><span data-stu-id="1c033-262">By default, outbound spam policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="1c033-263">優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。</span><span class="sxs-lookup"><span data-stu-id="1c033-263">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="1c033-264">2 つのポリシーが同じ優先度を持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="1c033-264">No two policies can have the same priority.</span></span>

<span data-ttu-id="1c033-265">カスタム送信スパムポリシーは、処理順に表示されます (最初のポリシーの**優先度**値は0です)。</span><span class="sxs-lookup"><span data-stu-id="1c033-265">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="1c033-266">"**送信スパムフィルターポリシー** " という名前の既定の送信スパムポリシーは、優先度の値が**低い**ので、これを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="1c033-266">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="1c033-267">ポリシーの優先度を変更するには、リスト内で上下に移動させます (セキュリティ/コンプライアンス センター内で直接、**優先順位**番号を変更することはできません)。</span><span class="sxs-lookup"><span data-stu-id="1c033-267">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="1c033-268">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="1c033-268">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="1c033-269">[**スパム対策設定**] ページで、[**種類**] 列の値が**カスタム送信スパムポリシー**であるポリシーを探します。</span><span class="sxs-lookup"><span data-stu-id="1c033-269">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="1c033-270">**[優先度]** 列の値に注目します。</span><span class="sxs-lookup"><span data-stu-id="1c033-270">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="1c033-271">優先度が最も高いカスタムの送信スパムポリシーには![、値の](../../media/ITPro-EAC-DownArrowIcon.png)下矢印アイコン**0**があります。</span><span class="sxs-lookup"><span data-stu-id="1c033-271">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="1c033-272">最も低い優先度を持つカスタムの送信スパムポリシーに![は、上矢印アイコン](../../media/ITPro-EAC-UpArrowIcon.png) **n** ( ![上矢印アイコン](../../media/ITPro-EAC-UpArrowIcon.png) **3**) の値が設定されています。</span><span class="sxs-lookup"><span data-stu-id="1c033-272">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="1c033-273">ユーザー設定の送信スパムポリシーが3つ以上ある場合、最高の優先度と最も低い優先![順位の間](../../media/ITPro-EAC-UpArrowIcon.png)![のポリシーは](../../media/ITPro-EAC-DownArrowIcon.png) 、上矢印アイコンの![下矢印アイコン](../../media/ITPro-EAC-UpArrowIcon.png)![ **n** (たとえば](../../media/ITPro-EAC-DownArrowIcon.png) 、上矢印アイコンを下矢印アイコン**2**) に設定します。</span><span class="sxs-lookup"><span data-stu-id="1c033-273">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="1c033-274">上</span><span class="sxs-lookup"><span data-stu-id="1c033-274">Click</span></span> ![矢印アイコン](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="1c033-276">または</span><span class="sxs-lookup"><span data-stu-id="1c033-276">or</span></span> ![下矢印アイコンをクリックして](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="1c033-278">を押して、カスタムの送信スパムポリシーを優先順位一覧で上または下に移動します。</span><span class="sxs-lookup"><span data-stu-id="1c033-278">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="1c033-279">セキュリティ & コンプライアンスセンターを使用して送信スパムポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="1c033-279">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="1c033-280">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="1c033-280">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="1c033-281">[**スパム対策設定**] ページで、[ ![展開]](../../media/scc-expand-icon.png)アイコンをクリックして、削除するカスタムポリシーを展開します ( **Type**列は**カスタム送信スパムポリシー**です)。</span><span class="sxs-lookup"><span data-stu-id="1c033-281">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="1c033-282">展開されたポリシー詳細で、**[ポリシーの削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c033-282">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="1c033-283">警告ダイアログが表示されたら、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c033-283">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="1c033-284">既定のポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="1c033-284">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="1c033-285">Exchange Online PowerShell または Exchange Online Protection PowerShell を使用して送信スパムポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="1c033-285">Use Exchange Online PowerShell or Exchange Online Protection PowerShell to configure outbound spam policies</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="1c033-286">PowerShell を使用して送信スパムポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="1c033-286">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="1c033-287">PowerShell で送信スパムポリシーを作成するには、2つの手順からなるプロセスがあります。</span><span class="sxs-lookup"><span data-stu-id="1c033-287">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="1c033-288">送信スパムフィルターポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="1c033-288">Create the outbound spam filter policy.</span></span>

2. <span data-ttu-id="1c033-289">ルールを適用する送信スパムフィルターポリシーを指定する送信スパムフィルタールールを作成します。</span><span class="sxs-lookup"><span data-stu-id="1c033-289">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="1c033-290">**注**:</span><span class="sxs-lookup"><span data-stu-id="1c033-290">**Notes**:</span></span>

- <span data-ttu-id="1c033-291">新しい送信スパムフィルタールールを作成して、関連付けられていない既存の送信スパムフィルターポリシーをそれに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1c033-291">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="1c033-292">送信スパムフィルタールールは、複数の送信スパムフィルターポリシーに関連付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="1c033-292">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="1c033-293">ポリシーを作成するまでは、セキュリティ & コンプライアンスセンターでは使用できない PowerShell の新しい送信スパムフィルターポリシーに対して、次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="1c033-293">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="1c033-294">新しいポリシーを無効として作成します ( **HostedOutboundSpamFilterRule**コマンドレットでは_有効_ `$false` )。</span><span class="sxs-lookup"><span data-stu-id="1c033-294">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

  - <span data-ttu-id="1c033-295">**HostedOutboundSpamFilterRule**コマンドレットで、作成中にポリシーの優先度を設定します (_優先度_ _ \<番号\>_)。</span><span class="sxs-lookup"><span data-stu-id="1c033-295">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="1c033-296">PowerShell で作成した新しい送信スパムフィルターポリシーは、そのポリシーをスパムフィルタールールに割り当てるまで、セキュリティ & コンプライアンスセンターに表示されません。</span><span class="sxs-lookup"><span data-stu-id="1c033-296">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="1c033-297">手順 1: PowerShell を使用して送信スパムフィルターポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="1c033-297">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="1c033-298">送信スパムフィルターポリシーを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="1c033-298">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="1c033-299">この例では、次の設定を使用して Contoso 重役という新しい送信スパムフィルターポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="1c033-299">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="1c033-300">受信者数の制限は、既定値より小さい値に制限されます。</span><span class="sxs-lookup"><span data-stu-id="1c033-300">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="1c033-301">詳細については、「 [Office での制限を送信365のオプション](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c033-301">For more information, see [Sending limits across Office 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="1c033-302">いずれかの制限に達すると、ユーザーはメッセージを送信できなくなります。</span><span class="sxs-lookup"><span data-stu-id="1c033-302">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="1c033-303">構文およびパラメーターの詳細については、「 [HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c033-303">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="1c033-304">手順 2: PowerShell を使用して送信スパムフィルタールールを作成する</span><span class="sxs-lookup"><span data-stu-id="1c033-304">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="1c033-305">送信スパムフィルタールールを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="1c033-305">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="1c033-306">この例では、次の設定を使用して Contoso 重役という新しい送信スパムフィルタールールを作成します。</span><span class="sxs-lookup"><span data-stu-id="1c033-306">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="1c033-307">Contoso エグゼクティブという名前の送信スパムフィルターポリシーがルールに関連付けられている。</span><span class="sxs-lookup"><span data-stu-id="1c033-307">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="1c033-308">ルールは Contoso Executives Group という名前のグループのメンバーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="1c033-308">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="1c033-309">構文およびパラメーターの詳細については、「 [HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c033-309">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="1c033-310">PowerShell を使用して送信スパムフィルターポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="1c033-310">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="1c033-311">すべての送信スパムフィルターポリシーの要約リストを返すには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1c033-311">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="1c033-312">特定の送信スパムフィルターポリシーの詳細情報を戻すには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="1c033-312">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="1c033-313">この例では、重役という送信スパムフィルターポリシーのすべてのプロパティ値を返します。</span><span class="sxs-lookup"><span data-stu-id="1c033-313">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="1c033-314">構文およびパラメーターの詳細については、「 [HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c033-314">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="1c033-315">PowerShell を使用して送信スパムフィルタールールを表示する</span><span class="sxs-lookup"><span data-stu-id="1c033-315">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="1c033-316">既存の送信スパムフィルタールールを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="1c033-316">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="1c033-317">すべての送信スパムフィルタールールの要約リストを返すには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1c033-317">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="1c033-318">ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1c033-318">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="1c033-319">特定の送信スパムフィルタールールに関する詳細情報を戻すには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="1c033-319">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="1c033-320">この例では、Contoso 重役という送信スパムフィルタールールのすべてのプロパティ値を返します。</span><span class="sxs-lookup"><span data-stu-id="1c033-320">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="1c033-321">構文およびパラメーターの詳細については、「 [HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c033-321">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="1c033-322">PowerShell を使用して送信スパムフィルターポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="1c033-322">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="1c033-323">このトピックで前述した「[手順 1: powershell を使用して送信スパムフィルターポリシーを作成](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy)する」の説明に従って、ポリシーの作成時に powershell のマルウェアフィルターポリシーを変更する場合にも、同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1c033-323">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this topic.</span></span>

<span data-ttu-id="1c033-324">**注**: 送信スパムフィルターポリシーの名前を変更することはできません ( **HostedOutboundSpamFilterPolicy**コマンドレットに_Name_パラメーターがありません)。</span><span class="sxs-lookup"><span data-stu-id="1c033-324">**Note**: You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="1c033-325">セキュリティ & コンプライアンスセンターで送信スパムポリシーの名前を変更する場合は、送信スパムフィルター_ルール_の名前のみを変更しています。</span><span class="sxs-lookup"><span data-stu-id="1c033-325">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="1c033-326">送信スパムフィルターポリシーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="1c033-326">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="1c033-327">構文およびパラメーターの詳細については、「 [HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c033-327">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="1c033-328">PowerShell を使用して送信スパムフィルタールールを変更する</span><span class="sxs-lookup"><span data-stu-id="1c033-328">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="1c033-329">PowerShell で送信スパムフィルタールールを変更するときには使用できない唯一の設定は、無効にされたルールを作成できる_有効_なパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="1c033-329">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="1c033-330">既存の送信スパムフィルタールールを有効または無効にするには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c033-330">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="1c033-331">それ以外の場合は、PowerShell で送信スパムフィルタールールを変更するときに、追加の設定を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="1c033-331">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="1c033-332">このトピックで前述した「[手順 2: PowerShell を使用して送信スパムフィルタールールを作成する](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule)」で説明されているように、ルールを作成する場合にも同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1c033-332">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="1c033-333">送信スパムフィルタールールを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="1c033-333">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="1c033-334">構文およびパラメーターの詳細については、「 [HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c033-334">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="1c033-335">PowerShell を使用して送信スパムフィルタールールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="1c033-335">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="1c033-336">PowerShell で送信スパムフィルタールールを有効または無効にすると、送信スパムポリシー全体 (送信スパムフィルタールールおよび割り当てられた送信スパムフィルターポリシー) が有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="1c033-336">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="1c033-337">既定の送信スパムポリシーを有効または無効にすることはできません (常にすべての受信者に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="1c033-337">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="1c033-338">PowerShell で送信スパムフィルタールールを有効または無効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="1c033-338">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="1c033-339">この例では、Marketing Department という名前の送信スパムフィルタールールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="1c033-339">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="1c033-340">この例では、同じルールを有効化します。</span><span class="sxs-lookup"><span data-stu-id="1c033-340">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="1c033-341">構文およびパラメーターの詳細については、「 [HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedoutboundspamfilterrule) 」および「 [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedoutboundspamfilterrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c033-341">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="1c033-342">PowerShell を使用して送信スパムフィルタールールの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="1c033-342">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="1c033-343">ルールに設定できる優先度の最高値値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="1c033-343">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="1c033-344">設定できる最低値はルールの数に依存します。</span><span class="sxs-lookup"><span data-stu-id="1c033-344">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="1c033-345">たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。</span><span class="sxs-lookup"><span data-stu-id="1c033-345">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="1c033-346">既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。</span><span class="sxs-lookup"><span data-stu-id="1c033-346">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="1c033-347">たとえば、カスタム ルールが 5 つあって (優先度 0 から 4)、1 つのルールの優先度を 2 に変更した場合には、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。</span><span class="sxs-lookup"><span data-stu-id="1c033-347">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="1c033-348">PowerShell で送信スパムフィルタールールの優先度を設定するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="1c033-348">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="1c033-p146">この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。</span><span class="sxs-lookup"><span data-stu-id="1c033-p146">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="1c033-351">**注**:</span><span class="sxs-lookup"><span data-stu-id="1c033-351">**Notes**:</span></span>

- <span data-ttu-id="1c033-352">新しいルールの作成時に優先度を設定するには、代わりに**HostedOutboundSpamFilterRule**コマンドレットで_priority_パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1c033-352">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>

- <span data-ttu-id="1c033-353">既定の送信スパムフィルターポリシーには、対応するスパムフィルタールールがありません。また、常に、未設定の優先度の値が**最低**になっています。</span><span class="sxs-lookup"><span data-stu-id="1c033-353">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="1c033-354">PowerShell を使用して送信スパムフィルターポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="1c033-354">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="1c033-355">PowerShell を使用して送信スパムフィルターポリシーを削除しても、それに対応する送信スパムフィルタールールは削除されません。</span><span class="sxs-lookup"><span data-stu-id="1c033-355">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="1c033-356">PowerShell で送信スパムフィルターポリシーを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="1c033-356">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="1c033-357">この例では、Marketing Department という名前の送信スパムフィルターポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="1c033-357">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="1c033-358">構文およびパラメーターの詳細については、「 [HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c033-358">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="1c033-359">PowerShell を使用して送信スパムフィルタールールを削除する</span><span class="sxs-lookup"><span data-stu-id="1c033-359">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="1c033-360">PowerShell を使用して送信スパムフィルタールールを削除しても、対応する送信スパムフィルターポリシーは削除されません。</span><span class="sxs-lookup"><span data-stu-id="1c033-360">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="1c033-361">PowerShell で送信スパムフィルタールールを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="1c033-361">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="1c033-362">この例では、Marketing Department という名前の送信スパムフィルタールールを削除します。</span><span class="sxs-lookup"><span data-stu-id="1c033-362">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="1c033-363">構文およびパラメーターの詳細については、「 [HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c033-363">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="1c033-364">関連情報</span><span class="sxs-lookup"><span data-stu-id="1c033-364">For more information</span></span>

[<span data-ttu-id="1c033-365">Office 365 の制限されたユーザー ポータルから、ブロックされたユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="1c033-365">Remove blocked users from the Restricted Users portal in Office 365</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="1c033-366">送信メッセージにおける危険度の高い配信プール</span><span class="sxs-lookup"><span data-stu-id="1c033-366">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="1c033-367">スパム対策保護に関してよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="1c033-367">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
