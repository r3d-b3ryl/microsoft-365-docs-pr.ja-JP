---
title: スパム フィルター ポリシーの構成
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: 基本のスパム フィルター設定には、スパムとして識別されたメッセージに対して実行されるアクションの選択が含まれます。
ms.openlocfilehash: f77a4f52e045c96a0538b140022ebee846cb1996
ms.sourcegitcommit: 8a88b7526e6a3a907f33a8567e0d25b74fe60d80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "43204102"
---
# <a name="configure-anti-spam-policies-in-office-365"></a><span data-ttu-id="db9d1-103">Office 365 でのスパム対策ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="db9d1-103">Configure anti-spam policies in Office 365</span></span>

<span data-ttu-id="db9d1-104">Exchange Online のメールボックスを使用している Office 365 のお客様、または Exchange Online のメールボックスを使用していないもののスタンドアロンの Exchange Online Protection (EOP) をお使いのお客様の場合、受信メール メッセージは EOP によってスパムから自動的に保護されます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-104">If you're an Office 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, inbound email messages are automatically protected against spam by EOP.</span></span> <span data-ttu-id="db9d1-105">EOP では、スパムに対する組織の全体的防御の一環として、スパム対策ポリシー (スパム フィルター ポリシーまたはコンテンツ フィルター ポリシーとも呼ばれます) を使用します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-105">EOP uses anti-spam policies (also known as spam filter policies or content filter policies) as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="db9d1-106">詳細については、「[Office 365 のスパム対策保護](anti-spam-protection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db9d1-106">For more information, see [Anti-spam protection in Office 365](anti-spam-protection.md).</span></span>

<span data-ttu-id="db9d1-107">管理者は、既定のスパム対策ポリシーの表示、編集、構成を行うことができます (削除はできません)。</span><span class="sxs-lookup"><span data-stu-id="db9d1-107">Admins can view, edit, and configure (but not delete) the default anti-spam policy.</span></span> <span data-ttu-id="db9d1-108">より細かく設定できるように、カスタムのスパム対策保護ポリシーを作成し、組織内の指定したユーザー、グループ、またはドメインに適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-108">For greater granularity, you can also create custom anti-spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="db9d1-109">カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (実行順序) を変更できます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-109">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="db9d1-110">スパム対策ポリシーの構成は、Office 365 セキュリティ/コンプライアンス センターで、または PowerShell (Office 365 のお客様の場合は Exchange Online PowerShell、スタンドアロンの EOP お客様の場合は Exchange Online Protection PowerShell) で行います。</span><span class="sxs-lookup"><span data-stu-id="db9d1-110">You can configure anti-spam policies in the Office 365 Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="anti-spam-policies-in-the-office-365-security--compliance-center-vs-exchange-online-powershell-or-exchange-online-protection-powershell"></a><span data-ttu-id="db9d1-111">Office 365 セキュリティ/コンプライアンス センターと Exchange Online PowerShell または Exchange Online Protection PowerShell のスパム対策ポリシーの比較</span><span class="sxs-lookup"><span data-stu-id="db9d1-111">Anti-spam policies in the Office 365 Security & Compliance Center vs Exchange Online PowerShell or Exchange Online Protection PowerShell</span></span>

<span data-ttu-id="db9d1-112">EOP のスパム対策ポリシーの基本的な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="db9d1-112">The basic elements of an anti-spam policy in EOP are:</span></span>

- <span data-ttu-id="db9d1-113">**スパム フィルター ポリシー**: スパム フィルター判定のアクションと通知オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-113">**The spam filter policy**: Specifies the actions for spam filtering verdicts and the notification options.</span></span>

- <span data-ttu-id="db9d1-114">**スパム フィルター ルール**: スパム フィルター ポリシーの優先順位と受信者フィルター (ポリシーが適用される対象者) を指定します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-114">**The spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a spam filter policy.</span></span>

<span data-ttu-id="db9d1-115">これら 2 つの要素の違いは、セキュリティ/コンプライアンス センターでスパム対策を管理する際には明白ではありませんが、以下の違いがあります。</span><span class="sxs-lookup"><span data-stu-id="db9d1-115">The difference between these two elements isn't obvious when you manage anti-spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="db9d1-116">セキュリティ/コンプライアンス センターでスパム対策ポリシーを作成する場合、実際にはスパム フィルター ルール、および関連付けられているスパム フィルター ポリシーの両方に同じ名前を使用して同時に作成しています。</span><span class="sxs-lookup"><span data-stu-id="db9d1-116">When you create an anti-spam policy in the Security & Compliance Center, you're actually creating a spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="db9d1-117">セキュリティ/コンプライアンス センターでスパム対策ポリシーを変更する場合、名前、優先順位、有効/無効の切り替え、そして受信者フィルターに関連する設定の変更は、実際にはスパム フィルター ルールを変更しています。</span><span class="sxs-lookup"><span data-stu-id="db9d1-117">When you modify an anti-spam policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the spam filter rule.</span></span> <span data-ttu-id="db9d1-118">他のすべての設定は、関連付けられているスパム フィルター ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-118">All other settings modify the associated spam filter policy.</span></span>

- <span data-ttu-id="db9d1-119">セキュリティ/コンプライアンス センターからスパム対策ポリシーを削除すると、スパム フィルター ルールおよび関連付けられたスパム フィルター ポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-119">When you remove an anti-spam policy from the Security & Compliance Center, the spam filter rule and the associated spam filter policy are removed.</span></span>

<span data-ttu-id="db9d1-120">Exchange Online PowerShell またはスタンドアロンの Exchange Online Protection PowerShell では、スパム フィルター ポリシーとスパム フィルター ルールの違いは明白です。</span><span class="sxs-lookup"><span data-stu-id="db9d1-120">In Exchange Online PowerShell or standalone Exchange Online Protection PowerShell, the difference between spam filter policies and spam filter rules is apparent.</span></span> <span data-ttu-id="db9d1-121">スパム フィルター ポリシーは **\*-HostedContentFilterPolicy** コマンドレットを使用して管理し、スパム フィルター ルールは **\*-HostedContentFilterRule** コマンドレットを使用して管理します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-121">You manage spam filter policies by using the **\*-HostedContentFilterPolicy** cmdlets, and you manage spam filter rules by using the **\*-HostedContentFilterRule** cmdlets.</span></span>

- <span data-ttu-id="db9d1-122">PowerShell では、最初にスパム フィルター ポリシーを作成し、それからルールが適用されるポリシーを特定するスパム フィルター ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-122">In PowerShell, you create the spam filter policy first, then you create the spam filter rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="db9d1-123">PowerShell では、スパム フィルター ポリシーとスパム フィルター ルールの設定は別々に変更します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-123">In PowerShell, you modify the settings in the spam filter policy and the spam filter rule separately.</span></span>

- <span data-ttu-id="db9d1-124">PowerShell からスパム フィルター ポリシーを削除しても、対応しているスパム フィルター ルールは自動で削除されず、逆もまた同様です。</span><span class="sxs-lookup"><span data-stu-id="db9d1-124">When you remove a spam filter policy from PowerShell, the corresponding spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-anti-spam-policy"></a><span data-ttu-id="db9d1-125">既定のスパム対策ポリシー</span><span class="sxs-lookup"><span data-stu-id="db9d1-125">Default anti-spam policy</span></span>

<span data-ttu-id="db9d1-126">各組織には Default という名前の組み込みのスパム対策ポリシーがあり、以下の特徴があります。</span><span class="sxs-lookup"><span data-stu-id="db9d1-126">Every organization has a built-in anti-spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="db9d1-127">ポリシーに関連付けられているスパム フィルター ルール (受信者フィルター) がない場合でも、Default という名前のスパム フィルター ポリシーは組織内の全受信者に適用されます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-127">The spam filter policy named Default is applied to all recipients in the organization, even though there's no spam filter rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="db9d1-128">Default という名前のポリシーにはカスタムの優先順位の値 **Lowest** が設定されており、変更することはできません (このポリシーは常に最後に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="db9d1-128">The policy named Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="db9d1-129">作成するどのカスタム ポリシーも、Default という名前のポリシーより高い優先順位を持ちます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-129">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>

- <span data-ttu-id="db9d1-130">Default という名前のポリシーは既定のポリシー (**IsDefault** のプロパティが `True` の値になっている) であり、既定のポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="db9d1-130">The policy named Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="db9d1-131">スパム フィルター処理の有効性を高めるために、特定のユーザーまたはユーザー グループに適用される、より厳密な設定を持つカスタムのスパム対策ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-131">To increase the effectiveness of spam filtering, you can create custom anti-spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="db9d1-132">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="db9d1-132">What do you need to know before you begin?</span></span>

- <span data-ttu-id="db9d1-133"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-133">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="db9d1-134">**[スパム対策の設定]** ページに直接移動するには、<https://protection.office.com/antispam> を使用します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-134">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="db9d1-135">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db9d1-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="db9d1-136">スタンドアロンの Exchange Online Protection PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db9d1-136">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="db9d1-137">これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="db9d1-137">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="db9d1-138">スパム対策ポリシーを追加、変更、削除するには、「**組織の管理**」または「**セキュリティ管理者**」役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="db9d1-138">To add, modify, and delete anti-spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="db9d1-139">スパム対策ポリシーに読み取り専用でアクセスするには、「**セキュリティ閲覧者**」役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="db9d1-139">For read-only access to anti-spam policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="db9d1-140">セキュリティ/コンプライアンス センターの役割グループの詳細については、「[Office 365 セキュリティ/コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="db9d1-140">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="db9d1-141">スパム対策ポリシーに推奨される設定については、「[EOP スパム対策ポリシーの設定](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db9d1-141">For our recommended settings for anti-spam policies, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-spam-policies"></a><span data-ttu-id="db9d1-142">セキュリティ/コンプライアンス センターを使用してスパム対策ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="db9d1-142">Use the Security & Compliance Center to create anti-spam policies</span></span>

<span data-ttu-id="db9d1-143">セキュリティ/コンプライアンス センターでスパム対策ポリシーを作成する場合、実際にはスパム フィルター ルール、および関連付けられているスパム フィルター ポリシーの両方に同じ名前を使用して同時に作成しています。</span><span class="sxs-lookup"><span data-stu-id="db9d1-143">Creating a custom anti-spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="db9d1-144">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-144">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="db9d1-145">**[スパム対策の設定]** ページの **[ポリシーの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-145">On the **Anti-spam settings** page, click **Create a policy**.</span></span>

3. <span data-ttu-id="db9d1-146">開いた **[新しいスパム フィルター ポリシー]** ポップアップで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-146">In the **New spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="db9d1-147">**[名前]**: わかりやすい一意のポリシー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-147">**Name**: Enter a unique, descriptive name for the policy.</span></span> <span data-ttu-id="db9d1-148">以下の文字は使用しないでください: `\ % & * + / = ? { } | < > ( ) ; : , [ ] "`</span><span class="sxs-lookup"><span data-stu-id="db9d1-148">Don't use the following characters: `\ % & * + / = ? { } | < > ( ) ; : , [ ] "`.</span></span>

      <span data-ttu-id="db9d1-149">これらの文字が含まれているスパム対策ポリシーを、Exchange 管理センター (EAC) で以前に作成した場合は、PowerShell でそのスパム対策ポリシーの名前を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db9d1-149">If you previously created anti-spam policies in the Exchange admin center (EAC) that contains these characters, you should rename the anti-spam policy in PowerShell.</span></span> <span data-ttu-id="db9d1-150">手順については、このトピックで後述する「[PowerShell を使用してスパム フィルター ルールを変更する](#use-powershell-to-modify-spam-filter-rules)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db9d1-150">For instructions, see the [Use PowerShell to modify spam filter rules](#use-powershell-to-modify-spam-filter-rules) section later in this topic.</span></span>

   - <span data-ttu-id="db9d1-151">**[説明]**: ポリシーについての説明を入力します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="db9d1-151">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="db9d1-152">(オプション) **[迷惑メールおよびバルク メールの処理]** セクションを展開し、以下の設定を確認または構成します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-152">(Optional) Expand the **Spam and bulk actions** section, and verify or configure the following settings:</span></span>

   - <span data-ttu-id="db9d1-153">**スパムとバルク メールを受信するためのアクションを選択します**: 以下のスパム対策フィルター判定に基づき、メッセージに対して行うアクションを選択または確認します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-153">**Select the action to take for incoming spam and bulk email**: Select or review the action to take on messages based on the following spam filtering verdicts:</span></span>

     - <span data-ttu-id="db9d1-154">**スパム**</span><span class="sxs-lookup"><span data-stu-id="db9d1-154">**Spam**</span></span>
     - <span data-ttu-id="db9d1-155">**高確度迷惑メール**</span><span class="sxs-lookup"><span data-stu-id="db9d1-155">**High confidence spam**</span></span>
     - <span data-ttu-id="db9d1-156">**フィッシング詐欺メール**</span><span class="sxs-lookup"><span data-stu-id="db9d1-156">**Phishing email**</span></span>
     - <span data-ttu-id="db9d1-157">**高確度フィッシング詐欺メール**</span><span class="sxs-lookup"><span data-stu-id="db9d1-157">**High confidence phishing email**</span></span>
     - <span data-ttu-id="db9d1-158">**バルク メール**</span><span class="sxs-lookup"><span data-stu-id="db9d1-158">**Bulk email**</span></span>

     <span data-ttu-id="db9d1-159">次の表で、スパム対策フィルター判定に使用可能なアクションを説明します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-159">The available actions for spam filtering verdicts are described in the following table.</span></span>

     - <span data-ttu-id="db9d1-160">チェック マーク (</span><span class="sxs-lookup"><span data-stu-id="db9d1-160">A check mark (</span></span> ![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<span data-ttu-id="db9d1-162">) は、アクションが使用可能であることを示します (すべてのアクションがすべてのスパム対策フィルター判定に使用できるわけではありません)。</span><span class="sxs-lookup"><span data-stu-id="db9d1-162">) indicates the action is available (not all actions are available for all spam filtering verdicts).</span></span>
     - <span data-ttu-id="db9d1-163">チェック マークの後にアスタリスク ( <sup>\*</sup> ) がある場合、スパム対策フィルター判定の既定のアクションであることを示しています。</span><span class="sxs-lookup"><span data-stu-id="db9d1-163">An asterisk ( <sup>\*</sup> ) after the check mark indicates the default action for the spam filtering verdict.</span></span>

    |||||||
    |:---|:---:|:---:|:---:|:---:|:---:|
    ||<span data-ttu-id="db9d1-164">**スパム**</span><span class="sxs-lookup"><span data-stu-id="db9d1-164">**Spam**</span></span>|<span data-ttu-id="db9d1-165">**高<br/>確度<br/>迷惑メール**</span><span class="sxs-lookup"><span data-stu-id="db9d1-165">**High<br/>confidence<br/>spam**</span></span>|<span data-ttu-id="db9d1-166">**フィッシング詐欺<br/>メール**</span><span class="sxs-lookup"><span data-stu-id="db9d1-166">**Phishing<br/>email**</span></span>|<span data-ttu-id="db9d1-167">**高<br/>確度<br/>フィッシング詐欺<br/>メール**</span><span class="sxs-lookup"><span data-stu-id="db9d1-167">**High<br/>confidence<br/>phishing<br/>email**</span></span>|<span data-ttu-id="db9d1-168">**バルク<br/> メール**</span><span class="sxs-lookup"><span data-stu-id="db9d1-168">**Bulk<br/>email**</span></span>|
    |<span data-ttu-id="db9d1-169">**メッセージを迷惑メール フォルダーに移動する**: メッセージはメールボックスに配信され、[迷惑メール] フォルダーに移動されます。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="db9d1-169">**Move message to Junk Email folder**: The message is delivered to the mailbox and moved to the Junk Email folder.<sup>1</sup></span></span>|<span data-ttu-id="db9d1-170">![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="db9d1-170">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="db9d1-171">![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="db9d1-171">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|<span data-ttu-id="db9d1-174">![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="db9d1-174">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
    |<span data-ttu-id="db9d1-175">**X-ヘッダーを追加する**: X-ヘッダーをメッセージ ヘッダーに追加し、そのメッセージをメールボックスに配信します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-175">**Add X-header**: Adds an X-header to the message header and delivers the message to the mailbox.</span></span> <br/> <span data-ttu-id="db9d1-176">後で **[この X ヘッダーのテキストを追加する]** ボックスに、X-ヘッダーのフィールド名 (値ではなく) を入力します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-176">You enter the X-header field name (not the value) later in the **Add this X-header text** box.</span></span> <br/><br/> <span data-ttu-id="db9d1-177">**スパム**および**高確度迷惑メール**判定の場合、メッセージは [迷惑メール] フォルダーに移動されます。<sup>1、2</sup></span><span class="sxs-lookup"><span data-stu-id="db9d1-177">For **Spam** and **High confidence spam** verdicts, the message is moved to the Junk Email folder.<sup>1,2</sup></span></span>|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||<span data-ttu-id="db9d1-181">![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="db9d1-181">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
    |<span data-ttu-id="db9d1-182">**件名行の先頭にテキストを追加する**: メッセージの件名行の先頭にテキストを追加します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-182">**Prepend subject line with text**: Adds text to the beginning of the message's subject line.</span></span> <span data-ttu-id="db9d1-183">メッセージはメールボックスに配信され、[迷惑メール] フォルダーに移動されます。<sup>1、2</sup></span><span class="sxs-lookup"><span data-stu-id="db9d1-183">The message is delivered to the mailbox and moved to the Junk email folder.<sup>1,2</sup></span></span> <br/> <span data-ttu-id="db9d1-184">テキストを後で **[件名行の先頭にこのテキストを追加する]** ボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-184">You enter the text later in the **Prefix subject line with this text** box.</span></span>|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |<span data-ttu-id="db9d1-189">**[メッセージをメール アドレスにリダイレクトする]:** メッセージを本来の受信者の代わりに他の受信者に送信します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-189">**Redirect message to email address**: Sends the message to other recipients instead of the intended recipients.</span></span> <br/> <span data-ttu-id="db9d1-190">後で、受信者を **[このメール アドレスにリダイレクトする]** ボックスに指定してください。</span><span class="sxs-lookup"><span data-stu-id="db9d1-190">You specify the recipients later in the **Redirect to this email address** box.</span></span>|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |<span data-ttu-id="db9d1-196">**[メッセージの削除]:** 添付ファイルすべてを含め、メッセージ全体が確認なしで削除されます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-196">**Delete message**: Silently deletes the entire message, including all attachments.</span></span>|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |<span data-ttu-id="db9d1-201">**[メッセージを隔離する]:** メッセージを本来の受信者に送信せず、検疫に送信します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-201">**Quarantine message**: Sends the message to quarantine instead of the intended recipients.</span></span> <br/> <span data-ttu-id="db9d1-202">後で、検疫でメッセージを保持する期間を **[検疫]** ボックスに指定します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-202">You specify how long the message should be held in quarantine later in the **Quarantine** box.</span></span>|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|<span data-ttu-id="db9d1-205">![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="db9d1-205">![Check mark](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |<span data-ttu-id="db9d1-208">**アクションなし**</span><span class="sxs-lookup"><span data-stu-id="db9d1-208">**No action**</span></span>|||||![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |

    > <span data-ttu-id="db9d1-210"><sup>1</sup> Exchange Online では、受信トレイで迷惑メール ルールが有効になっている場合、メッセージは [迷惑メール] フォルダーに移動されます (既定では有効)。</span><span class="sxs-lookup"><span data-stu-id="db9d1-210"><sup>1</sup> In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="db9d1-211">詳細については、「[Office 365 で Exchange Online のメールボックスの迷惑メール設定を構成する](configure-junk-email-settings-on-exo-mailboxes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db9d1-211">For more information, see [Configure junk email settings on Exchange Online mailboxes in Office 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span><br/><span data-ttu-id="db9d1-212">EOP がオンプレミスの Exchange メールボックスを保護するスタンドアロン EOP 環境では、オンプレミスの Exchange のメール フロー ルール (トランスポート ルールとも言う) を構成して、迷惑メール ルールによりメッセージが [迷惑メール] フォルダーに移動できるように、EOP スパム対策フィルター判定を解釈する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db9d1-212">In standalone EOP environments where EOP protects on-premises Exchange mailboxes, you need to configure mail flow rules (also known as transport rules) in on-premises Exchange to translate the EOP spam filtering verdict so the junk email rule can move the message to the Junk Email folder.</span></span> <span data-ttu-id="db9d1-213">詳細については、「[迷惑メール フォルダーにスパムを配信するようにスタンドアロン EOP を構成する](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db9d1-213">For details, see [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span><br/><br/><span data-ttu-id="db9d1-214"><sup>2</sup> この値を、メール フロー ルール (トランスポート ルールとも言う) の条件として、メッセージのフィルター処理やルーティングに使用することができます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-214"><sup>2</sup> You can this use value as a condition in mail flow rules (also known as transport rules) to filter or route the message.</span></span>

   - <span data-ttu-id="db9d1-215">**しきい値を選択**: **[バルク メール]** スパム対策フィルター判定に指定されたアクションをトリガーするメッセージの Bulk Complaint Level (BCL) を指定します (アクションは、指定された値以上ではなく、指定された値より大きい場合にトリガーされます)。</span><span class="sxs-lookup"><span data-stu-id="db9d1-215">**Select the threshold**: Specifies the bulk complaint level (BCL) of a message that triggers the specified action for the **Bulk email** spam filtering verdict (greater than the specified value, not greater than or equal to).</span></span> <span data-ttu-id="db9d1-216">値が大きければ大きいほど、そのメッセージの信頼度は低い (迷惑メールである可能性が高い) ことを示します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-216">A higher value indicates the message is less desirable (more likely to resemble spam).</span></span> <span data-ttu-id="db9d1-217">既定の値は 7 です。</span><span class="sxs-lookup"><span data-stu-id="db9d1-217">The default value is 7.</span></span> <span data-ttu-id="db9d1-218">詳細については、「[Office 365 の Bulk Complaint Level (BCL)](bulk-complaint-level-values.md)」および「[迷惑メールとバルク メールの違い](what-s-the-difference-between-junk-email-and-bulk-email.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db9d1-218">For more information, see [Bulk complaint level (BCL) in Office 365](bulk-complaint-level-values.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

     <span data-ttu-id="db9d1-219">既定では、スパム対策ポリシーでの PowerShell のみの設定である _MarkAsSpamBulkMail_ は、`On` です。</span><span class="sxs-lookup"><span data-stu-id="db9d1-219">By default, the PowerShell only setting _MarkAsSpamBulkMail_ is `On` in anti-spam policies.</span></span> <span data-ttu-id="db9d1-220">この設定は、**バルク メール** フィルター判定の結果に大きく影響します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-220">This setting dramatically affects the results of a **Bulk email** filtering verdict:</span></span>

     - <span data-ttu-id="db9d1-221">**_MarkAsSpamBulkMail_ が [On]**: しきい値よりも高い BCL は、フィルター判定「**スパム**」に相当する SCL 6 に変換され、**バルク メール** フィルター判定に指定されたアクションがメッセージに対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-221">**_MarkAsSpamBulkMail_ is On**: A BCL that's greater than the threshold is converted to an SCL 6 that corresponds to a filtering verdict of **Spam**, and the action for the **Bulk email** filtering verdict is taken on the message.</span></span>

     - <span data-ttu-id="db9d1-222">**_MarkAsSpamBulkMail_ が [Off]**: メッセージには BCL がスタンプされますが、**バルク メール** フィルター判定に対して_何のアクションも実行されません_。</span><span class="sxs-lookup"><span data-stu-id="db9d1-222">**_MarkAsSpamBulkMail_ is Off**: The message is stamped with the BCL, but _no action_ is taken for a **Bulk email** filtering verdict.</span></span> <span data-ttu-id="db9d1-223">実際には、BCL しきい値と**バルク メール** フィルター判定アクションは無関係です。</span><span class="sxs-lookup"><span data-stu-id="db9d1-223">In effect, the BCL threshold and **Bulk email** filtering verdict action are irrelevant.</span></span>

   - <span data-ttu-id="db9d1-224">**検疫**: スパム対策フィルター判定のアクションとして **[メッセージを検疫]** を選択した場合に、メッセージを検疫に保持する期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-224">**Quarantine**: Specifies how long to keep the message in quarantine if you selected **Quarantine message** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="db9d1-225">期間が終了すると、メッセージは削除されます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-225">After the time period expires, the message is deleted.</span></span> <span data-ttu-id="db9d1-226">既定値は 30 日です。</span><span class="sxs-lookup"><span data-stu-id="db9d1-226">The default value is 30 days.</span></span> <span data-ttu-id="db9d1-227">有効な値は 1 日から 30 日です。</span><span class="sxs-lookup"><span data-stu-id="db9d1-227">A valid value is from 1 to 30 days.</span></span> <span data-ttu-id="db9d1-228">検疫の詳細については、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="db9d1-228">For information about quarantine, see the following topics:</span></span>

     - [<span data-ttu-id="db9d1-229">Office 365 の検疫</span><span class="sxs-lookup"><span data-stu-id="db9d1-229">Quarantine in Office 365</span></span>](quarantine-email-messages.md)
     - [<span data-ttu-id="db9d1-230">Office 365 の管理者として検疫済みメッセージとファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="db9d1-230">Manage quarantined messages and files as an admin in Office 365</span></span>](manage-quarantined-messages-and-files.md)
     - [<span data-ttu-id="db9d1-231">Office 365 のユーザーとして検疫済みメッセージを検索して解放する</span><span class="sxs-lookup"><span data-stu-id="db9d1-231">Find and release quarantined messages as a user in Office 365</span></span>](find-and-release-quarantined-messages-as-a-user.md)

   - <span data-ttu-id="db9d1-232">**この X-ヘッダー テキストを追加する**: このボックスは、**[X-ヘッダーの追加]** を、スパム対策フィルター判定のアクションとして選択した場合にのみ必要で、選択可能になります。</span><span class="sxs-lookup"><span data-stu-id="db9d1-232">**Add this X-header text**: This box is required and available only if you selected **Add X-header** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="db9d1-233">指定する値は、メッセージ ヘッダーに追加されるヘッダー フィールドの*名前*です。</span><span class="sxs-lookup"><span data-stu-id="db9d1-233">The value you specify is the header field *name* that's added to the message header.</span></span> <span data-ttu-id="db9d1-234">ヘッダー フィールドの*値*は常に `This message appears to be spam` です。</span><span class="sxs-lookup"><span data-stu-id="db9d1-234">The header field *value* is always `This message appears to be spam`.</span></span>

     <span data-ttu-id="db9d1-235">最大の長さは 255 文字で、値にスペースやコロン (:) を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="db9d1-235">The maximum length is 255 characters, and the value can't contain spaces or colons (:).</span></span>

     <span data-ttu-id="db9d1-236">たとえば、値 `X-This-is-my-custom-header` を入力すると、メッセージに追加される X-ヘッダーは `X-This-is-my-custom-header: This message appears to be spam.` です。</span><span class="sxs-lookup"><span data-stu-id="db9d1-236">For example, if you enter the value `X-This-is-my-custom-header`, the X-header that's added to the message is `X-This-is-my-custom-header: This message appears to be spam.`</span></span>

     <span data-ttu-id="db9d1-237">スペースまたはコロン (:) を含む値を入力した場合、入力した値は無視され、既定の X-ヘッダー (`X-This-Is-Spam: This message appears to be spam.`) がメッセージに追加されます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-237">If you enter a value that contains spaces or colons (:), the value you enter is ignored, and the default X-header is added to the message (`X-This-Is-Spam: This message appears to be spam.`).</span></span>

   - <span data-ttu-id="db9d1-238">**件名行の先頭にこのテキストを追加する**: このボックスは、**[件名行の先頭にテキストを追加する]** を、スパム対策フィルター判定のアクションとして選択した場合にのみ必要で、選択可能になります。</span><span class="sxs-lookup"><span data-stu-id="db9d1-238">**Prepend subject line with this text**: This box is required and available only if you selected **Prepend subject line with text** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="db9d1-239">メッセージの件名行の先頭に追加するテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-239">Enter the text to add to the beginning of the message's subject line.</span></span>

   - <span data-ttu-id="db9d1-240">**このメール アドレスにリダイレクトする**: このボックスは、**[メール アドレスにリダイレクトする]** を、スパム対策フィルター判定のアクションとして選択した場合にのみ必要で、選択可能になります。</span><span class="sxs-lookup"><span data-stu-id="db9d1-240">**Redirect to this email address**: This box is required and available only if you selected the **Redirect message to email address** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="db9d1-241">メッセージの配信先のメール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-241">Enter the email address where you want to deliver the message.</span></span> <span data-ttu-id="db9d1-242">複数の値をセミコロン (;) で区切って入力できます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-242">You can enter multiple values separated by semicolons (;).</span></span>

   - <span data-ttu-id="db9d1-243">**安全性のヒント**: 既定で [安全性のヒント] は有効になっていますが、これらは **オン**になっているチェックボックスをオフにすることで無効にできます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-243">**Safety Tips**: By default, Safety Tips are enabled, but you can disable them by clearing the **On** checkbox.</span></span> <span data-ttu-id="db9d1-244">安全性のヒントの詳細については、「[Office 365 でのメール メッセージの安全性のヒント](safety-tips-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db9d1-244">For more information about Safety Tips, see [Safety tips in email messages in Office 365](safety-tips-in-office-365.md).</span></span>

   <span data-ttu-id="db9d1-245">**[ゼロアワー自動消去]** 設定: Exchange Online のメールボックスに既に配信されたメッセージを ZAP が検出し、アクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-245">**Zero-hour auto purge** settings: ZAP detects and takes action on messages that have already been delivered to Exchange Online mailboxes.</span></span> <span data-ttu-id="db9d1-246">ZAP の詳細については、「[ゼロアワー自動消去 - スパムまたはマルウェアからの保護](zero-hour-auto-purge.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db9d1-246">For more information about ZAP, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

   - <span data-ttu-id="db9d1-247">**Spam ZAP**: 既定では、ZAP はスパム検出に対して有効になっていますが、**オン**になっているチェックボックスをオフにすることで無効にできます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-247">**Spam ZAP**: By default, ZAP is enabled for spam detections, but you can disable it by clearing the **On** checkbox.</span></span>

   - <span data-ttu-id="db9d1-248">**フィッシング詐欺に対する ZAP**: 既定では、ZAP はフィッシング検出に対して有効になっていますが、**オン**になっているチェックボックスをオフにすることで無効にできます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-248">**Phish ZAP**: By default, ZAP is enabled for phish detections, but you can disable it by clearing the **On** checkbox.</span></span>

5. <span data-ttu-id="db9d1-249">(オプション) **[受信許可一覧]** セクションを展開すると、スパム対策フィルター処理をスキップできるメッセージ送信者を、メール アドレスごと、またはメール ドメインごとに構成できます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-249">(Optional) Expand the **Allow lists** section to configure message senders by email address or email domain that are allowed to skip spam filtering:</span></span>

   > [!CAUTION]
   > <ul><li><span data-ttu-id="db9d1-250">その場合、ドメインを追加する前に慎重に検討してください。</span><span class="sxs-lookup"><span data-stu-id="db9d1-250">Think very carefully before you add domains here.</span></span> <span data-ttu-id="db9d1-251">詳細については、「[Office 365 での信頼できる差出人リストの作成](create-safe-sender-lists-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db9d1-251">For more information, see [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md)</span></span></li><li><span data-ttu-id="db9d1-252">承認済みドメイン (自分が所有しているドメイン) や一般的なドメイン (microsoft.com や office.com など) は、決して、許可するドメインのリストに追加しないでください。</span><span class="sxs-lookup"><span data-stu-id="db9d1-252">Never add accepted domains (domains that you own) or common domains (for example, microsoft.com or office.com) to the allowed domains list.</span></span> <span data-ttu-id="db9d1-253">そのようにすると、攻撃者は組織にスパム フィルターをバイパスするメールを送信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="db9d1-253">This would allow attackers to send email that bypasses spam filtering into your organization.</span></span></li></ul>

   - <span data-ttu-id="db9d1-254">**受信許可**: **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-254">**Allow sender**: Click **Edit**.</span></span> <span data-ttu-id="db9d1-255">表示される **[許可された送信者一覧]** ポップアップで、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-255">In the **Allowed sender list** flyout that appears:</span></span>

      <span data-ttu-id="db9d1-256">a.</span><span class="sxs-lookup"><span data-stu-id="db9d1-256">a.</span></span> <span data-ttu-id="db9d1-257">送信者の電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-257">Enter the sender's email address.</span></span> <span data-ttu-id="db9d1-258">複数のメール アドレスをセミコロン (;) で区切って指定できます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-258">You can specify multiple email addresses separated by semicolons (;).</span></span>

      <span data-ttu-id="db9d1-259">b.</span><span class="sxs-lookup"><span data-stu-id="db9d1-259">b.</span></span> <span data-ttu-id="db9d1-260">Click</span><span class="sxs-lookup"><span data-stu-id="db9d1-260">Click</span></span> ![[追加] アイコン](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="db9d1-262">をクリックして送信者を追加します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-262">to add the senders.</span></span>

      <span data-ttu-id="db9d1-263">必要な回数だけこれらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-263">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="db9d1-264">追加した送信者が、ポップアップの **[受信許可送信者]** セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-264">The senders you added appear in the **Allowed Sender** section on the flyout.</span></span> <span data-ttu-id="db9d1-265">送信者を削除するには、![[削除] アイコン](../../media/scc-remove-icon.png)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-265">To delete a sender, click ![Remove icon](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="db9d1-266">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-266">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="db9d1-267">**ドメインを許可**: **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-267">**Allow domain**: Click **Edit**.</span></span> <span data-ttu-id="db9d1-268">表示される **[許可されているドメイン一覧]** ポップアップで、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-268">In the **Allowed domain list** flyout that appears do these steps:</span></span>

      <span data-ttu-id="db9d1-269">a.</span><span class="sxs-lookup"><span data-stu-id="db9d1-269">a.</span></span> <span data-ttu-id="db9d1-270">ドメインを入力します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-270">Enter the domain.</span></span> <span data-ttu-id="db9d1-271">複数のドメインをセミコロン (;) で区切って指定できます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-271">You can specify multiple domains separated by semicolons (;).</span></span>

      <span data-ttu-id="db9d1-272">b.</span><span class="sxs-lookup"><span data-stu-id="db9d1-272">b.</span></span> <span data-ttu-id="db9d1-273">Click</span><span class="sxs-lookup"><span data-stu-id="db9d1-273">Click</span></span> ![[追加] アイコン](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="db9d1-275">をクリックしてドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-275">to add the domains.</span></span>

      <span data-ttu-id="db9d1-276">必要な回数だけこれらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-276">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="db9d1-277">追加したドメインが、ポップアップの **[受信許可ドメイン]** セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-277">The domains you added appear in the **Allowed Domain** section on the flyout.</span></span> <span data-ttu-id="db9d1-278">ドメインを削除するには、![[削除] アイコン](../../media/scc-remove-icon.png)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-278">To delete a domain, click ![Remove icon](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="db9d1-279">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-279">When you're finished, click **Save**.</span></span>

6. <span data-ttu-id="db9d1-280">(オプション) **[受信拒否一覧]** セクションを展開すると、常に高確度迷惑メールとマークされるメッセージ送信者をメール アドレスごと、またはメール ドメインごとに構成できます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-280">(Optional) Expand the **Block lists** section to configure message senders by email address or email domain that will always be marked as high confidence spam:</span></span>

   > [!NOTE]
   > <span data-ttu-id="db9d1-281">手動でのドメインの受信拒否は危険ではありませんが、管理作業の負荷が増大する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="db9d1-281">Manually blocking domains isn't dangerous, but it can increase your administrative workload.</span></span> <span data-ttu-id="db9d1-282">詳細については、「[Office 365 での受信拒否リストの作成](create-block-sender-lists-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db9d1-282">For more information, see [Create block sender lists in Office 365](create-block-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="db9d1-283">**受信拒否**: **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-283">**Block sender**: Click **Edit**.</span></span> <span data-ttu-id="db9d1-284">表示される **[受信拒否リスト一覧]** で、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-284">In the **Blocked sender list** flyout that appears do these steps:</span></span>

      <span data-ttu-id="db9d1-285">a.</span><span class="sxs-lookup"><span data-stu-id="db9d1-285">a.</span></span> <span data-ttu-id="db9d1-286">送信者の電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-286">Enter the sender's email address.</span></span> <span data-ttu-id="db9d1-287">複数のメール アドレスをセミコロン (;) で区切って指定できます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-287">You can specify multiple email addresses separated by semicolons (;).</span></span> <span data-ttu-id="db9d1-288">ワイルドカード (\*) は使用できません。</span><span class="sxs-lookup"><span data-stu-id="db9d1-288">Wildcards (\*) aren't allowed.</span></span>

      <span data-ttu-id="db9d1-289">b.</span><span class="sxs-lookup"><span data-stu-id="db9d1-289">b.</span></span> <span data-ttu-id="db9d1-290">Click</span><span class="sxs-lookup"><span data-stu-id="db9d1-290">Click</span></span> ![[追加] アイコン](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="db9d1-292">をクリックして送信者を追加します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-292">to add the senders.</span></span>

      <span data-ttu-id="db9d1-293">必要な回数だけこれらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-293">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="db9d1-294">追加した送信者が、ポップアップの **[ブロックする差出人]** セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-294">The senders you added appear in the **Blocked Sender** section on the flyout.</span></span> <span data-ttu-id="db9d1-295">送信者を削除するには、![[削除] ボタン](../../media/scc-remove-icon.png)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-295">To delete a sender, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="db9d1-296">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-296">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="db9d1-297">**ドメインをブロック**: **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-297">**Block domain**: Click **Edit**.</span></span> <span data-ttu-id="db9d1-298">表示される **[ブロックされたドメイン一覧]** ポップアップで、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-298">In the **Blocked domain list** flyout that appears:</span></span>

      <span data-ttu-id="db9d1-299">a.</span><span class="sxs-lookup"><span data-stu-id="db9d1-299">a.</span></span> <span data-ttu-id="db9d1-300">ドメインを入力します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-300">Enter the domain.</span></span> <span data-ttu-id="db9d1-301">複数のドメインをセミコロン (;) で区切って指定できます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-301">You can specify multiple domains separated by semicolons (;).</span></span> <span data-ttu-id="db9d1-302">ワイルドカード (\*) は使用できません。</span><span class="sxs-lookup"><span data-stu-id="db9d1-302">Wildcards (\*) aren't allowed.</span></span>

      <span data-ttu-id="db9d1-303">b.</span><span class="sxs-lookup"><span data-stu-id="db9d1-303">b.</span></span> <span data-ttu-id="db9d1-304">Click</span><span class="sxs-lookup"><span data-stu-id="db9d1-304">Click</span></span> ![[追加] アイコン](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="db9d1-306">をクリックしてドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-306">to add the domains.</span></span>

      <span data-ttu-id="db9d1-307">必要な回数だけこれらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-307">Repeat these steps as many times as necessary.</span></span>

      <span data-ttu-id="db9d1-308">追加したドメインが、ポップアップの **[ブロックされたドメイン]** リストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-308">The domains you added appear in the **Blocked Domain** list on the flyout.</span></span> <span data-ttu-id="db9d1-309">ドメインを削除するには、![[削除] ボタン](../../media/scc-remove-icon.png)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-309">To delete a domain, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

      <span data-ttu-id="db9d1-310">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-310">When you're finished, click **Save**.</span></span>

7. <span data-ttu-id="db9d1-311">(オプション) **[海外からの迷惑メール]** セクションを展開すると、スパム対策フィルター処理によってブロックされる電子メールの言語や発信国を設定できます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-311">(Optional) Expand the **International spam** section to configure the email languages or source countries that are blocked by spam filtering:</span></span>

   - <span data-ttu-id="db9d1-312">**次の言語で書かれたメール メッセージをフィルターします**: この設定は既定では無効になっています (**状態: OFF**)。</span><span class="sxs-lookup"><span data-stu-id="db9d1-312">**Filter email messages written in the following languages**: This setting is disabled by default (**Status: OFF**).</span></span> <span data-ttu-id="db9d1-313">**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-313">Click **Edit**.</span></span> <span data-ttu-id="db9d1-314">表示される **[海外からの迷惑メールの設定]** ポップアップで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-314">In the **International spam settings** flyout that appears, configure the following settings:</span></span>

     - <span data-ttu-id="db9d1-315">**次の言語で書かれたメール メッセージをフィルターします**: この設定を有効にするには、チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-315">**Filter email messages written in the following languages**: Select the checkbox to enable this setting.</span></span> <span data-ttu-id="db9d1-316">この設定を無効にするには、チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-316">Clear the checkbox to disable this setting.</span></span>

     - <span data-ttu-id="db9d1-317">ボックス内をクリックし、言語の*名前*の入力を始めます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-317">Click in the box and start typing the *name* of the language.</span></span> <span data-ttu-id="db9d1-318">フィルター処理の対象となる、サポートされている言語のリストが、対応する ISO 639-2 の言語コードと共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-318">A filtered list of supported languages will appear, along with the corresponding ISO 639-2 language code.</span></span> <span data-ttu-id="db9d1-319">探している言語が見つかったら、それを選択します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-319">When you find the language you're looking for, select it.</span></span> <span data-ttu-id="db9d1-320">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-320">Repeat this step as many times as necessary.</span></span>

       <span data-ttu-id="db9d1-321">選択した言語のリストがポップアップに表示されます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-321">The list of languages you selected appears on the flyout.</span></span> <span data-ttu-id="db9d1-322">言語を削除するには、</span><span class="sxs-lookup"><span data-stu-id="db9d1-322">To delete a language, click</span></span> ![[削除] ボタンをクリックします](../../media/scc-remove-icon.png)<span data-ttu-id="db9d1-324">。</span><span class="sxs-lookup"><span data-stu-id="db9d1-324">.</span></span>

     <span data-ttu-id="db9d1-325">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-325">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="db9d1-326">**次の国または地域から送信されたメール メッセージをフィルターします**: この設定は、既定では無効になっています (**状態: OFF**)。</span><span class="sxs-lookup"><span data-stu-id="db9d1-326">**Filter email messages sent from the following countries or regions**: This setting is disabled by default (**Status: OFF**).</span></span> <span data-ttu-id="db9d1-327">有効にするには、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-327">To enable it, click **Edit**.</span></span> <span data-ttu-id="db9d1-328">表示される **[海外からの迷惑メールの設定]** ポップアップで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-328">In the **International spam settings** flyout that appears, configure the following settings:</span></span>

     - <span data-ttu-id="db9d1-329">**次の国または地域から送信されたメール メッセージをフィルターします**: この設定を有効にするには、チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-329">**Filter email messages sent from the following countries or regions**: Select the checkbox to enable this setting.</span></span> <span data-ttu-id="db9d1-330">この設定を無効にするには、チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-330">Clear the checkbox to disable this setting.</span></span>

     - <span data-ttu-id="db9d1-331">ボックス内をクリックし、国または地域の*名前*の入力を始めます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-331">Click in the box and start typing the *name* of the country or region.</span></span> <span data-ttu-id="db9d1-332">フィルター処理の対象となる、サポートされている国のリストが、対応する ISO 3166-1 の 2 文字の国コードと共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-332">A filtered list of supported countries will appear, along with the corresponding ISO 3166-1 two-letter country code.</span></span> <span data-ttu-id="db9d1-333">探している国や地域が見つかったら、それを選択します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-333">When you find the country or region you're looking for, select it.</span></span> <span data-ttu-id="db9d1-334">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-334">Repeat this step as many times as necessary.</span></span>

       <span data-ttu-id="db9d1-335">選択した国のリストがポップアップに表示されます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-335">The list of countries you selected appears on the flyout.</span></span> <span data-ttu-id="db9d1-336">国または地域を削除するには、</span><span class="sxs-lookup"><span data-stu-id="db9d1-336">To delete a country or region, click</span></span> ![[削除] ボタンをクリックします](../../media/scc-remove-icon.png)<span data-ttu-id="db9d1-338">。</span><span class="sxs-lookup"><span data-stu-id="db9d1-338">.</span></span>

     <span data-ttu-id="db9d1-339">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-339">When you're finished, click **Save**.</span></span>

8. <span data-ttu-id="db9d1-340">オプションの **[迷惑メールのプロパティ]** セクションには、既定では無効になっている高度なスパム フィルター (ASF) 設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-340">The optional **Spam properties** section contains Advanced Spam Filter (ASF) settings that are turned off by default.</span></span> <span data-ttu-id="db9d1-341">ASF の設定は廃止の処理中です。この機能はフィルター処理スタックの別の部分に組み込まれます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-341">ASF settings are in the process of being deprecated, and their functionality is being incorporated into other parts of the filtering stack.</span></span> <span data-ttu-id="db9d1-342">これらの ASF 設定はすべて、スパム対策ポリシーでオフにしておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-342">We recommend that you leave all of these ASF settings turned off in your anti-spam policies.</span></span>

   <span data-ttu-id="db9d1-343">これらの設定の詳細については、「[Office 365 での高度なスパム フィルターの設定](advanced-spam-filtering-asf-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db9d1-343">For details about these settings, see [Advanced Spam Filter settings in Office 365](advanced-spam-filtering-asf-options.md).</span></span>

9. <span data-ttu-id="db9d1-344">(必須) **[適用先]** セクションを展開して、ポリシーの適用先にする内部受信者を特定します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-344">(Required) Expand the **Applied to** section to identify the internal recipients that the policy applies to.</span></span>

    <span data-ttu-id="db9d1-345">各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-345">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="db9d1-346">同じ条件や例外に複数の値がある場合は、OR ロジック (たとえば、_\<recipient1\>_ or _\<recipient2\>_) を使用します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-346">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="db9d1-347">別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ and _\<member of group 1\>_) を使用します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-347">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="db9d1-348">使用可能なすべての条件を表示するには、**[条件の追加]** を 3 回クリックするのが最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="db9d1-348">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="db9d1-349">構成しない条件を削除するには、![[削除] ボタン](../../media/scc-remove-icon.png)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-349">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="db9d1-350">**受信者のドメインが次の場合**: Office 365 で構成済みの 1 つ以上の承認済みドメイン内の受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-350">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in Office 365.</span></span> <span data-ttu-id="db9d1-351">**[タグの追加]** ボックスをクリックして、ドメインを表示および選択します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-351">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="db9d1-352">複数のドメインが利用可能な場合は、**[タグの追加]** ボックスをもう一度クリックして、追加のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-352">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="db9d1-353">**受信者が次の場合**: 組織内の 1 つ以上のメールボックス、メール ユーザー、またはメール連絡先を指定します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-353">**Recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span> <span data-ttu-id="db9d1-354">**[タグの追加]** をクリックして、リストをフィルター処理するための入力を始めます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-354">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="db9d1-355">**[タグの追加]** ボックスをもう一度クリックして、追加の受信者を選択します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-355">Click again the **Add a tag** box to select additional recipients.</span></span>

    - <span data-ttu-id="db9d1-356">**受信者が次のメンバーの場合**: 組織内の 1 つ以上のグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-356">**Recipient is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="db9d1-357">**[タグの追加]** をクリックして、リストをフィルター処理するための入力を始めます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-357">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="db9d1-358">**[タグの追加]** ボックスをもう一度クリックして、追加の受信者を選択します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-358">Click again the **Add a tag** box to select additional recipients.</span></span>

    - <span data-ttu-id="db9d1-359">**次の場合を除く**: ルールの例外を追加するには、**[条件の追加]** を 3 回クリックして、使用可能なすべての例外を表示します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-359">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="db9d1-360">設定と動作は、条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="db9d1-360">The settings and behavior are exactly like the conditions.</span></span>

10. <span data-ttu-id="db9d1-361">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-361">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-spam-policies"></a><span data-ttu-id="db9d1-362">セキュリティ/コンプライアンス センターを使用してスパム対策ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="db9d1-362">Use the Security & Compliance Center to view anti-spam policies</span></span>

1. <span data-ttu-id="db9d1-363">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-363">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="db9d1-364">**[迷惑メール対策の設定]** ページで、![[展開] アイコン](../../media/scc-expand-icon.png)をクリックして、迷惑メール対策ポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-364">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an anti-spam policy:</span></span>

   - <span data-ttu-id="db9d1-365">既定のポリシーには **[既定のスパム フィルター ポリシー]** という名前が付いています。</span><span class="sxs-lookup"><span data-stu-id="db9d1-365">The default policy named **Default spam filter policy**.</span></span>

   - <span data-ttu-id="db9d1-366">ユーザーが作成したカスタム ポリシーの場合、**[種類]** 列の値が **[Custom anti-spam policy]** (カスタム迷惑メール対策ポリシー) になっています。</span><span class="sxs-lookup"><span data-stu-id="db9d1-366">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>

3. <span data-ttu-id="db9d1-367">重要なポリシー設定は、ポリシー詳細を拡張すると表示されます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-367">The important policy settings are displayed in the expanded policy details that appear.</span></span> <span data-ttu-id="db9d1-368">詳細を表示するには、**[ポリシーの編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-368">To see more details, click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-spam-policies"></a><span data-ttu-id="db9d1-369">セキュリティ/コンプライアンス センターを使用して迷惑メール対策ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="db9d1-369">Use the Security & Compliance Center to modify anti-spam policies</span></span>

1. <span data-ttu-id="db9d1-370">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-370">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="db9d1-371">**[迷惑メール対策の設定]** ページで、![[展開] アイコン](../../media/scc-expand-icon.png)をクリックして、迷惑メール対策ポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-371">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an anti-spam policy:</span></span>

   - <span data-ttu-id="db9d1-372">既定のポリシーには **[既定のスパム フィルター ポリシー]** という名前が付いています。</span><span class="sxs-lookup"><span data-stu-id="db9d1-372">The default policy named **Default spam filter policy**.</span></span>

   - <span data-ttu-id="db9d1-373">ユーザーが作成したカスタム ポリシーの場合、**[種類]** 列の値が **[Custom anti-spam policy]** (カスタム迷惑メール対策ポリシー) になっています。</span><span class="sxs-lookup"><span data-stu-id="db9d1-373">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>

3. <span data-ttu-id="db9d1-374">**[ポリシーの編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-374">Click **Edit policy**.</span></span>

<span data-ttu-id="db9d1-375">カスタム迷惑メール対策ポリシーの場合、表示されるポップアップで使用できる設定は、「[セキュリティ/コンプライアンス センターを使用して迷惑メール対策ポリシーを作成する](#use-the-security--compliance-center-to-create-anti-spam-policies)」セクションで説明した設定と同じです。</span><span class="sxs-lookup"><span data-stu-id="db9d1-375">For custom anti-spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create anti-spam policies](#use-the-security--compliance-center-to-create-anti-spam-policies) section.</span></span>

<span data-ttu-id="db9d1-376">「**既定の迷惑メール対策ポリシー**」という名前の付いた既定の迷惑メール対策ポリシーの場合、**[適用先]** セクションは選択できず (ポリシーは全員に適用される)、ポリシーの名前を変更することもできません。</span><span class="sxs-lookup"><span data-stu-id="db9d1-376">For the default anti-spam policy named **Default spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="db9d1-377">ポリシーを有効または無効にするには、ポリシーの優先順位を設定するか、またはエンドユーザーの検疫通知を構成します。後続の各セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="db9d1-377">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-anti-spam-policies"></a><span data-ttu-id="db9d1-378">迷惑メール対策の有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="db9d1-378">Enable or disable anti-spam policies</span></span>

1. <span data-ttu-id="db9d1-379">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-379">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="db9d1-380">**[迷惑メール対策の設定]** ページで ![[展開] アイコン](../../media/scc-expand-icon.png) をクリックすると、作成したカスタム ポリシーが展開されます (**[種類]** 列の値は **[カスタム迷惑メール対策ポリシー]**)。</span><span class="sxs-lookup"><span data-stu-id="db9d1-380">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom anti-spam policy**).</span></span>

3. <span data-ttu-id="db9d1-381">展開して表示されたポリシー詳細で、**[On]** 列の値をメモします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-381">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="db9d1-382">ポリシーを無効にするには、左に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-382">Move the toggle to the left to disable the policy:</span></span> ![オフに切り替え](../../media/scc-toggle-off.png)

   <span data-ttu-id="db9d1-384">ポリシーを有効にするには、右に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-384">Move the toggle to the right to enable the policy:</span></span> ![オンに切り替え](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="db9d1-386">既定の迷惑メール対策ポリシーを無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="db9d1-386">You can't disable the default anti-spam policy.</span></span>

### <a name="set-the-priority-of-custom-anti-spam-policies"></a><span data-ttu-id="db9d1-387">カスタム迷惑メール対策ポリシーの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="db9d1-387">Set the priority of custom anti-spam policies</span></span>

<span data-ttu-id="db9d1-388">既定では、迷惑メール対策ポリシーには、ポリシーの作成順序に基づいた優先度が設定されます (新しいポリシーの優先度が古いポリシーよりも低くなります)。</span><span class="sxs-lookup"><span data-stu-id="db9d1-388">By default, anti-spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="db9d1-389">優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。</span><span class="sxs-lookup"><span data-stu-id="db9d1-389">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="db9d1-390">2 つのポリシーが同じ優先度を持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="db9d1-390">No two policies can have the same priority.</span></span>

<span data-ttu-id="db9d1-391">カスタム迷惑メール対策ポリシーは、処理される順に表示されます (最初のポリシーの値は **優先度** が 0)。</span><span class="sxs-lookup"><span data-stu-id="db9d1-391">Custom anti-spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="db9d1-392">「**既定のスパム フィルター ポリシー**」という名前の付いた既定の迷惑メール対策ポリシーには値 **[Lowest]** が付いており、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="db9d1-392">The default anti-spam policy named **Default spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="db9d1-393">**注**: セキュリティ/コンプライアンス センターでは、スパム対策ポリシーの作成後にその優先度のみを変更できます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-393">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-spam policy after you create it.</span></span> <span data-ttu-id="db9d1-394">PowerShell では、スパム フィルター ルールの作成時に既定の優先度を上書きできます (この上書きが既存のルールの優先度に影響を与えることがあります)。</span><span class="sxs-lookup"><span data-stu-id="db9d1-394">In PowerShell, you can override the default priority when you create the spam filter rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="db9d1-395">ポリシーの優先度を変更するには、リスト内で上下に移動させます (セキュリティ/コンプライアンス センター内で直接、**優先順位**番号を変更することはできません)。</span><span class="sxs-lookup"><span data-stu-id="db9d1-395">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="db9d1-396">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-396">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="db9d1-397">**[迷惑メール対策の設定]** ページで、**[種類]** 列の値が **[カスタム迷惑メール対策ポリシー]** のポリシーを検索します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-397">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom anti-spam policy**.</span></span> <span data-ttu-id="db9d1-398">**[優先度]** 列の値に注目します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-398">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="db9d1-399">最も高い優先度を持つカスタム迷惑メール対策ポリシーの値は ![下矢印アイコン](../../media/ITPro-EAC-DownArrowIcon.png) **0** です。</span><span class="sxs-lookup"><span data-stu-id="db9d1-399">The custom anti-spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="db9d1-400">最も低い優先度を持つカスタム迷惑メール対策ポリシーの値は ![上矢印アイコン](../../media/ITPro-EAC-UpArrowIcon.png) **n** です (たとえば、「![上矢印アイコン](../../media/ITPro-EAC-UpArrowIcon.png) **3**」)。</span><span class="sxs-lookup"><span data-stu-id="db9d1-400">The custom anti-spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="db9d1-401">3 つ以上のカスタム迷惑メール対策ポリシーがある場合、最も高い優先度と最も低い優先度の間のポリシーの値は、![上矢印アイコン](../../media/ITPro-EAC-UpArrowIcon.png)![下矢印アイコン](../../media/ITPro-EAC-DownArrowIcon.png) **n** になります (たとえば、![上矢印アイコン](../../media/ITPro-EAC-UpArrowIcon.png)![下矢印アイコン](../../media/ITPro-EAC-DownArrowIcon.png) **2**)。</span><span class="sxs-lookup"><span data-stu-id="db9d1-401">If you have three or more custom anti-spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="db9d1-402">上</span><span class="sxs-lookup"><span data-stu-id="db9d1-402">Click</span></span> ![矢印アイコン](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="db9d1-404">または</span><span class="sxs-lookup"><span data-stu-id="db9d1-404">or</span></span> ![下矢印アイコンをクリックして](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="db9d1-406">ポリシー リスト内のカスタム迷惑メール対策ポリシーを上下に移動します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-406">to move the custom anti-spam policy up or down in the priority list.</span></span>

### <a name="configure-end-user-spam-notifications"></a><span data-ttu-id="db9d1-407">エンドユーザーの迷惑メール通知の構成</span><span class="sxs-lookup"><span data-stu-id="db9d1-407">Configure end-user spam notifications</span></span>

<span data-ttu-id="db9d1-408">スパム対策フィルター判定によりメッセージが検疫された場合に、受信者に送信されたメッセージに対する処理を知らせるために、エンドユーザーの迷惑メール通知を構成できます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-408">When a spam filtering verdict quarantines a message, you can configure end-user spam notifications to let recipients know what happened to messages that were sent to them.</span></span> <span data-ttu-id="db9d1-409">これらの通知の詳細については、「[Office 365 でのエンドユーザーの迷惑メール通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db9d1-409">For more information about these notifications, see [End-user spam notifications in Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="db9d1-410">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-410">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="db9d1-411">**[迷惑メール対策の設定]** ページで、![[展開] アイコン](../../media/scc-expand-icon.png)をクリックして、迷惑メール対策ポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-411">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an anti-spam policy:</span></span>

   - <span data-ttu-id="db9d1-412">既定のポリシーには **[既定のスパム フィルター ポリシー]** という名前が付いています。</span><span class="sxs-lookup"><span data-stu-id="db9d1-412">The default policy named **Default spam filter policy**.</span></span>

   - <span data-ttu-id="db9d1-413">ユーザーが作成したカスタム ポリシーの場合、**[種類]** 列の値が **[Custom anti-spam policy]** (カスタム迷惑メール対策ポリシー) になっています。</span><span class="sxs-lookup"><span data-stu-id="db9d1-413">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>

3. <span data-ttu-id="db9d1-414">展開して表示されたポリシー詳細で、**[エンドユーザーのスパム通知を構成する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-414">In the expanded policy details that appear, click **Configure end-user spam notifications**.</span></span>

4. <span data-ttu-id="db9d1-415">**\<[ポリシー名]\>** ダイアログが開いたら、以下の設定を行います。</span><span class="sxs-lookup"><span data-stu-id="db9d1-415">In the **\<Policy Name\>** dialog that opens, configure the following settings:</span></span>

   - <span data-ttu-id="db9d1-416">**エンドユーザーのスパム通知を有効にする**: 通知を有効にするには、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-416">**Enable end-user spam notifications**: Select the checkbobx to enable notifications.</span></span> <span data-ttu-id="db9d1-417">通知を無効にするには、チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-417">Clear the checkbox to disable notifications.</span></span>

   - <span data-ttu-id="db9d1-418">**エンドユーザーの迷惑メール通知の送信間隔 (日)**: 通知が送信される頻度を選択します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-418">**Send end-user spam notifications every (days)**: Select how frequently notifications are sent.</span></span> <span data-ttu-id="db9d1-419">既定値は 3 日です。</span><span class="sxs-lookup"><span data-stu-id="db9d1-419">The default value is 3 days.</span></span> <span data-ttu-id="db9d1-420">1 日から 15 日まで入力できます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-420">You can enter 1 to 15 days.</span></span>

   - <span data-ttu-id="db9d1-421">**通知言語**: ドロップダウンをクリックして、リストから使用可能な言語を選びます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-421">**Notification language**: Click the drop down an select an available language from the list.</span></span> <span data-ttu-id="db9d1-422">既定値は **Default** で、エンドユーザーへの検疫通知では EOP 組織の既定の言語が使用されます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-422">The default value is **Default**, which means end-user quarantine notifications use the default language of the EOP organization.</span></span>

   <span data-ttu-id="db9d1-423">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-423">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-spam-policies"></a><span data-ttu-id="db9d1-424">セキュリティ/コンプライアンス センターを使用して迷惑メール対策ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="db9d1-424">Use the Security & Compliance Center to remove anti-spam policies</span></span>

1. <span data-ttu-id="db9d1-425">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-425">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="db9d1-426">**[迷惑メール対策の設定]** ページで、![[展開] アイコン](../../media/scc-expand-icon.png)をクリックし、削除するカスタム ポリシーを展開します (**[種類]** 列の値は **[カスタム迷惑メール対策ポリシー]**)。</span><span class="sxs-lookup"><span data-stu-id="db9d1-426">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom anti-spam policy**).</span></span>

3. <span data-ttu-id="db9d1-427">展開されたポリシー詳細で、**[ポリシーの削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-427">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="db9d1-428">警告ダイアログが表示されたら、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-428">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="db9d1-429">既定のポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="db9d1-429">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-anti-spam-policies"></a><span data-ttu-id="db9d1-430">Exchange Online PowerShell または Exchange Online Protection PowerShell を使用して迷惑メール対策ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="db9d1-430">Use Exchange Online PowerShell or Exchange Online Protection PowerShell to configure anti-spam policies</span></span>

<span data-ttu-id="db9d1-431">次の迷惑メール対策ポリシー設定は、PowerShell でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-431">The following anti-spam policy settings are only available in PowerShell:</span></span>

- <span data-ttu-id="db9d1-432">_MarkAsSpamBulkMail_ パラメーター (既定は `On`)。</span><span class="sxs-lookup"><span data-stu-id="db9d1-432">The _MarkAsSpamBulkMail_ parameter that's `On` by default.</span></span> <span data-ttu-id="db9d1-433">この設定の影響については、このトピックで前述した「[セキュリティ/コンプライアンス センターを使用して迷惑メール対策ポリシーを作成する](#use-the-security--compliance-center-to-create-anti-spam-policies)」で説明されています。</span><span class="sxs-lookup"><span data-stu-id="db9d1-433">The effects of this setting were explained in the [Use the Security & Compliance Center to create anti-spam policies](#use-the-security--compliance-center-to-create-anti-spam-policies) section earlier in this topic.</span></span>

- <span data-ttu-id="db9d1-434">次の設定は、エンドユーザーの迷惑メール検疫通知の設定です。</span><span class="sxs-lookup"><span data-stu-id="db9d1-434">The following settings for end-user spam quarantine notifications:</span></span>

  - <span data-ttu-id="db9d1-435">_DownloadLink_ パラメーター。これにより、Outlook の迷惑メール報告ツールへのリンクを表示または非表示にできます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-435">The _DownloadLink_ parameter that shows or hides the link to the Junk Email Reporting Tool for Outlook.</span></span>

  - <span data-ttu-id="db9d1-436">_EndUserSpamNotificationCustomSubject_ パラメーター。これにより、通知の件名行をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-436">The _EndUserSpamNotificationCustomSubject_ parameter that you can use to customize the subject line of the notification.</span></span>

### <a name="use-powershell-to-create-anti-spam-policies"></a><span data-ttu-id="db9d1-437">PowerShell を使用して迷惑メール対策ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="db9d1-437">Use PowerShell to create anti-spam policies</span></span>

<span data-ttu-id="db9d1-438">PowerShell では、2 段階の手順で迷惑メール対策ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-438">Creating an anti-spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="db9d1-439">スパム フィルター ポリシーを作成する。</span><span class="sxs-lookup"><span data-stu-id="db9d1-439">Create the spam filter policy.</span></span>

2. <span data-ttu-id="db9d1-440">スパム フィルター ルールの適用先とするスパム フィルター ポリシーを指定するルールを作成する。</span><span class="sxs-lookup"><span data-stu-id="db9d1-440">Create the spam filter rule that specifies the spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="db9d1-441">**注**:</span><span class="sxs-lookup"><span data-stu-id="db9d1-441">**Notes**:</span></span>

- <span data-ttu-id="db9d1-442">新しいスパム フィルター ルールを作成して、既存の関連付けされていないスパム フィルター ポリシーをそれに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-442">You can create a new spam filter rule and assign an existing, unassociated spam filter policy to it.</span></span> <span data-ttu-id="db9d1-443">1 つのスパム フィルター ルールを複数のスパム フィルター ポリシーに関連付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="db9d1-443">A spam filter rule can't be associated with more than one spam filter policy.</span></span>

- <span data-ttu-id="db9d1-444">ポリシーを作成してからでなければセキュリティ/コンプライアンス センターで使用できない次の設定を、PowerShell で新しいスパム フィルター ポリシーに構成できます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-444">You can configure the following settings on new spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="db9d1-445">新しいポリシーを無効化された状態で作成する (**New-HostedContentFilterRule** コマンドレットで _Enabled_`$false` を指定)。</span><span class="sxs-lookup"><span data-stu-id="db9d1-445">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedContentFilterRule** cmdlet).</span></span>

  - <span data-ttu-id="db9d1-446">作成時にポリシーの優先度を設定する (**New-HostedContentFilterRule** コマンドレットで _Priority_ _\<Number\>_ を指定)。</span><span class="sxs-lookup"><span data-stu-id="db9d1-446">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedContentFilterRule** cmdlet).</span></span>

- <span data-ttu-id="db9d1-447">ポリシーをスパム フィルター ルールに割り当てるまでは、PowerShell で作成した新しいスパム フィルター ポリシーをセキュリティ/コンプライアンス センターに表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="db9d1-447">A new spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a><span data-ttu-id="db9d1-448">手順 1: PowerShell を使用してスパム フィルター ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="db9d1-448">Step 1: Use PowerShell to create a spam filter policy</span></span>

<span data-ttu-id="db9d1-449">スパム フィルター ポリシーを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-449">To create a spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="db9d1-450">この例では、次のような設定で Contoso Executives という名前のスパム フィルター ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-450">This example creates a spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="db9d1-451">スパム対策フィルター判定が「スパム」または「高確度スパム」の場合は、メッセージを検疫します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-451">Quarantine messages when the spam filtering verdict is spam or high confidence spam.</span></span>

- <span data-ttu-id="db9d1-452">BCL 6 で、「バルク メール」スパム対策フィルター判定のアクションがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-452">BCL 6 triggers the action for a bulk email spam filtering verdict.</span></span>

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

> [!NOTE]
> <span data-ttu-id="db9d1-453">**New-HostedContentFilterPolicy** と **Set-HostedContentFilterPolicy** には古い _ZapEnabled_ パラメーターと、新しい _PhishZapEnabled_ および _SpamZapEnabled_ パラメーターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="db9d1-453">**New-HostedContentFilterPolicy** and **Set-HostedContentFilterPolicy** contain an older _ZapEnabled_ parameter, as well as newer _PhishZapEnabled_ and _SpamZapEnabled_ parameters.</span></span> <span data-ttu-id="db9d1-454">_ZapEnabled_ パラメーターは 2020 年 2 月に廃止されました。</span><span class="sxs-lookup"><span data-stu-id="db9d1-454">The _ZapEnabled_ parameter was deprecated in February, 2020.</span></span> <span data-ttu-id="db9d1-455">_PhishZapEnabled_ および _SpamZapEnabled_ パラメーターでは、値を _ZapEnabled_ パラメーターから継承して使っていました。</span><span class="sxs-lookup"><span data-stu-id="db9d1-455">The _PhishZapEnabled_ and _SpamZapEnabled_ parameters used to inherit their values from the _ZapEnabled_ parameter.</span></span> <span data-ttu-id="db9d1-456">ただし、コマンドで _PhishZapEnabled_ や _SpamZapEnabled_ パラメーターを使用する場合や、セキュリティ/コンプライアンス センターで **[Spam ZAP]** (迷惑メールに対する ZAP) 設定や **[フィッシング詐欺に対する ZAP]** 設定を使用する場合、_ZapEnabled_ パラメーターの値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-456">But, if you use the _PhishZapEnabled_ and _SpamZapEnabled_ parameters in a command or you use the **Spam ZAP** or **Phish ZAP** settings in the anti-spam policy in the Security & Compliance Center, the value of the _ZapEnabled_ parameter is ignored.</span></span> <span data-ttu-id="db9d1-457">つまり、_ZapEnabled_ パラメーターは使用せず、代わりに _PhishZapEnabled_ および _SpamZapEnabled_ パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-457">In other words, don't use the _ZapEnabled_ parameter; use the  _PhishZapEnabled_ and _SpamZapEnabled_ parameters instead.</span></span>

<span data-ttu-id="db9d1-458">構文とパラメーターの詳細については、「[New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedcontentfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db9d1-458">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedcontentfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-spam-filter-rule"></a><span data-ttu-id="db9d1-459">手順 2: PowerShell を使用してスパム フィルター ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="db9d1-459">Step 2: Use PowerShell to create a spam filter rule</span></span>

<span data-ttu-id="db9d1-460">スパム フィルター ルールを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-460">To create a spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedContentFilterRule -Name "<RuleName>" -HostedContentFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="db9d1-461">この例では、次に示す設定で Contoso Executives という新しいスパム フィルター ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-461">This example creates a new spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="db9d1-462">Contoso Executives という名前のスパム フィルター ポリシーがルールに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="db9d1-462">The spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="db9d1-463">ルールは Contoso Executives Group という名前のグループのメンバーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-463">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedContentFilterRule -Name "Contoso Executives" -HostedContentFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="db9d1-464">構文とパラメーターの詳細については、「[New-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedcontentfilterrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db9d1-464">For detailed syntax and parameter information, see [New-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-view-spam-filter-policies"></a><span data-ttu-id="db9d1-465">PowerShell を使用してスパム フィルター ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="db9d1-465">Use PowerShell to view spam filter policies</span></span>

<span data-ttu-id="db9d1-466">すべてのスパム フィルター ポリシーの要約リストを返すには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-466">To return a summary list of all spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedContentFilterPolicy
```

<span data-ttu-id="db9d1-467">特定のスパム フィルター ポリシーに関する詳細情報を返すには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-467">To return detailed information about a specific spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedContentFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="db9d1-468">この例では、Executives というスパム フィルター ポリシーのすべてのプロパティの値を戻します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-468">This example returns all the property values for the spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedContentFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="db9d1-469">構文とパラメーターの詳細については、「[Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedcontentfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db9d1-469">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-view-spam-filter-rules"></a><span data-ttu-id="db9d1-470">PowerShell を使用してスパム フィルター ルールを表示する</span><span class="sxs-lookup"><span data-stu-id="db9d1-470">Use PowerShell to view spam filter rules</span></span>

<span data-ttu-id="db9d1-471">既存のスパム フィルター ルールを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-471">To view existing spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedContentFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="db9d1-472">すべてのスパム フィルター ルールの要約リストを返すには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-472">To return a summary list of all spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedContentFilterRule
```

<span data-ttu-id="db9d1-473">ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-473">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedContentFilterRule -State Disabled
```

```PowerShell
Get-HostedContentFilterRule -State Enabled
```

<span data-ttu-id="db9d1-474">特定のスパム フィルター ルールの詳細情報を返すには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-474">To return detailed information about a specific spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedContentFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="db9d1-475">この例では、Contoso Executives というスパム フィルター ルールのすべてのプロパティの値を返します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-475">This example returns all the property values for the spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedContentFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="db9d1-476">構文とパラメーターの詳細については、「[Get-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedcontentfilterrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db9d1-476">For detailed syntax and parameter information, see [Get-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-modify-spam-filter-policies"></a><span data-ttu-id="db9d1-477">PowerShell を使用してスパム フィルター ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="db9d1-477">Use PowerShell to modify spam filter policies</span></span>

<span data-ttu-id="db9d1-478">以下の項目以外には、このトピックで前述の「[手順 1: PowerShell を使用してスパム フィルター ポリシーを作成する](#step-1-use-powershell-to-create-a-spam-filter-policy)」で説明されたようにポリシーを作成したときと同じ設定を、PowerShell を使ってスパム フィルター ポリシーを変更するときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-478">Other than the following items, the same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create a spam filter policy](#step-1-use-powershell-to-create-a-spam-filter-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="db9d1-479">特定のポリシーを既定のポリシー (全員に適用され、常に **Lowest** 優先度を持ち、削除することはできない) に切り替える _MakeDefault_ スイッチは、PowerShell でスパム フィルター ポリシーを変更するときにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-479">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify a spam filter policy in PowerShell.</span></span>

- <span data-ttu-id="db9d1-480">スパム フィルター ポリシーの名前を変更することはできません (**Set-HostedContentFilterPolicy** コマンドレットには _Name_ パラメーターがありません)。</span><span class="sxs-lookup"><span data-stu-id="db9d1-480">You can't rename a spam filter policy (the **Set-HostedContentFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="db9d1-481">セキュリティ/コンプライアンス センターでスパム対策ポリシーの名前を変更する場合は、スパム フィルター _ルール_の名前を変更するだけになります。</span><span class="sxs-lookup"><span data-stu-id="db9d1-481">When you rename an anti-spam policy in the Security & Compliance Center, you're only renaming the spam filter _rule_.</span></span>

<span data-ttu-id="db9d1-482">スパム フィルター ポリシーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-482">To modify a spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="db9d1-483">構文とパラメーターの詳細については、「[Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db9d1-483">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-spam-filter-rules"></a><span data-ttu-id="db9d1-484">PowerShell を使用してスパム フィルター ルールを変更する</span><span class="sxs-lookup"><span data-stu-id="db9d1-484">Use PowerShell to modify spam filter rules</span></span>

<span data-ttu-id="db9d1-485">PowerShell でスパム フィルター ルールを変更するときに使用できない唯一の設定は、無効なルールの作成を可能にする _Enabled_ パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="db9d1-485">The only setting that isn't available when you modify a spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="db9d1-486">既存のスパム フィルター ルールを有効または無効にするには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="db9d1-486">To enable or disable existing spam filter rules, see the next section.</span></span>

<span data-ttu-id="db9d1-487">それ以外は、PowerShell でスパム フィルター ルールを変更する際に利用可能な追加の設定はありません。</span><span class="sxs-lookup"><span data-stu-id="db9d1-487">Otherwise, no additional settings are available when you modify a spam filter rule in PowerShell.</span></span> <span data-ttu-id="db9d1-488">このトピックで前述の「[手順 2: PowerShell を使用してスパム フィルター ルールを作成する](#step-2-use-powershell-to-create-a-spam-filter-rule)」セクションでルールを作成したときと同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-488">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a spam filter rule](#step-2-use-powershell-to-create-a-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="db9d1-489">スパム フィルター ルールを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-489">To modify a spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="db9d1-490">この例では、セキュリティ/コンプライアンス センターで問題を発生させる可能性がある `{Fabrikam Spam Filter}` という名前の既存のスパム フィルター ルールの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-490">This example renames the existing spam filter rule named `{Fabrikam Spam Filter}` that might cause problems in the Security & Compliance Center.</span></span>

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

<span data-ttu-id="db9d1-491">構文とパラメーターの詳細については、「[Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db9d1-491">For detailed syntax and parameter information, see [Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-spam-filter-rules"></a><span data-ttu-id="db9d1-492">PowerShell を使ってスパム フィルター ルールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="db9d1-492">Use PowerShell to enable or disable spam filter rules</span></span>

<span data-ttu-id="db9d1-493">PowerShell でスパム フィルター ルールを有効または無効にすると、すべての迷惑メール対策ポリシー (スパム フィルター ルールおよび割り当てられているスパム フィルター ポリシー) が有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="db9d1-493">Enabling or disabling a spam filter rule in PowerShell enables or disables the whole anti-spam policy (the spam filter rule and the assigned spam filter policy).</span></span> <span data-ttu-id="db9d1-494">既定の迷惑メール対策ポリシーを有効または無効にすることはできません (常にすべての受信者に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="db9d1-494">You can't enable or disable the default anti-spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="db9d1-495">PowerShell でスパム フィルター ルールを有効または無効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-495">To enable or disable a spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedContentFilterRule | Disable-HostedContentFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="db9d1-496">この例では、Marketing Department というスパム フィルター ルールを無効化します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-496">This example disables the spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="db9d1-497">この例では、同じルールを有効化します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-497">This example enables same rule.</span></span>

```PowerShell
Enable-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="db9d1-498">構文とパラメーターの詳細については、「[Enable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedcontentfilterrule)」と「[Disable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedcontentfilterrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db9d1-498">For detailed syntax and parameter information, see [Enable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedcontentfilterrule) and [Disable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-spam-filter-rules"></a><span data-ttu-id="db9d1-499">PowerShell を使用してスパム フィルター ルールの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="db9d1-499">Use PowerShell to set the priority of spam filter rules</span></span>

<span data-ttu-id="db9d1-500">ルールに設定できる優先度の最高値値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="db9d1-500">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="db9d1-501">設定できる最低値はルールの数に依存します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-501">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="db9d1-502">たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。</span><span class="sxs-lookup"><span data-stu-id="db9d1-502">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="db9d1-503">既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-503">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="db9d1-504">たとえば、カスタム ルールが 5 つあって (優先度 0 から 4)、1 つのルールの優先度を 2 に変更した場合には、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-504">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="db9d1-505">PowerShell でスパム フィルター ルールの優先度を設定するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-505">To set the priority of a spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="db9d1-p174">この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。</span><span class="sxs-lookup"><span data-stu-id="db9d1-p174">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="db9d1-508">**注**:</span><span class="sxs-lookup"><span data-stu-id="db9d1-508">**Notes**:</span></span>

- <span data-ttu-id="db9d1-509">新しく作成したルールの優先度を設定するには、_New-HostedContentFilterRule_ コマンドレットの **Priority** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-509">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedContentFilterRule** cmdlet instead.</span></span>

- <span data-ttu-id="db9d1-510">既定のスパム フィルター ポリシーには、対応するスパム フィルター ルールがありません。また、常に、**Lowest** の優先度が設定されており、変更はできません。</span><span class="sxs-lookup"><span data-stu-id="db9d1-510">The default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-spam-filter-policies"></a><span data-ttu-id="db9d1-511">PowerShell を使用してスパム フィルター ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="db9d1-511">Use PowerShell to remove spam filter policies</span></span>

<span data-ttu-id="db9d1-512">PowerShell を使用してスパム フィルター ポリシーを削除しても、それに対応するスパム フィルター ルールは削除されません。</span><span class="sxs-lookup"><span data-stu-id="db9d1-512">When you use PowerShell to remove a spam filter policy, the corresponding spam filter rule isn't removed.</span></span>

<span data-ttu-id="db9d1-513">PowerShell でスパム フィルター ポリシーを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-513">To remove a spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedContentFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="db9d1-514">この例では、Marketing Department というスパム フィルター ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-514">This example removes the spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedContentFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="db9d1-515">構文とパラメーターの詳細については、「[Remove-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedcontentfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db9d1-515">For detailed syntax and parameter information, see [Remove-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-spam-filter-rules"></a><span data-ttu-id="db9d1-516">PowerShell を使用してスパム フィルター ルールを削除する</span><span class="sxs-lookup"><span data-stu-id="db9d1-516">Use PowerShell to remove spam filter rules</span></span>

<span data-ttu-id="db9d1-517">PowerShell を使用してスパム フィルター ルールを削除しても、それに対応するスパム フィルター ポリシーは削除されません。</span><span class="sxs-lookup"><span data-stu-id="db9d1-517">When you use PowerShell to remove a spam filter rule, the corresponding spam filter policy isn't removed.</span></span>

<span data-ttu-id="db9d1-518">PowerShell でスパム フィルター ルールを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-518">To remove a spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedContentFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="db9d1-519">この例では、Marketing Department というスパム フィルター ルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-519">This example removes the spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="db9d1-520">構文とパラメーターの詳細については、「[Remove-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedcontentfilterrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db9d1-520">For detailed syntax and parameter information, see [Remove-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedcontentfilterrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="db9d1-521">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="db9d1-521">How do you know these procedures worked?</span></span>

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a><span data-ttu-id="db9d1-522">GTUBE メッセージを送信して迷惑メール対策ポリシーの設定をテストする</span><span class="sxs-lookup"><span data-stu-id="db9d1-522">Send a GTUBE message to test your spam policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="db9d1-523">これらの手順は、GTUBE メッセージを送信している電子メール組織が、送信スパムをスキャンしない場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="db9d1-523">These steps will only work if the email organization that you're sending the GTUBE message from doesn't scan for outbound spam.</span></span> <span data-ttu-id="db9d1-524">送信スパムをスキャンしている場合には、テスト メッセージは送信されません。</span><span class="sxs-lookup"><span data-stu-id="db9d1-524">If it does, the test message can't be sent.</span></span>

<span data-ttu-id="db9d1-525">Generic Test for Unsolicited Bulk Email (GTUBE) は、テスト メッセージに組み込んで組織のスパム対策設定を検証するための文字列です。</span><span class="sxs-lookup"><span data-stu-id="db9d1-525">Generic Test for Unsolicited Bulk Email (GTUBE) is a text string that you include in a test message to verify your organization's anti-spam settings.</span></span> <span data-ttu-id="db9d1-526">GTUBE メッセージは、マルウェア設定をテストするための European Institute for Computer Antivirus Research (EICAR) テキスト ファイルと似ています。</span><span class="sxs-lookup"><span data-stu-id="db9d1-526">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

<span data-ttu-id="db9d1-527">次の GTUBE テキストを、スペースや改行なしで 1 行で電子メール メッセージに入れます。</span><span class="sxs-lookup"><span data-stu-id="db9d1-527">Include the following GTUBE text in an email message on a single line, without any spaces or line breaks:</span></span>

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="allowblock-lists"></a><span data-ttu-id="db9d1-528">許可リストと禁止リスト</span><span class="sxs-lookup"><span data-stu-id="db9d1-528">Allow/Block Lists</span></span>

<span data-ttu-id="db9d1-529">メッセージがフィルターを通過してしまう場合や、システムが処理に追いつくために時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="db9d1-529">There will be times when our filters will miss the message or it takes time for our systems to catch up to it.</span></span> <span data-ttu-id="db9d1-530">このような場合のために、スパム対策ポリシーには、現在の判定を上書きするために使用できる許可リストと禁止リストが用意されています。</span><span class="sxs-lookup"><span data-stu-id="db9d1-530">In this cases, the antispam policy has an Allow and a Block list available to override the current verdict.</span></span> <span data-ttu-id="db9d1-531">このオプションは、リストが管理不能なほどにならないよう、控えめに使用する必要があります。また、フィルター処理スタックがその本来の処理を実行すべきであるので、一時的に使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="db9d1-531">This option should only be used sparingly since lists can become unmanageable and temporarily since our filtering stack should be doing what it is supposed to be doing.</span></span>

> [!TIP]
> <span data-ttu-id="db9d1-532">組織の判定が、このサービスが提供する判定と一致しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="db9d1-532">There may be situations where your organization may not agree with the verdict the service provides.</span></span> <span data-ttu-id="db9d1-533">そのような場合、許可リストと禁止リストを永続的に保持することがあります。</span><span class="sxs-lookup"><span data-stu-id="db9d1-533">In this case, you may want to keep the Allow or Block listing permanent.</span></span> <span data-ttu-id="db9d1-534">ただし、ドメインをかなりの期間にわたって許可リストに追加するような場合は、送信者のドメインが認証済みであることを確認するように送信者に伝える必要があります。認証済みでない場合は、DMARC 拒否に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db9d1-534">However, if you are going to put a domain on the Allow list for extended periods of time, you should tell the sender to make sure that their domain is authenticated and set to DMARC reject if it is not.</span></span>
