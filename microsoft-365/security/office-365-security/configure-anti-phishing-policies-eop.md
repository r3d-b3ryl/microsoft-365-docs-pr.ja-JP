---
title: EOP でフィッシング対策ポリシーを構成する
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
description: 管理者は、Exchange Online Protection (EOP) 組織で Exchange Online のメールボックスを持つまたは使用しない場合に使用可能なフィッシング対策ポリシーを作成、変更、および削除する方法を学習できます。
ms.openlocfilehash: af6577d32d43300867d29a365baaa4e1e7e1b5e3
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825751"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="60b19-103">EOP でフィッシング対策ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="60b19-103">Configure anti-phishing policies in EOP</span></span>

<span data-ttu-id="60b19-104">Exchange Online にメールボックスがある Microsoft 365 組織や、Exchange Online のメールボックスを使用しないスタンドアロン Exchange Online Protection (EOP) 組織では、既定で有効になっている、スプーフィング対策機能の数を制限したものを含む既定のフィッシング対策ポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="60b19-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="60b19-105">詳細については、フィッ [シング対策ポリシーでのスプーフィング設定に関するトピックを参照してください](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="60b19-105">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="60b19-106">管理者は、既定のフィッシング対策ポリシーを表示、編集、構成できます (削除はできません)。</span><span class="sxs-lookup"><span data-stu-id="60b19-106">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="60b19-107">よりきめ細かく計画する場合は、組織内の特定のユーザー、グループ、またはドメインに適用するカスタムのフィッシング対策ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="60b19-107">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="60b19-108">カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (実行順序) を変更できます。</span><span class="sxs-lookup"><span data-stu-id="60b19-108">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="60b19-109">Exchange Online メールボックスを使用している組織は、セキュリティコンプライアンス センターまたは Exchange Online PowerShell でフィッ &シング対策ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="60b19-109">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="60b19-110">スタンドアロン EOP 組織は、コンプライアンス センターのセキュリティ &のみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="60b19-110">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="60b19-111">Office 365 Advanced Threat Protection (Office 365 ATP) で利用できるより高度な ATP フィッシング対策ポリシーの作成と変更の詳細については [、「ATP フィッシング対策ポリシーを構成する」を参照してください](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="60b19-111">For information about creating and modifying the more advanced ATP anti-phishing policies that are available in Office 365 Advanced Threat Protection (Office 365 ATP), see [Configure ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

<span data-ttu-id="60b19-112">フィッシング対策ポリシーの基本的な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="60b19-112">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="60b19-113">**フィッシング対策ポリシー**: 有効化/無効化するフィッシング対策と、オプションを適用するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="60b19-113">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="60b19-114">**フィッシング対策ルール**: フィッシング対策ポリシーの優先順位と受信者フィルター (ポリシーが適用される対象者) を指定します。</span><span class="sxs-lookup"><span data-stu-id="60b19-114">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="60b19-115">これら 2 つの要素の違いは、セキュリティ/コンプライアンス センターでフィッシング対策ポリシーを管理する際には分&りません。</span><span class="sxs-lookup"><span data-stu-id="60b19-115">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="60b19-116">フィッシング対策ポリシーを作成する場合、実際にはフィッシング対策ルールと、関連するフィッシング対策ポリシーの両方に同じ名前を使用して同時に作成します。</span><span class="sxs-lookup"><span data-stu-id="60b19-116">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="60b19-117">フィッシング対策ポリシーを変更すると、名前、優先順位、有効/無効の設定、および受信者フィルターに関連する設定はフィッシング対策ルールを変更します。</span><span class="sxs-lookup"><span data-stu-id="60b19-117">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="60b19-118">その他のすべての設定は、関連付けられているフィッシング対策ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="60b19-118">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="60b19-119">フィッシング対策ポリシーを削除すると、フィッシング対策ルールと、関連するフィッシング対策ポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="60b19-119">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="60b19-120">Exchange Online PowerShell では、ポリシーとルールを個別に管理します。</span><span class="sxs-lookup"><span data-stu-id="60b19-120">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="60b19-121">詳細については、後述する [「Exchange Online PowerShell を使用する](#use-exchange-online-powershell-to-configure-anti-phishing-policies) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="60b19-121">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this topic.</span></span>

<span data-ttu-id="60b19-122">すべての組織には、Office365 AntiPhish Default という名前の組み込みのフィッシング対策ポリシーがあり、これには次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="60b19-122">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="60b19-123">ポリシーと関連付けられているフィッシング対策ルール (受信者フィルター) がない場合でも、ポリシーは組織内のすべての受信者に適用されます。</span><span class="sxs-lookup"><span data-stu-id="60b19-123">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="60b19-124">ポリシーにはカスタムの優先順位の値 **Lowest** が設定されており、変更することはできません (このポリシーは常に最後に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="60b19-124">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="60b19-125">作成するどのカスタム ポリシーも、より高い優先順位を持ちます。</span><span class="sxs-lookup"><span data-stu-id="60b19-125">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="60b19-126">ポリシーは既定のポリシー (**IsDefault** のプロパティが `True` の値になっている) であり、既定のポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="60b19-126">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="60b19-127">フィッシング対策保護の効果を高むには、特定のユーザーまたはユーザー グループに適用される、高い設定を持つカスタムのフィッシング対策ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="60b19-127">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="60b19-128">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="60b19-128">What do you need to know before you begin?</span></span>

- <span data-ttu-id="60b19-129"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="60b19-129">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="60b19-130">フィッシング **対策ページに直接移動するには** 、次の手順を使用します <https://protection.office.com/antiphishing> 。</span><span class="sxs-lookup"><span data-stu-id="60b19-130">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="60b19-131">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60b19-131">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="60b19-132">スタンドアロンの EOP PowerShell でフィッシング対策ポリシーを管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="60b19-132">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="60b19-133">このトピックの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="60b19-133">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="60b19-134">フィッシング対策ポリシーを追加、変更、および削除するには、次の役割グループのいずれかのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="60b19-134">To add, modify, and delete anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="60b19-135">**組織の管理**または[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ管理者**。</span><span class="sxs-lookup"><span data-stu-id="60b19-135">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="60b19-136">**組織の管理**または [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**検疫管理**。</span><span class="sxs-lookup"><span data-stu-id="60b19-136">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="60b19-137">フィッシング対策ポリシーに読み取り専用アクセスするには、次の役割グループのいずれかのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="60b19-137">For read-only access to anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="60b19-138">[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ閲覧者**。</span><span class="sxs-lookup"><span data-stu-id="60b19-138">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="60b19-139">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**表示限定の組織管理**。</span><span class="sxs-lookup"><span data-stu-id="60b19-139">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="60b19-140">スタンドアロン EOP で迷惑メール対策ポリシーを作成および変更するには、テナントの検疫が必要な _ことを行う_ 必要があります。</span><span class="sxs-lookup"><span data-stu-id="60b19-140">To be able to create and modify anti-spam policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="60b19-141">たとえば、Exchange 管理センター (EAC) で、[ **アクセス** 許可] タブに移動し、既存の役割グループを選択して、[ **編集** ![ ] アイコンをクリックし、役割を削除 (最終的にもう 1 ](../../media/ITPro-EAC-EditIcon.png) つ追加します) にできます。</span><span class="sxs-lookup"><span data-stu-id="60b19-141">For example, in the Exchange admin center (EAC), you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="60b19-142">テナントがハイドレートされていない場合は、[組織の設定 **の更新]** という名前のダイアログが表示されます。このバーが進行状況バーを使用して正常に完了します。</span><span class="sxs-lookup"><span data-stu-id="60b19-142">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="60b19-143">ハイドレートの詳細については [、「Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) コマンドレット (スタンドアロン EOP PowerShell またはセキュリティ/コンプライアンス センターでは使用できない」) & を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60b19-143">For more information about hydration, see the [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="60b19-144">フィッシング対策ポリシーに推奨される設定については [、EOP の既定のフィッシング対策ポリシー設定を参照してください](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="60b19-144">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="60b19-145">更新したポリシーが適用されるまで最大 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="60b19-145">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="60b19-146">フィルター パイプライン内でのフィッシング対策ポリシーの適用場所については、「 [メール保護の順序と優先順位」を参照してください](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="60b19-146">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="60b19-147">セキュリティ/コンプライアンス センター&使用してフィッシング対策ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="60b19-147">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="60b19-148">セキュリティ/& コンプライアンス センターでカスタム アンチフィッシング対策ポリシーを作成すると、フィッシング対策ルールと、関連するフィッシング対策ポリシーが両方に対して同じ名前を使用して同時に作成されます。</span><span class="sxs-lookup"><span data-stu-id="60b19-148">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="60b19-149">フィッシング対策ポリシーを作成する場合、ポリシー名、説明、およびポリシーが適用されるユーザーを識別する受信者フィルターのみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="60b19-149">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="60b19-150">ポリシーを作成した後は、ポリシーを変更して既定のフィッシング対策設定を変更または確認できます。</span><span class="sxs-lookup"><span data-stu-id="60b19-150">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="60b19-151">セキュリティ/コンプライアンス &で、脅威**Threat management**管理 \> **ポリシー** \> **のフィッシング対策に移動します**。</span><span class="sxs-lookup"><span data-stu-id="60b19-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="60b19-152">[フ **ィッシング対策] ページで、[作成** ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="60b19-152">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="60b19-153">新 **しいフィッシング対策ポリシーの作成ウィザード** が開きます。</span><span class="sxs-lookup"><span data-stu-id="60b19-153">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="60b19-154">[ポリシー **に名前を付けた** らす] ページで、以下の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="60b19-154">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="60b19-155">**[名前]**: わかりやすい一意のポリシー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="60b19-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="60b19-156">**[説明]**: ポリシーについての説明を入力します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="60b19-156">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="60b19-157">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60b19-157">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="60b19-158">表示される **ページに** [適用] ページで、ポリシーが適用される内部の受信者を識別します。</span><span class="sxs-lookup"><span data-stu-id="60b19-158">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="60b19-159">各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="60b19-159">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="60b19-160">同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="60b19-160">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="60b19-161">a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="60b19-161">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="60b19-162">[条件 **の追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="60b19-162">Click **Add a condition**.</span></span> <span data-ttu-id="60b19-163">表示されるドロップダウンで、[適用する条件: **Applied if**</span><span class="sxs-lookup"><span data-stu-id="60b19-163">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="60b19-164">**受信者は次の場所**に、組織内の 1 つ以上のメールボックス、メール ユーザー、またはメール連絡先を指定します。</span><span class="sxs-lookup"><span data-stu-id="60b19-164">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="60b19-165">**受信者が次のメンバーの場合**: 組織内の 1 つまたは複数のグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="60b19-165">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="60b19-166">**[受信者のドメインが次の値である]**: 組織内で構成済みの 1 つ以上の承認済みドメイン内の受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="60b19-166">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="60b19-167">条件を選択すると、これらのボックスが見つかり、対応する **ドロップダウンが表示** されます。</span><span class="sxs-lookup"><span data-stu-id="60b19-167">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="60b19-168">ボックス内をクリックし、選択する値のリストをスクロールします。</span><span class="sxs-lookup"><span data-stu-id="60b19-168">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="60b19-169">ボックスをクリックし、入力してリストをフィルター処理し、値を選択します。</span><span class="sxs-lookup"><span data-stu-id="60b19-169">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="60b19-170">値を追加するには、ボックス内の空の領域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60b19-170">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="60b19-171">個々のエントリを削除するには、値 \*\*の [削除\*\* ![ ] ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="60b19-171">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="60b19-172">条件全体を削除するには、条件の [ **削除** ![ ] ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="60b19-172">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="60b19-173">条件をさらに追加するには、条件を **追加し、[適用する場合** は残りの値 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="60b19-173">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="60b19-174">例外を追加するには、[条件を **追加] をクリックし、[** 次の場合を除く] の下 **で例外を選択します**。</span><span class="sxs-lookup"><span data-stu-id="60b19-174">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="60b19-175">設定と動作は、条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="60b19-175">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="60b19-176">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60b19-176">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="60b19-177">表示される **設定の確認** ページで設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="60b19-177">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="60b19-178">各設定で [ **編集** ] をクリックすると、変更できます。</span><span class="sxs-lookup"><span data-stu-id="60b19-178">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="60b19-179">完了したら、[このポリシーの作成] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="60b19-179">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="60b19-180">表示された確認ダイアログで **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60b19-180">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="60b19-181">これらの一般的なポリシー設定でフィッシング対策ポリシーを作成した後、次のセクションの手順を使用して、ポリシーの保護設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="60b19-181">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="60b19-182">セキュリティ コンプライアンス センター&、フィッシング対策ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="60b19-182">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="60b19-183">作成した新しいポリシー、または既にカスタマイズした既存のポリシーのフィッシング対策ポリシーを変更するには、以下の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="60b19-183">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="60b19-184">まだ開いていない場合は、セキュリティ/コンプライアンス センターを開&、脅威 **管理** \> **ポリシー** \> **アンチフィッシングに移動します**。</span><span class="sxs-lookup"><span data-stu-id="60b19-184">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="60b19-185">変更するカスタムのフィッシング対策ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="60b19-185">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="60b19-186">既に選択されている場合は、選択を解除してもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="60b19-186">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="60b19-187">[**ポリシーの編集 \<name\> ]** ポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="60b19-187">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="60b19-188">いずれかの **セクション** で [編集] をクリックすると、そのセクションの設定にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="60b19-188">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="60b19-189">次の手順は、セクションが表示される順番で示されますが、順番に説明しません (セクションは任意の順序で選択および変更できます)。</span><span class="sxs-lookup"><span data-stu-id="60b19-189">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="60b19-190">セクションで [**編集]** をクリックすると、使用できる設定がウィザード形式で表示されますが、任意の順序でページ内に移動できます。任意のページで**Save**[保存] または [**Close**閉じる] をクリックすると、[**ポリシー**の編集] ページに ![ 戻 ](../../media/scc-remove-icon.png) \*\*ることができます \<name\> \*\*(保存したり、そのまま中に行う必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="60b19-190">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="60b19-191">**ポリシー設定**: 前 **のセクション** でポリシーを作成した際に使用できていたのと同 [じ設定を変更するには](#use-the-security--compliance-center-to-create-anti-phishing-policies) 、[編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60b19-191">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="60b19-192">**名前**</span><span class="sxs-lookup"><span data-stu-id="60b19-192">**Name**</span></span>
   - <span data-ttu-id="60b19-193">**説明**</span><span class="sxs-lookup"><span data-stu-id="60b19-193">**Description**</span></span>
   - <span data-ttu-id="60b19-194">**適用先**</span><span class="sxs-lookup"><span data-stu-id="60b19-194">**Applied to**</span></span>
   - <span data-ttu-id="60b19-195">**設定の確認**</span><span class="sxs-lookup"><span data-stu-id="60b19-195">**Review your settings**</span></span>

   <span data-ttu-id="60b19-196">完了したら、[任意のページで保存 **]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60b19-196">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="60b19-197">**スプー**フ **ィング** : スプーフィング インテリジェンスを有効または無効にするには [編集] をクリックし、Outlook の認証されていない送信者識別情報をオンまたはオフにし、ブロックされるスプーフィングされた送信者からのメッセージに適用するアクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="60b19-197">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="60b19-198">詳細については、フィッ [シング対策ポリシーでのスプーフィング設定に関するトピックを参照してください](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="60b19-198">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="60b19-199">これらの設定は、ATP フィッシング対策ポリシーでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="60b19-199">Note that these same settings are also available in ATP anti-phishing policies.</span></span>

   - <span data-ttu-id="60b19-200">**スプーフィング フィルター**の設定: 既定値は **[オン**] です。このままにしておき、お勧めします。</span><span class="sxs-lookup"><span data-stu-id="60b19-200">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="60b19-201">オンにするには、トグルをオフに切り替 **えます**。</span><span class="sxs-lookup"><span data-stu-id="60b19-201">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="60b19-202">詳細については、「EOP でス [プーフィング インテリジェンスを構成する」を参照してください](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="60b19-202">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="60b19-203">MX レコードが Microsoft 365 をポイントしていない場合は、スプーフィング対策保護を無効にする必要がありです。コネクタの拡張フィルター処理を有効にします。</span><span class="sxs-lookup"><span data-stu-id="60b19-203">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="60b19-204">手順については [、「Exchange Online のコネクタ用の拡張フィルター処理」を参照してください](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="60b19-204">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="60b19-205">**[認証されていない送信者] 機能を有効**にします。既定値は **On です**。</span><span class="sxs-lookup"><span data-stu-id="60b19-205">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="60b19-206">オンにするには、トグルをオフに切り替 **えます**。</span><span class="sxs-lookup"><span data-stu-id="60b19-206">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="60b19-207">**アクション**: スプーフィング インテリジェンスに失敗したメッセージに対して実行するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="60b19-207">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="60b19-208">**メールが、ドメインのスプーフィングを許可されていないユーザーから送信された場合**:</span><span class="sxs-lookup"><span data-stu-id="60b19-208">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="60b19-209">**受信者の迷惑メール フォルダーにメッセージを移動する**</span><span class="sxs-lookup"><span data-stu-id="60b19-209">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="60b19-210">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="60b19-210">**Quarantine the message**</span></span>

   - <span data-ttu-id="60b19-211">**設定を確認**します。個々の手順をクリックする代わりに、設定が概要に表示されます。</span><span class="sxs-lookup"><span data-stu-id="60b19-211">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="60b19-212">各セクションで **[編集** ] をクリックすると、関連するページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="60b19-212">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="60b19-213">次の設定は、このページ **で直接 [オン** ] **または [オフ** ] に切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="60b19-213">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="60b19-214">**スプーフィング対策保護を有効にする**</span><span class="sxs-lookup"><span data-stu-id="60b19-214">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="60b19-215">**認証されていない送信者機能を有効にする**</span><span class="sxs-lookup"><span data-stu-id="60b19-215">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="60b19-216">完了したら、[任意のページで保存 **]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60b19-216">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="60b19-217">[ポリシーの編集 **] \<Name\> ページに戻り**、設定を確認してから [閉じる] を**クリックします**。</span><span class="sxs-lookup"><span data-stu-id="60b19-217">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="60b19-218">セキュリティ/コンプライアンス &使用して既定のフィッシング対策ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="60b19-218">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="60b19-219">既定のフィッシング対策ポリシーの名前は Office365 AntiPhish Default で、ポリシーの一覧には表示されません。</span><span class="sxs-lookup"><span data-stu-id="60b19-219">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="60b19-220">既定のフィッシング対策ポリシーを変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="60b19-220">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="60b19-221">セキュリティ/コンプライアンス &で、脅威**Threat management**管理 \> **ポリシー** \> **のフィッシング対策に移動します**。</span><span class="sxs-lookup"><span data-stu-id="60b19-221">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="60b19-222">[フ **ィッシング対策] ページで、[既定** のポリシー] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="60b19-222">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="60b19-223">ポリシー **の編集に Office365 AntiPhish の [Default]** ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="60b19-223">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="60b19-224">以下のセクションを利用できます。このセクションには、カスタム ポリシーを変更するときに関する同 [じ設定が含まれます](#use-the-security--compliance-center-to-modify-anti-phishing-policies)。</span><span class="sxs-lookup"><span data-stu-id="60b19-224">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   - <span data-ttu-id="60b19-225">**偽装**</span><span class="sxs-lookup"><span data-stu-id="60b19-225">**Impersonation**</span></span>
   - <span data-ttu-id="60b19-226">**スプーフィング**</span><span class="sxs-lookup"><span data-stu-id="60b19-226">**Spoof**</span></span>
   - <span data-ttu-id="60b19-227">**詳細設定**</span><span class="sxs-lookup"><span data-stu-id="60b19-227">**Advanced settings**</span></span>

   <span data-ttu-id="60b19-228">以下の設定は、既定のポリシーを変更する場合には使用できません。</span><span class="sxs-lookup"><span data-stu-id="60b19-228">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="60b19-229">ポリシー設定の**セクションと値**は表示されますが、[編集] リンク**Edit**がないため、設定 (ポリシー名、説明、ポリシーの対象者) は変更できません (ポリシー名、説明、ポリシーの対象者) は変更できません。</span><span class="sxs-lookup"><span data-stu-id="60b19-229">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="60b19-230">既定のポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="60b19-230">You can't delete the default policy.</span></span>
   - <span data-ttu-id="60b19-231">既定のポリシーの優先度は変更できません (常に最後に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="60b19-231">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="60b19-232">[ポリシー **の編集] ページで、Office365 AntiPhish Default** ページで設定を確認してから [閉じる] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="60b19-232">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="60b19-233">カスタムのフィッシング対策ポリシーの有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="60b19-233">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="60b19-234">セキュリティ/コンプライアンス &で、脅威**Threat management**管理 \> **ポリシー** \> **のフィッシング対策に移動します**。</span><span class="sxs-lookup"><span data-stu-id="60b19-234">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="60b19-235">状態列の値に **注意** してください。</span><span class="sxs-lookup"><span data-stu-id="60b19-235">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="60b19-236">ポリシーを無効にするには、 **トグ** ルをオフに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="60b19-236">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="60b19-237">ポリシーを有効にするには、ト **グルをオン** に切り替えします。</span><span class="sxs-lookup"><span data-stu-id="60b19-237">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="60b19-238">既定のフィッシング対策ポリシーを無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="60b19-238">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="60b19-239">カスタムのフィッシング対策ポリシーの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="60b19-239">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="60b19-240">既定では、フィッシング対策ポリシーには、ポリシーの作成順序に基づく優先度が設定されます (新しいポリシーの優先度は、古いポリシーよりも低くなります)。</span><span class="sxs-lookup"><span data-stu-id="60b19-240">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="60b19-241">優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。</span><span class="sxs-lookup"><span data-stu-id="60b19-241">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="60b19-242">2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。</span><span class="sxs-lookup"><span data-stu-id="60b19-242">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="60b19-243">優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60b19-243">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="60b19-244">カスタムのフィッシング対策ポリシーは、処理された順に表示されます (最初のポリシーの **優先度が** 0 に設定されています)。</span><span class="sxs-lookup"><span data-stu-id="60b19-244">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="60b19-245">Office365 AntiPhish Default という名前の既定のフィッシング対策ポリシーには、カスタム優先度 **の値 Lowest**が設定されているため、変更できません。</span><span class="sxs-lookup"><span data-stu-id="60b19-245">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="60b19-246">**注**: セキュリティ コンプライアンス & センターでは、ポリシーの作成後にのみフィッシング対策ポリシーの優先度を変更できます。</span><span class="sxs-lookup"><span data-stu-id="60b19-246">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="60b19-247">PowerShell では、フィッシング対策ルールの作成時に既定の優先度を上書きできます (これは、既存のルールの優先度に影響を与え可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="60b19-247">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="60b19-248">ポリシーの優先度を変更するには、ポリシー **のプロパティの優先度を上** 昇する、または **低** 下します (セキュリティ &/コンプライアンス センターの **優先度** 番号を直接変更することはできません)。</span><span class="sxs-lookup"><span data-stu-id="60b19-248">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="60b19-249">複数のポリシーがある場合のみ、ポリシーの優先度を変更するのは意味があります。</span><span class="sxs-lookup"><span data-stu-id="60b19-249">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="60b19-250">コンプライアンス センターから&で、 **脅威管理** \> **ポリシー** \> **の ATP フィッシング対策に移動します**。</span><span class="sxs-lookup"><span data-stu-id="60b19-250">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="60b19-251">変更するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="60b19-251">Select the policy that you want to modify.</span></span> <span data-ttu-id="60b19-252">既に選択されている場合は、選択を解除してもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="60b19-252">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="60b19-253">[**ポリシーの編集 \<name\> ]** ポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="60b19-253">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="60b19-254">優先度値 0 のカスタム フィッシ**Priority**ング対策ポリシーでは、優先度の値**を低\*\*\*\*下ボタンのみを使用**できます。</span><span class="sxs-lookup"><span data-stu-id="60b19-254">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="60b19-255">優先度の最も低い値を持つカスタムのフィッシ **ング** 対策ポリシー ( **たとえば、3)** には、[優先度の増 **分] ボタンのみが** 用意されています。</span><span class="sxs-lookup"><span data-stu-id="60b19-255">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="60b19-256">3 つ以上のカスタムのフィッシング対策ポリシーがある場合、優先度の高い値と最も低い値の間のポリシーでは **、優先度** の高い値と低い優先度 **ボタンの両方が** 使用できます。</span><span class="sxs-lookup"><span data-stu-id="60b19-256">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="60b19-257">優先度 **の値を上** 昇 **または下がり、** 優先度の値 **を変更** します。</span><span class="sxs-lookup"><span data-stu-id="60b19-257">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="60b19-258">完了したら、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60b19-258">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="60b19-259">セキュリティ コンプライアンス センターを&使用してフィッシング対策ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="60b19-259">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="60b19-260">セキュリティ コンプライアンス センター&で、脅威管理**ポリシーの** \> **Policy** \> **フィッシング対策に移動します**。</span><span class="sxs-lookup"><span data-stu-id="60b19-260">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="60b19-261">次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="60b19-261">Do one of the following steps:</span></span>

   - <span data-ttu-id="60b19-262">表示するカスタムのフィッシング対策ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="60b19-262">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="60b19-263">既に選択されている場合は、選択を解除してもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="60b19-263">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="60b19-264">[ **既定のポリシー]** をクリックして既定のフィッシング対策ポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="60b19-264">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="60b19-265">[**ポリシーの編集 \<name\> ]** ポップアップが表示され、設定や値を確認できます。</span><span class="sxs-lookup"><span data-stu-id="60b19-265">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="60b19-266">セキュリティ コンプライアンス センター&使用してフィッシング対策ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="60b19-266">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="60b19-267">セキュリティ/コンプライアンス &で、脅威**Threat management**管理 \> **ポリシー** \> **のフィッシング対策に移動します**。</span><span class="sxs-lookup"><span data-stu-id="60b19-267">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="60b19-268">削除するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="60b19-268">Select the policy that you want to remove.</span></span> <span data-ttu-id="60b19-269">既に選択されている場合は、選択を解除してもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="60b19-269">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="60b19-270">表示される**ポリシー ポ \<name\> ップ**アップの [削除] で、[**削除] ポリシーをクリック**し、表示される警告ダイアログ ボックスで [**は**い] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60b19-270">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="60b19-271">既定のポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="60b19-271">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="60b19-272">Exchange Online PowerShell を使用してフィッシング対策ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="60b19-272">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="60b19-273">前述のように、スパム対策ポリシーはフィッシング対策ポリシーとフィッシング対策ルールで構成されます。</span><span class="sxs-lookup"><span data-stu-id="60b19-273">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="60b19-274">Exchange Online PowerShell では、フィッシング対策ポリシーとフィッシング対策ルールの違いは明らかです。</span><span class="sxs-lookup"><span data-stu-id="60b19-274">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="60b19-275">\*\* \* -AntiPhishPolicy**コマンドレットを使用してフィッシング対策ポリシーを管理し** \* 、-AntiPhishRule\*\*コマンドレットを使用してフィッシング対策ルールを管理します。</span><span class="sxs-lookup"><span data-stu-id="60b19-275">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="60b19-276">PowerShell では、最初にフィッシング対策ポリシーを作成し、次に、そのルールを適用するポリシーを特定するフィッシング対策ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="60b19-276">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="60b19-277">PowerShell では、フィッシング対策ポリシーとフィッシング対策ルールの設定は個別に変更します。</span><span class="sxs-lookup"><span data-stu-id="60b19-277">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="60b19-278">PowerShell からフィッシング対策ポリシーを削除すると、対応するフィッシング対策ルールは自動で削除されず、逆も同じ手順で削除されます。</span><span class="sxs-lookup"><span data-stu-id="60b19-278">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="60b19-279">Exchange Online Protection PowerShell を使用して、次の PowerShell 手順は、スタンドアロン EOP 組織では使用できません。</span><span class="sxs-lookup"><span data-stu-id="60b19-279">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="60b19-280">PowerShell を使用してフィッシング対策ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="60b19-280">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="60b19-281">PowerShell では、フィッシング対策ポリシーの作成は 2 つの手順で行います。</span><span class="sxs-lookup"><span data-stu-id="60b19-281">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="60b19-282">フィッシング対策ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="60b19-282">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="60b19-283">ルールを適用するフィッシング対策ポリシーを指定するフィッシング対策ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="60b19-283">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="60b19-284">**注**:</span><span class="sxs-lookup"><span data-stu-id="60b19-284">**Notes**:</span></span>

- <span data-ttu-id="60b19-285">新しいフィッシング対策ルールを作成し、関連付けられていない既存のフィッシング対策ポリシーをそのルールに割り当てて、新しいフィッシング対策ルールを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="60b19-285">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="60b19-286">フィッシング対策ルールを複数のフィッシング対策ポリシーと関連付けすることはできません。</span><span class="sxs-lookup"><span data-stu-id="60b19-286">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="60b19-287">PowerShell の新しいフィッシング対策ポリシーに以下の設定を構成できます。これらの設定は、ポリシーを作成した後でなけない場合はセキュリティ & コンプライアンス センターでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="60b19-287">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="60b19-288">無効化された新しいポリシーを作成_します_ `$false` **(New-AntiPhishRule コマンドレットで有効** )。</span><span class="sxs-lookup"><span data-stu-id="60b19-288">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="60b19-289">_Priority_ _\<Number\>_ **New-AntiPhishRule**コマンドレット上で作成中にポリシーの優先度を設定します (優先順位)。</span><span class="sxs-lookup"><span data-stu-id="60b19-289">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="60b19-290">PowerShell で作成する新しいフィッシング対策ポリシーは、ポリシーをフィッシング対策規則に割り当てるまで、セキュリティ & コンプライアンス センターには表示されません。</span><span class="sxs-lookup"><span data-stu-id="60b19-290">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="60b19-291">手順 1: PowerShell を使用してフィッシング対策ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="60b19-291">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="60b19-292">フィッシング対策ポリシーを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="60b19-292">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableAntiSpoofEnforcement <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="60b19-293">この例では、次の設定で Research Quarantine という名前のフィッシング対策ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="60b19-293">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="60b19-294">ポリシーは有効になっています _(Enabled_ パラメーターを使用していません。既定値は次の値です `$true` )。</span><span class="sxs-lookup"><span data-stu-id="60b19-294">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="60b19-295">説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="60b19-295">The description is: Research department policy.</span></span>
- <span data-ttu-id="60b19-296">スプーフィングの既定のアクションを [検疫] に変更します。</span><span class="sxs-lookup"><span data-stu-id="60b19-296">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="60b19-297">構文およびパラメーターの詳細については [、New-AntiPhishPolicy を参照してください](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="60b19-297">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="60b19-298">手順 2: PowerShell を使用してフィッシング対策ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="60b19-298">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="60b19-299">フィッシング対策ルールを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="60b19-299">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="60b19-300">この例では、次の条件の、Research Department という名前のフィッシング対策ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="60b19-300">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="60b19-301">ルールは、Research Quarantine という名前のフィッシング対策ポリシーに関連付けられていです。</span><span class="sxs-lookup"><span data-stu-id="60b19-301">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="60b19-302">ルールは Research Department という名前のグループのメンバーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="60b19-302">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="60b19-303">Priority パラメーターを使用しない _ので_ 、既定の優先順位が使用されます。</span><span class="sxs-lookup"><span data-stu-id="60b19-303">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="60b19-304">構文およびパラメーターの詳細については [、New-AntiPhishRule を参照してください](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="60b19-304">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="60b19-305">PowerShell を使用してフィッシング対策ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="60b19-305">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="60b19-306">既存のフィッシング対策ポリシーを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="60b19-306">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="60b19-307">この例では、指定したプロパティと共にすべてのフィッシング対策ポリシーの要約リストを返します。</span><span class="sxs-lookup"><span data-stu-id="60b19-307">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="60b19-308">この例では、Executives という名前のフィッシング対策ポリシーのすべてのプロパティの値を返します。</span><span class="sxs-lookup"><span data-stu-id="60b19-308">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="60b19-309">構文およびパラメーターの詳細については [、「Get-AntiPhishPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="60b19-309">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="60b19-310">PowerShell を使用してフィッシング対策ルールを表示する</span><span class="sxs-lookup"><span data-stu-id="60b19-310">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="60b19-311">既存のフィッシング対策ルールを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="60b19-311">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="60b19-312">この例では、すべてのフィッシング対策ルールと指定したプロパティの要約リストを返します。</span><span class="sxs-lookup"><span data-stu-id="60b19-312">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="60b19-313">ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="60b19-313">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="60b19-314">この例では、Contoso Executives という名前のフィッシング対策ルールのすべてのプロパティの値を返します。</span><span class="sxs-lookup"><span data-stu-id="60b19-314">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="60b19-315">構文およびパラメーターの詳細については [、「Get-AntiPhishRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)。</span><span class="sxs-lookup"><span data-stu-id="60b19-315">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="60b19-316">PowerShell を使用してフィッシング対策ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="60b19-316">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="60b19-317">以下の項目以外では、PowerShell でフィッシング対策ポリシーを変更するときにも、このトピックの前述の手順 [1 で説明](#step-1-use-powershell-to-create-an-anti-phish-policy) したように、ポリシーを作成する場合と同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="60b19-317">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="60b19-318">指定 _したポリシー_ を既定のポリシー (すべてのユーザーに適用し、常に優先度が最も低 **く、削除** できない) に切り替える MakeDefault スイッチは、PowerShell でフィッシング対策ポリシーを変更する場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="60b19-318">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="60b19-319">フィッシング対策ポリシーの名前は、変更できません **(Set-AntiPhishPolicy コマンドレット** には _Name_ パラメーターはありません)。</span><span class="sxs-lookup"><span data-stu-id="60b19-319">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="60b19-320">セキュリティ/& コンプライアンス センターでフィッシング対策ポリシーの名前を変更する場合、フィッシング対策ルールの名前のみを変更 _しています_。</span><span class="sxs-lookup"><span data-stu-id="60b19-320">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="60b19-321">フィッシング対策ポリシーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="60b19-321">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="60b19-322">構文およびパラメーターの詳細については [、「Set-AntiPhishPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="60b19-322">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="60b19-323">PowerShell を使用してフィッシング対策ルールを変更する</span><span class="sxs-lookup"><span data-stu-id="60b19-323">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="60b19-324">PowerShell でフィッシング対策ルールを変更するときに使用できない設定は _、無効なルール_ の作成を可能にする Enabled パラメーターのみです。</span><span class="sxs-lookup"><span data-stu-id="60b19-324">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="60b19-325">既存のフィッシング対策ルールを有効または無効にするには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="60b19-325">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="60b19-326">それ以外の場合、PowerShell でフィッシング対策ルールを変更するときに利用可能な追加の設定はありません。</span><span class="sxs-lookup"><span data-stu-id="60b19-326">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="60b19-327">手順 [2: PowerShell](#step-2-use-powershell-to-create-an-anti-phish-rule) を使用して前述の手順で説明したルールを作成するときに同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="60b19-327">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="60b19-328">フィッシング対策ルールを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="60b19-328">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="60b19-329">構文およびパラメーターの詳細については [、「Set-AntiPhishRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="60b19-329">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="60b19-330">PowerShell を使用してフィッシング対策ルールを有効化または無効化する</span><span class="sxs-lookup"><span data-stu-id="60b19-330">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="60b19-331">PowerShell でフィッシング対策ルールを有効化または無効化すると、フィッシング対策ポリシー全体 (フィッシング対策ルールおよび割り当てられたフィッシング対策ポリシー) が有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="60b19-331">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="60b19-332">既定のフィッシング対策ポリシーを有効または無効にすることはできません (常にすべての受信者に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="60b19-332">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="60b19-333">PowerShell でフィッシング対策ルールを有効化または無効化するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="60b19-333">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="60b19-334">この例では、Marketing Department という名前のフィッシング対策ルールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="60b19-334">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="60b19-335">この例では、同じルールを有効化します。</span><span class="sxs-lookup"><span data-stu-id="60b19-335">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="60b19-336">構文およびパラメーターの詳細については [、「Enable-AntiPhishRule および](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) [Disable-AntiPhishRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule)。</span><span class="sxs-lookup"><span data-stu-id="60b19-336">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="60b19-337">PowerShell を使用してフィッシング対策ルールの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="60b19-337">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="60b19-338">ルールに設定できる優先度の最高値値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="60b19-338">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="60b19-339">設定できる最低値はルールの数に依存します。</span><span class="sxs-lookup"><span data-stu-id="60b19-339">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="60b19-340">たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。</span><span class="sxs-lookup"><span data-stu-id="60b19-340">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="60b19-341">既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。</span><span class="sxs-lookup"><span data-stu-id="60b19-341">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="60b19-342">たとえば、カスタム ルールが 5 つあって (優先度 0 から 4)、1 つのルールの優先度を 2 に変更した場合には、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。</span><span class="sxs-lookup"><span data-stu-id="60b19-342">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="60b19-343">PowerShell でフィッシング対策ルールの優先度を設定するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="60b19-343">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="60b19-p137">この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。</span><span class="sxs-lookup"><span data-stu-id="60b19-p137">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="60b19-346">**注**:</span><span class="sxs-lookup"><span data-stu-id="60b19-346">**Notes**:</span></span>

- <span data-ttu-id="60b19-347">新しく作成したルールの優先度を設定するには **、New-AntiPhishRule**コマンドレットの_Priority_パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="60b19-347">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="60b19-348">既定のフィッシング対策ポリシーには対応するフィッシング対策ルールがありません。また、常に、変更不可能な優先順位の **値 Lowest が設定されます**。</span><span class="sxs-lookup"><span data-stu-id="60b19-348">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="60b19-349">PowerShell を使用してフィッシング対策ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="60b19-349">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="60b19-350">PowerShell を使用してフィッシング対策ポリシーを削除した場合、対応するフィッシング対策ルールは削除されません。</span><span class="sxs-lookup"><span data-stu-id="60b19-350">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="60b19-351">PowerShell でフィッシング対策ポリシーを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="60b19-351">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="60b19-352">この例では、Marketing Department という名前のフィッシング対策ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="60b19-352">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="60b19-353">構文およびパラメーターの詳細については [、Remove-AntiPhishPolicy を参照してください](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="60b19-353">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="60b19-354">PowerShell を使用してフィッシング対策ルールを削除する</span><span class="sxs-lookup"><span data-stu-id="60b19-354">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="60b19-355">PowerShell を使用してフィッシング対策ルールを削除した場合、対応するフィッシング対策ポリシーは削除されません。</span><span class="sxs-lookup"><span data-stu-id="60b19-355">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="60b19-356">PowerShell でフィッシング対策ルールを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="60b19-356">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="60b19-357">この例では、Marketing Department という名前のフィッシング対策ルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="60b19-357">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="60b19-358">構文およびパラメーターの詳細については [、Remove-AntiPhishRule を参照してください](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="60b19-358">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="60b19-359">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="60b19-359">How do you know these procedures worked?</span></span>

<span data-ttu-id="60b19-360">ATP フィッシング対策ポリシーが正常に構成されたことを確認するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="60b19-360">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="60b19-361">セキュリティ/コンプライアンス &で、脅威**Threat management**管理 \> **ポリシー** \> **のフィッシング対策に移動します**。</span><span class="sxs-lookup"><span data-stu-id="60b19-361">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="60b19-362">ポリシーの一覧とその Status 値 **および Priority** 値 **を確認** します。</span><span class="sxs-lookup"><span data-stu-id="60b19-362">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="60b19-363">詳細を表示するには、次の手順のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="60b19-363">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="60b19-364">一覧からポリシーを選択して、ポップアップに詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="60b19-364">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="60b19-365">[ **既定] ポリシーを** クリックし、ポップアップに詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="60b19-365">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="60b19-366">Exchange Online PowerShell でポリシーまたは \<Name\> ルールの名前を置き換え、次のコマンドを実行し、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="60b19-366">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
