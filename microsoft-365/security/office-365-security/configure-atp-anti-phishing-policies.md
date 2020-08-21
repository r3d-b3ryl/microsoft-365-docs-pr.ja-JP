---
title: ATP フィッシング詐欺対策ポリシーを設定する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理者は、Office 365 Advanced Threat Protection (Office 365 ATP) を使用して組織で使用可能な高度なフィッシング対策ポリシーを作成、変更、削除する方法について説明します。
ms.openlocfilehash: f7770945e6b99a3d2f3fa2b12daa13b2cc3c2612
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825739"
---
# <a name="configure-atp-anti-phishing-policies"></a><span data-ttu-id="ca25c-103">ATP フィッシング詐欺対策ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="ca25c-103">Configure ATP anti-phishing policies</span></span>

<span data-ttu-id="ca25c-104">ATP フィッシング対策ポリシーは [、365 Advanced Threat Protection Officeの一部です](office-365-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-104">ATP anti-phishing policies are part of [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="ca25c-105">ATP フィッシング対策ポリシーは、悪意のある偽装ベースのフィッシング攻撃やその他の種類のフィッシング攻撃から組織を保護することができます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-105">ATP anti-phishing policies can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="ca25c-106">Exchange Online Protection (EOP) と ATP フィッシング対策ポリシーの違いの詳細については、「フィッシング対策 [保護」を参照してください](anti-phishing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-106">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and ATP anti-phishing policies, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="ca25c-107">管理者は、既定の ATP フィッシング対策ポリシーを表示、編集、構成できます (削除することはできません)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-107">Admins can view, edit, and configure (but not delete) the default ATP anti-phishing policy.</span></span> <span data-ttu-id="ca25c-108">よりきめ細かく計画する場合は、組織内の特定のユーザー、グループ、またはドメインに適用される、カスタム ATP フィッシング対策ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-108">For greater granularity, you can also create custom ATP anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="ca25c-109">カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (実行順序) を変更できます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-109">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="ca25c-110">ATP のフィッシング対策ポリシーは、セキュリティ コンプライアンス & Exchange Online PowerShell で構成できます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-110">You can configure ATP anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="ca25c-111">Exchange Online Protection 組織で使用可能なフィッシング対策ポリシーの構成 (つまり、Office 365 ATP を使用しない Microsoft 365 組織) の詳細については、「EOP でフィッシング対策 [ポリシーを構成する」を参照してください](configure-anti-phishing-policies-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-111">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, Microsoft 365 organizations without Office 365 ATP), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

## <a name="atp-anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="ca25c-112">セキュリティ センターと PowerShell の ATP & フィッシング対策ポリシー</span><span class="sxs-lookup"><span data-stu-id="ca25c-112">ATP anti-phishing policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="ca25c-113">ATP フィッシング対策ポリシーの基本的な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ca25c-113">The basic elements of an ATP anti-phishing policy are:</span></span>

- <span data-ttu-id="ca25c-114">**フィッシング対策ポリシー**: 有効化/無効化するフィッシング対策と、オプションを適用するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-114">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="ca25c-115">**フィッシング対策ルール**: フィッシング対策ポリシーの優先順位と受信者フィルター (ポリシーが適用される対象者) を指定します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-115">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="ca25c-116">これら 2 つの要素の違いは、セキュリティ/コンプライアンス センターで ATP のフィッシング対策ポリシーを管理する際には分 &いません。</span><span class="sxs-lookup"><span data-stu-id="ca25c-116">The difference between these two elements isn't obvious when you manage ATP anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="ca25c-117">ポリシーを作成する場合、実際にはフィッシング対策ルールと、関連するフィッシング対策ポリシーの両方に同じ名前を使用して同時に作成します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-117">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="ca25c-118">ポリシーを変更すると、名前、優先順位、有効/無効、および受信者フィルターに関連する設定はフィッシング対策ルールを変更します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-118">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="ca25c-119">その他のすべての設定は、関連付けられているフィッシング対策ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-119">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="ca25c-120">ポリシーを削除すると、フィッシング対策ルールと、関連付けられているフィッシング対策ポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-120">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="ca25c-121">Exchange Online PowerShell では、ポリシーとルールを個別に管理します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-121">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="ca25c-122">詳細については、このトピックで後述する [「Exchange Online PowerShell を使用して ATP フ](#use-exchange-online-powershell-to-configure-atp-anti-phishing-policies) ィッシング対策ポリシー」セクションを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca25c-122">For more information, see the [Use Exchange Online PowerShell to configure ATP anti-phishing policies](#use-exchange-online-powershell-to-configure-atp-anti-phishing-policies) section later in this topic.</span></span>

<span data-ttu-id="ca25c-123">Office 365 ATP の組織には、Office365 AntiPhish Default という名前の組み込みの ATP フィッシング対策ポリシーがあります。このポリシーには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="ca25c-123">Every Office 365 ATP organization has a built-in ATP anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="ca25c-124">ポリシーと関連付けられているフィッシング対策ルール (受信者フィルター) がない場合でも、ポリシーは組織内のすべての受信者に適用されます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-124">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="ca25c-125">ポリシーにはカスタムの優先順位の値 **Lowest** が設定されており、変更することはできません (このポリシーは常に最後に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-125">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="ca25c-126">作成するどのカスタム ポリシーも、より高い優先順位を持ちます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-126">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="ca25c-127">ポリシーは既定のポリシー (**IsDefault** のプロパティが `True` の値になっている) であり、既定のポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="ca25c-127">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="ca25c-128">フィッシング対策保護の効果を高むには、特定のユーザーまたはユーザー グループに適用される、高い設定を持つカスタム ATP フィッシング対策ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-128">To increase the effectiveness of anti-phishing protection, you can create custom ATP anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ca25c-129">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="ca25c-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ca25c-130"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-130">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="ca25c-131">ATP フィッシ **ング対策ページに直接移動するには** 、次の手順を使用します <https://protection.office.com/antiphishing> 。</span><span class="sxs-lookup"><span data-stu-id="ca25c-131">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="ca25c-132">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca25c-132">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="ca25c-133">このトピックの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca25c-133">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="ca25c-134">ATP フィッシング対策ポリシーを追加、変更、および削除するには、次の役割グループのいずれかのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca25c-134">To add, modify, and delete ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="ca25c-135">**組織の管理**または[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ管理者**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-135">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="ca25c-136">**組織の管理**または [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**検疫管理**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-136">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="ca25c-137">ATP フィッシング対策ポリシーに読み取り専用アクセスするには、次の役割グループのいずれかのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca25c-137">For read-only access to ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="ca25c-138">[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ閲覧者**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-138">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="ca25c-139">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**表示限定の組織管理**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-139">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="ca25c-140">ATP フィッシング対策ポリシーに推奨される設定については [、「ATP フィッシング対策Officeのポリシー設定」を参照してください](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-140">For our recommended settings for ATP anti-phishing policies, see [Office ATP anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="ca25c-141">新しいポリシーまたは更新されたポリシーの適用を最大 30 分間許可します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-141">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="ca25c-142">フィルター パイプライン内でのフィッシング対策ポリシーの適用場所については、「 [メール保護の順序と優先順位」を参照してください](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-142">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-atp-anti-phishing-policies"></a><span data-ttu-id="ca25c-143">セキュリティ コンプライアンス センターを&、ATP フィッシング対策ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="ca25c-143">Use the Security & Compliance Center to create ATP anti-phishing policies</span></span>

<span data-ttu-id="ca25c-144">セキュリティ & コンプライアンス センターでカスタム ATP フィッシング対策ポリシーを作成すると、フィッシング対策ルールと関連するフィッシング対策ポリシーが両方に対して同じ名前を使用して同時に作成されます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-144">Creating a custom ATP anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="ca25c-145">ATP フィッシング対策ポリシーを作成する場合、ポリシーの名前、説明、ポリシーが適用されるユーザーを識別する受信者フィルターのみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-145">When you create an ATP anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="ca25c-146">ポリシーを作成した後は、ポリシーを変更して既定のフィッシング対策設定を変更または確認できます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-146">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="ca25c-147">コンプライアンス センターから&で、 **脅威管理** \> **ポリシー** \> **の ATP フィッシング対策に移動します**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-147">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="ca25c-148">[フ **ィッシング対策] ページで、[作成** ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-148">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="ca25c-149">新 **しいフィッシング対策ポリシーの作成ウィザード** が開きます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-149">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="ca25c-150">[ポリシー **に名前を付けた** らす] ページで、以下の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-150">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="ca25c-151">**[名前]**: わかりやすい一意のポリシー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-151">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="ca25c-152">**[説明]**: ポリシーについての説明を入力します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-152">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="ca25c-153">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca25c-153">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="ca25c-154">表示される **ページに** [適用] ページで、ポリシーが適用される内部の受信者を識別します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-154">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="ca25c-155">各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-155">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="ca25c-156">同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-156">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="ca25c-157">a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-157">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="ca25c-158">[条件 **の追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-158">Click **Add a condition**.</span></span> <span data-ttu-id="ca25c-159">表示されるドロップダウンで、[適用する条件: **Applied if**</span><span class="sxs-lookup"><span data-stu-id="ca25c-159">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="ca25c-160">**受信者は次の場所**に、組織内の 1 つ以上のメールボックス、メール ユーザー、またはメール連絡先を指定します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-160">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="ca25c-161">**受信者が次のメンバーの場合**: 組織内の 1 つまたは複数のグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-161">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="ca25c-162">**受信者のドメインが**、組織内で構成されている承認済みドメインの 1 つ以上に含まれます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-162">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="ca25c-163">条件を選択すると、これらのボックスが見つかり、対応する **ドロップダウンが表示** されます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-163">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="ca25c-164">ボックス内をクリックし、選択する値のリストをスクロールします。</span><span class="sxs-lookup"><span data-stu-id="ca25c-164">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="ca25c-165">ボックスをクリックし、入力してリストをフィルター処理し、値を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-165">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="ca25c-166">値を追加するには、ボックス内の空の領域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca25c-166">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="ca25c-167">個々のエントリを削除するには、値 \*\*の [削除\*\* ![ ] ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca25c-167">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="ca25c-168">条件全体を削除するには、条件の [ **削除** ![ ] ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca25c-168">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="ca25c-169">条件をさらに追加するには、条件を **追加し、[適用する場合** は残りの値 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-169">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="ca25c-170">例外を追加するには、[条件を **追加] をクリックし、[** 次の場合を除く] の下 **で例外を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-170">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="ca25c-171">設定と動作は、条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="ca25c-171">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="ca25c-172">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca25c-172">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="ca25c-173">表示される **設定の確認** ページで設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-173">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="ca25c-174">各設定で [ **編集** ] をクリックすると、変更できます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-174">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="ca25c-175">完了したら、[このポリシーの作成] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-175">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="ca25c-176">表示された確認ダイアログで **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca25c-176">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="ca25c-177">これらの一般的なポリシー設定で ATP フィッシング対策ポリシーを作成した後、次のセクションの手順を使用して、ポリシーの保護設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-177">After you create the ATP anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-atp-anti-phishing-policies"></a><span data-ttu-id="ca25c-178">セキュリティ センター ポリシーを&、ATP フィッシング対策ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="ca25c-178">Use the Security & Compliance Center to modify ATP anti-phishing policies</span></span>

<span data-ttu-id="ca25c-179">作成した新しいポリシー、または既にカスタマイズした既存のポリシーの ATP フィッシング対策ポリシーを変更するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-179">Use the following procedures to modify ATP anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="ca25c-180">セキュリティ センターを開いていない場合は、セキュリティ コンプライアンス センターを開&、 **脅威管理** \> **ポリシー** \> **ATP フィッシング対策に移動します**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-180">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="ca25c-181">変更するカスタム ATP フィッシング対策ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-181">Select the custom ATP anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="ca25c-182">既に選択されている場合は、選択を解除してもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-182">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="ca25c-183">[**ポリシーの編集 \<name\> ]** ポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-183">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="ca25c-184">いずれかの **セクション** で [編集] をクリックすると、そのセクションの設定にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-184">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="ca25c-185">次の手順は、セクションが表示される順番で示されますが、順番に説明しません (セクションは任意の順序で選択および変更できます)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-185">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="ca25c-186">セクションで [**編集]** をクリックすると、使用できる設定がウィザード形式で表示されますが、任意の順序でページ内に移動できます。任意のページで**Save**[保存] または [**Close**閉じる] をクリックすると、[**ポリシー**の編集] ページに ![ 戻 ](../../media/scc-remove-icon.png) \*\*ることができます \<name\> \*\*(保存したり、そのまま中に行う必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-186">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="ca25c-187">**ポリシー設定**: 前 **のセクション** でポリシーを作成した際に使用できていたのと同 [じ設定を変更するには](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) 、[編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca25c-187">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="ca25c-188">**名前**</span><span class="sxs-lookup"><span data-stu-id="ca25c-188">**Name**</span></span>
   - <span data-ttu-id="ca25c-189">**説明**</span><span class="sxs-lookup"><span data-stu-id="ca25c-189">**Description**</span></span>
   - <span data-ttu-id="ca25c-190">**適用先**</span><span class="sxs-lookup"><span data-stu-id="ca25c-190">**Applied to**</span></span>
   - <span data-ttu-id="ca25c-191">**設定の確認**</span><span class="sxs-lookup"><span data-stu-id="ca25c-191">**Review your settings**</span></span>

   <span data-ttu-id="ca25c-192">完了したら、[任意のページで保存 **]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca25c-192">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="ca25c-193">**偽装:**[ **編集] をクリック** して、ポリシー内の保護対象の送信者と保護ドメインを変更します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-193">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="ca25c-194">これらの設定は、スプーフィングされた送信者が受信メッセージの差出人アドレスで検索対象 (個別またはドメイン単位) を識別するポリシーの条件です。</span><span class="sxs-lookup"><span data-stu-id="ca25c-194">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="ca25c-195">詳細については [、ATP フィッシング対策ポリシーの偽装設定に関する記事を参照してください](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-195">For more information, see [Impersonation settings in ATP anti-phishing policies](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="ca25c-196">**保護するユーザーを追加**します: 既定値は **Off です**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-196">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="ca25c-197">オンにするには、トグルを **オン**にスライドして、表示される **[Add user]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca25c-197">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="ca25c-198">表示される **[ユーザーを追加** ] ポップアップで、次の値を構成します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-198">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="ca25c-199">**Email address**:</span><span class="sxs-lookup"><span data-stu-id="ca25c-199">**Email address**:</span></span>

        - <span data-ttu-id="ca25c-200">ボックス内をクリックし、選択するユーザーの一覧をスクロールします。</span><span class="sxs-lookup"><span data-stu-id="ca25c-200">Click in the box and scroll through the list of users to select.</span></span>
        - <span data-ttu-id="ca25c-201">ボックスをクリックし、入力してリストをフィルター処理し、ユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-201">Click in the box and start typing to filter the list and select a user.</span></span>
        - <span data-ttu-id="ca25c-202">エントリを削除するには、ユーザーの \*\*[削除\*\* ![ ] ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca25c-202">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="ca25c-203">**Name:** この値は選択したメール アドレスに基づいて設定されますが、変更できます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-203">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="ca25c-204">完了したら、[任意のページで保存 **]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca25c-204">When you're finished, click **Save** on any page.</span></span>

    <span data-ttu-id="ca25c-205">既存のエントリを編集するには、一覧で保護されたユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-205">To edit an existing entry, select the protected user in the list.</span></span>

   - <span data-ttu-id="ca25c-206">**保護するドメインを追加**します。次の設定の一方または両方を構成します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-206">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="ca25c-207">**自動的に自分のドメインを含**め: 既定値は **Off です**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-207">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="ca25c-208">オンにするには、トグルを On に切り替 **えなをスライドします**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-208">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="ca25c-209">**カスタム ドメインを含**む: 既定値は **Off です**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-209">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="ca25c-210">トグルをオンにスライドして **オンに**し、[ドメインの追加 **] ボックス** にドメイン名 (例: contoso.com) を入力し、Enter キーを押して必要に応じて繰り返します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-210">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="ca25c-211">**操作**: [編集] **をクリックします**</span><span class="sxs-lookup"><span data-stu-id="ca25c-211">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="ca25c-212">**偽装されたユーザーによって電子メールが送信されている場合**: 偽装された送信者が保護対象のユーザーを追加する場合に指定した保護されたユーザーの 1 人であるメッセージに対して、 **次のいずれかの操作を構成します**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-212">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="ca25c-213">**アクションを適用しない**</span><span class="sxs-lookup"><span data-stu-id="ca25c-213">**Don't apply any action**</span></span>
       - <span data-ttu-id="ca25c-214">**他の電子メール アドレスへのメッセージのリダイレクト**</span><span class="sxs-lookup"><span data-stu-id="ca25c-214">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="ca25c-215">**迷惑メール フォルダーにメッセージを移動する**</span><span class="sxs-lookup"><span data-stu-id="ca25c-215">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="ca25c-216">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="ca25c-216">**Quarantine the message**</span></span>
       - <span data-ttu-id="ca25c-217">**メッセージを配信して、他のアドレスを BCC 行に追加する**</span><span class="sxs-lookup"><span data-stu-id="ca25c-217">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="ca25c-218">**配信される前にメッセージを削除する**</span><span class="sxs-lookup"><span data-stu-id="ca25c-218">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="ca25c-219">**偽装ドメインによってメールが送信されている場合**: 保護対象のドメインに指定した保護されたドメインのいずれかに、スプーフィングされた送信者が、次のいずれかの **アクションを実行します**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-219">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

     - <span data-ttu-id="ca25c-220">**アクションを適用しない**</span><span class="sxs-lookup"><span data-stu-id="ca25c-220">**Don't apply any action**</span></span>
     - <span data-ttu-id="ca25c-221">**他の電子メール アドレスへのメッセージのリダイレクト**</span><span class="sxs-lookup"><span data-stu-id="ca25c-221">**Redirect message to other email addresses**</span></span>
     - <span data-ttu-id="ca25c-222">**迷惑メール フォルダーにメッセージを移動する**</span><span class="sxs-lookup"><span data-stu-id="ca25c-222">**Move message to Junk Email folder**</span></span>
     - <span data-ttu-id="ca25c-223">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="ca25c-223">**Quarantine the message**</span></span>
     - <span data-ttu-id="ca25c-224">**メッセージを配信して、他のアドレスを BCC 行に追加する**</span><span class="sxs-lookup"><span data-stu-id="ca25c-224">**Deliver the message and add other addresses to the Bcc line**</span></span>
     - <span data-ttu-id="ca25c-225">**配信される前にメッセージを削除する**</span><span class="sxs-lookup"><span data-stu-id="ca25c-225">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="ca25c-226">偽 **装の安全のヒントを有効にし、** 次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-226">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="ca25c-227">**偽装ユーザーのヒントを表示します**。既定値は **"オフ**" です。</span><span class="sxs-lookup"><span data-stu-id="ca25c-227">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="ca25c-228">オンにするには、トグルを On に切り替 **えなをスライドします**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-228">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="ca25c-229">**偽装ドメインのヒントを表示**: 既定値は **"オフ**" です。</span><span class="sxs-lookup"><span data-stu-id="ca25c-229">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="ca25c-230">オンにするには、トグルを On に切り替 **えなをスライドします**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-230">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="ca25c-231">**通常使いない文字のヒントを**表示: 既定値は **Off です**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-231">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="ca25c-232">オンにするには、トグルを On に切り替 **えなをスライドします**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-232">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="ca25c-233">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca25c-233">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="ca25c-234">**メールボックス インテリジェンス**:</span><span class="sxs-lookup"><span data-stu-id="ca25c-234">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="ca25c-235">**メールボックスのインテリジェンスを有効にしますか?:** 既定値は **On**です。</span><span class="sxs-lookup"><span data-stu-id="ca25c-235">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="ca25c-236">オンにするには、トグルをオフに切り替 **えます**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-236">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="ca25c-237">**メールボックス インテリジェンス ベース偽装保護を有効にしますか?:** この設定は、メールボックス インテリジェンス **を有効にする場合にのみ使用できますか?** **オン**はオン</span><span class="sxs-lookup"><span data-stu-id="ca25c-237">**Enable mailbox intelligence based impersonation protection?**: This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="ca25c-238">偽 **装されたユーザーによって電子メールが送信された場合は、** 次のいずれかのアクションを、メールボックス インテリジェンス障害 (保護されたユーザーや保護されたドメインに対して実行可能なアクションと同じ操作) に対して実行する処理を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-238">In **If email is sent by an impersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="ca25c-239">**アクションを適用しない**</span><span class="sxs-lookup"><span data-stu-id="ca25c-239">**Don't apply any action**</span></span>
       - <span data-ttu-id="ca25c-240">**他の電子メール アドレスへのメッセージのリダイレクト**</span><span class="sxs-lookup"><span data-stu-id="ca25c-240">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="ca25c-241">**迷惑メール フォルダーにメッセージを移動する**</span><span class="sxs-lookup"><span data-stu-id="ca25c-241">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="ca25c-242">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="ca25c-242">**Quarantine the message**</span></span>
       - <span data-ttu-id="ca25c-243">**メッセージを配信して、他のアドレスを BCC 行に追加する**</span><span class="sxs-lookup"><span data-stu-id="ca25c-243">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="ca25c-244">**配信される前にメッセージを削除する**</span><span class="sxs-lookup"><span data-stu-id="ca25c-244">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="ca25c-245">**信頼できる送信者とドメインの追加**: ポリシーの例外を指定します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-245">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="ca25c-246">**信頼できる送信者**:</span><span class="sxs-lookup"><span data-stu-id="ca25c-246">**Trusted senders**:</span></span>

       - <span data-ttu-id="ca25c-247">ボックス内をクリックし、選択するユーザーの一覧をスクロールします。</span><span class="sxs-lookup"><span data-stu-id="ca25c-247">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="ca25c-248">ボックスをクリックし、入力してリストをフィルター処理し、ユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-248">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="ca25c-249">エントリを削除するには、ユーザーの \*\*[削除\*\* ![ ] ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca25c-249">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="ca25c-250">**信頼できるドメイン**: ドメイン名 (例: contoso.com) を入力し、Enter キーを押して、必要に応じて繰り返します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-250">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="ca25c-251">**設定を確認**します。個々の手順をクリックする代わりに、設定が概要に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-251">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="ca25c-252">各セクションで **[編集** ] をクリックすると、関連するページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="ca25c-252">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="ca25c-253">次の設定は、このページ **で直接 [オン** ] **または [オフ** ] に切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-253">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="ca25c-254">**保護されたユーザー**</span><span class="sxs-lookup"><span data-stu-id="ca25c-254">**Protected users**</span></span>
       - <span data-ttu-id="ca25c-255">**保護されたドメイン** \>**所有するドメインを含む**</span><span class="sxs-lookup"><span data-stu-id="ca25c-255">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="ca25c-256">**保護されたドメイン** \>**保護されたドメイン**(カスタム ドメイン)</span><span class="sxs-lookup"><span data-stu-id="ca25c-256">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="ca25c-257">**メールボックス インテリジェンス**</span><span class="sxs-lookup"><span data-stu-id="ca25c-257">**Mailbox intelligence**</span></span>

   <span data-ttu-id="ca25c-258">完了したら、[任意のページで保存 **]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca25c-258">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="ca25c-259">**スプー**フ **ィング** : スプーフィング インテリジェンスを有効または無効にするには [編集] をクリックし、Outlook の認証されていない送信者識別情報をオンまたはオフにし、ブロックされるスプーフィングされた送信者からのメッセージに適用するアクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-259">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="ca25c-260">詳細については、フィッ [シング対策ポリシーでのスプーフィング設定に関するトピックを参照してください](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-260">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="ca25c-261">これらの設定は、EOP のフィッシング対策ポリシーでも使用可能であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ca25c-261">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="ca25c-262">**スプーフィング フィルター**の設定: 既定値は **[オン**] です。このままにしておき、お勧めします。</span><span class="sxs-lookup"><span data-stu-id="ca25c-262">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="ca25c-263">オンにするには、トグルをオフに切り替 **えます**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-263">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="ca25c-264">詳細については、「EOP でス [プーフィング インテリジェンスを構成する」を参照してください](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-264">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="ca25c-265">MX レコードが Microsoft 365 をポイントしていない場合は、スプーフィング対策保護を無効にする必要がありです。コネクタの拡張フィルター処理を有効にします。</span><span class="sxs-lookup"><span data-stu-id="ca25c-265">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="ca25c-266">手順については [、「Exchange Online のコネクタ用の拡張フィルター処理」を参照してください](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-266">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="ca25c-267">**[認証されていない送信者] 機能を有効**にします。既定値は **On です**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-267">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="ca25c-268">オンにするには、トグルをオフに切り替 **えます**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-268">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="ca25c-269">**アクション**: スプーフィング インテリジェンスに失敗したメッセージに対して実行するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-269">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="ca25c-270">**メールが、ドメインのスプーフィングを許可されていないユーザーから送信された場合**:</span><span class="sxs-lookup"><span data-stu-id="ca25c-270">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="ca25c-271">**受信者の迷惑メール フォルダーにメッセージを移動する**</span><span class="sxs-lookup"><span data-stu-id="ca25c-271">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="ca25c-272">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="ca25c-272">**Quarantine the message**</span></span>

   - <span data-ttu-id="ca25c-273">**設定を確認**します。個々の手順をクリックする代わりに、設定が概要に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-273">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="ca25c-274">各セクションで **[編集** ] をクリックすると、関連するページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="ca25c-274">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="ca25c-275">次の設定は、このページ **で直接 [オン** ] **または [オフ** ] に切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-275">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="ca25c-276">**スプーフィング対策保護を有効にする**</span><span class="sxs-lookup"><span data-stu-id="ca25c-276">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="ca25c-277">**認証されていない送信者機能を有効にする**</span><span class="sxs-lookup"><span data-stu-id="ca25c-277">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="ca25c-278">完了したら、[任意のページで保存 **]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca25c-278">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="ca25c-279">**詳細設定**: [ **編集] をクリック** して、高度なフィッシングしきい値を構成します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-279">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="ca25c-280">詳細については [、ATP フィッシング対策ポリシーの高度なフィッシングしきい値を参照してください](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-280">For more information, see [Advanced phishing thresholds in ATP anti-phishing policies](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="ca25c-281">**高度なフィッシングしきい値**: 次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-281">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="ca25c-282">**1 - 標準** (これが既定値です)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-282">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="ca25c-283">**2 - Aggressive**</span><span class="sxs-lookup"><span data-stu-id="ca25c-283">**2 - Aggressive**</span></span>
   - <span data-ttu-id="ca25c-284">**3 - よりすか**</span><span class="sxs-lookup"><span data-stu-id="ca25c-284">**3 - More aggressive**</span></span>
   - <span data-ttu-id="ca25c-285">**4 - 最ももさもする**</span><span class="sxs-lookup"><span data-stu-id="ca25c-285">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="ca25c-286">**設定を確認します**。[ **編集]** をクリックして、[詳細フィッ **シングのしきい値] ページに戻** ります。</span><span class="sxs-lookup"><span data-stu-id="ca25c-286">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="ca25c-287">完了したら、[ページの [保存 **]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca25c-287">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="ca25c-288">[ポリシーの編集 **] \<Name\> ページに戻り**、設定を確認してから [閉じる] を**クリックします**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-288">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-atp-anti-phishing-policy"></a><span data-ttu-id="ca25c-289">セキュリティ/コンプライアンス センター&、既定の ATP フィッシング対策ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="ca25c-289">Use the Security & Compliance Center to modify the default ATP anti-phishing policy</span></span>

<span data-ttu-id="ca25c-290">既定の ATP フィッシング対策ポリシーの名前は Office365 AntiPhish Default で、ポリシーの一覧には表示されません。</span><span class="sxs-lookup"><span data-stu-id="ca25c-290">The default ATP anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="ca25c-291">既定の ATP フィッシング対策ポリシーを変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-291">To modify the default ATP anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="ca25c-292">コンプライアンス センターから&で、 **脅威管理** \> **ポリシー** \> **の ATP フィッシング対策に移動します**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-292">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="ca25c-293">[フ **ィッシング対策] ページで、[既定** のポリシー] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-293">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="ca25c-294">ポリシー **の編集に Office365 AntiPhish の [Default]** ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-294">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="ca25c-295">次のセクションを利用できます。このセクションには、カスタム ポリシーを変更するときに関する同じ [設定が含まれます](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-295">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):</span></span>

   - <span data-ttu-id="ca25c-296">**偽装**</span><span class="sxs-lookup"><span data-stu-id="ca25c-296">**Impersonation**</span></span>
   - <span data-ttu-id="ca25c-297">**スプーフィング**</span><span class="sxs-lookup"><span data-stu-id="ca25c-297">**Spoof**</span></span>
   - <span data-ttu-id="ca25c-298">**詳細設定**</span><span class="sxs-lookup"><span data-stu-id="ca25c-298">**Advanced settings**</span></span>

   <span data-ttu-id="ca25c-299">以下の設定は、既定のポリシーを変更する場合には使用できません。</span><span class="sxs-lookup"><span data-stu-id="ca25c-299">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="ca25c-300">ポリシー設定の**セクションと値**は表示されますが、[編集] リンク**Edit**がないため、設定 (ポリシー名、説明、ポリシーの対象者) は変更できません (ポリシー名、説明、ポリシーの対象者) は変更できません。</span><span class="sxs-lookup"><span data-stu-id="ca25c-300">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="ca25c-301">既定のポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="ca25c-301">You can't delete the default policy.</span></span>
   - <span data-ttu-id="ca25c-302">既定のポリシーの優先度は変更できません (常に最後に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-302">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="ca25c-303">[ポリシー **の編集] ページで、Office365 AntiPhish Default** ページで設定を確認してから [閉じる] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-303">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-atp-anti-phishing-policies"></a><span data-ttu-id="ca25c-304">カスタム ATP フィッシング対策ポリシーを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="ca25c-304">Enable or disable custom ATP anti-phishing policies</span></span>

1. <span data-ttu-id="ca25c-305">コンプライアンス センターから&で、 **脅威管理** \> **ポリシー** \> **の ATP フィッシング対策に移動します**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-305">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="ca25c-306">状態列の値に **注意** してください。</span><span class="sxs-lookup"><span data-stu-id="ca25c-306">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="ca25c-307">ポリシーを無効にするには、 **トグ** ルをオフに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-307">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="ca25c-308">ポリシーを有効にするには、ト **グルをオン** に切り替えします。</span><span class="sxs-lookup"><span data-stu-id="ca25c-308">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="ca25c-309">既定のフィッシング対策ポリシーを無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ca25c-309">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-atp-anti-phishing-policies"></a><span data-ttu-id="ca25c-310">カスタムの ATP フィッシング対策ポリシーの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="ca25c-310">Set the priority of custom ATP anti-phishing policies</span></span>

<span data-ttu-id="ca25c-311">既定では、ATP フィッシング対策ポリシーには、ポリシーの作成順序に基づく優先度が設定されます (新しいポリシーの優先度は、古いポリシーよりも低くなります)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-311">By default, ATP anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="ca25c-312">優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-312">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="ca25c-313">2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-313">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="ca25c-314">優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca25c-314">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="ca25c-315">カスタム ATP フィッシング対策ポリシーは、処理された順に表示されます (最初のポリシーの **優先度** が 0 に設定されている)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-315">Custom ATP anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="ca25c-316">Office365 AntiPhish Default という名前の既定のフィッシング対策ポリシーには、カスタム優先度 **の値 Lowest**が設定されているため、変更できません。</span><span class="sxs-lookup"><span data-stu-id="ca25c-316">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="ca25c-317">**注**: コンプライアンス センターでは&、ATP フィッシング対策ポリシーの優先度は、そのポリシーの作成後にのみ変更できます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-317">**Note**: In the Security & Compliance Center, you can only change the priority of the ATP anti-phishing policy after you create it.</span></span> <span data-ttu-id="ca25c-318">PowerShell では、フィッシング対策ルールの作成時に既定の優先度を上書きできます (これは、既存のルールの優先度に影響を与え可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-318">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="ca25c-319">ポリシーの優先度を変更するには、ポリシー **のプロパティの優先度を上** 昇する、または **低** 下します (セキュリティ &/コンプライアンス センターの **優先度** 番号を直接変更することはできません)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-319">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="ca25c-320">複数のポリシーがある場合のみ、ポリシーの優先度を変更するのは意味があります。</span><span class="sxs-lookup"><span data-stu-id="ca25c-320">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="ca25c-321">コンプライアンス センターから&で、 **脅威管理** \> **ポリシー** \> **の ATP フィッシング対策に移動します**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-321">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="ca25c-322">変更するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-322">Select the policy that you want to modify.</span></span> <span data-ttu-id="ca25c-323">既に選択されている場合は、選択を解除してもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-323">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="ca25c-324">[**ポリシーの編集 \<name\> ]** ポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-324">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="ca25c-325">**優先度**値 0 のカスタム ATP フィッシング対策ポリシーでは、優先度の値**を 0**とするだけ**を表示**しています。</span><span class="sxs-lookup"><span data-stu-id="ca25c-325">The custom ATP anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="ca25c-326">優先度の値が最も低いカスタム ATP フィッ**Priority**シング ポリシー (**たとえば、3)** には、[優先度の増**分] ボタンのみが**用意されています。</span><span class="sxs-lookup"><span data-stu-id="ca25c-326">The custom ATP anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="ca25c-327">3 つ以上のカスタムのフィッシング対策ポリシーがある場合、優先度の高い値と最も低い値の間のポリシーでは **、優先度** の高い値と低い優先度 **ボタンの両方が** 使用できます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-327">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="ca25c-328">優先度 **の値を上** 昇 **または下がり、** 優先度の値 **を変更** します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-328">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="ca25c-329">完了したら、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca25c-329">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-atp-anti-phishing-policies"></a><span data-ttu-id="ca25c-330">セキュリティ センター/コンプライアンス &使用して、ATP フィッシング対策ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="ca25c-330">Use the Security & Compliance Center to view ATP anti-phishing policies</span></span>

1. <span data-ttu-id="ca25c-331">セキュリティ コンプライアンス センター&で、脅威**Threat management**管理 \> **ポリシー** \> **の ATP フィッシング対策に移動します**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-331">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="ca25c-332">次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-332">Do one of the following steps:</span></span>

   - <span data-ttu-id="ca25c-333">表示するカスタム ATP フィッシング対策ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-333">Select a custom ATP anti-phishing policy that you want to view.</span></span> <span data-ttu-id="ca25c-334">既に選択されている場合は、選択を解除してもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-334">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="ca25c-335">[ **既定のポリシー]** をクリックして既定のフィッシング対策ポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-335">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="ca25c-336">[**ポリシーの編集 \<name\> ]** ポップアップが表示され、設定や値を確認できます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-336">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-atp-anti-phishing-policies"></a><span data-ttu-id="ca25c-337">セキュリティ/コンプライアンス センター&使用して、ATP フィッシング対策ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="ca25c-337">Use the Security & Compliance Center to remove ATP anti-phishing policies</span></span>

1. <span data-ttu-id="ca25c-338">コンプライアンス センターから&で、 **脅威管理** \> **ポリシー** \> **の ATP フィッシング対策に移動します**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-338">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="ca25c-339">削除するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-339">Select the policy that you want to remove.</span></span> <span data-ttu-id="ca25c-340">既に選択されている場合は、選択を解除してもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-340">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="ca25c-341">表示される**ポリシー ポ \<name\> ップ**アップの [削除] で、[**削除] ポリシーをクリック**し、表示される警告ダイアログ ボックスで [**は**い] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca25c-341">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="ca25c-342">既定のポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="ca25c-342">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-atp-anti-phishing-policies"></a><span data-ttu-id="ca25c-343">Exchange Online PowerShell を使用して ATP フィッシング対策ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="ca25c-343">Use Exchange Online PowerShell to configure ATP anti-phishing policies</span></span>

<span data-ttu-id="ca25c-344">前述のように、ATP のスパム対策ポリシーは、フィッシング対策ポリシーとフィッシング対策ルールで構成されています。</span><span class="sxs-lookup"><span data-stu-id="ca25c-344">As previously described, an ATP anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="ca25c-345">Exchange Online PowerShell では、フィッシング対策ポリシーとフィッシング対策ルールの違いは明らかです。</span><span class="sxs-lookup"><span data-stu-id="ca25c-345">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="ca25c-346">\*\* \* -AntiPhishPolicy**コマンドレットを使用してフィッシング対策ポリシーを管理し** \* 、-AntiPhishRule\*\*コマンドレットを使用してフィッシング対策ルールを管理します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-346">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="ca25c-347">PowerShell では、最初にフィッシング対策ポリシーを作成し、次に、そのルールを適用するポリシーを特定するフィッシング対策ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-347">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="ca25c-348">PowerShell では、フィッシング対策ポリシーとフィッシング対策ルールの設定は個別に変更します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-348">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="ca25c-349">PowerShell からフィッシング対策ポリシーを削除すると、対応するフィッシング対策ルールは自動で削除されず、逆も同じ手順で削除されます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-349">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="ca25c-350">PowerShell を使用してフィッシング対策ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="ca25c-350">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="ca25c-351">PowerShell では、フィッシング対策ポリシーの作成は 2 つの手順で行います。</span><span class="sxs-lookup"><span data-stu-id="ca25c-351">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="ca25c-352">フィッシング対策ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-352">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="ca25c-353">ルールを適用するフィッシング対策ポリシーを指定するフィッシング対策ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-353">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="ca25c-354">**注**:</span><span class="sxs-lookup"><span data-stu-id="ca25c-354">**Notes**:</span></span>

- <span data-ttu-id="ca25c-355">新しいフィッシング対策ルールを作成し、関連付けられていない既存のフィッシング対策ポリシーをそのルールに割り当てて、新しいフィッシング対策ルールを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-355">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="ca25c-356">フィッシング対策ルールを複数のフィッシング対策ポリシーと関連付けすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ca25c-356">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="ca25c-357">PowerShell の新しいフィッシング対策ポリシーに以下の設定を構成できます。これらの設定は、ポリシーを作成した後でなけない場合はセキュリティ & コンプライアンス センターでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="ca25c-357">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="ca25c-358">無効化された新しいポリシーを作成_します_ `$false` **(New-AntiPhishRule コマンドレットで有効** )。</span><span class="sxs-lookup"><span data-stu-id="ca25c-358">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="ca25c-359">_Priority_ _\<Number\>_ **New-AntiPhishRule**コマンドレット上で作成中にポリシーの優先度を設定します (優先順位)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-359">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="ca25c-360">PowerShell で作成する新しいフィッシング対策ポリシーは、ポリシーをフィッシング対策規則に割り当てるまで、セキュリティ & コンプライアンス センターには表示されません。</span><span class="sxs-lookup"><span data-stu-id="ca25c-360">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="ca25c-361">手順 1: PowerShell を使用してフィッシング対策ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="ca25c-361">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="ca25c-362">フィッシング対策ポリシーを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-362">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="ca25c-363">この例では、次の設定で Research Quarantine という名前のフィッシング対策ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-363">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="ca25c-364">ポリシーは有効になっています _(Enabled_ パラメーターを使用していません。既定値は次の値です `$true` )。</span><span class="sxs-lookup"><span data-stu-id="ca25c-364">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="ca25c-365">説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ca25c-365">The description is: Research department policy.</span></span>
- <span data-ttu-id="ca25c-366">すべての承認済みドメイン、および組織のドメインのターゲット ドメインに対する組織ドメインfabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="ca25c-366">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="ca25c-367">偽装から保護するユーザーとして Mai Fujito (mfujito@fabrikam.com) を指定します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-367">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="ca25c-368">メールボックスのインテリジェンスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ca25c-368">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="ca25c-369">メールボックスのインテリジェンス保護を有効にし、検疫アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-369">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="ca25c-370">安全性のヒントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ca25c-370">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="ca25c-371">構文およびパラメーターの詳細については [、New-AntiPhishPolicy を参照してください](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-371">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="ca25c-372">手順 2: PowerShell を使用してフィッシング対策ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="ca25c-372">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="ca25c-373">フィッシング対策ルールを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-373">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="ca25c-374">この例では、次の条件の、Research Department という名前のフィッシング対策ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-374">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="ca25c-375">ルールは、Research Quarantine という名前のフィッシング対策ポリシーに関連付けられていです。</span><span class="sxs-lookup"><span data-stu-id="ca25c-375">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="ca25c-376">ルールは Research Department という名前のグループのメンバーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-376">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="ca25c-377">Priority パラメーターを使用しない _ので_ 、既定の優先順位が使用されます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-377">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="ca25c-378">構文およびパラメーターの詳細については [、New-AntiPhishRule を参照してください](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-378">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="ca25c-379">PowerShell を使用してフィッシング対策ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="ca25c-379">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="ca25c-380">既存のフィッシング対策ポリシーを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-380">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="ca25c-381">この例では、指定したプロパティと共にすべてのフィッシング対策ポリシーの要約リストを返します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-381">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="ca25c-382">この例では、Executives という名前のフィッシング対策ポリシーのすべてのプロパティの値を返します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-382">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="ca25c-383">構文およびパラメーターの詳細については [、「Get-AntiPhishPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-383">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="ca25c-384">PowerShell を使用してフィッシング対策ルールを表示する</span><span class="sxs-lookup"><span data-stu-id="ca25c-384">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="ca25c-385">既存のフィッシング対策ルールを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-385">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="ca25c-386">この例では、すべてのフィッシング対策ルールと指定したプロパティの要約リストを返します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-386">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="ca25c-387">ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-387">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="ca25c-388">この例では、Contoso Executives という名前のフィッシング対策ルールのすべてのプロパティの値を返します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-388">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="ca25c-389">構文およびパラメーターの詳細については [、「Get-AntiPhishRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-389">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="ca25c-390">PowerShell を使用してフィッシング対策ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="ca25c-390">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="ca25c-391">以下の項目以外では、PowerShell でフィッシング対策ポリシーを変更するときにも、このトピックの前述の手順 [1 で説明](#step-1-use-powershell-to-create-an-anti-phish-policy) したように、ポリシーを作成する場合と同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-391">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="ca25c-392">指定 _したポリシー_ を既定のポリシー (すべてのユーザーに適用し、常に優先度が最も低 **く、削除** できない) に切り替える MakeDefault スイッチは、PowerShell でフィッシング対策ポリシーを変更する場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-392">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="ca25c-393">フィッシング対策ポリシーの名前は、変更できません **(Set-AntiPhishPolicy コマンドレット** には _Name_ パラメーターはありません)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-393">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="ca25c-394">セキュリティ/& コンプライアンス センターでフィッシング対策ポリシーの名前を変更する場合、フィッシング対策ルールの名前のみを変更 _しています_。</span><span class="sxs-lookup"><span data-stu-id="ca25c-394">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="ca25c-395">フィッシング対策ポリシーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-395">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="ca25c-396">構文およびパラメーターの詳細については [、「Set-AntiPhishPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-396">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="ca25c-397">PowerShell を使用してフィッシング対策ルールを変更する</span><span class="sxs-lookup"><span data-stu-id="ca25c-397">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="ca25c-398">PowerShell でフィッシング対策ルールを変更するときに使用できない設定は _、無効なルール_ の作成を可能にする Enabled パラメーターのみです。</span><span class="sxs-lookup"><span data-stu-id="ca25c-398">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="ca25c-399">既存のフィッシング対策ルールを有効または無効にするには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca25c-399">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="ca25c-400">それ以外の場合、PowerShell でフィッシング対策ルールを変更するときに利用可能な追加の設定はありません。</span><span class="sxs-lookup"><span data-stu-id="ca25c-400">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="ca25c-401">手順 [2: PowerShell](#step-2-use-powershell-to-create-an-anti-phish-rule) を使用して前述の手順で説明したルールを作成するときに同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-401">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="ca25c-402">フィッシング対策ルールを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-402">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="ca25c-403">構文およびパラメーターの詳細については [、「Set-AntiPhishRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-403">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="ca25c-404">PowerShell を使用してフィッシング対策ルールを有効化または無効化する</span><span class="sxs-lookup"><span data-stu-id="ca25c-404">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="ca25c-405">PowerShell でフィッシング対策ルールを有効化または無効化すると、フィッシング対策ポリシー全体 (フィッシング対策ルールおよび割り当てられたフィッシング対策ポリシー) が有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="ca25c-405">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="ca25c-406">既定のフィッシング対策ポリシーを有効または無効にすることはできません (常にすべての受信者に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-406">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="ca25c-407">PowerShell でフィッシング対策ルールを有効化または無効化するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-407">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="ca25c-408">この例では、Marketing Department という名前のフィッシング対策ルールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="ca25c-408">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="ca25c-409">この例では、同じルールを有効化します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-409">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="ca25c-410">構文およびパラメーターの詳細については [、「Enable-AntiPhishRule および](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) [Disable-AntiPhishRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-410">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="ca25c-411">PowerShell を使用してフィッシング対策ルールの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="ca25c-411">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="ca25c-412">ルールに設定できる優先度の最高値値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="ca25c-412">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="ca25c-413">設定できる最低値はルールの数に依存します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-413">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="ca25c-414">たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。</span><span class="sxs-lookup"><span data-stu-id="ca25c-414">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="ca25c-415">既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-415">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="ca25c-416">たとえば、カスタム ルールが 5 つあって (優先度 0 から 4)、1 つのルールの優先度を 2 に変更した場合には、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。</span><span class="sxs-lookup"><span data-stu-id="ca25c-416">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="ca25c-417">PowerShell でフィッシング対策ルールの優先度を設定するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-417">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="ca25c-p144">この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-p144">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="ca25c-420">**注**:</span><span class="sxs-lookup"><span data-stu-id="ca25c-420">**Notes**:</span></span>

- <span data-ttu-id="ca25c-421">新しく作成したルールの優先度を設定するには **、New-AntiPhishRule**コマンドレットの_Priority_パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-421">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="ca25c-422">既定のフィッシング対策ポリシーには対応するフィッシング対策ルールがありません。また、常に、変更不可能な優先順位の **値 Lowest が設定されます**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-422">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="ca25c-423">PowerShell を使用してフィッシング対策ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="ca25c-423">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="ca25c-424">PowerShell を使用してフィッシング対策ポリシーを削除した場合、対応するフィッシング対策ルールは削除されません。</span><span class="sxs-lookup"><span data-stu-id="ca25c-424">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="ca25c-425">PowerShell でフィッシング対策ポリシーを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-425">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="ca25c-426">この例では、Marketing Department という名前のフィッシング対策ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-426">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="ca25c-427">構文およびパラメーターの詳細については [、Remove-AntiPhishPolicy を参照してください](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-427">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="ca25c-428">PowerShell を使用してフィッシング対策ルールを削除する</span><span class="sxs-lookup"><span data-stu-id="ca25c-428">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="ca25c-429">PowerShell を使用してフィッシング対策ルールを削除した場合、対応するフィッシング対策ポリシーは削除されません。</span><span class="sxs-lookup"><span data-stu-id="ca25c-429">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="ca25c-430">PowerShell でフィッシング対策ルールを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-430">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="ca25c-431">この例では、Marketing Department という名前のフィッシング対策ルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-431">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="ca25c-432">構文およびパラメーターの詳細については [、Remove-AntiPhishRule を参照してください](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="ca25c-432">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="ca25c-433">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="ca25c-433">How do you know these procedures worked?</span></span>

<span data-ttu-id="ca25c-434">ATP フィッシング対策ポリシーが正常に構成されたことを確認するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-434">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="ca25c-435">コンプライアンス センターから&で、 **脅威管理** \> **ポリシー** \> **の ATP フィッシング対策に移動します**。</span><span class="sxs-lookup"><span data-stu-id="ca25c-435">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="ca25c-436">ポリシーの一覧とその Status 値 **および Priority** 値 **を確認** します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-436">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="ca25c-437">詳細を表示するには、次の手順のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-437">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="ca25c-438">一覧からポリシーを選択して、ポップアップに詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-438">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="ca25c-439">[ **既定] ポリシーを** クリックし、ポップアップに詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-439">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="ca25c-440">Exchange Online PowerShell でポリシーまたは \<Name\> ルールの名前を置き換え、次のコマンドを実行し、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="ca25c-440">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
