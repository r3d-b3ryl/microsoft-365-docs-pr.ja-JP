---
title: コンテンツを自動的に保持または削除するアイテム保持ポリシーの詳細
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: アイテム保持ポリシーを使用すると、コンテンツを保持するか、コンテンツを削除するか、またはその両方かを積極的に決定できます。コンテンツを保持してから削除する、組織全体または特定の場所またはユーザーに単一のポリシーを適用する、すべてのコンテンツまたは特定の条件を満たすコンテンツにポリシーを適用する、などです。
ms.openlocfilehash: b91b4be724c3d664cdd237fc01596372a2a6bdcc
ms.sourcegitcommit: 5c96d06496d40d2523edbea336f7355c3c77cc80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412816"
---
# <a name="learn-about-retention-policies"></a><span data-ttu-id="a8c72-103">アイテム保持ポリシーの詳細</span><span class="sxs-lookup"><span data-stu-id="a8c72-103">Learn about retention policies</span></span>

><span data-ttu-id="a8c72-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="a8c72-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="a8c72-p101">ほとんどの組織では、電子メール、ドキュメント、インスタント メッセージなどのデータの量と複雑さが日々増しています。次の必要性から、これらの情報を効果的に管理することが重要です。</span><span class="sxs-lookup"><span data-stu-id="a8c72-p101">For most organizations, the volume and complexity of their data is increasing daily—email, documents, instant messages, and more. Effectively managing or governing this information is important because you need to:</span></span>
  
- <span data-ttu-id="a8c72-107">**最小限の期間コンテンツを保持することを要求する業界の規制や内部ポリシーを積極的に遵守する**: たとえば、米国企業改革法により、特定の種類のコンテンツを 7 年間保持することが求められる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a8c72-107">**Comply proactively with industry regulations and internal policies** that require you to retain content for a minimum period of time—for example, the Sarbanes-Oxley Act might require you to retain certain types of content for seven years.</span></span> 
    
- <span data-ttu-id="a8c72-108">**訴訟やセキュリティ違反が発生した場合にリスクを軽減する**: このために、保持する必要がなくなった古いコンテンツは完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="a8c72-108">**Reduce your risk in the event of litigation or a security breach** by permanently deleting old content that you're no longer required to keep.</span></span> 
    
- <span data-ttu-id="a8c72-109">**組織内での効率的な知識の共有と迅速な対応に役立てる**: このために、ユーザーは現時点で関連性のあるコンテンツのみを対象に作業するようにします。</span><span class="sxs-lookup"><span data-stu-id="a8c72-109">**Help your organization to share knowledge effectively and be more agile** by ensuring that your users work only with content that's current and relevant to them.</span></span> 
    
<span data-ttu-id="a8c72-p102">アイテム保持ポリシーは、これらすべての目標の達成に役立ちます。一般に、コンテンツの管理に求められる操作は次の 2 つです。</span><span class="sxs-lookup"><span data-stu-id="a8c72-p102">A retention policy can help you achieve all of these goals. Managing content commonly requires two actions:</span></span>
  
- <span data-ttu-id="a8c72-112">**コンテンツの保持**: 保持期間が満了するまではコンテンツの完全な削除ができないようにします。</span><span class="sxs-lookup"><span data-stu-id="a8c72-112">**Retaining** content so that it can't be permanently deleted before the end of the retention period.</span></span> 
    
- <span data-ttu-id="a8c72-113">**コンテンツの削除**: 保持期間の満了時点でコンテンツを完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="a8c72-113">**Deleting** content permanently at the end of the retention period.</span></span> 
    
<span data-ttu-id="a8c72-114">アイテム保持ポリシーにより、次のことが可能になります。</span><span class="sxs-lookup"><span data-stu-id="a8c72-114">With a retention policy, you can:</span></span>
  
- <span data-ttu-id="a8c72-115">コンテンツを保持するか、コンテンツを削除するか、またはその両方を行う (コンテンツを保持した後に削除する) かを事前に決定する。</span><span class="sxs-lookup"><span data-stu-id="a8c72-115">Decide proactively whether to retain content, delete content, or both—retain and then delete the content.</span></span>
    
- <span data-ttu-id="a8c72-116">組織全体または特定の場所またはユーザーに単一のポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="a8c72-116">Apply a single policy to the entire organization or specific locations or users.</span></span>
    
- <span data-ttu-id="a8c72-117">キーワードまたは[種類の機密情報](what-the-sensitive-information-types-look-for.md)を含むコンテンツなど、すべてのコンテンツまたは特定の条件を満たすコンテンツにポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="a8c72-117">Apply a policy to all content or to content when it meets specific conditions, such as content containing keywords or [types of sensitive information](what-the-sensitive-information-types-look-for.md).</span></span>
    
<span data-ttu-id="a8c72-p103">コンテンツがアイテム保持ポリシーの対象になったときに、ユーザーは何も変更されていないかのようにコンテンツの編集と操作を続行できます。コンテンツは元の場所に保持されます。ただし、アイテム保持ポリシーの対象となるコンテンツを他のユーザーが編集または削除した場合、元のコンテンツのコピーは安全な場所に保存され、そのコンテンツのアイテム保持ポリシーが有効である間は保持されます。詳細については、このページの「[アイテム保持ポリシーは所定の場所にあるコンテンツに対してどのように作用するか](#how-a-retention-policy-works-with-content-in-place)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a8c72-p103">When content is subject to a retention policy, people can continue to edit and work with the content as if nothing's changed. The content is retained in place, in its original location. But if someone edits or deletes content that's subject to the retention policy, a copy of the original content is saved to a secure location where it's retained while the retention policy for that content is in effect. For more information, see the [How a retention policy works with content in place](#how-a-retention-policy-works-with-content-in-place) section on this page</span></span>
  
<span data-ttu-id="a8c72-122">さらに、一部の組織は、米国証券取引委員会 (SEC) 規則 17a-4 などの規制に準拠する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8c72-122">Additionally, some organizations have to comply with regulations such as Securities and Exchange Commission (SEC) Rule 17a-4.</span></span> <span data-ttu-id="a8c72-123">この規制では、アイテム保持ポリシーを有効にした後、無効にしたり制限を緩和したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a8c72-123">This regulation requires that after a retention policy is turned on, it cannot be turned off or made less restrictive.</span></span> <span data-ttu-id="a8c72-124">この要件を満たすために、[**保持ロック**] を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a8c72-124">To meet this requirement, you can use **Preservation Lock**.</span></span> <span data-ttu-id="a8c72-125">アイテム保持ポリシーがロックされた後、管理者を含め誰もアイテム保持ポリシーをオフにしたり、制限を緩和したりすることはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="a8c72-125">After a retention policy's been locked, no one (including an administrator) can turn off the retention policy or make it less restrictive.</span></span> <span data-ttu-id="a8c72-126">詳細については、このページの「[[保持ロック] を使用して規制要件に準拠する](#use-preservation-lock-to-comply-with-regulatory-requirements)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8c72-126">For more information, see the [Use Preservation Lock to comply with regulatory requirements](#use-preservation-lock-to-comply-with-regulatory-requirements) section on this page.</span></span>

## <a name="how-a-retention-policy-works-with-content-in-place"></a><span data-ttu-id="a8c72-127">アイテム保持ポリシーは所定の場所にあるコンテンツに対してどのように作用するか</span><span class="sxs-lookup"><span data-stu-id="a8c72-127">How a retention policy works with content in place</span></span>

<span data-ttu-id="a8c72-128">サイトやメールボックスなどの場所をアイテム保持ポリシーに含めると、コンテンツは元の場所に引き続き保持されます。</span><span class="sxs-lookup"><span data-stu-id="a8c72-128">When you include a location such as a site or mailbox in a retention policy, the content remains in its original location.</span></span> <span data-ttu-id="a8c72-129">このため、ユーザーは何事もなかったかのように、ドキュメントやメールで作業を続けることができます。</span><span class="sxs-lookup"><span data-stu-id="a8c72-129">People can continue to work with their documents or mail as if nothing's changed.</span></span> <span data-ttu-id="a8c72-130">ただし、アイテム保持ポリシーを含むコンテンツを編集したり削除したりした場合、ポリシーを適用したときの状態でコンテンツのコピーが保持されます。</span><span class="sxs-lookup"><span data-stu-id="a8c72-130">But if they edit or delete content that's included in the retention policy, a copy of the content is retained as it existed when you applied the policy.</span></span>
  
- <span data-ttu-id="a8c72-131">SharePoint および OneDrive サイトの場合: コピーは、**アイテム保管**ライブラリに保持されます。</span><span class="sxs-lookup"><span data-stu-id="a8c72-131">For SharePoint and OneDrive sites: The copy is retained in the **Preservation Hold** library.</span></span> <span data-ttu-id="a8c72-132">アイテム保管ライブラリは、サイトのストレージ クォータを消費することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a8c72-132">Be aware that the Preservation Hold library consumes storage quota for the site.</span></span>

- <span data-ttu-id="a8c72-133">メールおよびパブリック フォルダーの場合: コピーは**回復可能なアイテム** フォルダーに保持されます。</span><span class="sxs-lookup"><span data-stu-id="a8c72-133">For email and public folders: The copy is retained in the **Recoverable Items** folder.</span></span> 

- <span data-ttu-id="a8c72-134">Teams コンテンツの場合: コピーは Exchange の**回復可能なアイテム** フォルダーに保持されます。</span><span class="sxs-lookup"><span data-stu-id="a8c72-134">For Teams content: The copy is retained in the Exchange **Recoverable Items** folder.</span></span>

- <span data-ttu-id="a8c72-135">Microsoft 365 グループ ([以前の Office 365 グループ](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) の場合:</span><span class="sxs-lookup"><span data-stu-id="a8c72-135">For Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)):</span></span> 
    - <span data-ttu-id="a8c72-136">グループ メールボックスは、Exchange の**回復可能なアイテム** フォルダーに保持されます。</span><span class="sxs-lookup"><span data-stu-id="a8c72-136">The group mailbox is retained in the Exchange **Recoverable Items** folder.</span></span>
    - <span data-ttu-id="a8c72-137">サイトのコンテンツはすべて、**アイテム保管**ライブラリに保持されます。</span><span class="sxs-lookup"><span data-stu-id="a8c72-137">Any site content is retained in the **Preservation Hold** library.</span></span>

> [!NOTE]
> <span data-ttu-id="a8c72-138">アイテム保管ライブラリは、サイトのストレージ クォータから除外されていないストレージを消費します。</span><span class="sxs-lookup"><span data-stu-id="a8c72-138">The Preservation Hold library consumes storage that isn't exempt from a site's storage quota.</span></span> <span data-ttu-id="a8c72-139">SharePoint および Microsoft 365 グループのアイテム保持ポリシーを使用する場合は、ストレージを増やす必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="a8c72-139">You might need to increase your storage when you use retention policies for SharePoint and Microsoft 365 groups.</span></span>
> 
<span data-ttu-id="a8c72-140">これらの安全な場所や保持されたコンテンツは、ほとんどのユーザーに表示されることはありません。</span><span class="sxs-lookup"><span data-stu-id="a8c72-140">These secure locations and the retained content are not visible to most people.</span></span> <span data-ttu-id="a8c72-141">アイテム保持ポリシーがあれば、ユーザーはユーザーのコンテンツがそのポリシーの対象であるということを知る必要さえありません。</span><span class="sxs-lookup"><span data-stu-id="a8c72-141">With a retention policy, people do not even need to know that their content is subject to the policy.</span></span>

<span data-ttu-id="a8c72-142">アイテム保持ポリシーがさまざまなワークロードでどのように機能するかの詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8c72-142">For more detailed information about how retention policies work with different workloads, see the following articles:</span></span>

- [<span data-ttu-id="a8c72-143">SharePoint と OneDrive のアイテム保持ポリシーの詳細</span><span class="sxs-lookup"><span data-stu-id="a8c72-143">Learn about retention policies for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="a8c72-144">Microsoft Teams のアイテム保持ポリシーの詳細</span><span class="sxs-lookup"><span data-stu-id="a8c72-144">Learn about retention policies for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="a8c72-145">Exchange のアイテム保持ポリシーの詳細</span><span class="sxs-lookup"><span data-stu-id="a8c72-145">Learn about retention policies for Exchange</span></span>](retention-policies-exchange.md)

## <a name="the-principles-of-retention-or-what-takes-precedence"></a><span data-ttu-id="a8c72-146">保持の原則、すなわち優先順位について</span><span class="sxs-lookup"><span data-stu-id="a8c72-146">The principles of retention, or what takes precedence?</span></span>

<span data-ttu-id="a8c72-147">コンテンツにいくつかのアイテム保持ポリシーが適用されると、各ポリシーでアクション (保持、削除、または保持してから削除) や保持期間が異なることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="a8c72-147">It's possible or even likely that content might have several retention policies applied to it, each with a different action (retain, delete, or retain and then delete) and retention period.</span></span> <span data-ttu-id="a8c72-148">優先順位</span><span class="sxs-lookup"><span data-stu-id="a8c72-148">What takes precedence?</span></span> <span data-ttu-id="a8c72-149">最上位のレベルでは、1 つのアイテム保持ポリシーで保持されているコンテンツが、別のアイテム保持ポリシーで完全に削除されることはないので、ご安心ください。</span><span class="sxs-lookup"><span data-stu-id="a8c72-149">At the highest level, rest assured that content being retained by one retention policy can't be permanently deleted by another retention policy.</span></span>
  
![保持の原則の図](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
<span data-ttu-id="a8c72-151">さまざまなアイテム保持ポリシーが、どのようにコンテンツに適用されるかを理解するために、次に示す保持の原則を覚えておいてください。</span><span class="sxs-lookup"><span data-stu-id="a8c72-151">To understand how different retention policies are applied to content, keep these principles of retention in mind:</span></span>
  
1. <span data-ttu-id="a8c72-152">**削除よりも保持が優先されます。**</span><span class="sxs-lookup"><span data-stu-id="a8c72-152">**Retention wins over deletion.**</span></span> <span data-ttu-id="a8c72-153">3 年後に Exchange メールを削除するように構成されているアイテム保持ポリシーがあり、加えて 5 年間 Exchange メールを保持してから削除するように構成されている別のアイテム保持ポリシーもあるとします。</span><span class="sxs-lookup"><span data-stu-id="a8c72-153">Suppose that one retention policy is configured to delete Exchange email after three years, but another retention policy is configured to retain Exchange email for five years and then delete it.</span></span> <span data-ttu-id="a8c72-154">作成後 3 年に達するコンテンツはすべて削除され、ユーザーのビューから非表示になりますが、コンテンツが完全に削除される 5 年に達するまで、[回復可能なアイテム] フォルダーに保持されます。</span><span class="sxs-lookup"><span data-stu-id="a8c72-154">Any content that reaches three years old will be deleted and hidden from the users' view, but still retained in the Recoverable Items folder until the content reaches five years old, when it is permanently deleted.</span></span> 
    
2. <span data-ttu-id="a8c72-155">**最長の保持期間が優先されます。**</span><span class="sxs-lookup"><span data-stu-id="a8c72-155">**The longest retention period wins.**</span></span> <span data-ttu-id="a8c72-156">コンテンツがコンテンツを保持する複数のアイテム保持ポリシーの対象である場合、最長の保持期間が終了するまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="a8c72-156">If content is subject to multiple retention policies that retain content, it will be retained until the end of the longest retention period.</span></span> 
    
3. <span data-ttu-id="a8c72-157">**明示的に含める方が、暗黙的に含めるよりも優先されます。**</span><span class="sxs-lookup"><span data-stu-id="a8c72-157">**Explicit inclusion wins over implicit inclusion.**</span></span> <span data-ttu-id="a8c72-158">これは、次のことを意味します。</span><span class="sxs-lookup"><span data-stu-id="a8c72-158">This means:</span></span> 
    
    1. <span data-ttu-id="a8c72-159">Exchange メールや OneDrive ドキュメントなど、ユーザーが保持設定の保持ラベルを手動でアイテムに割り当てた場合、サイトまたはメールボックス レベルで割り当てたアイテム保持ポリシーや、ドキュメント ライブラリで割り当てた既定の保持ラベルよりも、手動で割り当てたラベルが優先されます。</span><span class="sxs-lookup"><span data-stu-id="a8c72-159">If a retention label with retention settings is manually assigned by a user to an item, such as an Exchange email or OneDrive document, that retention label takes precedence over both a retention policy assigned at the site or mailbox level and a default retention label assigned by the document library.</span></span> <span data-ttu-id="a8c72-160">たとえば、明示的な保持ラベルでは 10 年間コンテンツを保持するように構成され、サイトに割り当てたアイテム保持ポリシーでは 5 年間のみコンテンツを保持するように構成された場合、明示的な保持ラベルが優先されます。</span><span class="sxs-lookup"><span data-stu-id="a8c72-160">For example, if the explicit retention label is configured to retain content for 10 years, but the retention policy assigned to the site is configured to retain content for only five years, the retention label takes precedence.</span></span> <span data-ttu-id="a8c72-161">自動適用の保持ラベルは、Microsoft 365 によって自動的に適用されるため、明示的ではなく、暗黙的とされます。</span><span class="sxs-lookup"><span data-stu-id="a8c72-161">Auto-applied retention labels are considered implicit rather than explicit, because they're applied automatically by Microsoft 365.</span></span>
    
    2. <span data-ttu-id="a8c72-162">アイテム保持ポリシーに特定のユーザーのメールボックスまたは OneDrive のアカウントなどの特定の場所が含まれている場合、そのアイテム保持ポリシーは、すべてのユーザーのメールボックスまたは OneDrive のアカウントに適用されるが、そのユーザーのメールボックスを特に含まない別の保持ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="a8c72-162">If a retention policy includes a specific location, such as a specific user's mailbox or OneDrive account, that retention policy takes precedence over another retention policy that applies to all users' mailboxes or OneDrive accounts but doesn't specifically include that user's mailbox.</span></span>
    
4. <span data-ttu-id="a8c72-163">**最短の削除期間が優先されます。**</span><span class="sxs-lookup"><span data-stu-id="a8c72-163">**The shortest deletion period wins.**</span></span> <span data-ttu-id="a8c72-164">同様に、コンテンツに複数のアイテム保持ポリシーが適用され、保持期間なしでコンテンツが削除される場合、そのコンテンツは最短保持期間の終了時に削除されます。</span><span class="sxs-lookup"><span data-stu-id="a8c72-164">Similarly, if content is subject to multiple retention policies that delete content without a retention period, that content will be deleted at the end of the shortest retention period.</span></span> 
    
<span data-ttu-id="a8c72-165">保持の原則は上位から下位のタイブレーク フローとして機能することを理解します。すべてのアイテム保持ポリシーまたは保持ラベルによって適用された複数のルールがあるレベルで同じ場合、フローは次の下位レベルに移動し、ルールが適用される優先順位を決定します。</span><span class="sxs-lookup"><span data-stu-id="a8c72-165">Understand that the principles of retention work as a tie-breaking flow from top to bottom: If the rules applied by all retention policies or retention labels are the same at one level, the flow moves down to the next level to determine precedence for which rule is applied.</span></span>
  
<span data-ttu-id="a8c72-166">最後に、アイテム保持ポリシーや保持ラベルは、電子情報開示のために保持しているコンテンツを完全に削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="a8c72-166">Finally, a retention policy or retention label cannot permanently delete any content that's on hold for eDiscovery.</span></span> <span data-ttu-id="a8c72-167">保持対象からリリースされると、コンテンツは再び上記で説明したクリーンアップ処理の対象になります。</span><span class="sxs-lookup"><span data-stu-id="a8c72-167">When the hold is released, the content again becomes eligible for the cleanup process described above.</span></span>

## <a name="use-preservation-lock-to-comply-with-regulatory-requirements"></a><span data-ttu-id="a8c72-168">[保持ロック] を使用して規制要件に準拠する</span><span class="sxs-lookup"><span data-stu-id="a8c72-168">Use Preservation Lock to comply with regulatory requirements</span></span>

<span data-ttu-id="a8c72-169">一部の組織は、米国証券取引委員会 (SEC) 規則 17a-4 など、規制機関によって定義された規則に準拠する必要があります。その場合、アイテム保持ポリシーをオンにした後、それをオフにしたり、制限を緩和したりすることはできないという要求があります。</span><span class="sxs-lookup"><span data-stu-id="a8c72-169">Some organizations might need to comply with rules defined by regulatory bodies such as the Securities and Exchange Commission (SEC) Rule 17a-4, which requires that after a retention policy is turned on, it cannot be turned off or made less restrictive.</span></span> 

<span data-ttu-id="a8c72-170">保持ロックは、アイテム保持ポリシーをロックし、誰も (管理者を含む) がポリシーをオフにしたり制限を緩和したりできないようにするため、組織がこのような規制要件を満たすことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="a8c72-170">Preservation Lock ensures your organization can meet such regulatory requirements because it locks a retention policy so that no one—including the administrator—can turn off the policy or make it less restrictive.</span></span>
  
<span data-ttu-id="a8c72-171">保持ポリシーがロックされている場合:</span><span class="sxs-lookup"><span data-stu-id="a8c72-171">When a retention policy is locked:</span></span>

- <span data-ttu-id="a8c72-172">誰もそれをオフにすることはできません</span><span class="sxs-lookup"><span data-stu-id="a8c72-172">No one can it turn off</span></span>
- <span data-ttu-id="a8c72-173">場所は追加できますが、削除できません</span><span class="sxs-lookup"><span data-stu-id="a8c72-173">Locations can be added but not removed</span></span> 
- <span data-ttu-id="a8c72-174">ポリシーの対象となるコンテンツは、保持期間中は変更または削除できません</span><span class="sxs-lookup"><span data-stu-id="a8c72-174">Content subject to the policy can't be modified or deleted during the retention period</span></span>
- <span data-ttu-id="a8c72-175">保持期間を延長することはできますが、短縮することはできません</span><span class="sxs-lookup"><span data-stu-id="a8c72-175">You can extend a retention period but not decrease it</span></span>

<span data-ttu-id="a8c72-176">要約すると、ロックされたアイテム保持ポリシーを増やしたり延長したりすることは可能ですが、減らしたり、オフにしたりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a8c72-176">In summary, a locked retention policy can be increased or extended, but it can't be reduced or turned off.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a8c72-177">アイテム保持ポリシーをロックする前に、影響を理解し、組織がコンプライアンス要件を満たす必要があるかどうかを確認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="a8c72-177">Before you lock a retention policy, it's critical that you understand the impact and confirm whether it's required for your organization to meet compliance requirements.</span></span>

## <a name="releasing-a-retention-policy"></a><span data-ttu-id="a8c72-178">アイテム保持ポリシーを解除する</span><span class="sxs-lookup"><span data-stu-id="a8c72-178">Releasing a retention policy</span></span>

<span data-ttu-id="a8c72-179">アイテム保持ポリシーに保持ロックがない場合、アイテム保持ポリシーをいつでもオフにしたり削除したりできます。</span><span class="sxs-lookup"><span data-stu-id="a8c72-179">Providing your retention policy doesn't have a Preservation Lock, you can turn off or delete a retention policy at any time.</span></span> 

<span data-ttu-id="a8c72-180">この操作を行うと、[アイテム保管ライブラリ] で保持されている SharePoint や OneDrive のコンテンツは、すぐには完全に削除されません。</span><span class="sxs-lookup"><span data-stu-id="a8c72-180">When you do so, any SharePoint or OneDrive content that's being retained in the Preservation Hold library is not immediately and permanently deleted.</span></span> <span data-ttu-id="a8c72-181">代わりに、不注意によるデータの損失を防ぐために、30 日間の猶予期間があります。そのポリシーのコンテンツの有効期限は、[アイテム保管ライブラリ] には表示されず、必要に応じてコンテンツを復元できます。</span><span class="sxs-lookup"><span data-stu-id="a8c72-181">Instead, to help prevent inadvertent data loss, there is a 30-day grace period, during which content expiration for that policy does not happen in the Preservation Hold library, so that you can restore any content from there, if needed.</span></span> <span data-ttu-id="a8c72-182">また、猶予期間中はこのコンテンツを手動で削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="a8c72-182">Additionally, you can't manually delete this content during the grace period.</span></span>

<span data-ttu-id="a8c72-183">猶予期間中にアイテム保持ポリシーをもう一度有効にすることができます。そのポリシーのコンテンツは削除されません。</span><span class="sxs-lookup"><span data-stu-id="a8c72-183">You can turn on the retention policy again during the grace period, and no content will be deleted for that policy.</span></span>

<span data-ttu-id="a8c72-184">この SharePoint と OneDrive の 30 日の猶予期間は、Exchange の 30 日の保留期間に対応しています。</span><span class="sxs-lookup"><span data-stu-id="a8c72-184">This 30-day grace period in SharePoint and OneDrive corresponds to the 30-day delay hold in Exchange.</span></span> <span data-ttu-id="a8c72-185">詳しくは、[メールボックスの管理についての詳細](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold) をご覧ください。。</span><span class="sxs-lookup"><span data-stu-id="a8c72-185">For more information, see [Managing mailboxes on delay hold](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).</span></span>

## <a name="use-a-retention-policy-instead-of-older-features"></a><span data-ttu-id="a8c72-186">古いの機能の代わりにアイテム保持ポリシーを使用する</span><span class="sxs-lookup"><span data-stu-id="a8c72-186">Use a retention policy instead of older features</span></span>

<span data-ttu-id="a8c72-187">1 つのアイテム保持ポリシーは、組織全体や、Exchange Online、SharePoint Online、OneDrive、Microsoft 365 グループなどの Microsoft 365 全体の場所に簡単に適用できます。</span><span class="sxs-lookup"><span data-stu-id="a8c72-187">A single retention policy can easily apply to an entire organization and locations across Microsoft 365, including Exchange Online, SharePoint Online, OneDrive, and Microsoft 365 groups.</span></span> <span data-ttu-id="a8c72-188">Microsoft 365 内の任意の場所でコンテンツを保持または削除する必要がある場合は、アイテム保持ポリシーを使用し、オプションでこれに[保持ラベル](labels.md)を追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a8c72-188">If you need to retain or delete content anywhere in Microsoft 365, we recommend that you use a retention policy and optionally supplement this with [retention labels](labels.md).</span></span>
  
<span data-ttu-id="a8c72-189">以前に他の構成を使用して Microsoft 365 のコンテンツを保持または削除したことがある場合、それらはアイテム保持ポリシーと保持ラベルと並行して機能し続けます。</span><span class="sxs-lookup"><span data-stu-id="a8c72-189">If you have previously used other configurations to retain or delete content in Microsoft 365, they will continue to work side by side with retention policies and retention labels.</span></span> <span data-ttu-id="a8c72-190">ただし、今後はアイテム保持ポリシーと保持ラベルを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a8c72-190">However, we recommend that going forward, you use retention policies and retention labels instead.</span></span> <span data-ttu-id="a8c72-191">それらは、Microsoft 365 全体でコンテンツの保持と削除の両方を集中管理する単一のメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="a8c72-191">They provide you with a single mechanism to centrally manage both retention and deletion of content across Microsoft 365.</span></span>

<span data-ttu-id="a8c72-192">使用した可能性がある古い機能:</span><span class="sxs-lookup"><span data-stu-id="a8c72-192">The older features that you might have used:</span></span>
  
<span data-ttu-id="a8c72-193">**Exchange Online の古い機能:**</span><span class="sxs-lookup"><span data-stu-id="a8c72-193">**Older features from Exchange Online:**</span></span>

- <span data-ttu-id="a8c72-194">[Office 365 のセキュリティ センター/コンプライアンス センターでの電子情報開示のケースの管理](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery) (電子情報開示の保留リスト)</span><span class="sxs-lookup"><span data-stu-id="a8c72-194">[Manage eDiscovery cases in the Office 365 Security &amp; Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery) (eDiscovery hold)</span></span> 
    
- <span data-ttu-id="a8c72-195">[インプレース ホールドと訴訟ホールド](https://go.microsoft.com/fwlink/?linkid=846124) (電子情報開示の保留リスト)</span><span class="sxs-lookup"><span data-stu-id="a8c72-195">[In-Place Hold and Litigation Hold](https://go.microsoft.com/fwlink/?linkid=846124) (eDiscovery hold)</span></span> 

- [<span data-ttu-id="a8c72-196">Exchange Online メールボックスに適用されている保留の種類を特定する方法</span><span class="sxs-lookup"><span data-stu-id="a8c72-196">How to identify the type of hold placed on an Exchange Online mailbox</span></span>](identify-a-hold-on-an-exchange-online-mailbox.md)
    
- <span data-ttu-id="a8c72-197">[メッセージング レコード管理 (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) とも呼ばれる、[保持タグおよびアイテム保持ポリシー](https://go.microsoft.com/fwlink/?linkid=846125) (削除のみ)</span><span class="sxs-lookup"><span data-stu-id="a8c72-197">[Retention tags and retention policies](https://go.microsoft.com/fwlink/?linkid=846125), also known as [messaging records management (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (deletion only)</span></span>
    
<span data-ttu-id="a8c72-198">**SharePoint と OneDrive の古い機能:**</span><span class="sxs-lookup"><span data-stu-id="a8c72-198">**Older features from SharePoint and OneDrive:**</span></span>

- <span data-ttu-id="a8c72-199">[Office 365 のセキュリティ センター/コンプライアンス センターでの電子情報開示のケースの管理](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery) (電子情報開示の保留リスト)</span><span class="sxs-lookup"><span data-stu-id="a8c72-199">[Manage eDiscovery cases in the Office 365 Security &amp; Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery) (eDiscovery hold)</span></span> 
    
- <span data-ttu-id="a8c72-200">[電子情報開示センターでのコンテンツのケースへの追加とソースの保留リストへの配置](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center) (電子情報開示の保留リスト)</span><span class="sxs-lookup"><span data-stu-id="a8c72-200">[Add content to a case and place sources on hold in the eDiscovery Center](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center) (eDiscovery hold)</span></span> 
    
- <span data-ttu-id="a8c72-201">[ドキュメント削除ポリシーの概要](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff) (削除のみ)</span><span class="sxs-lookup"><span data-stu-id="a8c72-201">[Document deletion policies](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff) (deletion only)</span></span>
    
- <span data-ttu-id="a8c72-202">[インプレース レコード管理の構成](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (保持のみ)</span><span class="sxs-lookup"><span data-stu-id="a8c72-202">[Configuring in place records management](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (retention only)</span></span> 
    
- <span data-ttu-id="a8c72-203">[サイトのクローズと削除のポリシーを使用する](https://support.microsoft.com/ja-JP/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (削除のみ)</span><span class="sxs-lookup"><span data-stu-id="a8c72-203">[Use policies for site closure and deletion](https://support.microsoft.com/ja-JP/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (deletion only)</span></span> 
    
- <span data-ttu-id="a8c72-204">[情報管理ポリシー](intro-to-info-mgmt-policies.md) (削除のみ)</span><span class="sxs-lookup"><span data-stu-id="a8c72-204">[Information management policies](intro-to-info-mgmt-policies.md) (deletion only)</span></span>
     
<span data-ttu-id="a8c72-205">以前に情報ガバナンスを目的として電子情報開示の保留のいずれかを使用したことがある場合は、予防的なコンプライアンスのために、代わりにアイテム保持ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="a8c72-205">If you've previously used any of the eDiscovery holds for the purpose of information governance, for proactive compliance, use a retention policy instead.</span></span> <span data-ttu-id="a8c72-206">電子情報開示は、保留リストのみに使用します。</span><span class="sxs-lookup"><span data-stu-id="a8c72-206">Use eDiscovery for holds only.</span></span>
  
### <a name="retention-policies-and-sharepoint-content-type-policies-or-information-management-policies"></a><span data-ttu-id="a8c72-207">アイテム保持ポリシーと SharePoint コンテンツ タイプ ポリシーまたは情報管理ポリシー</span><span class="sxs-lookup"><span data-stu-id="a8c72-207">Retention policies and SharePoint content type policies or information management policies</span></span>

<span data-ttu-id="a8c72-208">コンテンツ タイプ ポリシーまたは情報管理ポリシーの SharePoint サイトを構成して、リストまたはライブラリのコンテンツを保持している場合は、前者のポリシーは無視され、保持ポリシーが有効になります。</span><span class="sxs-lookup"><span data-stu-id="a8c72-208">If you have configured SharePoint sites for content type policies or information management policies to retain content for a list or library, those policies are ignored while a retention policy is in effect.</span></span> 
  
### <a name="preservation-policies-are-converted-to-retention-policies"></a><span data-ttu-id="a8c72-209">保持ポリシーはアイテム保持ポリシーに変換される</span><span class="sxs-lookup"><span data-stu-id="a8c72-209">Preservation policies are converted to retention policies</span></span>

<span data-ttu-id="a8c72-210">保持ポリシーを使用してメールボックス、SharePoint または OneDrive サイト、またはパブリック フォルダーにデータを保持している場合: そのポリシーはアイテム保持ポリシーに自動的に変換されます。ポリシーがコンテンツを削除することはありません。</span><span class="sxs-lookup"><span data-stu-id="a8c72-210">If you were using a preservation policy to retain data in mailboxes, SharePoint or OneDrive sites, or public folders: That policy has been automatically converted to a retention policy that uses only the retain action—the policy won't delete content.</span></span> <span data-ttu-id="a8c72-211">構成済みの保持ポリシーと同じ結果を得るために、ユーザーが変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a8c72-211">No changes are needed from you for the same outcome as your configured preservation policy.</span></span>

<span data-ttu-id="a8c72-212">構成された保持ポリシーは、[**ポリシー**] ページ ([Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)内)、または [**保持**] ページ ([**情報ガバナンス**] 下、[セキュリティ &amp;コンプライアンス センター](https://protection.office.com/)内) にあります。</span><span class="sxs-lookup"><span data-stu-id="a8c72-212">You can find any configured preservation policies on the **Policies** page in the [Microsoft 365 compliance center](https://compliance.microsoft.com/), or on the **Retention** page under **Information governance** in the [Security &amp; Compliance Center](https://protection.office.com/).</span></span> <span data-ttu-id="a8c72-213">保持ポリシーを編集して保持期間を変更することはできますが、それ以外の変更 (場所の追加や削除など) はできません。</span><span class="sxs-lookup"><span data-stu-id="a8c72-213">You can edit a preservation policy to change the retention period, but you can't make other changes, such as adding or removing locations.</span></span> 


## <a name="related-information"></a><span data-ttu-id="a8c72-214">関連情報</span><span class="sxs-lookup"><span data-stu-id="a8c72-214">Related information</span></span>

- [<span data-ttu-id="a8c72-215">保持ポリシーを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="a8c72-215">Create and configure retention policies</span></span>](create-retention-policies.md)
- [<span data-ttu-id="a8c72-216">保持ラベルの詳細情報</span><span class="sxs-lookup"><span data-stu-id="a8c72-216">Learn about retention labels</span></span>](labels.md)
- [<span data-ttu-id="a8c72-217">SharePoint Online の制限</span><span class="sxs-lookup"><span data-stu-id="a8c72-217">SharePoint Online Limits</span></span>](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [<span data-ttu-id="a8c72-218">Microsoft Teams の制限事項と仕様</span><span class="sxs-lookup"><span data-stu-id="a8c72-218">Limits and specifications for Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) 
- [<span data-ttu-id="a8c72-219">SEC Rule 17a-4 に準拠する </span><span class="sxs-lookup"><span data-stu-id="a8c72-219">Comply with SEC Rule 17a-4</span></span>](use-exchange-online-to-comply-with-sec-rule-17a-4.md)
