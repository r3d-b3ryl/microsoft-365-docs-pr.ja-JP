---
title: Microsoft コンプライアンスマネージャーリリースノート
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft コンプライアンスマネージャーは、Microsoft Service Trust Portal の無料のワークフローベースのリスク評価ツールです。 コンプライアンスマネージャーを使用すると、Microsoft クラウドサービスに関連する規制コンプライアンスアクティビティを追跡、割り当て、検証することができます。
ms.openlocfilehash: 3fc16e92e912676d7aedc861ffe8306d68388c95
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42078654"
---
# <a name="release-notes-for-compliance-manager-preview"></a><span data-ttu-id="cfddb-104">コンプライアンスマネージャーのリリースノート (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="cfddb-104">Release Notes for Compliance Manager (Preview)</span></span>

<span data-ttu-id="cfddb-105">コンプライアンスマネージャーの公開プレビューでは、今後の機能と更新プログラムに早期にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="cfddb-105">The public preview of Compliance Manager provides you with early access to upcoming functionality and updates.</span></span>

<span data-ttu-id="cfddb-106">[Service Trust Portal](https://servicetrust.microsoft.com)の更新された[コンプライアンスマネージャー](https://servicetrust.microsoft.com/ComplianceManager)ツールを使用して、Microsoft クラウドサービスに関連する規制コンプライアンスアクティビティを追跡、割り当て、検証することができます。</span><span class="sxs-lookup"><span data-stu-id="cfddb-106">You can use the updated [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) tool on the [Service Trust Portal](https://servicetrust.microsoft.com) to track, assign, and verify regulatory compliance activities related to Microsoft cloud services.</span></span>

## <a name="whats-new-in-compliance-manager-preview"></a><span data-ttu-id="cfddb-107">コンプライアンスマネージャーの新機能 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="cfddb-107">What’s new in Compliance Manager (Preview)</span></span>

- <span data-ttu-id="cfddb-108">**コンプライアンスマネージャーへの役割ベースのアクセス:** 既定の**ゲストアクセス**役割が削除されました。</span><span class="sxs-lookup"><span data-stu-id="cfddb-108">**Role-based access to Compliance Manager:** The default **Guest access** role has been removed.</span></span> <span data-ttu-id="cfddb-109">ユーザーがコンプライアンスマネージャーにアクセスするためには、グローバル管理者が[各ユーザーにアクセス許可を割り当てる](compliance-manager-overview.md#permissions)必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfddb-109">In order for a user to access Compliance Manager, the global admin must [assign each user a permission](compliance-manager-overview.md#permissions).</span></span>

- <span data-ttu-id="cfddb-110">**更新されたコンプライアンススコア**: コンプライアンススコアに、Microsoft が管理するアクションのスコアが含まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="cfddb-110">**Updated Compliance Score**: Compliance Score now includes scores for Microsoft-managed actions.</span></span> <span data-ttu-id="cfddb-111">結果としてスコアが増加します。</span><span class="sxs-lookup"><span data-stu-id="cfddb-111">Your score will increase as a result.</span></span>

- <span data-ttu-id="cfddb-112">**アクションアイテム:** アクションアイテムは現在、個別のアイテムで、多くの Microsoft Secure Score Graph API からのテレメトリコレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cfddb-112">**Actions Items:** Action Items are now individual items and many include telemetry collection from the Microsoft Secure Score Graph API.</span></span> <span data-ttu-id="cfddb-113">可能であれば、技術的なアクションの推奨事項が Office 365 サービスの該当する構成ページへのリンクを持つようになります。</span><span class="sxs-lookup"><span data-stu-id="cfddb-113">Where possible, technical action recommendations now have links to the applicable configuration page in the Office 365 service.</span></span>

- <span data-ttu-id="cfddb-114">**テナント管理:** コンプライアンスマネージャー (プレビュー) で新しいデータ要素を管理するための新しいインターフェイス:</span><span class="sxs-lookup"><span data-stu-id="cfddb-114">**Tenant Management:** New interface for managing new data elements in Compliance Manager (Preview):</span></span>
    - <span data-ttu-id="cfddb-115">**次元:** テンプレート、評価、およびアクションアイテムのメタデータを表示、追加、およびカスタマイズして、フィルターのカスタムピボットを作成できます。</span><span class="sxs-lookup"><span data-stu-id="cfddb-115">**Dimensions:** View, add and customize metadata for Templates, Assessments, and Action Items that allow you to create custom pivots for filters.</span></span>
    - <span data-ttu-id="cfddb-116">**所有者:** 各アクションアイテムの所有者を指定します。</span><span class="sxs-lookup"><span data-stu-id="cfddb-116">**Owners:** Specify an owner for each Action Item.</span></span>
    - <span data-ttu-id="cfddb-117">**お客様のアクション:** コンプライアンスマネージャー (プレビュー) に含まれるアクションアイテムの完全なリストを管理し、セキュリティで保護されたスコアと統合されたアクションアイテムのセキュリティで保護されたスコア監視を有効/無効にします。</span><span class="sxs-lookup"><span data-stu-id="cfddb-117">**Customer Actions:** Manage the complete list of Actions Items included in Compliance Manager (Preview) and enable/disable Secure Score monitoring for Action Items integrated with Secure Score.</span></span>

## <a name="known-issues-in-compliance-manager-preview"></a><span data-ttu-id="cfddb-118">コンプライアンスマネージャーの既知の問題 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="cfddb-118">Known issues in Compliance Manager (Preview)</span></span>

<span data-ttu-id="cfddb-119">次のセクションでは、コンプライアンスマネージャーの今後のリリースで解決される既知の問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="cfddb-119">The following sections cover known issues to be resolved in upcoming releases of Compliance Manager.</span></span>

### <a name="compliance-score"></a><span data-ttu-id="cfddb-120">コンプライアンス スコア</span><span class="sxs-lookup"><span data-stu-id="cfddb-120">Compliance Score</span></span>

- <span data-ttu-id="cfddb-121">**スコープ内にない**とマークされたアクションアイテムの場合、アクションアイテムに割り当てられているスコアは、コンプライアンススコアの計算から除外されません。</span><span class="sxs-lookup"><span data-stu-id="cfddb-121">For Action Items marked as **Not in Scope**, the score assigned to the Action Item isn't excluded from the compliance score calculation.</span></span> <span data-ttu-id="cfddb-122">**スコープにない**アクションアイテムは、コンプライアンススコアを増加しません。</span><span class="sxs-lookup"><span data-stu-id="cfddb-122">Action Items marked **Not in Scope** don't increase your compliance score.</span></span>

### <a name="secure-score"></a><span data-ttu-id="cfddb-123">セキュリティ スコア</span><span class="sxs-lookup"><span data-stu-id="cfddb-123">Secure Score</span></span>

- <span data-ttu-id="cfddb-124">セキュリティで保護されたスコアの結果は、一部の Microsoft 365 および Office 365 サブスクリプションの一部のアクションアイテムでは利用できません。</span><span class="sxs-lookup"><span data-stu-id="cfddb-124">Secure Score results aren't available for some Actions Items in certain Microsoft 365 and Office 365 subscriptions.</span></span> <span data-ttu-id="cfddb-125">このような場合は、セキュリティで保護されたスコアの結果を検出できません**でした**。</span><span class="sxs-lookup"><span data-stu-id="cfddb-125">The Secure Score result is **Could not be detected** in these cases.</span></span>
- <span data-ttu-id="cfddb-126">セキュリティで保護されたスコアの結果が、対応するポリシーおよび完了していないアクションアイテムに対して返されることがあります。</span><span class="sxs-lookup"><span data-stu-id="cfddb-126">Sometimes Secure Score results are returned for corresponding policies and Action Items not completed.</span></span>
- <span data-ttu-id="cfddb-127">新しいテナントの場合、すべてのアクションのセキュリティで保護されたスコアの更新が自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="cfddb-127">For new tenants, Secure Score updates for all actions is automatically turned on.</span></span> <span data-ttu-id="cfddb-128">全体管理者は、セキュリティで保護されたスコア継続的更新スイッチを off に設定して、すべてのアクションの更新をオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="cfddb-128">The global administrator can set the Secure Score continuous update switch to off, which turns off updates for all actions.</span></span>
  - <span data-ttu-id="cfddb-129">**注**: 組織が最初に Microsoft 365 または Office 365 を展開するときは、セキュリティで保護されたスコアがデータを完全に収集してスコアになるまでに約7日かかります。</span><span class="sxs-lookup"><span data-stu-id="cfddb-129">**Note**: when organizations first deploy Microsoft 365 or Office 365, it takes approximately seven days for Secure Score to fully collect data and factor it into your score.</span></span> <span data-ttu-id="cfddb-130">その間、「Secure Score continuous update」スイッチを [**オフ**] に設定し、**実装**するアクションを手動で設定すると、スコアに対する処理がカウントされます。</span><span class="sxs-lookup"><span data-stu-id="cfddb-130">During that time, setting the Secure Score continuous update switch to **Off** and manually setting an action to **implemented** will count that action toward your score.</span></span> <span data-ttu-id="cfddb-131">最初の7日より後に、セキュリティで保護されたスコア継続的更新をオンにすると、それ以降の継続的な監視が有効になります。</span><span class="sxs-lookup"><span data-stu-id="cfddb-131">After the initial seven days, turning Secure Score continuous update back on will enable continuous monitoring from that point forward.</span></span>
- <span data-ttu-id="cfddb-132">セキュリティで保護されたスコアの更新が有効になっている場合、アクションはセキュリティで保護されたスコアでアクティブに監視されますが、アクションのテスト日は監視を反映するように更新されません。</span><span class="sxs-lookup"><span data-stu-id="cfddb-132">When Secure Score updates are turned on, actions are actively monitored by Secure Score, although the action’s test date won't be updated to reflect monitoring.</span></span>
- <span data-ttu-id="cfddb-133">新しい評価が作成されると、スコアは自動的に Microsoft 管理の制御スコアとセキュリティで保護されたスコアの統合を含みます。</span><span class="sxs-lookup"><span data-stu-id="cfddb-133">When new assessments are created, scores automatically include Microsoft-managed control scores and Secure Score integration.</span></span>
- <span data-ttu-id="cfddb-134">セキュリティで保護されたスコア統合でサポートされていないアクションは、手動で実装できます。</span><span class="sxs-lookup"><span data-stu-id="cfddb-134">Any actions that are not supported by Secure Score integration can be manually implemented.</span></span> <span data-ttu-id="cfddb-135">手動による実装では、そのアクションのグループのスコアが考慮されます。</span><span class="sxs-lookup"><span data-stu-id="cfddb-135">A manual implementation will factor into the score for that action's group.</span></span>

### <a name="microsoft-managed-controls"></a><span data-ttu-id="cfddb-136">Microsoft 管理コントロール</span><span class="sxs-lookup"><span data-stu-id="cfddb-136">Microsoft-managed controls</span></span>

- <span data-ttu-id="cfddb-137">Microsoft 管理コントロールのテスト日は、評価に含まれていても UI に表示されません。</span><span class="sxs-lookup"><span data-stu-id="cfddb-137">The test date for Microsoft-managed controls isn't appearing in the UI, even when included in the Assessment.</span></span> <span data-ttu-id="cfddb-138">テスト日付情報を表示するには、評価をエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfddb-138">To see test date information, you must export the Assessment.</span></span>

### <a name="customization"></a><span data-ttu-id="cfddb-139">カスタマイズ</span><span class="sxs-lookup"><span data-stu-id="cfddb-139">Customization</span></span>

- <span data-ttu-id="cfddb-140">カスタムコントロールを追加することで、新しいコントロールを既存のコントロールファミリに追加することはできますが、新しいコントロールファミリを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="cfddb-140">Adding custom Controls enables adding a new control to an existing control family, but it doesn't allow you to add a new Control Family.</span></span>
- <span data-ttu-id="cfddb-141">このリリースでは、アクションアイテムをリンクしたり、アクションアイテムまたはコントロールを評価に追加したりすることはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="cfddb-141">This release doesn't support linking Action Items or adding Actions Items or Controls to an Assessment.</span></span>
- <span data-ttu-id="cfddb-142">カスタムアクションを作成した場合、それを編集または削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="cfddb-142">If you create a custom Action, you can't edit or delete it.</span></span>

### <a name="control-families-not-shown-in-assessments"></a><span data-ttu-id="cfddb-143">評価に表示されていないコントロールファミリ</span><span class="sxs-lookup"><span data-stu-id="cfddb-143">Control Families Not Shown in Assessments</span></span>

- <span data-ttu-id="cfddb-144">テンプレートをインポートすると、そのテンプレートに基づくすべての評価に、テンプレートの一部であるすべてのコントロールファミリが反映されます。</span><span class="sxs-lookup"><span data-stu-id="cfddb-144">When you import a Template, all Assessments based on that Template reflect all Control Families that are part of the Template.</span></span> <span data-ttu-id="cfddb-145">しかし、テンプレートに新しいコントロールファミリを追加した場合、既存の評価には変更が反映されません。</span><span class="sxs-lookup"><span data-stu-id="cfddb-145">But if you add new Control Families to the Template, any existing Assessments won't reflect the changes.</span></span> <span data-ttu-id="cfddb-146">更新されたテンプレートから作成された新しい評価のみが変更を反映しています。</span><span class="sxs-lookup"><span data-stu-id="cfddb-146">Only new Assessments created off the updated Template reflect the changes.</span></span>

### <a name="templates"></a><span data-ttu-id="cfddb-147">テンプレート</span><span class="sxs-lookup"><span data-stu-id="cfddb-147">Templates</span></span>

- <span data-ttu-id="cfddb-148">テンプレートを作成する場合は、[コンプライアンススコア] にテンプレートが表示されるように、**製品**と**証明書**の両方のディメンションを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfddb-148">When creating a template, you must include Dimensions for both **Product** and **Certification** to ensure your template displays in Compliance Score.</span></span>
- <span data-ttu-id="cfddb-149">アーカイブされたテンプレートは編集可能で、編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="cfddb-149">Archived templates are editable and they shouldn't be editable.</span></span>
- <span data-ttu-id="cfddb-150">ロックされたテンプレートは、評価の作成を許可しません。</span><span class="sxs-lookup"><span data-stu-id="cfddb-150">Locked templates allow for Assessment creation when they shouldn't.</span></span> <span data-ttu-id="cfddb-151">テンプレートのロックは、評価の作成に使用されないようにすることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="cfddb-151">Locking a Template is meant to prevent it from being used to create Assessments.</span></span>

### <a name="export"></a><span data-ttu-id="cfddb-152">エクスポート</span><span class="sxs-lookup"><span data-stu-id="cfddb-152">Export</span></span>

- <span data-ttu-id="cfddb-153">テンプレートの状態が [**インポート**済みまたは**保留中の承認**] に設定されている場合、JSON へのテンプレートのエクスポートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="cfddb-153">Template export to JSON fails when the template status is set to **Imported** or **Pending Approval**.</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="cfddb-154">サポート対象ブラウザー</span><span class="sxs-lookup"><span data-stu-id="cfddb-154">Supported browsers</span></span>

- <span data-ttu-id="cfddb-155">Microsoft Edge、Chrome、および Safari の最新バージョンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="cfddb-155">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="cfddb-156">ブラウザーを更新するまで、更新されたデータが表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="cfddb-156">There may be instances where updated data doesn't appear until your browser is refreshed.</span></span>
- <span data-ttu-id="cfddb-157">Microsoft Edge のプレビューバージョンはサポートされていませんが、既知の問題はありません。</span><span class="sxs-lookup"><span data-stu-id="cfddb-157">The preview version of Microsoft Edge isn't supported but has no known issues.</span></span>
- <span data-ttu-id="cfddb-158">Internet Explorer はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="cfddb-158">Internet Explorer isn't supported.</span></span>

### <a name="session-timeout"></a><span data-ttu-id="cfddb-159">セッションのタイムアウト</span><span class="sxs-lookup"><span data-stu-id="cfddb-159">Session timeout</span></span>

- <span data-ttu-id="cfddb-160">セッションがタイムアウトになると、"問題が発生しました" というエラーが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="cfddb-160">When a session times out, a “Something went wrong” error may appear.</span></span> <span data-ttu-id="cfddb-161">解決するには、[[コンプライアンスマネージャー](https://servicetrust.microsoft.com/ComplianceManager) ] に移動して、再度ログインします。</span><span class="sxs-lookup"><span data-stu-id="cfddb-161">To resolve, go to [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) and log in again.</span></span>
 
### <a name="language-support"></a><span data-ttu-id="cfddb-162">言語サポート</span><span class="sxs-lookup"><span data-stu-id="cfddb-162">Language support</span></span>

- <span data-ttu-id="cfddb-163">すべての web ページですべての言語がサポートされるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="cfddb-163">All languages aren't supported for all webpages.</span></span> <span data-ttu-id="cfddb-164">ローカル言語がサポートされていない場合は、英語 (米国) で表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfddb-164">If your local language is unsupported, view in US English.</span></span>
