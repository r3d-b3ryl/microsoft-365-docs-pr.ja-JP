---
title: スパム フィルター ポリシーの構成
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: 管理者が、Exchange Online Protection (EOP) で迷惑メール対策ポリシーを表示、作成、変更、削除する方法を説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 78cfef52988e7da611edc0cc4d475e8a4624bc0e
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879098"
---
# <a name="configure-anti-spam-policies-in-eop"></a><span data-ttu-id="04373-103">EOP でのスパム対策ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="04373-103">Configure anti-spam policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="04373-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="04373-104">**Applies to**</span></span>
- [<span data-ttu-id="04373-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="04373-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="04373-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="04373-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="04373-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="04373-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="04373-108">Exchange Online のメールボックスを使用している Microsoft 365 の組織、または Exchange Online のメールボックスを使用していないもののスタンドアロンの Exchange Online Protection (EOP) をお使いの組織の場合、受信メール メッセージは EOP によってスパムから自動的に保護されます。</span><span class="sxs-lookup"><span data-stu-id="04373-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spam by EOP.</span></span> <span data-ttu-id="04373-109">EOP では、スパムに対する組織の全体的防御の一環として、スパム対策ポリシー (スパム フィルター ポリシーまたはコンテンツ フィルター ポリシーとも呼ばれます) を使用します。</span><span class="sxs-lookup"><span data-stu-id="04373-109">EOP uses anti-spam policies (also known as spam filter policies or content filter policies) as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="04373-110">詳細については、「[スパム対策保護](anti-spam-protection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04373-110">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="04373-111">管理者は、既定のスパム対策ポリシーの表示、編集、構成を行うことができます (削除はできません)。</span><span class="sxs-lookup"><span data-stu-id="04373-111">Admins can view, edit, and configure (but not delete) the default anti-spam policy.</span></span> <span data-ttu-id="04373-112">より細かく設定できるように、カスタムのスパム対策保護ポリシーを作成し、組織内の指定したユーザー、グループ、またはドメインに適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="04373-112">For greater granularity, you can also create custom anti-spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="04373-113">カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (実行順序) を変更できます。</span><span class="sxs-lookup"><span data-stu-id="04373-113">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="04373-114">スパム対策ポリシーの構成は、Microsoft 365 Defender ポータルで、または PowerShell (Exchange Online にメールボックスを持つ Microsoft 365 の組織向け Exchange Online PowerShell、Exchange Online メールボックスを持たない組織向けのスタンドアロン EOP PowerShell) で行います。</span><span class="sxs-lookup"><span data-stu-id="04373-114">You can configure anti-spam policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="04373-115">スパム対策ポリシーの基本的な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="04373-115">The basic elements of an anti-spam policy are:</span></span>

- <span data-ttu-id="04373-116">**スパム フィルター ポリシー**: スパム フィルター判定のアクションと通知オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="04373-116">**The spam filter policy**: Specifies the actions for spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="04373-117">**スパム フィルター ルール**: スパム フィルター ポリシーの優先順位と受信者フィルター (ポリシーが適用される対象者) を指定します。</span><span class="sxs-lookup"><span data-stu-id="04373-117">**The spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a spam filter policy.</span></span>

<span data-ttu-id="04373-118">これら 2 つの要素の違いは、Microsoft 365 Defender ポータルでスパム対策ポリシーを管理する際には明白ではありませんが、以下の違いがあります。</span><span class="sxs-lookup"><span data-stu-id="04373-118">The difference between these two elements isn't obvious when you manage anti-spam polices in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="04373-119">スパム対策ポリシーを作成する場合、実際にはスパム フィルター ルール、および関連付けられているスパム フィルター ポリシーの両方に同じ名前を使用して同時に作成しています。</span><span class="sxs-lookup"><span data-stu-id="04373-119">When you create an anti-spam policy, you're actually creating a spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="04373-p103">セキュリティ/コンプライアンス センターでスパム対策ポリシーを変更する場合、名前、優先順位、有効/無効の切り替え、そして受信者フィルターに関連する設定の変更は、実際にはスパム フィルター ルールを変更しています。他のすべての設定は、関連付けられているスパム フィルター ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="04373-p103">When you modify an anti-spam policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the spam filter rule. All other settings modify the associated spam filter policy.</span></span>
- <span data-ttu-id="04373-122">スパム対策ポリシーを削除すると、スパム フィルター ルールおよび関連付けられたスパム フィルター ポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="04373-122">When you remove an anti-spam policy, the spam filter rule and the associated spam filter policy are removed.</span></span>

<span data-ttu-id="04373-123">Exchange Online PowerShell またはスタンドアロン EOP PowerShell では、ポリシーとルールを個別に管理します。</span><span class="sxs-lookup"><span data-stu-id="04373-123">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="04373-124">詳細については、この記事で後述する「[Exchange Online PowerShell または スタンドアロン EOP PowerShell を使用して迷惑メール対策ポリシーを構成する](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="04373-124">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure anti-spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies) section later in this article.</span></span>

<span data-ttu-id="04373-125">各組織には Default という名前の組み込みのスパム対策ポリシーがあり、以下の特徴があります。</span><span class="sxs-lookup"><span data-stu-id="04373-125">Every organization has a built-in anti-spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="04373-126">ポリシーに関連付けられているスパム フィルター ルール (受信者フィルター) がない場合でも、ポリシーは組織内の全受信者に適用されます。</span><span class="sxs-lookup"><span data-stu-id="04373-126">The policy is applied to all recipients in the organization, even though there's no spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="04373-127">ポリシーにはカスタムの優先順位の値 **Lowest** が設定されており、変更することはできません (このポリシーは常に最後に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="04373-127">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="04373-128">作成するどのカスタム ポリシーも、より高い優先順位を持ちます。</span><span class="sxs-lookup"><span data-stu-id="04373-128">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="04373-129">ポリシーは既定のポリシー (**IsDefault** のプロパティが `True` の値になっている) であり、既定のポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="04373-129">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="04373-130">スパム フィルター処理の有効性を高めるために、特定のユーザーまたはユーザー グループに適用される、より厳密な設定を持つカスタムのスパム対策ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="04373-130">To increase the effectiveness of spam filtering, you can create custom anti-spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="04373-131">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="04373-131">What do you need to know before you begin?</span></span>

- <span data-ttu-id="04373-132"><https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。</span><span class="sxs-lookup"><span data-stu-id="04373-132">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="04373-133">**[スパム対策ポリシー]** ページに直接移動するには、<https://security.microsoft.com/antispam> を使用します。</span><span class="sxs-lookup"><span data-stu-id="04373-133">To go directly to the **Anti-spam policies** page, use <https://security.microsoft.com/antispam>.</span></span>

- <span data-ttu-id="04373-134">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04373-134">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="04373-135">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04373-135">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="04373-136">この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="04373-136">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="04373-137">スパム対策ポリシーを追加、変更、削除するには、「**組織管理**」または「**セキュリティ管理者**」役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="04373-137">To add, modify, and delete anti-spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="04373-138">スパム対策ポリシーに読み取り専用でアクセスするには、「**グローバル閲覧者**」あるいは「**セキュリティ閲覧者**」役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="04373-138">For read-only access to anti-spam policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="04373-139">詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04373-139">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="04373-140">**注**:</span><span class="sxs-lookup"><span data-stu-id="04373-140">**Notes**:</span></span>

  - <span data-ttu-id="04373-141">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="04373-141">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="04373-142">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04373-142">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="04373-143">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。</span><span class="sxs-lookup"><span data-stu-id="04373-143">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="04373-144">スパム対策ポリシーに推奨される設定については、「[EOP スパム対策ポリシーの設定](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04373-144">For our recommended settings for anti-spam policies, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-spam-policies"></a><span data-ttu-id="04373-145">Microsoft 365 Defender ポータルを使用して、スパム対策ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="04373-145">Use the Microsoft 365 Defender portal to create anti-spam policies</span></span>

<span data-ttu-id="04373-146">Microsoft 365 Defender ポータルでカスタムのスパム対策ポリシーを作成すると、スパム フィルター ルールと関連するスパム フィルター ポリシーが同時に作成され、両方に同じ名前が使われます。</span><span class="sxs-lookup"><span data-stu-id="04373-146">Creating a custom anti-spam policy in the Microsoft 365 Defender portal creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="04373-147">Microsoft 365 Defender ポータルで、**[メールと共同作業]**、\>**[ポリシーとルール]**、\>**[脅威ポリシー]**、\>**[ポリシー** セクション]\> **[スパム対策]**.の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="04373-147">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="04373-148">**[スパム対策ポリシー]** ページで、![[アイコンの作成]](../../media/m365-cc-sc-create-icon.png) **[ポリシーの作成]** の順にクリックして、ドロップ ダウンリストから **[Iインバウンド]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="04373-148">On the **Anti-spam policies** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create policy** and then select **Inbound** from the drop down list.</span></span>

3. <span data-ttu-id="04373-149">ポリシー ウィザードが開きます。</span><span class="sxs-lookup"><span data-stu-id="04373-149">The policy wizard opens.</span></span> <span data-ttu-id="04373-150">**［ポリシーの名前を設定する］ ページ** で、以下の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="04373-150">On the **Name your policy page**, configure these settings:</span></span>
   - <span data-ttu-id="04373-151">**[名前]**: わかりやすい一意のポリシー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="04373-151">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="04373-152">**[説明]**: ポリシーについての説明を入力します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="04373-152">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="04373-153">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04373-153">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="04373-154">表示される **ユーザー、グループ、およびドメイン** ページで、ポリシーを適用する内部の受信者を特定します (受信者条件)。</span><span class="sxs-lookup"><span data-stu-id="04373-154">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="04373-155">**ユーザー**: 組織内で指定された 1 つ以上のメールボックス、メール ユーザー、またはメール連絡先。</span><span class="sxs-lookup"><span data-stu-id="04373-155">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="04373-156">**グループ**: 組織内で指定された配布グループ、メール対応セキュリティ グループ、または Microsoft 365 グループ。</span><span class="sxs-lookup"><span data-stu-id="04373-156">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="04373-157">**ドメイン**: 組織内で指定された [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)のすべての受信者。</span><span class="sxs-lookup"><span data-stu-id="04373-157">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="04373-158">適正なボックスをクリックし、値の入力を開始し、結果で希望する値を選択します。</span><span class="sxs-lookup"><span data-stu-id="04373-158">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="04373-159">必要な回数だけこの処理を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="04373-159">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="04373-160">既存の値を削除するには、削除をクリックします</span><span class="sxs-lookup"><span data-stu-id="04373-160">To remove an existing value, click remove</span></span> ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="04373-162">値の隣。</span><span class="sxs-lookup"><span data-stu-id="04373-162">next to the value.</span></span>

   <span data-ttu-id="04373-163">ユーザーやグループには、ほとんどの識別子 (名前、表示名、エイリアス、メールアドレス、アカウント名など) を使用できますが、対応する表示名が結果に表示されます。</span><span class="sxs-lookup"><span data-stu-id="04373-163">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="04373-164">ユーザーの場合、アスタリスク (\*) を単独で入力すると、使用可能なすべての値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="04373-164">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="04373-165">同じ条件に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="04373-165">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="04373-166">別の条件では、AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) を使用します。</span><span class="sxs-lookup"><span data-stu-id="04373-166">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="04373-167">**これらのユーザー、グループ、およびドメインを除外する**: ポリシーが適用される内部の受信者に関する例外 (受信者の例外) を追加するには、このオプションを選択して例外を構成します。</span><span class="sxs-lookup"><span data-stu-id="04373-167">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="04373-168">設定と動作は、条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="04373-168">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="04373-169">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04373-169">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="04373-170">表示される **[一括メールのしきい値と迷惑メール プロパティ**] ページで、以下の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="04373-170">On the **Bulk email threshold & spam properties** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="04373-171">**一括メールのしきい値**: 次のページで、**一括** スパム対策フィルター判定に指定されたアクションをトリガーするメッセージの Bulk Complaint Level (BCL) を指定します (アクションは、指定された値以上ではなく、指定された値より大きい場合にトリガーされます)。</span><span class="sxs-lookup"><span data-stu-id="04373-171">**Bulk email threshold**: Specifies the bulk complaint level (BCL) of a message that triggers the specified action for the **Bulk** spam filtering verdict that you configure on the next page (greater than the specified value, not greater than or equal to).</span></span> <span data-ttu-id="04373-172">値が大きければ大きいほど、そのメッセージの信頼度は低い (迷惑メールである可能性が高い) ことを示します。</span><span class="sxs-lookup"><span data-stu-id="04373-172">A higher value indicates the message is less desirable (more likely to resemble spam).</span></span> <span data-ttu-id="04373-173">既定の値は 7 です。</span><span class="sxs-lookup"><span data-stu-id="04373-173">The default value is 7.</span></span> <span data-ttu-id="04373-174">詳細については、「[EOP の Bulk Complaint Level (BCL)](bulk-complaint-level-values.md)」および「[迷惑メールとバルク メールの違い](what-s-the-difference-between-junk-email-and-bulk-email.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04373-174">For more information, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

     <span data-ttu-id="04373-175">既定では、スパム対策ポリシーでの PowerShell のみの設定である _MarkAsSpamBulkMail_ は、`On` です。</span><span class="sxs-lookup"><span data-stu-id="04373-175">By default, the PowerShell only setting _MarkAsSpamBulkMail_ is `On` in anti-spam policies.</span></span> <span data-ttu-id="04373-176">この設定は、**一括** フィルター処理判定の結果に大きく影響します。</span><span class="sxs-lookup"><span data-stu-id="04373-176">This setting dramatically affects the results of a **Bulk** filtering verdict:</span></span>

     - <span data-ttu-id="04373-177">**_MarkAsSpamBulkMail_ が [On]**: しきい値よりも高い BCL は、フィルター判定「**スパム**」に相当する SCL 6 に変換され、**一括** フィルター処理判定に指定されたアクションがメッセージに対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="04373-177">**_MarkAsSpamBulkMail_ is On**: A BCL that's greater than the threshold is converted to an SCL 6 that corresponds to a filtering verdict of **Spam**, and the action for the **Bulk** filtering verdict is taken on the message.</span></span>
     - <span data-ttu-id="04373-178">**_MarkAsSpamBulkMail_ が [Off]**: メッセージには BCL がスタンプされますが、**一括** フィルター処理判定に対して _何のアクションも実行されません_。</span><span class="sxs-lookup"><span data-stu-id="04373-178">**_MarkAsSpamBulkMail_ is Off**: The message is stamped with the BCL, but _no action_ is taken for a **Bulk** filtering verdict.</span></span> <span data-ttu-id="04373-179">実際には、BCL しきい値と **一括** フィルター処理判定アクションは無関係です。</span><span class="sxs-lookup"><span data-stu-id="04373-179">In effect, the BCL threshold and **Bulk** filtering verdict action are irrelevant.</span></span>

   - <span data-ttu-id="04373-180">**スパム スコアを上げる**、**スパムとしてマーク**<sup>\*</sup>、**テスト モード**: 規定ではオフになっている高度なスパム フィルター (ASF) の設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="04373-180">**Increase spam score**, **Mark as spam**<sup>\*</sup> and **Test mode**: Contains the Advanced Spam Filter (ASF) settings that are turned off by default.</span></span> <span data-ttu-id="04373-181">ASF の設定は廃止の処理中です。この機能はフィルター処理スタックの別の部分に組み込まれます。</span><span class="sxs-lookup"><span data-stu-id="04373-181">ASF settings are in the process of being deprecated, and their functionality is being incorporated into other parts of the filtering stack.</span></span> <span data-ttu-id="04373-182">これらの ASF 設定はすべて、スパム対策ポリシーでオフにしておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="04373-182">We recommend that you leave all of these ASF settings turned off in your anti-spam policies.</span></span>

     <span data-ttu-id="04373-183">これらの設定の詳細については、「[EOP での高度なスパム フィルターの設定](advanced-spam-filtering-asf-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04373-183">For details about these settings, see [Advanced Spam Filter settings in EOP](advanced-spam-filtering-asf-options.md).</span></span>

      <span data-ttu-id="04373-184"><sup>\*</sup> **特定の言語を含む** と **これらの国から** は、ASF の設定に含まれません。</span><span class="sxs-lookup"><span data-stu-id="04373-184"><sup>\*</sup> **Contains specific languages** and **from these countries** are not part of ASF settings.</span></span>

   - <span data-ttu-id="04373-185">**特定の言語を含む**: ボックスをクリックして、ドロップダウン リストから **[オン]** または **[オフ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="04373-185">**Contains specific languages**: Click the box and select **On** or **Off** from the drop down list.</span></span> <span data-ttu-id="04373-186">オンにした場合は、ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="04373-186">If you turn it on, a box appears.</span></span> <span data-ttu-id="04373-187">ボックスで、言語の名前の入力を始めます。</span><span class="sxs-lookup"><span data-stu-id="04373-187">Start typing the name of a language in the box.</span></span> <span data-ttu-id="04373-188">サポートされている言語のフィルター処理されたリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="04373-188">A filtered list of supported languages will appear.</span></span> <span data-ttu-id="04373-189">探している言語が見つかったら、それを選択します。</span><span class="sxs-lookup"><span data-stu-id="04373-189">When you find the language that you're looking for, select it.</span></span> <span data-ttu-id="04373-190">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="04373-190">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="04373-191">既存の値を削除するには、値の横にある ![[アイコンの削除]](../../media/m365-cc-sc-remove-selection-icon.png) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04373-191">To remove an existing value, click remove ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to the value.</span></span>

   - <span data-ttu-id="04373-192">**これらの国から** _: ボックスをクリックして、ドロップダウン リストで *[オン]*\* または **[オフ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="04373-192">**From these countries** _: Click the box and select _ *On*\* or **Off** from the drop down list.</span></span> <span data-ttu-id="04373-193">オンにした場合は、ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="04373-193">If you turn it on, a box appears.</span></span> <span data-ttu-id="04373-194">ボックスで、国の名前の入力を始めます。</span><span class="sxs-lookup"><span data-stu-id="04373-194">Start typing the name of a country in the box.</span></span> <span data-ttu-id="04373-195">サポートされている国のフィルター処理されたリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="04373-195">A filtered list of supported countries will appear.</span></span> <span data-ttu-id="04373-196">探している国が見つかったら、それを選択します。</span><span class="sxs-lookup"><span data-stu-id="04373-196">When you find the country that you're looking for, select it.</span></span> <span data-ttu-id="04373-197">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="04373-197">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="04373-198">既存の値を削除するには、値の横にある ![[アイコンの削除]](../../media/m365-cc-sc-remove-selection-icon.png) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04373-198">To remove an existing value, click remove ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to the value.</span></span>

   <span data-ttu-id="04373-199">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04373-199">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="04373-200">**[アクション]** ページが表示されたら、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="04373-200">On the **Actions** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="04373-201">**メッセージ アクション**: 以下のスパム対策フィルター判定に基づき、メッセージに対して行うアクションを選択または確認します。</span><span class="sxs-lookup"><span data-stu-id="04373-201">**Message actions**: Select or review the action to take on messages based on the following spam filtering verdicts:</span></span>
     - <span data-ttu-id="04373-202">**スパム**</span><span class="sxs-lookup"><span data-stu-id="04373-202">**Spam**</span></span>
     - <span data-ttu-id="04373-203">**高確度迷惑メール**</span><span class="sxs-lookup"><span data-stu-id="04373-203">**High confidence spam**</span></span>
     - <span data-ttu-id="04373-204">**フィッシング**</span><span class="sxs-lookup"><span data-stu-id="04373-204">**Phishing**</span></span>
     - <span data-ttu-id="04373-205">**高確度のフィッシング**</span><span class="sxs-lookup"><span data-stu-id="04373-205">**High confidence phishing**</span></span>
     - <span data-ttu-id="04373-206">**バルク**</span><span class="sxs-lookup"><span data-stu-id="04373-206">**Bulk**</span></span>

     <span data-ttu-id="04373-207">次の表で、スパム対策フィルター判定に使用可能なアクションを説明します。</span><span class="sxs-lookup"><span data-stu-id="04373-207">The available actions for spam filtering verdicts are described in the following table.</span></span>

     - <span data-ttu-id="04373-208">チェック マーク (</span><span class="sxs-lookup"><span data-stu-id="04373-208">A check mark (</span></span> ![チェック マーク](../../media/checkmark.png)<span data-ttu-id="04373-210">) は、アクションが使用可能であることを示します (すべてのアクションがすべての判定に使用できるわけではありません)。</span><span class="sxs-lookup"><span data-stu-id="04373-210">) indicates the action is available (not all actions are available for all verdicts).</span></span>
     - <span data-ttu-id="04373-211">チェック マークの後にアスタリスク ( <sup>\*</sup> ) がある場合、スパム対策フィルター判定の既定のアクションであることを示しています。</span><span class="sxs-lookup"><span data-stu-id="04373-211">An asterisk ( <sup>\*</sup> ) after the check mark indicates the default action for the spam filtering verdict.</span></span>

     <br>

     ****

     |<span data-ttu-id="04373-212">アクション</span><span class="sxs-lookup"><span data-stu-id="04373-212">Action</span></span>|<span data-ttu-id="04373-213">スパム</span><span class="sxs-lookup"><span data-stu-id="04373-213">Spam</span></span>|<span data-ttu-id="04373-214">高</span><span class="sxs-lookup"><span data-stu-id="04373-214">High</span></span><br><span data-ttu-id="04373-215">信頼度</span><span class="sxs-lookup"><span data-stu-id="04373-215">confidence</span></span><br><span data-ttu-id="04373-216">スパム</span><span class="sxs-lookup"><span data-stu-id="04373-216">spam</span></span>|<span data-ttu-id="04373-217">フィッシング詐欺</span><span class="sxs-lookup"><span data-stu-id="04373-217">Phishing</span></span>|<span data-ttu-id="04373-218">高</span><span class="sxs-lookup"><span data-stu-id="04373-218">High</span></span><br><span data-ttu-id="04373-219">信頼度</span><span class="sxs-lookup"><span data-stu-id="04373-219">confidence</span></span><br><span data-ttu-id="04373-220">フィッシング詐欺</span><span class="sxs-lookup"><span data-stu-id="04373-220">phishing</span></span>|<span data-ttu-id="04373-221">バルク</span><span class="sxs-lookup"><span data-stu-id="04373-221">Bulk</span></span>|
     |---|:---:|:---:|:---:|:---:|:---:|
     |<span data-ttu-id="04373-222">**メッセージを迷惑メール フォルダーに移動する**: メッセージはメールボックスに配信され、[迷惑メール] フォルダーに移動されます。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="04373-222">**Move message to Junk Email folder**: The message is delivered to the mailbox and moved to the Junk Email folder.<sup>1</sup></span></span>|<span data-ttu-id="04373-223">![チェック マーク](../../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="04373-223">![Check mark](../../media/checkmark.png)<sup>\*</sup></span></span>|<span data-ttu-id="04373-224">![チェック マーク](../../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="04373-224">![Check mark](../../media/checkmark.png)<sup>\*</sup></span></span>|![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|<span data-ttu-id="04373-227">![チェック マーク](../../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="04373-227">![Check mark](../../media/checkmark.png)<sup>\*</sup></span></span>|
     |<span data-ttu-id="04373-228">**X-ヘッダーを追加する**: X-ヘッダーをメッセージ ヘッダーに追加し、そのメッセージをメールボックスに配信します。</span><span class="sxs-lookup"><span data-stu-id="04373-228">**Add X-header**: Adds an X-header to the message header and delivers the message to the mailbox.</span></span> <p> <span data-ttu-id="04373-229">後で **[この X ヘッダーのテキストを追加する]** ボックスに、X-ヘッダーのフィールド名 (値ではなく) を入力します。</span><span class="sxs-lookup"><span data-stu-id="04373-229">You enter the X-header field name (not the value) later in the **Add this X-header text** box.</span></span> <p> <span data-ttu-id="04373-230">**スパム** および **高確度迷惑メール** 判定の場合、メッセージは [迷惑メール] フォルダーに移動されます。<sup>1、2</sup></span><span class="sxs-lookup"><span data-stu-id="04373-230">For **Spam** and **High confidence spam** verdicts, the message is moved to the Junk Email folder.<sup>1,2</sup></span></span>|![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)||<span data-ttu-id="04373-234">![チェック マーク](../../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="04373-234">![Check mark](../../media/checkmark.png)<sup>\*</sup></span></span>|
     |<span data-ttu-id="04373-235">**件名行の先頭にテキストを追加する**: メッセージの件名行の先頭にテキストを追加します。</span><span class="sxs-lookup"><span data-stu-id="04373-235">**Prepend subject line with text**: Adds text to the beginning of the message's subject line.</span></span> <span data-ttu-id="04373-236">メッセージはメールボックスに配信され、[迷惑メール] フォルダーに移動されます。<sup>1、2</sup></span><span class="sxs-lookup"><span data-stu-id="04373-236">The message is delivered to the mailbox and moved to the Junk email folder.<sup>1,2</sup></span></span> <p> <span data-ttu-id="04373-237">テキストを後で **[件名行の先頭にこのテキストを追加する]** ボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="04373-237">You enter the text later in the **Prefix subject line with this text** box.</span></span>|![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)||![チェック マーク](../../media/checkmark.png)|
     |<span data-ttu-id="04373-242">**[メッセージをメール アドレスにリダイレクトする]:** メッセージを本来の受信者の代わりに他の受信者に送信します。</span><span class="sxs-lookup"><span data-stu-id="04373-242">**Redirect message to email address**: Sends the message to other recipients instead of the intended recipients.</span></span> <p> <span data-ttu-id="04373-243">後で、受信者を **[このメール アドレスにリダイレクトする]** ボックスに指定してください。</span><span class="sxs-lookup"><span data-stu-id="04373-243">You specify the recipients later in the **Redirect to this email address** box.</span></span>|![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|
     |<span data-ttu-id="04373-249">**[メッセージの削除]:** 添付ファイルすべてを含め、メッセージ全体が確認なしで削除されます。</span><span class="sxs-lookup"><span data-stu-id="04373-249">**Delete message**: Silently deletes the entire message, including all attachments.</span></span>|![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)||![チェック マーク](../../media/checkmark.png)|
     |<span data-ttu-id="04373-254">**[メッセージを隔離する]:** メッセージを本来の受信者に送信せず、検疫に送信します。</span><span class="sxs-lookup"><span data-stu-id="04373-254">**Quarantine message**: Sends the message to quarantine instead of the intended recipients.</span></span> <p> <span data-ttu-id="04373-255">後で、検疫でメッセージを保持する期間を **[検疫]** ボックスに指定します。</span><span class="sxs-lookup"><span data-stu-id="04373-255">You specify how long the message should be held in quarantine later in the **Quarantine** box.</span></span>|![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|<span data-ttu-id="04373-258">![チェック マーク](../../media/checkmark.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="04373-258">![Check mark](../../media/checkmark.png)<sup>\*</sup></span></span>|![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|
     |<span data-ttu-id="04373-261">**アクションなし**</span><span class="sxs-lookup"><span data-stu-id="04373-261">**No action**</span></span>|||||![チェック マーク](../../media/checkmark.png)|
     |

     > <span data-ttu-id="04373-263"><sup>1</sup> Exchange Online では、受信トレイで迷惑メール ルールが有効になっている場合、メッセージは [迷惑メール] フォルダーに移動されます (既定では有効)。</span><span class="sxs-lookup"><span data-stu-id="04373-263"><sup>1</sup> In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="04373-264">詳細については、「[Exchange Online のメールボックスの迷惑メール設定を構成する](configure-junk-email-settings-on-exo-mailboxes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04373-264">For more information, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>
     >
     > <span data-ttu-id="04373-265">EOP がオンプレミスの Exchange メールボックスを保護するハイブリット環境では、オンプレミスの Exchange のメール フロー ルール (トランスポート ルールとも言う) を構成して、迷惑メール ルールによりメッセージが [迷惑メール] フォルダーに移動できるように、EOP スパム対策フィルター判定を解釈する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04373-265">In hybrid environments where EOP protects on-premises Exchange mailboxes, you need to configure mail flow rules (also known as transport rules) in on-premises Exchange to translate the EOP spam filtering verdict so the junk email rule can move the message to the Junk Email folder.</span></span> <span data-ttu-id="04373-266">詳細については、「[迷惑メール フォルダーにスパムを配信するように EOP を構成する](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04373-266">For details, see [Configure EOP to deliver spam to the Junk Email folder in hybrid environments](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).</span></span>
     >
     > <span data-ttu-id="04373-267"><sup>2</sup> この値をメール フロー ルールの条件として、フィルターやルールに使用することができます。</span><span class="sxs-lookup"><span data-stu-id="04373-267"><sup>2</sup> You can this use value as a condition in mail flow rules to filter or route the message.</span></span>

   - <span data-ttu-id="04373-268">**スパムを指定した日数隔離しておく**: スパム対策フィルター判定のアクションとして **[メッセージを検疫]** を選択した場合に、メッセージを検疫に保持する期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="04373-268">**Retain spam in quarantine for this many days**: Specifies how long to keep the message in quarantine if you selected **Quarantine message** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="04373-269">期間が終了すると、メッセージは削除されます。</span><span class="sxs-lookup"><span data-stu-id="04373-269">After the time period expires, the message is deleted.</span></span> <span data-ttu-id="04373-270">既定値は 30 日です。</span><span class="sxs-lookup"><span data-stu-id="04373-270">The default value is 30 days.</span></span> <span data-ttu-id="04373-271">有効な値は 1 日から 30 日です。</span><span class="sxs-lookup"><span data-stu-id="04373-271">A valid value is from 1 to 30 days.</span></span> <span data-ttu-id="04373-272">検疫の詳細については、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="04373-272">For information about quarantine, see the following topics:</span></span>

     - [<span data-ttu-id="04373-273">EOP で隔離されたメッセージ</span><span class="sxs-lookup"><span data-stu-id="04373-273">Quarantined messages in EOP</span></span>](quarantine-email-messages.md)
     - [<span data-ttu-id="04373-274">EOP の管理者として検疫済みメッセージとファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="04373-274">Manage quarantined messages and files as an admin in EOP</span></span>](manage-quarantined-messages-and-files.md)
     - [<span data-ttu-id="04373-275">EOP のユーザーとして検疫済みメッセージを検索して解放する</span><span class="sxs-lookup"><span data-stu-id="04373-275">Find and release quarantined messages as a user in EOP</span></span>](find-and-release-quarantined-messages-as-a-user.md)

   - <span data-ttu-id="04373-276">**この X-ヘッダー テキストを追加する**: このボックスは、**[X-ヘッダーの追加]** を、スパム対策フィルター判定のアクションとして選択した場合にのみ必要で、選択可能になります。</span><span class="sxs-lookup"><span data-stu-id="04373-276">**Add this X-header text**: This box is required and available only if you selected **Add X-header** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="04373-277">指定する値は、メッセージ ヘッダーに追加されるヘッダー フィールドの *名前* です。</span><span class="sxs-lookup"><span data-stu-id="04373-277">The value you specify is the header field *name* that's added to the message header.</span></span> <span data-ttu-id="04373-278">ヘッダー フィールドの *値* は常に `This message appears to be spam` です。</span><span class="sxs-lookup"><span data-stu-id="04373-278">The header field *value* is always `This message appears to be spam`.</span></span>

     <span data-ttu-id="04373-279">最大の長さは 255 文字で、値にスペースやコロン (:) を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="04373-279">The maximum length is 255 characters, and the value can't contain spaces or colons (:).</span></span>

     <span data-ttu-id="04373-280">たとえば、値 `X-This-is-my-custom-header` を入力すると、メッセージに追加される X-ヘッダーは `X-This-is-my-custom-header: This message appears to be spam.` です。</span><span class="sxs-lookup"><span data-stu-id="04373-280">For example, if you enter the value `X-This-is-my-custom-header`, the X-header that's added to the message is `X-This-is-my-custom-header: This message appears to be spam.`</span></span>

     <span data-ttu-id="04373-281">スペースまたはコロン (:) を含む値を入力した場合、入力した値は無視され、既定の X-ヘッダー (`X-This-Is-Spam: This message appears to be spam.`) がメッセージに追加されます。</span><span class="sxs-lookup"><span data-stu-id="04373-281">If you enter a value that contains spaces or colons (:), the value you enter is ignored, and the default X-header is added to the message (`X-This-Is-Spam: This message appears to be spam.`).</span></span>

   - <span data-ttu-id="04373-282">**件名行の先頭にこのテキストを追加する**: このボックスは、**[件名行の先頭にテキストを追加する]** を、スパム対策フィルター判定のアクションとして選択した場合にのみ必要で、選択可能になります。</span><span class="sxs-lookup"><span data-stu-id="04373-282">**Prepend subject line with this text**: This box is required and available only if you selected **Prepend subject line with text** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="04373-283">メッセージの件名行の先頭に追加するテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="04373-283">Enter the text to add to the beginning of the message's subject line.</span></span>

   - <span data-ttu-id="04373-284">**このメール アドレスにリダイレクトする**: このボックスは、**[メール アドレスにリダイレクトする]** を、スパム対策フィルター判定のアクションとして選択した場合にのみ必要で、選択可能になります。</span><span class="sxs-lookup"><span data-stu-id="04373-284">**Redirect to this email address**: This box is required and available only if you selected the **Redirect message to email address** as the action for a spam filtering verdict.</span></span> <span data-ttu-id="04373-285">メッセージの配信先のメール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="04373-285">Enter the email address where you want to deliver the message.</span></span> <span data-ttu-id="04373-286">複数の値をセミコロン (;) で区切って入力できます。</span><span class="sxs-lookup"><span data-stu-id="04373-286">You can enter multiple values separated by semicolons (;).</span></span>

   - <span data-ttu-id="04373-287">**安全性のヒントを有効にする**: 既定で [安全性のヒント] は有効になっていますが、これらはチェックボックスをオフにすることで無効にできます。</span><span class="sxs-lookup"><span data-stu-id="04373-287">**Enable safety Tips**: By default, Safety Tips are enabled, but you can disable them by clearing the checkbox.</span></span> <span data-ttu-id="04373-288">安全性のヒントの詳細については、「[メール メッセージの安全性のヒント](safety-tips-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04373-288">For more information about Safety Tips, see [Safety tips in email messages](safety-tips-in-office-365.md).</span></span>

   - <span data-ttu-id="04373-289">**[ゼロアワー自動消去 (ZAP) を有効にする]**: Exchange Online のメールボックスに既に配信されたメッセージを ZAP が検出し、アクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="04373-289">**Enable zero-hour auto purge (ZAP)**: ZAP detects and takes action on messages that have already been delivered to Exchange Online mailboxes.</span></span> <span data-ttu-id="04373-290">詳細については、「[ゼロアワー自動消去 - スパムまたはマルウェアからの保護](zero-hour-auto-purge.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04373-290">For more information, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

     <span data-ttu-id="04373-291">既定では、ZAP はオンになっています。</span><span class="sxs-lookup"><span data-stu-id="04373-291">ZAP is turned on by default.</span></span> <span data-ttu-id="04373-292">ZAP をオンにすると、以下の設定が使用できます。</span><span class="sxs-lookup"><span data-stu-id="04373-292">When ZAP is turned on, the following settings are available:</span></span>

     - <span data-ttu-id="04373-293">**フィッシング メッセージに対して ZAP を有効にする**: 既定では、ZAP はフィッシング検出に対して有効になっていますが、チェックボックスをオフにすることで無効にできます。</span><span class="sxs-lookup"><span data-stu-id="04373-293">**Enable ZAP for phishing messages**: By default, ZAP is enabled for phishing detections, but you can disable it by clearing the checkbox.</span></span>
     - <span data-ttu-id="04373-294">**スパム メッセージに対して ZAP を有効にする**: 既定では、ZAP はスパム検出に対して有効になっていますが、チェックボックスをオフにすることで無効にできます。</span><span class="sxs-lookup"><span data-stu-id="04373-294">**Enable ZAP for spam messages**: By default, ZAP is enabled for spam detections, but you can disable it by clearing the checkbox.</span></span>

   - <span data-ttu-id="04373-295">**エンド ユーザーのスパム通知を有効にする**: 詳細については、このトピックで後述する「[エンド ユーザーのスパム通知を構成する](#configure-end-user-spam-notifications)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="04373-295">**Enable end-user spam notifications**: For more information, see the [Configure end-user spam notifications](#configure-end-user-spam-notifications) section later in this topic.</span></span>

   <span data-ttu-id="04373-296">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04373-296">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="04373-297">**[受信許可とブロック一覧]** ポップアップでは、スパム対策フィルター処理をスキップできるメッセージ送信者を、メール アドレスごと、またはメール ドメインごとに構成できます。</span><span class="sxs-lookup"><span data-stu-id="04373-297">On the **Allow & block list** flyout that appears, you are able to configure message senders by email address or email domain that are allowed to skip spam filtering.</span></span>

   <span data-ttu-id="04373-298">**[許可]** セクションでは、許可された送信者と許可されたドメインを構成できます。</span><span class="sxs-lookup"><span data-stu-id="04373-298">In the **Allowed** section, you can configure allowed senders and allowed domains.</span></span> <span data-ttu-id="04373-299">**[ブロック]** セクションでは、ブロックされた送信者とブロックされたドメインを追加できます。</span><span class="sxs-lookup"><span data-stu-id="04373-299">In the **Blocked** section, you can add blocked senders and blocked domains.</span></span>

   > [!IMPORTANT]
   >
   > <span data-ttu-id="04373-300">許可されたドメイン一覧にドメインを追加する前に慎重に検討してください。</span><span class="sxs-lookup"><span data-stu-id="04373-300">Think very carefully before you add domains to the allowed domains list.</span></span> <span data-ttu-id="04373-301">詳細については、「[EOP での信頼できる差出人リストの作成](create-safe-sender-lists-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04373-301">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md)</span></span>
   >
   > <span data-ttu-id="04373-302">[承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)や一般的なドメイン (microsoft.com や office.com など) は、決して、許可するドメインのリストに追加しないでください。</span><span class="sxs-lookup"><span data-stu-id="04373-302">Never add your own [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) or common domains (for example, microsoft.com or office.com) to the allowed domains list.</span></span> <span data-ttu-id="04373-303">これらのドメインがスパム対策フィルター処理を回避できた場合は、攻撃者がメールを簡単に組織内に送信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="04373-303">If these domains are allowed to bypass spam filtering, allow attackers an easily send email into your organization.</span></span>
   >
   > <span data-ttu-id="04373-304">ドメインをブロックされたドメイン一覧に追加して手動でドメインを受信拒否にすることは危険ではありませんが、管理作業の負荷が増大する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="04373-304">Manually blocking domains by adding the domains to the blocked domains list isn't dangerous, but it can increase your administrative workload.</span></span> <span data-ttu-id="04373-305">詳細については、「[EOP での受信拒否リストの作成](create-block-sender-lists-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04373-305">For more information, see [Create block sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>
   >
   > <span data-ttu-id="04373-306">メッセージがフィルターを通過してしまう場合や、フィルター処理判定に同意できない場合や、システムが処理に追いつくために時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="04373-306">There will be times when our filters will miss a message, you don't agree with the filtering verdict, or it takes time for our systems to catch up to it.</span></span> <span data-ttu-id="04373-307">このような場合には、現在のフィルター処理判定を上書きするために、許可リストとブロック リストを利用することができます。</span><span class="sxs-lookup"><span data-stu-id="04373-307">In these cases, the allow list and block list are available to override the current filtering verdicts.</span></span> <span data-ttu-id="04373-308">ただし、リストが管理不能なほどにならないよう、控えめで一時的なものにすることが必要です。また、フィルター処理スタックがその本来の処理を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04373-308">But, you should use these lists sparingly and temporarily: longs lists can become unmanageable, and our filtering stack should be doing what it's supposed to be doing.</span></span> <span data-ttu-id="04373-309">許可されたドメインをかなりの期間にわたって保持するような場合は、送信者のドメインが認証済みであることを確認するように送信者に伝える必要があります。認証済みでない場合は、DMARC 拒否に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04373-309">If you're going to keep an allowed domain for an extended period of time, you should tell the sender to verify that their domain is authenticated and set to DMARC reject if it's not.</span></span>

   <span data-ttu-id="04373-310">どのリストにもエントリを追加する手順は同じです。</span><span class="sxs-lookup"><span data-stu-id="04373-310">The steps to add entries to any of the lists are the same:</span></span>

   1. <span data-ttu-id="04373-311">構成する以下のリストのリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="04373-311">Click the link for the list that you want to configure:</span></span>
      - <span data-ttu-id="04373-312">**許可された** \> **送信者**: **[送信者の管理]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04373-312">**Allowed** \> **Senders**: Click **Manage (nn) sender(s)**.</span></span>
      - <span data-ttu-id="04373-313">**許可された** \> **ドメイン**: **[ドメインの許可]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04373-313">**Allowed** \> **Domains**: Click **Allow domains**.</span></span>
      - <span data-ttu-id="04373-314">**ブロックされた** \> **送信者**: **[送信者の管理]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04373-314">**Blocked** \> **Senders**: Click **Manage (nn) sender(s)**.</span></span>
      - <span data-ttu-id="04373-315">**ブロックされた** \> **ドメイン**: **[ドメインのブロック]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04373-315">**Blocked** \> **Domains**: Click **Block domains**.</span></span>

   2. <span data-ttu-id="04373-316">表示されるポップアップで、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="04373-316">In the flyout that appears, do the following steps:</span></span>
      1. <span data-ttu-id="04373-317">![[アイコンの作成]](../../media/m365-cc-sc-create-icon.png) をクリックして、**[送信者の追加]** または **[ドメインの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04373-317">Click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Add senders** or **Add domains**.</span></span>
      2. <span data-ttu-id="04373-318">表示された **[送信者の追加]** または **[ドメインの追加]** ポップアップで、**[送信者]** ボックスまたは **[ドメイン]** ボックスのドメインで送信者のメールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="04373-318">In the **Add senders** or **Add domains** flyout that appears, enter the sender's email address in the **Sender** box or the domain in the **Domain** box.</span></span> <span data-ttu-id="04373-319">入力している間、ボックスの下に値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="04373-319">As you're typing, the value appears below the box.</span></span> <span data-ttu-id="04373-320">メールアドレスやドメインの入力が終わった場合は、ボックスの下にある値を選択します。</span><span class="sxs-lookup"><span data-stu-id="04373-320">When you're finished typing the email address or domain, select the value below the box.</span></span>
      3. <span data-ttu-id="04373-321">必要な回数だけ前の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="04373-321">Repeat the previous step as many times as necessary.</span></span> <span data-ttu-id="04373-322">既存の値を削除するには、削除をクリックします</span><span class="sxs-lookup"><span data-stu-id="04373-322">To remove an existing value, click remove</span></span> ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="04373-324">値の隣。</span><span class="sxs-lookup"><span data-stu-id="04373-324">next to the value.</span></span>

      <span data-ttu-id="04373-325">完了したら、**[送信者の追加]** または **[ドメインの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04373-325">When you're finished, click **Add senders** or **Add domains**.</span></span>

      <span data-ttu-id="04373-326">メイン ポップアウトに戻ると、ページに追加した送信者やドメインが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="04373-326">Back on the main flyout, the senders or domains that you added are listed on the page.</span></span> <span data-ttu-id="04373-327">このページでエントリを削除するには、以下の手順で行います。</span><span class="sxs-lookup"><span data-stu-id="04373-327">To remove an entry from this page, do the following steps:</span></span>

      1. <span data-ttu-id="04373-328">1 つ以上のエントリをリストから選択します。</span><span class="sxs-lookup"><span data-stu-id="04373-328">Select one or more entries from the list.</span></span> <span data-ttu-id="04373-329">また、**検索** ボックスを使ってリスト内の値を検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="04373-329">You can also use the **Search** box to find values in the list.</span></span>
      2. <span data-ttu-id="04373-330">1 つ以上のエントリを選択した後、削除アイコン</span><span class="sxs-lookup"><span data-stu-id="04373-330">After you select at least one entry, the delete icon</span></span> ![[削除] アイコン](../../media/m365-cc-sc-delete-icon.png) <span data-ttu-id="04373-332">表示されます。</span><span class="sxs-lookup"><span data-stu-id="04373-332">appears.</span></span>
      3. <span data-ttu-id="04373-333">[削除] アイコンをクリックする</span><span class="sxs-lookup"><span data-stu-id="04373-333">Click the delete icon</span></span> ![[削除] アイコン](../../media/m365-cc-sc-delete-icon.png) <span data-ttu-id="04373-335">選択したエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="04373-335">to remove the selected entries.</span></span>

      <span data-ttu-id="04373-336">完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04373-336">When you're finished, click **Done**.</span></span>

      <span data-ttu-id="04373-337">**[許可 & ブロック リスト]** ページに戻り、続行する場合は **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04373-337">Back on the **Allow & block list** page, click **Next** when you're read to continue.</span></span>

8. <span data-ttu-id="04373-338">表示された **[レビュー]** ページで、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="04373-338">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="04373-339">各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="04373-339">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="04373-340">または、**[戻る]** をクリックするか、ウィザードで特定のページを選択します。</span><span class="sxs-lookup"><span data-stu-id="04373-340">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="04373-341">完了したら、**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04373-341">When you're finished, click **Create**.</span></span>

9. <span data-ttu-id="04373-342">表示された [確認]ページで、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04373-342">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-spam-policies"></a><span data-ttu-id="04373-343">Microsoft 365 Defender ポータルを使用して、スパム対策ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="04373-343">Use the Microsoft 365 Defender portal to view anti-spam policies</span></span>

1. <span data-ttu-id="04373-344">Microsoft 365 Defender ポータルで、**[メールと共同作業]**、\>**[ポリシーとルール]**、\>**[脅威ポリシー]**、\>**[ポリシー** セクション]\> **[スパム対策]**.の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="04373-344">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="04373-345">**[スパム対策ポリシー]** ページで、以下のいずれかの値を探します。</span><span class="sxs-lookup"><span data-stu-id="04373-345">On the **Anti-spam policies** page, look for one of the following values:</span></span>
   - <span data-ttu-id="04373-346">**[種類]** 値は **カスタムの迷惑メール対策ポリシー** です。</span><span class="sxs-lookup"><span data-stu-id="04373-346">The **Type** value is **Custom anti-spam policy**</span></span>
   - <span data-ttu-id="04373-347">**[名前]** 値は **迷惑メール受信対策ポリシー (既定)** です。</span><span class="sxs-lookup"><span data-stu-id="04373-347">The **Name** value is **Anti-spam inbound policy (Default)**</span></span>

   <span data-ttu-id="04373-348">迷惑メール対策ポリシーの一覧には、以下のプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="04373-348">The following properties are displayed in the list of anti-spam policies:</span></span>

   - <span data-ttu-id="04373-349">**名前**</span><span class="sxs-lookup"><span data-stu-id="04373-349">**Name**</span></span>
   - <span data-ttu-id="04373-350">**状態**</span><span class="sxs-lookup"><span data-stu-id="04373-350">**Status**</span></span>
   - <span data-ttu-id="04373-351">**優先度**</span><span class="sxs-lookup"><span data-stu-id="04373-351">**Priority**</span></span>
   - <span data-ttu-id="04373-352">**種類**</span><span class="sxs-lookup"><span data-stu-id="04373-352">**Type**</span></span>

3. <span data-ttu-id="04373-353">迷惑メール対策ポリシーの名前をクリックして選択すると、ポリシー設定がポップアウトで表示されます。</span><span class="sxs-lookup"><span data-stu-id="04373-353">When you select an anti-spam policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-spam-policies"></a><span data-ttu-id="04373-354">Microsoft 365 Defender ポータルを使用して、スパム対策ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="04373-354">Use the Microsoft 365 Defender portal to modify anti-spam policies</span></span>

1. <span data-ttu-id="04373-355">Microsoft 365 Defender ポータルで、**[メールと共同作業]**、\>**[ポリシーとルール]**、\>**[脅威ポリシー]**、\>**[ポリシー** セクション]\> **[スパム対策]**.の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="04373-355">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="04373-356">**[迷惑メール対策ポリシー]** ページで、リストから迷惑メール対策ポリシーの名前をクリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="04373-356">On the **Anti-spam policies** page, select an anti-spam policy from the list by clicking on the name:</span></span>
   - <span data-ttu-id="04373-357">ユーザーが作成したカスタム ポリシーの場合、**[種類]** 列の値が **[カスタム 迷惑メール対策ポリシー]** になっています。</span><span class="sxs-lookup"><span data-stu-id="04373-357">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>
   - <span data-ttu-id="04373-358">既定のポリシーには、**迷惑メール受信対策ポリシー (既定)** と名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="04373-358">The default policy named **Anti-spam inbound policy (Default)**.</span></span>

3. <span data-ttu-id="04373-359">表示されるポリシーの詳細ポップアップで、各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="04373-359">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="04373-360">設定の詳細については、この以前の記事の「[Microsoft 365 Defender ポータルを使用してスパム対策ポリシーを作成する](#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="04373-360">For more information about the settings, see the previous [Use the Microsoft 365 Defender portal to create anti-spam policies](#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) section in this article.</span></span>

   <span data-ttu-id="04373-361">既定の迷惑メール対策ポリシーの場合、**[適用先]** セクションは選択できず (ポリシーは全員に適用される)、ポリシーの名前を変更することもできません。</span><span class="sxs-lookup"><span data-stu-id="04373-361">For the default anti-spam policy, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="04373-362">ポリシーを有効または無効にするには、ポリシーの優先順位を設定するか、またはエンドユーザーの検疫通知を構成します。後続の各セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="04373-362">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-anti-spam-policies"></a><span data-ttu-id="04373-363">迷惑メール対策の有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="04373-363">Enable or disable anti-spam policies</span></span>

<span data-ttu-id="04373-364">既定の迷惑メール対策ポリシーを無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="04373-364">You can't disable the default anti-spam policy.</span></span>

1. <span data-ttu-id="04373-365">Microsoft 365 Defender ポータルで、**[メールと共同作業]**、\>**[ポリシーとルール]**、\>**[脅威ポリシー]**、\>**[ポリシー** セクション]\> **[スパム対策]**.の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="04373-365">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="04373-366">**[迷惑メール対策ポリシー]** ページで、リストから **[カスタム 迷惑メール対策ポリシー]** の **[種類] 値** の名前をクリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="04373-366">On the **Anti-spam policies** page, select a policy with the **Type value** of **Custom anti-spam policy** from the list by clicking on the name.</span></span>

3. <span data-ttu-id="04373-367">表示されるポリシーの詳細ポップアップの上部には、以下のいずれかの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="04373-367">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="04373-368">**ポリシー オフ**: ポリシーをオンにするには、![[アイコンをオンにする]](../../media/m365-cc-sc-turn-on-off-icon.png)、**[オンにする]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="04373-368">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="04373-369">**ポリシー オン**: ポリシーをオフにするには、![[アイコンをオフにする]](../../media/m365-cc-sc-turn-on-off-icon.png)、**[オフにする]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="04373-369">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="04373-370">確認ダイアログ ボックスが表示されたら、**[オンにする]** または **[オフにする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04373-370">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="04373-371">ポリシーの詳細ポップアップで **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04373-371">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="04373-372">ポリシーのメイン ページに戻ると、ポリシーの **[状態]** の値が **[オン]** または **[オフ]** になります。</span><span class="sxs-lookup"><span data-stu-id="04373-372">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-anti-spam-policies"></a><span data-ttu-id="04373-373">カスタム迷惑メール対策ポリシーの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="04373-373">Set the priority of custom anti-spam policies</span></span>

<span data-ttu-id="04373-p141">既定では、迷惑メール対策ポリシーには、ポリシーの作成順序に基づいた優先度が指定されます (新しいポリシーの優先度が古いポリシーよりも低くなります)。優先度番号が小さいほど、ポリシーの優先度が高くなることを意味し (0 が最高)、ポリシーは優先度順に処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも前に処理されます)。2 つのポリシーに同じ優先度を設定することはできず、ポリシー処理は最初のポリシーが適用されると停止します。</span><span class="sxs-lookup"><span data-stu-id="04373-p141">By default, anti-spam policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies). A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies). No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="04373-377">ポリシーの優先度を変更するには、ポリシーのプロパティで **[優先度を上げる]** または **[優先度を下げる]** をクリックします (Microsoft 365 Defender ポータルの **[優先度]** の数値を直接変更することはできません)。</span><span class="sxs-lookup"><span data-stu-id="04373-377">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="04373-378">ポリシーの優先度を変更することは、複数のポリシーを所有している場合にのみ意味があります。</span><span class="sxs-lookup"><span data-stu-id="04373-378">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="04373-379">**注意**:</span><span class="sxs-lookup"><span data-stu-id="04373-379">**Notes**:</span></span>

- <span data-ttu-id="04373-380">Microsoft 365 Defender ポータルでは、スパム対策ポリシーの作成後にその優先度のみを変更できます。</span><span class="sxs-lookup"><span data-stu-id="04373-380">In the Microsoft 365 Defender portal, you can only change the priority of the anti-spam policy after you create it.</span></span> <span data-ttu-id="04373-381">PowerShell では、スパム フィルター ルールの作成時に既定の優先度を上書きできます (この上書きが既存のルールの優先度に影響を与えることがあります)。</span><span class="sxs-lookup"><span data-stu-id="04373-381">In PowerShell, you can override the default priority when you create the spam filter rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="04373-382">迷惑メール対策ポリシーは、表示される順に処理されます (最初のポリシーの値は **優先度** が 0)。</span><span class="sxs-lookup"><span data-stu-id="04373-382">Anti-spam policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="04373-383">既定の迷惑メール対策ポリシーには値 **[Lowest]** が付いており、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="04373-383">The default anti-spam policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="04373-384">Microsoft 365 Defender ポータルで、**[メールと共同作業]**、\>**[ポリシーとルール]**、\>**[脅威ポリシー]**、\>**[ポリシー** セクション]\> **[スパム対策]**.の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="04373-384">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="04373-385">**[迷惑メール対策ポリシー]** ページで、リストから **[カスタム 迷惑メール対策ポリシー]** の **[種類] 値** の名前をクリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="04373-385">On the **Anti-spam policies** page, select a select a policy with the **Type value** of **Custom anti-spam policy** from the list by clicking on the name.</span></span>

3. <span data-ttu-id="04373-386">表示されるポリシーの詳細ポップアップの上部には、現在の優先度の値とカスタム ポリシーの数に基づいて、**[優先度を上げる]** または **[優先度を下げる]** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="04373-386">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="04373-387">**優先度** 値が **0** の迷惑メール対策ポリシーでは、**[優先度を下げる]** オプションのみ利用可能です。</span><span class="sxs-lookup"><span data-stu-id="04373-387">The anti-spam policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="04373-388">**優先度** 値が最低の (例: **3**) の迷惑メール対策ポリシーでは、**[優先度を下げる]** オプションのみ利用可能です。</span><span class="sxs-lookup"><span data-stu-id="04373-388">The anti-spam policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="04373-389">3 つ以上の迷惑メール対策ポリシーがある場合、優先度の値が最も高いポリシーと最も低いポリシーの間では、**[優先度を上げる]** と **[優先度を下げる]** の両方のオプションが利用可能です。</span><span class="sxs-lookup"><span data-stu-id="04373-389">If you have three or more anti-spam policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="04373-390">![[優先度を上げる] アイコン](../../media/m365-cc-sc-increase-icon.png)、**[優先度を上げる]** の順にクリックするか、または ![[優先度を下げる] アイコン](../../media/m365-cc-sc-decrease-icon.png)、**[優先度を下げる]** の順にクリックして、**優先度** 値を変更します。</span><span class="sxs-lookup"><span data-stu-id="04373-390">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="04373-391">完了したら、ポリシーの詳細ポップアップで **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04373-391">When you're finished, click **Close** in the policy details flyout.</span></span>

### <a name="configure-end-user-spam-notifications"></a><span data-ttu-id="04373-392">エンドユーザーの迷惑メール通知の構成</span><span class="sxs-lookup"><span data-stu-id="04373-392">Configure end-user spam notifications</span></span>

<span data-ttu-id="04373-393">スパム対策フィルター判定によりメッセージが検疫された場合に、受信者に送信されたメッセージに対する処理を知らせるために、エンドユーザーの迷惑メール通知を構成できます。</span><span class="sxs-lookup"><span data-stu-id="04373-393">When a spam filtering verdict quarantines a message, you can configure end-user spam notifications to let recipients know what happened to messages that were sent to them.</span></span> <span data-ttu-id="04373-394">これらの通知の詳細については、「[EOP でのエンドユーザーの迷惑メール通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04373-394">For more information about these notifications, see [End-user spam notifications in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="04373-395">Microsoft 365 Defender ポータルで、**[メールと共同作業]**、\>**[ポリシーとルール]**、\>**[脅威ポリシー]**、\>**[ポリシー** セクション]\> **[スパム対策]**.の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="04373-395">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="04373-396">**[迷惑メール対策ポリシー]** ページで、リストから迷惑メール対策ポリシーの名前をクリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="04373-396">On the **Anti-spam policies** page, select an anti-spam policy from the list by clicking on the name:</span></span>
   - <span data-ttu-id="04373-397">ユーザーが作成したカスタム ポリシーの場合、**[種類]** 列の値が **[カスタム 迷惑メール対策ポリシー]** になっています。</span><span class="sxs-lookup"><span data-stu-id="04373-397">A custom policy that you created where the value in the **Type** column is **Custom anti-spam policy**.</span></span>
   - <span data-ttu-id="04373-398">既定のポリシーには、**迷惑メール受信対策ポリシー (既定)** と名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="04373-398">The default policy named **Anti-spam inbound policy (Default)**.</span></span>

3. <span data-ttu-id="04373-399">表示されるポリシーの詳細ポップアップで、**[アクション]** セクションで **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04373-399">In the policy details flyout that appears, click **Edit** in the **Actions** section.</span></span> <span data-ttu-id="04373-400">**[アクション]** ポップアップが表示されたら、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="04373-400">In the **Actions** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="04373-401">**エンドユーザーのスパム通知を有効にする**: チェックボックスを選択して通知を有効にするか、チェックボックスをオフにして通知を無効にします。</span><span class="sxs-lookup"><span data-stu-id="04373-401">**Enable end-user spam notifications**: Select the checkbox to enable notifications or clear the checkbox to disable notifications.</span></span> <span data-ttu-id="04373-402">チェックボックスを選択すると、以下の追加設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="04373-402">When you select the checkbox, the following additional settings appear:</span></span>

     - <span data-ttu-id="04373-403">**エンドユーザーの迷惑メール通知の送信間隔 (日)**: 通知が送信される頻度を選択します。</span><span class="sxs-lookup"><span data-stu-id="04373-403">**Send end-user spam notifications every (days)**: Select how frequently notifications are sent.</span></span> <span data-ttu-id="04373-404">既定値は 3 日です。</span><span class="sxs-lookup"><span data-stu-id="04373-404">The default value is 3 days.</span></span> <span data-ttu-id="04373-405">1 日から 15 日まで入力できます。</span><span class="sxs-lookup"><span data-stu-id="04373-405">You can enter 1 to 15 days.</span></span>

       <span data-ttu-id="04373-406">エンドユーザーのスパム通知は、24時間以内に 3 サイクルあります。これは、次の時間に始まります: 01:00 UTC、08:00 UTC、および 16:00 UTC。</span><span class="sxs-lookup"><span data-stu-id="04373-406">There are 3 cycles of end-user spam notification within a 24 hour period that start at the following times: 01:00 UTC, 08:00 UTC, and 16:00 UTC.</span></span>

       > [!NOTE]
       > <span data-ttu-id="04373-407">前回のサイクルで通知を受信できなかった場合は、後続のサイクルが通知をプッシュします。</span><span class="sxs-lookup"><span data-stu-id="04373-407">If we missed a notification during a previous cycle, a subsequent cycle will push the notification.</span></span> <span data-ttu-id="04373-408">これにより、同じ日に複数の通知が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="04373-408">This might give the appearance of multiple notifications within the same day.</span></span>

     - <span data-ttu-id="04373-409">**言語**: ドロップダウンをクリックして、リストから使用可能な言語を選びます。</span><span class="sxs-lookup"><span data-stu-id="04373-409">**Language**: Click the drop down an select an available language from the list.</span></span> <span data-ttu-id="04373-410">既定値は、英語で、**Default** です。</span><span class="sxs-lookup"><span data-stu-id="04373-410">The default value is **Default**, which means English.</span></span>

   <span data-ttu-id="04373-411">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04373-411">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="04373-412">ポリシーの詳細ポップアップに戻り、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04373-412">Back on the policy details flyout, click **Close**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-spam-policies"></a><span data-ttu-id="04373-413">Microsoft 365 Defender ポータルを使用して、カスタムのスパム対策ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="04373-413">Use the Microsoft 365 Defender portal to remove custom anti-spam policies</span></span>

<span data-ttu-id="04373-414">Microsoft 365 Defender ポータルを使用してカスタムのスパム対策ポリシーを削除すると、スパム フィルター ルールと、それに対応するスパム フィルター ポリシーが両方とも削除されます。</span><span class="sxs-lookup"><span data-stu-id="04373-414">When you use the Microsoft 365 Defender portal to remove a custom anti-spam policy, the spam filter rule and the corresponding spam filter policy are both deleted.</span></span> <span data-ttu-id="04373-415">既定のスパム対策ポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="04373-415">You can't remove the default anti-spam policy.</span></span>

1. <span data-ttu-id="04373-416">Microsoft 365 Defender ポータルで、**[メールと共同作業]**、\>**[ポリシーとルール]**、\>**[脅威ポリシー]**、\>**[ポリシー** セクション]\> **[スパム対策]**.の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="04373-416">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="04373-417">**[迷惑メール対策ポリシー]** ページで、リストから **[カスタム 迷惑メール対策ポリシー]** の **[種類] 値** の名前をクリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="04373-417">On the **Anti-spam policies** page, select a policy with the **Type value** of **Custom anti-spam policy** from the list by clicking on the name.</span></span> <span data-ttu-id="04373-418">表示されるポリシーの詳細ポップアウトの上部で、![[その他の操作] アイコン](../../media/m365-cc-sc-more-actions-icon.png)、**[その他の操作]** \>、![[ポリシーの削除] アイコン](../../media/m365-cc-sc-delete-icon.png)、**[ポリシーの削除]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="04373-418">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="04373-419">確認ダイアログ ボックスが表示されたら、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04373-419">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies"></a><span data-ttu-id="04373-420">Exchange Online PowerShell または スタンドアロン EOP PowerShell を使用して迷惑メール対策ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="04373-420">Use Exchange Online PowerShell or standalone EOP PowerShell to configure anti-spam policies</span></span>

<span data-ttu-id="04373-421">前述したように、迷惑メール対策ポリシーは、スパム フィルター ポリシーとスパム フィルター ルールから構成されます。</span><span class="sxs-lookup"><span data-stu-id="04373-421">As previously described, an anti-spam policy consists of a spam filter policy and a spam filter rule.</span></span>

<span data-ttu-id="04373-422">Exchange Online PowerShell またはスタンドアロンの EOP PowerShell では、スパム フィルター ポリシーとスパム フィルター ルールの違いは明白です。</span><span class="sxs-lookup"><span data-stu-id="04373-422">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between spam filter policies and spam filter rules is apparent.</span></span> <span data-ttu-id="04373-423">スパム フィルター ポリシーは **\*-HostedContentFilterPolicy** コマンドレットを使用して管理し、スパム フィルター ルールは **\*-HostedContentFilterRule** コマンドレットを使用して管理します。</span><span class="sxs-lookup"><span data-stu-id="04373-423">You manage spam filter policies by using the **\*-HostedContentFilterPolicy** cmdlets, and you manage spam filter rules by using the **\*-HostedContentFilterRule** cmdlets.</span></span>

- <span data-ttu-id="04373-424">PowerShell では、最初にスパム フィルター ポリシーを作成し、それからルールが適用されるポリシーを特定するスパム フィルター ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="04373-424">In PowerShell, you create the spam filter policy first, then you create the spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="04373-425">PowerShell では、スパム フィルター ポリシーとスパム フィルター ルールの設定は別々に変更します。</span><span class="sxs-lookup"><span data-stu-id="04373-425">In PowerShell, you modify the settings in the spam filter policy and the spam filter rule separately.</span></span>
- <span data-ttu-id="04373-426">PowerShell からスパム フィルター ポリシーを削除しても、対応しているスパム フィルター ルールは自動で削除されず、逆もまた同様です。</span><span class="sxs-lookup"><span data-stu-id="04373-426">When you remove a spam filter policy from PowerShell, the corresponding spam filter rule isn't automatically removed, and vice versa.</span></span>

<span data-ttu-id="04373-427">次の迷惑メール対策ポリシー設定は、PowerShell でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="04373-427">The following anti-spam policy settings are only available in PowerShell:</span></span>

- <span data-ttu-id="04373-428">_MarkAsSpamBulkMail_ パラメーター (既定は `On`)。</span><span class="sxs-lookup"><span data-stu-id="04373-428">The _MarkAsSpamBulkMail_ parameter that's `On` by default.</span></span> <span data-ttu-id="04373-429">この設定の影響については、この記事で前述した「[Microsoft 365 Defender ポータルを使用してスパム対策ポリシーを作成する](#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies)」セクションで説明されています。</span><span class="sxs-lookup"><span data-stu-id="04373-429">The effects of this setting were explained in the [Use the Microsoft 365 Defender portal to create anti-spam policies](#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) section earlier in this article.</span></span>

- <span data-ttu-id="04373-430">次の設定は、エンドユーザーの迷惑メール検疫通知の設定です。</span><span class="sxs-lookup"><span data-stu-id="04373-430">The following settings for end-user spam quarantine notifications:</span></span>
  - <span data-ttu-id="04373-431">_DownloadLink_ パラメーター。これにより、Outlook の迷惑メール報告ツールへのリンクを表示または非表示にできます。</span><span class="sxs-lookup"><span data-stu-id="04373-431">The _DownloadLink_ parameter that shows or hides the link to the Junk Email Reporting Tool for Outlook.</span></span>
  - <span data-ttu-id="04373-432">_EndUserSpamNotificationCustomSubject_ パラメーター。これにより、通知の件名行をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="04373-432">The _EndUserSpamNotificationCustomSubject_ parameter that you can use to customize the subject line of the notification.</span></span>

### <a name="use-powershell-to-create-anti-spam-policies"></a><span data-ttu-id="04373-433">PowerShell を使用して迷惑メール対策ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="04373-433">Use PowerShell to create anti-spam policies</span></span>

<span data-ttu-id="04373-434">PowerShell では、2 段階の手順で迷惑メール対策ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="04373-434">Creating an anti-spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="04373-435">スパム フィルター ポリシーを作成する。</span><span class="sxs-lookup"><span data-stu-id="04373-435">Create the spam filter policy.</span></span>
2. <span data-ttu-id="04373-436">スパム フィルター ルールの適用先とするスパム フィルター ポリシーを指定するルールを作成する。</span><span class="sxs-lookup"><span data-stu-id="04373-436">Create the spam filter rule that specifies the spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="04373-437">**注**:</span><span class="sxs-lookup"><span data-stu-id="04373-437">**Notes**:</span></span>

- <span data-ttu-id="04373-438">新しいスパム フィルター ルールを作成して、既存の関連付けされていないスパム フィルター ポリシーをそれに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="04373-438">You can create a new spam filter rule and assign an existing, unassociated spam filter policy to it.</span></span> <span data-ttu-id="04373-439">1 つのスパム フィルター ルールを複数のスパム フィルター ポリシーに関連付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="04373-439">A spam filter rule can't be associated with more than one spam filter policy.</span></span>
- <span data-ttu-id="04373-440">ポリシーを作成するまで Microsoft 365 Defender ポータルで使用できない次の設定を、PowerShell で新しいスパム フィルター ポリシーに構成できます。</span><span class="sxs-lookup"><span data-stu-id="04373-440">You can configure the following settings on new spam filter policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
  - <span data-ttu-id="04373-441">新しいポリシーを無効化された状態で作成する (**New-HostedContentFilterRule** コマンドレットで _Enabled_`$false` を指定)。</span><span class="sxs-lookup"><span data-stu-id="04373-441">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedContentFilterRule** cmdlet).</span></span>
  - <span data-ttu-id="04373-442">作成時にポリシーの優先度を設定する (**New-HostedContentFilterRule** コマンドレットで _Priority_ _\<Number\>_ を指定)。</span><span class="sxs-lookup"><span data-stu-id="04373-442">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedContentFilterRule** cmdlet).</span></span>

- <span data-ttu-id="04373-443">ポリシーをスパム フィルター ルールに割り当てるまでは、PowerShell で作成した新しいスパム フィルター ポリシーを Microsoft 365 Defender ポータルに表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="04373-443">A new spam filter policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a><span data-ttu-id="04373-444">手順 1: PowerShell を使用してスパム フィルター ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="04373-444">Step 1: Use PowerShell to create a spam filter policy</span></span>

<span data-ttu-id="04373-445">スパム フィルター ポリシーを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="04373-445">To create a spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="04373-446">この例では、次のような設定で Contoso Executives という名前のスパム フィルター ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="04373-446">This example creates a spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="04373-447">スパム対策フィルター判定が「スパム」または「高確度スパム」の場合は、メッセージを検疫します。</span><span class="sxs-lookup"><span data-stu-id="04373-447">Quarantine messages when the spam filtering verdict is spam or high confidence spam.</span></span>
- <span data-ttu-id="04373-448">BCL 7、8、または 9 で、「バルク メール」スパム対策フィルター判定のアクションがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="04373-448">BCL 7, 8, or 9 triggers the action for a bulk email spam filtering verdict.</span></span>

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

<span data-ttu-id="04373-449">構文とパラメーターの詳細については、「[New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04373-449">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-spam-filter-rule"></a><span data-ttu-id="04373-450">手順 2: PowerShell を使用してスパム フィルター ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="04373-450">Step 2: Use PowerShell to create a spam filter rule</span></span>

<span data-ttu-id="04373-451">スパム フィルター ルールを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="04373-451">To create a spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedContentFilterRule -Name "<RuleName>" -HostedContentFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="04373-452">この例では、次に示す設定で Contoso Executives という新しいスパム フィルター ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="04373-452">This example creates a new spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="04373-453">Contoso Executives という名前のスパム フィルター ポリシーがルールに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="04373-453">The spam filter policy named Contoso Executives is associated with the rule.</span></span>
- <span data-ttu-id="04373-454">ルールは Contoso Executives Group という名前のグループのメンバーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="04373-454">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedContentFilterRule -Name "Contoso Executives" -HostedContentFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="04373-455">構文とパラメーターの詳細については、「[New-HostedContentFilterRule](/powershell/module/exchange/new-hostedcontentfilterrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04373-455">For detailed syntax and parameter information, see [New-HostedContentFilterRule](/powershell/module/exchange/new-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-view-spam-filter-policies"></a><span data-ttu-id="04373-456">PowerShell を使用してスパム フィルター ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="04373-456">Use PowerShell to view spam filter policies</span></span>

<span data-ttu-id="04373-457">すべてのスパム フィルター ポリシーの要約リストを返すには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="04373-457">To return a summary list of all spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedContentFilterPolicy
```

<span data-ttu-id="04373-458">特定のスパム フィルター ポリシーに関する詳細情報を返すには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="04373-458">To return detailed information about a specific spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedContentFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="04373-459">この例では、Executives というスパム フィルター ポリシーのすべてのプロパティの値を戻します。</span><span class="sxs-lookup"><span data-stu-id="04373-459">This example returns all the property values for the spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedContentFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="04373-460">構文とパラメーターの詳細については、「[Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04373-460">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-view-spam-filter-rules"></a><span data-ttu-id="04373-461">PowerShell を使用してスパム フィルター ルールを表示する</span><span class="sxs-lookup"><span data-stu-id="04373-461">Use PowerShell to view spam filter rules</span></span>

<span data-ttu-id="04373-462">既存のスパム フィルター ルールを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="04373-462">To view existing spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedContentFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="04373-463">すべてのスパム フィルター ルールの要約リストを返すには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="04373-463">To return a summary list of all spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedContentFilterRule
```

<span data-ttu-id="04373-464">ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="04373-464">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedContentFilterRule -State Disabled
```

```PowerShell
Get-HostedContentFilterRule -State Enabled
```

<span data-ttu-id="04373-465">特定のスパム フィルター ルールの詳細情報を返すには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="04373-465">To return detailed information about a specific spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedContentFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="04373-466">この例では、Contoso Executives というスパム フィルター ルールのすべてのプロパティの値を返します。</span><span class="sxs-lookup"><span data-stu-id="04373-466">This example returns all the property values for the spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedContentFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="04373-467">構文とパラメーターの詳細については、「[Get-HostedContentFilterRule](/powershell/module/exchange/get-hostedcontentfilterrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04373-467">For detailed syntax and parameter information, see [Get-HostedContentFilterRule](/powershell/module/exchange/get-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-modify-spam-filter-policies"></a><span data-ttu-id="04373-468">PowerShell を使用してスパム フィルター ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="04373-468">Use PowerShell to modify spam filter policies</span></span>

<span data-ttu-id="04373-469">以下の項目以外には、、PowerShell を使ってスパム フィルター ポリシーを変更する場合も、この記事で前述の「[手順 1: PowerShell を使用してスパム フィルター ポリシーを作成する](#step-1-use-powershell-to-create-a-spam-filter-policy)」で説明したポリシーを作成する場合と同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="04373-469">Other than the following items, the same settings are available when you modify a spam filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create a spam filter policy](#step-1-use-powershell-to-create-a-spam-filter-policy) section earlier in this article.</span></span>

- <span data-ttu-id="04373-470">特定のポリシーを既定のポリシー (全員に適用され、常に **Lowest** 優先度を持ち、削除することはできない) に切り替える _MakeDefault_ スイッチは、PowerShell でスパム フィルター ポリシーを変更するときにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="04373-470">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify a spam filter policy in PowerShell.</span></span>
- <span data-ttu-id="04373-471">スパム フィルター ポリシーの名前を変更することはできません (**Set-HostedContentFilterPolicy** コマンドレットには _Name_ パラメーターがありません)。</span><span class="sxs-lookup"><span data-stu-id="04373-471">You can't rename a spam filter policy (the **Set-HostedContentFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="04373-472">Microsoft 365 Defender ポータルでスパム対策ポリシーの名前を変更する場合は、スパム フィルター _ルール_ の名前を変更するだけになります。</span><span class="sxs-lookup"><span data-stu-id="04373-472">When you rename an anti-spam policy in the Microsoft 365 Defender portal, you're only renaming the spam filter _rule_.</span></span>

<span data-ttu-id="04373-473">スパム フィルター ポリシーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="04373-473">To modify a spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="04373-474">構文とパラメーターの詳細については、「[Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04373-474">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-spam-filter-rules"></a><span data-ttu-id="04373-475">PowerShell を使用してスパム フィルター ルールを変更する</span><span class="sxs-lookup"><span data-stu-id="04373-475">Use PowerShell to modify spam filter rules</span></span>

<span data-ttu-id="04373-476">PowerShell でスパム フィルター ルールを変更するときに使用できない唯一の設定は、無効なルールの作成を可能にする _Enabled_ パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="04373-476">The only setting that isn't available when you modify a spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="04373-477">既存のスパム フィルター ルールを有効または無効にするには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="04373-477">To enable or disable existing spam filter rules, see the next section.</span></span>

<span data-ttu-id="04373-478">それ以外は、PowerShell でスパム フィルター ルールを変更する際に利用可能な追加の設定はありません。</span><span class="sxs-lookup"><span data-stu-id="04373-478">Otherwise, no additional settings are available when you modify a spam filter rule in PowerShell.</span></span> <span data-ttu-id="04373-479">この記事で前述の「[手順 2: PowerShell を使用してスパム フィルター ルールを作成する](#step-2-use-powershell-to-create-a-spam-filter-rule)」セクションでルールを作成したときと同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="04373-479">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a spam filter rule](#step-2-use-powershell-to-create-a-spam-filter-rule) section earlier in this article.</span></span>

<span data-ttu-id="04373-480">スパム フィルター ルールを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="04373-480">To modify a spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="04373-481">この例では、`{Fabrikam Spam Filter}` と名前の付けられた既存のスパム フィルター ルールの名前を変更しています。</span><span class="sxs-lookup"><span data-stu-id="04373-481">This example renames the existing spam filter rule named `{Fabrikam Spam Filter}`.</span></span>

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

<span data-ttu-id="04373-482">構文とパラメーターの詳細については、「[Set-HostedContentFilterRule](/powershell/module/exchange/set-hostedcontentfilterrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04373-482">For detailed syntax and parameter information, see [Set-HostedContentFilterRule](/powershell/module/exchange/set-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-spam-filter-rules"></a><span data-ttu-id="04373-483">PowerShell を使ってスパム フィルター ルールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="04373-483">Use PowerShell to enable or disable spam filter rules</span></span>

<span data-ttu-id="04373-484">PowerShell でスパム フィルター ルールを有効または無効にすると、すべての迷惑メール対策ポリシー (スパム フィルター ルールおよび割り当てられているスパム フィルター ポリシー) が有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="04373-484">Enabling or disabling a spam filter rule in PowerShell enables or disables the whole anti-spam policy (the spam filter rule and the assigned spam filter policy).</span></span> <span data-ttu-id="04373-485">既定の迷惑メール対策ポリシーを有効または無効にすることはできません (常にすべての受信者に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="04373-485">You can't enable or disable the default anti-spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="04373-486">PowerShell でスパム フィルター ルールを有効または無効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="04373-486">To enable or disable a spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedContentFilterRule | Disable-HostedContentFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="04373-487">この例では、Marketing Department というスパム フィルター ルールを無効化します。</span><span class="sxs-lookup"><span data-stu-id="04373-487">This example disables the spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="04373-488">この例では、同じルールを有効化します。</span><span class="sxs-lookup"><span data-stu-id="04373-488">This example enables same rule.</span></span>

```PowerShell
Enable-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="04373-489">構文とパラメーターの詳細については、「[Enable-HostedContentFilterRule](/powershell/module/exchange/enable-hostedcontentfilterrule)」と「[Disable-HostedContentFilterRule](/powershell/module/exchange/disable-hostedcontentfilterrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04373-489">For detailed syntax and parameter information, see [Enable-HostedContentFilterRule](/powershell/module/exchange/enable-hostedcontentfilterrule) and [Disable-HostedContentFilterRule](/powershell/module/exchange/disable-hostedcontentfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-spam-filter-rules"></a><span data-ttu-id="04373-490">PowerShell を使用してスパム フィルター ルールの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="04373-490">Use PowerShell to set the priority of spam filter rules</span></span>

<span data-ttu-id="04373-p160">ルールに設定できる優先度の最高値値は 0 です。設定できる最低値はルールの数に依存します。たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。たとえば、カスタム ルールが五つある場合 (優先度 0 から 4) に、一つのルールの優先度を 2 に変更した場合、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。</span><span class="sxs-lookup"><span data-stu-id="04373-p160">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="04373-496">PowerShell でスパム フィルター ルールの優先度を設定するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="04373-496">To set the priority of a spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="04373-p161">この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。</span><span class="sxs-lookup"><span data-stu-id="04373-p161">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedContentFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="04373-499">**注**:</span><span class="sxs-lookup"><span data-stu-id="04373-499">**Notes**:</span></span>

- <span data-ttu-id="04373-500">新しく作成したルールの優先度を設定するには、_New-HostedContentFilterRule_ コマンドレットの **Priority** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="04373-500">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedContentFilterRule** cmdlet instead.</span></span>
- <span data-ttu-id="04373-501">既定のスパム フィルター ポリシーには、対応するスパム フィルター ルールがありません。また、常に、**Lowest** の優先度が設定されており、変更はできません。</span><span class="sxs-lookup"><span data-stu-id="04373-501">The default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-spam-filter-policies"></a><span data-ttu-id="04373-502">PowerShell を使用してスパム フィルター ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="04373-502">Use PowerShell to remove spam filter policies</span></span>

<span data-ttu-id="04373-503">PowerShell を使用してスパム フィルター ポリシーを削除しても、それに対応するスパム フィルター ルールは削除されません。</span><span class="sxs-lookup"><span data-stu-id="04373-503">When you use PowerShell to remove a spam filter policy, the corresponding spam filter rule isn't removed.</span></span>

<span data-ttu-id="04373-504">PowerShell でスパム フィルター ポリシーを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="04373-504">To remove a spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedContentFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="04373-505">この例では、Marketing Department というスパム フィルター ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="04373-505">This example removes the spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedContentFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="04373-506">構文とパラメーターの詳細については、「[Remove-HostedContentFilterPolicy](/powershell/module/exchange/remove-hostedcontentfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04373-506">For detailed syntax and parameter information, see [Remove-HostedContentFilterPolicy](/powershell/module/exchange/remove-hostedcontentfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-spam-filter-rules"></a><span data-ttu-id="04373-507">PowerShell を使用してスパム フィルター ルールを削除する</span><span class="sxs-lookup"><span data-stu-id="04373-507">Use PowerShell to remove spam filter rules</span></span>

<span data-ttu-id="04373-508">PowerShell を使用してスパム フィルター ルールを削除しても、それに対応するスパム フィルター ポリシーは削除されません。</span><span class="sxs-lookup"><span data-stu-id="04373-508">When you use PowerShell to remove a spam filter rule, the corresponding spam filter policy isn't removed.</span></span>

<span data-ttu-id="04373-509">PowerShell でスパム フィルター ルールを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="04373-509">To remove a spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedContentFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="04373-510">この例では、Marketing Department というスパム フィルター ルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="04373-510">This example removes the spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedContentFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="04373-511">構文とパラメーターの詳細については、「[Remove-HostedContentFilterRule](/powershell/module/exchange/remove-hostedcontentfilterrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04373-511">For detailed syntax and parameter information, see [Remove-HostedContentFilterRule](/powershell/module/exchange/remove-hostedcontentfilterrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="04373-512">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="04373-512">How do you know these procedures worked?</span></span>

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a><span data-ttu-id="04373-513">GTUBE メッセージを送信して迷惑メール対策ポリシーの設定をテストする</span><span class="sxs-lookup"><span data-stu-id="04373-513">Send a GTUBE message to test your spam policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="04373-p162">これらの手順は、GTUBE メッセージを送信している電子メール組織が、送信スパムをスキャンしない場合にのみ機能します。送信スパムをスキャンしている場合には、テスト メッセージを送信できません。</span><span class="sxs-lookup"><span data-stu-id="04373-p162">These steps will only work if the email organization that you're sending the GTUBE message from doesn't scan for outbound spam. If it does, you can't send the test message.</span></span>

<span data-ttu-id="04373-516">Generic Test for Unsolicited Bulk Email (GTUBE) は、テスト メッセージに組み込んで組織のスパム対策設定を検証するための文字列です。</span><span class="sxs-lookup"><span data-stu-id="04373-516">Generic Test for Unsolicited Bulk Email (GTUBE) is a text string that you include in a test message to verify your organization's anti-spam settings.</span></span> <span data-ttu-id="04373-517">GTUBE メッセージは、マルウェア設定をテストするための European Institute for Computer Antivirus Research (EICAR) テキスト ファイルと似ています。</span><span class="sxs-lookup"><span data-stu-id="04373-517">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

<span data-ttu-id="04373-518">次の GTUBE テキストを、スペースや改行なしで 1 行で電子メール メッセージに入れます。</span><span class="sxs-lookup"><span data-stu-id="04373-518">Include the following GTUBE text in an email message on a single line, without any spaces or line breaks:</span></span>

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```
