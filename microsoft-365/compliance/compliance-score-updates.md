---
title: Microsoft コンプライアンススコアの更新
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
description: Microsoft コンプライアンススコア (プレビュー) の今後の更新プログラムの詳細については、M365 コンプライアンスセンターの機能の1つで、リスク評価を簡略化および自動化できます。
ms.openlocfilehash: c46b70d0762a805e4ecfc83b70173c56d21a3933
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857782"
---
# <a name="microsoft-compliance-score-preview-updates"></a><span data-ttu-id="f7a44-103">Microsoft コンプライアンススコア (プレビュー) の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="f7a44-103">Microsoft Compliance Score (Preview) updates</span></span>

 <span data-ttu-id="f7a44-104">この記事では、 [Microsoft コンプライアンススコア](compliance-score.md)および[microsoft コンプライアンスマネージャー](compliance-manager-overview.md)の今後の更新プログラムの詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="f7a44-104">This article provides details about future updates to [Microsoft Compliance Score](compliance-score.md) and [Microsoft Compliance Manager](compliance-manager-overview.md).</span></span> <span data-ttu-id="f7a44-105">[リレーションシップ](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager)の詳細については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7a44-105">Learn more about their [relationship](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager).</span></span>

## <a name="improved-template-creation-and-update-processes"></a><span data-ttu-id="f7a44-106">テンプレートの作成および更新プロセスの向上</span><span class="sxs-lookup"><span data-stu-id="f7a44-106">Improved template creation and update processes</span></span>

<span data-ttu-id="f7a44-107">評価用にテンプレートをインポート、エクスポート、変更するプロセスを簡素化しています。</span><span class="sxs-lookup"><span data-stu-id="f7a44-107">We're simplifying the process for importing, exporting, and modifying templates for assessments.</span></span> <span data-ttu-id="f7a44-108">新しい操作性により、独自の評価をコンプライアンススコアにして、更新を維持することが容易になります。</span><span class="sxs-lookup"><span data-stu-id="f7a44-108">The new experience will make it easier for you to bring your own assessments into Compliance Score and keep them updated.</span></span>

### <a name="the-current-process"></a><span data-ttu-id="f7a44-109">現在のプロセス</span><span class="sxs-lookup"><span data-stu-id="f7a44-109">The current process</span></span>

<span data-ttu-id="f7a44-110">コンプライアンスマネージャーでテンプレートを作成する方法は2つあります。</span><span class="sxs-lookup"><span data-stu-id="f7a44-110">There are two ways to create a template in Compliance Manager.</span></span> <span data-ttu-id="f7a44-111">既存のテンプレートをコピーしたり、Excel スプレッドシートからテンプレートデータを新しいテンプレートにインポートしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="f7a44-111">You can copy an existing template, or you can import template data from an Excel spreadsheet into a new template.</span></span> <span data-ttu-id="f7a44-112">[**テンプレート**] ページで、[ **+ テンプレートの追加**] を選択して、名前を入力し、ディメンションを選択し、Excel ファイルを特定の形式とスキーマでアップロードすることによって、新しいテンプレートを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7a44-112">From your **Templates** page, you select **+ Add template** to create a brand new template by entering a name, selecting dimensions, and uploading an Excel file with a specific format and schema.</span></span> <span data-ttu-id="f7a44-113">または、次の図に示すように、[**既存のテンプレートからコピー**する] ボックスをオンにし、コピーするテンプレートを選択して、ディメンションを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="f7a44-113">Or you can check the **Copy from an existing template** box, select a template to copy, and verify dimensions, as shown in the image below.</span></span> <span data-ttu-id="f7a44-114">テンプレートをカスタマイズするには、テンプレートの作成後に [**カスタムコントロールの追加**] を選択することによって、[複数の手順から成るプロセス](working-with-compliance-manager.md#templates)が必要になります。</span><span class="sxs-lookup"><span data-stu-id="f7a44-114">Customizing your template requires a [multi-step process](working-with-compliance-manager.md#templates) that begins by selecting **Add custom control** after creating your template.</span></span>

<span data-ttu-id="f7a44-115">![コンプライアンススコア-ダッシュボード](../media/compliance-score-template-update-old.png "現在のテンプレートコピープロセス")</span><span class="sxs-lookup"><span data-stu-id="f7a44-115">![Compliance Score - dashboard](../media/compliance-score-template-update-old.png "Current template copy process")</span></span>

### <a name="whats-changing"></a><span data-ttu-id="f7a44-116">変更点</span><span class="sxs-lookup"><span data-stu-id="f7a44-116">What's changing</span></span>

<span data-ttu-id="f7a44-117">新しいテンプレートを簡単に作成できるようになっています。</span><span class="sxs-lookup"><span data-stu-id="f7a44-117">We're making it easier for you to create new templates.</span></span> <span data-ttu-id="f7a44-118">ワンステップの**拡張**処理では、自分のアクションとコントロールを含むスプレッドシートを既存の Microsoft テンプレートに追加して、独自のカスタマイズされたバージョンを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f7a44-118">In a one-step **extension** process, you can add a spreadsheet with your actions and controls to an existing Microsoft template to make your own customized version.</span></span> <span data-ttu-id="f7a44-119">下の図に示されているように、**テンプレート**のポップアップウィンドウで、[**グローバルテンプレートから拡張機能を作成**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f7a44-119">On the **Template** flyout pane, select the **Create extension from global template** checkbox, as shown in the image below.</span></span> <span data-ttu-id="f7a44-120">次に、現在よりも複雑な Excel の新しい形式を使用して、カスタマイズを追加します。</span><span class="sxs-lookup"><span data-stu-id="f7a44-120">You'll then add customizations using a new Excel format that is less complex than the current one.</span></span> <span data-ttu-id="f7a44-121">この新しいプロセスは、**既存のテンプレートから**現在のコピーを置き換えて、**カスタムコントロール**関数を追加します。</span><span class="sxs-lookup"><span data-stu-id="f7a44-121">This new process replaces the current **Copy from an existing template** and **Add custom control** functions.</span></span>

<span data-ttu-id="f7a44-122">以下に示すバージョン管理プロセスによって元の評価が更新されるたびに、カスタマイズされた評価はそれらの更新を継承し、カスタムコントロールを保持します。</span><span class="sxs-lookup"><span data-stu-id="f7a44-122">Each time the original assessment is updated through the versioning process outlined below, your customized assessment will inherit those updates and keep your custom controls.</span></span>

<span data-ttu-id="f7a44-123">また、独自の既存のテンプレートを変更することも簡単になりました。</span><span class="sxs-lookup"><span data-stu-id="f7a44-123">We're also making it easier to modify your own existing templates.</span></span> <span data-ttu-id="f7a44-124">テンプレートをエクスポートし、同じブックで変更を加えてから、編集内容を保存してインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="f7a44-124">You can export your template, make changes in the same workbook, then import it with your edits saved.</span></span>

<span data-ttu-id="f7a44-125">![コンプライアンススコア-ダッシュボード](../media/compliance-score-template-update-new.png "新しいテンプレートの作成プロセス")</span><span class="sxs-lookup"><span data-stu-id="f7a44-125">![Compliance Score - dashboard](../media/compliance-score-template-update-new.png "New template creation process")</span></span>

## <a name="versioning-notice-and-control"></a><span data-ttu-id="f7a44-126">バージョン管理の通知と制御</span><span class="sxs-lookup"><span data-stu-id="f7a44-126">Versioning notice and control</span></span>

<span data-ttu-id="f7a44-127">組織は、コンプライアンススコアとコンプライアンスマネージャーの次のリリースで更新された評価を受け取って、認定および規制の更新に役立てます。</span><span class="sxs-lookup"><span data-stu-id="f7a44-127">Your organization will receive updated assessments in the next release of Compliance Score and Compliance Manager to help you align with certification and regulation updates.</span></span>

<span data-ttu-id="f7a44-128">今後は、評価のテンプレートまたは改善アクションの更新が可能になるたびに、更新の準備が整ったことを通知する警告アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f7a44-128">Going forward, whenever an update is available for an assessment's template or an improvement action, an alert icon notifies you that an update is ready.</span></span> <span data-ttu-id="f7a44-129">このアイコンをクリックすると、更新プログラムについて説明するポップアップウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f7a44-129">When you click on that icon, a pop-up window explains the update and prompts you to accept.</span></span> <span data-ttu-id="f7a44-130">次に、評価のバージョン管理警告の例を示します。</span><span class="sxs-lookup"><span data-stu-id="f7a44-130">Below is an example of the versioning alert for an assessment:</span></span>

<span data-ttu-id="f7a44-131">![コンプライアンススコア-バージョン管理警告](../media/compliance-score-assessment-version.png "評価バージョン更新通知")</span><span class="sxs-lookup"><span data-stu-id="f7a44-131">![Compliance Score - versioning alert](../media/compliance-score-assessment-version.png "Assessment version update alert")</span></span>

<span data-ttu-id="f7a44-132">通知アイコンを選択すると、更新プログラムについて説明するフライアウトウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f7a44-132">Selecting the alert icon reveals a flyout pane explaining the update and prompting you to accept:</span></span>

<span data-ttu-id="f7a44-133">![コンプライアンススコア-バージョン管理のポップアップ](../media/compliance-score-assessment-version-accept.png "評価の更新の確認ウィンドウ")</span><span class="sxs-lookup"><span data-stu-id="f7a44-133">![Compliance Score - versioning flyout](../media/compliance-score-assessment-version-accept.png "Assessment update confirmation pane")</span></span>

## <a name="common-actions-will-synch-status-across-groups"></a><span data-ttu-id="f7a44-134">共通のアクションにより、グループ間で状態が同期されます。</span><span class="sxs-lookup"><span data-stu-id="f7a44-134">Common actions will synch status across groups</span></span>

<span data-ttu-id="f7a44-135">組織に複数の評価グループが含まれている場合、**技術的**な操作 (つまり、組織全体に影響を与えるアクション) の動作が変わります。</span><span class="sxs-lookup"><span data-stu-id="f7a44-135">If your organization has multiple groups of assessments, the behavior of **Technical** actions (that is, actions affecting your entire organization) will change.</span></span> <span data-ttu-id="f7a44-136">グループ間で重複するアクションは、1つのアクションにまとめられます。</span><span class="sxs-lookup"><span data-stu-id="f7a44-136">Any duplicate actions across groups will be combined into one single action.</span></span> <span data-ttu-id="f7a44-137">この1つのアクションには、複製されたすべてのメモと証拠が重複バージョンから含まれます。</span><span class="sxs-lookup"><span data-stu-id="f7a44-137">That single action will contain all uploaded notes and evidence from the duplicate versions.</span></span> <span data-ttu-id="f7a44-138">この変更により、技術的なアクションは同じグループに属しているときと同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="f7a44-138">With this change, technical actions will behave as they currently do when they belong to the same group.</span></span> <span data-ttu-id="f7a44-139">あるグループまたは評価のアクションに加えられた変更は、すべてのインスタンスに反映されるようになります。</span><span class="sxs-lookup"><span data-stu-id="f7a44-139">Any change made to the action in one group or assessment will now be reflected in all instances.</span></span> <span data-ttu-id="f7a44-140"> *\*実装の状態*\*、*\*実装 Dat*\*、*\*テストの状態*\*、およびテストの*\*日付** は、最新の更新プログラムを反映しています。</span><span class="sxs-lookup"><span data-stu-id="f7a44-140">The **Implementation Status**, **Implementation Dat**, **Test Status**, and **Test Date** will reflect the most recent updates.</span></span>

## <a name="language-support"></a><span data-ttu-id="f7a44-141">言語サポート</span><span class="sxs-lookup"><span data-stu-id="f7a44-141">Language support</span></span>

<span data-ttu-id="f7a44-142">コンプライアンススコアは、英語 (簡体字)、中国語 (繁体字)、フランス語、ドイツ語、イタリア語、日本語、韓国語、ポルトガル語 (ブラジル)、ロシア語、スペイン語に加えて、次の言語で利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f7a44-142">Compliance Score will now be available in the following languages in addition to English: Chinese (Simplified), Chinese (Traditional), French, German, Italian, Japanese, Korean, Portuguese (Brazil), Russian, and Spanish.</span></span>
