---
title: ランサムウェア用のメール ルールを作成する
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
description: ランサムウェアを防止するメール ルールを作成する方法について学習します。
ms.openlocfilehash: 3b45af71aa26beb31e21f5db662091f46343f97d
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926116"
---
# <a name="create-email-rules-to-prevent-ransomware"></a><span data-ttu-id="cd1ba-103">ランサムウェアを防止するメール ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="cd1ba-103">Create email rules to prevent ransomware</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

<span data-ttu-id="cd1ba-104">Microsoft 365 は、JavaScript、バッチ、実行可能ファイルなどの潜在的な危険なファイルが Outlook で開かされないようにすることで、ランサムウェアからビジネスを保護します。</span><span class="sxs-lookup"><span data-stu-id="cd1ba-104">Microsoft 365 helps protect your business against ransomware by preventing potentially dangerous files, like JavaScript, batch, and executables, from being opened in Outlook.</span></span> <span data-ttu-id="cd1ba-105">他の種類のファイルをブロックまたは警告するルールを追加して、このレベルの保護を強化するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cd1ba-105">To increase this level of protection by adding rules that block or warn you of additional types of files, follow these steps.</span></span>

## <a name="try-it"></a><span data-ttu-id="cd1ba-106">演習</span><span class="sxs-lookup"><span data-stu-id="cd1ba-106">Try it!</span></span>

1. <span data-ttu-id="cd1ba-107">From the admin center [https://admin.microsoft.com](https://admin.microsoft.com) at, choose **Exchange** under **Admin centers**.</span><span class="sxs-lookup"><span data-stu-id="cd1ba-107">From the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), choose **Exchange** under **Admin centers**.</span></span>
1. <span data-ttu-id="cd1ba-108">左側のメニューから、[メール フロー] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cd1ba-108">From the menu on the left, choose **mail flow**.</span></span>
1. <span data-ttu-id="cd1ba-109">[ルール] タブで、プラス記号 (+) の横にある矢印を選択し、[新しいルールの作成] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cd1ba-109">On the rules tab, choose the arrow next to the plus (+) symbol, and then choose **Create a new rule**.</span></span>
1. <span data-ttu-id="cd1ba-110">新しい **ルール ページで** 、ルールの名前を入力し、一番下までスクロールして、[その他のオプション] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cd1ba-110">On the **new rule** page, enter a name for your rule, scroll to the bottom, and then choose **More options**.</span></span>
1. <span data-ttu-id="cd1ba-111">[ **このルールを適用する条件] で**[任意の添付ファイル] **を** 選択し、次の単語を含 **むファイル拡張子を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cd1ba-111">Under **Apply this rule if**, select **Any attachment**, and then select **file extension includes these words**.</span></span>
1. <span data-ttu-id="cd1ba-112">[単語 **または語句の** 指定] ボックスに、ルールを適用するファイル拡張子 (マクロを含むファイル拡張子など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="cd1ba-112">In the box under **specify words or phrases**, enter the file extensions that you want the rule to be applied to, such as file extensions that can contain macros.</span></span> <span data-ttu-id="cd1ba-113">プラス記号 (+) を使用して、一度に 1 つ追加します。</span><span class="sxs-lookup"><span data-stu-id="cd1ba-113">Use the plus (+) symbol to add them one at a time.</span></span>

    <span data-ttu-id="cd1ba-114">ランサムウェアからの保護に関する記事を参照して、ファイル [の種類について詳しくは、「ランサムウェアからの保護」を参照してください](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware)。</span><span class="sxs-lookup"><span data-stu-id="cd1ba-114">Learn more about file types by reading [Protect against ransomware](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware).</span></span>

1. <span data-ttu-id="cd1ba-115">下にスクロールしてリストを確認し **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cd1ba-115">Scroll down to review your list, and then choose **OK**.</span></span>
1. <span data-ttu-id="cd1ba-116">On the **new rule** page, choose **add condition,** and then choose a condition under **Do the following**.</span><span class="sxs-lookup"><span data-stu-id="cd1ba-116">On the **new rule** page, choose **add condition**, and then choose a condition under **Do the following**.</span></span>
1. <span data-ttu-id="cd1ba-117">You have many rule options to choose from, but in this example we'll choose to **Notify the recipient with a message**.</span><span class="sxs-lookup"><span data-stu-id="cd1ba-117">You have many rule options to choose from, but in this example we'll choose to **Notify the recipient with a message**.</span></span>
1. <span data-ttu-id="cd1ba-118">通知のメッセージ テキストを入力し **、[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cd1ba-118">Enter message text for your notification, and then chose **OK**.</span></span>
1. <span data-ttu-id="cd1ba-119">オプション: 新しいルール **ページ** で、[例外の追加] を選択し、ルールに対する例外の詳細 (信頼できる送信者からのメッセージなど) を入力します。</span><span class="sxs-lookup"><span data-stu-id="cd1ba-119">Optional: On the **new rule** page, choose **add exception**, and enter any details for exceptions to your rule, such as messages from trusted senders.</span></span>
1. <span data-ttu-id="cd1ba-120">新しいルール ページで、[保存] **を選択** し、提供されたルールの概要情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="cd1ba-120">On the new rule page, choose **Save**, and review the rule summary information provided.</span></span>