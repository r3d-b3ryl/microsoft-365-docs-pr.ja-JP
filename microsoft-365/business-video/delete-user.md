---
title: Microsoft 365 for business からユーザーを削除する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: ビジネス向け Microsoft 365 でユーザーを削除する方法について説明します。
ms.openlocfilehash: 01c26431947950195c5fc711d8bd0d82c808beec
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49927276"
---
# <a name="delete-a-user"></a><span data-ttu-id="23d15-103">ユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="23d15-103">Delete a user</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR?autoplay=false]

<span data-ttu-id="23d15-104">従業員が会社を離れる場合は、ビジネス向け Microsoft 365 から削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23d15-104">When an employee leaves the company, you'll need to remove them from Microsoft 365 for business.</span></span> <span data-ttu-id="23d15-105">その前に、会社のファイルへのアクセスをブロックし、作成したドキュメントを保持し、ユーザーの削除に関連する他のいくつかの管理タスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23d15-105">Before doing so, you should block them from accessing company files, preserve the documents they created, and perform several other admin tasks associated with removing a user.</span></span>

## <a name="try-it"></a><span data-ttu-id="23d15-106">演習</span><span class="sxs-lookup"><span data-stu-id="23d15-106">Try it!</span></span>

1. <span data-ttu-id="23d15-107">管理センターから [ユーザー] を選択 **し**、[アクティブなユーザー] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="23d15-107">From the admin center, select **Users**, and choose **Active users**.</span></span>
1. <span data-ttu-id="23d15-108">削除するユーザーを選択し、[ユーザーの削除] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="23d15-108">Select the user you want to remove, and then select **Delete user**.</span></span>
1. <span data-ttu-id="23d15-109">ライセンスを削除するにはチェック ボックスをオンにし、メール エイリアスを削除するにはチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="23d15-109">Check the box to remove their license, and check the box to remove their email aliases.</span></span>
1. <span data-ttu-id="23d15-110">ユーザーが代理人メールボックスのアクセス許可を持っていた場合は、ここで削除できます。</span><span class="sxs-lookup"><span data-stu-id="23d15-110">If the user had delegate mailbox permissions, you can remove those here.</span></span>
1. <span data-ttu-id="23d15-111">別のユーザーに元従業員の OneDrive へのアクセス権を与える場合は、このチェック ボックスをオンにし、そのユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="23d15-111">Check the box to give another user access to the former employee’s OneDrive, and search for that user.</span></span>
1. <span data-ttu-id="23d15-112">名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="23d15-112">Select their name.</span></span>
1. <span data-ttu-id="23d15-113">このユーザーは、新しい場所にファイルを移動する期間が 30 日間になります。</span><span class="sxs-lookup"><span data-stu-id="23d15-113">This user will now have 30 days to move the files to a new location.</span></span>
1. <span data-ttu-id="23d15-114">別のユーザーに元従業員のメールへのアクセス権を与える場合は、このチェック ボックスをオンにし、[ユーザーの選択] を選択してメール **オプションを設定します**。</span><span class="sxs-lookup"><span data-stu-id="23d15-114">Check the box to give another user access to the former employee’s email, and choose **Select a user and set email options**.</span></span>
1. <span data-ttu-id="23d15-115">ユーザーを選択し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="23d15-115">Choose the user, and then select **Next**.</span></span>
1. <span data-ttu-id="23d15-116">必要な場合は、メールボックスが元従業員に属していたかどうかを示す新しい表示名を作成し、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="23d15-116">If you want, you can create a new display name that indicates the mailbox belonged to a former employee, and then select **Next**.</span></span>
1. <span data-ttu-id="23d15-117">自動応答を有効にし、必要に応じ返信テキストを変更します。</span><span class="sxs-lookup"><span data-stu-id="23d15-117">Turn on automatic replies, and change the reply text if you want.</span></span>
1. <span data-ttu-id="23d15-118">自動返信を送信するユーザー、会社の内部または社外のユーザー、および同じ返信が社外のユーザーに送信されるかどうかを選択し、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="23d15-118">Choose who to send automatic replies to, people inside or outside your company and whether the same reply goes to the people outside your company, and then select **Next**.</span></span>
1. <span data-ttu-id="23d15-119">関連付けられた電子メール エイリアスを削除するには、エイリアス **の横にある [X]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="23d15-119">To remove associated email aliases, select **X** next to their aliases.</span></span>
1. <span data-ttu-id="23d15-120">共有メールボックス情報を確認し、[完了] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="23d15-120">Review the shared mailbox information, and select **Finish**.</span></span>
1. <span data-ttu-id="23d15-121">オプションが正しく設定されていることを確認し、[割り当てと変換 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="23d15-121">Confirm your options are set correctly, and choose **Assign and convert**.</span></span>
1. <span data-ttu-id="23d15-122">結果を確認し、[閉じる] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="23d15-122">Review your results, and select **Close**.</span></span>

<span data-ttu-id="23d15-123">ユーザーを削除した後、そのユーザーのアカウントを復元するには、最大 30 日間必要です。</span><span class="sxs-lookup"><span data-stu-id="23d15-123">After you remove a user, you have up to 30 days to restore their account.</span></span>
