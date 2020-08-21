---
title: 送信スパム フィルターの構成
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) で送信スパム ポリシーを表示、作成、変更、削除する方法を学習できます。
ms.openlocfilehash: 530c1af9b7802be6073f19331ce7f6a20bdb2668
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845980"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="fafaf-103">EOP で送信スパム フィルターを構成する</span><span class="sxs-lookup"><span data-stu-id="fafaf-103">Configure outbound spam filtering in EOP</span></span>

<span data-ttu-id="fafaf-104">Exchange Online にメールボックスを含む Microsoft 365 組織、または Exchange Online のメールボックスを使用しているスタンドアロン Exchange Online Protection (EOP) 組織では、EOP 経由で送信される送信電子メール メッセージに対してスパム メッセージと異法な送信処理が自動的にチェックされます。</span><span class="sxs-lookup"><span data-stu-id="fafaf-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="fafaf-105">組織内のユーザーからの送信スパムは、通常、アカウントの侵害を示しています。</span><span class="sxs-lookup"><span data-stu-id="fafaf-105">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="fafaf-106">不審な送信メッセージは (Spam Confidence Level や SCL に関係なく) スパムとしてマークされ、サービスの評価[high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md)を保護するためにリスクの高い配信プールを経由してルーティングされます (つまり、Microsoft 365 ソースの電子メール サーバーを IP 禁止リストに含める)。</span><span class="sxs-lookup"><span data-stu-id="fafaf-106">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="fafaf-107">管理者は、送信電子メール アクティビティについて自動的に通知され、ユーザーは警告ポリシーによって [ブロックされます](../../compliance/alert-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="fafaf-107">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="fafaf-108">EOP では、スパムに対する組織の全体的な防が層として送信スパム ポリシーを使用する。</span><span class="sxs-lookup"><span data-stu-id="fafaf-108">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="fafaf-109">詳細については、「[スパム対策保護](anti-spam-protection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fafaf-109">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="fafaf-110">管理者は、既定の送信スパム ポリシーを表示、編集、構成できます (削除はできません)。</span><span class="sxs-lookup"><span data-stu-id="fafaf-110">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="fafaf-111">さらにきめ細かく計画する場合は、組織内の特定のユーザー、グループ、またはドメインに適用するカスタムの送信スパム ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="fafaf-111">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="fafaf-112">カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (実行順序) を変更できます。</span><span class="sxs-lookup"><span data-stu-id="fafaf-112">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="fafaf-113">送信スパム ポリシーは、セキュリティ & コンプライアンス センターまたは PowerShell (Exchange Online にメールボックスを持つ Microsoft 365 組織用の Exchange Online PowerShell、Exchange Online メールボックスを持つ組織のスタンドアロン EOP PowerShell) で構成できます。</span><span class="sxs-lookup"><span data-stu-id="fafaf-113">You can configure outbound spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="fafaf-114">EOP の送信スパム ポリシーの基本的な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fafaf-114">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="fafaf-115">**送信スパム フィルター ポリシー**: 送信スパム対策フィルターの確認と通知オプションのアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-115">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="fafaf-116">**送信スパム フィルター ルール**: 送信スパム フィルター ポリシーの優先順位と受信者フィルター (ポリシーが適用される対象者) を指定します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-116">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="fafaf-117">これら 2 つの要素の違いは、セキュリティ/コンプライアンス センターで送信スパム ポリシーを管理する際には&にくいです。</span><span class="sxs-lookup"><span data-stu-id="fafaf-117">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="fafaf-118">ポリシーを作成した後、実際には送信スパム フィルター ルールと、関連付けられた送信スパム フィルター ポリシーを両方に同じ名前を使用して同時に作成しています。</span><span class="sxs-lookup"><span data-stu-id="fafaf-118">When you create a policy, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="fafaf-119">ポリシーを変更すると、名前、優先順位、有効/無効の設定、および受信者フィルターに関連する設定は、送信スパム フィルター ルールを変更します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="fafaf-120">他のすべての設定では、関連付けられた送信スパム フィルター ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-120">All other settings modify the associated outbound spam filter policy.</span></span>
- <span data-ttu-id="fafaf-121">ポリシーを削除すると、送信スパム フィルター ルールおよび関連付けられた送信スパム フィルター ポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="fafaf-121">When you remove a policy, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="fafaf-122">Exchange Online PowerShell またはスタンドアロン EOP PowerShell では、ポリシーとルールを個別に管理します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="fafaf-123">詳細については、このトピックで後 [述する「Exchange Online PowerShell またはスタンドアロン EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) を使用して送信スパム ポリシー」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fafaf-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) section later in this topic.</span></span>

<span data-ttu-id="fafaf-124">各組織には Default という名前の組み込みの送信スパム ポリシーがあり、以下のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="fafaf-124">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="fafaf-125">ポリシーに関連付けられた送信スパム フィルター ルール (受信者フィルター) がない場合でも、ポリシーは組織内のすべての受信者に適用されます。</span><span class="sxs-lookup"><span data-stu-id="fafaf-125">The policy is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="fafaf-126">ポリシーにはカスタムの優先順位の値 **Lowest** が設定されており、変更することはできません (このポリシーは常に最後に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="fafaf-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="fafaf-127">作成するどのカスタム ポリシーも、Default という名前のポリシーより高い優先順位を持ちます。</span><span class="sxs-lookup"><span data-stu-id="fafaf-127">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>
- <span data-ttu-id="fafaf-128">ポリシーは既定のポリシー (**IsDefault** のプロパティが `True` の値になっている) であり、既定のポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="fafaf-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="fafaf-129">送信スパム フィルターの効果を高い方法で使用するには、特定のユーザーまたはユーザー グループに適用される、高い設定を持つ送信スパム ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="fafaf-129">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="fafaf-130">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="fafaf-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="fafaf-131"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="fafaf-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="fafaf-132">**[スパム対策の設定]** ページに直接移動するには、<https://protection.office.com/antispam> を使用します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-132">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="fafaf-133">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fafaf-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="fafaf-134">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fafaf-134">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="fafaf-135">このトピックの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="fafaf-135">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="fafaf-136">送信スパム ポリシーを追加、変更、削除するには、次の役割グループのいずれかのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="fafaf-136">To add, modify, and delete outbound spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="fafaf-137">**組織の管理**または[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ管理者**。</span><span class="sxs-lookup"><span data-stu-id="fafaf-137">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="fafaf-138">**組織の管理**または [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**検疫管理**。</span><span class="sxs-lookup"><span data-stu-id="fafaf-138">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="fafaf-139">送信スパム ポリシーに読み取り専用アクセスするには、次の役割グループのいずれかのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="fafaf-139">For read-only access to outbound spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="fafaf-140">[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ閲覧者**。</span><span class="sxs-lookup"><span data-stu-id="fafaf-140">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="fafaf-141">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**表示限定の組織管理**。</span><span class="sxs-lookup"><span data-stu-id="fafaf-141">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="fafaf-142">送信スパム ポリシーに推奨される設定については [、「EOP 送信スパム フィルター ポリシーの設定」を参照してください](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="fafaf-142">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="fafaf-143">電子メール送信[の制限](../../compliance/alert-policies.md)**を超え、\*\*\*\*不**審な電子メール送信パターンが検出され、**ユーザーが**、通常の送信メール アクティビティと送信スパムによってブロックされているユーザーに関しては既にメール通知を**TenantAdmins** (**グローバル**管理者) グループのメンバーに送信できませんでした。</span><span class="sxs-lookup"><span data-stu-id="fafaf-143">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="fafaf-144">詳細については、「制限付き [ユーザーのアラート設定を確認する」を参照してください](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。</span><span class="sxs-lookup"><span data-stu-id="fafaf-144">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="fafaf-145">送信スパム ポリシーの通知オプションの代わりに、これらのアラート ポリシーを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fafaf-145">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="fafaf-146">セキュリティ コンプライアンス センターを&、送信スパム ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="fafaf-146">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="fafaf-147">セキュリティ & コンプライアンス センターでカスタムの送信スパム ポリシーを作成する場合、スパム フィルター ルールと、関連付けられているスパム フィルター ポリシーを両方とも同じ名前で同時に作成します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-147">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="fafaf-148">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-148">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="fafaf-149">[スパム **対策の設定] ページで** 、[ **送信ポリシーの作成] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="fafaf-149">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="fafaf-150">送信スパム **フィルター ポリシー ポップアップが** 開いたら、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-150">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="fafaf-151">**[名前]**: わかりやすい一意のポリシー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-151">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="fafaf-152">**[説明]**: ポリシーについての説明を入力します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="fafaf-152">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="fafaf-153">(省略可能)[通知 **] セクション** を展開して、不審な送信電子メール メッセージのコピーと通知を受信する必要がある追加のユーザーを構成します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-153">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="fafaf-154">**不審な送信電子メール メッセージのコピーを特定のユーザーに送信します**。 この設定により、指定されたユーザーを BCC 受信者として不審な送信メッセージに追加します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-154">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span>

     > [!NOTE]
     > <span data-ttu-id="fafaf-155">この設定は既定の送信スパム ポリシーでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-155">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="fafaf-156">作成したカスタム送信スパム ポリシーでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="fafaf-156">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="fafaf-157">この設定を有効にするには:</span><span class="sxs-lookup"><span data-stu-id="fafaf-157">To enable this setting:</span></span>

     1. <span data-ttu-id="fafaf-158">設定を有効にするには、チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="fafaf-158">Select the check box to enable the setting.</span></span>

     1. <span data-ttu-id="fafaf-159">[ユーザー **の追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="fafaf-159">Click **Add people**.</span></span> <span data-ttu-id="fafaf-160">表示される **受信者を追加または** 削除するポップアップで、次の手順に示します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-160">In the **Add or remove recipients** flyout that appears:</span></span>

     1. <span data-ttu-id="fafaf-161">送信者の電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-161">Enter the sender's email address.</span></span> <span data-ttu-id="fafaf-162">複数のメール アドレスをセミコロン (.) で区切って指定;)または 1 行に 1 受信者を追加します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-162">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     1. <span data-ttu-id="fafaf-163">Click</span><span class="sxs-lookup"><span data-stu-id="fafaf-163">Click</span></span> ![[追加] アイコン](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="fafaf-165">をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fafaf-165">to add the recipients.</span></span>

        <span data-ttu-id="fafaf-166">必要な回数だけこれらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-166">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="fafaf-167">追加した受信者は、ポップアップ **の受信者** リスト セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fafaf-167">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="fafaf-168">受信者を削除するには、[削除] ![ ボタンをクリックします ](../../media/scc-remove-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="fafaf-168">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     1. <span data-ttu-id="fafaf-169">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fafaf-169">When you're finished, click **Save**.</span></span>

        <span data-ttu-id="fafaf-170">この設定を無効にするには、このチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="fafaf-170">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="fafaf-171">**送信スパムの送信によって送信者がブロックされている場合は、特定のユーザーに通知します**。</span><span class="sxs-lookup"><span data-stu-id="fafaf-171">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!IMPORTANT]
     >
     > - <span data-ttu-id="fafaf-172">この設定は、送信スパム ポリシーからの廃止処理中です。</span><span class="sxs-lookup"><span data-stu-id="fafaf-172">This setting is in the process of being deprecated from outbound spam policies.</span></span>
     >
     > - <span data-ttu-id="fafaf-173">「受信者 [の制限」セクション](../../compliance/alert-policies.md) の制限を超過したために **ユーザーがブロック** されている場合、ユーザーが **ブロックされているときには、"User** Limits/**受信者の**制限" グループのメンバーに対しては既にメール通知 **を送信していない** という名前の既定のアラート ポリシー。</span><span class="sxs-lookup"><span data-stu-id="fafaf-173">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="fafaf-174">**管理者や他のユーザーに通知するには、送信スパム ポリシーでこの設定を使用するのではなく、アラート ポリシーを使用するように強くお勧めします**。</span><span class="sxs-lookup"><span data-stu-id="fafaf-174">**We strongly recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users**.</span></span> <span data-ttu-id="fafaf-175">手順については、「制限付き [ユーザーのアラート設定を確認する」を参照してください](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。</span><span class="sxs-lookup"><span data-stu-id="fafaf-175">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

5. <span data-ttu-id="fafaf-176">(省略可能)[受信者 **の制限]** セクションを展開して、不審な送信電子メール メッセージの制限とアクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-176">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="fafaf-177">これらの設定は、クラウドベースのメールボックスにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="fafaf-177">These settings are only applicable to cloud-based mailboxes.</span></span>

   - <span data-ttu-id="fafaf-178">**ユーザーあたりの最大受信者数**</span><span class="sxs-lookup"><span data-stu-id="fafaf-178">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="fafaf-179">有効な値は 0 から 10000 です。</span><span class="sxs-lookup"><span data-stu-id="fafaf-179">A valid value is 0 to 10000.</span></span> <span data-ttu-id="fafaf-180">既定値は 0 で、サービスの既定値が使用されるという意味です。</span><span class="sxs-lookup"><span data-stu-id="fafaf-180">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="fafaf-181">詳細については、「送信の制限 [」を参照してください](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)。</span><span class="sxs-lookup"><span data-stu-id="fafaf-181">For more information, see [Sending limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

     - <span data-ttu-id="fafaf-182">**外部時間限値**: 1 時間あたりの外部受信者の最大数。</span><span class="sxs-lookup"><span data-stu-id="fafaf-182">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="fafaf-183">**内部時間制限 :** 1 時間あたりの内部受信者の最大数。</span><span class="sxs-lookup"><span data-stu-id="fafaf-183">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="fafaf-184">**1 日あたりの制限**: 1 日あたりの受信者の最大数。</span><span class="sxs-lookup"><span data-stu-id="fafaf-184">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="fafaf-185">**ユーザーが上記の制限を超えた**場合の処理: 受信者の制限のいずれかを超えた場合に実行 **するアクション** を構成する</span><span class="sxs-lookup"><span data-stu-id="fafaf-185">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="fafaf-186">すべてのアクションで、ユーザーに指定されている受信者**User restricted from sending email**がメールアラート ポリシーを送信できなくなります (さらに、送信スパム ポリシー**Notify specific people if a sender is blocked due to sending outbound spam**の送信スパム設定を送信したために送信者がブロックされている場合は、特定のユーザーに通知を受信します)。</span><span class="sxs-lookup"><span data-stu-id="fafaf-186">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="fafaf-187">**ユーザーが次の日にメールを送信するのを制限**します。これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="fafaf-187">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="fafaf-188">電子メール通知が送信され、ユーザーは UTC 時間に基づいて、次の日付までメッセージを送信できません。</span><span class="sxs-lookup"><span data-stu-id="fafaf-188">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="fafaf-189">管理者がこのブロックを上書きする方法はありません。</span><span class="sxs-lookup"><span data-stu-id="fafaf-189">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="fafaf-190">メール送信を制限 **された [ユーザー] というアクティビティ アラート** は、(メールおよびアラートの表示ページで) 管理者 **に通知** します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-190">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="fafaf-191">ポリシーの送信スパム設定 **の送信によって送信者がブロックされている場合** 、指定した受信者もすべて通知されます。</span><span class="sxs-lookup"><span data-stu-id="fafaf-191">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="fafaf-192">ユーザーは、UTC 時間に基づいて、次の日付までメッセージを送信できません。</span><span class="sxs-lookup"><span data-stu-id="fafaf-192">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="fafaf-193">管理者がこのブロックを上書きする方法はありません。</span><span class="sxs-lookup"><span data-stu-id="fafaf-193">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="fafaf-194">**ユーザーがメールを送信するのを制限**する: 電子メール通知が送信されます。ユーザーはセキュリティ & コンプライアンス センターの \*\*[制限 <https://sip.protection.office.com/restrictedusers> \*\*付きユーザー] ポータルに追加され、管理者が制限されたユーザー ポータルからユーザーが削除されるまで **、ユーザーはメール**を送信できません。管理者が一覧からユーザーを削除した後、その日に対して再び制限されるわけになります。</span><span class="sxs-lookup"><span data-stu-id="fafaf-194">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="fafaf-195">詳細については、「スパム メール [を送信した後で制限付きユーザー」 ポータルからユーザーを削除する」を参照してください](removing-user-from-restricted-users-portal-after-spam.md)。</span><span class="sxs-lookup"><span data-stu-id="fafaf-195">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="fafaf-196">**操作なし、アラートのみ**: 電子メール通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="fafaf-196">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="fafaf-197">(省略可能)[ **自動転送] セクションを** 展開し、外部送信者へのユーザーによる自動転送を制御します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-197">(Optional) Expand **Automatic forwarding** section to control automatic email forwarding by users to external senders.</span></span> <span data-ttu-id="fafaf-198">自動転送の詳細については、「メール転送を [構成する」を参照してください](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding)。</span><span class="sxs-lookup"><span data-stu-id="fafaf-198">For more information about automatic forwarding, see [Configure email forwarding](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="fafaf-199">2020 年 9 月前には、これらの設定は使用できますが、強制されません。</span><span class="sxs-lookup"><span data-stu-id="fafaf-199">Before September 2020, these settings are available but not enforced.</span></span>
   >
   > - <span data-ttu-id="fafaf-200">これらの設定は、クラウドベースのメールボックスにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="fafaf-200">These settings apply only to cloud-based mailboxes.</span></span>
   >
   > - <span data-ttu-id="fafaf-201">内部受信者への自動転送は、これらの設定の影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="fafaf-201">Automatic forwarding to internal recipients is not affected by these setting.</span></span>

   <span data-ttu-id="fafaf-202">使用できる値は次のとおりです:</span><span class="sxs-lookup"><span data-stu-id="fafaf-202">The available values are:</span></span>

   - <span data-ttu-id="fafaf-203">**自動 - システム管理: 外部電子**メールの自動転送を制御するために送信スパム フィルタリングを許可します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-203">**Automatic - System-controlled**: Allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="fafaf-204">これは既定の値です。</span><span class="sxs-lookup"><span data-stu-id="fafaf-204">This is the default value.</span></span>

   - <span data-ttu-id="fafaf-205">**On:** 外部メール転送がポリシーによって無効化されていない。</span><span class="sxs-lookup"><span data-stu-id="fafaf-205">**On**: Automatic external email forwarding is not disabled by the policy.</span></span>

   - <span data-ttu-id="fafaf-206">**Off:** 外部メールの自動転送はすべてポリシーによって無効になります。</span><span class="sxs-lookup"><span data-stu-id="fafaf-206">**Off**: All automatic external email forwarding is disabled by the policy.</span></span>

7. <span data-ttu-id="fafaf-207">(必須)[ **適用対象] セクション** を展開して、ポリシーが適用される内部送信者を特定します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-207">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="fafaf-208">各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="fafaf-208">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="fafaf-209">同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<sender1\>_ または _\<sender2\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="fafaf-209">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="fafaf-210">a別の条件や例外がある場合は AND ロジック (たとえば、_\<sender1\>_ かつ _\<member of group 1\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="fafaf-210">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="fafaf-211">使用可能なすべての条件を表示するには、**[条件の追加]** を 3 回クリックするのが最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="fafaf-211">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="fafaf-212">構成しない条件を削除するには、![[削除] ボタン](../../media/scc-remove-icon.png)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fafaf-212">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="fafaf-213">**送信者ドメインが次の**場合: 組織内で構成済みの承認済みドメインの 1 つ以上の送信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-213">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in the organization.</span></span> <span data-ttu-id="fafaf-214">**[タグの追加]** ボックスをクリックして、ドメインを表示および選択します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-214">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="fafaf-215">複数のドメインが利用可能な場合は、**[タグの追加]** ボックスをもう一度クリックして、追加のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-215">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="fafaf-216">**送信者]**: 組織内の 1 人または複数のユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-216">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="fafaf-217">**[タグの追加]** をクリックして、リストをフィルター処理するための入力を始めます。</span><span class="sxs-lookup"><span data-stu-id="fafaf-217">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="fafaf-218">もう一度 [ **タグの追加] ボックスを** クリックして、追加の送信者を選択します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-218">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="fafaf-219">**Sender が次のメンバーの場合**: 組織内の 1 つまたは複数のグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-219">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="fafaf-220">**[タグの追加]** をクリックして、リストをフィルター処理するための入力を始めます。</span><span class="sxs-lookup"><span data-stu-id="fafaf-220">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="fafaf-221">もう一度 [ **タグの追加] ボックスを** クリックして、追加の送信者を選択します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-221">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="fafaf-222">**次の場合を除く**: ルールの例外を追加するには、**[条件の追加]** を 3 回クリックして、使用可能なすべての例外を表示します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-222">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="fafaf-223">設定と動作は、条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="fafaf-223">The settings and behavior are exactly like the conditions.</span></span>

8. <span data-ttu-id="fafaf-224">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fafaf-224">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="fafaf-225">セキュリティ/コンプライアンス センターを&使用して送信スパム ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="fafaf-225">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="fafaf-226">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-226">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="fafaf-227">[スパム **対策の設定] ページで、[** 展開] ![ アイコン ](../../media/scc-expand-icon.png) をクリックして送信スパム ポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-227">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="fafaf-228">送信スパム フィルター ポリシーという **名前の既定ポリシー**。</span><span class="sxs-lookup"><span data-stu-id="fafaf-228">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="fafaf-229">[種類] 列の値が「カスタムの **送信スパム** ポリシー」 **である場所に作成したカスタム ポリシー**。</span><span class="sxs-lookup"><span data-stu-id="fafaf-229">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="fafaf-230">展開されたポリシー詳細にポリシー設定が表示されるか、ポリシーの編集を **クリックすることができます**。</span><span class="sxs-lookup"><span data-stu-id="fafaf-230">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="fafaf-231">セキュリティ コンプライアンス センターを&変更して送信スパム ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="fafaf-231">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="fafaf-232">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-232">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="fafaf-233">[スパム **対策の設定] ページで、[** 展開] ![ アイコン ](../../media/scc-expand-icon.png) をクリックして送信スパム ポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-233">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="fafaf-234">送信スパム フィルター ポリシーという **名前の既定ポリシー**。</span><span class="sxs-lookup"><span data-stu-id="fafaf-234">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="fafaf-235">[種類] 列の値が「カスタムの **送信スパム** ポリシー」 **である場所に作成したカスタム ポリシー**。</span><span class="sxs-lookup"><span data-stu-id="fafaf-235">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="fafaf-236">**[ポリシーの編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fafaf-236">Click **Edit policy**.</span></span>

<span data-ttu-id="fafaf-237">カスタム送信スパム ポリシーの場合、表示されるポップアップで使用できる設定は、「セキュリティ & コンプライアンス センターを使用して送信スパム ポリシーを作成 [する」セクションで説明されている設定と同じ](#use-the-security--compliance-center-to-create-outbound-spam-policies) です。</span><span class="sxs-lookup"><span data-stu-id="fafaf-237">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="fafaf-238">「送信スパム フィルター ポリシー」という名前 **の既定の送信スパム ポリシー**の場合、 **セクション** に適用は使用できません (ポリシーはすべてのユーザーに適用されます)、ポリシーの名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="fafaf-238">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="fafaf-239">ポリシーを有効または無効にするには、ポリシーの優先順位を設定するか、またはエンドユーザーの検疫通知を構成します。後続の各セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fafaf-239">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="fafaf-240">送信スパム ポリシーを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="fafaf-240">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="fafaf-241">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-241">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="fafaf-242">[スパム \*\*対策の設定] ページで、[\*\* ![ 展開] アイコンをクリックして、作成したカスタム ](../../media/scc-expand-icon.png) ポリシーを展開します ([種類] **列** の値は **「カスタム送信スパム ポリシー」です**)。</span><span class="sxs-lookup"><span data-stu-id="fafaf-242">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="fafaf-243">展開して表示されたポリシー詳細で、**[On]** 列の値をメモします。</span><span class="sxs-lookup"><span data-stu-id="fafaf-243">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="fafaf-244">ポリシーを無効にするには、左に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="fafaf-244">Move the toggle to the left to disable the policy:</span></span> ![オフに切り替え](../../media/scc-toggle-off.png)

   <span data-ttu-id="fafaf-246">ポリシーを有効にするには、右に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="fafaf-246">Move the toggle to the right to enable the policy:</span></span> ![オンに切り替え](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="fafaf-248">既定の送信スパム ポリシーを無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="fafaf-248">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="fafaf-249">カスタム送信スパム ポリシーの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="fafaf-249">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="fafaf-250">既定では、送信スパム ポリシーには、ポリシーの作成順序に基づく優先度が設定されます (新しいポリシーの優先度が古いポリシーよりも低くなります)。</span><span class="sxs-lookup"><span data-stu-id="fafaf-250">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="fafaf-251">優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。</span><span class="sxs-lookup"><span data-stu-id="fafaf-251">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="fafaf-252">2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-252">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="fafaf-253">カスタムの送信スパム ポリシーは、処理される順に表示されます (最初のポリシーの **Priority** 値が 0)。</span><span class="sxs-lookup"><span data-stu-id="fafaf-253">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="fafaf-254">「Outbound スパム フィルター ポリシー」 **という名前の既定の送信スパム** ポリシーの優先度 **は「最低**」で、変更できません。</span><span class="sxs-lookup"><span data-stu-id="fafaf-254">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="fafaf-255">ポリシーの優先度を変更するには、リスト内で上下に移動させます (セキュリティ/コンプライアンス センター内で直接、**優先順位**番号を変更することはできません)。</span><span class="sxs-lookup"><span data-stu-id="fafaf-255">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="fafaf-256">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-256">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="fafaf-257">[スパム**対策の設定] ページで**、[種類] 列の値が**カスタムの送信スパム\*\*\*\*ポリシーであるポリシーを見つける。**</span><span class="sxs-lookup"><span data-stu-id="fafaf-257">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="fafaf-258">**[優先度]** 列の値に注目します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-258">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="fafaf-259">優先度が最も高いカスタム送信スパム ポリシーの値は、下矢 ![ 印アイコン ](../../media/ITPro-EAC-DownArrowIcon.png) **0 です**。</span><span class="sxs-lookup"><span data-stu-id="fafaf-259">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="fafaf-260">最も低い優先度を持つカスタム送信スパム ポリシーの値 ![ は上矢印アイコン ](../../media/ITPro-EAC-UpArrowIcon.png) **n** (たとえば、 ![ 上矢印アイコン ](../../media/ITPro-EAC-UpArrowIcon.png) **3) です**。</span><span class="sxs-lookup"><span data-stu-id="fafaf-260">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="fafaf-261">3 つ以上のカスタム送信スパム ポリシーがある場合、最も優先度の高い優先度と最も小さい間のポリシーでは、上矢印アイコン ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ n ](../../media/ITPro-EAC-DownArrowIcon.png) の値が**表示されます**(たとえば、上矢印アイコン ![ の下矢印アイコン ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **2)。**</span><span class="sxs-lookup"><span data-stu-id="fafaf-261">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="fafaf-262">上</span><span class="sxs-lookup"><span data-stu-id="fafaf-262">Click</span></span> ![矢印アイコン](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="fafaf-264">または</span><span class="sxs-lookup"><span data-stu-id="fafaf-264">or</span></span> ![下矢印アイコンをクリックして](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="fafaf-266">優先度リストのカスタム送信スパム ポリシーを上下に移動します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-266">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="fafaf-267">セキュリティ コンプライアンス センター&、送信スパム ポリシーの削除</span><span class="sxs-lookup"><span data-stu-id="fafaf-267">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="fafaf-268">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-268">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="fafaf-269">[スパム \*\*対策の設定] ページで、[\*\* ![ 展開] アイコンを ](../../media/scc-expand-icon.png) クリックして、削除するカスタム ポリシーを展開します **([種類** ] 列は **「カスタム送信スパム ポリシー」です**)。</span><span class="sxs-lookup"><span data-stu-id="fafaf-269">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="fafaf-270">展開されたポリシー詳細で、**[ポリシーの削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fafaf-270">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="fafaf-271">警告ダイアログが表示されたら、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fafaf-271">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="fafaf-272">既定のポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="fafaf-272">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="fafaf-273">Exchange Online PowerShell またはスタンドアロン EOP PowerShell を使用して送信スパム ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="fafaf-273">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

<span data-ttu-id="fafaf-274">前述のとおり、送信スパム ポリシーは送信スパム フィルター ポリシーと送信スパム フィルター ルールで構成されます。</span><span class="sxs-lookup"><span data-stu-id="fafaf-274">As previously described, an outbound spam policy consists of an outbound spam filter policy and an outbound spam filter rule.</span></span>

<span data-ttu-id="fafaf-275">Exchange Online PowerShell またはスタンドアロン EOP PowerShell では、送信スパム フィルター ポリシーと送信スパム フィルター ルールの違いは明らかです。</span><span class="sxs-lookup"><span data-stu-id="fafaf-275">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="fafaf-276">\*\* \* -HostedOutboundSpamFilterPolicy**コマンドレットを使用して送信スパム フィルター ポリシーを管理し、送信スパム フィルター ルールを管理するには** \* 、-HostedOutboundSpamFilterRule コマンドレットを\*\*使用します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-276">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="fafaf-277">PowerShell では、最初に送信スパム フィルター ポリシーを作成し、次にルールが適用されるポリシーを特定する送信スパム フィルター ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-277">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="fafaf-278">PowerShell では、送信スパム フィルター ポリシーと送信スパム フィルター ルールの設定は別々に変更されます。</span><span class="sxs-lookup"><span data-stu-id="fafaf-278">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>
- <span data-ttu-id="fafaf-279">PowerShell から送信スパム フィルター ポリシーを削除すると、対応する送信スパム フィルター ルールは自動で削除されず、逆もまた同じくなります。</span><span class="sxs-lookup"><span data-stu-id="fafaf-279">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="fafaf-280">PowerShell を使用して送信スパム ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="fafaf-280">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="fafaf-281">PowerShell で送信スパム ポリシーを作成する手順は 2 つの手順で行います。</span><span class="sxs-lookup"><span data-stu-id="fafaf-281">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="fafaf-282">送信スパム フィルター ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-282">Create the outbound spam filter policy.</span></span>
2. <span data-ttu-id="fafaf-283">ルールが適用される送信スパム フィルター ポリシーを指定する送信スパム フィルター ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-283">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="fafaf-284">**注**:</span><span class="sxs-lookup"><span data-stu-id="fafaf-284">**Notes**:</span></span>

- <span data-ttu-id="fafaf-285">新しい送信スパム フィルター ルールを作成して、既存の関連付けされていない送信スパム フィルター ポリシーをそのトランスポート ルールに割り当てたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="fafaf-285">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="fafaf-286">送信スパム フィルター ルールを複数の送信スパム フィルター ポリシーに関連付けられるルールは使用できません。</span><span class="sxs-lookup"><span data-stu-id="fafaf-286">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="fafaf-287">ポリシーを作成しない限りセキュリティ/コンプライアンス センターでは使用できない次 &の設定を、PowerShell の新しい送信スパム フィルター ポリシーに構成できます。</span><span class="sxs-lookup"><span data-stu-id="fafaf-287">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="fafaf-288">無効化された新しいポリシーを作成_します_ `$false` **(New-HostedOutboundSpamFilterRule コマンドレットで有効** )。</span><span class="sxs-lookup"><span data-stu-id="fafaf-288">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
  - <span data-ttu-id="fafaf-289">作成中にポリシーの優先度を設定する (_優先_ _\<Number\>_ 順位) **は、New-HostedOutboundSpamFilterRule コマンドレットで設定** します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-289">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="fafaf-290">ポリシーをスパム フィルター ルールに割り当てるまで、PowerShell で作成した新しい送信スパム フィルター ポリシーは、セキュリティ & コンプライアンス センターに表示されません。</span><span class="sxs-lookup"><span data-stu-id="fafaf-290">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="fafaf-291">手順 1: PowerShell を使用して送信スパム フィルター ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="fafaf-291">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="fafaf-292">送信スパム フィルター ポリシーを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-292">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="fafaf-293">この例では、次のような設定で Contoso Executives という新しい送信スパム フィルター ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-293">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="fafaf-294">受信者レートの制限は、既定値の小さい値に制限されています。</span><span class="sxs-lookup"><span data-stu-id="fafaf-294">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="fafaf-295">詳細については [、「Microsoft 365 オプション間の送信制限」を参照してください](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)。</span><span class="sxs-lookup"><span data-stu-id="fafaf-295">For more information, see [Sending limits across Microsoft 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="fafaf-296">制限の 1 つに達すると、ユーザーはメッセージを送信できません。</span><span class="sxs-lookup"><span data-stu-id="fafaf-296">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="fafaf-297">構文とパラメーターの詳細については [、「New-HostedOutboundSpamFilterPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="fafaf-297">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="fafaf-298">手順 2: PowerShell を使用して送信スパム フィルター ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="fafaf-298">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="fafaf-299">送信スパム フィルター ルールを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-299">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="fafaf-300">この例では、次に示す設定で Contoso Executives という新しい送信スパム フィルター ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-300">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="fafaf-301">Contoso Executives という名前の送信スパム フィルター ポリシーがルールに関連付けられていいます。</span><span class="sxs-lookup"><span data-stu-id="fafaf-301">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="fafaf-302">ルールは Contoso Executives Group という名前のグループのメンバーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="fafaf-302">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="fafaf-303">構文とパラメーターの詳細については [、「New-HostedOutboundSpamFilterRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="fafaf-303">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="fafaf-304">PowerShell を使用して送信スパム フィルター ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="fafaf-304">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="fafaf-305">すべての送信スパム フィルター ポリシーの要約リストを返すには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-305">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="fafaf-306">特定の送信スパム フィルター ポリシーに関する詳細情報を返すには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-306">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="fafaf-307">この例では、Executives という送信スパム フィルター ポリシーのすべてのプロパティの値が返されます。</span><span class="sxs-lookup"><span data-stu-id="fafaf-307">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="fafaf-308">構文とパラメーターの詳細については [、「Get-HostedOutboundSpamFilterPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="fafaf-308">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="fafaf-309">PowerShell を使用して送信スパム フィルター ルールを表示する</span><span class="sxs-lookup"><span data-stu-id="fafaf-309">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="fafaf-310">既存の送信スパム フィルター ルールを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-310">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="fafaf-311">すべての送信スパム フィルター ルールの要約リストを返すには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-311">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="fafaf-312">ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-312">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="fafaf-313">特定の送信スパム フィルター ルールに関する詳細情報を返すには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-313">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="fafaf-314">この例では、Contoso Executives という名前の送信スパム フィルター ルールのすべてのプロパティの値が返されます。</span><span class="sxs-lookup"><span data-stu-id="fafaf-314">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="fafaf-315">構文とパラメーターの詳細については [、「Get-HostedOutboundSpamFilterRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="fafaf-315">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="fafaf-316">PowerShell を使用して送信スパム フィルター ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="fafaf-316">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="fafaf-317">PowerShell でマルウェア フィルター ポリシーを変更する場合と、このトピックで前述した [手順 1 で説明](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) したように、ポリシーを作成する場合と同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="fafaf-317">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="fafaf-318">送信スパム フィルター ポリシーの名前を変更することはできません **(Set-HostedOutboundSpamFilterPolicy コマンドレット** には _Name_ パラメーターはありません)。</span><span class="sxs-lookup"><span data-stu-id="fafaf-318">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="fafaf-319">セキュリティ コンプライアンス センターで送信スパム ポリシーの名前を変更する&、送信スパム フィルター ルールの名前のみを変更 _します_。</span><span class="sxs-lookup"><span data-stu-id="fafaf-319">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="fafaf-320">送信スパム フィルター ポリシーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-320">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="fafaf-321">構文とパラメーターの詳細については [、「Set-HostedOutboundSpamFilterPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="fafaf-321">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="fafaf-322">PowerShell を使用して送信スパム フィルター ルールを変更する</span><span class="sxs-lookup"><span data-stu-id="fafaf-322">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="fafaf-323">PowerShell で送信スパム フィルター ルールを変更するときに使用できない設定は _、無効なルール_ の作成を可能にする Enabled パラメーターだけです。</span><span class="sxs-lookup"><span data-stu-id="fafaf-323">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="fafaf-324">既存の送信スパム フィルター ルールを有効または無効にするには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fafaf-324">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="fafaf-325">それ以外の場合、PowerShell で送信スパム フィルター ルールを変更する際に利用可能な追加の設定は存在しない。</span><span class="sxs-lookup"><span data-stu-id="fafaf-325">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="fafaf-326">手順 [2: PowerShell](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) を使用して送信スパム フィルター ルールを作成する手順の前述のセクションに示したとおりです。</span><span class="sxs-lookup"><span data-stu-id="fafaf-326">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="fafaf-327">送信スパム フィルター ルールを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-327">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="fafaf-328">構文とパラメーターの詳細については [、「Set-HostedOutboundSpamFilterRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="fafaf-328">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="fafaf-329">PowerShell を使用して送信スパム フィルター ルールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="fafaf-329">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="fafaf-330">PowerShell で送信スパム フィルター ルールを有効化または無効化すると、送信スパム ポリシー全体 (送信スパム フィルター ルールおよび割り当てられた送信スパム フィルター ポリシー) が有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="fafaf-330">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="fafaf-331">既定の送信スパム ポリシーを有効または無効にすることはできません (常にすべての受信者に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="fafaf-331">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="fafaf-332">PowerShell で送信スパム フィルター ルールを有効または無効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-332">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="fafaf-333">この例では、Marketing Department という名前の送信スパム フィルター ルールを無効化します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-333">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="fafaf-334">この例では、同じルールを有効化します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-334">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="fafaf-335">構文とパラメーターの詳細については [、「Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) および [Disable-HostedOutboundSpamFilterRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="fafaf-335">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="fafaf-336">PowerShell を使用して送信スパム フィルター ルールの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="fafaf-336">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="fafaf-337">ルールに設定できる優先度の最高値値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="fafaf-337">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="fafaf-338">設定できる最低値はルールの数に依存します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-338">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="fafaf-339">たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。</span><span class="sxs-lookup"><span data-stu-id="fafaf-339">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="fafaf-340">既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。</span><span class="sxs-lookup"><span data-stu-id="fafaf-340">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="fafaf-341">たとえば、カスタム ルールが 5 つあって (優先度 0 から 4)、1 つのルールの優先度を 2 に変更した場合には、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。</span><span class="sxs-lookup"><span data-stu-id="fafaf-341">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="fafaf-342">PowerShell で送信スパム フィルター ルールの優先度を設定するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-342">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="fafaf-p139">この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。</span><span class="sxs-lookup"><span data-stu-id="fafaf-p139">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - <span data-ttu-id="fafaf-345">新しく作成したルールの優先度を設定するには、**代わりに、New-HostedOutboundSpamFilterRule コマンドレットの** _Priority_パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-345">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
>
> - <span data-ttu-id="fafaf-346">送信された既定のスパム フィルター ポリシーには、対応するスパム フィルター ルールがありません。常に、変更不可能な優先度の値 **Lowest が設定されています**。</span><span class="sxs-lookup"><span data-stu-id="fafaf-346">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="fafaf-347">PowerShell を使用して送信スパム フィルター ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="fafaf-347">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="fafaf-348">PowerShell を使用して送信スパム フィルター ポリシーを削除した場合、対応する送信スパム フィルター ルールは削除されません。</span><span class="sxs-lookup"><span data-stu-id="fafaf-348">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="fafaf-349">PowerShell で送信スパム フィルター ポリシーを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-349">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="fafaf-350">この例では、Marketing Department という送信スパム フィルター ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-350">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="fafaf-351">構文とパラメーターの詳細については [、「Remove-HostedOutboundSpamFilterPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="fafaf-351">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="fafaf-352">PowerShell を使用して送信スパム フィルター ルールを削除する</span><span class="sxs-lookup"><span data-stu-id="fafaf-352">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="fafaf-353">PowerShell を使用して送信スパム フィルター ルールを削除した場合は、対応する送信スパム フィルター ポリシーは削除されません。</span><span class="sxs-lookup"><span data-stu-id="fafaf-353">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="fafaf-354">PowerShell で送信スパム フィルター ルールを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-354">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="fafaf-355">この例では、Marketing Department という名前の送信スパム フィルター ルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="fafaf-355">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="fafaf-356">構文とパラメーターの詳細については [、「Remove-HostedOutboundSpamFilterRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule)。</span><span class="sxs-lookup"><span data-stu-id="fafaf-356">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="fafaf-357">詳細情報</span><span class="sxs-lookup"><span data-stu-id="fafaf-357">For more information</span></span>

[<span data-ttu-id="fafaf-358">制限されたユーザー ポータルからブロックされたユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="fafaf-358">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="fafaf-359">送信メッセージにおける危険度の高い配信プール</span><span class="sxs-lookup"><span data-stu-id="fafaf-359">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="fafaf-360">スパム対策保護に関してよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="fafaf-360">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)

[<span data-ttu-id="fafaf-361">自動転送済みメッセージレポート</span><span class="sxs-lookup"><span data-stu-id="fafaf-361">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)
