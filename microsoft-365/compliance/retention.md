---
title: コンテンツを自動的に保持または削除するアイテム保持ポリシーと保持ラベルの詳細
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
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 必要なコンテンツを保持し不要なコンテンツを削除するのに役立つ、アイテム保持ポリシーと保持ラベルについて説明します。
ms.openlocfilehash: e2833d966fb8a1fcc15cbeb02b781d9c0325b9c1
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519378"
---
# <a name="learn-about-retention-policies-and-retention-labels"></a><span data-ttu-id="344c1-103">アイテム保持ポリシーと保持ラベルの詳細</span><span class="sxs-lookup"><span data-stu-id="344c1-103">Learn about retention policies and retention labels</span></span>

><span data-ttu-id="344c1-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="344c1-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="344c1-p101">ほとんどの組織では、電子メール、ドキュメント、インスタント メッセージなどのデータの量と複雑さが日々増しています。次の必要性から、これらの情報を効果的に管理することが重要です。</span><span class="sxs-lookup"><span data-stu-id="344c1-p101">For most organizations, the volume and complexity of their data is increasing daily—email, documents, instant messages, and more. Effectively managing or governing this information is important because you need to:</span></span>
  
- <span data-ttu-id="344c1-107">**最小限の期間コンテンツを保持することを要求する業界の規制や内部ポリシーを積極的に遵守する**: たとえば、米国企業改革法により、特定の種類のコンテンツを 7 年間保持することが求められる場合があります。</span><span class="sxs-lookup"><span data-stu-id="344c1-107">**Comply proactively with industry regulations and internal policies** that require you to retain content for a minimum period of time—for example, the Sarbanes-Oxley Act might require you to retain certain types of content for seven years.</span></span> 

- <span data-ttu-id="344c1-108">**訴訟やセキュリティ違反が発生した場合にリスクを軽減する**: このために、保持する必要がなくなった古いコンテンツは完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="344c1-108">**Reduce your risk in the event of litigation or a security breach** by permanently deleting old content that you're no longer required to keep.</span></span> 
    
- <span data-ttu-id="344c1-109">**組織内での効率的な知識の共有と迅速な対応に役立てる**: このために、ユーザーは現時点で関連性のあるコンテンツのみを対象に作業するようにします。</span><span class="sxs-lookup"><span data-stu-id="344c1-109">**Help your organization to share knowledge effectively and be more agile** by ensuring that your users work only with content that's current and relevant to them.</span></span> 
    
<span data-ttu-id="344c1-p102">構成する保持設定は、これらすべての目標を達成するのに役立ちます。一般に、コンテンツの管理に求められる操作は次の 2 つです。</span><span class="sxs-lookup"><span data-stu-id="344c1-p102">Retention settings that you configure can help you achieve all these goals. Managing content commonly requires two actions:</span></span>
  
- <span data-ttu-id="344c1-112">**コンテンツの保持**: 保持期間が満了するまではコンテンツの完全な削除ができないようにします。</span><span class="sxs-lookup"><span data-stu-id="344c1-112">**Retaining** content so that it can't be permanently deleted before the end of the retention period.</span></span> 
    
- <span data-ttu-id="344c1-113">**コンテンツの削除**: 保持期間の満了時点でコンテンツを完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="344c1-113">**Deleting** content permanently at the end of the retention period.</span></span> 
    

<span data-ttu-id="344c1-114">これら 2 つの保持アクションを使用して、次の結果が得られるように保持設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="344c1-114">With these two retention actions, you can configure retention settings for the following outcomes:</span></span>

- <span data-ttu-id="344c1-115">保持のみ: コンテンツを無期限または指定した期間保持します。</span><span class="sxs-lookup"><span data-stu-id="344c1-115">Retain-only: Retain content forever or for a specified period of time.</span></span>
- <span data-ttu-id="344c1-116">削除のみ: 指定した期間の後にコンテンツを削除します。</span><span class="sxs-lookup"><span data-stu-id="344c1-116">Delete-only: Delete content after a specified period of time.</span></span>
- <span data-ttu-id="344c1-117">保持してから削除: 指定した期間、コンテンツを保持してから削除します。</span><span class="sxs-lookup"><span data-stu-id="344c1-117">Retain and then delete: Retain content for a specified period of time and then delete it.</span></span>

<span data-ttu-id="344c1-p103">これらの保持設定は所定の場所にあるコンテンツに作用し、コンプライアンス上の理由でコンテンツを保持する必要がある場合でも、追加のストレージを作成して構成するための追加のオーバーヘッドを節約できます。また、このデータをコピーして同期するために、カスタマイズしたプロセスを実装する必要もありません。</span><span class="sxs-lookup"><span data-stu-id="344c1-p103">These retention settings work with content in place that saves you the additional overheads of creating and configuring additional storage when you need to retain content for compliance reasons. In addition, you don't need to implement customized processes to copy and synchronize this data.</span></span>

## <a name="how-retention-settings-work-with-content-in-place"></a><span data-ttu-id="344c1-120">保持設定が所定の場所にあるコンテンツに作用するしくみ</span><span class="sxs-lookup"><span data-stu-id="344c1-120">How retention settings work with content in place</span></span>

<span data-ttu-id="344c1-p104">コンテンツに保持設定が割り当てられるとき、そのコンテンツは元の場所にそのまま残ります。このため、ユーザーは何事もなかったかのように、ドキュメントやメールで作業を続けることができます。ただし、アイテム保持ポリシーに含まれているコンテンツをユーザーが編集または削除すると、そのコンテンツのコピーが自動的に保持されます。</span><span class="sxs-lookup"><span data-stu-id="344c1-p104">When content has retention settings assigned to it, that content remains in its original location. People can continue to work with their documents or mail as if nothing's changed. But if they edit or delete content that's included in the retention policy, a copy of the content is automatically retained.</span></span>
  
- <span data-ttu-id="344c1-124">SharePoint および OneDrive サイトの場合: コピーは、**アイテム保管** ライブラリに保持されます。</span><span class="sxs-lookup"><span data-stu-id="344c1-124">For SharePoint and OneDrive sites: The copy is retained in the **Preservation Hold** library.</span></span>

- <span data-ttu-id="344c1-125">Exchange メールボックスの場合: コピーは、**[回復可能なアイテム]** フォルダーに保持されます。</span><span class="sxs-lookup"><span data-stu-id="344c1-125">For Exchange mailboxes: The copy is retained in the **Recoverable Items** folder.</span></span> 

- <span data-ttu-id="344c1-126">Teams と Yammer のメッセージの場合: **SubstrateHolds** という名前の隠しフォルダーに Exchange の **[回復可能なアイテム]** フォルダー内のサブフォルダーとして保持されます。</span><span class="sxs-lookup"><span data-stu-id="344c1-126">For Teams and Yammer messages: The copy is retained in a hidden folder named **SubstrateHolds** as a subfolder in the Exchange **Recoverable Items** folder.</span></span>

> [!NOTE]
> <span data-ttu-id="344c1-p105">アイテム保管ライブラリは、サイトのストレージ クォータから除外されていないストレージを消費します。SharePoint グループや Microsoft 365 グループに対して保持設定を使用する場合は、ストレージを増やすことが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="344c1-p105">The Preservation Hold library consumes storage that isn't exempt from a site's storage quota. You might need to increase your storage when you use retention settings for SharePoint and Microsoft 365 groups.</span></span>
> 
<span data-ttu-id="344c1-p106">これらの安全な場所や保持されたコンテンツは、ほとんどのユーザーに表示されることはありません。ほとんどの場合、ユーザーは自分のコンテンツが保持設定の対象であることを知る必要さえありません。</span><span class="sxs-lookup"><span data-stu-id="344c1-p106">These secure locations and the retained content are not visible to most people. In most cases, people do not even need to know that their content is subject to retention settings.</span></span>

<span data-ttu-id="344c1-131">保持設定がさまざまなワークロードに対してどのように機能するかの詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="344c1-131">For more detailed information about how retention settings work for different workloads, see the following articles:</span></span>

- [<span data-ttu-id="344c1-132">SharePoint と OneDrive の保持の詳細</span><span class="sxs-lookup"><span data-stu-id="344c1-132">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="344c1-133">Microsoft Teams の保持の詳細</span><span class="sxs-lookup"><span data-stu-id="344c1-133">Learn about retention for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="344c1-134">Yammerの保持の詳細</span><span class="sxs-lookup"><span data-stu-id="344c1-134">Learn about retention for Yammer</span></span>](retention-policies-yammer.md)
- [<span data-ttu-id="344c1-135">Exchange の保持の詳細</span><span class="sxs-lookup"><span data-stu-id="344c1-135">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="retention-policies-and-retention-labels"></a><span data-ttu-id="344c1-136">アイテム保持ポリシーと保持ラベル</span><span class="sxs-lookup"><span data-stu-id="344c1-136">Retention policies and retention labels</span></span>

<span data-ttu-id="344c1-137">アイテム保持ポリシーと保持ラベルの両方を使用して、保持設定をコンテンツに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="344c1-137">You can use both retention policies and retention labels with label policies to assign your retention settings to content.</span></span> 

<span data-ttu-id="344c1-138">サイト レベルやメールボックス レベルで同一の保持設定を割り当てるには、アイテム保持ポリシーを使用します。一方、アイテム レベル (フォルダー、ドキュメント、メール) で保持設定を割り当てるには、保持ラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="344c1-138">Use a retention policy to assign the same retention settings for content at a site or mailbox level, and use a retention label to assign retention settings at an item level (folder, document, email).</span></span>

<span data-ttu-id="344c1-p107">たとえば、SharePoint サイト内のすべてのドキュメントを 5 年間保持する必要がある場合は、同じ保持ラベルをサイト内のすべてのドキュメントに適用するよりも、アイテム保持ポリシーを使用する方が効率的です。一方、サイト内の一部のドキュメントは 5 年間保持し、一部は 10 年間保持する必要がある場合、アイテム保持ポリシーではこれを行うことができません。アイテム レベルで保持設定を指定する必要がある場合は、保持ラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="344c1-p107">For example, if all documents in a SharePoint site should be retained for 5 years, it's more efficient to do this with a retention policy than apply the same retention label to all documents in that site. However, if some documents in that site should be retained for 5 years and others retained for 10 years, a retention policy wouldn't be able to do this. When you need to specify retention settings at the item level, use retention labels.</span></span> 

<span data-ttu-id="344c1-p108">アイテム保持ポリシーとは異なり、保持ラベルによる保持設定は、コンテンツが Microsoft 365 テナントの別の場所に移動された場合でもコンテンツに適用されたままになります。また、保持ラベルには、アイテム保持ポリシーではサポートされていない次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="344c1-p108">Unlike retention policies, retention settings from retention labels travel with the content if it’s moved to a different location within your Microsoft 365 tenant. In addition, retention labels have the following capabilities that retention policies don't support:</span></span> 
 
- <span data-ttu-id="344c1-144">コンテンツの保持期間や最終更新日以外に、コンテンツにラベルが付けられた時点やイベントに基づいて保持期間を開始するオプション。</span><span class="sxs-lookup"><span data-stu-id="344c1-144">Options to start the retention period from when the content was labeled or based on an event, in addition to the age of the content or when it was last modified.</span></span>

- <span data-ttu-id="344c1-145">[トレーニング可能な分類子](classifier-learn-about.md)を使用して、ラベル付けするコンテンツを識別する。</span><span class="sxs-lookup"><span data-stu-id="344c1-145">Use [trainable classifiers](classifier-learn-about.md) to identify content to label.</span></span>

- <span data-ttu-id="344c1-146">SharePoint ドキュメントに既定のラベルを適用する。</span><span class="sxs-lookup"><span data-stu-id="344c1-146">Apply a default label for SharePoint documents.</span></span>

- <span data-ttu-id="344c1-147">コンテンツを完全に削除する前にコンテンツを確認する[廃棄確認](disposition-reviews.md) のサポート。</span><span class="sxs-lookup"><span data-stu-id="344c1-147">Support [disposition review](disposition-reviews.md) to review the content before it's permanently deleted.</span></span>

- <span data-ttu-id="344c1-148">ラベル設定の一部として、コンテンツを [[レコード]](records-management.md#records) としてマークし、保持期間の終了時にコンテンツが削除されるときに [廃棄の証明](disposition.md#disposition-of-records) を常に取得する。</span><span class="sxs-lookup"><span data-stu-id="344c1-148">Mark the content as a [record](records-management.md#records) as part of the label settings, and always have [proof of disposition](disposition.md#disposition-of-records) when content is deleted at the end of its retention period.</span></span>

### <a name="retention-policies"></a><span data-ttu-id="344c1-149">アイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="344c1-149">Retention policies</span></span>

<span data-ttu-id="344c1-150">アイテム保持ポリシーは、次の場所に適用できます。</span><span class="sxs-lookup"><span data-stu-id="344c1-150">Retention policies can be applied to the following locations:</span></span>
- <span data-ttu-id="344c1-151">Exchange メール</span><span class="sxs-lookup"><span data-stu-id="344c1-151">Exchange email</span></span>
- <span data-ttu-id="344c1-152">SharePoint サイト</span><span class="sxs-lookup"><span data-stu-id="344c1-152">SharePoint site</span></span>
- <span data-ttu-id="344c1-153">OneDrive アカウント</span><span class="sxs-lookup"><span data-stu-id="344c1-153">OneDrive accounts</span></span>
- <span data-ttu-id="344c1-154">Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="344c1-154">Microsoft 365 Groups</span></span>
- <span data-ttu-id="344c1-155">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="344c1-155">Skype for Business</span></span>
- <span data-ttu-id="344c1-156">Exchange パブリック フォルダー</span><span class="sxs-lookup"><span data-stu-id="344c1-156">Exchange public folders</span></span>
- <span data-ttu-id="344c1-157">チームのチャネル メッセージ</span><span class="sxs-lookup"><span data-stu-id="344c1-157">Teams channel messages</span></span>
- <span data-ttu-id="344c1-158">Teams のチャット</span><span class="sxs-lookup"><span data-stu-id="344c1-158">Teams chats</span></span>
- <span data-ttu-id="344c1-159">Yammer コミュニティのメッセージ</span><span class="sxs-lookup"><span data-stu-id="344c1-159">Yammer community messages</span></span>
- <span data-ttu-id="344c1-160">Yammer の個人用メッセージ</span><span class="sxs-lookup"><span data-stu-id="344c1-160">Yammer private messages</span></span>

<span data-ttu-id="344c1-161">複数の場所にも特定の場所やユーザーにも、1 つのポリシーを非常に効率的に適用できます。</span><span class="sxs-lookup"><span data-stu-id="344c1-161">You can very efficiently apply a single policy to multiple locations, or to specific locations or users.</span></span>

<span data-ttu-id="344c1-162">保持期間の開始時に、コンテンツがいつ作成されたか、またはファイルと、コンテンツが最後に変更された SharePoint、OneDrive、Microsoft 365 グループの場所でのみサポートされるかを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="344c1-162">For the start of the retention period, you can choose when the content was created or, supported only for files and the SharePoint, OneDrive, and Microsoft 365 Groups locations, when the content was last modified.</span></span>

<span data-ttu-id="344c1-p109">アイテムは、アイテム保持ポリシーで指定されたコンテナーからアイテム保持設定を継承します。ポリシーがコンテンツを保持するように構成されているときに、それらがそのコンテナーの外部に移動された場合、そのアイテムのコピーがワークロードのセキュリティで保護された場所に保持されます。ただし、保持設定は、コンテンツとともに新しい場所に移動することはありません。必要な場合は、アイテム保持ポリシーの代わりに保持ラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="344c1-p109">Items inherit the retention settings from their container specified in the retention policy. If they are then moved outside that container when the policy is configured to retain content, a copy of that item is retained in the workload's secured location. However, the retention settings don't travel with the content in its new location. If that's required, use retention labels instead of retention policies.</span></span>

### <a name="retention-labels"></a><span data-ttu-id="344c1-167">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="344c1-167">Retention labels</span></span>

<span data-ttu-id="344c1-p110">保持ラベルは、異なる保持設定を必要とするさまざまな種類のコンテンツに対して使用できます。例:</span><span class="sxs-lookup"><span data-stu-id="344c1-p110">Use retention labels for different types of content that require different retention settings. For example:</span></span>
  
- <span data-ttu-id="344c1-170">最低限の期間、保持する必要のある納税申告書。</span><span class="sxs-lookup"><span data-stu-id="344c1-170">Tax forms that need to be retained for a minimum period of time.</span></span> 
    
- <span data-ttu-id="344c1-171">特定の期間が経過した後、完全に削除する必要があるプレス資料。</span><span class="sxs-lookup"><span data-stu-id="344c1-171">Press materials that need to be permanently deleted when they reach a specific age.</span></span> 
    
- <span data-ttu-id="344c1-172">特定の期間保持した後に完全に削除する必要がある競合企業のリサーチ。</span><span class="sxs-lookup"><span data-stu-id="344c1-172">Competitive research that needs to be retained for a specific period and then permanently deleted.</span></span> 
    
- <span data-ttu-id="344c1-173">編集も削除もできないように、レコードとしてマークする必要がある就労ビザ。</span><span class="sxs-lookup"><span data-stu-id="344c1-173">Work visas that must be marked as a record so that they can't be edited or deleted.</span></span> 
    
<span data-ttu-id="344c1-174">いずれの場合も、保持ラベルを使用すると、アイテム レベル (ドキュメントやメール) でガバナンス制御用の保持設定を適用できます。</span><span class="sxs-lookup"><span data-stu-id="344c1-174">In all these cases, retention labels let you apply retention settings for governance control at the item level (document or email).</span></span>
  
<span data-ttu-id="344c1-175">保持ラベルを使用すると、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="344c1-175">With retention labels, you can:</span></span>
  
- <span data-ttu-id="344c1-p111">Outlook、Outlook on the web、OneDrive、SharePoint、Microsoft 365 グループのコンテンツに、**組織内のユーザーが保持ラベルを手動で適用** できるようにします。多くの場合、コンテンツの種類を最も良く理解しているのはそれを扱っているユーザーです。そこでユーザーにコンテンツを分類し、適切なアイテム保持設定を適用してもらいます。</span><span class="sxs-lookup"><span data-stu-id="344c1-p111">**Enable people in your organization to apply a retention label manually** to content in Outlook and Outlook on the web, OneDrive, SharePoint, and Microsoft 365 groups. Users often know best what type of content they're working with, so they can classify it and have the appropriate retention settings applied.</span></span> 
    
- <span data-ttu-id="344c1-178">コンテンツに次のものが含まれている場合など、特定の条件に一致するときには、**保持ラベルをコンテンツに自動的に適用** できます。</span><span class="sxs-lookup"><span data-stu-id="344c1-178">**Apply retention labels to content automatically** if it matches specific conditions, such as when the content contains:</span></span> 
    - <span data-ttu-id="344c1-179">特定の種類の機密情報。</span><span class="sxs-lookup"><span data-stu-id="344c1-179">Specific types of sensitive information.</span></span>
    - <span data-ttu-id="344c1-180">作成したクエリに一致する特定のキーワード。</span><span class="sxs-lookup"><span data-stu-id="344c1-180">Specific keywords that match a query you create.</span></span>
    - <span data-ttu-id="344c1-181">トレーニング可能な分類子のパターン マッチ。</span><span class="sxs-lookup"><span data-stu-id="344c1-181">Pattern matches for a trainable classifier.</span></span>

- <span data-ttu-id="344c1-p112">**コンテンツにラベルが付けられた時点から保持期間を開始する** SharePoint サイトや OneDrive アカウントのドキュメント、および予定表アイテム以外のメール アイテムに対してこの操作を行えます。この構成の保持ラベルを予定表アイテムに適用すると、保持期間はアイテムが送信された時点から開始されます。</span><span class="sxs-lookup"><span data-stu-id="344c1-p112">**Start the retention period from when the content was labeled** for documents in SharePoint sites and OneDrive accounts, and to email items with the exception of calendar items. If you apply a retention label with this configuration to a calendar item, the retention period starts from when it is sent.</span></span>

- <span data-ttu-id="344c1-184">従業員の退職や契約の期限切れなど、**イベントの発生時に保持期間を開始する**。</span><span class="sxs-lookup"><span data-stu-id="344c1-184">**Start the retention period when an event occurs**, such as employees leave the organization, or contracts expire.</span></span>

- <span data-ttu-id="344c1-185">SharePoint の **ドキュメント ライブラリ、フォルダー、またはドキュメント セットに既定の保持ラベルを適用** することにより、この場所に保存するすべてのドキュメントに既定の保持ラベルが継承されるようになります。</span><span class="sxs-lookup"><span data-stu-id="344c1-185">**Apply a default retention label to a document library, folder, or document set** in SharePoint, so that all documents that are stored in that location inherit the default retention label.</span></span>

<span data-ttu-id="344c1-p113">さらに、保持ラベルは、Microsoft 365 アプリとサービス全体でのメールとドキュメントの[レコード管理](records-management.md)をサポートします。保持ラベルを使用して、アイテムをレコードとしてマークできます。この問題が発生し、コンテンツが Microsoft 365 に残っている場合は、このラベルで規制上の理由から必要になる可能性があるコンテンツがさらに制限されます。詳細については、「[許可またはブロックされているアクションの制限を比較する](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="344c1-p113">Additionally, retention labels support [records management](records-management.md) for email and documents across Microsoft 365 apps and services. You can use a retention label to mark items as a record. When this happens and the content remains in Microsoft 365, the label places further restrictions on the content that might be needed for regulatory reasons. For more information, see [Compare restrictions for what actions are allowed or blocked](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

<span data-ttu-id="344c1-190">保持ラベルは、[秘密度ラベル](sensitivity-labels.md)とは異なり、コンテンツが Microsoft 365 以外の場所に移動した場合は保持されません。</span><span class="sxs-lookup"><span data-stu-id="344c1-190">Retention labels, unlike [sensitivity labels](sensitivity-labels.md), do not persist if the content is moved outside Microsoft 365.</span></span>

<span data-ttu-id="344c1-p114">テナントでサポートされる保持ラベルの数に制限はありません。ただし、10,000 がテナントでサポートされるポリシーの最大数であり、これらには、ラベルを適用するポリシー (保持ラベル ポリシーと自動適用アイテム保持ポリシー) とアイテム保持ポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="344c1-p114">There is no limit to the number of retention labels that are supported for a tenant. However, 10,000 is the maximum number of policies that are supported for a tenant and these include the policies that apply the labels (retention label policies and auto-apply retention policies), as well as retention policies.</span></span>

#### <a name="classifying-content-without-applying-any-actions"></a><span data-ttu-id="344c1-193">アクションを適用しないでコンテンツを分類する</span><span class="sxs-lookup"><span data-stu-id="344c1-193">Classifying content without applying any actions</span></span>

<span data-ttu-id="344c1-p115">保持ラベルの主な目的はコンテンツを保持または削除することですが、保持やその他のアクションを有効にしないで保持ラベルを使用することもできます。この場合、テキスト ラベルとしてのみ保持ラベルを使用し、他のアクションは適用しません。</span><span class="sxs-lookup"><span data-stu-id="344c1-p115">Although the main purpose of retention labels is to retain or delete content, you can also use retention labels without turning on any retention or other actions. In this case, you can use a retention label simply as a text label, without enforcing any actions.</span></span>
  
<span data-ttu-id="344c1-196">たとえば、アクションを含まない "後で確認" という名前の保持ラベルを作成して適用し、後からそのコンテンツを見つけるためにそのラベルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="344c1-196">For example, you can create and apply a retention label named "Review later" with no actions, and then use that label to find that content later.</span></span>
  
![分類専用のラベル設定](../media/retention-label-retentionoff.png)

#### <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="344c1-198">DLP ポリシーで保持ラベルを条件として使用する</span><span class="sxs-lookup"><span data-stu-id="344c1-198">Using a retention label as a condition in a DLP policy</span></span>

<span data-ttu-id="344c1-p116">SharePoint のドキュメントのデータ損失防止 (DLP) ポリシーの条件として、保持ラベルを指定することができます。たとえば、指定された保持ラベルがドキュメントに適用されている場合はそのドキュメントが組織外に共有されないように、DLP ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="344c1-p116">You can specify a retention label as a condition in a data loss prevention (DLP) policy for documents in SharePoint. For example, configure a DLP policy to prevent documents from being shared outside the organization if they have a specified retention label applied to it.</span></span>

<span data-ttu-id="344c1-201">詳細については、「[DLP ポリシーでの条件としての保持ラベルの使用](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="344c1-201">For more information, see [Using a retention label as a condition in a DLP policy](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy).</span></span>

#### <a name="retention-labels-and-policies-that-apply-them"></a><span data-ttu-id="344c1-202">保持ラベルと保持ラベルを適用するポリシー</span><span class="sxs-lookup"><span data-stu-id="344c1-202">Retention labels and policies that apply them</span></span>

<span data-ttu-id="344c1-p117">保持ラベルは、独立した、再利用可能な文書パーツです。ラベル ポリシーの主な目的は、保持ラベルのセットをグループ化し、それらのラベルを表示する場所を指定することです。そうすることにより、管理者とユーザーはラベルをそれらの場所のコンテンツに適用できます。</span><span class="sxs-lookup"><span data-stu-id="344c1-p117">Retention labels are independent, reusable building blocks. The primary purpose of a retention label policy is to group a set of retention labels and specify the locations where you want those labels to appear. Then, admins and users can apply those labels to content in those locations.</span></span>
  
![ラベル、ラベル ポリシー、および場所の図](../media/eee42516-adf0-4664-b5ab-76727a9a3511.png)
  
<span data-ttu-id="344c1-207">保持ラベルを発行すると、それらは保持ラベル ポリシーに含まれます。このポリシーを使用することで、管理者やユーザーは次の中から選択して保持ラベルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="344c1-207">When you publish retention labels, they're included in a retention label policy that make them available for admins and users to select:</span></span>

- <span data-ttu-id="344c1-208">1 つの保持ラベルを複数の保持ラベル ポリシーに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="344c1-208">A single retention label can be included in many retention label policies.</span></span>

- <span data-ttu-id="344c1-209">保持ラベル ポリシーは保持ラベルを発行する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="344c1-209">Retention label policies specify the locations to publish the retention labels.</span></span>

- <span data-ttu-id="344c1-210">1 つの場所を複数の保持ラベル ポリシーに含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="344c1-210">A single location can also be included in many retention label policies.</span></span>

<span data-ttu-id="344c1-p118">保持ラベル ポリシーに加えて、1 つ以上の自動適用ポリシーを作成して、それぞれに保持ラベルを 1 つ指定することもできます。このポリシーを使うと、ポリシーで指定した条件が満たされた場合に、保持ラベルが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="344c1-p118">In addition to retention label policies, you can also create one or more auto-apply policies, each with a single retention label. With this policy, a retention label is automatically applied when conditions that you specify in the policy are met.</span></span> 

#### <a name="retention-label-policies-and-locations"></a><span data-ttu-id="344c1-213">保持ラベルのポリシーと場所</span><span class="sxs-lookup"><span data-stu-id="344c1-213">Retention label policies and locations</span></span>

<span data-ttu-id="344c1-214">保持ラベルの内容に応じて、多様な種類の保持ラベルをさまざまな場所に発行できます。</span><span class="sxs-lookup"><span data-stu-id="344c1-214">Different types of retention labels can be published to different locations, depending on what the retention label does.</span></span>
  
| <span data-ttu-id="344c1-215">保持ラベルの種類</span><span class="sxs-lookup"><span data-stu-id="344c1-215">If the retention label is…</span></span> | <span data-ttu-id="344c1-216">ラベル ポリシーの適用先</span><span class="sxs-lookup"><span data-stu-id="344c1-216">Then the label policy can be applied to…</span></span> |
|:-----|:-----|
|<span data-ttu-id="344c1-217">管理者とエンド ユーザーに発行されたラベル</span><span class="sxs-lookup"><span data-stu-id="344c1-217">Published to admins and end users</span></span>  <br/> |<span data-ttu-id="344c1-218">Exchange、SharePoint、OneDrive、Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="344c1-218">Exchange, SharePoint, OneDrive, Microsoft 365 Groups</span></span>  <br/> |
|<span data-ttu-id="344c1-219">機密情報の種類またはトレーニング可能な分類子に基づいて自動適用されたラベル</span><span class="sxs-lookup"><span data-stu-id="344c1-219">Auto-applied based on sensitive information types or trainable classifiers</span></span>  <br/> |<span data-ttu-id="344c1-220">Exchange (すべてのメールボックスのみ)、SharePoint、OneDrive</span><span class="sxs-lookup"><span data-stu-id="344c1-220">Exchange (all mailboxes only), SharePoint, OneDrive</span></span>  <br/> |
|<span data-ttu-id="344c1-221">クエリに基づいて自動適用されたラベル</span><span class="sxs-lookup"><span data-stu-id="344c1-221">Auto-applied based on a query</span></span>  <br/> |<span data-ttu-id="344c1-222">Exchange、SharePoint、OneDrive、Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="344c1-222">Exchange, SharePoint, OneDrive, Microsoft 365 Groups</span></span>  <br/> |
   
<span data-ttu-id="344c1-p119">Exchange では、自動適用の保持ラベルは、新しく送信されたメッセージ (送信中のデータ) にのみ適用され、現在メールボックスにあるすべてのアイテム (保存データ) には適用されません。また、機密情報の種類やトレーニング可能な分類子向けの自動適用の保持ラベルは、すべてのメールボックスにのみ適用されます。ただし、特定のメールボックスを選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="344c1-p119">In Exchange, auto-apply retention labels are applied only to messages newly sent (data in transit), not to all items currently in the mailbox (data at rest). Also, auto-apply retention labels for sensitive information types and trainable classifiers apply to all mailboxes; you can't select specific mailboxes.</span></span>
  
<span data-ttu-id="344c1-p120">Exchange パブリックフォルダー、Skype、Teams、Yammer メッセージは保持ラベルをサポートしていません。これらの場所のコンテンツを保持または削除するには、代わりにアイテム保持ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="344c1-p120">Exchange public folders, Skype, Teams and Yammer messages do not support retention labels. To retain and delete contain from these locations, use retention policies instead.</span></span>

#### <a name="only-one-retention-label-at-a-time"></a><span data-ttu-id="344c1-227">一度に 1 つの保持ラベルのみ</span><span class="sxs-lookup"><span data-stu-id="344c1-227">Only one retention label at a time</span></span>

<span data-ttu-id="344c1-228">メールやドキュメントに一度に適用できる保持ラベルは、1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="344c1-228">An email or document can have only a single retention label applied to it at a time.</span></span> <span data-ttu-id="344c1-229">保持ラベルは、エンド ユーザーや管理者が[手動](create-apply-retention-labels.md#manually-apply-retention-labels)で適用することも、次のいずれかの方法を使用して自動で適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="344c1-229">A retention label can be applied [manually](create-apply-retention-labels.md#manually-apply-retention-labels) by an end user or admin, or automatically by using any of the following methods:</span></span>

- [<span data-ttu-id="344c1-230">自動適用ラベル ポリシー</span><span class="sxs-lookup"><span data-stu-id="344c1-230">Auto-apply label policy</span></span>](apply-retention-labels-automatically.md)
- [<span data-ttu-id="344c1-231">SharePoint Syntex のドキュメント理解モデル</span><span class="sxs-lookup"><span data-stu-id="344c1-231">Document understanding model for SharePoint Syntex</span></span>](https://docs.microsoft.com/microsoft-365/contentunderstanding/apply-a-retention-label-to-a-model)
- <span data-ttu-id="344c1-232">[Outlook](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder) または [SharePoint の既定のラベル](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set)</span><span class="sxs-lookup"><span data-stu-id="344c1-232">[Default label for SharePoint](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set) or [Outlook](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)</span></span>
- [<span data-ttu-id="344c1-233">Outlook のルール</span><span class="sxs-lookup"><span data-stu-id="344c1-233">Outlook rules</span></span>](create-apply-retention-labels.md#automatically-applying-a-retention-label-to-email-by-using-rules)

<span data-ttu-id="344c1-234">標準的な保持ラベルの場合 (アイテムを[レコードや規制レコード](records-management.md#records)としてマークしません)。</span><span class="sxs-lookup"><span data-stu-id="344c1-234">For standard retention labels (they don't mark items as a [record or regulatory record](records-management.md#records)):</span></span>

- <span data-ttu-id="344c1-235">管理者とエンド ユーザーは、コンテンツに適用されている既存の保持ラベルを手動で変更または削除できます。</span><span class="sxs-lookup"><span data-stu-id="344c1-235">Admins and end users can manually change or remove an existing retention label that's applied on content.</span></span> 

- <span data-ttu-id="344c1-236">コンテンツに既に保持ラベルが適用されている場合、既存のラベルが自動的に削除されたり、別の保持ラベルに置き換えられたりすることはありません。ただし、例外が 1 つあり、既存のラベルが既定のラベルとして適用されている場合です。</span><span class="sxs-lookup"><span data-stu-id="344c1-236">When content already has a retention label applied, the existing label won't be automatically removed or replaced by another retention label with one possible exception: The existing label was applied as a default label.</span></span>
    
    <span data-ttu-id="344c1-237">既定のラベルを使用して適用した場合のラベルの動作については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="344c1-237">For more information about the label behavior when it's applied by using a default label:</span></span>
    - <span data-ttu-id="344c1-238">SharePoint の既定のラベル: [SharePoint の既定のラベルを使用した場合のラベルの動作](create-apply-retention-labels.md#label-behavior-when-you-use-a-default-label-for-sharepoint)</span><span class="sxs-lookup"><span data-stu-id="344c1-238">Default label for SharePoint: [Label behavior when you use a default label for SharePoint](create-apply-retention-labels.md#label-behavior-when-you-use-a-default-label-for-sharepoint)</span></span>
    - <span data-ttu-id="344c1-239">Outlook の既定のラベル: [Outlook フォルダーに既定の保持ラベルを適用する](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)</span><span class="sxs-lookup"><span data-stu-id="344c1-239">Default label for Outlook: [Applying a default retention label to an Outlook folder](create-apply-retention-labels.md#applying-a-default-retention-label-to-an-outlook-folder)</span></span>

- <span data-ttu-id="344c1-240">保持ラベルを適用できる自動適用ラベル ポリシーが複数あり、コンテンツが複数のポリシーの条件を満たしている場合、(作成日を基準にして) 最も古い自動適用ラベル ポリシーの保持ラベルが適用されます。</span><span class="sxs-lookup"><span data-stu-id="344c1-240">If there are multiple auto-apply label policies that could apply a retention label, and content meets the conditions of multiple policies, the retention label for the oldest auto-apply label policy (by date created) is applied.</span></span>

<span data-ttu-id="344c1-241">保持ラベルがアイテムをレコードまたは規制レコードとしてマークしている場合、これらのラベルが自動的に変更されることはありません。</span><span class="sxs-lookup"><span data-stu-id="344c1-241">When retention labels mark items as a record or a regulatory record, these labels are never automatically changed.</span></span> <span data-ttu-id="344c1-242">コンテナーの管理者のみが、アイテムをレコードとしてマークする保持ラベルを手動で変更または削除することができますが、規制レコードについてはできません。</span><span class="sxs-lookup"><span data-stu-id="344c1-242">Only admins for the container can manually change or remove retention labels that mark items as a record, but not regulatory records.</span></span> <span data-ttu-id="344c1-243">詳細については、「[許可またはブロックされているアクションの制限を比較する](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="344c1-243">For more information, see [Compare restrictions for what actions are allowed or blocked](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

#### <a name="monitoring-retention-labels"></a><span data-ttu-id="344c1-244">保持ラベルの監視</span><span class="sxs-lookup"><span data-stu-id="344c1-244">Monitoring retention labels</span></span>

<span data-ttu-id="344c1-245">Microsoft 365 コンプライアンス センターから、**データ分類** > **概要** を使用して、保持ラベルがテナントでどのように使用されているかを監視し、ラベル付きアイテムの場所を特定します。</span><span class="sxs-lookup"><span data-stu-id="344c1-245">From the Microsoft 365 compliance center, use **Data classification** > **Overview** to monitor how your retention labels are being used in your tenant, and identify where your labeled items are located.</span></span> <span data-ttu-id="344c1-246">重要な前提条件を含む詳細については、「[データを理解する - データ分類の概要](data-classification-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="344c1-246">For more information, including important prerequisites, see [Know your data - data classification overview](data-classification-overview.md).</span></span>

<span data-ttu-id="344c1-247">詳細については、[コンテンツ エクスプローラー](data-classification-content-explorer.md) と [アクティビティ エクスプローラー](data-classification-activity-explorer.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="344c1-247">You can then drill down into details by using [content explorer](data-classification-content-explorer.md) and [activity explorer](data-classification-activity-explorer.md).</span></span>

> [!TIP]
><span data-ttu-id="344c1-248">トレーニング可能な分類子や機密情報タイプなど、他のデータ分類インサイトのいくつかを使用することを検討して、レコードとして保持または削除する必要がある、またはレコードとして管理する必要があるコンテンツを特定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="344c1-248">Consider using some of the other data classification insights, such as trainable classifiers and sensitive info types, to help you identify content that you might need to retain or delete, or manage as records.</span></span>

<span data-ttu-id="344c1-249">Office 365 セキュリティ/コンプライアンス センターには、**情報ガバナンス** > **ダッシュボード** の保持ラベルと同等の概要情報と、**情報ガバナンス** > **ラベル アクティビティ エクスプローラー** の詳細情報があります。</span><span class="sxs-lookup"><span data-stu-id="344c1-249">The Office 365 Security & Compliance Center has the equivalent overview information for retention labels from **Information governance** > **Dashboard**, and more detailed information from **Information governance** > **Label activity explorer**.</span></span> <span data-ttu-id="344c1-250">この古い管理センターから保持ラベルを監視する方法の詳細については、次のドキュメントを参照してください:</span><span class="sxs-lookup"><span data-stu-id="344c1-250">For more information about monitoring retention labels from this older admin center, see the following documentation:</span></span>
- [<span data-ttu-id="344c1-251">データ ガバナンスのレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="344c1-251">View the data governance reports</span></span>](view-the-data-governance-reports.md)
- [<span data-ttu-id="344c1-252">ラベル分析によるラベル使用状況を表示する</span><span class="sxs-lookup"><span data-stu-id="344c1-252">View label usage with label analytics</span></span>](label-analytics.md)
- [<span data-ttu-id="344c1-253">ドキュメントのラベルのアクティビティを表示する</span><span class="sxs-lookup"><span data-stu-id="344c1-253">View label activity for documents</span></span>](view-label-activity-for-documents.md)

#### <a name="using-content-search-to-find-all-content-with-a-specific-retention-label"></a><span data-ttu-id="344c1-254">コンテンツ検索を使用した特定の保持ラベルを持つすべてのコンテンツの検索</span><span class="sxs-lookup"><span data-stu-id="344c1-254">Using Content Search to find all content with a specific retention label</span></span>

<span data-ttu-id="344c1-255">保持ラベルがユーザーによって、または自動適用されてコンテンツに適用された後、コンテンツ検索を使用して、特定の保持ラベルが適用されているすべてのアイテムを検索できます。</span><span class="sxs-lookup"><span data-stu-id="344c1-255">After retention labels are applied to content, either by users or auto-applied, you can use content search to find all items that have a specific retention label applied.</span></span>

<span data-ttu-id="344c1-256">コンテンツ検索を作成するとき、**保持 ラベル** の条件を選択し、完全な保持ラベル名を入力するか、ラベル名の一部を入力してワイルドカードを使用します。</span><span class="sxs-lookup"><span data-stu-id="344c1-256">When you create a content search, choose the **Retention label** condition, and then enter the complete retention label name or part of the label name and use a wildcard.</span></span> <span data-ttu-id="344c1-257">詳細については、「[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="344c1-257">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
![保持ラベルの条件](../media/retention-label-condition.png)


## <a name="compare-capabilities-for-retention-policies-and-retention-labels"></a><span data-ttu-id="344c1-259">アイテム保持ポリシーと保持ラベルの機能比較</span><span class="sxs-lookup"><span data-stu-id="344c1-259">Compare capabilities for retention policies and retention labels</span></span>

<span data-ttu-id="344c1-260">次の表は、アイテム保持ポリシーと保持ラベルのどちらを使用するかを、機能に基づいて決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="344c1-260">Use the following table to help you identify whether to use a retention policy or retention label, based on capabilities.</span></span>

|<span data-ttu-id="344c1-261">機能</span><span class="sxs-lookup"><span data-stu-id="344c1-261">Capability</span></span>|<span data-ttu-id="344c1-262">アイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="344c1-262">Retention policy</span></span> |<span data-ttu-id="344c1-263">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="344c1-263">Retention label</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="344c1-264">保持してから削除、保持のみ、削除のみを指定できる保持設定</span><span class="sxs-lookup"><span data-stu-id="344c1-264">Retention settings that can retain and then delete, retain-only, or delete-only</span></span> |<span data-ttu-id="344c1-265">はい</span><span class="sxs-lookup"><span data-stu-id="344c1-265">Yes</span></span> |<span data-ttu-id="344c1-266">はい</span><span class="sxs-lookup"><span data-stu-id="344c1-266">Yes</span></span> |
|<span data-ttu-id="344c1-267">サポートされるワークロード:</span><span class="sxs-lookup"><span data-stu-id="344c1-267">Workloads supported:</span></span> <br /><span data-ttu-id="344c1-268">- Exchange</span><span class="sxs-lookup"><span data-stu-id="344c1-268">- Exchange</span></span> <br /><span data-ttu-id="344c1-269">- SharePoint</span><span class="sxs-lookup"><span data-stu-id="344c1-269">- SharePoint</span></span> <br /><span data-ttu-id="344c1-270">- OneDrive</span><span class="sxs-lookup"><span data-stu-id="344c1-270">- OneDrive</span></span> <br /><span data-ttu-id="344c1-271">- Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="344c1-271">- Microsoft 365 groups</span></span> <br /><span data-ttu-id="344c1-272">- Skype for Business</span><span class="sxs-lookup"><span data-stu-id="344c1-272">- Skype for Business</span></span> <br /><span data-ttu-id="344c1-273">- Teams</span><span class="sxs-lookup"><span data-stu-id="344c1-273">- Teams</span></span><br /><span data-ttu-id="344c1-274">- Yammer</span><span class="sxs-lookup"><span data-stu-id="344c1-274">- Yammer</span></span>|<br /> <span data-ttu-id="344c1-275">はい</span><span class="sxs-lookup"><span data-stu-id="344c1-275">Yes</span></span> <br /> <span data-ttu-id="344c1-276">はい</span><span class="sxs-lookup"><span data-stu-id="344c1-276">Yes</span></span> <br /> <span data-ttu-id="344c1-277">はい</span><span class="sxs-lookup"><span data-stu-id="344c1-277">Yes</span></span> <br /> <span data-ttu-id="344c1-278">はい</span><span class="sxs-lookup"><span data-stu-id="344c1-278">Yes</span></span> <br /> <span data-ttu-id="344c1-279">はい</span><span class="sxs-lookup"><span data-stu-id="344c1-279">Yes</span></span> <br /> <span data-ttu-id="344c1-280">はい</span><span class="sxs-lookup"><span data-stu-id="344c1-280">Yes</span></span> <br /> <span data-ttu-id="344c1-281">はい</span><span class="sxs-lookup"><span data-stu-id="344c1-281">Yes</span></span> | <br /> <span data-ttu-id="344c1-282">はい (パブリック フォルダーを除く)</span><span class="sxs-lookup"><span data-stu-id="344c1-282">Yes, except public folders</span></span> <br /> <span data-ttu-id="344c1-283">はい</span><span class="sxs-lookup"><span data-stu-id="344c1-283">Yes</span></span> <br /> <span data-ttu-id="344c1-284">はい</span><span class="sxs-lookup"><span data-stu-id="344c1-284">Yes</span></span> <br /> <span data-ttu-id="344c1-285">はい</span><span class="sxs-lookup"><span data-stu-id="344c1-285">Yes</span></span> <br /> <span data-ttu-id="344c1-286">いいえ</span><span class="sxs-lookup"><span data-stu-id="344c1-286">No</span></span> <br /> <span data-ttu-id="344c1-287">いいえ</span><span class="sxs-lookup"><span data-stu-id="344c1-287">No</span></span> <br /> <span data-ttu-id="344c1-288">いいえ</span><span class="sxs-lookup"><span data-stu-id="344c1-288">No</span></span> |
|<span data-ttu-id="344c1-289">保持の自動適用</span><span class="sxs-lookup"><span data-stu-id="344c1-289">Retention applied automatically</span></span> | <span data-ttu-id="344c1-290">はい</span><span class="sxs-lookup"><span data-stu-id="344c1-290">Yes</span></span> | <span data-ttu-id="344c1-291">はい</span><span class="sxs-lookup"><span data-stu-id="344c1-291">Yes</span></span> |
|<span data-ttu-id="344c1-292">条件に基づいて適用される保持</span><span class="sxs-lookup"><span data-stu-id="344c1-292">Retention applied based on conditions</span></span> <br /> <span data-ttu-id="344c1-293">- 機密情報の種類、KQL クエリ、トレーニング可能な分類子</span><span class="sxs-lookup"><span data-stu-id="344c1-293">- sensitive info types, KQL queries, trainable classifiers</span></span>| <span data-ttu-id="344c1-294">不要</span><span class="sxs-lookup"><span data-stu-id="344c1-294">No</span></span> | <span data-ttu-id="344c1-295">はい</span><span class="sxs-lookup"><span data-stu-id="344c1-295">Yes</span></span> |
|<span data-ttu-id="344c1-296">保持の手動適用</span><span class="sxs-lookup"><span data-stu-id="344c1-296">Retention applied manually</span></span> | <span data-ttu-id="344c1-297">いいえ</span><span class="sxs-lookup"><span data-stu-id="344c1-297">No</span></span> | <span data-ttu-id="344c1-298">はい</span><span class="sxs-lookup"><span data-stu-id="344c1-298">Yes</span></span> |
|<span data-ttu-id="344c1-299">エンド ユーザー向け UI の存在</span><span class="sxs-lookup"><span data-stu-id="344c1-299">UI presence for end users</span></span> | <span data-ttu-id="344c1-300">いいえ</span><span class="sxs-lookup"><span data-stu-id="344c1-300">No</span></span> | <span data-ttu-id="344c1-301">はい</span><span class="sxs-lookup"><span data-stu-id="344c1-301">Yes</span></span> |
|<span data-ttu-id="344c1-302">コンテンツが移動された場合の保持</span><span class="sxs-lookup"><span data-stu-id="344c1-302">Persists if the content is moved</span></span> | <span data-ttu-id="344c1-303">いいえ</span><span class="sxs-lookup"><span data-stu-id="344c1-303">No</span></span> | <span data-ttu-id="344c1-304">はい (Microsoft 365 テナント内で)</span><span class="sxs-lookup"><span data-stu-id="344c1-304">Yes, within your Microsoft 365 tenant</span></span> |
|<span data-ttu-id="344c1-305">レコードとしてアイテムを宣言</span><span class="sxs-lookup"><span data-stu-id="344c1-305">Declare item as a record</span></span>| <span data-ttu-id="344c1-306">不要</span><span class="sxs-lookup"><span data-stu-id="344c1-306">No</span></span> | <span data-ttu-id="344c1-307">はい</span><span class="sxs-lookup"><span data-stu-id="344c1-307">Yes</span></span> |
|<span data-ttu-id="344c1-308">ラベル作成時またはイベント発生時に保持期間を開始</span><span class="sxs-lookup"><span data-stu-id="344c1-308">Start the retention period when labeled or based on an event</span></span> | <span data-ttu-id="344c1-309">不要</span><span class="sxs-lookup"><span data-stu-id="344c1-309">No</span></span> | <span data-ttu-id="344c1-310">はい</span><span class="sxs-lookup"><span data-stu-id="344c1-310">Yes</span></span> |
|<span data-ttu-id="344c1-311">処理確認</span><span class="sxs-lookup"><span data-stu-id="344c1-311">Disposition review</span></span> | <span data-ttu-id="344c1-312">いいえ</span><span class="sxs-lookup"><span data-stu-id="344c1-312">No</span></span>| <span data-ttu-id="344c1-313">はい</span><span class="sxs-lookup"><span data-stu-id="344c1-313">Yes</span></span> |
|<span data-ttu-id="344c1-314">廃棄の証明 (最大 7 年間)</span><span class="sxs-lookup"><span data-stu-id="344c1-314">Proof of disposition for up to 7 years</span></span> | <span data-ttu-id="344c1-315">いいえ</span><span class="sxs-lookup"><span data-stu-id="344c1-315">No</span></span> |<span data-ttu-id="344c1-316">はい (アイテムがレコードとして宣言されている場合)</span><span class="sxs-lookup"><span data-stu-id="344c1-316">Yes, when item is declared a record</span></span>|
|<span data-ttu-id="344c1-317">管理者アクティビティを監査する</span><span class="sxs-lookup"><span data-stu-id="344c1-317">Audit admin activities</span></span>| <span data-ttu-id="344c1-318">はい</span><span class="sxs-lookup"><span data-stu-id="344c1-318">Yes</span></span> | <span data-ttu-id="344c1-319">はい</span><span class="sxs-lookup"><span data-stu-id="344c1-319">Yes</span></span>|
|<span data-ttu-id="344c1-320">保持対象のアイテムの特定</span><span class="sxs-lookup"><span data-stu-id="344c1-320">Identify items subject to retention:</span></span> <br /> <span data-ttu-id="344c1-321">- コンテンツ検索</span><span class="sxs-lookup"><span data-stu-id="344c1-321">- Content Search</span></span> <br /> <span data-ttu-id="344c1-322">- データ分類ページ、コンテンツ エクスプローラー、アクティビティ エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="344c1-322">- Data classification page, content explorer, activity explorer</span></span> | <br /> <span data-ttu-id="344c1-323">不要</span><span class="sxs-lookup"><span data-stu-id="344c1-323">No</span></span> <br /> <span data-ttu-id="344c1-324">いいえ</span><span class="sxs-lookup"><span data-stu-id="344c1-324">No</span></span> | <br /> <span data-ttu-id="344c1-325">はい</span><span class="sxs-lookup"><span data-stu-id="344c1-325">Yes</span></span> <br /> <span data-ttu-id="344c1-326">はい</span><span class="sxs-lookup"><span data-stu-id="344c1-326">Yes</span></span>|

<span data-ttu-id="344c1-327">アイテム保持ポリシーと保持ラベルの両方を補完的な保持方法として使用することができます。</span><span class="sxs-lookup"><span data-stu-id="344c1-327">Note that you can use both retention policies and retention labels as complementary retention methods.</span></span> <span data-ttu-id="344c1-328">例:</span><span class="sxs-lookup"><span data-stu-id="344c1-328">For example:</span></span>

1. <span data-ttu-id="344c1-329">最終更新日から 5 年後にコンテンツを自動的に削除するアイテム保持ポリシーを作成して構成し、すべての OneDrive アカウントにそのポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="344c1-329">You create and configure a retention policy that automatically deletes content five years after it's last modified, and apply the policy to all OneDrive accounts.</span></span>

2. <span data-ttu-id="344c1-330">コンテンツを無期限に保持する保持ラベルを作成して構成し、すべての OneDrive アカウントに対して発行するラベル ポリシーにこのラベルを追加します。</span><span class="sxs-lookup"><span data-stu-id="344c1-330">You create and configure a retention label that keeps content forever and add this to a label policy that you publish to all OneDrive accounts.</span></span> <span data-ttu-id="344c1-331">5 年間更新されない場合でも自動削除されないようにする必要のある特定のドキュメントに対して、このラベルを手動で適用する方法をユーザーに説明します。</span><span class="sxs-lookup"><span data-stu-id="344c1-331">You explain to users how to manually apply this label to specific documents that should be excluded from automatic deletion if not modified after five years.</span></span>

<span data-ttu-id="344c1-332">アイテム保持ポリシーと保持ラベルを組み合わせて使用する方法、および組み合わせて使用した場合の結果の確認方法の詳細については、保持の原則と優先順位について説明している次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="344c1-332">For more information about how retention policies and retention labels work together and how to determine their combined outcome, see the next section that explains the principles of retention and what takes precedence.</span></span>

## <a name="the-principles-of-retention-or-what-takes-precedence"></a><span data-ttu-id="344c1-333">保持の原則と優先順位</span><span class="sxs-lookup"><span data-stu-id="344c1-333">The principles of retention, or what takes precedence?</span></span>

<span data-ttu-id="344c1-334">コンテンツにアイテム保持ポリシーや保持ラベルがいくつか適用されており、それぞれのポリシーやラベルに異なるアクション (保持、削除、保持してから削除) や保持期間が指定されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="344c1-334">It's possible or even likely that content might have several retention policies and retention labels applied to it, each with a different action (retain, delete, or retain and then delete) and retention period.</span></span> <span data-ttu-id="344c1-335">優先順位</span><span class="sxs-lookup"><span data-stu-id="344c1-335">What takes precedence?</span></span> 

<span data-ttu-id="344c1-336">大まかに言えば、保持は削除より常に優先され、最長の保持期間が優先されます。</span><span class="sxs-lookup"><span data-stu-id="344c1-336">At a high level, you can be assured that retention always takes precedence over deletion, and then the longest retention period wins.</span></span> 

<span data-ttu-id="344c1-337">とはいえ、組み合わせて使用する場合は他にも決定要因があります。結果を理解するため、次のフロー図を使用して説明します。この図の各レベルは、優先順位に従って上から下に配列されており、上位のレベルで結果が決定する場合は次のレベルには進みません。</span><span class="sxs-lookup"><span data-stu-id="344c1-337">However, there are a few more factors to throw into the mix, so use the following flow to understand the outcome where each level acts as a tie-breaker from top to bottom: If the outcome is determined by the first level, there's no need to progress to the next level, and so on.</span></span> <span data-ttu-id="344c1-338">そのレベルのルールで結果が決定しない場合のみ、フロー図の下位のレベルに進み、その保持設定の優先順位で結果を判断します。</span><span class="sxs-lookup"><span data-stu-id="344c1-338">Only if the outcome can't be determined by the rules for the level does the flow move down to the next level to determine the outcome for which retention settings take precedence.</span></span>

![保持の原則の図](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
<span data-ttu-id="344c1-340">4 つのレベルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="344c1-340">Explanation for the four different levels:</span></span>
  
1. <span data-ttu-id="344c1-341">**削除よりも保持が優先されます。**</span><span class="sxs-lookup"><span data-stu-id="344c1-341">**Retention wins over deletion.**</span></span> <span data-ttu-id="344c1-342">3 年後に Exchange メールを削除するように構成されているアイテム保持ポリシーがあり、加えて 5 年間 Exchange メールを保持してから削除するように構成されている別のアイテム保持ポリシーもあるとします。</span><span class="sxs-lookup"><span data-stu-id="344c1-342">Suppose that one retention policy is configured to delete Exchange email after three years, but another retention policy is configured to retain Exchange email for five years and then delete it.</span></span> <span data-ttu-id="344c1-343">作成後 3 年に達するコンテンツはすべて削除され、ユーザーのビューから非表示になりますが、コンテンツが完全に削除される 5 年に達するまで、[回復可能なアイテム] フォルダーに保持されます。</span><span class="sxs-lookup"><span data-stu-id="344c1-343">Any content that reaches three years old will be deleted and hidden from the users' view, but still retained in the Recoverable Items folder until the content reaches five years old, when it is permanently deleted.</span></span> 
2. <span data-ttu-id="344c1-344">**最長の保持期間が優先されます。**</span><span class="sxs-lookup"><span data-stu-id="344c1-344">**The longest retention period wins.**</span></span> <span data-ttu-id="344c1-345">期間の異なる複数の保持設定がコンテンツに対して指定されている場合、そのコンテンツは最長の保持期間が終了するまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="344c1-345">If content is subject to multiple retention settings that retain content for different periods of time, the content will be retained until the end of the longest retention period.</span></span>
    
3. <span data-ttu-id="344c1-346">**明示的に含める方が、暗黙的に含めるよりも優先されます。**</span><span class="sxs-lookup"><span data-stu-id="344c1-346">**Explicit inclusion wins over implicit inclusion.**</span></span> <span data-ttu-id="344c1-347">これは、次のことを意味します。</span><span class="sxs-lookup"><span data-stu-id="344c1-347">This means:</span></span> 
    
    1. <span data-ttu-id="344c1-348">Exchange メールや OneDrive ドキュメントなど、ユーザーが保持設定を含む保持ラベルをアイテムに手動で割り当てた場合は、サイト レベルまたはメールボックス レベルで割り当てられているアイテム保持ポリシーや、ドキュメント ライブラリに割り当てられている既定の保持ラベルよりも、手動で割り当てたラベルが優先されます。</span><span class="sxs-lookup"><span data-stu-id="344c1-348">If a retention label with retention settings is manually assigned by a user to an item, such as an Exchange email or OneDrive document, that retention label takes precedence over both a retention policy assigned at the site or mailbox level and a default retention label assigned to the document library.</span></span> <span data-ttu-id="344c1-349">たとえば、明示的な保持ラベルでは 10 年間コンテンツを保持するように構成され、サイトに割り当てられているアイテム保持ポリシーでは 5 年間のみコンテンツを保持するように構成されている場合、明示的な保持ラベルが優先されます。</span><span class="sxs-lookup"><span data-stu-id="344c1-349">For example, if the explicit retention label is configured to retain content for ten years, but a retention policy assigned to the site is configured to retain content for only five years, the retention label takes precedence.</span></span>
    
    2. <span data-ttu-id="344c1-350">アイテム保持ポリシーに特定のユーザーのメールボックスまたは OneDrive のアカウントなどの特定の場所が含まれている場合、そのアイテム保持ポリシーは、すべてのユーザーのメールボックスまたは OneDrive のアカウントに適用されるが、そのユーザーのメールボックスを特に含まない別の保持ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="344c1-350">If a retention policy includes a specific location, such as a specific user's mailbox or OneDrive account, that retention policy takes precedence over another retention policy that applies to all users' mailboxes or OneDrive accounts but doesn't specifically include that user's mailbox.</span></span>
    
4. <span data-ttu-id="344c1-351">**最短の削除期間が優先されます。**</span><span class="sxs-lookup"><span data-stu-id="344c1-351">**The shortest deletion period wins.**</span></span> <span data-ttu-id="344c1-352">同様に、保持期間なしでコンテンツを削除する複数の保持設定が指定されている場合、そのコンテンツは最短保持期間の終了時に削除されます。</span><span class="sxs-lookup"><span data-stu-id="344c1-352">Similarly, if content is subject to multiple retention settings that delete content without a retention period, that content will be deleted at the end of the shortest retention period.</span></span> 

<span data-ttu-id="344c1-353">最後に、アイテム保持ポリシーや保持ラベルでは、電子情報開示のために保持しているコンテンツを完全に削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="344c1-353">Finally, a retention policy or retention label cannot permanently delete any content that's on hold for eDiscovery.</span></span> <span data-ttu-id="344c1-354">電子情報開示のための保持を解除すると、コンテンツは再びそのワークロードに対するセキュリティで保護された場所のクリーンアップ プロセスの対象になります。</span><span class="sxs-lookup"><span data-stu-id="344c1-354">When that hold is released, the content again becomes eligible for the cleanup process in the secured locations for the workload.</span></span>

## <a name="use-preservation-lock-to-restrict-changes-to-policies"></a><span data-ttu-id="344c1-355">保管ロックを使用してポリシーへの変更を制限する</span><span class="sxs-lookup"><span data-stu-id="344c1-355">Use Preservation Lock to restrict changes to policies</span></span>

<span data-ttu-id="344c1-356">一部の組織は、米国証券取引委員会 (SEC) 規則 17a-4 など、規制機関によって定義された規則に準拠する必要があります。その場合、保持ポリシーをオンにした後、それをオフにしたり、制限を緩和したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="344c1-356">Some organizations might need to comply with rules defined by regulatory bodies such as the Securities and Exchange Commission (SEC) Rule 17a-4, which requires that after a policy for retention is turned on, it cannot be turned off or made less restrictive.</span></span> 

<span data-ttu-id="344c1-357">保管ロックを使用すると、アイテム保持ポリシーまたは保持ラベル ポリシーがロックされ、管理者を含むいかなるユーザーも、ポリシーをオフにしたり、削除、またはその制限を緩和したりすることができなくなるため、組織はこのような規制要件を確実に満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="344c1-357">Preservation Lock ensures your organization can meet such regulatory requirements because it locks a retention policy or retention label policy so that no one—including an administrator—can turn off the policy, delete the policy, or make it less restrictive.</span></span>
  
<span data-ttu-id="344c1-358">アイテム保持ポリシーまたは保持ラベル ポリシーを作成した後に、PowerShell を使用して保管ロックを適用します。</span><span class="sxs-lookup"><span data-stu-id="344c1-358">You apply Preservation Lock after the retention policy or retention label policy is created.</span></span> <span data-ttu-id="344c1-359">詳細と手順については、「[保管ロックを使用して、アイテム保持ポリシーと保持ラベル ポリシーへの変更を制限する](retention-preservation-lock.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="344c1-359">For more information and instructions, see [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).</span></span>

## <a name="releasing-a-policy-for-retention"></a><span data-ttu-id="344c1-360">保持に関するポリシーを解放する</span><span class="sxs-lookup"><span data-stu-id="344c1-360">Releasing a policy for retention</span></span>

<span data-ttu-id="344c1-361">保管ロックが適用されていない保持に関するポリシーの場合は、いつでもポリシーを削除できます。それにより、以前に適用された保持設定は事実上無効になります。</span><span class="sxs-lookup"><span data-stu-id="344c1-361">Providing your policies for retention don't have a Preservation Lock, you can delete your policies at any time, which effectively turns off the previously applied retention settings.</span></span> <span data-ttu-id="344c1-362">ポリシーを維持して、場所の状態をオフに変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="344c1-362">You can also keep the policy but change the location status to off.</span></span>
 
<span data-ttu-id="344c1-363">これらの操作のいずれかを実行しても、[アイテム保管ライブラリ] に保持されている SharePoint や OneDrive のコンテンツについては、直ちに完全に削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="344c1-363">When you do either of these actions, any SharePoint or OneDrive content that's being retained in the Preservation Hold library is not immediately and permanently deleted.</span></span> <span data-ttu-id="344c1-364">代わりに、不注意によるデータの損失を防ぐために、30 日間の猶予期間があります。そのポリシーのコンテンツの有効期限は、[アイテム保管ライブラリ] には表示されず、必要に応じてコンテンツを復元できます。</span><span class="sxs-lookup"><span data-stu-id="344c1-364">Instead, to help prevent inadvertent data loss, there is a 30-day grace period, during which content expiration for that policy does not happen in the Preservation Hold library, so that you can restore any content from there, if needed.</span></span> <span data-ttu-id="344c1-365">また、猶予期間中はこのコンテンツを手動で削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="344c1-365">Additionally, you can't manually delete this content during the grace period.</span></span>

<span data-ttu-id="344c1-366">猶予期間中に場所の状態をオンに戻すことができ、そのポリシーのコンテンツは削除されません。</span><span class="sxs-lookup"><span data-stu-id="344c1-366">You can change the location status back to on during the grace period, and no content will be deleted for that policy.</span></span>

<span data-ttu-id="344c1-367">この SharePoint と OneDrive の 30 日の猶予期間は、Exchange の 30 日の保留期間に対応しています。</span><span class="sxs-lookup"><span data-stu-id="344c1-367">This 30-day grace period in SharePoint and OneDrive corresponds to the 30-day delay hold in Exchange.</span></span> <span data-ttu-id="344c1-368">詳しくは、[メールボックスの管理についての詳細](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold) をご覧ください。。</span><span class="sxs-lookup"><span data-stu-id="344c1-368">For more information, see [Managing mailboxes on delay hold](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).</span></span>

## <a name="auditing-retention-configuration"></a><span data-ttu-id="344c1-369">アイテム保持構成の監査</span><span class="sxs-lookup"><span data-stu-id="344c1-369">Auditing retention configuration</span></span>

<span data-ttu-id="344c1-370">[監査が有効になっている](turn-audit-log-search-on-or-off.md) 場合、アイテム保持ポリシーと保持ラベルの管理者アクションは監査ログに保存されます。</span><span class="sxs-lookup"><span data-stu-id="344c1-370">Administrator actions for retention policies and retention labels are saved to the audit log when [auditing is enabled](turn-audit-log-search-on-or-off.md).</span></span> <span data-ttu-id="344c1-371">たとえば、アイテム保持ポリシーまたはラベルを作成、構成、または削除すると、監査イベントが作成されます。</span><span class="sxs-lookup"><span data-stu-id="344c1-371">For example, an audit event is created when a retention policy or label is created, configured, or deleted.</span></span> <span data-ttu-id="344c1-372">完全なリストについては、「[アイテム保持ポリシーと保持ラベルのアクティビティ](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="344c1-372">For the full list, see [Retention policy and retention label activities](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities).</span></span>

## <a name="powershell-cmdlets-for-retention-policies-and-retention-labels"></a><span data-ttu-id="344c1-373">アイテム保持ポリシーと保持ラベルの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="344c1-373">PowerShell cmdlets for retention policies and retention labels</span></span>

<span data-ttu-id="344c1-374">保持コマンドレットを使用するには、最初に [Office 365 セキュリティ/コンプライアンス センターの PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) に接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="344c1-374">To use the retention cmdlets, you must first [connect to the Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="344c1-375">次に、次のいずれかのコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="344c1-375">Then, use any of the following cmdlets:</span></span>

- [<span data-ttu-id="344c1-376">Get-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="344c1-376">Get-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancetag)

- [<span data-ttu-id="344c1-377">New-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="344c1-377">New-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-compliancetag)

- [<span data-ttu-id="344c1-378">Remove-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="344c1-378">Remove-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-compliancetag)

- [<span data-ttu-id="344c1-379">Set-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="344c1-379">Set-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-compliancetag)

- [<span data-ttu-id="344c1-380">Enable-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="344c1-380">Enable-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/enable-compliancetagstorage)

- [<span data-ttu-id="344c1-381">Get-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="344c1-381">Get-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancetagstorage)

- [<span data-ttu-id="344c1-382">Get-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="344c1-382">Get-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)

- [<span data-ttu-id="344c1-383">New-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="344c1-383">New-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)

- [<span data-ttu-id="344c1-384">Remove-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="344c1-384">Remove-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)

- [<span data-ttu-id="344c1-385">Set-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="344c1-385">Set-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)

- [<span data-ttu-id="344c1-386">Get-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="344c1-386">Get-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)

- [<span data-ttu-id="344c1-387">New-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="344c1-387">New-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)

- [<span data-ttu-id="344c1-388">Remove-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="344c1-388">Remove-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)

- [<span data-ttu-id="344c1-389">Set-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="344c1-389">Set-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)

## <a name="when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds"></a><span data-ttu-id="344c1-390">アイテム保持ポリシーと保持ラベルまたは電子情報開示用の保留を使用する場合</span><span class="sxs-lookup"><span data-stu-id="344c1-390">When to use retention policies and retention labels or eDiscovery holds</span></span>

<span data-ttu-id="344c1-391">保持の設定と[電子情報開示ケースを使用して作成した保留](create-ediscovery-holds.md)は、両方ともデータが完全に削除されるのを防ぐことができますが、さまざまなシナリオに対応できるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="344c1-391">Although retention settings and [holds that you create with an eDiscovery case](create-ediscovery-holds.md) can both prevent data from being permanently deleted, they are designed for different scenarios.</span></span> <span data-ttu-id="344c1-392">違いを理解し、どちらを使用するかを決定するために、以下のガイダンスをご利用ください。</span><span class="sxs-lookup"><span data-stu-id="344c1-392">To help you understand the differences and decide which to use, use the following guidance:</span></span>

- <span data-ttu-id="344c1-393">アイテム保持ポリシーや保持ラベルで指定する保持の設定は、コンプライアンス要件に合わせてデータを保持または削除する長期的な情報ガバナンス戦略のために設計されています。</span><span class="sxs-lookup"><span data-stu-id="344c1-393">Retention settings that you specify in retention policies and retention labels are designed for a long-term information governance strategy to retain or delete data for compliance requirements.</span></span> <span data-ttu-id="344c1-394">その範囲は通常、個々のユーザーよりも場所やコンテンツに焦点を合わせた幅広いものとなっています。</span><span class="sxs-lookup"><span data-stu-id="344c1-394">The scope is usually broad with the main focus being the location and content rather than individual users.</span></span> <span data-ttu-id="344c1-395">保持期間の開始日と終了日は構成可能で、追加の管理者が介入することなくコンテンツを自動的に削除できるオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="344c1-395">The start and end of the retention period is configurable, with the option to automatically delete content without additional administrator intervention.</span></span>

- <span data-ttu-id="344c1-396">電子情報開示 (コア電子情報開示または Advanced eDiscovery ケース) のための保留は、法的な調査のためにデータを保存する限られた期間のために設計されています。</span><span class="sxs-lookup"><span data-stu-id="344c1-396">Holds for eDiscovery (either Core eDiscovery or Advanced eDiscovery cases) are designed for a limited duration to preserve data for a legal investigation.</span></span> <span data-ttu-id="344c1-397">範囲については、特定のユーザーが所有するコンテンツに限定されます。</span><span class="sxs-lookup"><span data-stu-id="344c1-397">The scope is specific with the focus being content owned by identified users.</span></span> <span data-ttu-id="344c1-398">保持期間の開始日と終了日は構成できませんが、個々の管理者の操作に依存し、保留が解除されたときにコンテンツを自動的に削除するオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="344c1-398">The start and end of the preservation period isn't configurable but dependent on individual administrator actions, without an option to automatically delete content when the hold is released.</span></span>

<span data-ttu-id="344c1-399">保持と保留を比較するための概要</span><span class="sxs-lookup"><span data-stu-id="344c1-399">Summary to compare retention with holds:</span></span>

|<span data-ttu-id="344c1-400">考慮事項</span><span class="sxs-lookup"><span data-stu-id="344c1-400">Consideration</span></span>|<span data-ttu-id="344c1-401">保持</span><span class="sxs-lookup"><span data-stu-id="344c1-401">Retention</span></span> |<span data-ttu-id="344c1-402">電子情報開示の保留</span><span class="sxs-lookup"><span data-stu-id="344c1-402">eDiscovery holds</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="344c1-403">ビジネス ニーズ:</span><span class="sxs-lookup"><span data-stu-id="344c1-403">Business need:</span></span> |<span data-ttu-id="344c1-404">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="344c1-404">Compliance</span></span> |<span data-ttu-id="344c1-405">法務</span><span class="sxs-lookup"><span data-stu-id="344c1-405">Legal</span></span> |
|<span data-ttu-id="344c1-406">時間の範囲:</span><span class="sxs-lookup"><span data-stu-id="344c1-406">Time scope:</span></span> |<span data-ttu-id="344c1-407">長期</span><span class="sxs-lookup"><span data-stu-id="344c1-407">Long-term</span></span> |<span data-ttu-id="344c1-408">短期</span><span class="sxs-lookup"><span data-stu-id="344c1-408">Short-term</span></span> |
|<span data-ttu-id="344c1-409">フォーカス:</span><span class="sxs-lookup"><span data-stu-id="344c1-409">Focus:</span></span> |<span data-ttu-id="344c1-410">広範囲、コンテンツベース</span><span class="sxs-lookup"><span data-stu-id="344c1-410">Broad, content-based</span></span> |<span data-ttu-id="344c1-411">限定的、ユーザーベース</span><span class="sxs-lookup"><span data-stu-id="344c1-411">Specific, user-based</span></span> |
|<span data-ttu-id="344c1-412">開始日と終了日の構成が可能:</span><span class="sxs-lookup"><span data-stu-id="344c1-412">Start and end date configurable:</span></span> |<span data-ttu-id="344c1-413">必要</span><span class="sxs-lookup"><span data-stu-id="344c1-413">Yes</span></span> |<span data-ttu-id="344c1-414">いいえ</span><span class="sxs-lookup"><span data-stu-id="344c1-414">No</span></span> |
|<span data-ttu-id="344c1-415">コンテンツの削除</span><span class="sxs-lookup"><span data-stu-id="344c1-415">Content deletion:</span></span> |<span data-ttu-id="344c1-416">はい (オプション)</span><span class="sxs-lookup"><span data-stu-id="344c1-416">Yes (optional)</span></span> |<span data-ttu-id="344c1-417">いいえ</span><span class="sxs-lookup"><span data-stu-id="344c1-417">No</span></span> |
|<span data-ttu-id="344c1-418">管理費:</span><span class="sxs-lookup"><span data-stu-id="344c1-418">Administrative overheads:</span></span> |<span data-ttu-id="344c1-419">低い</span><span class="sxs-lookup"><span data-stu-id="344c1-419">Low</span></span> |<span data-ttu-id="344c1-420">高い</span><span class="sxs-lookup"><span data-stu-id="344c1-420">High</span></span> |

<span data-ttu-id="344c1-421">コンテンツが保持の設定と電子情報開示の保留の両方の対象になっている場合、電子情報開示の保留のためのコンテンツの保存が常に優先されます。</span><span class="sxs-lookup"><span data-stu-id="344c1-421">If content is subject to both retention settings and an eDiscovery hold, preserving content for the eDiscovery hold always takes precedence.</span></span> <span data-ttu-id="344c1-422">このように、管理者が手動で保留を解除するまでデータは保持されるため、[保持の原則](#the-principles-of-retention-or-what-takes-precedence)は電子情報開示の保留にまで拡張されます。</span><span class="sxs-lookup"><span data-stu-id="344c1-422">In this way, the [principles of retention](#the-principles-of-retention-or-what-takes-precedence) expand to eDiscovery holds because they preserve data until an administrator manually releases the hold.</span></span> <span data-ttu-id="344c1-423">ただし、このような優先順位があるにもかかわらず、長期的な情報ガバナンスのために電子情報開示の保留を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="344c1-423">However, despite this precedence, don't use eDiscovery holds for long-term information governance.</span></span> <span data-ttu-id="344c1-424">データの自動削除について心配がある場合は、アイテムを無期限に保持するように保持の設定を構成したり、保持ラベルを用いて[処理確認](disposition.md#disposition-reviews)を使用したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="344c1-424">If you are concerned about automatic deletion of data, you can configure retention settings to retain items forever, or use [disposition review](disposition.md#disposition-reviews) with retention labels.</span></span>

<span data-ttu-id="344c1-425">古い電子情報開示ツールを使用してデータを保存している場合は、以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="344c1-425">If you are using older eDiscovery tools to preserve data, see the following resources:</span></span>

- <span data-ttu-id="344c1-426">Exchange:</span><span class="sxs-lookup"><span data-stu-id="344c1-426">Exchange:</span></span> 
    - [<span data-ttu-id="344c1-427">インプレース保持と訴訟ホールド</span><span class="sxs-lookup"><span data-stu-id="344c1-427">In-Place Hold and Litigation Hold</span></span>](https://go.microsoft.com/fwlink/?linkid=846124)
    - [<span data-ttu-id="344c1-428">Exchange Online メールボックスに適用されている保留の種類を特定する方法</span><span class="sxs-lookup"><span data-stu-id="344c1-428">How to identify the type of hold placed on an Exchange Online mailbox</span></span>](https://docs.microsoft.com/microsoft-365/compliance/identify-a-hold-on-an-exchange-online-mailbox)

- <span data-ttu-id="344c1-429">SharePoint と OneDrive</span><span class="sxs-lookup"><span data-stu-id="344c1-429">SharePoint and OneDrive:</span></span> 
    - [<span data-ttu-id="344c1-430">電子情報開示センターでのコンテンツのケースへの追加とソースの保留リストへの配置</span><span class="sxs-lookup"><span data-stu-id="344c1-430">Add content to a case and place sources on hold in the eDiscovery Center</span></span>](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center)

- [<span data-ttu-id="344c1-431">従来の電子情報開示ツールの廃止</span><span class="sxs-lookup"><span data-stu-id="344c1-431">Retirement of legacy eDiscovery tools</span></span>](legacy-ediscovery-retirement.md)

## <a name="use-retention-policies-and-retention-labels-instead-of-older-features"></a><span data-ttu-id="344c1-432">以前の機能の代わりにアイテム保持ポリシーと保持ラベルを使用する</span><span class="sxs-lookup"><span data-stu-id="344c1-432">Use retention policies and retention labels instead of older features</span></span>

<span data-ttu-id="344c1-433">情報ガバナンスを目的として、Microsoft 365 のコンテンツをプロアクティブに保持または削除する必要がある場合は、次に示す以前の機能の代わりにアイテム保持ポリシーと保持ラベルを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="344c1-433">If you need to proactively retain or delete content in Microsoft 365 for information governance, we recommend that you use retention policies and retention labels instead of the following older features.</span></span>

<span data-ttu-id="344c1-434">これらの以前の機能を現在使用している場合、それらもアイテム保持ポリシーおよび保持ラベルと並行して機能し続けます。</span><span class="sxs-lookup"><span data-stu-id="344c1-434">If you currently use these older features, they will continue to work side-by-side with retention policies and retention labels.</span></span> <span data-ttu-id="344c1-435">ただし、今後はアイテム保持ポリシーと保持ラベルを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="344c1-435">However, we recommend that going forward, you use retention policies and retention labels instead.</span></span> <span data-ttu-id="344c1-436">それらは、Microsoft 365 全体でコンテンツの保持と削除の両方を集中管理する単一のメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="344c1-436">They provide you with a single mechanism to centrally manage both retention and deletion of content across Microsoft 365.</span></span>

<span data-ttu-id="344c1-437">**Exchange Online の古い機能:**</span><span class="sxs-lookup"><span data-stu-id="344c1-437">**Older features from Exchange Online:**</span></span>

- <span data-ttu-id="344c1-438">[メッセージング レコード管理 (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) とも呼ばれる、[保持タグおよびアイテム保持ポリシー](https://go.microsoft.com/fwlink/?linkid=846125) (削除のみ)</span><span class="sxs-lookup"><span data-stu-id="344c1-438">[Retention tags and retention policies](https://go.microsoft.com/fwlink/?linkid=846125), also known as [messaging records management (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (deletion only)</span></span>

<span data-ttu-id="344c1-439">**SharePoint と OneDrive の古い機能:**</span><span class="sxs-lookup"><span data-stu-id="344c1-439">**Older features from SharePoint and OneDrive:**</span></span>

- <span data-ttu-id="344c1-440">[ドキュメント削除ポリシーの概要](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff) (削除のみ)</span><span class="sxs-lookup"><span data-stu-id="344c1-440">[Document deletion policies](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff) (deletion only)</span></span>
    
- <span data-ttu-id="344c1-441">[インプレース レコード管理の構成](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (保持のみ)</span><span class="sxs-lookup"><span data-stu-id="344c1-441">[Configuring in place records management](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (retention only)</span></span> 
    
- <span data-ttu-id="344c1-442">[サイトのクローズと削除のポリシーを使用する](https://support.microsoft.com/ja-JP/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (削除のみ)</span><span class="sxs-lookup"><span data-stu-id="344c1-442">[Use policies for site closure and deletion](https://support.microsoft.com/ja-JP/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (deletion only)</span></span> 
    
- <span data-ttu-id="344c1-443">[情報管理ポリシー](intro-to-info-mgmt-policies.md) (削除のみ)</span><span class="sxs-lookup"><span data-stu-id="344c1-443">[Information management policies](intro-to-info-mgmt-policies.md) (deletion only)</span></span>
     
<span data-ttu-id="344c1-444">コンテンツ タイプ ポリシーまたは情報管理ポリシーの SharePoint サイトを構成して、リストまたはライブラリのコンテンツを保持している場合は、前者のポリシーは無視され、保持ポリシーが有効になります。</span><span class="sxs-lookup"><span data-stu-id="344c1-444">If you have configured SharePoint sites for content type policies or information management policies to retain content for a list or library, those policies are ignored while a retention policy is in effect.</span></span> 

## <a name="related-information"></a><span data-ttu-id="344c1-445">関連情報</span><span class="sxs-lookup"><span data-stu-id="344c1-445">Related information</span></span>

- [<span data-ttu-id="344c1-446">SharePoint Online の制限</span><span class="sxs-lookup"><span data-stu-id="344c1-446">SharePoint Online Limits</span></span>](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [<span data-ttu-id="344c1-447">Microsoft Teams の制限事項と仕様</span><span class="sxs-lookup"><span data-stu-id="344c1-447">Limits and specifications for Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) 
- [<span data-ttu-id="344c1-448">情報ガバナンスおよびレコード管理の規制要件を満たすために役立つリソース</span><span class="sxs-lookup"><span data-stu-id="344c1-448">Resources to help you meet regulatory requirements for information governance and records management</span></span>](retention-regulatory-requirements.md)

## <a name="next-steps"></a><span data-ttu-id="344c1-449">次の手順</span><span class="sxs-lookup"><span data-stu-id="344c1-449">Next steps</span></span>

<span data-ttu-id="344c1-450">アイテム保持ポリシーを作成する準備ができている場合は、「[アイテム保持ポリシーを作成して構成する](create-retention-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="344c1-450">If you are ready to create retention policies, see [Create and configure retention policies](create-retention-policies.md).</span></span>

<span data-ttu-id="344c1-451">保持ラベルを作成して適用するには:</span><span class="sxs-lookup"><span data-stu-id="344c1-451">To create and apply retention labels:</span></span>
- [<span data-ttu-id="344c1-452">アイテム保持ラベルを作成してアプリに適用する</span><span class="sxs-lookup"><span data-stu-id="344c1-452">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="344c1-453">保持ラベルをコンテンツに自動的に適用する</span><span class="sxs-lookup"><span data-stu-id="344c1-453">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

