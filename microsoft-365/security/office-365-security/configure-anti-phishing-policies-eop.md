---
title: EOP でのスパム対策ポリシーの構成
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online メールボックスを使用または使用しない Exchange Online Protection (EOP) 組織で使用可能なフィッシング対策ポリシーを作成、変更、および削除する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 052e19d811f56fe633ff0fbde79f51860a04a669
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165849"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="17bce-103">EOP でのスパム対策ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="17bce-103">Configure anti-phishing policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="17bce-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="17bce-104">**Applies to**</span></span>
- [<span data-ttu-id="17bce-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="17bce-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)

<span data-ttu-id="17bce-106">Exchange Online または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織にメールボックスがある Microsoft 365 組織では、既定で有効になっている限られた数のスプーフィング対策機能を含む既定のフィッシング対策ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="17bce-106">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="17bce-107">詳細については、「フィッシング対策ポリシー [のスプーフィング設定」を参照してください](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="17bce-107">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="17bce-108">管理者は、既定のフィッシング詐欺対策ポリシーを表示、編集、および構成 (削除しない) できます。</span><span class="sxs-lookup"><span data-stu-id="17bce-108">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="17bce-109">よりきめ細かく管理するために、組織内の特定のユーザー、グループ、またはドメインに適用されるカスタムフィッシング対策ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="17bce-109">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="17bce-110">カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (実行順序) を変更できます。</span><span class="sxs-lookup"><span data-stu-id="17bce-110">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="17bce-111">Exchange Online メールボックスを持つ組織は、セキュリティ/コンプライアンス センターまたは Exchange Online PowerShell &フィッシング対策ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="17bce-111">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="17bce-112">スタンドアロンの EOP 組織は、セキュリティ/コンプライアンス センター&使用できます。</span><span class="sxs-lookup"><span data-stu-id="17bce-112">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="17bce-113">Defender for Office 365 で使用可能な Office 365 向け Microsoft Defender で高度なフィッシング対策ポリシーを作成および変更する方法については [、「Office 365](configure-atp-anti-phishing-policies.md)向け Microsoft Defender でフィッシング対策ポリシーを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17bce-113">For information about creating and modifying the more advanced anti-phishing policies in Microsoft Defender for Office 365 that are available in Defender for Office 365, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

<span data-ttu-id="17bce-114">フィッシング対策ポリシーの基本的な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="17bce-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="17bce-115">**フィッシング対策ポリシー**: 有効または無効にするフィッシング対策と、オプションを適用するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="17bce-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="17bce-116">**フィッシング対策ルール**: フィッシング対策ポリシーの優先度と受信者フィルター (ポリシーが適用されるユーザー) を指定します。</span><span class="sxs-lookup"><span data-stu-id="17bce-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="17bce-117">これらの 2 つの要素の違いは、セキュリティ/コンプライアンス センターでフィッシング対策ポリシーを管理&明らかではありません。</span><span class="sxs-lookup"><span data-stu-id="17bce-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="17bce-118">フィッシング対策ポリシーを作成する場合、実際には、両方に同じ名前を使用して、フィッシング対策ルールと関連付けられたフィッシング対策ポリシーを同時に作成します。</span><span class="sxs-lookup"><span data-stu-id="17bce-118">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="17bce-119">フィッシング詐欺対策ポリシーを変更すると、名前、優先度、有効または無効、受信者フィルターに関連する設定によってフィッシング対策ルールが変更されます。</span><span class="sxs-lookup"><span data-stu-id="17bce-119">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="17bce-120">その他のすべての設定では、関連するフィッシング対策ポリシーが変更されます。</span><span class="sxs-lookup"><span data-stu-id="17bce-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="17bce-121">フィッシング対策ポリシーを削除すると、フィッシング対策ルールと関連付けられたフィッシング対策ポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="17bce-121">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="17bce-122">Exchange Online PowerShell では、ポリシーとルールを個別に管理します。</span><span class="sxs-lookup"><span data-stu-id="17bce-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="17bce-123">詳細については、後の [「Exchange Online PowerShell](#use-exchange-online-powershell-to-configure-anti-phishing-policies) を使用してフィッシング対策ポリシーを構成する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="17bce-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="17bce-124">すべての組織には、次のプロパティを持つ Office365 AntiPhish Default という名前の組み込みのフィッシング対策ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="17bce-124">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="17bce-125">ポリシーに関連付けられているフィッシング対策ルール (受信者フィルター) がない場合でも、ポリシーは組織内のすべての受信者に適用されます。</span><span class="sxs-lookup"><span data-stu-id="17bce-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="17bce-126">ポリシーにはカスタムの優先順位の値 **Lowest** が設定されており、変更することはできません (このポリシーは常に最後に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="17bce-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="17bce-127">作成するどのカスタム ポリシーも、より高い優先順位を持ちます。</span><span class="sxs-lookup"><span data-stu-id="17bce-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="17bce-128">ポリシーは既定のポリシー (**IsDefault** のプロパティが `True` の値になっている) であり、既定のポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="17bce-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="17bce-129">フィッシング対策保護の効果を高めるには、特定のユーザーまたはユーザー グループに適用されるより厳しい設定を使用して、カスタムのフィッシング対策ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="17bce-129">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="17bce-130">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="17bce-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="17bce-131"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="17bce-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="17bce-132">フィッシング対策ページに直接 **移動するには、次** のコマンドを使用します <https://protection.office.com/antiphishing> 。</span><span class="sxs-lookup"><span data-stu-id="17bce-132">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="17bce-133">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17bce-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="17bce-134">スタンドアロンの EOP PowerShell でフィッシング対策ポリシーを管理できない。</span><span class="sxs-lookup"><span data-stu-id="17bce-134">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="17bce-135">この記事に記載の手順を行うには、セキュリティ/コンプライアンス センターのアクセス許可が割り当てられている必要があります:</span><span class="sxs-lookup"><span data-stu-id="17bce-135">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="17bce-136">フィッシング対策ポリシーを追加、変更、および削除するには、組織の管理役割グループまたはセキュリティ管理者役割グループのメンバー **である** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="17bce-136">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="17bce-137">フィッシング対策ポリシーへの読み取り専用アクセスの場合、グローバル閲覧者またはセキュリティ閲覧者の役割グループのメンバー **である必要** があります <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="17bce-137">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="17bce-138">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17bce-138">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="17bce-139">**注**:</span><span class="sxs-lookup"><span data-stu-id="17bce-139">**Notes**:</span></span>

  - <span data-ttu-id="17bce-140">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、セキュリティ/コンプライアンス センター の必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="17bce-140">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="17bce-141">詳細については、「[管理者の役割について](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17bce-141">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="17bce-142">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) **の View-Only Organization Management** 役割グループは、この機能への読み取り専用アクセスも提供します <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="17bce-142">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="17bce-143"><sup>\*</sup> セキュリティ センターコンプライアンス センター&読み取り専用アクセスにより、ユーザーはカスタムフィッシング対策ポリシーの設定を表示できます。</span><span class="sxs-lookup"><span data-stu-id="17bce-143"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="17bce-144">読み取り専用のユーザーは、既定のフィッシング対策ポリシーの設定を表示できない。</span><span class="sxs-lookup"><span data-stu-id="17bce-144">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="17bce-145">スタンドアロン EOP でフィッシング対策ポリシーを作成および変更するには、テナントのハイドレーションが必要な操作を _行う必要_ があります。</span><span class="sxs-lookup"><span data-stu-id="17bce-145">To create and modify anti-phishing policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="17bce-146">たとえば、Exchange 管理センター (EAC) で、[アクセス許可]タブに移動し、既存の役割グループを選択し、[編集] アイコンをクリックして、役割を削除します ![ (最終的には戻ります)。 ](../../media/ITPro-EAC-EditIcon.png)</span><span class="sxs-lookup"><span data-stu-id="17bce-146">For example, in the Exchange admin center (EAC), you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="17bce-147">テナントが終了したことがない場合は、[ **組織** の設定の更新] という名前のダイアログが表示され、進行状況バーが表示され、正常に完了します。</span><span class="sxs-lookup"><span data-stu-id="17bce-147">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="17bce-148">ハイドレーションの詳細については [、Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) コマンドレットを参照してください (スタンドアロンの EOP PowerShell またはセキュリティ & コンプライアンス センターでは使用できません)。</span><span class="sxs-lookup"><span data-stu-id="17bce-148">For more information about hydration, see the [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="17bce-149">フィッシング対策ポリシーの推奨設定については、「EOP の既定のフィッシング対策ポリシー設定 [」を参照してください](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="17bce-149">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="17bce-150">更新されたポリシーが適用されるのに最大 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="17bce-150">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="17bce-151">フィッシング対策ポリシーがフィルター パイプラインで適用される場所については、「メール保護の順序と優先順位」 [を参照してください](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="17bce-151">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="17bce-152">セキュリティ/コンプライアンス センター&使用してフィッシング対策ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="17bce-152">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="17bce-153">セキュリティ & コンプライアンス センターでカスタムフィッシング対策ポリシーを作成すると、両方に同じ名前を使用して、フィッシング対策ルールと関連付けられたフィッシング対策ポリシーが同時に作成されます。</span><span class="sxs-lookup"><span data-stu-id="17bce-153">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="17bce-154">フィッシング詐欺対策ポリシーを作成する場合は、ポリシーの名前、説明、およびポリシーが適用されるユーザーを識別する受信者フィルターのみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="17bce-154">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="17bce-155">ポリシーを作成した後、ポリシーを変更して、既定のフィッシング対策設定を変更または確認できます。</span><span class="sxs-lookup"><span data-stu-id="17bce-155">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="17bce-156">セキュリティ/コンプライアンス センター&、脅威 **管理ポリシー** のフィッシング対策 \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="17bce-156">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="17bce-157">[フィッシング対策 **] ページで、[作成** ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="17bce-157">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="17bce-158">新 **しいフィッシング対策ポリシーの作成ウィザードが** 開きます。</span><span class="sxs-lookup"><span data-stu-id="17bce-158">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="17bce-159">[ポリシー **に名前を付け] ページ** で、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="17bce-159">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="17bce-160">**[名前]**: わかりやすい一意のポリシー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="17bce-160">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="17bce-161">**[説明]**: ポリシーについての説明を入力します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="17bce-161">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="17bce-162">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bce-162">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="17bce-163">表示される **[適用先** ] ページで、ポリシーが適用される内部受信者を特定します。</span><span class="sxs-lookup"><span data-stu-id="17bce-163">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="17bce-164">各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="17bce-164">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="17bce-165">同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="17bce-165">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="17bce-166">a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="17bce-166">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="17bce-167">[条件 **の追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="17bce-167">Click **Add a condition**.</span></span> <span data-ttu-id="17bce-168">表示されるドロップダウンで、[適用] の下の条件を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="17bce-168">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="17bce-169">**受信者は、** 組織内の 1 つ以上のメールボックス、メール ユーザー、またはメール連絡先を指定します。</span><span class="sxs-lookup"><span data-stu-id="17bce-169">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="17bce-170">**受信者が次のメンバーである**: 組織内の 1 つ以上のグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="17bce-170">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="17bce-171">**[受信者のドメインが次の値である]**: 組織内で構成済みの 1 つ以上の承認済みドメイン内の受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="17bce-171">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="17bce-172">条件を選択すると、対応するドロップダウンが [Any **of these] ボックスと一緒に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="17bce-172">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="17bce-173">ボックス内をクリックし、値の一覧をスクロールして選択します。</span><span class="sxs-lookup"><span data-stu-id="17bce-173">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="17bce-174">ボックス内をクリックし、入力を開始してリストをフィルター処理し、値を選択します。</span><span class="sxs-lookup"><span data-stu-id="17bce-174">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="17bce-175">値を追加するには、ボックス内の空の領域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bce-175">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="17bce-176">個々のエントリを削除するには、値の **[削除]** ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bce-176">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="17bce-177">条件全体を削除するには、条件の **[削除**] ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bce-177">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="17bce-178">追加の条件を追加するには、[条件の追加] **をクリックし** 、[適用する条件] の下の残りの値 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="17bce-178">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="17bce-179">例外を追加するには、[条件の追加] をクリックし、[次の場合を除く] で例外 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="17bce-179">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="17bce-180">設定と動作は、条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="17bce-180">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="17bce-181">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bce-181">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="17bce-182">表示される **[設定の確認** ] ページで、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="17bce-182">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="17bce-183">各設定で **[編集]** をクリックして変更できます。</span><span class="sxs-lookup"><span data-stu-id="17bce-183">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="17bce-184">完了したら、[このポリシーの作成 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="17bce-184">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="17bce-185">表示 **される確認ダイアログで [OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bce-185">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="17bce-186">これらの一般的なポリシー設定を使用してフィッシング対策ポリシーを作成した後、次のセクションの手順を使用して、ポリシーの保護設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="17bce-186">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="17bce-187">セキュリティ/コンプライアンス センター&使用してフィッシング対策ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="17bce-187">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="17bce-188">フィッシング対策ポリシー (作成した新しいポリシー、または既にカスタマイズした既存のポリシー) を変更するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="17bce-188">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="17bce-189">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="17bce-189">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="17bce-190">変更するカスタムフィッシング詐欺対策ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="17bce-190">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="17bce-191">既に選択されている場合は、選択を解除して、もう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="17bce-191">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="17bce-192">[**ポリシーの編集 \<name\> ]** フライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="17bce-192">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="17bce-193">任意の **セクションで [** 編集] をクリックすると、そのセクションの設定にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="17bce-193">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="17bce-194">次の手順は、セクションが表示される順序で示されますが、順番には表示されません (セクションは任意の順序で選択および変更できます)。</span><span class="sxs-lookup"><span data-stu-id="17bce-194">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="17bce-195">セクションで [編集] をクリックすると、使用可能な設定がウィザード形式で表示されますが、任意の順序でページ内にジャンプできます。また、任意のページで [保存]  (または [キャンセル] または [閉じる] アイコン) をクリックしてポリシーの編集ページに戻ります ![ ](../../media/scc-remove-icon.png) (**\<name\>** 保存または終了するにはウィザードの最後のページにアクセスする必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="17bce-195">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="17bce-196">**ポリシー設定**: [編集 **] を** クリックして、前の [](#use-the-security--compliance-center-to-create-anti-phishing-policies)セクションでポリシーを作成した場合と同じ設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="17bce-196">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="17bce-197">**名前**</span><span class="sxs-lookup"><span data-stu-id="17bce-197">**Name**</span></span>
   - <span data-ttu-id="17bce-198">**説明**</span><span class="sxs-lookup"><span data-stu-id="17bce-198">**Description**</span></span>
   - <span data-ttu-id="17bce-199">**適用先**</span><span class="sxs-lookup"><span data-stu-id="17bce-199">**Applied to**</span></span>
   - <span data-ttu-id="17bce-200">**設定を確認する**</span><span class="sxs-lookup"><span data-stu-id="17bce-200">**Review your settings**</span></span>

   <span data-ttu-id="17bce-201">完了したら、任意のページで [保存 **]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bce-201">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="17bce-202">**ス** プーフィング : **[編集** ] をクリックしてスプーフィング インテリジェンスを有効またはオフにし、Outlook の認証されていない送信者の識別をオンまたはオフにし、ブロックされたスプーフィングされた送信者からのメッセージに適用するアクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="17bce-202">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="17bce-203">詳細については、「フィッシング対策ポリシー [のスプーフィング設定」を参照してください](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="17bce-203">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="17bce-204">これらの設定は、Defender for Office 365 のフィッシング対策ポリシーでも利用できます。</span><span class="sxs-lookup"><span data-stu-id="17bce-204">Note that these same settings are also available in anti-phishing policies in Defender for Office 365.</span></span>

   - <span data-ttu-id="17bce-205">**スプーフィング フィルターの** 設定 : 既定値は **オン** であり、オンのままにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="17bce-205">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="17bce-206">オフに切り替えるには、トグルを [オフ] に **スライドします**。</span><span class="sxs-lookup"><span data-stu-id="17bce-206">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="17bce-207">詳細については、「EOP でスプーフィング [インテリジェンスを構成する」を参照してください](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="17bce-207">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="17bce-208">MX レコードが Microsoft 365 をポイントしない場合は、スプーフィング対策保護を無効にする必要があります。コネクタの拡張フィルターを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="17bce-208">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="17bce-209">手順については [、「Exchange Online のコネクタの拡張フィルター処理」を参照してください](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="17bce-209">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="17bce-210">**認証されていない送信者機能を有効** にする : 既定値は **[オン] です**。</span><span class="sxs-lookup"><span data-stu-id="17bce-210">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="17bce-211">オフに切り替えるには、トグルを [オフ] に **スライドします**。</span><span class="sxs-lookup"><span data-stu-id="17bce-211">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="17bce-212">**アクション**: スプーフィング インテリジェンスに失敗したメッセージに対して実行するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="17bce-212">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="17bce-213">**ドメインのスプーフィングが許可されていないユーザーからメールが送信された場合**:</span><span class="sxs-lookup"><span data-stu-id="17bce-213">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="17bce-214">**受信者の迷惑メール フォルダーにメッセージを移動する**</span><span class="sxs-lookup"><span data-stu-id="17bce-214">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="17bce-215">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="17bce-215">**Quarantine the message**</span></span>

   - <span data-ttu-id="17bce-216">**設定を確認** します。個々の手順をクリックする代わりに、設定が概要に表示されます。</span><span class="sxs-lookup"><span data-stu-id="17bce-216">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="17bce-217">各セクションで **[編集]** をクリックすると、関連するページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="17bce-217">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="17bce-218">このページで直接、次の **設定をオン\*\*\*\*またはオフ** に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="17bce-218">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="17bce-219">**スプーフ対策保護を有効にする**</span><span class="sxs-lookup"><span data-stu-id="17bce-219">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="17bce-220">**認証されていない送信者機能を有効にする**</span><span class="sxs-lookup"><span data-stu-id="17bce-220">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="17bce-221">完了したら、任意のページで [保存 **]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bce-221">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="17bce-222">[ポリシーの編集 **] \<Name\> ページに戻** り、設定を確認し、[閉じる] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="17bce-222">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="17bce-223">セキュリティ/コンプライアンス センター&使用して、既定のフィッシング対策ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="17bce-223">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="17bce-224">既定のフィッシング対策ポリシーの名前は Office365 AntiPhish Default で、ポリシーの一覧には表示されません。</span><span class="sxs-lookup"><span data-stu-id="17bce-224">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="17bce-225">既定のフィッシング対策ポリシーを変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="17bce-225">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="17bce-226">セキュリティ/コンプライアンス センター&、脅威 **管理ポリシー** のフィッシング対策 \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="17bce-226">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="17bce-227">[フィッシング対策 **] ページで、[既定** のポリシー] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="17bce-227">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="17bce-228">[ **ポリシーの編集] の [Office365 AntiPhish Default]** ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="17bce-228">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="17bce-229">次のセクションを使用できます。このセクションには、カスタム ポリシーを変更する場合と同じ [設定が含まれます](#use-the-security--compliance-center-to-modify-anti-phishing-policies)。</span><span class="sxs-lookup"><span data-stu-id="17bce-229">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   - <span data-ttu-id="17bce-230">**偽装**</span><span class="sxs-lookup"><span data-stu-id="17bce-230">**Impersonation**</span></span>
   - <span data-ttu-id="17bce-231">**スプーフィング**</span><span class="sxs-lookup"><span data-stu-id="17bce-231">**Spoof**</span></span>
   - <span data-ttu-id="17bce-232">**詳細設定**</span><span class="sxs-lookup"><span data-stu-id="17bce-232">**Advanced settings**</span></span>

   <span data-ttu-id="17bce-233">既定のポリシーを変更する場合、次の設定は使用できません。</span><span class="sxs-lookup"><span data-stu-id="17bce-233">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="17bce-234">[ポリシー設定]セクションと値を確認できますが、[編集]リンクは表示されません。そのため、設定 (ポリシー名、説明、およびポリシーが適用されるユーザー (すべての受信者に適用されます) を変更できない。</span><span class="sxs-lookup"><span data-stu-id="17bce-234">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="17bce-235">既定のポリシーは削除できない。</span><span class="sxs-lookup"><span data-stu-id="17bce-235">You can't delete the default policy.</span></span>
   - <span data-ttu-id="17bce-236">既定のポリシーの優先度は変更できない (常に最後に適用される)。</span><span class="sxs-lookup"><span data-stu-id="17bce-236">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="17bce-237">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span><span class="sxs-lookup"><span data-stu-id="17bce-237">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="17bce-238">カスタムフィッシング対策ポリシーを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="17bce-238">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="17bce-239">セキュリティ/コンプライアンス センター&、脅威 **管理ポリシー** のフィッシング対策 \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="17bce-239">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="17bce-240">[状態] 列の値 **に注意** してください。</span><span class="sxs-lookup"><span data-stu-id="17bce-240">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="17bce-241">トグルを [ **オフ] にスライド** してポリシーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="17bce-241">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="17bce-242">トグルを [ **オン] にスライドして** ポリシーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="17bce-242">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="17bce-243">既定のフィッシング詐欺対策ポリシーを無効にできない。</span><span class="sxs-lookup"><span data-stu-id="17bce-243">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="17bce-244">カスタムフィッシング対策ポリシーの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="17bce-244">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="17bce-245">既定では、フィッシング詐欺対策ポリシーには、作成された順序に基づく優先度が設定されます (新しいポリシーは、古いポリシーよりも優先度が低くなります)。</span><span class="sxs-lookup"><span data-stu-id="17bce-245">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="17bce-246">優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。</span><span class="sxs-lookup"><span data-stu-id="17bce-246">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="17bce-247">2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。</span><span class="sxs-lookup"><span data-stu-id="17bce-247">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="17bce-248">優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17bce-248">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="17bce-249">カスタムフィッシング詐欺対策ポリシーは、処理順に表示されます (最初のポリシーの **優先度** の値は 0 です)。</span><span class="sxs-lookup"><span data-stu-id="17bce-249">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="17bce-250">Office365 AntiPhish Default という名前の既定のフィッシング詐欺対策ポリシーには、カスタム優先度の値 **Lowest** が設定されています。この値は変更できます。</span><span class="sxs-lookup"><span data-stu-id="17bce-250">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="17bce-251">**注**: セキュリティ & コンプライアンス センターでは、フィッシング対策ポリシーを作成した後にのみ、優先度を変更できます。</span><span class="sxs-lookup"><span data-stu-id="17bce-251">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="17bce-252">PowerShell では、フィッシング対策ルールを作成するときに既定の優先度を上書きできます (既存のルールの優先度に影響を与える可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="17bce-252">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="17bce-253">ポリシーの優先度を変更するには、ポリシーのプロパティで [優先度の引き上げ] または [優先度の下げ]をクリックします (セキュリティ/コンプライアンス センターで優先度番号を直接変更&することはできません)。 </span><span class="sxs-lookup"><span data-stu-id="17bce-253">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="17bce-254">ポリシーの優先度の変更は、複数のポリシーがある場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="17bce-254">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="17bce-255">セキュリティ/コンプライアンス センター&、**脅威管理ポリシー** ATP のフィッシング対策 \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="17bce-255">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="17bce-256">変更するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="17bce-256">Select the policy that you want to modify.</span></span> <span data-ttu-id="17bce-257">既に選択されている場合は、選択を解除して、もう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="17bce-257">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="17bce-258">[**ポリシーの編集 \<name\> ]** フライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="17bce-258">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="17bce-259">優先度の値が **0** のカスタムフィッシング詐欺対策ポリシーでは、[優先度の下がり]**ボタンしか** 使用できません。</span><span class="sxs-lookup"><span data-stu-id="17bce-259">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="17bce-260">優先度の値が最も低いカスタムフィッシング詐欺対策ポリシー (**たとえば、3)** では、[優先度の引き上げ]**ボタンしか使用** できません。</span><span class="sxs-lookup"><span data-stu-id="17bce-260">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="17bce-261">3 つ以上のカスタムフィッシング詐欺対策ポリシーがある場合は、優先度の高い値と最も低い値の間のポリシーの [優先度の引き上げ] ボタンと [優先度の下げ] ボタンの両方を使用できます。</span><span class="sxs-lookup"><span data-stu-id="17bce-261">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="17bce-262">[優先度 **の引き上げ\*\*\*\*] または [優先度の下げ**] をクリックして、[優先度] の **値を変更** します。</span><span class="sxs-lookup"><span data-stu-id="17bce-262">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="17bce-263">完了したら、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bce-263">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="17bce-264">セキュリティ/コンプライアンス &を使用してフィッシング対策ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="17bce-264">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="17bce-265">セキュリティ/コンプライアンス センター&、脅威管理ポリシーのフィッシング対策 \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="17bce-265">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="17bce-266">次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="17bce-266">Do one of the following steps:</span></span>

   - <span data-ttu-id="17bce-267">表示するカスタムフィッシング対策ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="17bce-267">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="17bce-268">既に選択されている場合は、選択を解除して、もう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="17bce-268">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="17bce-269">既定 **のフィッシング** 対策ポリシーを表示するには、[既定のポリシー] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bce-269">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="17bce-270">[**ポリシーの編集 \<name\> ]** フライアウトが表示され、設定と値を表示できます。</span><span class="sxs-lookup"><span data-stu-id="17bce-270">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="17bce-271">セキュリティ/コンプライアンス センター&使用してフィッシング対策ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="17bce-271">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="17bce-272">セキュリティ/コンプライアンス センター&、脅威 **管理ポリシー** のフィッシング対策 \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="17bce-272">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="17bce-273">削除するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="17bce-273">Select the policy that you want to remove.</span></span> <span data-ttu-id="17bce-274">既に選択されている場合は、選択を解除して、もう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="17bce-274">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="17bce-275">表示される **[ポリシー \<name\> の** 編集] フライアウトで、[ポリシーの削除]をクリックし、表示される警告ダイアログで [はい] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17bce-275">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="17bce-276">既定のポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="17bce-276">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="17bce-277">Exchange Online PowerShell を使用してフィッシング対策ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="17bce-277">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="17bce-278">前述のように、フィッシング対策ポリシーは、フィッシング対策ポリシーとフィッシング対策ルールで構成されます。</span><span class="sxs-lookup"><span data-stu-id="17bce-278">As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="17bce-279">Exchange Online PowerShell では、フィッシング対策ポリシーとフィッシング対策ルールの違いは明白です。</span><span class="sxs-lookup"><span data-stu-id="17bce-279">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="17bce-280">**\* -AntiPhishPolicy** コマンドレットを使用してフィッシング対策ポリシーを管理し **\* 、-AntiPhishRule** コマンドレットを使用してフィッシング対策ルールを管理します。</span><span class="sxs-lookup"><span data-stu-id="17bce-280">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="17bce-281">PowerShell では、最初にフィッシング対策ポリシーを作成し、次に、そのルールが適用されるポリシーを識別するフィッシング対策ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="17bce-281">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="17bce-282">PowerShell では、フィッシング対策ポリシーとフィッシング対策ルールの設定を個別に変更します。</span><span class="sxs-lookup"><span data-stu-id="17bce-282">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="17bce-283">PowerShell からフィッシング対策ポリシーを削除すると、対応するフィッシング対策ルールは自動的には削除されません。その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="17bce-283">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="17bce-284">次の PowerShell 手順は、Exchange Online Protection PowerShell を使用するスタンドアロンの EOP 組織では使用できません。</span><span class="sxs-lookup"><span data-stu-id="17bce-284">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="17bce-285">PowerShell を使用してフィッシング対策ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="17bce-285">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="17bce-286">PowerShell でフィッシング対策ポリシーを作成するには、次の 2 つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="17bce-286">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="17bce-287">フィッシング対策ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="17bce-287">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="17bce-288">ルールが適用されるフィッシング対策ポリシーを指定するフィッシング対策ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="17bce-288">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="17bce-289">**注**:</span><span class="sxs-lookup"><span data-stu-id="17bce-289">**Notes**:</span></span>

- <span data-ttu-id="17bce-290">新しいフィッシング対策ルールを作成し、関連付けされていない既存のフィッシング対策ポリシーを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="17bce-290">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="17bce-291">フィッシング詐欺対策ルールは、複数のフィッシング対策ポリシーに関連付けらなけな。</span><span class="sxs-lookup"><span data-stu-id="17bce-291">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="17bce-292">ポリシーを作成するまで、セキュリティ/コンプライアンス センターで使用できない新しいフィッシング詐欺対策ポリシーに関する次の設定を構成&できます。</span><span class="sxs-lookup"><span data-stu-id="17bce-292">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="17bce-293">新しいポリシーを無効な状態 _で作成_ `$false` します **(New-AntiPhishRule コマンドレットで有効** )。</span><span class="sxs-lookup"><span data-stu-id="17bce-293">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="17bce-294"> _\<Number\>_ **New-AntiPhishRule** コマンドレットで、作成時のポリシーの優先度 (優先度) を設定します。</span><span class="sxs-lookup"><span data-stu-id="17bce-294">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="17bce-295">PowerShell で作成した新しいフィッシング対策ポリシーは、そのポリシーをフィッシング対策ルールに割り当てるまで、セキュリティ & コンプライアンス センターに表示されません。</span><span class="sxs-lookup"><span data-stu-id="17bce-295">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="17bce-296">手順 1: PowerShell を使用してフィッシング対策ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="17bce-296">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="17bce-297">フィッシング対策ポリシーを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="17bce-297">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="17bce-298">この例では、次の設定で Research Quarantine という名前のフィッシング対策ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="17bce-298">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="17bce-299">説明は、リサーチ部門のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="17bce-299">The description is: Research department policy.</span></span>
- <span data-ttu-id="17bce-300">スプーフィングの既定のアクションを検疫に変更します。</span><span class="sxs-lookup"><span data-stu-id="17bce-300">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="17bce-301">構文およびパラメーターの詳細については [、「New-AntiPhishPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="17bce-301">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="17bce-302">手順 2: PowerShell を使用してフィッシング対策ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="17bce-302">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="17bce-303">フィッシング対策ルールを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="17bce-303">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="17bce-304">この例では、次の条件で Research Department という名前のフィッシング対策ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="17bce-304">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="17bce-305">ルールは、Research Quarantine という名前のフィッシング対策ポリシーに関連付けられている。</span><span class="sxs-lookup"><span data-stu-id="17bce-305">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="17bce-306">ルールは Research Department という名前のグループのメンバーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="17bce-306">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="17bce-307">_Priority_ パラメーターを使用していないので、既定の優先度が使用されます。</span><span class="sxs-lookup"><span data-stu-id="17bce-307">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="17bce-308">構文およびパラメーターの詳細については [、「New-AntiPhishRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="17bce-308">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="17bce-309">PowerShell を使用してフィッシング対策ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="17bce-309">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="17bce-310">既存のフィッシング対策ポリシーを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="17bce-310">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="17bce-311">この例では、指定したプロパティと共に、すべてのフィッシング対策ポリシーの要約リストを返します。</span><span class="sxs-lookup"><span data-stu-id="17bce-311">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="17bce-312">この例では、Executives という名前のフィッシング対策ポリシーのすべてのプロパティ値を返します。</span><span class="sxs-lookup"><span data-stu-id="17bce-312">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="17bce-313">構文およびパラメーターの詳細については [、「Get-AntiPhishPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="17bce-313">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="17bce-314">PowerShell を使用してフィッシング対策ルールを表示する</span><span class="sxs-lookup"><span data-stu-id="17bce-314">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="17bce-315">既存のフィッシング対策ルールを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="17bce-315">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="17bce-316">この例では、指定したプロパティと一緒に、すべてのフィッシング対策ルールの要約リストを返します。</span><span class="sxs-lookup"><span data-stu-id="17bce-316">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="17bce-317">ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="17bce-317">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="17bce-318">この例では、Contoso Executives という名前のフィッシング対策ルールのすべてのプロパティ値を返します。</span><span class="sxs-lookup"><span data-stu-id="17bce-318">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="17bce-319">構文およびパラメーターの詳細については [、「Get-AntiPhishRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)。</span><span class="sxs-lookup"><span data-stu-id="17bce-319">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="17bce-320">PowerShell を使用してフィッシング対策ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="17bce-320">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="17bce-321">次の項目以外に、PowerShell でフィッシング対策ポリシーを変更する場合も、「手順 [1: PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) を使用してフィッシング対策ポリシーを作成する」で説明したように、PowerShell でフィッシング対策ポリシーを変更する場合と同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="17bce-321">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="17bce-322">指定したポリシーを既定のポリシー (すべてのユーザーに適用され、常に最も低い優先度に適用され、削除できない) に変える _MakeDefault_ スイッチは、PowerShell でフィッシング対策ポリシーを変更した場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="17bce-322">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="17bce-323">フィッシング対策ポリシーの名前を変更することはできません **(Set-AntiPhishPolicy** コマンドレットには _Name_ パラメーターはありません)。</span><span class="sxs-lookup"><span data-stu-id="17bce-323">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="17bce-324">セキュリティ/コンプライアンス センターでフィッシング対策ポリシーの名前を変更&、フィッシング対策ルールの名前を変更するだけ _です_。</span><span class="sxs-lookup"><span data-stu-id="17bce-324">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="17bce-325">フィッシング対策ポリシーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="17bce-325">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="17bce-326">構文およびパラメーターの詳細については [、「Set-AntiPhishPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="17bce-326">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="17bce-327">PowerShell を使用してフィッシング対策ルールを変更する</span><span class="sxs-lookup"><span data-stu-id="17bce-327">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="17bce-328">PowerShell でフィッシング対策ルールを変更する場合に使用できない唯一の設定は、無効にされたルールを作成できる _Enabled_ パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="17bce-328">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="17bce-329">既存のフィッシング対策ルールを有効または無効にするには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="17bce-329">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="17bce-330">それ以外の場合は、「手順 [2: PowerShell](#step-2-use-powershell-to-create-an-anti-phish-rule) を使用してフィッシング詐欺対策ルールを作成する」セクションで説明したルールを作成する場合と同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="17bce-330">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="17bce-331">フィッシング対策ルールを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="17bce-331">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="17bce-332">構文およびパラメーターの詳細については [、「Set-AntiPhishRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="17bce-332">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="17bce-333">PowerShell を使用してフィッシング対策ルールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="17bce-333">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="17bce-334">PowerShell でフィッシング対策ルールを有効または無効にすると、フィッシング対策ポリシー全体 (フィッシング対策ルールと割り当てられたフィッシング対策ポリシー) を有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="17bce-334">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="17bce-335">既定のフィッシング詐欺対策ポリシーを有効または無効にできない (常にすべての受信者に適用される)。</span><span class="sxs-lookup"><span data-stu-id="17bce-335">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="17bce-336">PowerShell でフィッシング対策ルールを有効または無効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="17bce-336">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="17bce-337">この例では、Marketing Department という名前のフィッシング対策ルールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="17bce-337">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="17bce-338">この例では、同じルールを有効化します。</span><span class="sxs-lookup"><span data-stu-id="17bce-338">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="17bce-339">構文およびパラメーターの詳細については [、「Enable-AntiPhishRule」](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) および [「Disable-AntiPhishRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="17bce-339">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="17bce-340">PowerShell を使用してフィッシング対策ルールの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="17bce-340">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="17bce-341">ルールに設定できる優先度の最高値値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="17bce-341">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="17bce-342">設定できる最低値はルールの数に依存します。</span><span class="sxs-lookup"><span data-stu-id="17bce-342">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="17bce-343">たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。</span><span class="sxs-lookup"><span data-stu-id="17bce-343">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="17bce-344">既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。</span><span class="sxs-lookup"><span data-stu-id="17bce-344">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="17bce-345">たとえば、カスタム ルールが 5 つあって (優先度 0 から 4)、1 つのルールの優先度を 2 に変更した場合には、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。</span><span class="sxs-lookup"><span data-stu-id="17bce-345">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="17bce-346">PowerShell でフィッシング対策ルールの優先度を設定するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="17bce-346">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="17bce-p138">この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。</span><span class="sxs-lookup"><span data-stu-id="17bce-p138">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="17bce-349">**注**:</span><span class="sxs-lookup"><span data-stu-id="17bce-349">**Notes**:</span></span>

- <span data-ttu-id="17bce-350">新しいルールを作成するときに優先度を設定するには、代わりに **New-AntiPhishRule** コマンドレットの _Priority_ パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="17bce-350">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="17bce-351">既定のフィッシング対策ポリシーには対応するフィッシング対策ルールが設定されていないので、常に変更できない優先度の値 **が Lowest です**。</span><span class="sxs-lookup"><span data-stu-id="17bce-351">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="17bce-352">PowerShell を使用してフィッシング対策ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="17bce-352">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="17bce-353">PowerShell を使用してフィッシング対策ポリシーを削除する場合、対応するフィッシング対策ルールは削除されません。</span><span class="sxs-lookup"><span data-stu-id="17bce-353">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="17bce-354">PowerShell でフィッシング対策ポリシーを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="17bce-354">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="17bce-355">この例では、Marketing Department という名前のフィッシング対策ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="17bce-355">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="17bce-356">構文およびパラメーターの詳細については [、「Remove-AntiPhishPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="17bce-356">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="17bce-357">PowerShell を使用してフィッシング対策ルールを削除する</span><span class="sxs-lookup"><span data-stu-id="17bce-357">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="17bce-358">PowerShell を使用してフィッシング対策ルールを削除する場合、対応するフィッシング対策ポリシーは削除されません。</span><span class="sxs-lookup"><span data-stu-id="17bce-358">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="17bce-359">PowerShell でフィッシング対策ルールを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="17bce-359">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="17bce-360">この例では、Marketing Department という名前のフィッシング対策ルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="17bce-360">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="17bce-361">構文およびパラメーターの詳細については [、「Remove-AntiPhishRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="17bce-361">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="17bce-362">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="17bce-362">How do you know these procedures worked?</span></span>

<span data-ttu-id="17bce-363">Office 365 用に Microsoft Defender でフィッシング対策ポリシーが正常に構成されたことを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="17bce-363">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="17bce-364">セキュリティ/コンプライアンス センター&、脅威 **管理ポリシー** のフィッシング対策 \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="17bce-364">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="17bce-365">ポリシーの一覧、状態の値、 **および優先度** の値を **確認** します。</span><span class="sxs-lookup"><span data-stu-id="17bce-365">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="17bce-366">詳細を表示するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="17bce-366">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="17bce-367">一覧からポリシーを選択し、詳細をフライアウトで表示します。</span><span class="sxs-lookup"><span data-stu-id="17bce-367">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="17bce-368">[ **既定のポリシー]** をクリックし、詳細をフライアウトに表示します。</span><span class="sxs-lookup"><span data-stu-id="17bce-368">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="17bce-369">Exchange Online PowerShell で、ポリシーまたはルールの名前に置き換え、次のコマンドを実行して \<Name\> 、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="17bce-369">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
