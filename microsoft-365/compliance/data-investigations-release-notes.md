---
title: Microsoft 365 のデータ調査用リリースノート (プレビュー)
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
description: この記事では、Microsoft 365 のデータ調査 (プレビュー) ツールの変更点と新機能を含むリリースノートについて説明します。
ms.openlocfilehash: 2a46236d000c62c4ab73f8a47e9c9f661fb17a61
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285413"
---
# <a name="release-notes-for-data-investigations-preview-in-microsoft-365"></a><span data-ttu-id="3f02c-103">Microsoft 365 のデータ調査用リリースノート (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="3f02c-103">Release notes for Data Investigations (preview) in Microsoft 365</span></span>

<span data-ttu-id="3f02c-104">Microsoft 365 の新しいデータ調査 (プレビュー) ツールを使用すると、データ流出インシデントや内部調査など、データに関連するインシデントのトリアージ、調査、および修復を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3f02c-104">You can use the new Data Investigations (preview) tool in Microsoft 365 to triage, investigate, and remediate data-related incidents, such as a data spillage incident or an internal investigation.</span></span> <span data-ttu-id="3f02c-105">データ調査のパブリックプレビューを使用すると、今後予定されている機能と更新プログラムに早期にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3f02c-105">The Public Preview of Data Investigations provides you with early access to the upcoming functionality and updates.</span></span> <span data-ttu-id="3f02c-106">最新の機能にいち早くアクセスするには、セキュリティ & コンプライアンスセンターのデータ調査 (プレビュー) で新しい調査を作成します。</span><span class="sxs-lookup"><span data-stu-id="3f02c-106">To get early access to the newest features, create a new investigation in Data Investigations (preview) in the Security & Compliance Center.</span></span> <span data-ttu-id="3f02c-107">その方法については、「 [Manage a data 流出 incident In Microsoft 365](manage-data-spillage-incidents.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f02c-107">To learn how, see [Manage a data spillage incident in Microsoft 365](manage-data-spillage-incidents.md).</span></span>

## <a name="whats-new"></a><span data-ttu-id="3f02c-108">新機能</span><span class="sxs-lookup"><span data-stu-id="3f02c-108">What's new</span></span> 

- <span data-ttu-id="3f02c-109">**調査-調査** を作成することで、検索とインシデントをグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="3f02c-109">**Investigations** - You can group searches and incidents by creating an investigation.</span></span> <span data-ttu-id="3f02c-110">メンバーを追加または削除することで、調査にアクセスできるユーザーを管理します。</span><span class="sxs-lookup"><span data-stu-id="3f02c-110">Manage who can access the investigation by adding or removing members.</span></span>  <span data-ttu-id="3f02c-111">お気に入りの調査を選択してマークすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3f02c-111">You can also select and mark your favorite investigations.</span></span> <span data-ttu-id="3f02c-112">新しいダッシュボードを使用して、調査内および調査間でのアクティビティを追跡および監視します。</span><span class="sxs-lookup"><span data-stu-id="3f02c-112">Track and monitor activity within and across investigations using new dashboards.</span></span> <span data-ttu-id="3f02c-113">調査を完了したら、それをクローズまたは削除することができます。</span><span class="sxs-lookup"><span data-stu-id="3f02c-113">After you complete your investigation, you can close or delete it.</span></span>

- <span data-ttu-id="3f02c-114">**関心のある** ユーザー–調査に関心のあるユーザーを追加すると、そのユーザーのメールボックス、OneDrive for business アカウント、および Microsoft Teams サイトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f02c-114">**People of interest** – When you add users to investigations as people of interest, you can see their mailbox, OneDrive for Business account, and Microsoft Teams sites.</span></span> <span data-ttu-id="3f02c-115">それらを使用して、調査対象のコンテンツ検索の範囲を作成できます。</span><span class="sxs-lookup"><span data-stu-id="3f02c-115">You can use them to scope your investigative content searches.</span></span> <span data-ttu-id="3f02c-116">関心のある人物をさらに調査するには、Microsoft 365 およびその他の Microsoft サービスの活動に関連する監査レコードを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="3f02c-116">To further investigate a person of interest, you can also view audit records related to their activities in Microsoft 365 and other Microsoft services.</span></span>

- <span data-ttu-id="3f02c-117">**検索** –さまざまな検索条件を使用して組織全体の検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="3f02c-117">**Searches** – Create an organization-wide search using various search conditions.</span></span> <span data-ttu-id="3f02c-118">検索するユーザーまたはサイトがわかっている場合は、それらのユーザーを関心のあるユーザーとして追加したり、検索作成ウィザードでサイトの場所を指定したりできます。</span><span class="sxs-lookup"><span data-stu-id="3f02c-118">If you know users or sites that you want to search, you can do so by adding those users as people of interest or specifying site locations in search creation wizard.</span></span> 

- <span data-ttu-id="3f02c-119">**証拠** –新しい証拠セットを作成し、確認する検索結果を追加します。</span><span class="sxs-lookup"><span data-stu-id="3f02c-119">**Evidence** – Create a new evidence set and add search results that you want to review.</span></span> <span data-ttu-id="3f02c-120">個々のドキュメントを確認し、調査メモを残すように注釈を付け、結果をエクスポートして別の環境に移動することができます。</span><span class="sxs-lookup"><span data-stu-id="3f02c-120">You can review individual documents, annotate to leave investigation notes, and export results to move to a different environment.</span></span> 

- <span data-ttu-id="3f02c-121">**レビュー** –インシデントに追加されたドキュメントを確認するには、ネイティブ、テキスト、およびほぼネイティブのビューを使用します。</span><span class="sxs-lookup"><span data-stu-id="3f02c-121">**Review** – Use a native, text, and near-native views to review the documents added to an incident.</span></span> <span data-ttu-id="3f02c-122">分析をドキュメントに適用して、重複、電子メールスレッド、およびテーマによってアイテムをグループ化することもできます。これは、インシデントのレビューを支援するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3f02c-122">You can also apply analytics to documents to group items by duplicates, email threads, and themes, which can help assist your review of the incident.</span></span> 

- <span data-ttu-id="3f02c-123">**墨消し、タグ、および注釈** : ドキュメントの校閲時に、テキストの墨消し、タグの適用、注釈の作成を行います。</span><span class="sxs-lookup"><span data-stu-id="3f02c-123">**Redact, tag, and annotate** – Redact text, apply tags, and make annotations as you review documents.</span></span>
  
- <span data-ttu-id="3f02c-124">**高度なインデックス作成** –部分的にインデックスが作成されたアイテムがある場合は、すべてのデータが検索に使用されるように、必要に応じて再インデックス化されます。</span><span class="sxs-lookup"><span data-stu-id="3f02c-124">**Advanced indexing** – If there are any partially indexed items, they will be reindexed on demand so that all data will be available for searching.</span></span>

- <span data-ttu-id="3f02c-125">**エラーの修復** –処理エラーを修復またはダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="3f02c-125">**Error remediation** – Remediate or download processing errors.</span></span> <span data-ttu-id="3f02c-126">これには、大きなファイルの種類、パスワードで保護されたファイル、およびインデックス作成エラーに関連するその他の問題の修復サポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3f02c-126">This includes remediation support for large file types, password protected files, and other issues related to indexing errors.</span></span> 

- <span data-ttu-id="3f02c-127">**ジョブ** –長時間実行されているプロセスの状態を追跡します。</span><span class="sxs-lookup"><span data-stu-id="3f02c-127">**Jobs** – Track status of long-running processes.</span></span>

- <span data-ttu-id="3f02c-128">**ハードディスクを削除するメールボックスアイテム** -緊急事態の場合は、正しく配置されていないアイテムを完全に削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f02c-128">**Hard-delete mailbox items** - In urgent situations, you may need to permanently delete misplaced items.</span></span> <span data-ttu-id="3f02c-129">これを行うには、セキュリティ & コンプライアンスセンターの PowerShell で PurgeType を使用して、メールボックスからアイテムを完全に削除するように、 **new-compliancesearchaction-のハード削除** コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3f02c-129">To do this, you can run the **New-ComplianceSearchAction -Purge -PurgeType HardDelete** command in Security & Compliance Center PowerShell to permanently remove items from mailboxes.</span></span> <span data-ttu-id="3f02c-130">詳細については、「[New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearchaction)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f02c-130">For more information, see [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearchaction).</span></span>
