---
title: Microsoft コンプライアンス マネージャーと GDPR
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft Compliance Manager は、Microsoft Service Trust Portal の無料のワークフロー ベースのリスク評価ツールです。 コンプライアンス マネージャーを使用すると、Microsoft クラウド サービスに関連する規制コンプライアンス活動を追跡、割り当て、検証できます。
ms.openlocfilehash: 69e6551620fb654cb09d46554e6e3c98b6a2fc60
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595804"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a><span data-ttu-id="703e5-104">Microsoft コンプライアンス マネージャーと GDPR</span><span class="sxs-lookup"><span data-stu-id="703e5-104">Microsoft Compliance Manager and the GDPR</span></span>

<span data-ttu-id="703e5-105">EU が制定した一般データ保護規則 (GDPR) は、コンプライアンス戦略に影響を与え、コンプライアンス マネージャーで使用されるユーザーおよび顧客情報を管理するための特定のアクションを義務付ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="703e5-105">The General Data Protection Regulation (GDPR) enacted by the European Union can impact your compliance strategy and mandate specific actions to manage user and customer information used in Compliance Manager.</span></span>

## <a name="user-privacy-settings"></a><span data-ttu-id="703e5-106">ユーザー プライバシーの設定</span><span class="sxs-lookup"><span data-stu-id="703e5-106">User Privacy settings</span></span>

<span data-ttu-id="703e5-107">特定の規制では、組織がユーザー履歴データを削除できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="703e5-107">Certain regulations require that an organization must be able to delete user history data.</span></span> <span data-ttu-id="703e5-108">コンプライアンス マネージャーには、**管理者が次設定** できるユーザー プライバシー 機能が提供されています。</span><span class="sxs-lookup"><span data-stu-id="703e5-108">Compliance Manager provides **User Privacy Settings** functions that allow administrators to:</span></span>
  
- [<span data-ttu-id="703e5-109">ユーザーの検索</span><span class="sxs-lookup"><span data-stu-id="703e5-109">Search for a user</span></span>](#search-for-a-user)
- [<span data-ttu-id="703e5-110">アカウント データ履歴のレポートのエクスポート</span><span class="sxs-lookup"><span data-stu-id="703e5-110">Export a report of account data history</span></span>](#export-a-report-of-account-data-history)
- [<span data-ttu-id="703e5-111">ユーザー データの履歴の削除</span><span class="sxs-lookup"><span data-stu-id="703e5-111">Delete user data history</span></span>](#delete-user-data-history)
  
## <a name="search-for-a-user"></a><span data-ttu-id="703e5-112">ユーザーの検索</span><span class="sxs-lookup"><span data-stu-id="703e5-112">Search for a user</span></span>

<span data-ttu-id="703e5-113">ユーザー アカウントを検索するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="703e5-113">To search for a user account:</span></span>
  
1. <span data-ttu-id="703e5-114">ユーザーのメール エイリアス (@記号の左側の情報) を入力し、右側のドメイン サフィックス リストからドメイン名を選択します。</span><span class="sxs-lookup"><span data-stu-id="703e5-114">Enter the user email alias (the information to the left of the @ symbol) and choose the domain name from the  domain suffix list on the right.</span></span> <span data-ttu-id="703e5-115">複数の登録ドメインを持つ組織の場合は、ドメイン名のサフィックスを確認して、正しいドメイン名を確認します。</span><span class="sxs-lookup"><span data-stu-id="703e5-115">For organizations with multiple registered domains, double check the domain name suffix to ensure that it is correct.</span></span>

2. <span data-ttu-id="703e5-116">ユーザー名が正しく入力されている場合は、[検索] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="703e5-116">When you have the username correctly entered, select **Search**.</span></span>

3. <span data-ttu-id="703e5-117">返されないユーザー アカウントの場合、ページには [ユーザーが **見つかりません] と表示されます**。</span><span class="sxs-lookup"><span data-stu-id="703e5-117">For user accounts not returned, the page displays **User not found**.</span></span> <span data-ttu-id="703e5-118">ユーザーのメール アドレス情報を確認し、必要に応じて修正を行います。</span><span class="sxs-lookup"><span data-stu-id="703e5-118">Check the user's email address information and make corrections as necessary.</span></span> <span data-ttu-id="703e5-119">再試行するには、[検索] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="703e5-119">To retry, select **Search**.</span></span>

4. <span data-ttu-id="703e5-120">返されるユーザー アカウントの場合、ボタンのテキストが [検索] から **[クリア** ] に **変わります**。</span><span class="sxs-lookup"><span data-stu-id="703e5-120">For user accounts returned, the text of the button changes from **Search** to **Clear**.</span></span> <span data-ttu-id="703e5-121">これは、返されるユーザー アカウントが追加機能の操作コンテキストであり、これらの関数がこのユーザー アカウントに適用されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="703e5-121">This indicates that the returned user account is the operating context for the additional functions and that these functions apply to this user account.</span></span>

5. <span data-ttu-id="703e5-122">検索結果をクリアして別のユーザーを検索するには、[クリア] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="703e5-122">To clear search results and search for a different user, select **Clear**.</span></span>

## <a name="export-a-report-of-account-data-history"></a><span data-ttu-id="703e5-123">アカウント データ履歴のレポートのエクスポート</span><span class="sxs-lookup"><span data-stu-id="703e5-123">Export a report of account data history</span></span>

<span data-ttu-id="703e5-124">識別されたユーザー アカウントごとに、アカウントにリンクされた依存関係のレポートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="703e5-124">For each user account identified, you can generate a report of dependencies linked to the account.</span></span> <span data-ttu-id="703e5-125">この情報を使用すると、開いているアクション アイテムを再割り当てしたり、以前にアップロードした証拠にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="703e5-125">This information allows you to reassign open Action Items or ensure access to previously uploaded evidence.</span></span>
  
 <span data-ttu-id="703e5-126">レポートを生成してエクスポートするには:</span><span class="sxs-lookup"><span data-stu-id="703e5-126">To generate and export a report:</span></span>
  
1. <span data-ttu-id="703e5-127">[ **エクスポート]** を選択して、現在返されたユーザー アカウントに割り当てられているコンプライアンス マネージャー コントロールのアクション アイテムと、そのユーザーがアップロードしたドキュメントの一覧のレポートを生成してダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="703e5-127">Select **Export** to generate and download a report of the Compliance Manager control Action Items currently assigned to the returned user account, and the list of documents uploaded by that user.</span></span> <span data-ttu-id="703e5-128">割り当てられたアクションやアップロードされたドキュメントがない場合は、「このユーザーのデータなし」というエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="703e5-128">If there are no assigned actions or uploaded documents, an error message states "No data for this user".</span></span>

2. <span data-ttu-id="703e5-129">レポートは、ブラウザーのダウンロード履歴を確認するダウンロード ポップアップが表示されていない場合に、アクティブなブラウザー ウィンドウのバックグラウンドでダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="703e5-129">The report downloads in the background of the active browser window — if you don't see a download popup that you want to check your browser download history.</span></span>

3. <span data-ttu-id="703e5-130">ドキュメントを開いてレポート データを確認します。</span><span class="sxs-lookup"><span data-stu-id="703e5-130">Open the document to review the report data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="703e5-131">レポート データは、アクション アイテムの割り当て履歴に対する状態の変更を保持および表示する履歴リストではありません。</span><span class="sxs-lookup"><span data-stu-id="703e5-131">The report data is not a historical list that retains and displays state changes to Action Item assignment history.</span></span> <span data-ttu-id="703e5-132">生成されたレポートは、レポートの実行時に割り当てられたコントロールのアクション アイテム (レポートに書き込まれた日付とタイム スタンプ) のスナップショットです。</span><span class="sxs-lookup"><span data-stu-id="703e5-132">The generated report is a snapshot of the control Action Items assigned at the time that the report is run (date and time stamp written into the report).</span></span> <span data-ttu-id="703e5-133">たとえば、アクション アイテムをそれ以降に再割り当てすると、同じユーザーに対してレポートが再度生成されると、異なるスナップショット レポート データが生成されます。</span><span class="sxs-lookup"><span data-stu-id="703e5-133">For example, any subsequent reassignment of Action Items result in different snapshot report data if the report is generated again for the same user.</span></span>
  
## <a name="delete-user-data-history"></a><span data-ttu-id="703e5-134">ユーザー データの履歴の削除</span><span class="sxs-lookup"><span data-stu-id="703e5-134">Delete user data history</span></span>

<span data-ttu-id="703e5-135">返されたユーザーに割り当てられているすべてのコントロール Action Items を '未割り当て' に設定します。</span><span class="sxs-lookup"><span data-stu-id="703e5-135">Sets all control Action Items assigned to the returned user to 'unassigned'.</span></span> <span data-ttu-id="703e5-136">返された **ユーザーがアップロード** したドキュメントの値によってアップロードされた値を 'ユーザーが削除済み' に設定します。</span><span class="sxs-lookup"><span data-stu-id="703e5-136">Sets the **uploaded by** value for any documents uploaded by the returned user to 'user removed'.</span></span>
  
<span data-ttu-id="703e5-137">ユーザー アカウントのアクション アイテムとドキュメントのアップロード履歴を削除するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="703e5-137">To delete the user account Action Item and document upload history:</span></span>
  
1. <span data-ttu-id="703e5-138">**[削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="703e5-138">Select **Delete**.</span></span>

    <span data-ttu-id="703e5-139">確認ダイアログが表示されます。 "これにより、選択したユーザーのすべてのコントロールアクション アイテムの割り当てとドキュメントのアップロード *履歴が削除されます。このアクションは永続的です。続行する必要がありますか?*</span><span class="sxs-lookup"><span data-stu-id="703e5-139">A confirmation dialog is displayed: "*This removes all control Action Item assignments and the document upload history for the selected user. This action is permanent. Are you sure you want to continue?*"</span></span>

2. <span data-ttu-id="703e5-140">[OK] を選択 **し続ける** には、それ以外の場合は [キャンセル] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="703e5-140">To continue select **OK**, otherwise select **Cancel**.</span></span>
