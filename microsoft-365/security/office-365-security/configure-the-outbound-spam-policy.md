---
title: 送信スパムフィルターを構成する
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
ms.openlocfilehash: e788310ae8fd3c0da7f1a39fbba2dc0d6e369d30
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "42893965"
---
# <a name="configure-outbound-spam-filtering-in-office-365"></a><span data-ttu-id="d0010-103">Office 365 で送信スパムフィルターを構成する</span><span class="sxs-lookup"><span data-stu-id="d0010-103">Configure outbound spam filtering in Office 365</span></span>

<span data-ttu-id="d0010-104">Exchange Online または exchange online メールボックスを持たないスタンドアロンの Exchange Online Protection (EOP) 顧客のメールボックスを使用している Office 365 お客様の場合、EOP を介して送信される送信電子メールメッセージは自動的にチェックされ、スパムや異常をチェックします。送信アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="d0010-104">If you're an Office 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="d0010-105">組織内のユーザーからの送信スパムは、通常、侵害されたアカウントを示しています。</span><span class="sxs-lookup"><span data-stu-id="d0010-105">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="d0010-106">疑わしい送信メッセージは、スパムの信頼レベルまたは SCL に関係なく、スパムとしてマークされ、[高リスクの配信プール](high-risk-delivery-pool-for-outbound-messages.md)を経由してサービスの評価を保護します (つまり、Office 365 ソースの電子メールサーバーが IP 禁止一覧に保持されたままになります)。</span><span class="sxs-lookup"><span data-stu-id="d0010-106">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Office 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="d0010-107">管理者は、疑わしい送信電子メールアクティビティとブロックされたユーザーに対して通知[ポリシー](../../compliance/alert-policies.md)を使用して自動的に通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d0010-107">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="d0010-108">EOP では、スパムに対する組織の全体的な防衛の一環として、送信スパムポリシーを使用しています。</span><span class="sxs-lookup"><span data-stu-id="d0010-108">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="d0010-109">詳細については、「 [Office 365 のスパム対策保護](anti-spam-protection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0010-109">For more information, see [Anti-spam protection in Office 365](anti-spam-protection.md).</span></span>

<span data-ttu-id="d0010-110">管理者は、既定の送信スパムポリシーを表示、編集、および構成することはできますが、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="d0010-110">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="d0010-111">よりきめ細かく制御する場合は、組織内の特定のユーザー、グループ、またはドメインに適用するカスタムの送信スパムポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="d0010-111">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="d0010-112">カスタムポリシーは、常に既定のポリシーより優先されますが、カスタムポリシーの優先度 (実行順序) を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="d0010-112">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="d0010-113">送信スパムポリシーを構成するには、Office 365 Security & コンプライアンスセンターまたは PowerShell (Office 365 お客様の場合は Exchange Online PowerShell) を使用します。Exchange Online Protection PowerShell (スタンドアロン EOP のお客様向け)。</span><span class="sxs-lookup"><span data-stu-id="d0010-113">You can configure outbound spam policies in the Office 365 Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="outbound-spam-policies-in-the-office-365-security--compliance-center-vs-exchange-online-powershell-or-exchange-online-protection-powershell"></a><span data-ttu-id="d0010-114">Office 365 セキュリティ & コンプライアンスセンター vs Exchange online PowerShell または Exchange Online Protection PowerShell の送信スパムポリシー</span><span class="sxs-lookup"><span data-stu-id="d0010-114">Outbound spam policies in the Office 365 Security & Compliance Center vs Exchange Online PowerShell or Exchange Online Protection PowerShell</span></span>

<span data-ttu-id="d0010-115">EOP の送信スパムポリシーの基本的な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d0010-115">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="d0010-116">**送信スパムフィルターポリシー**: 送信スパムフィルター verdicts のアクションと通知オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="d0010-116">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>

- <span data-ttu-id="d0010-117">**送信スパムフィルタールール**: 送信スパムフィルターポリシーの優先順位と受信者フィルター (ポリシーが適用されるユーザー) を指定します。</span><span class="sxs-lookup"><span data-stu-id="d0010-117">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="d0010-118">セキュリティ & コンプライアンスセンターで送信スパムポリシーを管理する場合、この2つの要素の違いは明白ではありません。</span><span class="sxs-lookup"><span data-stu-id="d0010-118">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="d0010-119">セキュリティ & コンプライアンスセンターで送信スパムポリシーを作成すると、実際には、両方に同じ名前を使用して、送信スパムフィルタールールと関連する送信スパムフィルターポリシーを同時に作成しています。</span><span class="sxs-lookup"><span data-stu-id="d0010-119">When you create an outbound spam policy in the Security & Compliance Center, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="d0010-120">セキュリティ & コンプライアンスセンターで送信スパムポリシーを変更すると、名前、優先度、有効または無効に関連する設定、および受信者フィルターによって送信スパムフィルタールールが変更されます。</span><span class="sxs-lookup"><span data-stu-id="d0010-120">When you modify an outbound spam policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="d0010-121">他のすべての設定は、関連する送信スパムフィルターポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="d0010-121">All other settings modify the associated outbound spam filter policy.</span></span>

- <span data-ttu-id="d0010-122">送信スパムポリシーをセキュリティ & コンプライアンスセンターから削除すると、送信スパムフィルタールールとそれに関連付けられた送信スパムフィルターポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="d0010-122">When you remove an outbound spam policy from the Security & Compliance Center, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="d0010-123">Exchange Online PowerShell またはスタンドアロンの Exchange Online Protection の PowerShell では、送信スパムフィルターポリシーと送信スパムフィルタールールの違いが明らかです。</span><span class="sxs-lookup"><span data-stu-id="d0010-123">In Exchange Online PowerShell or standalone Exchange Online Protection PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="d0010-124">送信スパムフィルターポリシーを管理するには、 \*\* \*-set-hostedcontentfilterpolicy**コマンドレットを使用して、 \*\* \*-disable-hostedcontentfilterrule**コマンドレットを使用して送信スパムフィルタールールを管理します。</span><span class="sxs-lookup"><span data-stu-id="d0010-124">You manage outbound spam filter policies by using the **\*-HostedContentFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedContentFilterRule** cmdlets.</span></span>

- <span data-ttu-id="d0010-125">PowerShell では、送信スパムフィルターポリシーを最初に作成してから、ルールが適用されるポリシーを識別する送信スパムフィルタールールを作成します。</span><span class="sxs-lookup"><span data-stu-id="d0010-125">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="d0010-126">PowerShell では、送信スパムフィルターポリシーと送信スパムフィルタールールの設定を個別に変更します。</span><span class="sxs-lookup"><span data-stu-id="d0010-126">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>

- <span data-ttu-id="d0010-127">送信スパムフィルターポリシーを PowerShell から削除すると、対応する送信スパムフィルタールールは自動的には削除されません。また、その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="d0010-127">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-outbound-spam-policy"></a><span data-ttu-id="d0010-128">既定の送信スパムポリシー</span><span class="sxs-lookup"><span data-stu-id="d0010-128">Default outbound spam policy</span></span>

<span data-ttu-id="d0010-129">すべての組織には、Default という名前の組み込みの送信スパムポリシーがあります。これらのプロパティは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d0010-129">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="d0010-130">Default という名前の送信スパムフィルターポリシーは、ポリシーに関連付けられた送信スパムフィルタールール (受信者フィルター) がない場合でも、組織内のすべての受信者に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d0010-130">The outbound spam filter policy named Default is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="d0010-131">Default という名前のポリシーでは、変更できないカスタムの優先度の値が**最低**です (ポリシーは常に最後に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="d0010-131">The policy named Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="d0010-132">作成するカスタムポリシーは、常に Default という名前のポリシーよりも高い優先順位を持ちます。</span><span class="sxs-lookup"><span data-stu-id="d0010-132">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>

- <span data-ttu-id="d0010-133">Default という名前のポリシーが既定のポリシーである ( **IsDefault**プロパティ`True`の値がである) ため、既定のポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="d0010-133">The policy named Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="d0010-134">送信スパムフィルター処理の有効性を高めるために、特定のユーザーまたはユーザーグループに適用される厳密な設定を使用して、カスタムの送信スパムポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="d0010-134">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d0010-135">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="d0010-135">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d0010-136">セキュリティ & コンプライアンスセンターに<https://protection.office.com/>表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0010-136">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="d0010-137">[**スパム対策設定**] ページに直接移動するには<https://protection.office.com/antispam>、を使用します。</span><span class="sxs-lookup"><span data-stu-id="d0010-137">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="d0010-138">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0010-138">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="d0010-139">スタンドアロンの Exchange Online Protection の PowerShell に接続するには、「 [Exchange Online protection の powershell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0010-139">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="d0010-140">これらの手順を実行する前に、アクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0010-140">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="d0010-141">送信スパムポリシーを追加、変更、および削除するには、**組織の管理**または**セキュリティ管理者**の役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0010-141">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="d0010-142">送信スパムポリシーに対する読み取り専用アクセスでは、**セキュリティリーダー**役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0010-142">For read-only access to outbound spam policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="d0010-143">セキュリティ & コンプライアンスセンターの役割グループの詳細については、「 [Office 365 セキュリティ & コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0010-143">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="d0010-144">送信スパムポリシーの推奨設定については、「 [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0010-144">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="d0010-145">**電子メール送信の制限**が設定されている既定の[警告ポリシー](../../compliance/alert-policies.md) 、**疑わしい電子メール送信パターンが検出さ**れたこと、および電子メールが送信**Global admins**を拒否したことによって、電子メール通知が通常の送信電子メールアクティビティやブロックされたユーザーについて**は、送信**スパムによる**もの**であることを示します。</span><span class="sxs-lookup"><span data-stu-id="d0010-145">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="d0010-146">詳細については、「制限され[たユーザーの通知設定を確認する](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0010-146">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="d0010-147">送信スパムポリシーの通知オプションではなく、これらのアラートポリシーを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d0010-147">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="d0010-148">セキュリティ & コンプライアンスセンターを使用して送信スパムポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="d0010-148">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="d0010-149">セキュリティ & コンプライアンスセンターでカスタムの送信スパムポリシーを作成すると、両方に同じ名前を使用して、スパムフィルタールールと関連するスパムフィルターポリシーが同時に作成されます。</span><span class="sxs-lookup"><span data-stu-id="d0010-149">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="d0010-150">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー** \>のスパム**対策**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="d0010-150">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="d0010-151">[**スパム対策設定**] ページで、[**送信ポリシーの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0010-151">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="d0010-152">[**送信スパムフィルターポリシー** ] が表示されたら、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="d0010-152">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="d0010-153">[**名前**]: わかりやすい一意のポリシー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="d0010-153">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="d0010-154">**説明**: ポリシーの説明 (オプション) を入力します。</span><span class="sxs-lookup"><span data-stu-id="d0010-154">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="d0010-155">オプション[**通知**] セクションを展開して、疑わしい送信電子メールメッセージのコピーと通知を受信する必要がある追加のユーザーを構成します。</span><span class="sxs-lookup"><span data-stu-id="d0010-155">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="d0010-156">**疑わしい送信電子メールメッセージのコピーを特定のユーザーに送信**する: この設定を行うと、指定されたユーザーが Bcc 受信者として疑わしい送信メッセージに追加されます。</span><span class="sxs-lookup"><span data-stu-id="d0010-156">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span> <span data-ttu-id="d0010-157">この設定を有効にするには:</span><span class="sxs-lookup"><span data-stu-id="d0010-157">To enable this setting:</span></span>

     <span data-ttu-id="d0010-158">a.</span><span class="sxs-lookup"><span data-stu-id="d0010-158">a.</span></span> <span data-ttu-id="d0010-159">チェックボックスをオンにして、設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d0010-159">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="d0010-160">b.</span><span class="sxs-lookup"><span data-stu-id="d0010-160">b.</span></span> <span data-ttu-id="d0010-161">[**ユーザーの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0010-161">Click **Add people**.</span></span> <span data-ttu-id="d0010-162">[**受信者の追加または削除**] ポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0010-162">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="d0010-163">c.</span><span class="sxs-lookup"><span data-stu-id="d0010-163">c.</span></span> <span data-ttu-id="d0010-164">送信者の電子メールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="d0010-164">Enter the sender's email address.</span></span> <span data-ttu-id="d0010-165">複数の電子メールアドレスをセミコロンで区切って指定できます (;)または1行に1人の受信者。</span><span class="sxs-lookup"><span data-stu-id="d0010-165">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="d0010-166">d.</span><span class="sxs-lookup"><span data-stu-id="d0010-166">d.</span></span> <span data-ttu-id="d0010-167">[追加] アイコン</span><span class="sxs-lookup"><span data-stu-id="d0010-167">Click</span></span> ![をクリックして、DAG を作成します。](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="d0010-169">受信者を追加します。</span><span class="sxs-lookup"><span data-stu-id="d0010-169">to add the recipients.</span></span>

        <span data-ttu-id="d0010-170">必要な回数だけこれらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d0010-170">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="d0010-171">追加した受信者が、フライアウトの [**受信者リスト**] セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0010-171">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="d0010-172">受信者を削除するに![は、](../../media/scc-remove-icon.png)[削除] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0010-172">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="d0010-173">e. </span><span class="sxs-lookup"><span data-stu-id="d0010-173">e.</span></span> <span data-ttu-id="d0010-174">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0010-174">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="d0010-175">この設定を無効にするには、このチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="d0010-175">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="d0010-176">送信**スパムの送信によって送信者がブロックされた場合に、特定のユーザーに通知し**ます。</span><span class="sxs-lookup"><span data-stu-id="d0010-176">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!NOTE]
     > <span data-ttu-id="d0010-177">ユーザーが [**受信者の制限**] セクションの制限を超えたためにユーザーがブロックされた**Global admins**場合は、ユーザーによって [**送信メールが電子メール**によって制限されました] という名前の既定の[警告ポリシー](../../compliance/alert-policies.md)が、既に**tenantadmins**グループのメンバーに電子メール通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="d0010-177">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="d0010-178">送信スパムポリシーのこの設定ではなく、通知ポリシーを使用して、管理者およびその他のユーザーに通知することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d0010-178">We recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users.</span></span> <span data-ttu-id="d0010-179">手順については、「制限され[たユーザーの通知設定を確認する](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0010-179">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

     <span data-ttu-id="d0010-180">この設定を有効にするには:</span><span class="sxs-lookup"><span data-stu-id="d0010-180">To enable this setting:</span></span>

     <span data-ttu-id="d0010-181">a.</span><span class="sxs-lookup"><span data-stu-id="d0010-181">a.</span></span> <span data-ttu-id="d0010-182">チェックボックスをオンにして、設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d0010-182">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="d0010-183">b.</span><span class="sxs-lookup"><span data-stu-id="d0010-183">b.</span></span> <span data-ttu-id="d0010-184">[**ユーザーの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0010-184">Click **Add people**.</span></span> <span data-ttu-id="d0010-185">[**受信者の追加または削除**] ポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0010-185">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="d0010-186">c.</span><span class="sxs-lookup"><span data-stu-id="d0010-186">c.</span></span> <span data-ttu-id="d0010-187">送信者の電子メールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="d0010-187">Enter the sender's email address.</span></span> <span data-ttu-id="d0010-188">複数の電子メールアドレスをセミコロンで区切って指定できます (;)または1行に1人の受信者。</span><span class="sxs-lookup"><span data-stu-id="d0010-188">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="d0010-189">d.</span><span class="sxs-lookup"><span data-stu-id="d0010-189">d.</span></span> <span data-ttu-id="d0010-190">[追加] アイコン</span><span class="sxs-lookup"><span data-stu-id="d0010-190">Click</span></span> ![をクリックして、DAG を作成します。](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="d0010-192">受信者を追加します。</span><span class="sxs-lookup"><span data-stu-id="d0010-192">to add the recipients.</span></span>

        <span data-ttu-id="d0010-193">必要な回数だけこれらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d0010-193">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="d0010-194">追加した受信者が、フライアウトの [**受信者リスト**] セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0010-194">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="d0010-195">受信者を削除するに![は、](../../media/scc-remove-icon.png)[削除] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0010-195">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="d0010-196">e. </span><span class="sxs-lookup"><span data-stu-id="d0010-196">e.</span></span> <span data-ttu-id="d0010-197">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0010-197">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="d0010-198">この設定を無効にするには、このチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="d0010-198">To disable this setting, clear the check box.</span></span>

5. <span data-ttu-id="d0010-199">オプション[**受信者の制限**] セクションを展開して、疑わしい送信電子メールメッセージの制限およびアクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="d0010-199">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages: ]</span></span>
   - <span data-ttu-id="d0010-200">**ユーザーあたりの最大受信者数**</span><span class="sxs-lookup"><span data-stu-id="d0010-200">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="d0010-201">有効な値は、0 ~ 1万です。</span><span class="sxs-lookup"><span data-stu-id="d0010-201">A valid value is 0 to 10000.</span></span> <span data-ttu-id="d0010-202">既定値は0です。これは、サービスの既定値が使用されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="d0010-202">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="d0010-203">詳細については、「 [Office での制限を送信365のオプション](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0010-203">For more information, see [Sending limits across Office 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

     - <span data-ttu-id="d0010-204">**外部の時間**単位の制限: 1 時間あたりの外部受信者の最大数。</span><span class="sxs-lookup"><span data-stu-id="d0010-204">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="d0010-205">[内部最大時間**制限**数: 1 時間あたりの内部受信者の最大数。</span><span class="sxs-lookup"><span data-stu-id="d0010-205">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="d0010-206">**Daily limit**: 1 日あたりの受信者の最大合計数。</span><span class="sxs-lookup"><span data-stu-id="d0010-206">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="d0010-207">**ユーザーが上記の制限を超えた場合の対処**:**受信者の制限**のいずれかを超えた場合に実行するアクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="d0010-207">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="d0010-208">すべての操作について、ユーザーが**電子メール**通知ポリシーを送信することを制限しています (これで、送信スパムポリシーで送信スパムの設定**を送信するために送信者がブロックされている場合**は、特定のユーザーに対して特定のユーザーに指定された受信者が電子メール通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="d0010-208">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="d0010-209">**ユーザーが次の日までメールを送信**できないように制限します。これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="d0010-209">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="d0010-210">電子メール通知が送信され、ユーザーは UTC 時間に基づいて、次の日までメッセージを送信できなくなります。</span><span class="sxs-lookup"><span data-stu-id="d0010-210">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="d0010-211">管理者がこのブロックを上書きする方法はありません。</span><span class="sxs-lookup"><span data-stu-id="d0010-211">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="d0010-212">[**ユーザーが電子メールを送信**できないようにする] という名前のアクティビティアラートは、管理者に電子メールを介して通知を送信します ([通知の**表示**] ページ)。</span><span class="sxs-lookup"><span data-stu-id="d0010-212">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="d0010-213">ポリシーの送信スパム設定の**送信によって送信者がブロックされた場合**、[特定のユーザーを通知する] で指定されたすべての受信者にも通知されます。</span><span class="sxs-lookup"><span data-stu-id="d0010-213">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="d0010-214">このユーザーは、UTC 時間に基づいて、次の日まで、それ以上のメッセージを送信できなくなります。</span><span class="sxs-lookup"><span data-stu-id="d0010-214">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="d0010-215">管理者がこのブロックを上書きする方法はありません。</span><span class="sxs-lookup"><span data-stu-id="d0010-215">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="d0010-216">**ユーザーがメールを送信する**のを制限する: 電子メール通知が送信され、ユーザーはセキュリティ & コンプライアンスセンターの**<https://sip.protection.office.com/restrictedusers> [制限付きユーザー]** ポータルに追加され、ユーザーは管理者によって**制限付きユーザー**ポータルから削除されるまで電子メールを送信できません。管理者がリストからユーザーを削除した後は、その日に対してユーザーが再度制限されることはありません。</span><span class="sxs-lookup"><span data-stu-id="d0010-216">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="d0010-217">手順については、「[迷惑メールの送信後に制限付きユーザーポータルからユーザーを削除する](removing-user-from-restricted-users-portal-after-spam.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0010-217">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="d0010-218">**アクションなし、通知のみ**: 電子メール通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="d0010-218">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="d0010-219">要する[**適用先**] セクションを展開して、ポリシーが適用される内部送信者を特定します。</span><span class="sxs-lookup"><span data-stu-id="d0010-219">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="d0010-220">条件または例外は1回だけ使用できますが、条件または例外には複数の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d0010-220">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="d0010-221">同じ条件または例外の複数の値を使用するか、ロジック (たとえば、 _ \<sender1\> _または_ \<sender2\>_) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d0010-221">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="d0010-222">さまざまな条件や例外、およびロジック ( _ \<sender1\> _ 、 _ \<グループ\>1 のメンバー_など) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d0010-222">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="d0010-223">使用可能なすべての条件を表示するには、[**条件を**3 回追加する] をクリックするのが最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="d0010-223">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="d0010-224">構成しない![条件を](../../media/scc-remove-icon.png)削除するには、[削除] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0010-224">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="d0010-225">**送信者ドメイン**: 構成された1つ以上の承認済みドメインで Office 365 に送信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="d0010-225">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in Office 365.</span></span> <span data-ttu-id="d0010-226">[タグの**追加**] ボックスをクリックして、ドメインを表示および選択します。</span><span class="sxs-lookup"><span data-stu-id="d0010-226">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="d0010-227">複数のドメインが使用可能な場合は、[**タグの追加**] ボックスを再度クリックして、追加のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="d0010-227">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="d0010-228">**Sender is**: 組織内の1人または複数のユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="d0010-228">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="d0010-229">[タグの**追加**] をクリックし、入力を開始して、リストにフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="d0010-229">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="d0010-230">[**タグの追加**] ボックスをもう一度クリックして、追加の送信者を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0010-230">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="d0010-231">**送信者が次のメンバーの場合**: 組織内の1つまたは複数のグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="d0010-231">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="d0010-232">[タグの**追加**] をクリックし、入力を開始して、リストにフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="d0010-232">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="d0010-233">[**タグの追加**] ボックスをもう一度クリックして、追加の送信者を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0010-233">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="d0010-234">次の**場合を除き**、ルールの例外を追加するには、[条件を3回**追加**する] をクリックして、使用可能な例外をすべて表示します。</span><span class="sxs-lookup"><span data-stu-id="d0010-234">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="d0010-235">設定と動作は条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="d0010-235">The settings and behavior are exactly like the conditions.</span></span>

7. <span data-ttu-id="d0010-236">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0010-236">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="d0010-237">セキュリティ & コンプライアンスセンターを使用して、送信スパムポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="d0010-237">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="d0010-238">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー** \>のスパム**対策**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="d0010-238">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="d0010-239">[**スパム対策設定**] ページで、[ ![展開]](../../media/scc-expand-icon.png)アイコンをクリックして、送信スパムポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="d0010-239">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="d0010-240">**送信スパムフィルターポリシー**という名前の既定のポリシー。</span><span class="sxs-lookup"><span data-stu-id="d0010-240">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="d0010-241">作成したカスタムポリシーで、[**種類**] 列の値が [**カスタム送信スパムポリシー**] になっています。</span><span class="sxs-lookup"><span data-stu-id="d0010-241">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="d0010-242">ポリシー設定は、表示される拡張されたポリシーの詳細に表示されるか、[**ポリシーの編集**] をクリックできます。</span><span class="sxs-lookup"><span data-stu-id="d0010-242">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="d0010-243">セキュリティ & コンプライアンスセンターを使用して送信スパムポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="d0010-243">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="d0010-244">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー** \>のスパム**対策**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="d0010-244">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="d0010-245">[**スパム対策設定**] ページで、[ ![展開]](../../media/scc-expand-icon.png)アイコンをクリックして、送信スパムポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="d0010-245">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="d0010-246">**送信スパムフィルターポリシー**という名前の既定のポリシー。</span><span class="sxs-lookup"><span data-stu-id="d0010-246">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="d0010-247">作成したカスタムポリシーで、[**種類**] 列の値が [**カスタム送信スパムポリシー**] になっています。</span><span class="sxs-lookup"><span data-stu-id="d0010-247">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="d0010-248">[**ポリシーの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0010-248">Click **Edit policy**.</span></span>

<span data-ttu-id="d0010-249">カスタムの送信スパムポリシーの場合、表示されるポップアップで使用可能な設定は、「[セキュリティ & コンプライアンスセンターを使用して送信スパムポリシーを作成する](#use-the-security--compliance-center-to-create-outbound-spam-policies)」セクションに記載されている設定と同じです。</span><span class="sxs-lookup"><span data-stu-id="d0010-249">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="d0010-250">"**送信スパムフィルターポリシー**" という名前の既定の送信スパムポリシーの場合、[**適用先**] セクションは利用できません (ポリシーはすべてのユーザーに適用されます)。また、ポリシーの名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="d0010-250">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="d0010-251">ポリシーを有効または無効にしたり、ポリシーの優先順位を設定したり、エンドユーザーの検疫通知を構成したりするには、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0010-251">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="d0010-252">送信スパムポリシーを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="d0010-252">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="d0010-253">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー** \>のスパム**対策**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="d0010-253">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="d0010-254">[**スパム対策設定**] ページで、[ ![展開]](../../media/scc-expand-icon.png)アイコンをクリックして、作成したカスタムポリシーを展開します ([**種類**] 列の値は、**カスタムの送信スパムポリシー**です)。</span><span class="sxs-lookup"><span data-stu-id="d0010-254">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="d0010-255">表示される拡張されたポリシーの詳細で、 **[オン**] 列の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="d0010-255">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="d0010-256">[トグル] を左に移動して、ポリシーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="d0010-256">Move the toggle to the left to disable the policy:</span></span> ![オフに切り替える](../../media/scc-toggle-off.png)

   <span data-ttu-id="d0010-258">[トグル] を右に移動して、ポリシーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d0010-258">Move the toggle to the right to enable the policy:</span></span> ![トグルオン](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="d0010-260">既定の送信スパムポリシーを無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d0010-260">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="d0010-261">カスタム送信スパムポリシーの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="d0010-261">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="d0010-262">既定では、送信スパムポリシーには、作成された順序に基づく優先度が与えられます (新しいポリシーは、以前のポリシーよりも優先度が低いです)。</span><span class="sxs-lookup"><span data-stu-id="d0010-262">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="d0010-263">優先度の低い値は、ポリシーの優先度が高い (0 が最高である) ことを示し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは優先度の低いポリシーよりも先に処理されます)。</span><span class="sxs-lookup"><span data-stu-id="d0010-263">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="d0010-264">2 つのポリシーに同じ優先度を設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="d0010-264">No two policies can have the same priority.</span></span>

<span data-ttu-id="d0010-265">カスタム送信スパムポリシーは、処理順に表示されます (最初のポリシーの**優先度**値は0です)。</span><span class="sxs-lookup"><span data-stu-id="d0010-265">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="d0010-266">"**送信スパムフィルターポリシー** " という名前の既定の送信スパムポリシーは、優先度の値が**低い**ので、これを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="d0010-266">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="d0010-267">ポリシーの優先度を変更するには、リスト内でポリシーを上下に移動します (セキュリティ & コンプライアンスセンターで**優先度**番号を直接変更することはできません)。</span><span class="sxs-lookup"><span data-stu-id="d0010-267">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="d0010-268">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー** \>のスパム**対策**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="d0010-268">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="d0010-269">[**スパム対策設定**] ページで、[**種類**] 列の値が**カスタム送信スパムポリシー**であるポリシーを探します。</span><span class="sxs-lookup"><span data-stu-id="d0010-269">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="d0010-270">[**優先度**] 列の値に注目してください。</span><span class="sxs-lookup"><span data-stu-id="d0010-270">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="d0010-271">優先度が最も高いカスタムの送信スパムポリシーには![、値の](../../media/ITPro-EAC-DownArrowIcon.png)下矢印アイコン**0**があります。</span><span class="sxs-lookup"><span data-stu-id="d0010-271">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="d0010-272">最も低い優先度を持つカスタムの送信スパムポリシーに![は、上矢印アイコン](../../media/ITPro-EAC-UpArrowIcon.png) **n** ( ![上矢印アイコン](../../media/ITPro-EAC-UpArrowIcon.png) **3**) の値が設定されています。</span><span class="sxs-lookup"><span data-stu-id="d0010-272">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="d0010-273">ユーザー設定の送信スパムポリシーが3つ以上ある場合、最高の優先度と最も低い優先![順位の間](../../media/ITPro-EAC-UpArrowIcon.png)![のポリシーは](../../media/ITPro-EAC-DownArrowIcon.png) 、上矢印アイコンの![下矢印アイコン](../../media/ITPro-EAC-UpArrowIcon.png)![ **n** (たとえば](../../media/ITPro-EAC-DownArrowIcon.png) 、上矢印アイコンを下矢印アイコン**2**) に設定します。</span><span class="sxs-lookup"><span data-stu-id="d0010-273">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="d0010-274">[追加] アイコン</span><span class="sxs-lookup"><span data-stu-id="d0010-274">Click</span></span> ![上矢印アイコン](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="d0010-276">or</span><span class="sxs-lookup"><span data-stu-id="d0010-276">or</span></span> ![下矢印アイコン](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="d0010-278">を押して、カスタムの送信スパムポリシーを優先順位一覧で上または下に移動します。</span><span class="sxs-lookup"><span data-stu-id="d0010-278">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="d0010-279">セキュリティ & コンプライアンスセンターを使用して送信スパムポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="d0010-279">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="d0010-280">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー** \>のスパム**対策**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="d0010-280">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="d0010-281">[**スパム対策設定**] ページで、[ ![展開]](../../media/scc-expand-icon.png)アイコンをクリックして、削除するカスタムポリシーを展開します ( **Type**列は**カスタム送信スパムポリシー**です)。</span><span class="sxs-lookup"><span data-stu-id="d0010-281">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="d0010-282">表示される拡張されたポリシーの詳細で、[**ポリシーの削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0010-282">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="d0010-283">表示される警告ダイアログで [**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0010-283">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="d0010-284">既定のポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="d0010-284">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="d0010-285">Exchange Online PowerShell または Exchange Online Protection PowerShell を使用して送信スパムポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="d0010-285">Use Exchange Online PowerShell or Exchange Online Protection PowerShell to configure outbound spam policies</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="d0010-286">PowerShell を使用して送信スパムポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="d0010-286">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="d0010-287">PowerShell で送信スパムポリシーを作成するには、2つの手順からなるプロセスがあります。</span><span class="sxs-lookup"><span data-stu-id="d0010-287">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="d0010-288">送信スパムフィルターポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d0010-288">Create the outbound spam filter policy.</span></span>

2. <span data-ttu-id="d0010-289">ルールを適用する送信スパムフィルターポリシーを指定する送信スパムフィルタールールを作成します。</span><span class="sxs-lookup"><span data-stu-id="d0010-289">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="d0010-290">**注**:</span><span class="sxs-lookup"><span data-stu-id="d0010-290">**Notes**:</span></span>

- <span data-ttu-id="d0010-291">新しい送信スパムフィルタールールを作成して、関連付けられていない既存の送信スパムフィルターポリシーをそれに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d0010-291">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="d0010-292">送信スパムフィルタールールは、複数の送信スパムフィルターポリシーに関連付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="d0010-292">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="d0010-293">ポリシーを作成するまでは、セキュリティ & コンプライアンスセンターでは使用できない PowerShell の新しい送信スパムフィルターポリシーに対して、次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="d0010-293">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="d0010-294">新しいポリシーを無効として作成します ( **HostedOutboundSpamFilterRule**コマンドレットでは_有効_ `$false` )。</span><span class="sxs-lookup"><span data-stu-id="d0010-294">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

  - <span data-ttu-id="d0010-295">**HostedOutboundSpamFilterRule**コマンドレットで、作成中にポリシーの優先度を設定します (_優先度_ _ \<番号\>_)。</span><span class="sxs-lookup"><span data-stu-id="d0010-295">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="d0010-296">PowerShell で作成した新しい送信スパムフィルターポリシーは、そのポリシーをスパムフィルタールールに割り当てるまで、セキュリティ & コンプライアンスセンターに表示されません。</span><span class="sxs-lookup"><span data-stu-id="d0010-296">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="d0010-297">手順 1: PowerShell を使用して送信スパムフィルターポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="d0010-297">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="d0010-298">送信スパムフィルターポリシーを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d0010-298">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="d0010-299">この例では、次の設定を使用して Contoso 重役という新しい送信スパムフィルターポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d0010-299">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="d0010-300">受信者数の制限は、既定値より小さい値に制限されます。</span><span class="sxs-lookup"><span data-stu-id="d0010-300">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="d0010-301">詳細については、「 [Office での制限を送信365のオプション](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0010-301">For more information, see [Sending limits across Office 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="d0010-302">いずれかの制限に達すると、ユーザーはメッセージを送信できなくなります。</span><span class="sxs-lookup"><span data-stu-id="d0010-302">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="d0010-303">構文およびパラメーターの詳細については、「 [HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0010-303">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="d0010-304">手順 2: PowerShell を使用して送信スパムフィルタールールを作成する</span><span class="sxs-lookup"><span data-stu-id="d0010-304">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="d0010-305">送信スパムフィルタールールを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d0010-305">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="d0010-306">この例では、次の設定を使用して Contoso 重役という新しい送信スパムフィルタールールを作成します。</span><span class="sxs-lookup"><span data-stu-id="d0010-306">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="d0010-307">Contoso エグゼクティブという名前の送信スパムフィルターポリシーがルールに関連付けられている。</span><span class="sxs-lookup"><span data-stu-id="d0010-307">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="d0010-308">ルールは、Contoso 重役グループというグループのメンバーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d0010-308">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="d0010-309">構文およびパラメーターの詳細については、「 [HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0010-309">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="d0010-310">PowerShell を使用して送信スパムフィルターポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="d0010-310">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="d0010-311">すべての送信スパムフィルターポリシーの要約リストを返すには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d0010-311">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="d0010-312">特定の送信スパムフィルターポリシーの詳細情報を戻すには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d0010-312">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="d0010-313">この例では、重役という送信スパムフィルターポリシーのすべてのプロパティ値を返します。</span><span class="sxs-lookup"><span data-stu-id="d0010-313">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="d0010-314">構文およびパラメーターの詳細については、「 [HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0010-314">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="d0010-315">PowerShell を使用して送信スパムフィルタールールを表示する</span><span class="sxs-lookup"><span data-stu-id="d0010-315">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="d0010-316">既存の送信スパムフィルタールールを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d0010-316">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="d0010-317">すべての送信スパムフィルタールールの要約リストを返すには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d0010-317">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="d0010-318">有効または無効なルールで一覧をフィルター処理するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d0010-318">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="d0010-319">特定の送信スパムフィルタールールに関する詳細情報を戻すには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d0010-319">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="d0010-320">この例では、Contoso 重役という送信スパムフィルタールールのすべてのプロパティ値を返します。</span><span class="sxs-lookup"><span data-stu-id="d0010-320">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="d0010-321">構文およびパラメーターの詳細については、「 [HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0010-321">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="d0010-322">PowerShell を使用して送信スパムフィルターポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="d0010-322">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="d0010-323">このトピックで前述した「[手順 1: powershell を使用して送信スパムフィルターポリシーを作成](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy)する」の説明に従って、ポリシーの作成時に powershell のマルウェアフィルターポリシーを変更する場合にも、同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d0010-323">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this topic.</span></span>

<span data-ttu-id="d0010-324">**注**: 送信スパムフィルターポリシーの名前を変更することはできません ( **HostedOutboundSpamFilterPolicy**コマンドレットに_Name_パラメーターがありません)。</span><span class="sxs-lookup"><span data-stu-id="d0010-324">**Note**: You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="d0010-325">セキュリティ & コンプライアンスセンターで送信スパムポリシーの名前を変更する場合は、送信スパムフィルター_ルール_の名前のみを変更しています。</span><span class="sxs-lookup"><span data-stu-id="d0010-325">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="d0010-326">送信スパムフィルターポリシーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d0010-326">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="d0010-327">構文およびパラメーターの詳細については、「 [HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0010-327">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="d0010-328">PowerShell を使用して送信スパムフィルタールールを変更する</span><span class="sxs-lookup"><span data-stu-id="d0010-328">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="d0010-329">PowerShell で送信スパムフィルタールールを変更するときには使用できない唯一の設定は、無効にされたルールを作成できる_有効_なパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="d0010-329">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="d0010-330">既存の送信スパムフィルタールールを有効または無効にするには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0010-330">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="d0010-331">それ以外の場合は、PowerShell で送信スパムフィルタールールを変更するときに、追加の設定を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d0010-331">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="d0010-332">このトピックで前述した「[手順 2: PowerShell を使用して送信スパムフィルタールールを作成する](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule)」で説明されているように、ルールを作成する場合にも同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d0010-332">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="d0010-333">送信スパムフィルタールールを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d0010-333">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="d0010-334">構文およびパラメーターの詳細については、「 [HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0010-334">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="d0010-335">PowerShell を使用して送信スパムフィルタールールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="d0010-335">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="d0010-336">PowerShell で送信スパムフィルタールールを有効または無効にすると、送信スパムポリシー全体 (送信スパムフィルタールールおよび割り当てられた送信スパムフィルターポリシー) が有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="d0010-336">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="d0010-337">既定の送信スパムポリシーを有効または無効にすることはできません (常にすべての受信者に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="d0010-337">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="d0010-338">PowerShell で送信スパムフィルタールールを有効または無効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d0010-338">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="d0010-339">この例では、Marketing Department という名前の送信スパムフィルタールールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="d0010-339">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="d0010-340">この例では、同じルールを有効化します。</span><span class="sxs-lookup"><span data-stu-id="d0010-340">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="d0010-341">構文およびパラメーターの詳細については、「 [HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedoutboundspamfilterrule) 」および「 [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedoutboundspamfilterrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0010-341">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="d0010-342">PowerShell を使用して送信スパムフィルタールールの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="d0010-342">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="d0010-343">ルールに設定できる優先度の最高値値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="d0010-343">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="d0010-344">設定できる最低値はルールの数に依存します。</span><span class="sxs-lookup"><span data-stu-id="d0010-344">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="d0010-345">たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。</span><span class="sxs-lookup"><span data-stu-id="d0010-345">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="d0010-346">既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。</span><span class="sxs-lookup"><span data-stu-id="d0010-346">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="d0010-347">たとえば、5つのカスタムルール (優先度 0 ~ 4) があり、ルールの優先度を2に変更した場合、優先度2の既存のルールは優先度3に変更され、優先度3のルールは優先度4に変更されます。</span><span class="sxs-lookup"><span data-stu-id="d0010-347">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="d0010-348">PowerShell で送信スパムフィルタールールの優先度を設定するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d0010-348">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="d0010-p146">この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。</span><span class="sxs-lookup"><span data-stu-id="d0010-p146">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="d0010-351">**注**:</span><span class="sxs-lookup"><span data-stu-id="d0010-351">**Notes**:</span></span>

- <span data-ttu-id="d0010-352">新しいルールの作成時に優先度を設定するには、代わりに**HostedOutboundSpamFilterRule**コマンドレットで_priority_パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="d0010-352">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>

- <span data-ttu-id="d0010-353">既定の送信スパムフィルターポリシーには、対応するスパムフィルタールールがありません。また、常に、未設定の優先度の値が**最低**になっています。</span><span class="sxs-lookup"><span data-stu-id="d0010-353">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="d0010-354">PowerShell を使用して送信スパムフィルターポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="d0010-354">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="d0010-355">PowerShell を使用して送信スパムフィルターポリシーを削除しても、それに対応する送信スパムフィルタールールは削除されません。</span><span class="sxs-lookup"><span data-stu-id="d0010-355">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="d0010-356">PowerShell で送信スパムフィルターポリシーを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d0010-356">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="d0010-357">この例では、Marketing Department という名前の送信スパムフィルターポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="d0010-357">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="d0010-358">構文およびパラメーターの詳細については、「 [HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0010-358">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="d0010-359">PowerShell を使用して送信スパムフィルタールールを削除する</span><span class="sxs-lookup"><span data-stu-id="d0010-359">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="d0010-360">PowerShell を使用して送信スパムフィルタールールを削除しても、対応する送信スパムフィルターポリシーは削除されません。</span><span class="sxs-lookup"><span data-stu-id="d0010-360">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="d0010-361">PowerShell で送信スパムフィルタールールを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d0010-361">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="d0010-362">この例では、Marketing Department という名前の送信スパムフィルタールールを削除します。</span><span class="sxs-lookup"><span data-stu-id="d0010-362">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="d0010-363">構文およびパラメーターの詳細については、「 [HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0010-363">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterrule).</span></span>


## <a name="for-more-information"></a><span data-ttu-id="d0010-364">関連情報</span><span class="sxs-lookup"><span data-stu-id="d0010-364">For more information</span></span>

[<span data-ttu-id="d0010-365">迷惑メールを送信した後で制限付きユーザー ポータルからユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="d0010-365">Removing a user from the Restricted Users portal after sending spam email</span></span>](https://docs.microsoft.com/office365/SecurityCompliance/removing-user-from-restricted-users-portal-after-spam)

[<span data-ttu-id="d0010-366">送信メッセージにおける危険度の高い配信プール</span><span class="sxs-lookup"><span data-stu-id="d0010-366">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="d0010-367">スパム対策保護に関してよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="d0010-367">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
