---
title: Microsoft Defender でフィッシング対策ポリシーを構成する (Office 365)
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
description: 管理者は、Microsoft Defender for Office 365 の組織で利用可能な高度なフィッシング対策ポリシーを作成、変更、削除する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 89b931b37119d7c8c689d0f3c044fcd550db67ab
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287499"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="95c08-103">Microsoft Defender でフィッシング対策ポリシーを構成する (Office 365)</span><span class="sxs-lookup"><span data-stu-id="95c08-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="95c08-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="95c08-104">**Applies to**</span></span>
- [<span data-ttu-id="95c08-105">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="95c08-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="95c08-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="95c08-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="95c08-107">[microsoft Defender for Office 365](office-365-atp.md)のフィッシング対策ポリシーは、悪意のある偽装ベースのフィッシング攻撃や他の種類のフィッシング攻撃から組織を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="95c08-107">Anti-phishing policies in [Microsoft Defender for Office 365](office-365-atp.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="95c08-108">Exchange Online Protection (EOP) のフィッシング対策ポリシーと Microsoft Defender for Office 365 のフィッシング対策ポリシーの違いの詳細については、「フィッシング対策保護[](anti-phishing-protection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95c08-108">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="95c08-109">管理者は、既定のフィッシング詐欺対策ポリシーを表示、編集、構成 (削除しない) できます。</span><span class="sxs-lookup"><span data-stu-id="95c08-109">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="95c08-110">よりきめ細かく管理するために、組織内の特定のユーザー、グループ、またはドメインに適用されるカスタムフィッシング対策ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="95c08-110">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="95c08-111">カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (実行順序) を変更できます。</span><span class="sxs-lookup"><span data-stu-id="95c08-111">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="95c08-112">フィッシング対策ポリシーは、セキュリティ/コンプライアンス センターまたは Exchange Online PowerShell &構成できます。</span><span class="sxs-lookup"><span data-stu-id="95c08-112">You can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="95c08-113">Exchange Online Protection 組織 (つまり、Microsoft Defender for Office 365 を使用しない組織) で利用可能なフィッシング対策ポリシーの構成の詳細については [、「EOP](configure-anti-phishing-policies-eop.md)でフィッシング対策ポリシーを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95c08-113">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, organizations without Microsoft Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="95c08-114">フィッシング対策ポリシーの基本的な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="95c08-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="95c08-115">**フィッシング対策ポリシー**: 有効または無効にするフィッシング対策と、オプションを適用するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="95c08-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="95c08-116">**フィッシング対策ルール**: フィッシング対策ポリシーの優先度と受信者フィルター (ポリシーが適用されるユーザー) を指定します。</span><span class="sxs-lookup"><span data-stu-id="95c08-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="95c08-117">これらの 2 つの要素の違いは、セキュリティ/コンプライアンス センターでフィッシング対策ポリシーを管理&明らかではありません。</span><span class="sxs-lookup"><span data-stu-id="95c08-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="95c08-118">ポリシーを作成する場合、実際には、両方に同じ名前を使用して、フィッシング対策ルールと関連付けられたフィッシング対策ポリシーを同時に作成します。</span><span class="sxs-lookup"><span data-stu-id="95c08-118">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="95c08-119">ポリシーを変更すると、名前、優先度、有効または無効、受信者フィルターに関連する設定によってフィッシング対策ルールが変更されます。</span><span class="sxs-lookup"><span data-stu-id="95c08-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="95c08-120">その他のすべての設定では、関連するフィッシング対策ポリシーが変更されます。</span><span class="sxs-lookup"><span data-stu-id="95c08-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="95c08-121">ポリシーを削除すると、フィッシング対策ルールと関連するフィッシング対策ポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="95c08-121">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="95c08-122">Exchange Online PowerShell では、ポリシーとルールを個別に管理します。</span><span class="sxs-lookup"><span data-stu-id="95c08-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="95c08-123">詳細については、後の「Exchange Online PowerShell を使用して [Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) のフィッシング対策ポリシーを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95c08-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) section later in this article.</span></span>

<span data-ttu-id="95c08-124">Office 365 組織のすべての Microsoft Defender には、次のプロパティを持つ Office365 AntiPhish Default という名前の組み込みのフィッシング対策ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="95c08-124">Every Microsoft Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="95c08-125">ポリシーに関連付けられているフィッシング対策ルール (受信者フィルター) がない場合でも、ポリシーは組織内のすべての受信者に適用されます。</span><span class="sxs-lookup"><span data-stu-id="95c08-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="95c08-126">ポリシーにはカスタムの優先順位の値 **Lowest** が設定されており、変更することはできません (このポリシーは常に最後に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="95c08-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="95c08-127">作成するどのカスタム ポリシーも、より高い優先順位を持ちます。</span><span class="sxs-lookup"><span data-stu-id="95c08-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="95c08-128">ポリシーは既定のポリシー (**IsDefault** のプロパティが `True` の値になっている) であり、既定のポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="95c08-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="95c08-129">microsoft Defender for Office 365 のフィッシング対策保護の効果を高めるには、特定のユーザーまたはユーザー グループに適用されるより厳しい設定を使用して、カスタムのフィッシング対策ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="95c08-129">To increase the effectiveness of anti-phishing protection in Microsoft Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="95c08-130">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="95c08-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="95c08-131"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="95c08-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="95c08-132">ATP フィッシング詐欺対策ページ **に直接移動するには** 、次のコマンドを使用します <https://protection.office.com/antiphishing> 。</span><span class="sxs-lookup"><span data-stu-id="95c08-132">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="95c08-133">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95c08-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="95c08-134">この記事に記載の手順を行うには、セキュリティ/コンプライアンス センターのアクセス許可が割り当てられている必要があります:</span><span class="sxs-lookup"><span data-stu-id="95c08-134">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="95c08-135">フィッシング対策ポリシーを追加、変更、および削除するには、組織の管理役割グループまたはセキュリティ管理者役割グループのメンバー **である** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="95c08-135">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="95c08-136">フィッシング対策ポリシーに読み取り専用でアクセスするには、グローバル閲覧者またはセキュリティ閲覧者の役割グループのメンバー **である必要** があります <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="95c08-136">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="95c08-137">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95c08-137">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="95c08-138">**注**:</span><span class="sxs-lookup"><span data-stu-id="95c08-138">**Notes**:</span></span>

  - <span data-ttu-id="95c08-139">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、セキュリティ/コンプライアンス センター の必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="95c08-139">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="95c08-140">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95c08-140">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="95c08-141">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) **の View-Only Organization Management** 役割グループは、この機能への読み取り専用アクセスも提供します <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="95c08-141">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="95c08-142"><sup>\*</sup> セキュリティ センターコンプライアンス センター&読み取り専用アクセスにより、ユーザーはカスタムフィッシング対策ポリシーの設定を表示できます。</span><span class="sxs-lookup"><span data-stu-id="95c08-142"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="95c08-143">読み取り専用のユーザーは、既定のフィッシング対策ポリシーの設定を表示できない。</span><span class="sxs-lookup"><span data-stu-id="95c08-143">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="95c08-144">Office 365 向け Microsoft Defender のフィッシング対策ポリシーの推奨設定については、「Office [365](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)の設定」の「Defender のフィッシング対策ポリシー」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95c08-144">For our recommended settings for anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="95c08-145">新しいポリシーまたは更新されたポリシーを適用するには、最大 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="95c08-145">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="95c08-146">フィッシング対策ポリシーがフィルター パイプラインで適用される場所の詳細については、「電子メール保護の順序と優先順位」 [を参照してください](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="95c08-146">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="95c08-147">セキュリティ/コンプライアンス センター&使用して、Microsoft Defender for Office 365 でフィッシング対策ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="95c08-147">Use the Security & Compliance Center to create anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="95c08-148">セキュリティ & コンプライアンス センターでカスタムフィッシング対策ポリシーを作成すると、両方に同じ名前を使用して、フィッシング対策ルールと関連付けられたフィッシング対策ポリシーが同時に作成されます。</span><span class="sxs-lookup"><span data-stu-id="95c08-148">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="95c08-149">フィッシング対策ポリシーを作成する場合、ポリシーの名前、説明、およびポリシーが適用されるユーザーを識別する受信者フィルターのみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="95c08-149">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="95c08-150">ポリシーを作成した後、ポリシーを変更して、既定のフィッシング対策設定を変更または確認できます。</span><span class="sxs-lookup"><span data-stu-id="95c08-150">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="95c08-151">セキュリティ/コンプライアンス センター&、脅威 **管理ポリシー** ATP のフィッシング対策 \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="95c08-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="95c08-152">[フィッシング対策 **] ページで、[作成** ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="95c08-152">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="95c08-153">新 **しいフィッシング対策ポリシーの作成ウィザードが** 開きます。</span><span class="sxs-lookup"><span data-stu-id="95c08-153">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="95c08-154">[ポリシー **に名前を付け] ページ** で、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="95c08-154">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="95c08-155">**[名前]**: わかりやすい一意のポリシー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="95c08-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="95c08-156">**[説明]**: ポリシーについての説明を入力します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="95c08-156">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="95c08-157">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95c08-157">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="95c08-158">表示される **[適用先** ] ページで、ポリシーが適用される内部受信者を特定します。</span><span class="sxs-lookup"><span data-stu-id="95c08-158">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="95c08-159">各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="95c08-159">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="95c08-160">同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="95c08-160">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="95c08-161">a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="95c08-161">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="95c08-162">[条件 **の追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="95c08-162">Click **Add a condition**.</span></span> <span data-ttu-id="95c08-163">表示されるドロップダウンで、[適用] の下の条件を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="95c08-163">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="95c08-164">**受信者は、** 組織内の 1 つ以上のメールボックス、メール ユーザー、またはメール連絡先を指定します。</span><span class="sxs-lookup"><span data-stu-id="95c08-164">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="95c08-165">**受信者が次のメンバーである**: 組織内の 1 つ以上のグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="95c08-165">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="95c08-166">**受信者のドメイン:** 組織内で構成されている 1 つ以上の承認されたドメインの受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="95c08-166">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="95c08-167">条件を選択すると、対応するドロップダウンが [任意] ボックス **と一緒に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="95c08-167">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="95c08-168">ボックス内をクリックし、値の一覧をスクロールして選択します。</span><span class="sxs-lookup"><span data-stu-id="95c08-168">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="95c08-169">ボックス内をクリックし、入力を開始してリストをフィルター処理し、値を選択します。</span><span class="sxs-lookup"><span data-stu-id="95c08-169">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="95c08-170">値を追加するには、ボックス内の空の領域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95c08-170">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="95c08-171">個々のエントリを削除するには、値の **[削除]** ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="95c08-171">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="95c08-172">条件全体を削除するには、条件の **[削除**] ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="95c08-172">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="95c08-173">追加の条件を追加するには、[条件の追加] **をクリック** し、[適用する条件] の下の残りの値 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="95c08-173">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="95c08-174">例外を追加するには、[条件の追加] をクリックし、[条件以外] で例外 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="95c08-174">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="95c08-175">設定と動作は、条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="95c08-175">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="95c08-176">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95c08-176">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="95c08-177">表示される **[設定の確認** ] ページで、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="95c08-177">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="95c08-178">各設定で **[編集]** をクリックして変更できます。</span><span class="sxs-lookup"><span data-stu-id="95c08-178">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="95c08-179">完了したら、[このポリシーの作成 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="95c08-179">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="95c08-180">表示 **される確認ダイアログで [OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95c08-180">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="95c08-181">これらの全般設定でフィッシング対策ポリシーを作成した後、次のセクションの手順を使用して、ポリシーの保護設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="95c08-181">After you create the anti-phishing policy with these general settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="95c08-182">セキュリティ/コンプライアンス センター&使用して、Microsoft Defender for Office 365 のフィッシング対策ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="95c08-182">Use the Security & Compliance Center to modify anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="95c08-183">フィッシング対策ポリシー (作成した新しいポリシー、または既にカスタマイズした既存のポリシー) を変更するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="95c08-183">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="95c08-184">まだお持ちではない場合は、セキュリティ/コンプライアンス センター&開き、脅威 **管理** ポリシー ATP のフィッシング \>  \> **対策に移動します**。</span><span class="sxs-lookup"><span data-stu-id="95c08-184">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="95c08-185">変更するカスタムフィッシング対策ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="95c08-185">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="95c08-186">既に選択されている場合は、選択を解除して、もう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="95c08-186">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="95c08-187">[**ポリシーの編集 \<name\> ]** フライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="95c08-187">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="95c08-188">任意の **セクションで [** 編集] をクリックすると、そのセクションの設定にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="95c08-188">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="95c08-189">次の手順は、セクションが表示される順序で示されますが、順番には表示されません (セクションは任意の順序で選択および変更できます)。</span><span class="sxs-lookup"><span data-stu-id="95c08-189">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="95c08-190">セクションで [編集] をクリックすると、使用可能な設定がウィザード形式で表示されますが、任意の順序でページ内に移動できます。また、任意のページで [保存]  (または [キャンセル] または [閉じる] アイコン) をクリックしてポリシーの編集ページに戻ります ![ ](../../media/scc-remove-icon.png) (**\<name\>** 保存または終了するには、ウィザードの最後のページにアクセスする必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="95c08-190">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="95c08-191">**ポリシー設定**: [編集 **]** をクリックして、前の [](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365)セクションでポリシーを作成した場合と同じ設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="95c08-191">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) in the previous section:</span></span>

   - <span data-ttu-id="95c08-192">**名前**</span><span class="sxs-lookup"><span data-stu-id="95c08-192">**Name**</span></span>
   - <span data-ttu-id="95c08-193">**説明**</span><span class="sxs-lookup"><span data-stu-id="95c08-193">**Description**</span></span>
   - <span data-ttu-id="95c08-194">**適用先**</span><span class="sxs-lookup"><span data-stu-id="95c08-194">**Applied to**</span></span>
   - <span data-ttu-id="95c08-195">**設定を確認する**</span><span class="sxs-lookup"><span data-stu-id="95c08-195">**Review your settings**</span></span>

   <span data-ttu-id="95c08-196">完了したら、任意のページで [保存 **]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95c08-196">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="95c08-197">**偽装 :**[編集 **]** をクリックして、ポリシー内の保護された送信者と保護されたドメインを変更します。</span><span class="sxs-lookup"><span data-stu-id="95c08-197">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="95c08-198">これらの設定は、受信メッセージの差出人アドレスでスプーフィングされた送信者が (個別に、またはドメインごとに) 探すポリシーの条件です。</span><span class="sxs-lookup"><span data-stu-id="95c08-198">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="95c08-199">詳細については、「Microsoft Defender for Office [365」](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95c08-199">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="95c08-200">**保護するユーザーを追加** する : 既定値は [オフ] **です**。</span><span class="sxs-lookup"><span data-stu-id="95c08-200">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="95c08-201">有効にする場合は、トグルを **[オン**] にスライドし、表示される **[ユーザー** の追加] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="95c08-201">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="95c08-202">表示される **[ユーザーの追加** ] フライアウトで、次の値を構成します。</span><span class="sxs-lookup"><span data-stu-id="95c08-202">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="95c08-203">**電子メール アドレス**:</span><span class="sxs-lookup"><span data-stu-id="95c08-203">**Email address**:</span></span>

       - <span data-ttu-id="95c08-204">ボックス内をクリックし、ユーザーの一覧をスクロールして選択します。</span><span class="sxs-lookup"><span data-stu-id="95c08-204">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="95c08-205">ボックスをクリックし、入力を開始してリストをフィルター処理し、ユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="95c08-205">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="95c08-206">エントリを削除するには、ユーザーの **[削除]** ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="95c08-206">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="95c08-207">**[** 名前]: この値は、選択したメール アドレスに基づいて設定されますが、変更できます。</span><span class="sxs-lookup"><span data-stu-id="95c08-207">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="95c08-208">完了したら、任意のページで [保存 **]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95c08-208">When you're finished, click **Save** on any page.</span></span>

     <span data-ttu-id="95c08-209">既存のエントリを編集するには、一覧で保護されたユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="95c08-209">To edit an existing entry, select the protected user in the list.</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="95c08-210">各フィッシング対策ポリシーでは、最大 60 人の保護されたユーザー (送信者の電子メール アドレス) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="95c08-210">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="95c08-211">複数のポリシーで同じ保護されたユーザーを指定できない。</span><span class="sxs-lookup"><span data-stu-id="95c08-211">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="95c08-212">送信者と受信者が以前に電子メールで通信した場合、ユーザー偽装保護は機能しません。</span><span class="sxs-lookup"><span data-stu-id="95c08-212">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="95c08-213">送信者と受信者が電子メールで通信したことがない場合、メッセージは偽装の試行として識別されます。</span><span class="sxs-lookup"><span data-stu-id="95c08-213">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

   - <span data-ttu-id="95c08-214">**保護するドメインを追加** する : 次の設定の一方または両方を構成します。</span><span class="sxs-lookup"><span data-stu-id="95c08-214">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="95c08-215">**所有しているドメインを自動的に含める**: 既定値は **[オフ] です**。</span><span class="sxs-lookup"><span data-stu-id="95c08-215">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="95c08-216">オンに切り替えるには、トグルを [オン] に **スライドします**。</span><span class="sxs-lookup"><span data-stu-id="95c08-216">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="95c08-217">**カスタム ドメインを含める**: 既定値は **オフです**。</span><span class="sxs-lookup"><span data-stu-id="95c08-217">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="95c08-218">有効にする場合は、トグルを **[オン**] にスライドし、[ドメインの追加] ボックスにドメイン名 (contoso.com など) を入力し、Enter キーを押して、必要に応じて繰り返します。</span><span class="sxs-lookup"><span data-stu-id="95c08-218">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

     > [!NOTE]
     > <span data-ttu-id="95c08-219">すべてのフィッシング対策ポリシーには、最大 50 のドメインを設定できます。</span><span class="sxs-lookup"><span data-stu-id="95c08-219">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

   - <span data-ttu-id="95c08-220">**Actions**: Click **Edit**</span><span class="sxs-lookup"><span data-stu-id="95c08-220">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="95c08-221">**偽装ユーザー** によって電子メールが送信される場合: 「保護するユーザーを追加する」で指定した保護されたユーザーの 1 つが、スプーフィングされた送信者であるメッセージに対して次のいずれかのアクションを **構成します**。</span><span class="sxs-lookup"><span data-stu-id="95c08-221">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="95c08-222">**アクションを適用しない**</span><span class="sxs-lookup"><span data-stu-id="95c08-222">**Don't apply any action**</span></span>
       - <span data-ttu-id="95c08-223">**メッセージを他のメール アドレスにリダイレクトする**</span><span class="sxs-lookup"><span data-stu-id="95c08-223">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="95c08-224">**メッセージを [迷惑メール] フォルダーに移動する**</span><span class="sxs-lookup"><span data-stu-id="95c08-224">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="95c08-225">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="95c08-225">**Quarantine the message**</span></span>
       - <span data-ttu-id="95c08-226">**メッセージを配信し、BCC 行に他のアドレスを追加する**</span><span class="sxs-lookup"><span data-stu-id="95c08-226">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="95c08-227">**配信前にメッセージを削除する**</span><span class="sxs-lookup"><span data-stu-id="95c08-227">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="95c08-228">**偽装された** ドメインによって電子メールが送信される場合: 「ドメインの追加」で指定した保護されたドメインの 1 つにスプーフィングされた送信者が含むメッセージに対して、次のいずれかのアクションを構成 **します**。</span><span class="sxs-lookup"><span data-stu-id="95c08-228">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

       - <span data-ttu-id="95c08-229">**アクションを適用しない**</span><span class="sxs-lookup"><span data-stu-id="95c08-229">**Don't apply any action**</span></span>
       - <span data-ttu-id="95c08-230">**メッセージを他のメール アドレスにリダイレクトする**</span><span class="sxs-lookup"><span data-stu-id="95c08-230">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="95c08-231">**メッセージを [迷惑メール] フォルダーに移動する**</span><span class="sxs-lookup"><span data-stu-id="95c08-231">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="95c08-232">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="95c08-232">**Quarantine the message**</span></span>
       - <span data-ttu-id="95c08-233">**メッセージを配信し、BCC 行に他のアドレスを追加する**</span><span class="sxs-lookup"><span data-stu-id="95c08-233">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="95c08-234">**配信前にメッセージを削除する**</span><span class="sxs-lookup"><span data-stu-id="95c08-234">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="95c08-235">[ **偽装の安全性に関するヒントをオンにする** ] をクリックし、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="95c08-235">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="95c08-236">**偽装したユーザーのヒントを表示** する : 既定値は **[オフ] です**。</span><span class="sxs-lookup"><span data-stu-id="95c08-236">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="95c08-237">オンに切り替えるには、トグルを [オン] に **スライドします**。</span><span class="sxs-lookup"><span data-stu-id="95c08-237">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="95c08-238">**偽装されたドメインのヒントを表示** する : 既定値は **[オフ] です**。</span><span class="sxs-lookup"><span data-stu-id="95c08-238">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="95c08-239">オンに切り替えるには、トグルを [オン] に **スライドします**。</span><span class="sxs-lookup"><span data-stu-id="95c08-239">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="95c08-240">**通常と異なっている文字のヒント** を表示する : 既定値は **オフです**。</span><span class="sxs-lookup"><span data-stu-id="95c08-240">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="95c08-241">オンに切り替えるには、トグルを [オン] に **スライドします**。</span><span class="sxs-lookup"><span data-stu-id="95c08-241">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="95c08-242">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95c08-242">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="95c08-243">**メールボックス インテリジェンス**:</span><span class="sxs-lookup"><span data-stu-id="95c08-243">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="95c08-244">**メールボックス インテリジェンスを有効にする:** 既定値は **[オン] です**。</span><span class="sxs-lookup"><span data-stu-id="95c08-244">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="95c08-245">オフに切り替えるには、トグルを [オフ] に **スライドします**。</span><span class="sxs-lookup"><span data-stu-id="95c08-245">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="95c08-246">**メールボックス インテリジェンス ベースの偽装保護を** 有効にする: この設定は、[メールボックス インテリジェンスを有効にする] が [オン] の場合 **にのみ** 使用 **できます**。</span><span class="sxs-lookup"><span data-stu-id="95c08-246">**Enable mailbox intelligence based impersonation protection?**: This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="95c08-247">In **If email is sent by an impersonated user,** you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span><span class="sxs-lookup"><span data-stu-id="95c08-247">In **If email is sent by an impersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="95c08-248">**アクションを適用しない**</span><span class="sxs-lookup"><span data-stu-id="95c08-248">**Don't apply any action**</span></span>
       - <span data-ttu-id="95c08-249">**メッセージを他のメール アドレスにリダイレクトする**</span><span class="sxs-lookup"><span data-stu-id="95c08-249">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="95c08-250">**メッセージを [迷惑メール] フォルダーに移動する**</span><span class="sxs-lookup"><span data-stu-id="95c08-250">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="95c08-251">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="95c08-251">**Quarantine the message**</span></span>
       - <span data-ttu-id="95c08-252">**メッセージを配信し、BCC 行に他のアドレスを追加する**</span><span class="sxs-lookup"><span data-stu-id="95c08-252">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="95c08-253">**配信前にメッセージを削除する**</span><span class="sxs-lookup"><span data-stu-id="95c08-253">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="95c08-254">**信頼できる送信者とドメインを追加** する : ポリシーの例外を指定します。</span><span class="sxs-lookup"><span data-stu-id="95c08-254">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="95c08-255">**信頼できる送信者**:</span><span class="sxs-lookup"><span data-stu-id="95c08-255">**Trusted senders**:</span></span>

       - <span data-ttu-id="95c08-256">ボックス内をクリックし、ユーザーの一覧をスクロールして選択します。</span><span class="sxs-lookup"><span data-stu-id="95c08-256">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="95c08-257">ボックスをクリックし、入力を開始してリストをフィルター処理し、ユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="95c08-257">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="95c08-258">エントリを削除するには、ユーザーの **[削除]** ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="95c08-258">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="95c08-259">**信頼されたドメイン**: ドメイン名 (たとえば、contoso.com) を入力し、Enter キーを押して、必要に応じて繰り返します。</span><span class="sxs-lookup"><span data-stu-id="95c08-259">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="95c08-260">**設定を確認** します。個々の手順をクリックする代わりに、設定が概要に表示されます。</span><span class="sxs-lookup"><span data-stu-id="95c08-260">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="95c08-261">各セクションで **[編集]** をクリックすると、関連するページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="95c08-261">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="95c08-262">このページでは、次の設定 **をオン** または **オフ** に直接切り替えます。</span><span class="sxs-lookup"><span data-stu-id="95c08-262">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="95c08-263">**保護されたユーザー**</span><span class="sxs-lookup"><span data-stu-id="95c08-263">**Protected users**</span></span>
       - <span data-ttu-id="95c08-264">**保護されたドメイン** \>**所有しているドメインを含める**</span><span class="sxs-lookup"><span data-stu-id="95c08-264">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="95c08-265">**保護されたドメイン** \>**保護されたドメイン**(カスタム ドメイン)</span><span class="sxs-lookup"><span data-stu-id="95c08-265">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="95c08-266">**メールボックス インテリジェンス**</span><span class="sxs-lookup"><span data-stu-id="95c08-266">**Mailbox intelligence**</span></span>

   <span data-ttu-id="95c08-267">完了したら、任意のページで [保存 **]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95c08-267">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="95c08-268">**ス** プーフィング : **[編集** ] をクリックして、スプーフィング インテリジェンスを有効またはオフにし、Outlook の認証されていない送信者の識別をオンまたはオフにし、ブロックされたスプーフィングされた送信者からのメッセージに適用するアクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="95c08-268">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="95c08-269">詳細については、「フィッシング対策ポリシー [のスプーフィング設定」を参照してください](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="95c08-269">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="95c08-270">これらの同じ設定は、EOP のフィッシング対策ポリシーでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="95c08-270">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="95c08-271">**スプーフィング フィルターの** 設定 : 既定値は **[オン**] であり、オンのままにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="95c08-271">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="95c08-272">オフに切り替えるには、トグルを [オフ] に **スライドします**。</span><span class="sxs-lookup"><span data-stu-id="95c08-272">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="95c08-273">詳細については [、「EOP でスプーフィング インテリジェンスを構成する」を参照してください](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="95c08-273">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="95c08-274">MX レコードが Microsoft 365 をポイントしない場合は、スプーフィング対策保護を無効にする必要があります。コネクタの拡張フィルターを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="95c08-274">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="95c08-275">手順については [、「Exchange Online のコネクタの拡張フィルター処理」を参照してください](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="95c08-275">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="95c08-276">**認証されていない送信者機能を有効** にする : 既定値は **[オン] です**。</span><span class="sxs-lookup"><span data-stu-id="95c08-276">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="95c08-277">オフに切り替えるには、トグルを [オフ] に **スライドします**。</span><span class="sxs-lookup"><span data-stu-id="95c08-277">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="95c08-278">**アクション**: スプーフィング インテリジェンスに失敗したメッセージに対して実行するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="95c08-278">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="95c08-279">**ドメインのなりすましを許可されていないユーザーからメールが送信された場合**:</span><span class="sxs-lookup"><span data-stu-id="95c08-279">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="95c08-280">**受信者の迷惑メール フォルダーにメッセージを移動する**</span><span class="sxs-lookup"><span data-stu-id="95c08-280">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="95c08-281">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="95c08-281">**Quarantine the message**</span></span>

   - <span data-ttu-id="95c08-282">**設定を確認** します。個々の手順をクリックする代わりに、設定が概要に表示されます。</span><span class="sxs-lookup"><span data-stu-id="95c08-282">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="95c08-283">各セクションで **[編集]** をクリックすると、関連するページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="95c08-283">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="95c08-284">このページでは、次の設定 **をオン** または **オフ** に直接切り替えます。</span><span class="sxs-lookup"><span data-stu-id="95c08-284">You can toggle the following settings **On** or **Off** directly on this page:</span></span>
       - <span data-ttu-id="95c08-285">**スプーフ対策保護を有効にする**</span><span class="sxs-lookup"><span data-stu-id="95c08-285">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="95c08-286">**認証されていない送信者機能を有効にする**</span><span class="sxs-lookup"><span data-stu-id="95c08-286">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="95c08-287">完了したら、任意のページで [保存 **]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95c08-287">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="95c08-288">**[詳細設定**] : [ **編集]** をクリックして、高度なフィッシングしきい値を構成します。</span><span class="sxs-lookup"><span data-stu-id="95c08-288">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="95c08-289">詳細については、Microsoft Defender for Office [365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)のフィッシング対策ポリシーの高度なフィッシングしきい値を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95c08-289">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="95c08-290">**高度なフィッシングのしきい値**: 次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="95c08-290">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="95c08-291">**1 - 標準** (これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="95c08-291">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="95c08-292">**2 - 積極的**</span><span class="sxs-lookup"><span data-stu-id="95c08-292">**2 - Aggressive**</span></span>
   - <span data-ttu-id="95c08-293">**3 - より積極的**</span><span class="sxs-lookup"><span data-stu-id="95c08-293">**3 - More aggressive**</span></span>
   - <span data-ttu-id="95c08-294">**4 - 最も積極的**</span><span class="sxs-lookup"><span data-stu-id="95c08-294">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="95c08-295">**設定を確認する**: [編集 **] を** クリックして、[高度なフィッシングのしきい値 **] ページに戻** ります。</span><span class="sxs-lookup"><span data-stu-id="95c08-295">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="95c08-296">完了したら、いずれかのページで [保存 **]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95c08-296">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="95c08-297">[ポリシーの編集 **] \<Name\> ページに戻** り、設定を確認し、[閉じる] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="95c08-297">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a><span data-ttu-id="95c08-298">セキュリティ/コンプライアンス センター&使用して、Microsoft Defender for Office 365 の既定のフィッシング対策ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="95c08-298">Use the Security & Compliance Center to modify the default anti-phishing policy in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="95c08-299">microsoft Defender for Office 365 の既定のフィッシング対策ポリシーは Office365 AntiPhish Default という名前で、ポリシーの一覧には表示されません。</span><span class="sxs-lookup"><span data-stu-id="95c08-299">The default anti-phishing policy in Microsoft Defender for Office 365 is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="95c08-300">既定のフィッシング対策ポリシーを変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="95c08-300">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="95c08-301">セキュリティ/コンプライアンス センター&、脅威 **管理ポリシー** ATP のフィッシング対策 \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="95c08-301">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="95c08-302">[フィッシング対策 **] ページで、[** 既定のポリシー] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="95c08-302">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="95c08-303">[ **ポリシーの編集] の [Office365 AntiPhish Default] ページ** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="95c08-303">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="95c08-304">以下のセクションを使用できます。カスタム ポリシーを変更する場合と同じ設定 [が含まれます](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="95c08-304">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span></span>

   - <span data-ttu-id="95c08-305">**偽装**</span><span class="sxs-lookup"><span data-stu-id="95c08-305">**Impersonation**</span></span>
   - <span data-ttu-id="95c08-306">**スプーフィング**</span><span class="sxs-lookup"><span data-stu-id="95c08-306">**Spoof**</span></span>
   - <span data-ttu-id="95c08-307">**詳細設定**</span><span class="sxs-lookup"><span data-stu-id="95c08-307">**Advanced settings**</span></span>

   <span data-ttu-id="95c08-308">既定のポリシーを変更する場合、次の設定は使用できません。</span><span class="sxs-lookup"><span data-stu-id="95c08-308">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="95c08-309">[ポリシー設定]セクションと値を確認できますが、[編集]リンクは表示されません。そのため、設定 (ポリシー名、説明、およびポリシーが適用されるユーザー (すべての受信者に適用されます) を変更できない。</span><span class="sxs-lookup"><span data-stu-id="95c08-309">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="95c08-310">既定のポリシーは削除できない。</span><span class="sxs-lookup"><span data-stu-id="95c08-310">You can't delete the default policy.</span></span>
   - <span data-ttu-id="95c08-311">既定のポリシーの優先度は変更できない (常に最後に適用される)。</span><span class="sxs-lookup"><span data-stu-id="95c08-311">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="95c08-312">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span><span class="sxs-lookup"><span data-stu-id="95c08-312">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="95c08-313">Microsoft Defender でカスタムフィッシング対策ポリシーを有効または無効にする (Office 365)</span><span class="sxs-lookup"><span data-stu-id="95c08-313">Enable or disable custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="95c08-314">セキュリティ/コンプライアンス センター&、脅威 **管理ポリシー** ATP のフィッシング対策 \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="95c08-314">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="95c08-315">[状態] 列の値 **に注意** してください。</span><span class="sxs-lookup"><span data-stu-id="95c08-315">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="95c08-316">トグルを [ **オフ] にスライド** してポリシーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="95c08-316">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="95c08-317">トグルを [ **オン] にスライドして** ポリシーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="95c08-317">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="95c08-318">既定のフィッシング詐欺対策ポリシーを無効にできない。</span><span class="sxs-lookup"><span data-stu-id="95c08-318">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="95c08-319">Microsoft Defender でカスタムフィッシング対策ポリシーの優先度を設定する (Office 365)</span><span class="sxs-lookup"><span data-stu-id="95c08-319">Set the priority of custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="95c08-320">既定では、フィッシング詐欺対策ポリシーには、作成された順序に基づく優先度が設定されます (新しいポリシーは、古いポリシーよりも優先度が低くなります)。</span><span class="sxs-lookup"><span data-stu-id="95c08-320">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="95c08-321">優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。</span><span class="sxs-lookup"><span data-stu-id="95c08-321">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="95c08-322">2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。</span><span class="sxs-lookup"><span data-stu-id="95c08-322">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="95c08-323">優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95c08-323">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="95c08-324">カスタムフィッシング詐欺対策ポリシーは、処理順に表示されます (最初のポリシーの **優先度** の値は 0 です)。</span><span class="sxs-lookup"><span data-stu-id="95c08-324">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="95c08-325">Office365 AntiPhish Default という名前の既定のフィッシング詐欺対策ポリシーにはカスタムの優先度値 **Lowest** が設定されています。この値は変更できます。</span><span class="sxs-lookup"><span data-stu-id="95c08-325">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="95c08-326">**注**: セキュリティ & コンプライアンス センターでは、フィッシング対策ポリシーを作成した後にのみ、優先度を変更できます。</span><span class="sxs-lookup"><span data-stu-id="95c08-326">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="95c08-327">PowerShell では、フィッシング対策ルールの作成時に既定の優先度を上書きできます (既存のルールの優先度に影響を与える可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="95c08-327">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="95c08-328">ポリシーの優先度を変更するには、ポリシーのプロパティで [優先度の引き上げ] または [優先度の下げ]をクリックします (セキュリティ/コンプライアンス センターで優先度番号を直接変更&することはできません)。 </span><span class="sxs-lookup"><span data-stu-id="95c08-328">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="95c08-329">ポリシーの優先度の変更は、複数のポリシーがある場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="95c08-329">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="95c08-330">セキュリティ/コンプライアンス センター&、脅威 **管理ポリシー** ATP のフィッシング対策 \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="95c08-330">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="95c08-331">変更するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="95c08-331">Select the policy that you want to modify.</span></span> <span data-ttu-id="95c08-332">既に選択されている場合は、選択を解除して、もう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="95c08-332">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="95c08-333">[**ポリシーの編集 \<name\> ]** フライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="95c08-333">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="95c08-334">優先度の値が **0** のカスタムフィッシング詐欺対策ポリシーでは、[優先度の下がり]**ボタンしか** 使用できません。</span><span class="sxs-lookup"><span data-stu-id="95c08-334">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="95c08-335">優先度の値が最も低いカスタムフィッシング詐欺対策ポリシー (**たとえば、3)** では、[優先度の引き上げ]**ボタンしか使用** できません。</span><span class="sxs-lookup"><span data-stu-id="95c08-335">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="95c08-336">3 つ以上のカスタムフィッシング詐欺対策ポリシーがある場合は、優先度の高い値と最も低い値の間のポリシーの [優先度の引き上げ] ボタンと [優先度の下げ] ボタンの両方を使用できます。</span><span class="sxs-lookup"><span data-stu-id="95c08-336">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="95c08-337">[優先度 **の引き上げ** ] または **[優先度の下げ** ] をクリックして、[優先度] の **値を変更** します。</span><span class="sxs-lookup"><span data-stu-id="95c08-337">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="95c08-338">完了したら、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95c08-338">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="95c08-339">セキュリティ/コンプライアンス センター&使用して、Microsoft Defender for Office 365 のフィッシング対策ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="95c08-339">Use the Security & Compliance Center to view anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="95c08-340">セキュリティ/コンプライアンス センター&、脅威 **管理** ポリシー ATP のフィッシング対策 \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="95c08-340">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="95c08-341">次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="95c08-341">Do one of the following steps:</span></span>

   - <span data-ttu-id="95c08-342">表示するカスタムフィッシング対策ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="95c08-342">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="95c08-343">既に選択されている場合は、選択を解除して、もう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="95c08-343">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="95c08-344">既定 **のフィッシング** 対策ポリシーを表示するには、[既定のポリシー] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95c08-344">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="95c08-345">[**ポリシーの編集 \<name\> ]** フライアウトが表示され、設定と値を表示できます。</span><span class="sxs-lookup"><span data-stu-id="95c08-345">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="95c08-346">セキュリティ/コンプライアンス センター&使用して、Microsoft Defender for Office 365 のフィッシング対策ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="95c08-346">Use the Security & Compliance Center to remove anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="95c08-347">セキュリティ/コンプライアンス センター&、脅威 **管理ポリシー** ATP のフィッシング対策 \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="95c08-347">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="95c08-348">削除するポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="95c08-348">Select the policy that you want to remove.</span></span> <span data-ttu-id="95c08-349">既に選択されている場合は、選択を解除して、もう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="95c08-349">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="95c08-350">表示される **[ポリシー \<name\> の** 編集] フライアウトで、[ポリシーの削除]をクリックし、表示される警告ダイアログで [はい] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95c08-350">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="95c08-351">既定のポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="95c08-351">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="95c08-352">Exchange Online PowerShell を使用して Microsoft Defender でフィッシング対策ポリシーを構成する (Office 365)</span><span class="sxs-lookup"><span data-stu-id="95c08-352">Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="95c08-353">前述のように、スパム対策ポリシーは、フィッシング対策ポリシーとフィッシング対策ルールで構成されます。</span><span class="sxs-lookup"><span data-stu-id="95c08-353">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="95c08-354">Exchange Online PowerShell では、フィッシング対策ポリシーとフィッシング対策ルールの違いは明白です。</span><span class="sxs-lookup"><span data-stu-id="95c08-354">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="95c08-355">**\* -AntiPhishPolicy** コマンドレットを使用してフィッシング対策ポリシーを管理し **\* 、-AntiPhishRule** コマンドレットを使用してフィッシング対策ルールを管理します。</span><span class="sxs-lookup"><span data-stu-id="95c08-355">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="95c08-356">PowerShell では、最初にフィッシング対策ポリシーを作成し、次に、そのルールが適用されるポリシーを識別するフィッシング対策ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="95c08-356">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="95c08-357">PowerShell では、フィッシング対策ポリシーとフィッシング対策ルールの設定を個別に変更します。</span><span class="sxs-lookup"><span data-stu-id="95c08-357">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="95c08-358">PowerShell からフィッシング対策ポリシーを削除すると、対応するフィッシング対策ルールは自動的には削除されません。その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="95c08-358">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="95c08-359">PowerShell を使用してフィッシング対策ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="95c08-359">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="95c08-360">PowerShell でフィッシング対策ポリシーを作成するには、次の 2 つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="95c08-360">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="95c08-361">フィッシング対策ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="95c08-361">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="95c08-362">ルールが適用されるフィッシング対策ポリシーを指定するフィッシング対策ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="95c08-362">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="95c08-363">**注**:</span><span class="sxs-lookup"><span data-stu-id="95c08-363">**Notes**:</span></span>

- <span data-ttu-id="95c08-364">新しいフィッシング対策ルールを作成し、関連付けされていない既存のフィッシング対策ポリシーを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="95c08-364">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="95c08-365">フィッシング詐欺対策ルールは、複数のフィッシング対策ポリシーに関連付けらなけな。</span><span class="sxs-lookup"><span data-stu-id="95c08-365">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="95c08-366">ポリシーを作成するまで、セキュリティ/コンプライアンス センターで使用できない新しいフィッシング詐欺対策ポリシーに関する次の設定を構成&できます。</span><span class="sxs-lookup"><span data-stu-id="95c08-366">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="95c08-367">新しいポリシーを無効な状態 _で作成_ `$false` します **(New-AntiPhishRule コマンドレットで有効** )。</span><span class="sxs-lookup"><span data-stu-id="95c08-367">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="95c08-368"> _\<Number\>_ **New-AntiPhishRule** コマンドレットで、作成時のポリシーの優先度 (優先度) を設定します。</span><span class="sxs-lookup"><span data-stu-id="95c08-368">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="95c08-369">PowerShell で作成した新しいフィッシング対策ポリシーは、そのポリシーをフィッシング対策ルールに割り当てるまで、セキュリティ & コンプライアンス センターに表示されません。</span><span class="sxs-lookup"><span data-stu-id="95c08-369">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="95c08-370">手順 1: PowerShell を使用してフィッシング対策ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="95c08-370">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="95c08-371">フィッシング対策ポリシーを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="95c08-371">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="95c08-372">この例では、次の設定で Research Quarantine という名前のフィッシング対策ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="95c08-372">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="95c08-373">ポリシーは有効です _(Enabled_ パラメーターは使用しません。既定値は有効です `$true` )。</span><span class="sxs-lookup"><span data-stu-id="95c08-373">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="95c08-374">説明は、リサーチ部門のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="95c08-374">The description is: Research department policy.</span></span>
- <span data-ttu-id="95c08-375">すべての承認されたドメインに対する組織ドメインの保護と、組織のドメインに対する対象ドメインfabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="95c08-375">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="95c08-376">偽装から保護するユーザーとして Mai Fujito (mfujito@fabrikam.com) を指定します。</span><span class="sxs-lookup"><span data-stu-id="95c08-376">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="95c08-377">メールボックスのインテリジェンスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="95c08-377">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="95c08-378">メールボックス インテリジェンス保護を有効にし、検疫アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="95c08-378">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="95c08-379">安全性のヒントを有効にする。</span><span class="sxs-lookup"><span data-stu-id="95c08-379">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="95c08-380">構文およびパラメーターの詳細については [、「New-AntiPhishPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="95c08-380">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="95c08-381">手順 2: PowerShell を使用してフィッシング対策ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="95c08-381">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="95c08-382">フィッシング対策ルールを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="95c08-382">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="95c08-383">この例では、次の条件で Research Department という名前のフィッシング対策ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="95c08-383">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="95c08-384">ルールは、Research Quarantine という名前のフィッシング対策ポリシーに関連付けられている。</span><span class="sxs-lookup"><span data-stu-id="95c08-384">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="95c08-385">ルールは Research Department という名前のグループのメンバーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="95c08-385">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="95c08-386">_Priority_ パラメーターを使用していないので、既定の優先度が使用されます。</span><span class="sxs-lookup"><span data-stu-id="95c08-386">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="95c08-387">構文およびパラメーターの詳細については [、「New-AntiPhishRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="95c08-387">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="95c08-388">PowerShell を使用してフィッシング対策ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="95c08-388">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="95c08-389">既存のフィッシング対策ポリシーを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="95c08-389">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="95c08-390">この例では、指定したプロパティと一緒に、すべてのフィッシング対策ポリシーの要約リストを返します。</span><span class="sxs-lookup"><span data-stu-id="95c08-390">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="95c08-391">この例では、Executives という名前のフィッシング対策ポリシーのすべてのプロパティ値を返します。</span><span class="sxs-lookup"><span data-stu-id="95c08-391">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="95c08-392">構文およびパラメーターの詳細については [、「Get-AntiPhishPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="95c08-392">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="95c08-393">PowerShell を使用してフィッシング対策ルールを表示する</span><span class="sxs-lookup"><span data-stu-id="95c08-393">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="95c08-394">既存のフィッシング対策ルールを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="95c08-394">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="95c08-395">この例では、指定したプロパティと一緒に、すべてのフィッシング対策ルールの要約リストを返します。</span><span class="sxs-lookup"><span data-stu-id="95c08-395">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="95c08-396">ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="95c08-396">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="95c08-397">この例では、Contoso Executives という名前のフィッシング対策ルールのすべてのプロパティ値を返します。</span><span class="sxs-lookup"><span data-stu-id="95c08-397">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="95c08-398">構文およびパラメーターの詳細については [、「Get-AntiPhishRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)。</span><span class="sxs-lookup"><span data-stu-id="95c08-398">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="95c08-399">PowerShell を使用してフィッシング対策ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="95c08-399">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="95c08-400">次の項目以外に、PowerShell でフィッシング対策ポリシーを変更する場合も、「手順 [1: PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) を使用してフィッシング詐欺対策ポリシーを作成する」セクションで説明したように、ポリシーを作成する場合と同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="95c08-400">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this article.</span></span>

- <span data-ttu-id="95c08-401">指定したポリシーを既定のポリシー (すべてのユーザーに適用され、常に最も低い優先度に適用され、削除できない) に変える _MakeDefault_ スイッチは、PowerShell でフィッシング対策ポリシーを変更した場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="95c08-401">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="95c08-402">フィッシング対策ポリシーの名前を変更することはできません **(Set-AntiPhishPolicy** コマンドレットには _Name_ パラメーターはありません)。</span><span class="sxs-lookup"><span data-stu-id="95c08-402">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="95c08-403">セキュリティ/コンプライアンス センターでフィッシング詐欺対策ポリシーの名前を変更&、フィッシング対策ルールの名前 _を変更する_ のみです。</span><span class="sxs-lookup"><span data-stu-id="95c08-403">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="95c08-404">フィッシング対策ポリシーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="95c08-404">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="95c08-405">構文およびパラメーターの詳細については [、「Set-AntiPhishPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="95c08-405">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="95c08-406">PowerShell を使用してフィッシング対策ルールを変更する</span><span class="sxs-lookup"><span data-stu-id="95c08-406">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="95c08-407">PowerShell でフィッシング対策ルールを変更する場合に使用できない唯一の設定は、無効にされたルールを作成できる _Enabled_ パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="95c08-407">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="95c08-408">既存のフィッシング対策ルールを有効または無効にするには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="95c08-408">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="95c08-409">それ以外の場合は、PowerShell でフィッシング対策ルールを変更するときに追加の設定を使用できません。</span><span class="sxs-lookup"><span data-stu-id="95c08-409">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="95c08-410">「手順 [2: PowerShell](#step-2-use-powershell-to-create-an-anti-phish-rule) を使用してフィッシング対策ルールを作成する」セクションで説明したように、ルールを作成する場合と同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="95c08-410">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="95c08-411">フィッシング対策ルールを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="95c08-411">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="95c08-412">構文およびパラメーターの詳細については [、「Set-AntiPhishRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="95c08-412">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="95c08-413">PowerShell を使用してフィッシング対策ルールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="95c08-413">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="95c08-414">PowerShell でフィッシング対策ルールを有効または無効にすると、フィッシング対策ポリシー全体 (フィッシング対策ルールと割り当てられたフィッシング対策ポリシー) が有効または無効にされます。</span><span class="sxs-lookup"><span data-stu-id="95c08-414">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="95c08-415">既定のフィッシング詐欺対策ポリシーを有効または無効にできない (常にすべての受信者に適用される)。</span><span class="sxs-lookup"><span data-stu-id="95c08-415">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="95c08-416">PowerShell でフィッシング対策ルールを有効または無効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="95c08-416">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="95c08-417">この例では、Marketing Department という名前のフィッシング対策ルールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="95c08-417">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="95c08-418">この例では、同じルールを有効化します。</span><span class="sxs-lookup"><span data-stu-id="95c08-418">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="95c08-419">構文およびパラメーターの詳細については [、「Enable-AntiPhishRule」](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) および [「Disable-AntiPhishRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule)。</span><span class="sxs-lookup"><span data-stu-id="95c08-419">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="95c08-420">PowerShell を使用してフィッシング対策ルールの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="95c08-420">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="95c08-421">ルールに設定できる優先度の最高値値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="95c08-421">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="95c08-422">設定できる最低値はルールの数に依存します。</span><span class="sxs-lookup"><span data-stu-id="95c08-422">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="95c08-423">たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。</span><span class="sxs-lookup"><span data-stu-id="95c08-423">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="95c08-424">既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。</span><span class="sxs-lookup"><span data-stu-id="95c08-424">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="95c08-425">たとえば、カスタム ルールが 5 つあって (優先度 0 から 4)、1 つのルールの優先度を 2 に変更した場合には、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。</span><span class="sxs-lookup"><span data-stu-id="95c08-425">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="95c08-426">PowerShell でフィッシング対策ルールの優先度を設定するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="95c08-426">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="95c08-p148">この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。</span><span class="sxs-lookup"><span data-stu-id="95c08-p148">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="95c08-429">**注**:</span><span class="sxs-lookup"><span data-stu-id="95c08-429">**Notes**:</span></span>

- <span data-ttu-id="95c08-430">新しいルールを作成するときに優先度を設定するには、代わりに **New-AntiPhishRule** コマンドレットの _Priority_ パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="95c08-430">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="95c08-431">既定のフィッシング対策ポリシーには対応するフィッシング対策ルールが設定されていないので、常に変更できない優先度の値 Lowest が **設定されています**。</span><span class="sxs-lookup"><span data-stu-id="95c08-431">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="95c08-432">PowerShell を使用してフィッシング対策ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="95c08-432">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="95c08-433">PowerShell を使用してフィッシング対策ポリシーを削除する場合、対応するフィッシング対策ルールは削除されません。</span><span class="sxs-lookup"><span data-stu-id="95c08-433">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="95c08-434">PowerShell でフィッシング対策ポリシーを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="95c08-434">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="95c08-435">この例では、Marketing Department という名前のフィッシング対策ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="95c08-435">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="95c08-436">構文およびパラメーターの詳細については [、「Remove-AntiPhishPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="95c08-436">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="95c08-437">PowerShell を使用してフィッシング対策ルールを削除する</span><span class="sxs-lookup"><span data-stu-id="95c08-437">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="95c08-438">PowerShell を使用してフィッシング対策ルールを削除する場合、対応するフィッシング対策ポリシーは削除されません。</span><span class="sxs-lookup"><span data-stu-id="95c08-438">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="95c08-439">PowerShell でフィッシング対策ルールを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="95c08-439">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="95c08-440">この例では、Marketing Department という名前のフィッシング対策ルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="95c08-440">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="95c08-441">構文およびパラメーターの詳細については [、「Remove-AntiPhishRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)。</span><span class="sxs-lookup"><span data-stu-id="95c08-441">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="95c08-442">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="95c08-442">How do you know these procedures worked?</span></span>

<span data-ttu-id="95c08-443">Office 365 用に Microsoft Defender でフィッシング対策ポリシーが正常に構成されたことを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="95c08-443">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="95c08-444">セキュリティ/コンプライアンス センター&、脅威 **管理ポリシー** ATP のフィッシング対策 \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="95c08-444">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="95c08-445">ポリシーの一覧、その状態の値、 **および優先度** の値を **確認** します。</span><span class="sxs-lookup"><span data-stu-id="95c08-445">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="95c08-446">詳細を表示するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="95c08-446">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="95c08-447">一覧からポリシーを選択し、詳細をフライアウトで表示します。</span><span class="sxs-lookup"><span data-stu-id="95c08-447">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="95c08-448">[ **既定のポリシー]** をクリックし、詳細をフライアウトに表示します。</span><span class="sxs-lookup"><span data-stu-id="95c08-448">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="95c08-449">Exchange Online PowerShell で、ポリシーまたはルールの名前に置き換え、次のコマンドを実行 \<Name\> して設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="95c08-449">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
