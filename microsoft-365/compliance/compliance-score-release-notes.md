---
title: Microsoft コンプライアンススコアリリースノート
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
description: Microsoft コンプライアンススコア (プレビュー) のリリースノートと既知の問題。 M365 コンプライアンスセンターの機能で、リスク評価を簡素化および自動化します。
ms.openlocfilehash: 192519e323f9d23420f82a603979b50f4581ac4f
ms.sourcegitcommit: e2ed110c4c3a8434f9fcc9d610069bc77bc39220
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "38686838"
---
# <a name="microsoft-compliance-score-release-notes-preview"></a><span data-ttu-id="bc030-103">Microsoft コンプライアンススコアリリースノート (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="bc030-103">Microsoft Compliance Score release notes (Preview)</span></span>

<span data-ttu-id="bc030-104">Microsoft コンプライアンススコアの公開プレビューでは、今後の機能と更新プログラムにいち早くアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="bc030-104">The public preview of Microsoft Compliance Score provides you with early access to upcoming functionality and updates.</span></span>

<span data-ttu-id="bc030-105">コンプライアンススコアは、 [Microsoft 365 コンプライアンスセンター](microsoft-365-compliance-center.md)の新機能の1つで、リスクベースのスコアを計算し、コンプライアンスリスクを軽減するために推奨される処置を完了するための進行状況を測定します。</span><span class="sxs-lookup"><span data-stu-id="bc030-105">Compliance Score is a new feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) that calculates a risk-based score, measuring your progress towards completing recommended actions that help reduce compliance risks.</span></span>

## <a name="compliance-score-and-compliance-manager-relationship"></a><span data-ttu-id="bc030-106">コンプライアンススコアとコンプライアンスマネージャーの関係</span><span class="sxs-lookup"><span data-stu-id="bc030-106">Compliance Score and Compliance Manager relationship</span></span>

<span data-ttu-id="bc030-107">コンプライアンスマネージャーで処理されるコンプライアンス機能の多くは、コンプライアンススコアで実行できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="bc030-107">Many of the compliance functions handled in Compliance Manager can now be done in Compliance Score.</span></span> <span data-ttu-id="bc030-108">ただし、一部の機能はコンプライアンスマネージャーにのみ存在し、コンプライアンスマネージャーの以前の機能の一部はパブリックプレビュー期間中に変更されます。</span><span class="sxs-lookup"><span data-stu-id="bc030-108">However some functionality still resides only in Compliance Manager, and some previous functionality in Compliance Manager is altered during the public preview period.</span></span> 

<span data-ttu-id="bc030-109">パブリックプレビュー中にコンプライアンススコアとコンプライアンスマネージャーを操作するときは、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="bc030-109">Keep these points in mind as you work with Compliance Score and Compliance Manager during public preview:</span></span>

- <span data-ttu-id="bc030-110">**評価の管理**: ユーザーは、コンプライアンススコアで評価とそのステータスの詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="bc030-110">**Managing assessments**: users can view assessments and their status details in Compliance Score.</span></span> <span data-ttu-id="bc030-111">ただし、コンプライアンスマネージャー ([表示手順](working-with-compliance-manager.md#assessments)) では評価管理タスクのみを実行でき、タスクは次のように制限されています。</span><span class="sxs-lookup"><span data-stu-id="bc030-111">However users can only perform assessment management tasks in Compliance Manager ([view instructions](working-with-compliance-manager.md#assessments)), and tasks and are limited to the following:</span></span>
    - <span data-ttu-id="bc030-112">新しい評価をアップロードするが、既存の評価を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="bc030-112">Upload new assessments, but not modify existing assessments.</span></span> <span data-ttu-id="bc030-113">既存の評価を変更する必要がある場合は、新しいテンプレートをアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc030-113">If you need to modify an existing assessment, you will need to upload a new template.</span></span>
    - <span data-ttu-id="bc030-114">評価をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="bc030-114">Export assessments</span></span>
    - <span data-ttu-id="bc030-115">アーカイブ評価</span><span class="sxs-lookup"><span data-stu-id="bc030-115">Archive assessments</span></span>
    - <span data-ttu-id="bc030-116">アーカイブされた評価の表示</span><span class="sxs-lookup"><span data-stu-id="bc030-116">View archived assessments</span></span>
 - <span data-ttu-id="bc030-117">**評価用テンプレートを作成する**:</span><span class="sxs-lookup"><span data-stu-id="bc030-117">**Creating templates for assessments**:</span></span> 
   - <span data-ttu-id="bc030-118">ユーザーが新しいテンプレートを作成し、既存のテンプレートをエクスポートするには、コンプライアンスマネージャーに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc030-118">Users must go to Compliance Manager to create new templates and export existing templates.</span></span> 
   - <span data-ttu-id="bc030-119">既存のテンプレートをカスタマイズすることはできません。</span><span class="sxs-lookup"><span data-stu-id="bc030-119">Existing templates cannot be customized.</span></span> <span data-ttu-id="bc030-120">[コンプライアンスマネージャーでテンプレートを管理](working-with-compliance-manager.md#templates)する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bc030-120">Read instructions for [managing templates in Compliance Manager](working-with-compliance-manager.md#templates).</span></span>
   - <span data-ttu-id="bc030-121">テンプレートを作成する場合は、[コンプライアンススコア] にテンプレートが表示されるように、**製品**と**証明書**の両方のディメンションを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc030-121">When creating a template, you must include Dimensions for both **Product** and **Certification** to ensure your template displays in Compliance Score.</span></span>
 - <span data-ttu-id="bc030-122">**権限の設定**: コンプライアンスマネージャーで事前にアクセス許可が付与されていないコンプライアンススコアのユーザーには、Microsoft 365 コンプライアンスセンターでアクセス許可を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc030-122">**Setting permissions**: Compliance Score users who were not previously granted permissions in Compliance Manager must have their permissions set in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="bc030-123">コンプライアンスマネージャーの役割が以前に設定されていたユーザーは、コンプライアンススコアで作業するときに同じアクセスレベルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bc030-123">Users whose roles were previously set in Compliance Manager can use that same level of access when working in Compliance Score.</span></span>
- <span data-ttu-id="bc030-124">**データの転送**: コンプライアンスマネージャーに含まれるデータを持つ組織は、コンプライアンススコアのデータを表示します。また、その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="bc030-124">**Transfer of data**: organizations with data residing in Compliance Manger will see that data in Compliance Score, and vice-versa.</span></span>
- <span data-ttu-id="bc030-125">コンプライアンス**スコアからコンプライアンスマネージャーへのサインイン**: ユーザーがコンプライアンススコアにサインインしており、コンプライアンスマネージャーにアクセスするためのリンクを選択した場合、ユーザーは再度サインインする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="bc030-125">**Signing in to Compliance Manager from Compliance Score**: if a user is signed in to Compliance Score and selects a link to go to Compliance Manager, the user will not have to sign in again.</span></span> <span data-ttu-id="bc030-126">リンクをクリックすると、ブラウザーで新しいタブが開き、ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc030-126">After clicking the link, a new tab opens in your browser featuring a dialogue box.</span></span> <span data-ttu-id="bc030-127">上部のセクションに、「既に Microsoft cloud services のお客様である」というヘッダーがあります。</span><span class="sxs-lookup"><span data-stu-id="bc030-127">In the top section with the header, “Already a Microsoft cloud services customer?</span></span> <span data-ttu-id="bc030-128">アカウントにサインインし、[**サインイン**] ボタンを選択して、コンプライアンスマネージャーに自動的にサインインします。</span><span class="sxs-lookup"><span data-stu-id="bc030-128">Sign in to your account,” select the **Sign In** button to automatically sign in to Compliance Manager.</span></span>

## <a name="known-issues-in-compliance-score-preview"></a><span data-ttu-id="bc030-129">コンプライアンススコアの既知の問題 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="bc030-129">Known issues in Compliance Score (Preview)</span></span>

<span data-ttu-id="bc030-130">次のセクションでは、コンプライアンススコアの今後のリリースで解決される既知の問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="bc030-130">The following sections cover known issues to be resolved in upcoming releases of Compliance Score.</span></span>

### <a name="launch-now-links-in-certain-improvement-actions"></a><span data-ttu-id="bc030-131">特定の改善アクションの [今すぐ開始リンク」リンク</span><span class="sxs-lookup"><span data-stu-id="bc030-131">Launch Now links in certain improvement actions</span></span>

<span data-ttu-id="bc030-132">一部の改善アクションでは、実装手順の下に表示される [**今すぐ起動**] リンクを選択すると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="bc030-132">In certain improvement actions, selecting the **Launch Now** link that appears underneath the implementation instructions gives an error.</span></span> <span data-ttu-id="bc030-133">SharePoint 管理センターである適切な宛先にアクセスするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bc030-133">To access the proper destination, which is the the SharePoint admin center, follow these steps:</span></span>

1. <span data-ttu-id="bc030-134">[Microsoft 365 管理センター](https://admin.microsoft.com)に移動します。</span><span class="sxs-lookup"><span data-stu-id="bc030-134">Go to the [Microsoft 365 Admin Center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="bc030-135">左側のナビゲーションメニューで、[**すべて表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bc030-135">On the left navigation menu, select **Show all**.</span></span>
3. <span data-ttu-id="bc030-136">[**管理センター] で、** [ **SharePoint**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bc030-136">Under **Admin centers,** select **SharePoint**.</span></span>

<span data-ttu-id="bc030-137">影響を受ける改善アクションは、以下のとおりです。これらはすべて、[**保護情報**] カテゴリにあります。</span><span class="sxs-lookup"><span data-stu-id="bc030-137">Below are the affected improvement actions, which all reside in the **Protect information** category:</span></span>
  - <span data-ttu-id="bc030-138">SharePoint ライブラリに暗号化を適用する</span><span class="sxs-lookup"><span data-stu-id="bc030-138">Apply encryption to SharePoint Library</span></span>
  - <span data-ttu-id="bc030-139">SharePoint Online でデータを分類する</span><span class="sxs-lookup"><span data-stu-id="bc030-139">Classify Data in SharePoint Online</span></span>
  - <span data-ttu-id="bc030-140">外部共有リンクを期限切れになるように構成する</span><span class="sxs-lookup"><span data-stu-id="bc030-140">Configure External Sharing Links to Expire</span></span>
  - <span data-ttu-id="bc030-141">ドキュメントライブラリのバージョン管理を有効にする</span><span class="sxs-lookup"><span data-stu-id="bc030-141">Enable Versioning for Document Libraries</span></span>

### <a name="long-load-times-for-non-admin-users"></a><span data-ttu-id="bc030-142">管理者以外のユーザーの読み込み時間が長くなる</span><span class="sxs-lookup"><span data-stu-id="bc030-142">Long load times for non-admin users</span></span>
<span data-ttu-id="bc030-143">コンプライアンススコア管理者の役割以外の役割を持つユーザーは、サインインしようとすると長時間の読み込み時間が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="bc030-143">Compliance Score users who hold roles other than an admin role may experience long load times when trying to a sign in.</span></span> <span data-ttu-id="bc030-144">ブラウザーを更新すると、この問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="bc030-144">Refreshing your browser will resolve this issue.</span></span> <span data-ttu-id="bc030-145">(詳細については、「[コンプライアンススコアの役割](compliance-score-setup.md#set-user-permissions-and-assign-roles)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="bc030-145">(Learn more about [Compliance Score roles](compliance-score-setup.md#set-user-permissions-and-assign-roles).)</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="bc030-146">サポート対象ブラウザー</span><span class="sxs-lookup"><span data-stu-id="bc030-146">Supported browsers</span></span>

- <span data-ttu-id="bc030-147">Microsoft Edge、Chrome、および Safari の最新バージョンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bc030-147">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="bc030-148">ブラウザーが更新されるまで、更新されたデータが表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="bc030-148">There may be instances where updated data does not appear until your browser is refreshed.</span></span>
- <span data-ttu-id="bc030-149">Microsoft Edge のプレビューバージョンはサポートされていませんが、既知の問題はありません。</span><span class="sxs-lookup"><span data-stu-id="bc030-149">The preview version of Microsoft Edge is not supported but has no known issues.</span></span>
- <span data-ttu-id="bc030-150">Internet Explorer はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="bc030-150">Internet Explorer is not supported.</span></span>
 
### <a name="language-support"></a><span data-ttu-id="bc030-151">言語サポート</span><span class="sxs-lookup"><span data-stu-id="bc030-151">Language support</span></span>

- <span data-ttu-id="bc030-152">コンプライアンススコアは米国英語でのみ利用可能です。</span><span class="sxs-lookup"><span data-stu-id="bc030-152">Compliance Score is only available in U.S. English.</span></span>