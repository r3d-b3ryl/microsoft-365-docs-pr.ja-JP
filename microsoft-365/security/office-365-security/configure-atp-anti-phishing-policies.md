---
title: Office 365 の Microsoft Defender でフィッシング対策ポリシーを構成する
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
description: 管理者は、Microsoft Defender for Office 365 を使用して組織で使用できる高度なフィッシング対策ポリシーを作成、変更、および削除する方法を学習できます。
ms.openlocfilehash: ecc68a8dc050a5f08c6982b023861e0ea8976775
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920658"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="6737f-103">Office 365 の Microsoft Defender でフィッシング対策ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="6737f-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6737f-104">[Microsoft Defender For Office 365 の](office-365-atp.md)フィッシング対策ポリシーは、悪意のある偽造ベースのフィッシング攻撃やその他の種類のフィッシング攻撃から組織を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6737f-104">Anti-phishing policies in [Microsoft Defender for Office 365](office-365-atp.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="6737f-105">Office 365 用の Microsoft Defender での Exchange Online Protection (EOP) とフィッシング対策ポリシーの相違点の詳細については、「 [フィッシング対策保護](anti-phishing-protection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6737f-105">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="6737f-106">管理者は、既定のフィッシング対策ポリシーを表示、編集、および構成できます (削除することはできません)。</span><span class="sxs-lookup"><span data-stu-id="6737f-106">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="6737f-107">よりきめ細かく制御する場合は、組織内の特定のユーザー、グループ、またはドメインに適用するカスタムのフィッシング対策ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="6737f-107">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="6737f-108">カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (実行順序) を変更できます。</span><span class="sxs-lookup"><span data-stu-id="6737f-108">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="6737f-109">セキュリティ & コンプライアンスセンターまたは Exchange Online PowerShell で、フィッシング対策ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="6737f-109">You can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="6737f-110">Exchange Online Protection 組織 (つまり、Microsoft Defender for Office 365 を使用していない組織) で利用できるフィッシング対策ポリシーで、より限定されたものを構成する方法については、「 [Configure フィッシング対策ポリシーを EOP で構成](configure-anti-phishing-policies-eop.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6737f-110">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, organizations without Microsoft Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="6737f-111">フィッシング対策ポリシーの基本的な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6737f-111">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="6737f-112">**フィッシングポリシー** : 有効または無効にするフィッシング対策、およびオプションを適用するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="6737f-112">**The anti-phish policy** : Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="6737f-113">**フィッシングルールで** は、フィッシングポリシーの優先順位と受信者フィルター (ポリシーが適用されるユーザー) を指定します。</span><span class="sxs-lookup"><span data-stu-id="6737f-113">**The anti-phish rule** : Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="6737f-114">セキュリティ & コンプライアンスセンターでフィッシング対策ポリシーを管理する場合、この2つの要素の違いは明白ではありません。</span><span class="sxs-lookup"><span data-stu-id="6737f-114">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="6737f-115">ポリシーを作成する場合、実際には、フィッシングルールと関連付けられているフィッシングポリシーを両方に同じ名前を使用して同時に作成しています。</span><span class="sxs-lookup"><span data-stu-id="6737f-115">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="6737f-116">ポリシーを変更する場合、name、priority、enabled または disabled、および recipient フィルターに関連する設定によって、フィッシングルールが変更されます。</span><span class="sxs-lookup"><span data-stu-id="6737f-116">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="6737f-117">他のすべての設定は、関連付けられたフィッシングポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="6737f-117">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="6737f-118">ポリシーを削除すると、フィッシングルールとそれに関連付けられているフィッシングポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="6737f-118">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="6737f-119">Exchange Online の PowerShell では、ポリシーとルールを個別に管理します。</span><span class="sxs-lookup"><span data-stu-id="6737f-119">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="6737f-120">詳細については、このトピックで後述 [する「Microsoft Defender For Office 365 で Exchange Online PowerShell を使用してフィッシング対策ポリシーを構成する](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6737f-120">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) section later in this topic.</span></span>

<span data-ttu-id="6737f-121">すべての Microsoft Defender for Office 365 組織には、Office365 フィッシング対策 Default という名前の組み込みのフィッシング対策ポリシーがあります。これらのプロパティは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6737f-121">Every Microsoft Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="6737f-122">ポリシーに関連付けられているフィッシングルール (受信者フィルター) がない場合でも、ポリシーは組織内のすべての受信者に適用されます。</span><span class="sxs-lookup"><span data-stu-id="6737f-122">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="6737f-123">ポリシーにはカスタムの優先順位の値 **Lowest** が設定されており、変更することはできません (このポリシーは常に最後に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="6737f-123">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="6737f-124">作成するどのカスタム ポリシーも、より高い優先順位を持ちます。</span><span class="sxs-lookup"><span data-stu-id="6737f-124">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="6737f-125">ポリシーは既定のポリシー ( **IsDefault** のプロパティが `True` の値になっている) であり、既定のポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="6737f-125">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="6737f-126">Microsoft Defender for Office 365 のフィッシング対策保護の有効性を高めるために、特定のユーザーまたはユーザーグループに適用される厳密な設定でカスタムのフィッシング対策ポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="6737f-126">To increase the effectiveness of anti-phishing protection in Microsoft Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6737f-127">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="6737f-127">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6737f-128"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="6737f-128">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="6737f-129">**ATP のフィッシング対策** ページに直接移動するには、を使用 <https://protection.office.com/antiphishing> します。</span><span class="sxs-lookup"><span data-stu-id="6737f-129">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="6737f-130">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6737f-130">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="6737f-131">この記事に記載されている手順を実行するには、事前にアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6737f-131">You need to be assigned permissions before you can do the procedures in this article:</span></span>

  - <span data-ttu-id="6737f-132">フィッシング対策ポリシーを追加、変更、および削除するには、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="6737f-132">To add, modify, and delete anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="6737f-133">**組織の管理** または [セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の **セキュリティ管理者** 。</span><span class="sxs-lookup"><span data-stu-id="6737f-133">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="6737f-134">**組織の管理** または [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の **検疫管理** 。</span><span class="sxs-lookup"><span data-stu-id="6737f-134">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="6737f-135">フィッシング対策ポリシーに対する読み取り専用アクセスでは、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="6737f-135">For read-only access to anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="6737f-136">[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の **セキュリティ閲覧者** 。</span><span class="sxs-lookup"><span data-stu-id="6737f-136">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="6737f-137">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の **表示限定の組織管理** 。</span><span class="sxs-lookup"><span data-stu-id="6737f-137">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="6737f-138">Microsoft Defender for Office 365 のフィッシング対策ポリシーの推奨設定については、「 [office 365 設定の defender のフィッシング対策ポリシー](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6737f-138">For our recommended settings for anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="6737f-139">新規または更新されたポリシーが適用されるまで最大30分かかります。</span><span class="sxs-lookup"><span data-stu-id="6737f-139">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="6737f-140">フィルタリングパイプラインにフィッシング対策ポリシーを適用する方法については、「 [メール保護の順序と優先順位](how-policies-and-protections-are-combined.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6737f-140">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="6737f-141">セキュリティ & コンプライアンスセンターを使用して、Microsoft Defender for Office 365 でフィッシング対策ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="6737f-141">Use the Security & Compliance Center to create anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="6737f-142">セキュリティ & コンプライアンスセンターでカスタムのフィッシング対策ポリシーを作成すると、両方に同じ名前を使用して、フィッシングルールと関連付けられているフィッシングポリシーを同時に作成します。</span><span class="sxs-lookup"><span data-stu-id="6737f-142">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="6737f-143">フィッシング対策ポリシーを作成する場合、ポリシー名、説明、およびポリシーの適用先を識別する受信者フィルターのみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6737f-143">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="6737f-144">ポリシーを作成したら、ポリシーを変更して既定のフィッシング対策設定を変更または確認することができます。</span><span class="sxs-lookup"><span data-stu-id="6737f-144">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="6737f-145">セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** \> **ATP のフィッシング対策** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="6737f-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="6737f-146">[ **フィッシング対策** ] ページで、[ **作成** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6737f-146">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="6737f-147">[ **新しいフィッシング対策ポリシーの作成** ] ウィザードが開きます。</span><span class="sxs-lookup"><span data-stu-id="6737f-147">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="6737f-148">[ **ポリシーに名前** をつける] ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="6737f-148">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="6737f-149">**[名前]** : わかりやすい一意のポリシー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="6737f-149">**Name** : Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="6737f-150">**[説明]** : ポリシーについての説明を入力します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="6737f-150">**Description** : Enter an optional description for the policy.</span></span>

   <span data-ttu-id="6737f-151">完了したら、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6737f-151">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="6737f-152">表示される [ **適用先** ] ページで、ポリシーが適用される内部の受信者を特定します。</span><span class="sxs-lookup"><span data-stu-id="6737f-152">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="6737f-153">各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="6737f-153">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="6737f-154">同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、 _\<recipient1\>_ または _\<recipient2\>_ ) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="6737f-154">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_ ).</span></span> <span data-ttu-id="6737f-155">a別の条件や例外がある場合は AND ロジック (たとえば、 _\<recipient1\>_ かつ _\<member of group 1\>_ ) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="6737f-155">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_ ).</span></span>

   <span data-ttu-id="6737f-156">[ **条件の追加] を** クリックします。</span><span class="sxs-lookup"><span data-stu-id="6737f-156">Click **Add a condition**.</span></span> <span data-ttu-id="6737f-157">表示されるドロップダウンで、[適用済みの **場合** ] の条件を選択します。</span><span class="sxs-lookup"><span data-stu-id="6737f-157">In the dropdown that appears, select a condition under **Applied if** :</span></span>

   - <span data-ttu-id="6737f-158">**受信者は** 次のとおりです。組織内で1つ以上のメールボックス、メールユーザー、またはメール連絡先を指定します。</span><span class="sxs-lookup"><span data-stu-id="6737f-158">**The recipient is** : Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="6737f-159">**受信者が次のメンバーの** 場合: 組織内の1つまたは複数のグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="6737f-159">**The recipient is a member of** : Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="6737f-160">**受信者のドメイン** : 構成された1つ以上の承認済みドメインの受信者を組織に指定します。</span><span class="sxs-lookup"><span data-stu-id="6737f-160">**The recipient domain is** : Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="6737f-161">条件を選択すると、対応するドロップ **ダウンボックスが** 表示されます。</span><span class="sxs-lookup"><span data-stu-id="6737f-161">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="6737f-162">ボックス内をクリックし、値の一覧をスクロールして選択します。</span><span class="sxs-lookup"><span data-stu-id="6737f-162">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="6737f-163">ボックス内をクリックして入力を開始し、リストにフィルターを適用して値を選択します。</span><span class="sxs-lookup"><span data-stu-id="6737f-163">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="6737f-164">その他の値を追加するには、ボックスの空の領域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6737f-164">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="6737f-165">個々のエントリを削除するには、その値の [削除] アイコン **をクリックし** ![ ](../../media/scc-remove-icon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="6737f-165">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="6737f-166">条件全体を削除するには、条件の [削除] アイコン **をクリックし** ![ ](../../media/scc-remove-icon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="6737f-166">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="6737f-167">別の条件を追加するには、[ **条件の追加** ] をクリックし、[ **適用** 時] で残りの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="6737f-167">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="6737f-168">例外を追加するには、[ **条件の追加** ] をクリックし、 **Except if** で例外を選択します。</span><span class="sxs-lookup"><span data-stu-id="6737f-168">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="6737f-169">設定と動作は、条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="6737f-169">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="6737f-170">完了したら、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6737f-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="6737f-171">表示される [ **設定の確認** ] ページで、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="6737f-171">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="6737f-172">各設定で [ **編集** ] をクリックして、変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6737f-172">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="6737f-173">完了したら、[ **このポリシーの作成** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6737f-173">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="6737f-174">表示される確認ダイアログで [ **OK** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6737f-174">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="6737f-175">これらの一般的な設定を使用してフィッシング対策ポリシーを作成したら、次のセクションの手順に従って、ポリシーの保護設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="6737f-175">After you create the anti-phishing policy with these general settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="6737f-176">セキュリティ & コンプライアンスセンターを使用して、Microsoft Defender for Office 365 のフィッシング対策ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="6737f-176">Use the Security & Compliance Center to modify anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="6737f-177">次の手順を使用して、作成した新しいポリシー、または既にカスタマイズした既存のポリシーを変更して、フィッシング対策ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="6737f-177">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="6737f-178">まだ存在しない場合は、セキュリティ & コンプライアンスセンターを開き、[ **脅威管理** \> **ポリシー** ] \> **ATP のフィッシング対策** に移動します。</span><span class="sxs-lookup"><span data-stu-id="6737f-178">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="6737f-179">変更するカスタムのフィッシング対策ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="6737f-179">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="6737f-180">既に選択されている場合は、選択を解除してもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="6737f-180">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="6737f-181">[ **ポリシー \<name\> の編集** のポップアップを表示します。</span><span class="sxs-lookup"><span data-stu-id="6737f-181">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="6737f-182">いずれかのセクションで [ **編集** ] をクリックすると、そのセクションの設定にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6737f-182">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="6737f-183">次の手順は、セクションが表示される順序で示されていますが、連続していません (任意の順序でセクションを選択して変更することができます)。</span><span class="sxs-lookup"><span data-stu-id="6737f-183">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="6737f-184">セクションで [ **編集** ] をクリックすると、使用可能な設定がウィザード形式で表示されますが、ページ内を任意の順序で移動できます。または、[すべての **Close** ページに **保存** **] を** クリックして ![ 、[ ](../../media/scc-remove-icon.png) **ポリシー \<name\> の編集** ] ページに戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="6737f-184">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="6737f-185">**ポリシー設定** : [ **編集** ] をクリックして、前のセクションで [ポリシーを作成](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) したときに使用したものと同じ設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="6737f-185">**Policy setting** : Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) in the previous section:</span></span>

   - <span data-ttu-id="6737f-186">**名前**</span><span class="sxs-lookup"><span data-stu-id="6737f-186">**Name**</span></span>
   - <span data-ttu-id="6737f-187">**説明**</span><span class="sxs-lookup"><span data-stu-id="6737f-187">**Description**</span></span>
   - <span data-ttu-id="6737f-188">**適用先**</span><span class="sxs-lookup"><span data-stu-id="6737f-188">**Applied to**</span></span>
   - <span data-ttu-id="6737f-189">**設定を確認する**</span><span class="sxs-lookup"><span data-stu-id="6737f-189">**Review your settings**</span></span>

   <span data-ttu-id="6737f-190">完了したら、[任意のページに **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6737f-190">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="6737f-191">**偽装** : [ **編集** ] をクリックして、ポリシー内の保護された送信者と保護されたドメインを変更します。</span><span class="sxs-lookup"><span data-stu-id="6737f-191">**Impersonation** : Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="6737f-192">これらの設定は、受信メッセージの From アドレスで (個別またはドメインによって) 検索するスプーフィングされた送信者を識別するポリシーの条件です。</span><span class="sxs-lookup"><span data-stu-id="6737f-192">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="6737f-193">詳細については、「 [Microsoft Defender のフィッシング対策ポリシーの偽装設定 (Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6737f-193">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="6737f-194">**保護するユーザーを追加する** : 既定値は **Off** です。</span><span class="sxs-lookup"><span data-stu-id="6737f-194">**Add users to protect** : The default value is **Off**.</span></span> <span data-ttu-id="6737f-195">これをオンにするには、トグルを **[オン** ] にして、表示される [ **ユーザーの追加** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6737f-195">To turn it on, slide the toggle to **On** , and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="6737f-196">[ **ユーザーの追加** ] ポップアップが表示されたら、次の値を構成します。</span><span class="sxs-lookup"><span data-stu-id="6737f-196">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="6737f-197">**メールアドレス** :</span><span class="sxs-lookup"><span data-stu-id="6737f-197">**Email address** :</span></span>

       - <span data-ttu-id="6737f-198">ボックス内をクリックし、ユーザーの一覧をスクロールして選択します。</span><span class="sxs-lookup"><span data-stu-id="6737f-198">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="6737f-199">ボックス内をクリックして入力を開始し、リストにフィルターを適用してユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="6737f-199">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="6737f-200">エントリを削除するには、ユーザーの [削除] アイコン **をクリックし** ![ ](../../media/scc-remove-icon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="6737f-200">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="6737f-201">**Name** : この値は、選択したメールアドレスに基づいて設定されますが、変更することができます。</span><span class="sxs-lookup"><span data-stu-id="6737f-201">**Name** : This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="6737f-202">完了したら、[任意のページに **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6737f-202">When you're finished, click **Save** on any page.</span></span>

     <span data-ttu-id="6737f-203">既存のエントリを編集するには、一覧で保護されたユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="6737f-203">To edit an existing entry, select the protected user in the list.</span></span>

     > [!NOTE]
     > <span data-ttu-id="6737f-204">すべてのフィッシング対策ポリシーには、最大60ユーザーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="6737f-204">You can have a maximum of 60 users in all anti-phishing policies.</span></span> <span data-ttu-id="6737f-205">言い換えると、60で保護されたユーザーを1つのポリシー、12のポリシーで保護されたユーザー5人に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6737f-205">In other words, you can have 60 protected users in one policy, 12 protected users in 5 policies, etc.</span></span>

   - <span data-ttu-id="6737f-206">**保護するドメインを追加する** : 次の設定の1つまたは両方を構成します。</span><span class="sxs-lookup"><span data-stu-id="6737f-206">**Add domains to protect** : Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="6737f-207">**自分が所有するドメインを自動的に追加** する: 既定値は **Off** です。</span><span class="sxs-lookup"><span data-stu-id="6737f-207">**Automatically include the domains I own** : The default value is **Off**.</span></span> <span data-ttu-id="6737f-208">これをオンにするには、トグルを **[オン** ] にします。</span><span class="sxs-lookup"><span data-stu-id="6737f-208">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="6737f-209">**カスタムドメインを含める** : 既定値は **Off** です。</span><span class="sxs-lookup"><span data-stu-id="6737f-209">**Include custom domains** : The default value is **Off**.</span></span> <span data-ttu-id="6737f-210">これをオンにするには、トグルを **[オン** ] にして、[ **ドメインの追加** ] ボックスにドメイン名 (contoso.com など) を入力し、enter キーを押して、必要に応じて繰り返します。</span><span class="sxs-lookup"><span data-stu-id="6737f-210">To turn it on, slide the toggle to **On** , and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

     > [!NOTE]
     > <span data-ttu-id="6737f-211">すべてのフィッシング対策ポリシーには、最大で50のドメインを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="6737f-211">You can have a maximum of 50 domains in all anti-phishing policies.</span></span> <span data-ttu-id="6737f-212">言い換えると、50で保護されたユーザーを1つのポリシーに、保護されたユーザーを5人にすることができます。</span><span class="sxs-lookup"><span data-stu-id="6737f-212">In other words, you can have 50 protected users in one policy, 10 protected users in 5 policies, etc.</span></span>

   - <span data-ttu-id="6737f-213">**アクション** : [ **編集** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6737f-213">**Actions** : Click **Edit**</span></span>

     - <span data-ttu-id="6737f-214">**偽装ユーザーによって電子メールが送信** される場合: スプーフィングされた送信者が、[ **保護するユーザーの追加** ] で指定した保護されたユーザーのいずれかであるメッセージに対して、次のいずれかのアクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="6737f-214">**If email is sent by an impersonated user** : Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect** :</span></span>

       - <span data-ttu-id="6737f-215">**どの操作も適用しない**</span><span class="sxs-lookup"><span data-stu-id="6737f-215">**Don't apply any action**</span></span>
       - <span data-ttu-id="6737f-216">**他の電子メールアドレスへのメッセージのリダイレクト**</span><span class="sxs-lookup"><span data-stu-id="6737f-216">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="6737f-217">**迷惑メールフォルダーにメッセージを移動する**</span><span class="sxs-lookup"><span data-stu-id="6737f-217">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="6737f-218">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="6737f-218">**Quarantine the message**</span></span>
       - <span data-ttu-id="6737f-219">**メッセージを配信し、その他のアドレスを Bcc 行に追加する**</span><span class="sxs-lookup"><span data-stu-id="6737f-219">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="6737f-220">**配信前にメッセージを削除する**</span><span class="sxs-lookup"><span data-stu-id="6737f-220">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="6737f-221">**偽装ドメインによって電子メールが送信** される場合: スプーフィングされた送信者が、 **保護するドメインの追加** で指定した保護されたドメインのいずれかにあるメッセージに対して、次のいずれかのアクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="6737f-221">**If email is sent by an impersonated domain** : Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect** :</span></span>

       - <span data-ttu-id="6737f-222">**どの操作も適用しない**</span><span class="sxs-lookup"><span data-stu-id="6737f-222">**Don't apply any action**</span></span>
       - <span data-ttu-id="6737f-223">**他の電子メールアドレスへのメッセージのリダイレクト**</span><span class="sxs-lookup"><span data-stu-id="6737f-223">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="6737f-224">**迷惑メールフォルダーにメッセージを移動する**</span><span class="sxs-lookup"><span data-stu-id="6737f-224">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="6737f-225">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="6737f-225">**Quarantine the message**</span></span>
       - <span data-ttu-id="6737f-226">**メッセージを配信し、その他のアドレスを Bcc 行に追加する**</span><span class="sxs-lookup"><span data-stu-id="6737f-226">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="6737f-227">**配信前にメッセージを削除する**</span><span class="sxs-lookup"><span data-stu-id="6737f-227">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="6737f-228">[ **偽装の安全性のヒントを有効にする** ] をクリックし、次のいずれかの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="6737f-228">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="6737f-229">**偽装ユーザーのヒントを表示する** : 既定値は **Off** です。</span><span class="sxs-lookup"><span data-stu-id="6737f-229">**Show tip for impersonated users** : The default value is **Off**.</span></span> <span data-ttu-id="6737f-230">これをオンにするには、トグルを **[オン** ] にします。</span><span class="sxs-lookup"><span data-stu-id="6737f-230">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="6737f-231">**偽装ドメインのヒントを表示する** : 既定値は **Off** です。</span><span class="sxs-lookup"><span data-stu-id="6737f-231">**Show tip for impersonated domains** : The default value is **Off**.</span></span> <span data-ttu-id="6737f-232">これをオンにするには、トグルを **[オン** ] にします。</span><span class="sxs-lookup"><span data-stu-id="6737f-232">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="6737f-233">**通常の文字にヒントを表示** する: 既定値は **Off** です。</span><span class="sxs-lookup"><span data-stu-id="6737f-233">**Show tip for unusual characters** : The default value is **Off**.</span></span> <span data-ttu-id="6737f-234">これをオンにするには、トグルを **[オン** ] にします。</span><span class="sxs-lookup"><span data-stu-id="6737f-234">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="6737f-235">完了したら、 **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6737f-235">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="6737f-236">**メールボックスインテリジェンス** :</span><span class="sxs-lookup"><span data-stu-id="6737f-236">**Mailbox intelligence** :</span></span>

     - <span data-ttu-id="6737f-237">**メールボックスインテリジェンスを有効に** しますか。既定値は **[オン** ] です。</span><span class="sxs-lookup"><span data-stu-id="6737f-237">**Enable mailbox intelligence?** : The default value is **On**.</span></span> <span data-ttu-id="6737f-238">この機能をオフにするには、トグルを [ **オフ** ] にします。</span><span class="sxs-lookup"><span data-stu-id="6737f-238">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="6737f-239">**[\*\*\*\*メールボックスインテリジェンスベースの偽装保護を有効にする]** : この設定は、 **メールボックスインテリジェンスを有効にする** 場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6737f-239">**Enable mailbox intelligence based impersonation protection?** : This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="6737f-240">で **偽装ユーザーによって電子メールが送信** された場合は、メールボックスインテリジェンスに失敗したメッセージに対して次のいずれかの操作を行うことができます (保護されたユーザーと保護されたドメインに対して使用可能なものと同じもの)。</span><span class="sxs-lookup"><span data-stu-id="6737f-240">In **If email is sent by an impersonated user** , you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="6737f-241">**どの操作も適用しない**</span><span class="sxs-lookup"><span data-stu-id="6737f-241">**Don't apply any action**</span></span>
       - <span data-ttu-id="6737f-242">**他の電子メールアドレスへのメッセージのリダイレクト**</span><span class="sxs-lookup"><span data-stu-id="6737f-242">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="6737f-243">**迷惑メールフォルダーにメッセージを移動する**</span><span class="sxs-lookup"><span data-stu-id="6737f-243">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="6737f-244">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="6737f-244">**Quarantine the message**</span></span>
       - <span data-ttu-id="6737f-245">**メッセージを配信し、その他のアドレスを Bcc 行に追加する**</span><span class="sxs-lookup"><span data-stu-id="6737f-245">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="6737f-246">**配信前にメッセージを削除する**</span><span class="sxs-lookup"><span data-stu-id="6737f-246">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="6737f-247">**信頼できる差出人とドメインを追加** する: ポリシーの例外を指定します。</span><span class="sxs-lookup"><span data-stu-id="6737f-247">**Add trusted senders and domains** : Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="6737f-248">**信頼できる送信者** :</span><span class="sxs-lookup"><span data-stu-id="6737f-248">**Trusted senders** :</span></span>

       - <span data-ttu-id="6737f-249">ボックス内をクリックし、ユーザーの一覧をスクロールして選択します。</span><span class="sxs-lookup"><span data-stu-id="6737f-249">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="6737f-250">ボックス内をクリックして入力を開始し、リストにフィルターを適用してユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="6737f-250">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="6737f-251">エントリを削除するには、ユーザーの [削除] アイコン **をクリックし** ![ ](../../media/scc-remove-icon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="6737f-251">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="6737f-252">[ **信頼されたドメイン** ]: ドメイン名 (たとえば、contoso.com) を入力し、enter キーを押して、必要に応じて繰り返します。</span><span class="sxs-lookup"><span data-stu-id="6737f-252">**Trusted domains** : Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="6737f-253">**設定を確認** します。個々の手順をクリックする代わりに、設定が概要で表示されます。</span><span class="sxs-lookup"><span data-stu-id="6737f-253">**Review your settings** : Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="6737f-254">各セクションで [ **編集** ] をクリックすると、関連するページに戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="6737f-254">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="6737f-255">このページでは、次の設定の **オン** と **オフ** を直接切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="6737f-255">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="6737f-256">**保護されたユーザー**</span><span class="sxs-lookup"><span data-stu-id="6737f-256">**Protected users**</span></span>
       - <span data-ttu-id="6737f-257">**保護されたドメイン** \>**所有** しているドメインを含める</span><span class="sxs-lookup"><span data-stu-id="6737f-257">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="6737f-258">**保護されたドメイン** \>**保護されたドメイン** (カスタムドメイン)</span><span class="sxs-lookup"><span data-stu-id="6737f-258">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="6737f-259">**メールボックス インテリジェンス**</span><span class="sxs-lookup"><span data-stu-id="6737f-259">**Mailbox intelligence**</span></span>

   <span data-ttu-id="6737f-260">完了したら、[任意のページに **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6737f-260">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="6737f-261">**スプーフィング** : [ **編集** ] をクリックして、スプーフィングインテリジェンスを有効または無効にしたり、Outlook で認証されていない送信者の識別をオンまたはオフにしたり、ブロックされたスプーフィングされた送信者からのメッセージに適用するアクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="6737f-261">**Spoof** : Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="6737f-262">詳細については、「 [フィッシング対策ポリシーのスプーフィング設定](set-up-anti-phishing-policies.md#spoof-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6737f-262">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="6737f-263">なお、これらの設定は EOP のフィッシング対策ポリシーでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="6737f-263">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="6737f-264">**フィルター設定のスプーフィング** : 既定値は **on** で、そのままにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6737f-264">**Spoofing filter settings** : The default value is **On** , and we recommend that you leave it on.</span></span> <span data-ttu-id="6737f-265">この機能をオフにするには、トグルを [ **オフ** ] にします。</span><span class="sxs-lookup"><span data-stu-id="6737f-265">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="6737f-266">詳細については、「 [Configure スプーフ知能 IN EOP」](learn-about-spoof-intelligence.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6737f-266">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="6737f-267">MX レコードが Microsoft 365 をポイントしていない場合は、スプーフィング防止保護を無効にする必要はありません。代わりに、コネクタの拡張フィルターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6737f-267">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="6737f-268">手順については、「 [Exchange Online のコネクタの拡張フィルター処理](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6737f-268">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="6737f-269">[認証されていない **送信者の機能を有効にする** ]: 既定値は **[オン** ] です。</span><span class="sxs-lookup"><span data-stu-id="6737f-269">**Enable Unauthenticated Sender feature** : The default value is **On**.</span></span> <span data-ttu-id="6737f-270">この機能をオフにするには、トグルを [ **オフ** ] にします。</span><span class="sxs-lookup"><span data-stu-id="6737f-270">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="6737f-271">**アクション** : スプーフィングインテリジェンスに失敗したメッセージに対して実行するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="6737f-271">**Actions** : Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="6737f-272">**ドメインのスプーフィングが許可されていないユーザーによって電子メールが送信** される場合:</span><span class="sxs-lookup"><span data-stu-id="6737f-272">**If email is sent by someone who's not allowed to spoof your domain** :</span></span>

     - <span data-ttu-id="6737f-273">**受信者の迷惑メールフォルダーにメッセージを移動する**</span><span class="sxs-lookup"><span data-stu-id="6737f-273">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="6737f-274">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="6737f-274">**Quarantine the message**</span></span>

   - <span data-ttu-id="6737f-275">**設定を確認** します。個々の手順をクリックする代わりに、設定が概要で表示されます。</span><span class="sxs-lookup"><span data-stu-id="6737f-275">**Review your settings** : Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="6737f-276">各セクションで [ **編集** ] をクリックすると、関連するページに戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="6737f-276">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="6737f-277">このページでは、次の設定の **オン** と **オフ** を直接切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="6737f-277">You can toggle the following settings **On** or **Off** directly on this page:</span></span>
       - <span data-ttu-id="6737f-278">**スプーフィング対策保護を有効にする**</span><span class="sxs-lookup"><span data-stu-id="6737f-278">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="6737f-279">**認証されていない送信者機能を有効にする**</span><span class="sxs-lookup"><span data-stu-id="6737f-279">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="6737f-280">完了したら、[任意のページに **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6737f-280">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="6737f-281">**詳細設定** : [ **編集** ] をクリックして、詳細なフィッシングしきい値を構成します。</span><span class="sxs-lookup"><span data-stu-id="6737f-281">**Advanced settings** : Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="6737f-282">詳細については、「 [Microsoft Defender 365 のフィッシング対策ポリシーの高度なフィッシングのしきい値](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6737f-282">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="6737f-283">**[Advanced フィッシングしきい** 値]: 次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="6737f-283">**Advanced phishing thresholds** : Select one of the following values:</span></span>

   - <span data-ttu-id="6737f-284">**1-標準** (これは既定値です)</span><span class="sxs-lookup"><span data-stu-id="6737f-284">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="6737f-285">**2-アグレッシブ**</span><span class="sxs-lookup"><span data-stu-id="6737f-285">**2 - Aggressive**</span></span>
   - <span data-ttu-id="6737f-286">**3つ以上のアグレッシブ**</span><span class="sxs-lookup"><span data-stu-id="6737f-286">**3 - More aggressive**</span></span>
   - <span data-ttu-id="6737f-287">**4-最も積極的**</span><span class="sxs-lookup"><span data-stu-id="6737f-287">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="6737f-288">**設定を確認** します。 [ **編集** ] をクリックすると、[ **詳細なフィッシングのしきい値** ] ページに戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="6737f-288">**Review your settings** : Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="6737f-289">完了したら、[どちらかのページで **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6737f-289">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="6737f-290">[ **ポリシー \<Name\> の編集** ] ページに戻り、設定を確認してから、[ **閉じる** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6737f-290">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a><span data-ttu-id="6737f-291">セキュリティ & コンプライアンスセンターを使用して、Microsoft Defender for Office 365 の既定のフィッシング対策ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="6737f-291">Use the Security & Compliance Center to modify the default anti-phishing policy in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="6737f-292">Microsoft Defender for Office 365 の既定のフィッシング対策ポリシーは、Office365 フィッシング対策 Default という名前で、ポリシーの一覧には表示されません。</span><span class="sxs-lookup"><span data-stu-id="6737f-292">The default anti-phishing policy in Microsoft Defender for Office 365 is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="6737f-293">既定のフィッシング対策ポリシーを変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6737f-293">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="6737f-294">セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** \> **ATP のフィッシング対策** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="6737f-294">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="6737f-295">[ **フィッシング対策** ] ページで、[ **既定のポリシー** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6737f-295">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="6737f-296">[ **ポリシーの Office 365 フィッシング対策の既定の編集** ] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6737f-296">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="6737f-297">次のセクションを使用できます。これには、 [カスタムポリシーを変更](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365)するときに、同一の設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6737f-297">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span></span>

   - <span data-ttu-id="6737f-298">**偽装**</span><span class="sxs-lookup"><span data-stu-id="6737f-298">**Impersonation**</span></span>
   - <span data-ttu-id="6737f-299">**なりすます**</span><span class="sxs-lookup"><span data-stu-id="6737f-299">**Spoof**</span></span>
   - <span data-ttu-id="6737f-300">**詳細設定**</span><span class="sxs-lookup"><span data-stu-id="6737f-300">**Advanced settings**</span></span>

   <span data-ttu-id="6737f-301">次の設定は、既定のポリシーを変更するときには使用できません。</span><span class="sxs-lookup"><span data-stu-id="6737f-301">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="6737f-302">**ポリシー設定** のセクションと値は表示できますが、 **編集** リンクはありません。そのため、設定 (ポリシー名、説明、ポリシーの適用先 (すべての受信者に適用)) を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="6737f-302">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="6737f-303">既定のポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="6737f-303">You can't delete the default policy.</span></span>
   - <span data-ttu-id="6737f-304">既定のポリシーの優先度を変更することはできません (常に最後に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="6737f-304">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="6737f-305">[ **Policy The Office365 フィッシング対策 Default** ] ページで、設定を確認し、[ **閉じる** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6737f-305">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="6737f-306">Office 365 の Microsoft Defender でカスタムのフィッシング対策ポリシーを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="6737f-306">Enable or disable custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="6737f-307">セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** \> **ATP のフィッシング対策** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="6737f-307">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="6737f-308">[ **状態** ] 列の値に注目してください。</span><span class="sxs-lookup"><span data-stu-id="6737f-308">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="6737f-309">トグルを [ **オフ** ] にして、ポリシーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="6737f-309">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="6737f-310">トグルに切り替えて、 **ポリシーを有効** にします。</span><span class="sxs-lookup"><span data-stu-id="6737f-310">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="6737f-311">既定のフィッシング対策ポリシーを無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="6737f-311">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="6737f-312">Office 365 の Microsoft Defender でカスタムのフィッシング対策ポリシーの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="6737f-312">Set the priority of custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="6737f-313">既定では、フィッシング対策ポリシーには、作成された順序に基づく優先度が与えられます (新しいポリシーは、以前のポリシーよりも優先度が低いです)。</span><span class="sxs-lookup"><span data-stu-id="6737f-313">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="6737f-314">優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。</span><span class="sxs-lookup"><span data-stu-id="6737f-314">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="6737f-315">2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。</span><span class="sxs-lookup"><span data-stu-id="6737f-315">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="6737f-316">優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6737f-316">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="6737f-317">カスタムのフィッシング対策ポリシーは、処理順に表示されます (最初のポリシーの **優先度** 値は0です)。</span><span class="sxs-lookup"><span data-stu-id="6737f-317">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="6737f-318">Office365 フィッシング対策 Default という既定のフィッシング対策ポリシーは、カスタムの優先度の値を **最小** にし、それを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="6737f-318">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest** , and you can't change it.</span></span>

 <span data-ttu-id="6737f-319">**注** : セキュリティ & コンプライアンスセンターでは、作成後に、フィッシング対策ポリシーの優先度のみを変更できます。</span><span class="sxs-lookup"><span data-stu-id="6737f-319">**Note** : In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="6737f-320">PowerShell では、フィッシングルールを作成するときに既定の優先順位を上書きできます (既存のルールの優先度に影響する場合があります)。</span><span class="sxs-lookup"><span data-stu-id="6737f-320">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="6737f-321">ポリシーの優先度を変更するには、ポリシーのプロパティで [ **優先度を上げる** ] または [ **優先度を下げる** ] をクリックします (セキュリティ & コンプライアンスセンターで **優先度** を直接変更することはできません)。</span><span class="sxs-lookup"><span data-stu-id="6737f-321">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="6737f-322">ポリシーの優先度を変更することは、複数のポリシーがある場合にのみ有効になります。</span><span class="sxs-lookup"><span data-stu-id="6737f-322">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="6737f-323">セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** \> **ATP のフィッシング対策** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="6737f-323">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="6737f-324">変更するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="6737f-324">Select the policy that you want to modify.</span></span> <span data-ttu-id="6737f-325">既に選択されている場合は、選択を解除してもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="6737f-325">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="6737f-326">[ **ポリシー \<name\> の編集** のポップアップを表示します。</span><span class="sxs-lookup"><span data-stu-id="6737f-326">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="6737f-327">**優先度** の値が **0** のカスタムのフィッシング対策ポリシーでは、[ **優先度を下げる** ] ボタンのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6737f-327">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="6737f-328">最も低い **優先度** の値 (たとえば **3** ) を持つカスタムのフィッシング対策ポリシーでは、[ **優先度を上げる** ] ボタンのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6737f-328">The custom anti-phishing policy with the lowest **Priority** value (for example, **3** ) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="6737f-329">3つ以上のカスタムのマルウェア対策ポリシーを所有している場合、最高の優先度と最も低い優先度の値の間のポリシーでは、[優先度を **上げる** ] ボタンと [ **優先度を下げる** ] ボタンの両方を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6737f-329">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="6737f-330">[優先 **度を上げる** ] または [ **優先度を下げる** ] をクリックし、 **優先度** の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="6737f-330">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="6737f-331">完了したら、 **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6737f-331">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="6737f-332">セキュリティ & コンプライアンスセンターを使用して、Microsoft Defender for Office 365 のフィッシング対策ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="6737f-332">Use the Security & Compliance Center to view anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="6737f-333">[セキュリティ & コンプライアンスセンター] で、[ **脅威管理** \> **ポリシー** \> **ATP のフィッシング対策** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="6737f-333">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="6737f-334">次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6737f-334">Do one of the following steps:</span></span>

   - <span data-ttu-id="6737f-335">表示するカスタムのフィッシング対策ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="6737f-335">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="6737f-336">既に選択されている場合は、選択を解除してもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="6737f-336">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="6737f-337">[ **既定のポリシー** ] をクリックして、既定のフィッシング対策ポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="6737f-337">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="6737f-338">[ **ポリシー \<name\> の編集** ] ポップアップが表示され、設定と値を表示できます。</span><span class="sxs-lookup"><span data-stu-id="6737f-338">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="6737f-339">セキュリティ & コンプライアンスセンターを使用して、Microsoft Defender for Office 365 のフィッシング対策ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="6737f-339">Use the Security & Compliance Center to remove anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="6737f-340">セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** \> **ATP のフィッシング対策** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="6737f-340">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="6737f-341">削除するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="6737f-341">Select the policy that you want to remove.</span></span> <span data-ttu-id="6737f-342">既に選択されている場合は、選択を解除してもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="6737f-342">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="6737f-343">表示される [ **ポリシー \<name\> の編集** ] ポップアップで、[ **ポリシーの削除** ] をクリックし、表示される警告ダイアログボックスで [ **はい** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6737f-343">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy** , and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="6737f-344">既定のポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="6737f-344">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="6737f-345">Exchange Online PowerShell を使用して Microsoft Defender for Office 365 でフィッシング対策ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="6737f-345">Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="6737f-346">前述したように、スパム対策ポリシーは、フィッシングポリシーとフィッシングルールで構成されています。</span><span class="sxs-lookup"><span data-stu-id="6737f-346">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="6737f-347">Exchange Online PowerShell では、フィッシングポリシーとフィッシングルールの違いが明らかです。</span><span class="sxs-lookup"><span data-stu-id="6737f-347">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="6737f-348">フィッシングポリシーを管理するには、 **\* -get-antiphishpolicy** コマンドレットを使用して、 **\* -new-antiphishrule** コマンドレットを使用してフィッシングルールを管理します。</span><span class="sxs-lookup"><span data-stu-id="6737f-348">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="6737f-349">PowerShell では、フィッシングポリシーを最初に作成してから、ルールが適用されるポリシーを識別するフィッシングルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="6737f-349">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="6737f-350">PowerShell では、フィッシングポリシーおよびフィッシングルールの設定を個別に変更します。</span><span class="sxs-lookup"><span data-stu-id="6737f-350">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="6737f-351">PowerShell からフィッシングポリシーを削除すると、対応するフィッシングルールは自動的に削除されず、その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="6737f-351">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="6737f-352">PowerShell を使用してフィッシング対策ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="6737f-352">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="6737f-353">PowerShell でのフィッシング対策ポリシーの作成は、次の2つの手順からなるプロセスです。</span><span class="sxs-lookup"><span data-stu-id="6737f-353">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="6737f-354">フィッシングポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="6737f-354">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="6737f-355">ルールが適用されるフィッシングポリシーを指定するフィッシングルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="6737f-355">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="6737f-356">**注** :</span><span class="sxs-lookup"><span data-stu-id="6737f-356">**Notes** :</span></span>

- <span data-ttu-id="6737f-357">新しいフィッシングルールを作成し、関連付けられていない既存のアンチフィッシングポリシーをそのルールに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6737f-357">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="6737f-358">フィッシングルールは、複数のフィッシングポリシーに関連付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="6737f-358">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="6737f-359">次の設定は、ポリシーを作成するまではセキュリティ & コンプライアンスセンターでは使用できない PowerShell の新しいフィッシングポリシーで構成できます。</span><span class="sxs-lookup"><span data-stu-id="6737f-359">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="6737f-360">新しいポリシーを無効として _Enabled_ 作成し `$false` ます ( **new-antiphishrule** コマンドレットでは有効)。</span><span class="sxs-lookup"><span data-stu-id="6737f-360">Create the new policy as disabled ( _Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="6737f-361">New-antiphishrule コマンドレットで、作成中にポリシーの優先度を設定します ( _優先度_ _\<Number\>_ )。 **New-AntiPhishRule**</span><span class="sxs-lookup"><span data-stu-id="6737f-361">Set the priority of the policy during creation ( _Priority_ _\<Number\>_ ) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="6737f-362">PowerShell で作成した新しいフィッシングポリシーは、ポリシーをフィッシングルールに割り当てるまで、セキュリティ & コンプライアンスセンターに表示されません。</span><span class="sxs-lookup"><span data-stu-id="6737f-362">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="6737f-363">手順 1: PowerShell を使用してフィッシングポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="6737f-363">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="6737f-364">フィッシングポリシーを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="6737f-364">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="6737f-365">この例では、次の設定を使用して Research Quarantine という名前のフィッシングポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="6737f-365">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="6737f-366">このポリシーは有効になっています ( _enabled_ パラメーターは使用していません。既定値はです `$true` )。</span><span class="sxs-lookup"><span data-stu-id="6737f-366">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="6737f-367">説明は、「研究部門のポリシー」です。</span><span class="sxs-lookup"><span data-stu-id="6737f-367">The description is: Research department policy.</span></span>
- <span data-ttu-id="6737f-368">すべての承認済みドメインに対する組織ドメインの保護と、fabrikam.com の対象となるドメインの保護を有効にします。</span><span class="sxs-lookup"><span data-stu-id="6737f-368">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="6737f-369">偽装から保護するユーザーとして Mai Fujito (mfujito@fabrikam.com) を指定します。</span><span class="sxs-lookup"><span data-stu-id="6737f-369">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="6737f-370">メールボックスのインテリジェンスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6737f-370">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="6737f-371">メールボックスインテリジェンス保護を有効にし、検疫アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="6737f-371">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="6737f-372">安全のヒントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6737f-372">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="6737f-373">構文およびパラメーターの詳細については、「 [get-antiphishpolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6737f-373">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="6737f-374">手順 2: PowerShell を使用してフィッシングルールを作成する</span><span class="sxs-lookup"><span data-stu-id="6737f-374">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="6737f-375">フィッシングルールを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="6737f-375">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="6737f-376">この例では、次の条件を使用して Research Department という名前のフィッシングルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="6737f-376">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="6737f-377">ルールは、Research Quarantine という名前のフィッシングポリシーに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="6737f-377">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="6737f-378">ルールは Research Department という名前のグループのメンバーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="6737f-378">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="6737f-379">_Priority_ パラメーターを使用していないので、既定の優先度が使用されます。</span><span class="sxs-lookup"><span data-stu-id="6737f-379">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="6737f-380">構文およびパラメーターの詳細については、「 [new-antiphishrule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6737f-380">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="6737f-381">PowerShell を使用してフィッシングのポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="6737f-381">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="6737f-382">既存のフィッシングポリシーを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="6737f-382">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="6737f-383">この例では、指定されたプロパティと共にすべてのフィッシングポリシーの要約リストを返します。</span><span class="sxs-lookup"><span data-stu-id="6737f-383">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="6737f-384">この例では、"重役" という名前のフィッシングポリシーのすべてのプロパティ値を返します。</span><span class="sxs-lookup"><span data-stu-id="6737f-384">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="6737f-385">構文およびパラメーターの詳細については、「 [get-antiphishpolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6737f-385">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="6737f-386">PowerShell を使用してフィッシングのルールを表示する</span><span class="sxs-lookup"><span data-stu-id="6737f-386">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="6737f-387">既存のフィッシングルールを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="6737f-387">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="6737f-388">この例では、指定したプロパティと共に、フィッシングのすべてのルールの要約リストを返します。</span><span class="sxs-lookup"><span data-stu-id="6737f-388">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="6737f-389">ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6737f-389">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="6737f-390">この例では、Contoso 重役という名前のフィッシングルールのすべてのプロパティ値を返します。</span><span class="sxs-lookup"><span data-stu-id="6737f-390">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="6737f-391">構文およびパラメーターの詳細については、「 [new-antiphishrule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6737f-391">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="6737f-392">PowerShell を使用してフィッシングポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="6737f-392">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="6737f-393">このトピックで前述したように、「 [手順 1: powershell を使用してフィッシングポリシーを作成する](#step-1-use-powershell-to-create-an-anti-phish-policy) 」で説明されているように、ポリシーの作成時に powershell のフィッシングポリシーを変更する場合は、次の項目以外にも同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6737f-393">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="6737f-394">指定されたポリシーを既定のポリシー (すべてのユーザーに適用して、常に **最下位** の優先度を適用し、削除することはできません) に変更する _makedefault_ スイッチは、PowerShell のフィッシングポリシーを変更する場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6737f-394">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="6737f-395">フィッシングポリシーの名前を変更することはできません ( **get-antiphishpolicy** コマンドレットには _Name_ パラメーターがありません)。</span><span class="sxs-lookup"><span data-stu-id="6737f-395">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="6737f-396">セキュリティ & コンプライアンスセンターでフィッシング対策ポリシーの名前を変更する場合、フィッシング _ルール_ の名前のみを変更しています。</span><span class="sxs-lookup"><span data-stu-id="6737f-396">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="6737f-397">フィッシングポリシーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="6737f-397">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="6737f-398">構文およびパラメーターの詳細については、「 [get-antiphishpolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6737f-398">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="6737f-399">PowerShell を使用してフィッシングルールを変更する</span><span class="sxs-lookup"><span data-stu-id="6737f-399">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="6737f-400">PowerShell でフィッシングルールを変更するときには使用できない唯一の設定は、無効にされたルールを作成できる _有効_ なパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="6737f-400">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="6737f-401">既存のフィッシングルールを有効または無効にするには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6737f-401">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="6737f-402">それ以外の場合は、PowerShell でフィッシングルールを変更しても、追加の設定は使用できません。</span><span class="sxs-lookup"><span data-stu-id="6737f-402">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="6737f-403">このトピックで前述した「 [手順 2: PowerShell を使用してフィッシングルールを作成する](#step-2-use-powershell-to-create-an-anti-phish-rule) 」で説明されているように、ルールを作成する場合にも同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6737f-403">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="6737f-404">フィッシングルールを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="6737f-404">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="6737f-405">構文およびパラメーターの詳細については、「 [new-antiphishrule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6737f-405">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="6737f-406">PowerShell を使用してフィッシングルールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="6737f-406">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="6737f-407">PowerShell でフィッシングルールを有効または無効にすると、フィッシング対策ポリシー全体 (フィッシングルールおよび割り当てられたフィッシングポリシー) が有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="6737f-407">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="6737f-408">既定のフィッシング対策ポリシーを有効または無効にすることはできません (常にすべての受信者に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="6737f-408">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="6737f-409">PowerShell でフィッシングルールを有効または無効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="6737f-409">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="6737f-410">この例では、Marketing Department という名前のフィッシングルールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="6737f-410">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="6737f-411">この例では、同じルールを有効化します。</span><span class="sxs-lookup"><span data-stu-id="6737f-411">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="6737f-412">構文およびパラメーターの詳細については、「 [new-antiphishrule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) 」および「 [Disable-new-antiphishrule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6737f-412">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="6737f-413">PowerShell を使用してフィッシングルールの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="6737f-413">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="6737f-414">ルールに設定できる優先度の最高値値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="6737f-414">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="6737f-415">設定できる最低値はルールの数に依存します。</span><span class="sxs-lookup"><span data-stu-id="6737f-415">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="6737f-416">たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。</span><span class="sxs-lookup"><span data-stu-id="6737f-416">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="6737f-417">既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。</span><span class="sxs-lookup"><span data-stu-id="6737f-417">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="6737f-418">たとえば、カスタム ルールが 5 つあって (優先度 0 から 4)、1 つのルールの優先度を 2 に変更した場合には、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。</span><span class="sxs-lookup"><span data-stu-id="6737f-418">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="6737f-419">PowerShell でフィッシングルールの優先度を設定するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="6737f-419">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="6737f-p146">この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。</span><span class="sxs-lookup"><span data-stu-id="6737f-p146">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="6737f-422">**注** :</span><span class="sxs-lookup"><span data-stu-id="6737f-422">**Notes** :</span></span>

- <span data-ttu-id="6737f-423">新しいルールの作成時に優先度を設定するには、代わりに **new-antiphishrule** コマンドレットで _priority_ パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="6737f-423">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="6737f-424">既定のフィッシングポリシーには、対応するフィッシングルールが設定されておらず、常に未設定の優先度の値が **最低** になっています。</span><span class="sxs-lookup"><span data-stu-id="6737f-424">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="6737f-425">PowerShell を使用してフィッシングポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="6737f-425">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="6737f-426">PowerShell を使用してフィッシングポリシーを削除しても、対応するフィッシングルールは削除されません。</span><span class="sxs-lookup"><span data-stu-id="6737f-426">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="6737f-427">PowerShell でフィッシングポリシーを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="6737f-427">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="6737f-428">この例では、Marketing Department という名前のフィッシングポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="6737f-428">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="6737f-429">構文およびパラメーターの詳細については、「 [get-antiphishpolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6737f-429">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="6737f-430">PowerShell を使用してフィッシングルールを削除する</span><span class="sxs-lookup"><span data-stu-id="6737f-430">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="6737f-431">PowerShell を使用してフィッシングルールを削除しても、対応するフィッシングポリシーは削除されません。</span><span class="sxs-lookup"><span data-stu-id="6737f-431">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="6737f-432">PowerShell でフィッシングルールを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="6737f-432">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="6737f-433">この例では、Marketing Department という名前のフィッシングルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="6737f-433">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="6737f-434">構文およびパラメーターの詳細については、「 [new-antiphishrule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6737f-434">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="6737f-435">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="6737f-435">How do you know these procedures worked?</span></span>

<span data-ttu-id="6737f-436">Microsoft Defender for Office 365 でフィッシング対策ポリシーが正常に構成されたことを確認するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6737f-436">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="6737f-437">セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** \> **ATP のフィッシング対策** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="6737f-437">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="6737f-438">ポリシーの一覧、その **状態** の値、およびその **優先度** の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="6737f-438">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="6737f-439">詳細を表示するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6737f-439">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="6737f-440">リストからポリシーを選択し、フライアウトの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="6737f-440">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="6737f-441">[ **既定のポリシー** ] をクリックして、フライアウトの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="6737f-441">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="6737f-442">Exchange Online PowerShell で、を \<Name\> ポリシーまたはルールの名前に置き換えて、次のコマンドを実行し、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="6737f-442">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
