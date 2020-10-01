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
description: 管理者は、Office 365 Advanced Threat Protection (Office 365 ATP) を使用して組織で使用できる高度なフィッシング対策ポリシーを作成、変更、および削除する方法を学習できます。
ms.openlocfilehash: c08046bdc9e72bc824dc28acdf2443c9071236a0
ms.sourcegitcommit: b06a4f21da247edb03fdf6a01eafb7d4fb387b33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333548"
---
# <a name="configure-atp-anti-phishing-policies"></a><span data-ttu-id="02fbc-103">ATP フィッシング詐欺対策ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="02fbc-103">Configure ATP anti-phishing policies</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="02fbc-104">ATP のフィッシング対策ポリシーは、 [Office 365 Advanced Threat Protection](office-365-atp.md)の一部です。</span><span class="sxs-lookup"><span data-stu-id="02fbc-104">ATP anti-phishing policies are part of [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="02fbc-105">ATP のフィッシング対策ポリシーは、悪意のある偽造ベースのフィッシング攻撃やその他の種類のフィッシング攻撃から組織を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-105">ATP anti-phishing policies can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="02fbc-106">Exchange Online Protection (EOP) と ATP のフィッシング対策ポリシーにおけるフィッシング対策ポリシーの相違点の詳細については、「 [フィッシング対策保護](anti-phishing-protection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02fbc-106">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and ATP anti-phishing policies, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="02fbc-107">管理者は、既定の ATP のフィッシング対策ポリシーを表示、編集、および構成できます (削除することはできません)。</span><span class="sxs-lookup"><span data-stu-id="02fbc-107">Admins can view, edit, and configure (but not delete) the default ATP anti-phishing policy.</span></span> <span data-ttu-id="02fbc-108">さらに細分性を高めるために、組織内の特定のユーザー、グループ、またはドメインに適用するカスタムの ATP のフィッシング対策ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-108">For greater granularity, you can also create custom ATP anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="02fbc-109">カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (実行順序) を変更できます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-109">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="02fbc-110">セキュリティ & コンプライアンスセンターまたは Exchange Online PowerShell で、ATP のフィッシング対策ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-110">You can configure ATP anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="02fbc-111">Exchange Online Protection 組織 (つまり、Office 365 ATP を使用しない Microsoft 365 組織) で使用可能なフィッシング対策ポリシーの構成の詳細については、「 [CONFIGURE EOP」の「Configure フィッシング対策ポリシー](configure-anti-phishing-policies-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02fbc-111">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, Microsoft 365 organizations without Office 365 ATP), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

## <a name="atp-anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="02fbc-112">セキュリティ & コンプライアンスセンター vs PowerShell の ATP のフィッシング対策ポリシー</span><span class="sxs-lookup"><span data-stu-id="02fbc-112">ATP anti-phishing policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="02fbc-113">ATP のフィッシング対策ポリシーの基本的な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="02fbc-113">The basic elements of an ATP anti-phishing policy are:</span></span>

- <span data-ttu-id="02fbc-114">**フィッシングポリシー**: 有効または無効にするフィッシング対策、およびオプションを適用するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-114">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="02fbc-115">**フィッシングルールで**は、フィッシングポリシーの優先順位と受信者フィルター (ポリシーが適用されるユーザー) を指定します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-115">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="02fbc-116">セキュリティ & コンプライアンスセンターで ATP のフィッシング対策ポリシーを管理する場合、次の2つの要素の違いは明白ではありません。</span><span class="sxs-lookup"><span data-stu-id="02fbc-116">The difference between these two elements isn't obvious when you manage ATP anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="02fbc-117">ポリシーを作成する場合、実際には、フィッシングルールと関連付けられているフィッシングポリシーを両方に同じ名前を使用して同時に作成しています。</span><span class="sxs-lookup"><span data-stu-id="02fbc-117">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="02fbc-118">ポリシーを変更する場合、name、priority、enabled または disabled、および recipient フィルターに関連する設定によって、フィッシングルールが変更されます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-118">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="02fbc-119">他のすべての設定は、関連付けられたフィッシングポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-119">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="02fbc-120">ポリシーを削除すると、フィッシングルールとそれに関連付けられているフィッシングポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-120">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="02fbc-121">Exchange Online の PowerShell では、ポリシーとルールを個別に管理します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-121">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="02fbc-122">詳細については、このトピックで後述 [する「Exchange Online の PowerShell を使用して ATP のフィッシング対策ポリシーを構成する](#use-exchange-online-powershell-to-configure-atp-anti-phishing-policies) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="02fbc-122">For more information, see the [Use Exchange Online PowerShell to configure ATP anti-phishing policies](#use-exchange-online-powershell-to-configure-atp-anti-phishing-policies) section later in this topic.</span></span>

<span data-ttu-id="02fbc-123">すべての Office 365 ATP 組織には、以下のプロパティを持つ Office365 フィッシング対策 Default という組み込みの ATP のフィッシング対策ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="02fbc-123">Every Office 365 ATP organization has a built-in ATP anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="02fbc-124">ポリシーに関連付けられているフィッシングルール (受信者フィルター) がない場合でも、ポリシーは組織内のすべての受信者に適用されます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-124">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="02fbc-125">ポリシーにはカスタムの優先順位の値 **Lowest** が設定されており、変更することはできません (このポリシーは常に最後に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="02fbc-125">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="02fbc-126">作成するどのカスタム ポリシーも、より高い優先順位を持ちます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-126">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="02fbc-127">ポリシーは既定のポリシー (**IsDefault** のプロパティが `True` の値になっている) であり、既定のポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="02fbc-127">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="02fbc-128">フィッシング対策保護の有効性を高めるために、特定のユーザーまたはユーザーグループに適用される厳密な設定を使用して、カスタムの ATP のフィッシング対策ポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-128">To increase the effectiveness of anti-phishing protection, you can create custom ATP anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="02fbc-129">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="02fbc-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="02fbc-130"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-130">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="02fbc-131">**ATP のフィッシング対策**ページに直接移動するには、を使用 <https://protection.office.com/antiphishing> します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-131">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="02fbc-132">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02fbc-132">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="02fbc-133">この記事に記載されている手順を実行するには、事前にアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="02fbc-133">You need to be assigned permissions before you can do the procedures in this article:</span></span>

  - <span data-ttu-id="02fbc-134">ATP のフィッシング対策ポリシーを追加、変更、および削除するには、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="02fbc-134">To add, modify, and delete ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="02fbc-135">**組織の管理**または[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ管理者**。</span><span class="sxs-lookup"><span data-stu-id="02fbc-135">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="02fbc-136">**組織の管理**または [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**検疫管理**。</span><span class="sxs-lookup"><span data-stu-id="02fbc-136">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="02fbc-137">ATP のフィッシング対策ポリシーへの読み取り専用アクセスでは、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="02fbc-137">For read-only access to ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="02fbc-138">[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ閲覧者**。</span><span class="sxs-lookup"><span data-stu-id="02fbc-138">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="02fbc-139">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**表示限定の組織管理**。</span><span class="sxs-lookup"><span data-stu-id="02fbc-139">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="02fbc-140">ATP のフィッシング対策ポリシーの推奨設定については、「 [atp のフィッシング対策ポリシーの設定](recommended-settings-for-eop-and-office365-atp.md#atp-anti-phishing-policy-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02fbc-140">For our recommended settings for ATP anti-phishing policies, see [ATP anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#atp-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="02fbc-141">新規または更新されたポリシーが適用されるまで最大30分かかります。</span><span class="sxs-lookup"><span data-stu-id="02fbc-141">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="02fbc-142">フィルタリングパイプラインにフィッシング対策ポリシーを適用する方法については、「 [メール保護の順序と優先順位](how-policies-and-protections-are-combined.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02fbc-142">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-atp-anti-phishing-policies"></a><span data-ttu-id="02fbc-143">セキュリティ & コンプライアンスセンターを使用して、ATP のフィッシング対策ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="02fbc-143">Use the Security & Compliance Center to create ATP anti-phishing policies</span></span>

<span data-ttu-id="02fbc-144">セキュリティ & コンプライアンスセンターでカスタムの ATP のフィッシング対策ポリシーを作成すると、フィッシングルールと関連付けられているフィッシングポリシーが両方に同じ名前で同時に作成されます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-144">Creating a custom ATP anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="02fbc-145">ATP のフィッシング対策ポリシーを作成する場合、ポリシー名、説明、およびポリシーの適用先を識別する受信者フィルターのみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-145">When you create an ATP anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="02fbc-146">ポリシーを作成したら、ポリシーを変更して既定のフィッシング対策設定を変更または確認することができます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-146">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="02fbc-147">セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** \> **ATP のフィッシング対策**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-147">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="02fbc-148">[ **フィッシング対策** ] ページで、[ **作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-148">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="02fbc-149">[ **新しいフィッシング対策ポリシーの作成** ] ウィザードが開きます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-149">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="02fbc-150">[ **ポリシーに名前** をつける] ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-150">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="02fbc-151">**[名前]**: わかりやすい一意のポリシー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-151">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="02fbc-152">**[説明]**: ポリシーについての説明を入力します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="02fbc-152">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="02fbc-153">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-153">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="02fbc-154">表示される [ **適用先** ] ページで、ポリシーが適用される内部の受信者を特定します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-154">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="02fbc-155">各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-155">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="02fbc-156">同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-156">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="02fbc-157">a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-157">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="02fbc-158">[ **条件の追加] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-158">Click **Add a condition**.</span></span> <span data-ttu-id="02fbc-159">表示されるドロップダウンで、[適用済みの **場合**] の条件を選択します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-159">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="02fbc-160">**受信者は**次のとおりです。組織内で1つ以上のメールボックス、メールユーザー、またはメール連絡先を指定します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-160">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="02fbc-161">**受信者が次のメンバーの**場合: 組織内の1つまたは複数のグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-161">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="02fbc-162">**受信者のドメイン**: 構成された1つ以上の承認済みドメインの受信者を組織に指定します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-162">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="02fbc-163">条件を選択すると、対応するドロップ **ダウンボックスが** 表示されます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-163">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="02fbc-164">ボックス内をクリックし、値の一覧をスクロールして選択します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-164">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="02fbc-165">ボックス内をクリックして入力を開始し、リストにフィルターを適用して値を選択します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-165">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="02fbc-166">その他の値を追加するには、ボックスの空の領域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-166">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="02fbc-167">個々のエントリを削除するには、その値の [削除] アイコン **をクリックし** ![ ](../../media/scc-remove-icon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-167">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="02fbc-168">条件全体を削除するには、条件の [削除] アイコン **をクリックし** ![ ](../../media/scc-remove-icon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-168">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="02fbc-169">別の条件を追加するには、[ **条件の追加** ] をクリックし、[ **適用**時] で残りの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-169">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="02fbc-170">例外を追加するには、[ **条件の追加** ] をクリックし、 **Except if**で例外を選択します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-170">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="02fbc-171">設定と動作は、条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="02fbc-171">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="02fbc-172">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-172">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="02fbc-173">表示される [ **設定の確認** ] ページで、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-173">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="02fbc-174">各設定で [ **編集** ] をクリックして、変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-174">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="02fbc-175">完了したら、[ **このポリシーの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-175">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="02fbc-176">表示される確認ダイアログで [ **OK** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-176">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="02fbc-177">これらの一般的なポリシー設定を使用して ATP のフィッシング対策ポリシーを作成した後、次のセクションの手順を使用して、ポリシーの保護設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-177">After you create the ATP anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-atp-anti-phishing-policies"></a><span data-ttu-id="02fbc-178">セキュリティ & コンプライアンスセンターを使用して ATP のフィッシング対策ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="02fbc-178">Use the Security & Compliance Center to modify ATP anti-phishing policies</span></span>

<span data-ttu-id="02fbc-179">ATP のフィッシング対策ポリシーを変更するには、次の手順を使用します。これは、作成した新しいポリシー、または既にカスタマイズした既存のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="02fbc-179">Use the following procedures to modify ATP anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="02fbc-180">まだ存在しない場合は、セキュリティ & コンプライアンスセンターを開き、[ **脅威管理** \> **ポリシー** ] \> **ATP のフィッシング対策**に移動します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-180">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="02fbc-181">変更するカスタムの ATP のフィッシング対策ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-181">Select the custom ATP anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="02fbc-182">既に選択されている場合は、選択を解除してもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-182">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="02fbc-183">[**ポリシー \<name\> の編集**のポップアップを表示します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-183">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="02fbc-184">いずれかのセクションで [ **編集** ] をクリックすると、そのセクションの設定にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-184">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="02fbc-185">次の手順は、セクションが表示される順序で示されていますが、連続していません (任意の順序でセクションを選択して変更することができます)。</span><span class="sxs-lookup"><span data-stu-id="02fbc-185">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="02fbc-186">セクションで [**編集**] をクリックすると、使用可能な設定がウィザード形式で表示されますが、ページ内を任意の順序で移動できます。または、[すべての**Close**ページに**保存** **] を**クリックして ![ 、[ ](../../media/scc-remove-icon.png) **ポリシー \<name\> の編集**] ページに戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-186">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="02fbc-187">**ポリシー設定**: [ **編集** ] をクリックして、前のセクションで [ポリシーを作成](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) したときに使用したものと同じ設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-187">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="02fbc-188">**名前**</span><span class="sxs-lookup"><span data-stu-id="02fbc-188">**Name**</span></span>
   - <span data-ttu-id="02fbc-189">**説明**</span><span class="sxs-lookup"><span data-stu-id="02fbc-189">**Description**</span></span>
   - <span data-ttu-id="02fbc-190">**適用先**</span><span class="sxs-lookup"><span data-stu-id="02fbc-190">**Applied to**</span></span>
   - <span data-ttu-id="02fbc-191">**設定を確認する**</span><span class="sxs-lookup"><span data-stu-id="02fbc-191">**Review your settings**</span></span>

   <span data-ttu-id="02fbc-192">完了したら、[任意のページに **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-192">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="02fbc-193">**偽装**: [ **編集** ] をクリックして、ポリシー内の保護された送信者と保護されたドメインを変更します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-193">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="02fbc-194">これらの設定は、受信メッセージの From アドレスで (個別またはドメインによって) 検索するスプーフィングされた送信者を識別するポリシーの条件です。</span><span class="sxs-lookup"><span data-stu-id="02fbc-194">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="02fbc-195">詳細については、「 [ATP のフィッシング対策ポリシー」の「偽装設定](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02fbc-195">For more information, see [Impersonation settings in ATP anti-phishing policies](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="02fbc-196">**保護するユーザーを追加する**: 既定値は **Off**です。</span><span class="sxs-lookup"><span data-stu-id="02fbc-196">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="02fbc-197">これをオンにするには、トグルを **[オン**] にして、表示される [ **ユーザーの追加** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-197">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="02fbc-198">[ **ユーザーの追加** ] ポップアップが表示されたら、次の値を構成します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-198">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="02fbc-199">**メールアドレス**:</span><span class="sxs-lookup"><span data-stu-id="02fbc-199">**Email address**:</span></span>

        - <span data-ttu-id="02fbc-200">ボックス内をクリックし、ユーザーの一覧をスクロールして選択します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-200">Click in the box and scroll through the list of users to select.</span></span>
        - <span data-ttu-id="02fbc-201">ボックス内をクリックして入力を開始し、リストにフィルターを適用してユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-201">Click in the box and start typing to filter the list and select a user.</span></span>
        - <span data-ttu-id="02fbc-202">エントリを削除するには、ユーザーの [削除] アイコン **をクリックし** ![ ](../../media/scc-remove-icon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-202">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="02fbc-203">**Name**: この値は、選択したメールアドレスに基づいて設定されますが、変更することができます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-203">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="02fbc-204">完了したら、[任意のページに **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-204">When you're finished, click **Save** on any page.</span></span>

    <span data-ttu-id="02fbc-205">既存のエントリを編集するには、一覧で保護されたユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-205">To edit an existing entry, select the protected user in the list.</span></span>

   - <span data-ttu-id="02fbc-206">**保護するドメインを追加する**: 次の設定の1つまたは両方を構成します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-206">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="02fbc-207">**自分が所有するドメインを自動的に追加**する: 既定値は **Off**です。</span><span class="sxs-lookup"><span data-stu-id="02fbc-207">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="02fbc-208">これをオンにするには、トグルを **[オン**] にします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-208">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="02fbc-209">**カスタムドメインを含める**: 既定値は **Off**です。</span><span class="sxs-lookup"><span data-stu-id="02fbc-209">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="02fbc-210">これをオンにするには、トグルを **[オン**] にして、[ **ドメインの追加** ] ボックスにドメイン名 (contoso.com など) を入力し、enter キーを押して、必要に応じて繰り返します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-210">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

       <span data-ttu-id="02fbc-211">**注**: セキュリティ & コンプライアンスセンターでは、最大20個のドメインを入力できます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-211">**Note**: In the Security & Compliance Center, you can enter a maximum of 20 domains.</span></span> <span data-ttu-id="02fbc-212">Exchange Online の PowerShell では、最大50のドメインを入力できます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-212">In Exchange Online PowerShell, you can enter a maximum of 50 domains.</span></span>

   - <span data-ttu-id="02fbc-213">**アクション**: [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-213">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="02fbc-214">**偽装ユーザーによって電子メールが送信**される場合: スプーフィングされた送信者が、[ **保護するユーザーの追加**] で指定した保護されたユーザーのいずれかであるメッセージに対して、次のいずれかのアクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-214">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="02fbc-215">**どの操作も適用しない**</span><span class="sxs-lookup"><span data-stu-id="02fbc-215">**Don't apply any action**</span></span>
       - <span data-ttu-id="02fbc-216">**他の電子メールアドレスへのメッセージのリダイレクト**</span><span class="sxs-lookup"><span data-stu-id="02fbc-216">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="02fbc-217">**迷惑メールフォルダーにメッセージを移動する**</span><span class="sxs-lookup"><span data-stu-id="02fbc-217">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="02fbc-218">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="02fbc-218">**Quarantine the message**</span></span>
       - <span data-ttu-id="02fbc-219">**メッセージを配信し、その他のアドレスを Bcc 行に追加する**</span><span class="sxs-lookup"><span data-stu-id="02fbc-219">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="02fbc-220">**配信前にメッセージを削除する**</span><span class="sxs-lookup"><span data-stu-id="02fbc-220">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="02fbc-221">**偽装ドメインによって電子メールが送信**される場合: スプーフィングされた送信者が、 **保護するドメインの追加**で指定した保護されたドメインのいずれかにあるメッセージに対して、次のいずれかのアクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-221">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

     - <span data-ttu-id="02fbc-222">**どの操作も適用しない**</span><span class="sxs-lookup"><span data-stu-id="02fbc-222">**Don't apply any action**</span></span>
     - <span data-ttu-id="02fbc-223">**他の電子メールアドレスへのメッセージのリダイレクト**</span><span class="sxs-lookup"><span data-stu-id="02fbc-223">**Redirect message to other email addresses**</span></span>
     - <span data-ttu-id="02fbc-224">**迷惑メールフォルダーにメッセージを移動する**</span><span class="sxs-lookup"><span data-stu-id="02fbc-224">**Move message to Junk Email folder**</span></span>
     - <span data-ttu-id="02fbc-225">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="02fbc-225">**Quarantine the message**</span></span>
     - <span data-ttu-id="02fbc-226">**メッセージを配信し、その他のアドレスを Bcc 行に追加する**</span><span class="sxs-lookup"><span data-stu-id="02fbc-226">**Deliver the message and add other addresses to the Bcc line**</span></span>
     - <span data-ttu-id="02fbc-227">**配信前にメッセージを削除する**</span><span class="sxs-lookup"><span data-stu-id="02fbc-227">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="02fbc-228">[ **偽装の安全性のヒントを有効にする** ] をクリックし、次のいずれかの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-228">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="02fbc-229">**偽装ユーザーのヒントを表示する**: 既定値は **Off**です。</span><span class="sxs-lookup"><span data-stu-id="02fbc-229">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="02fbc-230">これをオンにするには、トグルを **[オン**] にします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-230">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="02fbc-231">**偽装ドメインのヒントを表示する**: 既定値は **Off**です。</span><span class="sxs-lookup"><span data-stu-id="02fbc-231">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="02fbc-232">これをオンにするには、トグルを **[オン**] にします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-232">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="02fbc-233">**通常の文字にヒントを表示**する: 既定値は **Off**です。</span><span class="sxs-lookup"><span data-stu-id="02fbc-233">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="02fbc-234">これをオンにするには、トグルを **[オン**] にします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-234">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="02fbc-235">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-235">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="02fbc-236">**メールボックスインテリジェンス**:</span><span class="sxs-lookup"><span data-stu-id="02fbc-236">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="02fbc-237">**メールボックスインテリジェンスを有効に**しますか。既定値は **[オン**] です。</span><span class="sxs-lookup"><span data-stu-id="02fbc-237">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="02fbc-238">この機能をオフにするには、トグルを [ **オフ**] にします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-238">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="02fbc-239">**[\*\*\*\*メールボックスインテリジェンスベースの偽装保護を有効にする]**: この設定は、**メールボックスインテリジェンスを有効にする**場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-239">**Enable mailbox intelligence based impersonation protection?**: This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="02fbc-240">で **偽装ユーザーによって電子メールが送信**された場合は、メールボックスインテリジェンスに失敗したメッセージに対して次のいずれかの操作を行うことができます (保護されたユーザーと保護されたドメインに対して使用可能なものと同じもの)。</span><span class="sxs-lookup"><span data-stu-id="02fbc-240">In **If email is sent by an impersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="02fbc-241">**どの操作も適用しない**</span><span class="sxs-lookup"><span data-stu-id="02fbc-241">**Don't apply any action**</span></span>
       - <span data-ttu-id="02fbc-242">**他の電子メールアドレスへのメッセージのリダイレクト**</span><span class="sxs-lookup"><span data-stu-id="02fbc-242">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="02fbc-243">**迷惑メールフォルダーにメッセージを移動する**</span><span class="sxs-lookup"><span data-stu-id="02fbc-243">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="02fbc-244">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="02fbc-244">**Quarantine the message**</span></span>
       - <span data-ttu-id="02fbc-245">**メッセージを配信し、その他のアドレスを Bcc 行に追加する**</span><span class="sxs-lookup"><span data-stu-id="02fbc-245">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="02fbc-246">**配信前にメッセージを削除する**</span><span class="sxs-lookup"><span data-stu-id="02fbc-246">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="02fbc-247">**信頼できる差出人とドメインを追加**する: ポリシーの例外を指定します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-247">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="02fbc-248">**信頼できる送信者**:</span><span class="sxs-lookup"><span data-stu-id="02fbc-248">**Trusted senders**:</span></span>

       - <span data-ttu-id="02fbc-249">ボックス内をクリックし、ユーザーの一覧をスクロールして選択します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-249">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="02fbc-250">ボックス内をクリックして入力を開始し、リストにフィルターを適用してユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-250">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="02fbc-251">エントリを削除するには、ユーザーの [削除] アイコン **をクリックし** ![ ](../../media/scc-remove-icon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-251">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="02fbc-252">[**信頼されたドメイン**]: ドメイン名 (たとえば、contoso.com) を入力し、enter キーを押して、必要に応じて繰り返します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-252">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="02fbc-253">**設定を確認**します。個々の手順をクリックする代わりに、設定が概要で表示されます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-253">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="02fbc-254">各セクションで [ **編集** ] をクリックすると、関連するページに戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-254">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="02fbc-255">このページでは、次の設定の **オン** と **オフ** を直接切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-255">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="02fbc-256">**保護されたユーザー**</span><span class="sxs-lookup"><span data-stu-id="02fbc-256">**Protected users**</span></span>
       - <span data-ttu-id="02fbc-257">**保護されたドメイン** \>**所有**しているドメインを含める</span><span class="sxs-lookup"><span data-stu-id="02fbc-257">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="02fbc-258">**保護されたドメイン** \>**保護されたドメイン**(カスタムドメイン)</span><span class="sxs-lookup"><span data-stu-id="02fbc-258">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="02fbc-259">**メールボックス インテリジェンス**</span><span class="sxs-lookup"><span data-stu-id="02fbc-259">**Mailbox intelligence**</span></span>

   <span data-ttu-id="02fbc-260">完了したら、[任意のページに **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-260">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="02fbc-261">**スプーフィング**: [ **編集** ] をクリックして、スプーフィングインテリジェンスを有効または無効にしたり、Outlook で認証されていない送信者の識別をオンまたはオフにしたり、ブロックされたスプーフィングされた送信者からのメッセージに適用するアクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-261">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="02fbc-262">詳細については、「 [フィッシング対策ポリシーのスプーフィング設定](set-up-anti-phishing-policies.md#spoof-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02fbc-262">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="02fbc-263">なお、これらの設定は EOP のフィッシング対策ポリシーでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-263">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="02fbc-264">**フィルター設定のスプーフィング**: 既定値は **on**で、そのままにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-264">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="02fbc-265">この機能をオフにするには、トグルを [ **オフ**] にします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-265">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="02fbc-266">詳細については、「 [Configure スプーフ知能 IN EOP」](learn-about-spoof-intelligence.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02fbc-266">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="02fbc-267">MX レコードが Microsoft 365 をポイントしていない場合は、スプーフィング防止保護を無効にする必要はありません。代わりに、コネクタの拡張フィルターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-267">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="02fbc-268">手順については、「 [Exchange Online のコネクタの拡張フィルター処理](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02fbc-268">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="02fbc-269">[認証されていない**送信者の機能を有効にする**]: 既定値は **[オン**] です。</span><span class="sxs-lookup"><span data-stu-id="02fbc-269">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="02fbc-270">この機能をオフにするには、トグルを [ **オフ**] にします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-270">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="02fbc-271">**アクション**: スプーフィングインテリジェンスに失敗したメッセージに対して実行するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-271">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="02fbc-272">**ドメインのスプーフィングが許可されていないユーザーによって電子メールが送信**される場合:</span><span class="sxs-lookup"><span data-stu-id="02fbc-272">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="02fbc-273">**受信者の迷惑メールフォルダーにメッセージを移動する**</span><span class="sxs-lookup"><span data-stu-id="02fbc-273">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="02fbc-274">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="02fbc-274">**Quarantine the message**</span></span>

   - <span data-ttu-id="02fbc-275">**設定を確認**します。個々の手順をクリックする代わりに、設定が概要で表示されます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-275">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="02fbc-276">各セクションで [ **編集** ] をクリックすると、関連するページに戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-276">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="02fbc-277">このページでは、次の設定の **オン** と **オフ** を直接切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-277">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="02fbc-278">**スプーフィング対策保護を有効にする**</span><span class="sxs-lookup"><span data-stu-id="02fbc-278">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="02fbc-279">**認証されていない送信者機能を有効にする**</span><span class="sxs-lookup"><span data-stu-id="02fbc-279">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="02fbc-280">完了したら、[任意のページに **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-280">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="02fbc-281">**詳細設定**: [ **編集** ] をクリックして、詳細なフィッシングしきい値を構成します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-281">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="02fbc-282">詳細については、「 [ATP のフィッシング対策ポリシー」の「Advanced フィッシングしきい値](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02fbc-282">For more information, see [Advanced phishing thresholds in ATP anti-phishing policies](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="02fbc-283">**[Advanced フィッシングしきい**値]: 次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-283">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="02fbc-284">**1-標準** (これは既定値です)</span><span class="sxs-lookup"><span data-stu-id="02fbc-284">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="02fbc-285">**2-アグレッシブ**</span><span class="sxs-lookup"><span data-stu-id="02fbc-285">**2 - Aggressive**</span></span>
   - <span data-ttu-id="02fbc-286">**3つ以上のアグレッシブ**</span><span class="sxs-lookup"><span data-stu-id="02fbc-286">**3 - More aggressive**</span></span>
   - <span data-ttu-id="02fbc-287">**4-最も積極的**</span><span class="sxs-lookup"><span data-stu-id="02fbc-287">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="02fbc-288">**設定を確認**します。 [ **編集** ] をクリックすると、[ **詳細なフィッシングのしきい値** ] ページに戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-288">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="02fbc-289">完了したら、[どちらかのページで **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-289">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="02fbc-290">[**ポリシー \<Name\> の編集**] ページに戻り、設定を確認してから、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-290">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-atp-anti-phishing-policy"></a><span data-ttu-id="02fbc-291">セキュリティ & コンプライアンスセンターを使用して既定の ATP のフィッシング対策ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="02fbc-291">Use the Security & Compliance Center to modify the default ATP anti-phishing policy</span></span>

<span data-ttu-id="02fbc-292">既定の ATP のフィッシング対策ポリシーの名前は、Office365 フィッシング対策 Default で、ポリシーの一覧には表示されません。</span><span class="sxs-lookup"><span data-stu-id="02fbc-292">The default ATP anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="02fbc-293">既定の ATP のフィッシング対策ポリシーを変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-293">To modify the default ATP anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="02fbc-294">セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** \> **ATP のフィッシング対策**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-294">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="02fbc-295">[ **フィッシング対策** ] ページで、[ **既定のポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-295">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="02fbc-296">[ **ポリシーの Office 365 フィッシング対策の既定の編集** ] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-296">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="02fbc-297">次のセクションを使用できます。これには、 [カスタムポリシーを変更](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies)するときに、同一の設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="02fbc-297">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):</span></span>

   - <span data-ttu-id="02fbc-298">**偽装**</span><span class="sxs-lookup"><span data-stu-id="02fbc-298">**Impersonation**</span></span>
   - <span data-ttu-id="02fbc-299">**なりすます**</span><span class="sxs-lookup"><span data-stu-id="02fbc-299">**Spoof**</span></span>
   - <span data-ttu-id="02fbc-300">**詳細設定**</span><span class="sxs-lookup"><span data-stu-id="02fbc-300">**Advanced settings**</span></span>

   <span data-ttu-id="02fbc-301">次の設定は、既定のポリシーを変更するときには使用できません。</span><span class="sxs-lookup"><span data-stu-id="02fbc-301">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="02fbc-302">**ポリシー設定**のセクションと値は表示できますが、**編集**リンクはありません。そのため、設定 (ポリシー名、説明、ポリシーの適用先 (すべての受信者に適用)) を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="02fbc-302">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="02fbc-303">既定のポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="02fbc-303">You can't delete the default policy.</span></span>
   - <span data-ttu-id="02fbc-304">既定のポリシーの優先度を変更することはできません (常に最後に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="02fbc-304">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="02fbc-305">[ **Policy The Office365 フィッシング対策 Default** ] ページで、設定を確認し、[ **閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-305">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-atp-anti-phishing-policies"></a><span data-ttu-id="02fbc-306">カスタム ATP フィッシング対策ポリシーを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="02fbc-306">Enable or disable custom ATP anti-phishing policies</span></span>

1. <span data-ttu-id="02fbc-307">セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** \> **ATP のフィッシング対策**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-307">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="02fbc-308">[ **状態** ] 列の値に注目してください。</span><span class="sxs-lookup"><span data-stu-id="02fbc-308">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="02fbc-309">トグルを [ **オフ** ] にして、ポリシーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-309">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="02fbc-310">トグルに切り替えて、 **ポリシーを有効** にします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-310">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="02fbc-311">既定のフィッシング対策ポリシーを無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="02fbc-311">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-atp-anti-phishing-policies"></a><span data-ttu-id="02fbc-312">カスタム ATP フィッシング対策ポリシーの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="02fbc-312">Set the priority of custom ATP anti-phishing policies</span></span>

<span data-ttu-id="02fbc-313">既定では、ATP のフィッシング対策ポリシーには、作成された順序に基づく優先度が与えられます (新しいポリシーは、以前のポリシーよりも優先度が低いです)。</span><span class="sxs-lookup"><span data-stu-id="02fbc-313">By default, ATP anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="02fbc-314">優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。</span><span class="sxs-lookup"><span data-stu-id="02fbc-314">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="02fbc-315">2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-315">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="02fbc-316">優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02fbc-316">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="02fbc-317">カスタム ATP のフィッシング対策ポリシーは、処理順に表示されます (最初のポリシーの **優先度** 値は0になります)。</span><span class="sxs-lookup"><span data-stu-id="02fbc-317">Custom ATP anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="02fbc-318">Office365 フィッシング対策 Default という既定のフィッシング対策ポリシーは、カスタムの優先度の値を **最小**にし、それを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="02fbc-318">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="02fbc-319">**注**: セキュリティ & コンプライアンスセンターでは、作成後に ATP のフィッシング対策ポリシーの優先度のみを変更できます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-319">**Note**: In the Security & Compliance Center, you can only change the priority of the ATP anti-phishing policy after you create it.</span></span> <span data-ttu-id="02fbc-320">PowerShell では、フィッシングルールを作成するときに既定の優先順位を上書きできます (既存のルールの優先度に影響する場合があります)。</span><span class="sxs-lookup"><span data-stu-id="02fbc-320">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="02fbc-321">ポリシーの優先度を変更するには、ポリシーのプロパティで [ **優先度を上げる** ] または [ **優先度を下げる** ] をクリックします (セキュリティ & コンプライアンスセンターで **優先度** を直接変更することはできません)。</span><span class="sxs-lookup"><span data-stu-id="02fbc-321">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="02fbc-322">ポリシーの優先度を変更することは、複数のポリシーがある場合にのみ有効になります。</span><span class="sxs-lookup"><span data-stu-id="02fbc-322">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="02fbc-323">セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** \> **ATP のフィッシング対策**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-323">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="02fbc-324">変更するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-324">Select the policy that you want to modify.</span></span> <span data-ttu-id="02fbc-325">既に選択されている場合は、選択を解除してもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-325">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="02fbc-326">[**ポリシー \<name\> の編集**のポップアップを表示します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-326">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="02fbc-327">**優先順位**の値が**0**のカスタム ATP のフィッシング対策ポリシーでは、[**優先度を下げる**] ボタンのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-327">The custom ATP anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="02fbc-328">**優先度**の低い値 (たとえば**3**) を持つカスタム ATP のフィッシング対策ポリシーには、[**優先度を上げる**] ボタンだけが使用できます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-328">The custom ATP anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="02fbc-329">3つ以上のカスタムのマルウェア対策ポリシーを所有している場合、最高の優先度と最も低い優先度の値の間のポリシーでは、[優先度を **上げる** ] ボタンと [ **優先度を下げる** ] ボタンの両方を使用できます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-329">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="02fbc-330">[優先 **度を上げる** ] または [ **優先度を下げる** ] をクリックし、 **優先度** の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-330">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="02fbc-331">完了したら、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-331">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-atp-anti-phishing-policies"></a><span data-ttu-id="02fbc-332">セキュリティ & コンプライアンスセンターを使用して、ATP のフィッシング対策ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="02fbc-332">Use the Security & Compliance Center to view ATP anti-phishing policies</span></span>

1. <span data-ttu-id="02fbc-333">[セキュリティ & コンプライアンスセンター] で、[ **脅威管理** \> **ポリシー** \> **ATP のフィッシング対策**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-333">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="02fbc-334">次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-334">Do one of the following steps:</span></span>

   - <span data-ttu-id="02fbc-335">表示するカスタムの ATP のフィッシング対策ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-335">Select a custom ATP anti-phishing policy that you want to view.</span></span> <span data-ttu-id="02fbc-336">既に選択されている場合は、選択を解除してもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-336">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="02fbc-337">[ **既定のポリシー** ] をクリックして、既定のフィッシング対策ポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-337">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="02fbc-338">[**ポリシー \<name\> の編集**] ポップアップが表示され、設定と値を表示できます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-338">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-atp-anti-phishing-policies"></a><span data-ttu-id="02fbc-339">セキュリティ & コンプライアンスセンターを使用して、ATP のフィッシング対策ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="02fbc-339">Use the Security & Compliance Center to remove ATP anti-phishing policies</span></span>

1. <span data-ttu-id="02fbc-340">セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** \> **ATP のフィッシング対策**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-340">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="02fbc-341">削除するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-341">Select the policy that you want to remove.</span></span> <span data-ttu-id="02fbc-342">既に選択されている場合は、選択を解除してもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-342">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="02fbc-343">表示される [**ポリシー \<name\> の編集**] ポップアップで、[**ポリシーの削除**] をクリックし、表示される警告ダイアログボックスで [**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-343">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="02fbc-344">既定のポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="02fbc-344">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-atp-anti-phishing-policies"></a><span data-ttu-id="02fbc-345">Exchange Online PowerShell を使用して ATP のフィッシング対策ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="02fbc-345">Use Exchange Online PowerShell to configure ATP anti-phishing policies</span></span>

<span data-ttu-id="02fbc-346">前述したように、ATP のスパム対策ポリシーは、フィッシングポリシーとフィッシングルールで構成されています。</span><span class="sxs-lookup"><span data-stu-id="02fbc-346">As previously described, an ATP anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="02fbc-347">Exchange Online PowerShell では、フィッシングポリシーとフィッシングルールの違いが明らかです。</span><span class="sxs-lookup"><span data-stu-id="02fbc-347">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="02fbc-348">フィッシングポリシーを管理するには、 \*\* \* -get-antiphishpolicy**コマンドレットを使用して、 \*\* \* -new-antiphishrule**コマンドレットを使用してフィッシングルールを管理します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-348">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="02fbc-349">PowerShell では、フィッシングポリシーを最初に作成してから、ルールが適用されるポリシーを識別するフィッシングルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-349">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="02fbc-350">PowerShell では、フィッシングポリシーおよびフィッシングルールの設定を個別に変更します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-350">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="02fbc-351">PowerShell からフィッシングポリシーを削除すると、対応するフィッシングルールは自動的に削除されず、その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="02fbc-351">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="02fbc-352">PowerShell を使用してフィッシング対策ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="02fbc-352">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="02fbc-353">PowerShell でのフィッシング対策ポリシーの作成は、次の2つの手順からなるプロセスです。</span><span class="sxs-lookup"><span data-stu-id="02fbc-353">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="02fbc-354">フィッシングポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-354">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="02fbc-355">ルールが適用されるフィッシングポリシーを指定するフィッシングルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-355">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="02fbc-356">**注**:</span><span class="sxs-lookup"><span data-stu-id="02fbc-356">**Notes**:</span></span>

- <span data-ttu-id="02fbc-357">新しいフィッシングルールを作成し、関連付けられていない既存のアンチフィッシングポリシーをそのルールに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-357">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="02fbc-358">フィッシングルールは、複数のフィッシングポリシーに関連付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="02fbc-358">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="02fbc-359">次の設定は、ポリシーを作成するまではセキュリティ & コンプライアンスセンターでは使用できない PowerShell の新しいフィッシングポリシーで構成できます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-359">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="02fbc-360">新しいポリシーを無効として_Enabled_作成し `$false` ます ( **new-antiphishrule**コマンドレットでは有効)。</span><span class="sxs-lookup"><span data-stu-id="02fbc-360">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="02fbc-361">New-antiphishrule コマンドレットで、作成中にポリシーの優先度を設定します (_優先度_ _\<Number\>_ )。 **New-AntiPhishRule**</span><span class="sxs-lookup"><span data-stu-id="02fbc-361">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="02fbc-362">PowerShell で作成した新しいフィッシングポリシーは、ポリシーをフィッシングルールに割り当てるまで、セキュリティ & コンプライアンスセンターに表示されません。</span><span class="sxs-lookup"><span data-stu-id="02fbc-362">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="02fbc-363">手順 1: PowerShell を使用してフィッシングポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="02fbc-363">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="02fbc-364">フィッシングポリシーを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-364">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="02fbc-365">この例では、次の設定を使用して Research Quarantine という名前のフィッシングポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-365">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="02fbc-366">このポリシーは有効になっています ( _enabled_ パラメーターは使用していません。既定値はです `$true` )。</span><span class="sxs-lookup"><span data-stu-id="02fbc-366">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="02fbc-367">説明は、「研究部門のポリシー」です。</span><span class="sxs-lookup"><span data-stu-id="02fbc-367">The description is: Research department policy.</span></span>
- <span data-ttu-id="02fbc-368">すべての承認済みドメインに対する組織ドメインの保護と、fabrikam.com の対象となるドメインの保護を有効にします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-368">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="02fbc-369">偽装から保護するユーザーとして Mai Fujito (mfujito@fabrikam.com) を指定します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-369">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="02fbc-370">メールボックスのインテリジェンスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-370">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="02fbc-371">メールボックスインテリジェンス保護を有効にし、検疫アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-371">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="02fbc-372">安全のヒントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-372">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="02fbc-373">構文およびパラメーターの詳細については、「 [get-antiphishpolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02fbc-373">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="02fbc-374">手順 2: PowerShell を使用してフィッシングルールを作成する</span><span class="sxs-lookup"><span data-stu-id="02fbc-374">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="02fbc-375">フィッシングルールを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-375">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="02fbc-376">この例では、次の条件を使用して Research Department という名前のフィッシングルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-376">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="02fbc-377">ルールは、Research Quarantine という名前のフィッシングポリシーに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="02fbc-377">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="02fbc-378">ルールは Research Department という名前のグループのメンバーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-378">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="02fbc-379">_Priority_パラメーターを使用していないので、既定の優先度が使用されます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-379">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="02fbc-380">構文およびパラメーターの詳細については、「 [new-antiphishrule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02fbc-380">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="02fbc-381">PowerShell を使用してフィッシングのポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="02fbc-381">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="02fbc-382">既存のフィッシングポリシーを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-382">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="02fbc-383">この例では、指定されたプロパティと共にすべてのフィッシングポリシーの要約リストを返します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-383">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="02fbc-384">この例では、"重役" という名前のフィッシングポリシーのすべてのプロパティ値を返します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-384">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="02fbc-385">構文およびパラメーターの詳細については、「 [get-antiphishpolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02fbc-385">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="02fbc-386">PowerShell を使用してフィッシングのルールを表示する</span><span class="sxs-lookup"><span data-stu-id="02fbc-386">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="02fbc-387">既存のフィッシングルールを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-387">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="02fbc-388">この例では、指定したプロパティと共に、フィッシングのすべてのルールの要約リストを返します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-388">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="02fbc-389">ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-389">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="02fbc-390">この例では、Contoso 重役という名前のフィッシングルールのすべてのプロパティ値を返します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-390">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="02fbc-391">構文およびパラメーターの詳細については、「 [new-antiphishrule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02fbc-391">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="02fbc-392">PowerShell を使用してフィッシングポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="02fbc-392">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="02fbc-393">このトピックで前述したように、「 [手順 1: powershell を使用してフィッシングポリシーを作成する](#step-1-use-powershell-to-create-an-anti-phish-policy) 」で説明されているように、ポリシーの作成時に powershell のフィッシングポリシーを変更する場合は、次の項目以外にも同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-393">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="02fbc-394">指定されたポリシーを既定のポリシー (すべてのユーザーに適用して、常に**最下位**の優先度を適用し、削除することはできません) に変更する_makedefault_スイッチは、PowerShell のフィッシングポリシーを変更する場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-394">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="02fbc-395">フィッシングポリシーの名前を変更することはできません ( **get-antiphishpolicy** コマンドレットには _Name_ パラメーターがありません)。</span><span class="sxs-lookup"><span data-stu-id="02fbc-395">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="02fbc-396">セキュリティ & コンプライアンスセンターでフィッシング対策ポリシーの名前を変更する場合、フィッシング _ルール_の名前のみを変更しています。</span><span class="sxs-lookup"><span data-stu-id="02fbc-396">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="02fbc-397">フィッシングポリシーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-397">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="02fbc-398">構文およびパラメーターの詳細については、「 [get-antiphishpolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02fbc-398">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="02fbc-399">PowerShell を使用してフィッシングルールを変更する</span><span class="sxs-lookup"><span data-stu-id="02fbc-399">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="02fbc-400">PowerShell でフィッシングルールを変更するときには使用できない唯一の設定は、無効にされたルールを作成できる _有効_ なパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="02fbc-400">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="02fbc-401">既存のフィッシングルールを有効または無効にするには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="02fbc-401">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="02fbc-402">それ以外の場合は、PowerShell でフィッシングルールを変更しても、追加の設定は使用できません。</span><span class="sxs-lookup"><span data-stu-id="02fbc-402">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="02fbc-403">このトピックで前述した「 [手順 2: PowerShell を使用してフィッシングルールを作成する](#step-2-use-powershell-to-create-an-anti-phish-rule) 」で説明されているように、ルールを作成する場合にも同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-403">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="02fbc-404">フィッシングルールを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-404">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="02fbc-405">構文およびパラメーターの詳細については、「 [new-antiphishrule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02fbc-405">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="02fbc-406">PowerShell を使用してフィッシングルールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="02fbc-406">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="02fbc-407">PowerShell でフィッシングルールを有効または無効にすると、フィッシング対策ポリシー全体 (フィッシングルールおよび割り当てられたフィッシングポリシー) が有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="02fbc-407">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="02fbc-408">既定のフィッシング対策ポリシーを有効または無効にすることはできません (常にすべての受信者に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="02fbc-408">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="02fbc-409">PowerShell でフィッシングルールを有効または無効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-409">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="02fbc-410">この例では、Marketing Department という名前のフィッシングルールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="02fbc-410">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="02fbc-411">この例では、同じルールを有効化します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-411">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="02fbc-412">構文およびパラメーターの詳細については、「 [new-antiphishrule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) 」および「 [Disable-new-antiphishrule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02fbc-412">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="02fbc-413">PowerShell を使用してフィッシングルールの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="02fbc-413">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="02fbc-414">ルールに設定できる優先度の最高値値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="02fbc-414">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="02fbc-415">設定できる最低値はルールの数に依存します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-415">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="02fbc-416">たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。</span><span class="sxs-lookup"><span data-stu-id="02fbc-416">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="02fbc-417">既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-417">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="02fbc-418">たとえば、カスタム ルールが 5 つあって (優先度 0 から 4)、1 つのルールの優先度を 2 に変更した場合には、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。</span><span class="sxs-lookup"><span data-stu-id="02fbc-418">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="02fbc-419">PowerShell でフィッシングルールの優先度を設定するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-419">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="02fbc-p145">この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。</span><span class="sxs-lookup"><span data-stu-id="02fbc-p145">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="02fbc-422">**注**:</span><span class="sxs-lookup"><span data-stu-id="02fbc-422">**Notes**:</span></span>

- <span data-ttu-id="02fbc-423">新しいルールの作成時に優先度を設定するには、代わりに**new-antiphishrule**コマンドレットで_priority_パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-423">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="02fbc-424">既定のフィッシングポリシーには、対応するフィッシングルールが設定されておらず、常に未設定の優先度の値が **最低**になっています。</span><span class="sxs-lookup"><span data-stu-id="02fbc-424">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="02fbc-425">PowerShell を使用してフィッシングポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="02fbc-425">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="02fbc-426">PowerShell を使用してフィッシングポリシーを削除しても、対応するフィッシングルールは削除されません。</span><span class="sxs-lookup"><span data-stu-id="02fbc-426">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="02fbc-427">PowerShell でフィッシングポリシーを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-427">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="02fbc-428">この例では、Marketing Department という名前のフィッシングポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-428">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="02fbc-429">構文およびパラメーターの詳細については、「 [get-antiphishpolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02fbc-429">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="02fbc-430">PowerShell を使用してフィッシングルールを削除する</span><span class="sxs-lookup"><span data-stu-id="02fbc-430">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="02fbc-431">PowerShell を使用してフィッシングルールを削除しても、対応するフィッシングポリシーは削除されません。</span><span class="sxs-lookup"><span data-stu-id="02fbc-431">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="02fbc-432">PowerShell でフィッシングルールを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-432">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="02fbc-433">この例では、Marketing Department という名前のフィッシングルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-433">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="02fbc-434">構文およびパラメーターの詳細については、「 [new-antiphishrule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02fbc-434">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="02fbc-435">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="02fbc-435">How do you know these procedures worked?</span></span>

<span data-ttu-id="02fbc-436">ATP のフィッシング対策ポリシーが正常に構成されたことを確認するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-436">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="02fbc-437">セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** \> **ATP のフィッシング対策**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-437">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="02fbc-438">ポリシーの一覧、その **状態** の値、およびその **優先度** の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-438">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="02fbc-439">詳細を表示するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-439">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="02fbc-440">リストからポリシーを選択し、フライアウトの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-440">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="02fbc-441">[ **既定のポリシー** ] をクリックして、フライアウトの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-441">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="02fbc-442">Exchange Online PowerShell で、を \<Name\> ポリシーまたはルールの名前に置き換えて、次のコマンドを実行し、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="02fbc-442">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
