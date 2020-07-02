---
title: Microsoft コンプライアンススコアリリースノート
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
description: Microsoft コンプライアンススコア (プレビュー) のリリースノートと既知の問題。 M365 コンプライアンスセンターの機能で、リスク評価を簡素化および自動化します。
ms.openlocfilehash: 6678ec03d2cd87a97244acaa55a15483d78dd632
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "45022194"
---
# <a name="microsoft-compliance-score-preview-release-notes"></a><span data-ttu-id="78425-103">Microsoft コンプライアンススコア (プレビュー) リリースノート</span><span class="sxs-lookup"><span data-stu-id="78425-103">Microsoft Compliance Score (preview) release notes</span></span>

<span data-ttu-id="78425-104">**この記事の内容**このページには、 [Microsoft のコンプライアンススコア](compliance-score.md)のパブリックプレビューの**新**機能が表示されます。これにより、新しい機能に早期にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="78425-104">**In this article:** This page shows **what's new** in the public preview of [Microsoft Compliance Score](compliance-score.md), which provides you with early access to new functionality.</span></span>

## <a name="assessment-creation-and-management-functionality"></a><span data-ttu-id="78425-105">評価の作成と管理の機能</span><span class="sxs-lookup"><span data-stu-id="78425-105">Assessment creation and management functionality</span></span>

<span data-ttu-id="78425-106">2020年6月リリースは、コンプライアンススコアでユーザーが評価を作成、削除、および管理するための機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="78425-106">The June 2020 release adds functionality for users to create, delete, and manage their assessments directly in Compliance Score.</span></span> <span data-ttu-id="78425-107">以前は、すべての評価管理はコンプライアンスマネージャーに存在していました。</span><span class="sxs-lookup"><span data-stu-id="78425-107">Previously, all assessment management resided in Compliance Manager.</span></span> <span data-ttu-id="78425-108">コンプライアンススコアで評価を作成または変更すると、更新がコンプライアンスマネージャーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="78425-108">When you create or modify an assessment in Compliance Score, the updates will surface in Compliance Manager.</span></span> <span data-ttu-id="78425-109">同様に、コンプライアンスマネージャーで行われたすべての評価作業は、コンプライアンススコアとして機能します。</span><span class="sxs-lookup"><span data-stu-id="78425-109">Likewise, any assessment work performed in Compliance Manager will surface in Compliance Score.</span></span> <span data-ttu-id="78425-110">[コンプライアンススコアで評価を管理](compliance-score-assessments.md)する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="78425-110">Learn how to [manage assessments in Compliance Score](compliance-score-assessments.md).</span></span> <span data-ttu-id="78425-111">テンプレートの作成と変更はコンプライアンスマネージャーで引き続き管理されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="78425-111">Note that template creation and modification is still managed in Compliance Manager.</span></span>

## <a name="new-templates-for-assessments"></a><span data-ttu-id="78425-112">評価のための新しいテンプレート</span><span class="sxs-lookup"><span data-stu-id="78425-112">New templates for assessments</span></span>

<span data-ttu-id="78425-113">評価のための新しい使用準備テンプレートは、利用可能になるとコンプライアンススコアにリリースされます。</span><span class="sxs-lookup"><span data-stu-id="78425-113">New ready to use templates for assessments are released in Compliance Score as they become available.</span></span> <span data-ttu-id="78425-114">[ここでテンプレートの完全なリスト](compliance-score-templates.md)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="78425-114">Check the [full list of templates here](compliance-score-templates.md).</span></span> <span data-ttu-id="78425-115">最近追加されたもの:</span><span class="sxs-lookup"><span data-stu-id="78425-115">Recently added:</span></span>

- <span data-ttu-id="78425-116">Dubai Information Security Resolution (DGISR)</span><span class="sxs-lookup"><span data-stu-id="78425-116">Dubai Information Security Resolution (DGISR)</span></span>

## <a name="compliance-score-relationship-to-compliance-manager"></a><span data-ttu-id="78425-117">コンプライアンスマネージャーへのコンプライアンススコアの関係</span><span class="sxs-lookup"><span data-stu-id="78425-117">Compliance Score relationship to Compliance Manager</span></span>

<span data-ttu-id="78425-118">コンプライアンスマネージャーで処理される機能の多くは、コンプライアンススコアで実行できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="78425-118">Many of the functions handled in Compliance Manager can now be done in Compliance Score.</span></span> <span data-ttu-id="78425-119">ただし、一部の機能はコンプライアンスマネージャーにまだ存在しています。</span><span class="sxs-lookup"><span data-stu-id="78425-119">However some functions still live in Compliance Manager.</span></span> <span data-ttu-id="78425-120">パブリックプレビュー中にコンプライアンススコアとコンプライアンスマネージャーを操作するときは、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="78425-120">Keep these points in mind as you work with Compliance Score and Compliance Manager during public preview:</span></span>

 - <span data-ttu-id="78425-121">**評価用テンプレートを作成する**:</span><span class="sxs-lookup"><span data-stu-id="78425-121">**Creating templates for assessments**:</span></span> 
   - <span data-ttu-id="78425-122">ユーザーが[新しいテンプレートを作成したり、既存のテンプレートを変更したり](working-with-compliance-manager.md#templates)するには、コンプライアンスマネージャーに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78425-122">Users must go to Compliance Manager to [create new templates and modify existing templates](working-with-compliance-manager.md#templates).</span></span>
   - <span data-ttu-id="78425-123">新しいテンプレートには、**製品**と**証明書**の両方のディメンションを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="78425-123">New templates must include Dimensions for both **Product** and **Certification**.</span></span>
 - <span data-ttu-id="78425-124">**アクセス許可の設定**: コンプライアンスマネージャーのアクセス許可をまだ持っていないユーザーには、Microsoft 365 コンプライアンスセンターでアクセス許可が設定されている必要があります ([詳細につい](compliance-score-setup.md#set-user-permissions-and-assign-roles)ては、「」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="78425-124">**Setting permissions**: Compliance Score users who didn't already have permissions in Compliance Manager need their permissions set in the Microsoft 365 compliance center ([learn more](compliance-score-setup.md#set-user-permissions-and-assign-roles)).</span></span>
- <span data-ttu-id="78425-125">**データの転送**: コンプライアンスマネージャーにデータを持つ組織は、コンプライアンススコアでそのデータを表示するので、同じことが他の方法でも同様です。</span><span class="sxs-lookup"><span data-stu-id="78425-125">**Transfer of data**: organizations with data in Compliance Manager will see that data in Compliance Score, and the same is true the other way around.</span></span>
- <span data-ttu-id="78425-126">コンプライアンス**スコアからコンプライアンスマネージャーへのサインイン**: ユーザーがコンプライアンススコアにサインインしており、コンプライアンスマネージャーにアクセスするためのリンクを選択した場合、ユーザーはもう一度サインインする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="78425-126">**Signing in to Compliance Manager from Compliance Score**: if a user is signed in to Compliance Score and selects a link to go to Compliance Manager, the user won't have to sign in again.</span></span> <span data-ttu-id="78425-127">リンクをクリックすると、ブラウザーで新しいタブが開き、ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="78425-127">After clicking the link, a new tab opens in your browser featuring a dialogue box.</span></span> <span data-ttu-id="78425-128">上部のセクションに、「既に Microsoft cloud services のお客様である」というヘッダーがあります。</span><span class="sxs-lookup"><span data-stu-id="78425-128">In the top section with the header, "Already a Microsoft cloud services customer?</span></span> <span data-ttu-id="78425-129">アカウントにサインインし、[**サインイン**] ボタンを選択して、コンプライアンスマネージャーに自動的にサインインします。</span><span class="sxs-lookup"><span data-stu-id="78425-129">Sign in to your account," select the **Sign In** button to automatically sign in to Compliance Manager.</span></span>

## <a name="known-issues-in-compliance-score-preview"></a><span data-ttu-id="78425-130">コンプライアンススコアの既知の問題 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="78425-130">Known issues in Compliance Score (Preview)</span></span>

<span data-ttu-id="78425-131">次のセクションでは、コンプライアンススコアの今後のリリースで解決される既知の問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="78425-131">The following sections cover known issues to be resolved in upcoming releases of Compliance Score.</span></span>

### <a name="long-load-times-for-non-admin-users"></a><span data-ttu-id="78425-132">管理者以外のユーザーの読み込み時間が長くなる</span><span class="sxs-lookup"><span data-stu-id="78425-132">Long load times for non-admin users</span></span>
<span data-ttu-id="78425-133">コンプライアンススコア管理者の役割以外の役割を持つユーザーは、サインインしようとすると長時間の読み込み時間が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="78425-133">Compliance Score users who hold roles other than an admin role may experience long load times when trying to a sign in.</span></span> <span data-ttu-id="78425-134">ブラウザーを更新すると、この問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="78425-134">Refreshing your browser will resolve this issue.</span></span> <span data-ttu-id="78425-135">[コンプライアンススコアの役割](compliance-score-setup.md#set-user-permissions-and-assign-roles)について説明します。</span><span class="sxs-lookup"><span data-stu-id="78425-135">Learn more about [Compliance Score roles](compliance-score-setup.md#set-user-permissions-and-assign-roles).</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="78425-136">サポート対象ブラウザー</span><span class="sxs-lookup"><span data-stu-id="78425-136">Supported browsers</span></span>

- <span data-ttu-id="78425-137">Microsoft Edge、Chrome、および Safari の最新バージョンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="78425-137">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="78425-138">更新されたデータは、ブラウザーが更新されるまで表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="78425-138">Updated data sometimes doesn't appear until your browser is refreshed.</span></span>
- <span data-ttu-id="78425-139">Internet Explorer はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="78425-139">Internet Explorer is not supported.</span></span>
