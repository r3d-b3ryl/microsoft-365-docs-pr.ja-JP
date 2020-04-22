---
title: ATP フィッシング詐欺対策ポリシーを設定する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理者は、Office 365 Advanced Threat Protection (ATP) を使用して組織で使用できる高度なフィッシング対策ポリシーを作成、変更、および削除する方法を学習できます。
ms.openlocfilehash: 358abc2835e8d1fba39d72021f03b75775528bcf
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638465"
---
# <a name="configure-atp-anti-phishing-policies"></a><span data-ttu-id="76fc4-103">ATP フィッシング詐欺対策ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="76fc4-103">Configure ATP anti-phishing policies</span></span>

<span data-ttu-id="76fc4-104">ATP のフィッシング対策ポリシーは、 [Office 365 Advanced Threat Protection](office-365-atp.md)の一部です。</span><span class="sxs-lookup"><span data-stu-id="76fc4-104">ATP anti-phishing policies are part of [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="76fc4-105">ATP のフィッシング対策ポリシーは、悪意のある偽造ベースのフィッシング攻撃やその他の種類のフィッシング攻撃から組織を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-105">ATP anti-phishing policies can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="76fc4-106">Exchange Online Protection (EOP) と ATP のフィッシング対策ポリシーにおけるフィッシング対策ポリシーの相違点の詳細については、「[フィッシング対策保護](anti-phishing-protection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76fc4-106">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and ATP anti-phishing policies, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="76fc4-107">管理者は、既定の ATP のフィッシング対策ポリシーを表示、編集、および構成できます (削除することはできません)。</span><span class="sxs-lookup"><span data-stu-id="76fc4-107">Admins can view, edit, and configure (but not delete) the default ATP anti-phishing policy.</span></span> <span data-ttu-id="76fc4-108">さらに細分性を高めるために、組織内の特定のユーザー、グループ、またはドメインに適用するカスタムの ATP のフィッシング対策ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-108">For greater granularity, you can also create custom ATP anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="76fc4-109">カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (実行順序) を変更できます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-109">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="76fc4-110">セキュリティ & コンプライアンスセンターまたは Exchange Online PowerShell で、ATP のフィッシング対策ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-110">You can configure ATP anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="76fc4-111">Exchange Online Protection 組織 (ATP を使用しない Office 365 組織) で使用できる、制限のある組み込みのフィッシング対策ポリシーの構成の詳細については、「 [Configure the default フィッシング対策 policy IN EOP](configure-anti-phishing-policies-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76fc4-111">For information about configuring the more limited built-in anti-phishing policy that's available in Exchange Online Protection organizations (that is, Office 365 organizations without ATP), see [Configure the default anti-phishing policy in EOP](configure-anti-phishing-policies-eop.md).</span></span>

## <a name="atp-anti-phishing-policies-in-the-office-365-security--compliance-center-vs-exchange-online-powershell"></a><span data-ttu-id="76fc4-112">Office 365 セキュリティ & コンプライアンスセンター vs Exchange Online PowerShell での ATP のフィッシング対策ポリシー</span><span class="sxs-lookup"><span data-stu-id="76fc4-112">ATP anti-phishing policies in the Office 365 Security & Compliance Center vs Exchange Online PowerShell</span></span>

<span data-ttu-id="76fc4-113">ATP のフィッシング対策ポリシーの基本的な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="76fc4-113">The basic elements of an ATP anti-phishing policy are:</span></span>

- <span data-ttu-id="76fc4-114">**フィッシングポリシー**: 有効または無効にするフィッシング対策、およびオプションを適用するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-114">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>

- <span data-ttu-id="76fc4-115">**フィッシングルールで**は、フィッシングポリシーの優先順位と受信者フィルター (ポリシーが適用されるユーザー) を指定します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-115">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="76fc4-116">セキュリティ & コンプライアンスセンターで ATP のフィッシング対策ポリシーを管理する場合、次の2つの要素の違いは明白ではありません。</span><span class="sxs-lookup"><span data-stu-id="76fc4-116">The difference between these two elements isn't obvious when you manage ATP anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="76fc4-117">セキュリティ & コンプライアンスセンターで ATP のフィッシング対策ポリシーを作成する場合、実際には、フィッシングルールと関連付けられたフィッシングポリシーを両方に同じ名前を使用して同時に作成しています。</span><span class="sxs-lookup"><span data-stu-id="76fc4-117">When you create an ATP anti-phishing policy in the Security & Compliance Center, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="76fc4-118">セキュリティ & コンプライアンスセンターで ATP のフィッシング対策ポリシーを変更する場合、名前、優先度、有効または無効、および受信者フィルターに関連する設定によってフィッシングルールが変更されます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-118">When you modify an ATP anti-phishing policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="76fc4-119">他のすべての設定は、関連付けられたフィッシングポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-119">All other settings modify the associated anti-phish policy.</span></span>

- <span data-ttu-id="76fc4-120">セキュリティ & コンプライアンスセンターから ATP のフィッシング対策ポリシーを削除すると、フィッシングルールとそれに関連付けられているフィッシングポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-120">When you remove an ATP anti-phishing policy from the Security & Compliance Center, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="76fc4-121">Exchange Online PowerShell では、フィッシングポリシーとフィッシングルールの違いが明らかです。</span><span class="sxs-lookup"><span data-stu-id="76fc4-121">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="76fc4-122">フィッシングポリシーを管理するには、 \*\* \*-get-antiphishpolicy**コマンドレットを使用して、 \*\* \*-new-antiphishrule**コマンドレットを使用してフィッシングルールを管理します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-122">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="76fc4-123">PowerShell では、フィッシングポリシーを最初に作成してから、ルールが適用されるポリシーを識別するフィッシングルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-123">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="76fc4-124">PowerShell では、フィッシングポリシーおよびフィッシングルールの設定を個別に変更します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-124">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>

- <span data-ttu-id="76fc4-125">PowerShell からフィッシングポリシーを削除すると、対応するフィッシングルールは自動的に削除されず、その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="76fc4-125">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-atp-anti-phishing-policy"></a><span data-ttu-id="76fc4-126">既定の ATP のフィッシング対策ポリシー</span><span class="sxs-lookup"><span data-stu-id="76fc4-126">Default ATP anti-phishing policy</span></span>

<span data-ttu-id="76fc4-127">すべての ATP 組織には、以下のプロパティを持つ、Office365 フィッシング対策 Default という組み込みの ATP のフィッシング対策ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="76fc4-127">Every ATP organization has a built-in ATP anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="76fc4-128">Office365 フィッシング対策 Default という名前のフィッシングポリシーは、ポリシーに関連付けられているフィッシングルール (受信者フィルター) がない場合でも、組織内のすべての受信者に適用されます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-128">The anti-phish policy named Office365 AntiPhish Default is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="76fc4-129">Office365 フィッシング対策 Default という名前のポリシーには、変更できないカスタムの優先度の値が**最低**でもあります (ポリシーは常に最後に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="76fc4-129">The policy named Office365 AntiPhish Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="76fc4-130">作成するカスタムポリシーは、常に Office365 フィッシング対策 Default という名前のポリシーよりも高い優先順位を持ちます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-130">Any custom policies that you create always have a higher priority than the policy named Office365 AntiPhish Default.</span></span>

- <span data-ttu-id="76fc4-131">Office365 フィッシング対策 Default という名前のポリシーは既定のポリシーです ( **IsDefault**プロパティに`True`は値があります)。既定のポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="76fc4-131">The policy named Office365 AntiPhish Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="76fc4-132">フィッシング対策保護の有効性を高めるために、特定のユーザーまたはユーザーグループに適用される厳密な設定を使用して、カスタムの ATP のフィッシング対策ポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-132">To increase the effectiveness of anti-phishing protection, you can create custom ATP anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="76fc4-133">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="76fc4-133">What do you need to know before you begin?</span></span>

- <span data-ttu-id="76fc4-134"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-134">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="76fc4-135">**ATP のフィッシング対策**ページに直接移動するには、 <https://protection.office.com/antiphishing>を使用します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-135">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="76fc4-136">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76fc4-136">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="76fc4-137">これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="76fc4-137">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="76fc4-138">フィッシング対策ポリシーを追加、変更、および削除するには、**組織の管理**または**セキュリティ管理者**の役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="76fc4-138">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="76fc4-139">フィッシング対策ポリシーに対する読み取り専用アクセスでは、**セキュリティリーダー**役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="76fc4-139">For read-only access to anti-phishing policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="76fc4-140">セキュリティ & コンプライアンスセンターの役割グループの詳細については、「[セキュリティ & コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76fc4-140">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="76fc4-141">ATP のフィッシング対策ポリシーの推奨設定については、「 [OFFICE ATP のフィッシング対策ポリシーの設定](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76fc4-141">For our recommended settings for ATP anti-phishing policies, see [Office ATP anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="76fc4-142">新規または更新されたポリシーが適用されるまで最大30分かかります。</span><span class="sxs-lookup"><span data-stu-id="76fc4-142">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="76fc4-143">フィルタリングパイプラインにフィッシング対策ポリシーを適用する方法については、「 [Office 365 での電子メール保護の順序と優先順位](how-policies-and-protections-are-combined.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76fc4-143">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection in Office 365](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-atp-anti-phishing-policies"></a><span data-ttu-id="76fc4-144">セキュリティ & コンプライアンスセンターを使用して、ATP のフィッシング対策ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="76fc4-144">Use the Security & Compliance Center to create ATP anti-phishing policies</span></span>

<span data-ttu-id="76fc4-145">セキュリティ & コンプライアンスセンターでカスタムの ATP のフィッシング対策ポリシーを作成すると、フィッシングルールと関連付けられているフィッシングポリシーが両方に同じ名前で同時に作成されます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-145">Creating a custom ATP anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="76fc4-146">ATP のフィッシング対策ポリシーを作成する場合、ポリシー名、説明、およびポリシーの適用先を識別する受信者フィルターのみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-146">When you create an ATP anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="76fc4-147">ポリシーを作成したら、ポリシーを変更して既定のフィッシング対策設定を変更または確認することができます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-147">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="76fc4-148">セキュリティ & コンプライアンスセンターで、[**脅威管理** \> **ポリシー** \> **ATP のフィッシング対策**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-148">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="76fc4-149">[**フィッシング対策**] ページで、[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-149">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="76fc4-150">[**新しいフィッシング対策ポリシーの作成**] ウィザードが開きます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-150">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="76fc4-151">[**ポリシーに名前**をつける] ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-151">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="76fc4-152">**[名前]**: わかりやすい一意のポリシー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="76fc4-153">**[説明]**: ポリシーについての説明を入力します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="76fc4-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="76fc4-154">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="76fc4-155">表示される [**適用先**] ページで、ポリシーが適用される内部の受信者を特定します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-155">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="76fc4-156">各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-156">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="76fc4-157">同じ条件や例外に複数の値がある場合は、OR ロジック (たとえば、_\<recipient1\>_ or _\<recipient2\>_) を使用します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-157">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="76fc4-158">別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ and _\<member of group 1\>_) を使用します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-158">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="76fc4-159">[**条件の追加] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-159">Click **Add a condition**.</span></span> <span data-ttu-id="76fc4-160">表示されるドロップダウンで、[適用済みの**場合**] の条件を選択します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-160">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="76fc4-161">**受信者は**次のとおりです。組織内で1つ以上のメールボックス、メールユーザー、またはメール連絡先を指定します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-161">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="76fc4-162">**受信者が次のメンバーの**場合: 組織内の1つまたは複数のグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-162">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="76fc4-163">**受信者のドメインが次の場合**: Office 365 で構成済みの 1 つ以上の承認済みドメイン内の受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-163">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in Office 365.</span></span>

   <span data-ttu-id="76fc4-164">条件を選択すると、対応するドロップ**ダウンボックスが**表示されます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-164">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="76fc4-165">ボックス内をクリックし、値の一覧をスクロールして選択します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-165">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="76fc4-166">ボックス内をクリックして入力を開始し、リストにフィルターを適用して値を選択します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-166">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="76fc4-167">その他の値を追加するには、ボックスの空の領域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-167">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="76fc4-168">個々のエントリを削除するには、](../../media/scc-remove-icon.png)その値の [削除] アイコン**をクリックし** ![ます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-168">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="76fc4-169">条件全体を削除するには、条件\*\*の [\*\* ![削除] アイコン](../../media/scc-remove-icon.png)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-169">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="76fc4-170">別の条件を追加するには、[**条件の追加**] をクリックし、[**適用**時] で残りの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-170">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="76fc4-171">例外を追加するには、[**条件の追加**] をクリックし、 **Except if**で例外を選択します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-171">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="76fc4-172">設定と動作は、条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="76fc4-172">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="76fc4-173">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-173">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="76fc4-174">表示される [**設定の確認**] ページで、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-174">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="76fc4-175">各設定で [**編集**] をクリックして、変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-175">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="76fc4-176">完了したら、[**このポリシーの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-176">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="76fc4-177">表示される確認ダイアログで [ **OK** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-177">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="76fc4-178">これらの一般的なポリシー設定を使用して ATP のフィッシング対策ポリシーを作成した後、次のセクションの手順を使用して、ポリシーの保護設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-178">After you create the ATP anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-atp-anti-phishing-policies"></a><span data-ttu-id="76fc4-179">セキュリティ & コンプライアンスセンターを使用して ATP のフィッシング対策ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="76fc4-179">Use the Security & Compliance Center to modify ATP anti-phishing policies</span></span>

<span data-ttu-id="76fc4-180">ATP のフィッシング対策ポリシーを変更するには、次の手順を使用します。これは、作成した新しいポリシー、または既にカスタマイズした既存のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="76fc4-180">Use the following procedures to modify ATP anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="76fc4-181">まだ存在しない場合は、セキュリティ & コンプライアンスセンターを開き、[**脅威管理** \> **ポリシー** \> ] **ATP のフィッシング対策**に移動します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-181">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="76fc4-182">変更するカスタムの ATP のフィッシング対策ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-182">Select the custom ATP anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="76fc4-183">既に選択されている場合は、選択を解除してもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-183">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="76fc4-184">[**ポリシー \<名\>の編集**フライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-184">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="76fc4-185">いずれかのセクションで [**編集**] をクリックすると、そのセクションの設定にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-185">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="76fc4-186">次の手順は、セクションが表示される順序で示されていますが、連続していません (任意の順序でセクションを選択して変更することができます)。</span><span class="sxs-lookup"><span data-stu-id="76fc4-186">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="76fc4-187">セクションで [**編集**] をクリックすると、使用可能な設定がウィザード形式で表示されますが、ページ内を任意の順序で移動できます **。または** **Close** ![](../../media/scc-remove-icon.png) 、[任意のページに**保存**] をクリックして、[ \*\* \<ポリシー\>名の編集\*\*] ページに戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-187">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="76fc4-188">**ポリシー設定**: [**編集**] をクリックして、前のセクションで[ポリシーを作成](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies)したときに使用したものと同じ設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-188">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="76fc4-189">**名前**</span><span class="sxs-lookup"><span data-stu-id="76fc4-189">**Name**</span></span>
   - <span data-ttu-id="76fc4-190">**説明**</span><span class="sxs-lookup"><span data-stu-id="76fc4-190">**Description**</span></span>
   - <span data-ttu-id="76fc4-191">**適用先**</span><span class="sxs-lookup"><span data-stu-id="76fc4-191">**Applied to**</span></span>
   - <span data-ttu-id="76fc4-192">**設定を確認する**</span><span class="sxs-lookup"><span data-stu-id="76fc4-192">**Review your settings**</span></span>

   <span data-ttu-id="76fc4-193">完了したら、[任意のページに**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-193">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="76fc4-194">**偽装**: [**編集**] をクリックして、ポリシー内の保護された送信者と保護されたドメインを変更します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-194">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="76fc4-195">これらの設定は、受信メッセージの From アドレスで (個別またはドメインによって) 検索するスプーフィングされた送信者を識別するポリシーの条件です。</span><span class="sxs-lookup"><span data-stu-id="76fc4-195">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="76fc4-196">詳細については、「 [ATP のフィッシング対策ポリシー」の「偽装設定](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76fc4-196">For more information, see [Impersonation settings in ATP anti-phishing policies](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="76fc4-197">**保護するユーザーを追加する**: 既定値は**Off**です。</span><span class="sxs-lookup"><span data-stu-id="76fc4-197">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="76fc4-198">これをオンにするには、トグルを **[オン**] にして、表示される [**ユーザーの追加**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-198">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="76fc4-199">[**ユーザーの追加**] ポップアップが表示されたら、次の値を構成します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-199">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="76fc4-200">**メールアドレス**:</span><span class="sxs-lookup"><span data-stu-id="76fc4-200">**Email address**:</span></span>

        - <span data-ttu-id="76fc4-201">ボックス内をクリックし、ユーザーの一覧をスクロールして選択します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-201">Click in the box and scroll through the list of users to select.</span></span>
        - <span data-ttu-id="76fc4-202">ボックス内をクリックして入力を開始し、リストにフィルターを適用してユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-202">Click in the box and start typing to filter the list and select a user.</span></span>
        - <span data-ttu-id="76fc4-203">エントリを削除するには、ユーザーの](../../media/scc-remove-icon.png) **[削除] アイコンをクリックし** ![ます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-203">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="76fc4-204">**Name**: この値は、選択したメールアドレスに基づいて設定されますが、変更することができます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-204">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="76fc4-205">完了したら、[任意のページに**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-205">When you're finished, click **Save** on any page.</span></span>

    <span data-ttu-id="76fc4-206">既存のエントリを編集するには、一覧で保護されたユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-206">To edit an existing entry, select the protected user in the list.</span></span>

   - <span data-ttu-id="76fc4-207">**保護するドメインを追加する**: 次の設定の1つまたは両方を構成します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-207">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="76fc4-208">**自分が所有するドメインを自動的に追加**する: 既定値は**Off**です。</span><span class="sxs-lookup"><span data-stu-id="76fc4-208">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="76fc4-209">これをオンにするには、トグルを **[オン**] にします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-209">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="76fc4-210">**カスタムドメインを含める**: 既定値は**Off**です。</span><span class="sxs-lookup"><span data-stu-id="76fc4-210">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="76fc4-211">これをオンにするには、トグルを **[オン**] にして、[**ドメインの追加**] ボックスにドメイン名 (contoso.com など) を入力し、enter キーを押して、必要に応じて繰り返します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-211">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="76fc4-212">**アクション**: [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-212">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="76fc4-213">**偽装ユーザーによって電子メールが送信**される場合: スプーフィングされた送信者が、[**保護するユーザーの追加**] で指定した保護されたユーザーのいずれかであるメッセージに対して、次のいずれかのアクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-213">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="76fc4-214">**どの操作も適用しない**</span><span class="sxs-lookup"><span data-stu-id="76fc4-214">**Don't apply any action**</span></span>
       - <span data-ttu-id="76fc4-215">**他の電子メールアドレスへのメッセージのリダイレクト**</span><span class="sxs-lookup"><span data-stu-id="76fc4-215">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="76fc4-216">**迷惑メールフォルダーにメッセージを移動する**</span><span class="sxs-lookup"><span data-stu-id="76fc4-216">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="76fc4-217">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="76fc4-217">**Quarantine the message**</span></span>
       - <span data-ttu-id="76fc4-218">**メッセージを配信し、その他のアドレスを Bcc 行に追加する**</span><span class="sxs-lookup"><span data-stu-id="76fc4-218">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="76fc4-219">**配信前にメッセージを削除する**</span><span class="sxs-lookup"><span data-stu-id="76fc4-219">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="76fc4-220">**偽装ドメインによって電子メールが送信**される場合: スプーフィングされた送信者が、**保護するドメインの追加**で指定した保護されたドメインのいずれかにあるメッセージに対して、次のいずれかのアクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-220">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

     - <span data-ttu-id="76fc4-221">**どの操作も適用しない**</span><span class="sxs-lookup"><span data-stu-id="76fc4-221">**Don't apply any action**</span></span>
     - <span data-ttu-id="76fc4-222">**他の電子メールアドレスへのメッセージのリダイレクト**</span><span class="sxs-lookup"><span data-stu-id="76fc4-222">**Redirect message to other email addresses**</span></span>
     - <span data-ttu-id="76fc4-223">**迷惑メールフォルダーにメッセージを移動する**</span><span class="sxs-lookup"><span data-stu-id="76fc4-223">**Move message to Junk Email folder**</span></span>
     - <span data-ttu-id="76fc4-224">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="76fc4-224">**Quarantine the message**</span></span>
     - <span data-ttu-id="76fc4-225">**メッセージを配信し、その他のアドレスを Bcc 行に追加する**</span><span class="sxs-lookup"><span data-stu-id="76fc4-225">**Deliver the message and add other addresses to the Bcc line**</span></span>
     - <span data-ttu-id="76fc4-226">**配信前にメッセージを削除する**</span><span class="sxs-lookup"><span data-stu-id="76fc4-226">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="76fc4-227">[**偽装の安全性のヒントを有効にする**] をクリックし、次のいずれかの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-227">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="76fc4-228">**偽装ユーザーのヒントを表示する**: 既定値は**Off**です。</span><span class="sxs-lookup"><span data-stu-id="76fc4-228">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="76fc4-229">これをオンにするには、トグルを **[オン**] にします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-229">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="76fc4-230">**偽装ドメインのヒントを表示する**: 既定値は**Off**です。</span><span class="sxs-lookup"><span data-stu-id="76fc4-230">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="76fc4-231">これをオンにするには、トグルを **[オン**] にします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-231">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="76fc4-232">**通常の文字にヒントを表示**する: 既定値は**Off**です。</span><span class="sxs-lookup"><span data-stu-id="76fc4-232">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="76fc4-233">これをオンにするには、トグルを **[オン**] にします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-233">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="76fc4-234">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-234">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="76fc4-235">**メールボックスインテリジェンス**:</span><span class="sxs-lookup"><span data-stu-id="76fc4-235">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="76fc4-236">**メールボックスインテリジェンスを有効に**しますか。既定値は **[オン**] です。</span><span class="sxs-lookup"><span data-stu-id="76fc4-236">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="76fc4-237">この機能をオフにするには、トグルを [**オフ**] にします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-237">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="76fc4-238">**[\*\*\*\*メールボックスインテリジェンスベースの偽装保護を有効にする]**: この設定は、**メールボックスインテリジェンスを有効にする**場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-238">**Enable mailbox intelligence based impersonation protection?**: This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="76fc4-239">で**偽装ユーザーによって電子メールが送信**された場合は、メールボックスインテリジェンスに失敗したメッセージに対して次のいずれかの操作を行うことができます (保護されたユーザーと保護されたドメインに対して使用可能なものと同じもの)。</span><span class="sxs-lookup"><span data-stu-id="76fc4-239">In **If email is sent by an impersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="76fc4-240">**どの操作も適用しない**</span><span class="sxs-lookup"><span data-stu-id="76fc4-240">**Don't apply any action**</span></span>
       - <span data-ttu-id="76fc4-241">**他の電子メールアドレスへのメッセージのリダイレクト**</span><span class="sxs-lookup"><span data-stu-id="76fc4-241">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="76fc4-242">**迷惑メールフォルダーにメッセージを移動する**</span><span class="sxs-lookup"><span data-stu-id="76fc4-242">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="76fc4-243">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="76fc4-243">**Quarantine the message**</span></span>
       - <span data-ttu-id="76fc4-244">**メッセージを配信し、その他のアドレスを Bcc 行に追加する**</span><span class="sxs-lookup"><span data-stu-id="76fc4-244">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="76fc4-245">**配信前にメッセージを削除する**</span><span class="sxs-lookup"><span data-stu-id="76fc4-245">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="76fc4-246">**信頼できる差出人とドメインを追加**する: ポリシーの例外を指定します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-246">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="76fc4-247">**信頼できる送信者**:</span><span class="sxs-lookup"><span data-stu-id="76fc4-247">**Trusted senders**:</span></span>

       - <span data-ttu-id="76fc4-248">ボックス内をクリックし、ユーザーの一覧をスクロールして選択します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-248">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="76fc4-249">ボックス内をクリックして入力を開始し、リストにフィルターを適用してユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-249">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="76fc4-250">エントリを削除するには、ユーザーの](../../media/scc-remove-icon.png) **[削除] アイコンをクリックし** ![ます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-250">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="76fc4-251">[**信頼されたドメイン**]: ドメイン名 (たとえば、contoso.com) を入力し、enter キーを押して、必要に応じて繰り返します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-251">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="76fc4-252">**設定を確認**します。個々の手順をクリックする代わりに、設定が概要で表示されます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-252">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="76fc4-253">各セクションで [**編集**] をクリックすると、関連するページに戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-253">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="76fc4-254">このページでは、次の設定の**オン**と**オフ**を直接切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-254">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="76fc4-255">**保護されたユーザー**</span><span class="sxs-lookup"><span data-stu-id="76fc4-255">**Protected users**</span></span>
       - <span data-ttu-id="76fc4-256">**保護されたドメイン** \>に**は、所有しているドメインが含ま**れる</span><span class="sxs-lookup"><span data-stu-id="76fc4-256">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="76fc4-257">保護された**ドメイン** \> **保護された**ドメイン (カスタムドメイン)</span><span class="sxs-lookup"><span data-stu-id="76fc4-257">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="76fc4-258">**メールボックス インテリジェンス**</span><span class="sxs-lookup"><span data-stu-id="76fc4-258">**Mailbox intelligence**</span></span>

   <span data-ttu-id="76fc4-259">完了したら、[任意のページに**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-259">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="76fc4-260">**スプーフィング**: [**編集**] をクリックして、スプーフィングインテリジェンスを有効または無効にしたり、Outlook で認証されていない送信者の識別をオンまたはオフにしたり、ブロックされたスプーフィングされた送信者からのメッセージに適用するアクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-260">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="76fc4-261">詳細については、「[フィッシング対策ポリシーのスプーフィング設定](set-up-anti-phishing-policies.md#spoof-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76fc4-261">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="76fc4-262">これらの設定は、EOP の既定のフィッシング対策ポリシーで使用可能な設定と同一であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="76fc4-262">Note that these settings are identical to the settings that are available in the default anti-phishing policy in EOP.</span></span>

   - <span data-ttu-id="76fc4-263">**フィルター設定のスプーフィング**: 既定値は**on**で、そのままにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-263">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="76fc4-264">この機能をオフにするには、トグルを [**オフ**] にします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-264">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="76fc4-265">詳細については、「[Office 365 でのスプーフィング インテリジェンスの構成](learn-about-spoof-intelligence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76fc4-265">For more information, see [Configure spoof intelligence in Office 365](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="76fc4-266">MX レコードが Office 365 を指していない場合は、スプーフィング対策保護を無効にする必要はありません。代わりに、コネクタの拡張フィルターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-266">You don't need to disable anti-spoofing protection if your MX record doesn't point to Office 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="76fc4-267">手順については、「 [Exchange Online のコネクタの拡張フィルター処理](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76fc4-267">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="76fc4-268">[認証されていない**送信者の機能を有効にする**]: 既定値は **[オン**] です。</span><span class="sxs-lookup"><span data-stu-id="76fc4-268">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="76fc4-269">この機能をオフにするには、トグルを [**オフ**] にします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-269">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="76fc4-270">**アクション**: スプーフィングインテリジェンスに失敗したメッセージに対して実行するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-270">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="76fc4-271">**ドメインのスプーフィングが許可されていないユーザーによって電子メールが送信**される場合:</span><span class="sxs-lookup"><span data-stu-id="76fc4-271">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="76fc4-272">**受信者の迷惑メールフォルダーにメッセージを移動する**</span><span class="sxs-lookup"><span data-stu-id="76fc4-272">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="76fc4-273">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="76fc4-273">**Quarantine the message**</span></span>

   - <span data-ttu-id="76fc4-274">**設定を確認**します。個々の手順をクリックする代わりに、設定が概要で表示されます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-274">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="76fc4-275">各セクションで [**編集**] をクリックすると、関連するページに戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-275">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="76fc4-276">このページでは、次の設定の**オン**と**オフ**を直接切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-276">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="76fc4-277">**スプーフィング対策保護を有効にする**</span><span class="sxs-lookup"><span data-stu-id="76fc4-277">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="76fc4-278">**認証されていない送信者機能を有効にする**</span><span class="sxs-lookup"><span data-stu-id="76fc4-278">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="76fc4-279">完了したら、[任意のページに**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-279">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="76fc4-280">**詳細設定**: [**編集**] をクリックして、詳細なフィッシングしきい値を構成します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-280">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="76fc4-281">詳細については、「 [ATP のフィッシング対策ポリシー」の「Advanced フィッシングしきい値](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76fc4-281">For more information, see [Advanced phishing thresholds in ATP anti-phishing policies](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="76fc4-282">**[Advanced フィッシングしきい**値]: 次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-282">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="76fc4-283">**1-標準**(これは既定値です)</span><span class="sxs-lookup"><span data-stu-id="76fc4-283">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="76fc4-284">**2-アグレッシブ**</span><span class="sxs-lookup"><span data-stu-id="76fc4-284">**2 - Aggressive**</span></span>
   - <span data-ttu-id="76fc4-285">**3つ以上のアグレッシブ**</span><span class="sxs-lookup"><span data-stu-id="76fc4-285">**3 - More aggressive**</span></span>
   - <span data-ttu-id="76fc4-286">**4-最も積極的**</span><span class="sxs-lookup"><span data-stu-id="76fc4-286">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="76fc4-287">**設定を確認**します。 [**編集**] をクリックすると、[**詳細なフィッシングのしきい値**] ページに戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-287">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="76fc4-288">完了したら、[どちらかのページで**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-288">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="76fc4-289">[**ポリシー \<名\>の編集**] ページに戻り、設定を確認してから、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-289">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-atp-anti-phishing-policy"></a><span data-ttu-id="76fc4-290">セキュリティ & コンプライアンスセンターを使用して既定の ATP のフィッシング対策ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="76fc4-290">Use the Security & Compliance Center to modify the default ATP anti-phishing policy</span></span>

<span data-ttu-id="76fc4-291">既定の ATP のフィッシング対策ポリシーの名前は、Office365 フィッシング対策 Default で、ポリシーの一覧には表示されません。</span><span class="sxs-lookup"><span data-stu-id="76fc4-291">The default ATP anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="76fc4-292">既定の ATP のフィッシング対策ポリシーを変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-292">To modify the default ATP anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="76fc4-293">セキュリティ & コンプライアンスセンターで、[**脅威管理** \> **ポリシー** \> **ATP のフィッシング対策**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-293">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="76fc4-294">[**フィッシング対策**] ページで、[**既定のポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-294">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="76fc4-295">[**ポリシーの Office 365 フィッシング対策の既定の編集**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-295">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="76fc4-296">次のセクションを使用できます。これには、[カスタムポリシーを変更](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies)するときに、同一の設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="76fc4-296">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):</span></span>

   - <span data-ttu-id="76fc4-297">**偽装**</span><span class="sxs-lookup"><span data-stu-id="76fc4-297">**Impersonation**</span></span>
   - <span data-ttu-id="76fc4-298">**なりすます**</span><span class="sxs-lookup"><span data-stu-id="76fc4-298">**Spoof**</span></span>
   - <span data-ttu-id="76fc4-299">**詳細設定**</span><span class="sxs-lookup"><span data-stu-id="76fc4-299">**Advanced settings**</span></span>

   <span data-ttu-id="76fc4-300">次の設定は、既定のポリシーを変更するときには使用できません。</span><span class="sxs-lookup"><span data-stu-id="76fc4-300">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="76fc4-301">**ポリシー設定**のセクションと値は表示できますが、**編集**リンクはありません。そのため、設定 (ポリシー名、説明、ポリシーの適用先 (すべての受信者に適用)) を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="76fc4-301">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="76fc4-302">既定のポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="76fc4-302">You can't delete the default policy.</span></span>
   - <span data-ttu-id="76fc4-303">既定のポリシーの優先度を変更することはできません (常に最後に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="76fc4-303">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="76fc4-304">[ **Policy The Office365 フィッシング対策 Default** ] ページで、設定を確認し、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-304">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-atp-anti-phishing-policies"></a><span data-ttu-id="76fc4-305">カスタム ATP フィッシング対策ポリシーを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="76fc4-305">Enable or disable custom ATP anti-phishing policies</span></span>

1. <span data-ttu-id="76fc4-306">セキュリティ & コンプライアンスセンターで、[**脅威管理** \> **ポリシー** \> **ATP のフィッシング対策**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-306">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="76fc4-307">[**状態**] 列の値に注目してください。</span><span class="sxs-lookup"><span data-stu-id="76fc4-307">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="76fc4-308">トグルを [**オフ**] にして、ポリシーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-308">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="76fc4-309">トグルに切り替えて、**ポリシーを有効**にします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-309">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="76fc4-310">既定のフィッシング対策ポリシーを無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="76fc4-310">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-atp-anti-phishing-policies"></a><span data-ttu-id="76fc4-311">カスタム ATP フィッシング対策ポリシーの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="76fc4-311">Set the priority of custom ATP anti-phishing policies</span></span>

<span data-ttu-id="76fc4-312">既定では、ATP のフィッシング対策ポリシーには、作成された順序に基づく優先度が与えられます (新しいポリシーは、以前のポリシーよりも優先度が低いです)。</span><span class="sxs-lookup"><span data-stu-id="76fc4-312">By default, ATP anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="76fc4-313">優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。</span><span class="sxs-lookup"><span data-stu-id="76fc4-313">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="76fc4-314">2 つのポリシーが同じ優先度を持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="76fc4-314">No two policies can have the same priority.</span></span>

<span data-ttu-id="76fc4-315">カスタム ATP のフィッシング対策ポリシーは、処理順に表示されます (最初のポリシーの**優先度**値は0になります)。</span><span class="sxs-lookup"><span data-stu-id="76fc4-315">Custom ATP anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="76fc4-316">Office365 フィッシング対策 Default という既定のフィッシング対策ポリシーは、カスタムの優先度の値を**最小**にし、それを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="76fc4-316">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="76fc4-317">**注**: セキュリティ & コンプライアンスセンターでは、作成後に ATP のフィッシング対策ポリシーの優先度のみを変更できます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-317">**Note**: In the Security & Compliance Center, you can only change the priority of the ATP anti-phishing policy after you create it.</span></span> <span data-ttu-id="76fc4-318">PowerShell では、フィッシングルールを作成するときに既定の優先順位を上書きできます (既存のルールの優先度に影響する場合があります)。</span><span class="sxs-lookup"><span data-stu-id="76fc4-318">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="76fc4-319">ポリシーの優先度を変更するには、ポリシーのプロパティで [**優先度を上げる**] または [**優先度を下げる**] をクリックします (セキュリティ & コンプライアンスセンターで**優先度**を直接変更することはできません)。</span><span class="sxs-lookup"><span data-stu-id="76fc4-319">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="76fc4-320">ポリシーの優先度を変更することは、複数のポリシーがある場合にのみ有効になります。</span><span class="sxs-lookup"><span data-stu-id="76fc4-320">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="76fc4-321">セキュリティ & コンプライアンスセンターで、[**脅威管理** \> **ポリシー** \> **ATP のフィッシング対策**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-321">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="76fc4-322">変更するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-322">Select the policy that you want to modify.</span></span> <span data-ttu-id="76fc4-323">既に選択されている場合は、選択を解除してもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-323">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="76fc4-324">[**ポリシー \<名\>の編集**フライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-324">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="76fc4-325">**優先順位**の値が**0**のカスタム ATP のフィッシング対策ポリシーでは、[**優先度を下げる**] ボタンのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-325">The custom ATP anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="76fc4-326">**優先度**の低い値 (たとえば**3**) を持つカスタム ATP のフィッシング対策ポリシーには、[**優先度を上げる**] ボタンだけが使用できます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-326">The custom ATP anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="76fc4-327">3つ以上のカスタムのマルウェア対策ポリシーを所有している場合、最高の優先度と最も低い優先度の値の間のポリシーでは、[優先度を**上げる**] ボタンと [**優先度を下げる**] ボタンの両方を使用できます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-327">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="76fc4-328">[優先**度を上げる**] または [**優先度を下げる**] をクリックし、**優先度**の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-328">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="76fc4-329">完了したら、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-329">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-atp-anti-phishing-policies"></a><span data-ttu-id="76fc4-330">セキュリティ & コンプライアンスセンターを使用して、ATP のフィッシング対策ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="76fc4-330">Use the Security & Compliance Center to view ATP anti-phishing policies</span></span>

1. <span data-ttu-id="76fc4-331">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー** \> **ATP のフィッシング対策**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-331">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="76fc4-332">次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-332">Do one of the following steps:</span></span>

   - <span data-ttu-id="76fc4-333">表示するカスタムの ATP のフィッシング対策ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-333">Select a custom ATP anti-phishing policy that you want to view.</span></span> <span data-ttu-id="76fc4-334">既に選択されている場合は、選択を解除してもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-334">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="76fc4-335">[**既定のポリシー** ] をクリックして、既定のフィッシング対策ポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-335">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="76fc4-336">[ \*\* \<ポリシー名\>の編集\*\*] ポップアップが表示され、設定と値を確認できます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-336">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-atp-anti-phishing-policies"></a><span data-ttu-id="76fc4-337">セキュリティ & コンプライアンスセンターを使用して、ATP のフィッシング対策ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="76fc4-337">Use the Security & Compliance Center to remove ATP anti-phishing policies</span></span>

1. <span data-ttu-id="76fc4-338">セキュリティ & コンプライアンスセンターで、[**脅威管理** \> **ポリシー** \> **ATP のフィッシング対策**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-338">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="76fc4-339">削除するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-339">Select the policy that you want to remove.</span></span> <span data-ttu-id="76fc4-340">既に選択されている場合は、選択を解除してもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-340">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="76fc4-341">表示される [**ポリシー \<名\>の編集**] ポップアップで、[**ポリシーの削除**] をクリックし、表示される警告ダイアログボックスで [**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-341">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="76fc4-342">既定のポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="76fc4-342">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-atp-anti-phishing-policies"></a><span data-ttu-id="76fc4-343">Exchange Online PowerShell を使用して ATP のフィッシング対策ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="76fc4-343">Use Exchange Online PowerShell to configure ATP anti-phishing policies</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="76fc4-344">PowerShell を使用してフィッシング対策ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="76fc4-344">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="76fc4-345">PowerShell でのフィッシング対策ポリシーの作成は、次の2つの手順からなるプロセスです。</span><span class="sxs-lookup"><span data-stu-id="76fc4-345">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="76fc4-346">フィッシングポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-346">Create the anti-phish policy.</span></span>

2. <span data-ttu-id="76fc4-347">ルールが適用されるフィッシングポリシーを指定するフィッシングルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-347">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="76fc4-348">**注**:</span><span class="sxs-lookup"><span data-stu-id="76fc4-348">**Notes**:</span></span>

- <span data-ttu-id="76fc4-349">新しいフィッシングルールを作成し、関連付けられていない既存のアンチフィッシングポリシーをそのルールに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-349">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="76fc4-350">フィッシングルールは、複数のフィッシングポリシーに関連付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="76fc4-350">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="76fc4-351">次の設定は、ポリシーを作成するまではセキュリティ & コンプライアンスセンターでは使用できない PowerShell の新しいフィッシングポリシーで構成できます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-351">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="76fc4-352">新しいポリシーを無効として作成します ( **new-antiphishrule**コマンドレットでは_有効_ `$false` )。</span><span class="sxs-lookup"><span data-stu-id="76fc4-352">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>

  - <span data-ttu-id="76fc4-353">**New-antiphishrule**コマンドレットで、作成中にポリシーの優先度を設定します (_優先度_ _ \<番号\>_)。</span><span class="sxs-lookup"><span data-stu-id="76fc4-353">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="76fc4-354">PowerShell で作成した新しいフィッシングポリシーは、ポリシーをフィッシングルールに割り当てるまで、セキュリティ & コンプライアンスセンターに表示されません。</span><span class="sxs-lookup"><span data-stu-id="76fc4-354">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="76fc4-355">手順 1: PowerShell を使用してフィッシングポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="76fc4-355">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="76fc4-356">フィッシングポリシーを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-356">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="76fc4-357">この例では、次の設定を使用して Research Quarantine という名前のフィッシングポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-357">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="76fc4-358">このポリシーは有効になっています ( _enabled_パラメーターは使用してい`$true`ません。既定値はです)。</span><span class="sxs-lookup"><span data-stu-id="76fc4-358">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="76fc4-359">説明は、「研究部門のポリシー」です。</span><span class="sxs-lookup"><span data-stu-id="76fc4-359">The description is: Research department policy.</span></span>
- <span data-ttu-id="76fc4-360">すべての承認済みドメインに対する組織ドメインの保護と、fabrikam.com の対象となるドメインの保護を有効にします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-360">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="76fc4-361">偽装から保護するユーザーとして Mai Fujito (mfujito@fabrikam.com) を指定します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-361">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="76fc4-362">メールボックスのインテリジェンスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-362">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="76fc4-363">メールボックスインテリジェンス保護を有効にし、検疫アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-363">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="76fc4-364">安全のヒントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-364">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Default monitoring policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="76fc4-365">構文およびパラメーターの詳細については、「 [get-antiphishpolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishPolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76fc4-365">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="76fc4-366">手順 2: PowerShell を使用してフィッシングルールを作成する</span><span class="sxs-lookup"><span data-stu-id="76fc4-366">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="76fc4-367">フィッシングルールを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-367">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="76fc4-368">この例では、次の条件を使用して Research Department という名前のフィッシングルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-368">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="76fc4-369">ルールは、Research Quarantine という名前のフィッシングポリシーに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="76fc4-369">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="76fc4-370">ルールは Research Department という名前のグループのメンバーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-370">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="76fc4-371">_Priority_パラメーターを使用していないので、既定の優先度が使用されます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-371">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="76fc4-372">構文およびパラメーターの詳細については、「 [new-antiphishrule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishRule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76fc4-372">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="76fc4-373">PowerShell を使用してフィッシングのポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="76fc4-373">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="76fc4-374">既存のフィッシングポリシーを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-374">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="76fc4-375">この例では、指定されたプロパティと共にすべてのフィッシングポリシーの要約リストを返します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-375">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="76fc4-376">この例では、"重役" という名前のフィッシングポリシーのすべてのプロパティ値を返します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-376">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="76fc4-377">構文およびパラメーターの詳細については、「 [get-antiphishpolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76fc4-377">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="76fc4-378">PowerShell を使用してフィッシングのルールを表示する</span><span class="sxs-lookup"><span data-stu-id="76fc4-378">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="76fc4-379">既存のフィッシングルールを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-379">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="76fc4-380">この例では、指定したプロパティと共に、フィッシングのすべてのルールの要約リストを返します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-380">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="76fc4-381">ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-381">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="76fc4-382">この例では、Contoso 重役という名前のフィッシングルールのすべてのプロパティ値を返します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-382">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="76fc4-383">構文およびパラメーターの詳細については、「 [new-antiphishrule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76fc4-383">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="76fc4-384">PowerShell を使用してフィッシングポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="76fc4-384">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="76fc4-385">このトピックで前述したように、「[手順 1: powershell を使用してフィッシングポリシーを作成する](#step-1-use-powershell-to-create-an-anti-phish-policy)」で説明されているように、ポリシーの作成時に powershell のフィッシングポリシーを変更する場合は、次の項目以外にも同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-385">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="76fc4-386">指定されたポリシーを既定のポリシー (すべてのユーザーに適用して、常に**最下位**の優先度を適用し、削除することはできません) に変更する_makedefault_スイッチは、PowerShell のフィッシングポリシーを変更する場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-386">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="76fc4-387">フィッシングポリシーの名前を変更することはできません ( **get-antiphishpolicy**コマンドレットには_Name_パラメーターがありません)。</span><span class="sxs-lookup"><span data-stu-id="76fc4-387">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="76fc4-388">セキュリティ & コンプライアンスセンターでフィッシング対策ポリシーの名前を変更する場合、フィッシング_ルール_の名前のみを変更しています。</span><span class="sxs-lookup"><span data-stu-id="76fc4-388">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="76fc4-389">フィッシングポリシーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-389">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="76fc4-390">構文およびパラメーターの詳細については、「 [get-antiphishpolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76fc4-390">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="76fc4-391">PowerShell を使用してフィッシングルールを変更する</span><span class="sxs-lookup"><span data-stu-id="76fc4-391">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="76fc4-392">PowerShell でフィッシングルールを変更するときには使用できない唯一の設定は、無効にされたルールを作成できる_有効_なパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="76fc4-392">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="76fc4-393">既存のフィッシングルールを有効または無効にするには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="76fc4-393">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="76fc4-394">それ以外の場合は、PowerShell でフィッシングルールを変更しても、追加の設定は使用できません。</span><span class="sxs-lookup"><span data-stu-id="76fc4-394">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="76fc4-395">このトピックで前述した「[手順 2: PowerShell を使用してフィッシングルールを作成する](#step-2-use-powershell-to-create-an-anti-phish-rule)」で説明されているように、ルールを作成する場合にも同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-395">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="76fc4-396">フィッシングルールを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-396">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="76fc4-397">構文およびパラメーターの詳細については、「 [new-antiphishrule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76fc4-397">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="76fc4-398">PowerShell を使用してフィッシングルールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="76fc4-398">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="76fc4-399">PowerShell でフィッシングルールを有効または無効にすると、フィッシング対策ポリシー全体 (フィッシングルールおよび割り当てられたフィッシングポリシー) が有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="76fc4-399">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="76fc4-400">既定のフィッシング対策ポリシーを有効または無効にすることはできません (常にすべての受信者に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="76fc4-400">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="76fc4-401">PowerShell でフィッシングルールを有効または無効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-401">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="76fc4-402">この例では、Marketing Department という名前のフィッシングルールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="76fc4-402">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="76fc4-403">この例では、同じルールを有効化します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-403">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="76fc4-404">構文およびパラメーターの詳細については、「 [new-antiphishrule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/enable-AntiPhishrule) 」および「 [Disable-new-antiphishrule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/disable-AntiPhishrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76fc4-404">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/enable-AntiPhishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/disable-AntiPhishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="76fc4-405">PowerShell を使用してフィッシングルールの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="76fc4-405">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="76fc4-406">ルールに設定できる優先度の最高値値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="76fc4-406">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="76fc4-407">設定できる最低値はルールの数に依存します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-407">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="76fc4-408">たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。</span><span class="sxs-lookup"><span data-stu-id="76fc4-408">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="76fc4-409">既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-409">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="76fc4-410">たとえば、カスタム ルールが 5 つあって (優先度 0 から 4)、1 つのルールの優先度を 2 に変更した場合には、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。</span><span class="sxs-lookup"><span data-stu-id="76fc4-410">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="76fc4-411">PowerShell でフィッシングルールの優先度を設定するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-411">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="76fc4-p144">この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。</span><span class="sxs-lookup"><span data-stu-id="76fc4-p144">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="76fc4-414">**注**:</span><span class="sxs-lookup"><span data-stu-id="76fc4-414">**Notes**:</span></span>

- <span data-ttu-id="76fc4-415">新しいルールの作成時に優先度を設定するには、代わりに**new-antiphishrule**コマンドレットで_priority_パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-415">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="76fc4-416">既定のフィッシングポリシーには、対応するフィッシングルールが設定されておらず、常に未設定の優先度の値が**最低**になっています。</span><span class="sxs-lookup"><span data-stu-id="76fc4-416">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="76fc4-417">PowerShell を使用してフィッシングポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="76fc4-417">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="76fc4-418">PowerShell を使用してフィッシングポリシーを削除しても、対応するフィッシングルールは削除されません。</span><span class="sxs-lookup"><span data-stu-id="76fc4-418">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="76fc4-419">PowerShell でフィッシングポリシーを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-419">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="76fc4-420">この例では、Marketing Department という名前のフィッシングポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-420">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="76fc4-421">構文およびパラメーターの詳細については、「 [get-antiphishpolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishPolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76fc4-421">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="76fc4-422">PowerShell を使用してフィッシングルールを削除する</span><span class="sxs-lookup"><span data-stu-id="76fc4-422">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="76fc4-423">PowerShell を使用してフィッシングルールを削除しても、対応するフィッシングポリシーは削除されません。</span><span class="sxs-lookup"><span data-stu-id="76fc4-423">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="76fc4-424">PowerShell でフィッシングルールを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-424">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="76fc4-425">この例では、Marketing Department という名前のフィッシングルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-425">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="76fc4-426">構文およびパラメーターの詳細については、「 [new-antiphishrule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishRule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76fc4-426">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="76fc4-427">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="76fc4-427">How do you know these procedures worked?</span></span>

<span data-ttu-id="76fc4-428">ATP のフィッシング対策ポリシーが正常に構成されたことを確認するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-428">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="76fc4-429">セキュリティ & コンプライアンスセンターで、[**脅威管理** \> **ポリシー** \> **ATP のフィッシング対策**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-429">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="76fc4-430">ポリシーの一覧、その**状態**の値、およびその**優先度**の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-430">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="76fc4-431">詳細を表示するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-431">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="76fc4-432">リストからポリシーを選択し、フライアウトの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-432">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="76fc4-433">[**既定のポリシー** ] をクリックして、フライアウトの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-433">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="76fc4-434">Exchange Online PowerShell で、name \<\>をポリシーまたはルールの名前に置き換えて、次のコマンドを実行し、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="76fc4-434">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
