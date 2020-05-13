---
title: EOP でフィッシング対策ポリシーを構成する
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
description: 管理者は、exchange online Protection (EOP) 組織で使用可能なフィッシング対策ポリシーを作成、変更、および削除する方法について説明します。 Exchange Online のメールボックスは使用できません。
ms.openlocfilehash: 5c2e036c075072056e7783ca4dc5aeb1289d827a
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213390"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="0512c-103">EOP でフィッシング対策ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="0512c-103">Configure anti-phishing policies in EOP</span></span>

<span data-ttu-id="0512c-104">Exchange online またはスタンドアロンの exchange Online Protection (EOP) 組織内のメールボックスを使用する Microsoft 365 組織では、Exchange Online メールボックスを使用していない場合、既定で有効になっている一部のスプーフィング対策機能が含まれている既定のフィッシング対策ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="0512c-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="0512c-105">詳細については、「[フィッシング対策ポリシーのスプーフィング設定](set-up-anti-phishing-policies.md#spoof-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0512c-105">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="0512c-106">管理者は、既定のフィッシング対策ポリシーを表示、編集、および構成できます (削除することはできません)。</span><span class="sxs-lookup"><span data-stu-id="0512c-106">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="0512c-107">よりきめ細かく制御する場合は、組織内の特定のユーザー、グループ、またはドメインに適用するカスタムのフィッシング対策ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="0512c-107">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="0512c-108">カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (実行順序) を変更できます。</span><span class="sxs-lookup"><span data-stu-id="0512c-108">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="0512c-109">Exchange Online メールボックスを使用する組織は、セキュリティ & コンプライアンスセンターまたは Exchange Online PowerShell でフィッシング対策ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="0512c-109">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="0512c-110">スタンドアロン EOP 組織は、セキュリティ & コンプライアンスセンターのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0512c-110">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="0512c-111">Office 365 Advanced Threat Protection (Office 365 ATP) で利用可能な、より高度な ATP のフィッシング対策ポリシーの作成と変更の詳細については、「ATP の事前[フィッシング対策ポリシーを構成する](configure-atp-anti-phishing-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0512c-111">For information about creating and modifying the more advanced ATP anti-phishing policies that are available in Office 365 Advanced Threat Protection (Office 365 ATP), see [Configure ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="0512c-112">セキュリティ & コンプライアンスセンター vs PowerShell のフィッシング対策ポリシー</span><span class="sxs-lookup"><span data-stu-id="0512c-112">Anti-phishing policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="0512c-113">フィッシング対策ポリシーの基本的な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0512c-113">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="0512c-114">**フィッシングポリシー**: 有効または無効にするフィッシング対策、およびオプションを適用するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="0512c-114">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>

- <span data-ttu-id="0512c-115">**フィッシングルールで**は、フィッシングポリシーの優先順位と受信者フィルター (ポリシーが適用されるユーザー) を指定します。</span><span class="sxs-lookup"><span data-stu-id="0512c-115">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="0512c-116">セキュリティ & コンプライアンスセンターでフィッシング対策ポリシーを管理する場合、この2つの要素の違いは明白ではありません。</span><span class="sxs-lookup"><span data-stu-id="0512c-116">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="0512c-117">セキュリティ & コンプライアンスセンターでフィッシング対策ポリシーを作成する場合、実際には、フィッシングルールと関連付けられたフィッシングポリシーを両方に同じ名前を使用して同時に作成しています。</span><span class="sxs-lookup"><span data-stu-id="0512c-117">When you create an anti-phishing policy in the Security & Compliance Center, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="0512c-118">セキュリティ & コンプライアンスセンターでフィッシング対策ポリシーを変更する場合、名前、優先度、有効または無効、および受信者フィルターに関連する設定によってフィッシングルールが変更されます。</span><span class="sxs-lookup"><span data-stu-id="0512c-118">When you modify an anti-phishing policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="0512c-119">他のすべての設定は、関連付けられたフィッシングポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="0512c-119">All other settings modify the associated anti-phish policy.</span></span>

- <span data-ttu-id="0512c-120">セキュリティ & コンプライアンスセンターからフィッシング対策ポリシーを削除すると、フィッシングルールとそれに関連付けられているフィッシングポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="0512c-120">When you remove an anti-phishing policy from the Security & Compliance Center, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="0512c-121">Exchange Online PowerShell では、フィッシングポリシーとフィッシングルールの違いが明らかです。</span><span class="sxs-lookup"><span data-stu-id="0512c-121">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="0512c-122">フィッシングポリシーを管理するには、 \*\* \* -get-antiphishpolicy**コマンドレットを使用して、 \*\* \* -new-antiphishrule**コマンドレットを使用してフィッシングルールを管理します。</span><span class="sxs-lookup"><span data-stu-id="0512c-122">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="0512c-123">PowerShell では、フィッシングポリシーを最初に作成してから、ルールが適用されるポリシーを識別するフィッシングルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="0512c-123">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="0512c-124">PowerShell では、フィッシングポリシーおよびフィッシングルールの設定を個別に変更します。</span><span class="sxs-lookup"><span data-stu-id="0512c-124">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>

### <a name="default-atp-anti-phishing-policy"></a><span data-ttu-id="0512c-125">既定の ATP のフィッシング対策ポリシー</span><span class="sxs-lookup"><span data-stu-id="0512c-125">Default ATP anti-phishing policy</span></span>

<span data-ttu-id="0512c-126">すべての組織には、Office365 フィッシング対策 Default という名前の組み込みのフィッシング対策ポリシーがあります。これらのプロパティは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0512c-126">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="0512c-127">Office365 フィッシング対策 Default という名前のポリシーは、組織内のすべての受信者に適用されます (ただし、ポリシーに関連付けられているフィッシングルール (受信者フィルター) はありません。</span><span class="sxs-lookup"><span data-stu-id="0512c-127">The policy named Office365 AntiPhish Default is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="0512c-128">Office365 フィッシング対策 Default という名前のポリシーには、変更できないカスタムの優先度の値が**最低**でもあります (ポリシーは常に最後に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="0512c-128">The policy named Office365 AntiPhish Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="0512c-129">作成するカスタムポリシーは、常に Office365 フィッシング対策 Default という名前のポリシーよりも高い優先順位を持ちます。</span><span class="sxs-lookup"><span data-stu-id="0512c-129">Any custom policies that you create always have a higher priority than the policy named Office365 AntiPhish Default.</span></span>

- <span data-ttu-id="0512c-130">Office365 フィッシング対策 Default という名前のポリシーは既定のポリシーです ( **IsDefault**プロパティには値があり `True` ます)。既定のポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="0512c-130">The policy named Office365 AntiPhish Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="0512c-131">フィッシング対策保護の有効性を高めるために、特定のユーザーまたはユーザーグループに適用される厳密な設定を使用して、カスタムのフィッシング対策ポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="0512c-131">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0512c-132">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="0512c-132">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0512c-133"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="0512c-133">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="0512c-134">**フィッシング対策**ページに直接移動するには、を使用 <https://protection.office.com/antiphishing> します。</span><span class="sxs-lookup"><span data-stu-id="0512c-134">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="0512c-135">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0512c-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="0512c-136">スタンドアロン EOP PowerShell では、フィッシング対策ポリシーを管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="0512c-136">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="0512c-137">これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0512c-137">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="0512c-138">フィッシング対策ポリシーを追加、変更、および削除するには、**組織の管理**または**セキュリティ管理者**の役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0512c-138">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="0512c-139">フィッシング対策ポリシーに対する読み取り専用アクセスでは、**セキュリティリーダー**役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0512c-139">For read-only access to anti-phishing policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="0512c-140">セキュリティ/コンプライアンス センターの役割グループの詳細については、「[セキュリティ/コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0512c-140">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="0512c-141">スタンドアロン EOP でスパム対策ポリシーを作成および変更できるようにするには、テナントに対して_ハイドロ_を必要とするものを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0512c-141">To be able to create and modify anti-spam policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="0512c-142">たとえば、EAC では、[**アクセス許可**] タブに移動し、既存の役割グループを選択し、 \*\*[編集\*\* ![ ] 編集アイコンをクリックし ](../../media/ITPro-EAC-EditIcon.png) て、役割を削除します (最終的に追加します)。</span><span class="sxs-lookup"><span data-stu-id="0512c-142">For example, in the EAC, you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="0512c-143">テナントが hydrated されていない場合は、「**組織の設定を更新**する」という名前のダイアログが表示され、進行状況バーが正常に完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0512c-143">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="0512c-144">ハイドロの詳細については、「[組織をカスタマイズ](https://docs.microsoft.com/powershell/module/exchange/organization/enable-organizationcustomization)する」を参照してください。このコマンドレットは、スタンドアロンの EOP PowerShell またはセキュリティ & コンプライアンスセンターでは使用できません)。</span><span class="sxs-lookup"><span data-stu-id="0512c-144">For more information about hydration, see the [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/organization/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="0512c-145">フィッシング対策ポリシーの推奨設定については、「 [EOP default フィッシング対策ポリシーの設定](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0512c-145">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="0512c-146">更新されたポリシーが適用されるまで最大30分かかります。</span><span class="sxs-lookup"><span data-stu-id="0512c-146">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="0512c-147">フィルタリングパイプラインにフィッシング対策ポリシーを適用する方法については、「[メール保護の順序と優先順位](how-policies-and-protections-are-combined.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0512c-147">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="0512c-148">セキュリティ & コンプライアンスセンターを使用してフィッシング対策ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="0512c-148">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="0512c-149">セキュリティ & コンプライアンスセンターでカスタムのフィッシング対策ポリシーを作成すると、両方に同じ名前を使用して、フィッシングルールと関連付けられているフィッシングポリシーを同時に作成します。</span><span class="sxs-lookup"><span data-stu-id="0512c-149">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="0512c-150">フィッシング対策ポリシーを作成する場合、ポリシー名、説明、およびポリシーの適用先を識別する受信者フィルターのみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0512c-150">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="0512c-151">ポリシーを作成したら、ポリシーを変更して既定のフィッシング対策設定を変更または確認することができます。</span><span class="sxs-lookup"><span data-stu-id="0512c-151">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="0512c-152">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー**の \> **フィッシング対策**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="0512c-152">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="0512c-153">[**フィッシング対策**] ページで、[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0512c-153">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="0512c-154">[**新しいフィッシング対策ポリシーの作成**] ウィザードが開きます。</span><span class="sxs-lookup"><span data-stu-id="0512c-154">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="0512c-155">[**ポリシーに名前**をつける] ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="0512c-155">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="0512c-156">**[名前]**: わかりやすい一意のポリシー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="0512c-156">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="0512c-157">**[説明]**: ポリシーについての説明を入力します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="0512c-157">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="0512c-158">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0512c-158">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="0512c-159">表示される [**適用先**] ページで、ポリシーが適用される内部の受信者を特定します。</span><span class="sxs-lookup"><span data-stu-id="0512c-159">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="0512c-160">各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="0512c-160">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="0512c-161">同じ条件や例外に複数の値がある場合は、OR ロジック (たとえば、_\<recipient1\>_ or _\<recipient2\>_) を使用します。</span><span class="sxs-lookup"><span data-stu-id="0512c-161">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="0512c-162">別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ and _\<member of group 1\>_) を使用します。</span><span class="sxs-lookup"><span data-stu-id="0512c-162">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="0512c-163">[**条件の追加] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="0512c-163">Click **Add a condition**.</span></span> <span data-ttu-id="0512c-164">表示されるドロップダウンで、[適用済みの**場合**] の条件を選択します。</span><span class="sxs-lookup"><span data-stu-id="0512c-164">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="0512c-165">**受信者は**次のとおりです。組織内で1つ以上のメールボックス、メールユーザー、またはメール連絡先を指定します。</span><span class="sxs-lookup"><span data-stu-id="0512c-165">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="0512c-166">**受信者が次のメンバーの**場合: 組織内の1つまたは複数のグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="0512c-166">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="0512c-167">**受信者のドメイン**: 構成された1つ以上の承認済みドメインの受信者を組織に指定します。</span><span class="sxs-lookup"><span data-stu-id="0512c-167">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="0512c-168">条件を選択すると、対応するドロップ**ダウンボックスが**表示されます。</span><span class="sxs-lookup"><span data-stu-id="0512c-168">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="0512c-169">ボックス内をクリックし、値の一覧をスクロールして選択します。</span><span class="sxs-lookup"><span data-stu-id="0512c-169">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="0512c-170">ボックス内をクリックして入力を開始し、リストにフィルターを適用して値を選択します。</span><span class="sxs-lookup"><span data-stu-id="0512c-170">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="0512c-171">その他の値を追加するには、ボックスの空の領域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0512c-171">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="0512c-172">個々のエントリを削除するには、その値の [削除] アイコン**をクリックし** ![ ](../../media/scc-remove-icon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="0512c-172">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="0512c-173">条件全体を削除するには、条件の [削除] アイコン**をクリックし** ![ ](../../media/scc-remove-icon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="0512c-173">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="0512c-174">別の条件を追加するには、[**条件の追加**] をクリックし、[**適用**時] で残りの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="0512c-174">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="0512c-175">例外を追加するには、[**条件の追加**] をクリックし、 **Except if**で例外を選択します。</span><span class="sxs-lookup"><span data-stu-id="0512c-175">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="0512c-176">設定と動作は、条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="0512c-176">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="0512c-177">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0512c-177">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="0512c-178">表示される [**設定の確認**] ページで、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="0512c-178">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="0512c-179">各設定で [**編集**] をクリックして、変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0512c-179">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="0512c-180">完了したら、[**このポリシーの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0512c-180">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="0512c-181">表示される確認ダイアログで [ **OK** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0512c-181">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="0512c-182">これらの一般的なポリシー設定を使用してフィッシング対策ポリシーを作成した後、次のセクションの手順を使用して、ポリシーの保護設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="0512c-182">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="0512c-183">セキュリティ & コンプライアンスセンターを使用してフィッシング対策ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="0512c-183">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="0512c-184">次の手順を使用して、作成した新しいポリシー、または既にカスタマイズした既存のポリシーを変更して、フィッシング対策ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="0512c-184">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="0512c-185">まだ準備できていない場合は、セキュリティ & コンプライアンスセンターを開き、[**脅威管理** \> **ポリシー**の \> **フィッシング対策**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="0512c-185">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="0512c-186">変更するカスタムのフィッシング対策ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="0512c-186">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="0512c-187">既に選択されている場合は、選択を解除してもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="0512c-187">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="0512c-188">[**ポリシー \< 名 \> の編集**フライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0512c-188">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="0512c-189">いずれかのセクションで [**編集**] をクリックすると、そのセクションの設定にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0512c-189">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="0512c-190">次の手順は、セクションが表示される順序で示されていますが、連続していません (任意の順序でセクションを選択して変更することができます)。</span><span class="sxs-lookup"><span data-stu-id="0512c-190">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="0512c-191">セクションで [**編集**] をクリックすると、使用可能な設定がウィザード形式で表示されますが、ページ内を任意の順序で移動できます。または、[任意の**Close**ページに**保存** **] を**クリックして ![ 、[ ](../../media/scc-remove-icon.png) **ポリシー \< 名 \> の編集**] ページに戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="0512c-191">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="0512c-192">**ポリシー設定**: [**編集**] をクリックして、前のセクションで[ポリシーを作成](#use-the-security--compliance-center-to-create-anti-phishing-policies)したときに使用したものと同じ設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="0512c-192">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="0512c-193">**名前**</span><span class="sxs-lookup"><span data-stu-id="0512c-193">**Name**</span></span>
   - <span data-ttu-id="0512c-194">**説明**</span><span class="sxs-lookup"><span data-stu-id="0512c-194">**Description**</span></span>
   - <span data-ttu-id="0512c-195">**適用先**</span><span class="sxs-lookup"><span data-stu-id="0512c-195">**Applied to**</span></span>
   - <span data-ttu-id="0512c-196">**設定を確認する**</span><span class="sxs-lookup"><span data-stu-id="0512c-196">**Review your settings**</span></span>

   <span data-ttu-id="0512c-197">完了したら、[任意のページに**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0512c-197">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="0512c-198">**スプーフィング**: [**編集**] をクリックして、スプーフィングインテリジェンスを有効または無効にしたり、Outlook で認証されていない送信者の識別をオンまたはオフにしたり、ブロックされたスプーフィングされた送信者からのメッセージに適用するアクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="0512c-198">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="0512c-199">詳細については、「[フィッシング対策ポリシーのスプーフィング設定](set-up-anti-phishing-policies.md#spoof-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0512c-199">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="0512c-200">なお、これらの設定は、ATP のフィッシング対策ポリシーでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="0512c-200">Note that these same settings are also available in ATP anti-phishing policies.</span></span>

   - <span data-ttu-id="0512c-201">**フィルター設定のスプーフィング**: 既定値は**on**で、そのままにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0512c-201">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="0512c-202">この機能をオフにするには、トグルを [**オフ**] にします。</span><span class="sxs-lookup"><span data-stu-id="0512c-202">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="0512c-203">詳細については、「 [Configure スプーフ知能 IN EOP」](learn-about-spoof-intelligence.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0512c-203">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="0512c-204">MX レコードが Microsoft 365 をポイントしていない場合は、スプーフィング防止保護を無効にする必要はありません。代わりに、コネクタの拡張フィルターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="0512c-204">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="0512c-205">手順については、「 [Exchange Online のコネクタの拡張フィルター処理](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0512c-205">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="0512c-206">[認証されていない**送信者の機能を有効にする**]: 既定値は **[オン**] です。</span><span class="sxs-lookup"><span data-stu-id="0512c-206">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="0512c-207">この機能をオフにするには、トグルを [**オフ**] にします。</span><span class="sxs-lookup"><span data-stu-id="0512c-207">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="0512c-208">**アクション**: スプーフィングインテリジェンスに失敗したメッセージに対して実行するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="0512c-208">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="0512c-209">**ドメインのスプーフィングが許可されていないユーザーによって電子メールが送信**される場合:</span><span class="sxs-lookup"><span data-stu-id="0512c-209">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="0512c-210">**受信者の迷惑メールフォルダーにメッセージを移動する**</span><span class="sxs-lookup"><span data-stu-id="0512c-210">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="0512c-211">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="0512c-211">**Quarantine the message**</span></span>

   - <span data-ttu-id="0512c-212">**設定を確認**します。個々の手順をクリックする代わりに、設定が概要で表示されます。</span><span class="sxs-lookup"><span data-stu-id="0512c-212">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="0512c-213">各セクションで [**編集**] をクリックすると、関連するページに戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="0512c-213">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="0512c-214">このページでは、次の設定の**オン**と**オフ**を直接切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="0512c-214">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="0512c-215">**スプーフィング対策保護を有効にする**</span><span class="sxs-lookup"><span data-stu-id="0512c-215">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="0512c-216">**認証されていない送信者機能を有効にする**</span><span class="sxs-lookup"><span data-stu-id="0512c-216">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="0512c-217">完了したら、[任意のページに**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0512c-217">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="0512c-218">[**ポリシー \< 名 \> の編集**] ページに戻り、設定を確認してから、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0512c-218">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="0512c-219">セキュリティ & コンプライアンスセンターを使用して既定のフィッシング対策ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="0512c-219">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="0512c-220">既定のフィッシング対策ポリシーの名前は、Office365 フィッシング対策 Default で、ポリシーの一覧には表示されません。</span><span class="sxs-lookup"><span data-stu-id="0512c-220">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="0512c-221">既定のフィッシング対策ポリシーを変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0512c-221">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="0512c-222">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー**の \> **フィッシング対策**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="0512c-222">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="0512c-223">[**フィッシング対策**] ページで、[**既定のポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0512c-223">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="0512c-224">[**ポリシーの Office 365 フィッシング対策の既定の編集**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0512c-224">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="0512c-225">次のセクションを使用できます。これには、[カスタムポリシーを変更](#use-the-security--compliance-center-to-modify-anti-phishing-policies)するときに、同一の設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0512c-225">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   - <span data-ttu-id="0512c-226">**偽装**</span><span class="sxs-lookup"><span data-stu-id="0512c-226">**Impersonation**</span></span>
   - <span data-ttu-id="0512c-227">**なりすます**</span><span class="sxs-lookup"><span data-stu-id="0512c-227">**Spoof**</span></span>
   - <span data-ttu-id="0512c-228">**詳細設定**</span><span class="sxs-lookup"><span data-stu-id="0512c-228">**Advanced settings**</span></span>

   <span data-ttu-id="0512c-229">次の設定は、既定のポリシーを変更するときには使用できません。</span><span class="sxs-lookup"><span data-stu-id="0512c-229">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="0512c-230">**ポリシー設定**のセクションと値は表示できますが、**編集**リンクはありません。そのため、設定 (ポリシー名、説明、ポリシーの適用先 (すべての受信者に適用)) を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="0512c-230">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="0512c-231">既定のポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="0512c-231">You can't delete the default policy.</span></span>
   - <span data-ttu-id="0512c-232">既定のポリシーの優先度を変更することはできません (常に最後に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="0512c-232">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="0512c-233">[ **Policy The Office365 フィッシング対策 Default** ] ページで、設定を確認し、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0512c-233">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="0512c-234">カスタムのフィッシング対策ポリシーを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="0512c-234">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="0512c-235">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー**の \> **フィッシング対策**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="0512c-235">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="0512c-236">[**状態**] 列の値に注目してください。</span><span class="sxs-lookup"><span data-stu-id="0512c-236">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="0512c-237">トグルを [**オフ**] にして、ポリシーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="0512c-237">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="0512c-238">トグルに切り替えて、**ポリシーを有効**にします。</span><span class="sxs-lookup"><span data-stu-id="0512c-238">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="0512c-239">既定のフィッシング対策ポリシーを無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="0512c-239">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="0512c-240">カスタムフィッシング対策ポリシーの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="0512c-240">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="0512c-241">既定では、フィッシング対策ポリシーには、作成された順序に基づく優先度が与えられます (新しいポリシーは、以前のポリシーよりも優先度が低いです)。</span><span class="sxs-lookup"><span data-stu-id="0512c-241">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="0512c-242">優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。</span><span class="sxs-lookup"><span data-stu-id="0512c-242">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="0512c-243">2 つのポリシーが同じ優先度を持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="0512c-243">No two policies can have the same priority.</span></span>

<span data-ttu-id="0512c-244">カスタムのフィッシング対策ポリシーは、処理順に表示されます (最初のポリシーの**優先度**値は0です)。</span><span class="sxs-lookup"><span data-stu-id="0512c-244">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="0512c-245">Office365 フィッシング対策 Default という既定のフィッシング対策ポリシーは、カスタムの優先度の値を**最小**にし、それを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="0512c-245">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="0512c-246">**注**: セキュリティ & コンプライアンスセンターでは、作成後に、フィッシング対策ポリシーの優先度のみを変更できます。</span><span class="sxs-lookup"><span data-stu-id="0512c-246">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="0512c-247">PowerShell では、フィッシングルールを作成するときに既定の優先順位を上書きできます (既存のルールの優先度に影響する場合があります)。</span><span class="sxs-lookup"><span data-stu-id="0512c-247">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="0512c-248">ポリシーの優先度を変更するには、ポリシーのプロパティで [**優先度を上げる**] または [**優先度を下げる**] をクリックします (セキュリティ & コンプライアンスセンターで**優先度**を直接変更することはできません)。</span><span class="sxs-lookup"><span data-stu-id="0512c-248">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="0512c-249">ポリシーの優先度を変更することは、複数のポリシーがある場合にのみ有効になります。</span><span class="sxs-lookup"><span data-stu-id="0512c-249">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="0512c-250">セキュリティ & コンプライアンスセンターで、[**脅威管理** \> **ポリシー** \> **ATP のフィッシング対策**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="0512c-250">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0512c-251">変更するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="0512c-251">Select the policy that you want to modify.</span></span> <span data-ttu-id="0512c-252">既に選択されている場合は、選択を解除してもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="0512c-252">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="0512c-253">[**ポリシー \< 名 \> の編集**フライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0512c-253">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="0512c-254">**優先度**の値が**0**のカスタムのフィッシング対策ポリシーでは、[**優先度を下げる**] ボタンのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="0512c-254">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="0512c-255">最も低い**優先度**の値 (たとえば**3**) を持つカスタムのフィッシング対策ポリシーでは、[**優先度を上げる**] ボタンのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="0512c-255">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="0512c-256">3つ以上のカスタムのマルウェア対策ポリシーを所有している場合、最高の優先度と最も低い優先度の値の間のポリシーでは、[優先度を**上げる**] ボタンと [**優先度を下げる**] ボタンの両方を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0512c-256">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="0512c-257">[優先**度を上げる**] または [**優先度を下げる**] をクリックし、**優先度**の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="0512c-257">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="0512c-258">完了したら、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0512c-258">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="0512c-259">セキュリティ & コンプライアンスセンターを使用してフィッシング対策ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="0512c-259">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="0512c-260">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー**の \> **フィッシング対策**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="0512c-260">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="0512c-261">次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0512c-261">Do one of the following steps:</span></span>

   - <span data-ttu-id="0512c-262">表示するカスタムのフィッシング対策ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="0512c-262">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="0512c-263">既に選択されている場合は、選択を解除してもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="0512c-263">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="0512c-264">[**既定のポリシー** ] をクリックして、既定のフィッシング対策ポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="0512c-264">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="0512c-265">[**ポリシー \< 名 \> の編集**] ポップアップが表示され、設定と値を確認できます。</span><span class="sxs-lookup"><span data-stu-id="0512c-265">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="0512c-266">セキュリティ & コンプライアンスセンターを使用して、フィッシング対策ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="0512c-266">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="0512c-267">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー**の \> **フィッシング対策**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="0512c-267">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="0512c-268">削除するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="0512c-268">Select the policy that you want to remove.</span></span> <span data-ttu-id="0512c-269">既に選択されている場合は、選択を解除してもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="0512c-269">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="0512c-270">表示される [**ポリシー \< 名 \> の編集**] ポップアップで、[**ポリシーの削除**] をクリックし、表示される警告ダイアログボックスで [**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0512c-270">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="0512c-271">既定のポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="0512c-271">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="0512c-272">Exchange Online PowerShell を使用してフィッシング対策ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="0512c-272">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="0512c-273">次の手順は、スタンドアロン EOP 組織では使用できません。</span><span class="sxs-lookup"><span data-stu-id="0512c-273">The following procedures aren't available in standalone EOP organizations.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="0512c-274">PowerShell を使用してフィッシング対策ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="0512c-274">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="0512c-275">PowerShell でのフィッシング対策ポリシーの作成は、次の2つの手順からなるプロセスです。</span><span class="sxs-lookup"><span data-stu-id="0512c-275">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="0512c-276">フィッシングポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="0512c-276">Create the anti-phish policy.</span></span>

2. <span data-ttu-id="0512c-277">ルールが適用されるフィッシングポリシーを指定するフィッシングルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="0512c-277">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="0512c-278">**注**:</span><span class="sxs-lookup"><span data-stu-id="0512c-278">**Notes**:</span></span>

- <span data-ttu-id="0512c-279">新しいフィッシングルールを作成し、関連付けられていない既存のアンチフィッシングポリシーをそのルールに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="0512c-279">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="0512c-280">フィッシングルールは、複数のフィッシングポリシーに関連付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="0512c-280">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="0512c-281">次の設定は、ポリシーを作成するまではセキュリティ & コンプライアンスセンターでは使用できない PowerShell の新しいフィッシングポリシーで構成できます。</span><span class="sxs-lookup"><span data-stu-id="0512c-281">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="0512c-282">新しいポリシーを無効として_Enabled_作成し `$false` ます ( **new-antiphishrule**コマンドレットでは有効)。</span><span class="sxs-lookup"><span data-stu-id="0512c-282">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>

  - <span data-ttu-id="0512c-283">**New-antiphishrule**コマンドレットで、作成中にポリシーの優先度を設定します (_優先度_ _ \< 番号 \> _)。</span><span class="sxs-lookup"><span data-stu-id="0512c-283">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="0512c-284">PowerShell で作成した新しいフィッシングポリシーは、ポリシーをフィッシングルールに割り当てるまで、セキュリティ & コンプライアンスセンターに表示されません。</span><span class="sxs-lookup"><span data-stu-id="0512c-284">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="0512c-285">手順 1: PowerShell を使用してフィッシングポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="0512c-285">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="0512c-286">フィッシングポリシーを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="0512c-286">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableAntiSpoofEnforcement <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="0512c-287">この例では、次の設定を使用して Research Quarantine という名前のフィッシングポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="0512c-287">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="0512c-288">このポリシーは有効になっています ( _enabled_パラメーターは使用していません。既定値はです `$true` )。</span><span class="sxs-lookup"><span data-stu-id="0512c-288">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="0512c-289">説明は、「研究部門のポリシー」です。</span><span class="sxs-lookup"><span data-stu-id="0512c-289">The description is: Research department policy.</span></span>
- <span data-ttu-id="0512c-290">スプーフィングに対する既定のアクションを変更します。</span><span class="sxs-lookup"><span data-stu-id="0512c-290">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="0512c-291">構文およびパラメーターの詳細については、「 [get-antiphishpolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishPolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0512c-291">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="0512c-292">手順 2: PowerShell を使用してフィッシングルールを作成する</span><span class="sxs-lookup"><span data-stu-id="0512c-292">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="0512c-293">フィッシングルールを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="0512c-293">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="0512c-294">この例では、次の条件を使用して Research Department という名前のフィッシングルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="0512c-294">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="0512c-295">ルールは、Research Quarantine という名前のフィッシングポリシーに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="0512c-295">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="0512c-296">ルールは Research Department という名前のグループのメンバーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="0512c-296">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="0512c-297">_Priority_パラメーターを使用していないので、既定の優先度が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0512c-297">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="0512c-298">構文およびパラメーターの詳細については、「 [new-antiphishrule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishRule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0512c-298">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="0512c-299">PowerShell を使用してフィッシングのポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="0512c-299">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="0512c-300">既存のフィッシングポリシーを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="0512c-300">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="0512c-301">この例では、指定されたプロパティと共にすべてのフィッシングポリシーの要約リストを返します。</span><span class="sxs-lookup"><span data-stu-id="0512c-301">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="0512c-302">この例では、"重役" という名前のフィッシングポリシーのすべてのプロパティ値を返します。</span><span class="sxs-lookup"><span data-stu-id="0512c-302">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="0512c-303">構文およびパラメーターの詳細については、「 [get-antiphishpolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0512c-303">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="0512c-304">PowerShell を使用してフィッシングのルールを表示する</span><span class="sxs-lookup"><span data-stu-id="0512c-304">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="0512c-305">既存のフィッシングルールを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="0512c-305">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="0512c-306">この例では、指定したプロパティと共に、フィッシングのすべてのルールの要約リストを返します。</span><span class="sxs-lookup"><span data-stu-id="0512c-306">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="0512c-307">ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0512c-307">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="0512c-308">この例では、Contoso 重役という名前のフィッシングルールのすべてのプロパティ値を返します。</span><span class="sxs-lookup"><span data-stu-id="0512c-308">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="0512c-309">構文およびパラメーターの詳細については、「 [new-antiphishrule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0512c-309">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="0512c-310">PowerShell を使用してフィッシングポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="0512c-310">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="0512c-311">このトピックで前述したように、「[手順 1: powershell を使用してフィッシングポリシーを作成する](#step-1-use-powershell-to-create-an-anti-phish-policy)」で説明されているように、ポリシーの作成時に powershell のフィッシングポリシーを変更する場合は、次の項目以外にも同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0512c-311">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="0512c-312">指定されたポリシーを既定のポリシー (すべてのユーザーに適用して、常に**最下位**の優先度を適用し、削除することはできません) に変更する_makedefault_スイッチは、PowerShell のフィッシングポリシーを変更する場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="0512c-312">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="0512c-313">フィッシングポリシーの名前を変更することはできません ( **get-antiphishpolicy**コマンドレットには_Name_パラメーターがありません)。</span><span class="sxs-lookup"><span data-stu-id="0512c-313">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="0512c-314">セキュリティ & コンプライアンスセンターでフィッシング対策ポリシーの名前を変更する場合、フィッシング_ルール_の名前のみを変更しています。</span><span class="sxs-lookup"><span data-stu-id="0512c-314">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="0512c-315">フィッシングポリシーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="0512c-315">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="0512c-316">構文およびパラメーターの詳細については、「 [get-antiphishpolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0512c-316">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="0512c-317">PowerShell を使用してフィッシングルールを変更する</span><span class="sxs-lookup"><span data-stu-id="0512c-317">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="0512c-318">PowerShell でフィッシングルールを変更するときには使用できない唯一の設定は、無効にされたルールを作成できる_有効_なパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="0512c-318">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="0512c-319">既存のフィッシングルールを有効または無効にするには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0512c-319">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="0512c-320">それ以外の場合は、PowerShell でフィッシングルールを変更しても、追加の設定は使用できません。</span><span class="sxs-lookup"><span data-stu-id="0512c-320">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="0512c-321">このトピックで前述した「[手順 2: PowerShell を使用してフィッシングルールを作成する](#step-2-use-powershell-to-create-an-anti-phish-rule)」で説明されているように、ルールを作成する場合にも同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0512c-321">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="0512c-322">フィッシングルールを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="0512c-322">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="0512c-323">構文およびパラメーターの詳細については、「 [new-antiphishrule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0512c-323">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="0512c-324">PowerShell を使用してフィッシングルールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="0512c-324">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="0512c-325">PowerShell でフィッシングルールを有効または無効にすると、フィッシング対策ポリシー全体 (フィッシングルールおよび割り当てられたフィッシングポリシー) が有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="0512c-325">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="0512c-326">既定のフィッシング対策ポリシーを有効または無効にすることはできません (常にすべての受信者に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="0512c-326">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="0512c-327">PowerShell でフィッシングルールを有効または無効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="0512c-327">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="0512c-328">この例では、Marketing Department という名前のフィッシングルールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="0512c-328">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="0512c-329">この例では、同じルールを有効化します。</span><span class="sxs-lookup"><span data-stu-id="0512c-329">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="0512c-330">構文およびパラメーターの詳細については、「 [new-antiphishrule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/enable-AntiPhishrule) 」および「 [Disable-new-antiphishrule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/disable-AntiPhishrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0512c-330">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/enable-AntiPhishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/disable-AntiPhishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="0512c-331">PowerShell を使用してフィッシングルールの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="0512c-331">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="0512c-332">ルールに設定できる優先度の最高値値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="0512c-332">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="0512c-333">設定できる最低値はルールの数に依存します。</span><span class="sxs-lookup"><span data-stu-id="0512c-333">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="0512c-334">たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。</span><span class="sxs-lookup"><span data-stu-id="0512c-334">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="0512c-335">既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。</span><span class="sxs-lookup"><span data-stu-id="0512c-335">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="0512c-336">たとえば、カスタム ルールが 5 つあって (優先度 0 から 4)、1 つのルールの優先度を 2 に変更した場合には、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。</span><span class="sxs-lookup"><span data-stu-id="0512c-336">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="0512c-337">PowerShell でフィッシングルールの優先度を設定するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="0512c-337">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="0512c-p137">この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。</span><span class="sxs-lookup"><span data-stu-id="0512c-p137">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="0512c-340">**注**:</span><span class="sxs-lookup"><span data-stu-id="0512c-340">**Notes**:</span></span>

- <span data-ttu-id="0512c-341">新しいルールの作成時に優先度を設定するには、代わりに**new-antiphishrule**コマンドレットで_priority_パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="0512c-341">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="0512c-342">既定のフィッシングポリシーには、対応するフィッシングルールが設定されておらず、常に未設定の優先度の値が**最低**になっています。</span><span class="sxs-lookup"><span data-stu-id="0512c-342">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="0512c-343">PowerShell を使用してフィッシングポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="0512c-343">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="0512c-344">PowerShell を使用してフィッシングポリシーを削除しても、対応するフィッシングルールは削除されません。</span><span class="sxs-lookup"><span data-stu-id="0512c-344">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="0512c-345">PowerShell でフィッシングポリシーを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="0512c-345">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="0512c-346">この例では、Marketing Department という名前のフィッシングポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="0512c-346">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="0512c-347">構文およびパラメーターの詳細については、「 [get-antiphishpolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishPolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0512c-347">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="0512c-348">PowerShell を使用してフィッシングルールを削除する</span><span class="sxs-lookup"><span data-stu-id="0512c-348">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="0512c-349">PowerShell を使用してフィッシングルールを削除しても、対応するフィッシングポリシーは削除されません。</span><span class="sxs-lookup"><span data-stu-id="0512c-349">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="0512c-350">PowerShell でフィッシングルールを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="0512c-350">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="0512c-351">この例では、Marketing Department という名前のフィッシングルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="0512c-351">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="0512c-352">構文およびパラメーターの詳細については、「 [new-antiphishrule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishRule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0512c-352">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="0512c-353">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="0512c-353">How do you know these procedures worked?</span></span>

<span data-ttu-id="0512c-354">ATP のフィッシング対策ポリシーが正常に構成されたことを確認するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0512c-354">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="0512c-355">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー**の \> **フィッシング対策**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="0512c-355">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="0512c-356">ポリシーの一覧、その**状態**の値、およびその**優先度**の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="0512c-356">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="0512c-357">詳細を表示するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0512c-357">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="0512c-358">リストからポリシーを選択し、フライアウトの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="0512c-358">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="0512c-359">[**既定のポリシー** ] をクリックして、フライアウトの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="0512c-359">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="0512c-360">Exchange Online PowerShell で、 \< name を \> ポリシーまたはルールの名前に置き換えて、次のコマンドを実行し、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="0512c-360">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
