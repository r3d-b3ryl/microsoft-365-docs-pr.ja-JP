---
title: ランサムウェア用のメール ルールを作成する
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: ランサムウェアを防止するために電子メール ルールを作成する方法について学習します。
ms.openlocfilehash: 96822916753f2f70d481c213e7e31046f7081446
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580500"
---
# <a name="create-email-rules-to-prevent-ransomware"></a><span data-ttu-id="e950f-103">ランサムウェアを防止する電子メール ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="e950f-103">Create email rules to prevent ransomware</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

<span data-ttu-id="e950f-104">Microsoft 365は、JavaScript、バッチ、実行可能ファイルなどの潜在的に危険なファイルがランサムウェアで開かされないようにすることで、ランサムウェアからビジネスを保護するのにOutlook。</span><span class="sxs-lookup"><span data-stu-id="e950f-104">Microsoft 365 helps protect your business against ransomware by preventing potentially dangerous files, like JavaScript, batch, and executables, from being opened in Outlook.</span></span> <span data-ttu-id="e950f-105">追加の種類のファイルをブロックまたは警告するルールを追加して、このレベルの保護を強化するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e950f-105">To increase this level of protection by adding rules that block or warn you of additional types of files, follow these steps.</span></span>

## <a name="try-it"></a><span data-ttu-id="e950f-106">お試しください!</span><span class="sxs-lookup"><span data-stu-id="e950f-106">Try it!</span></span>

1. <span data-ttu-id="e950f-107">[管理センター] で [https://admin.microsoft.com](https://admin.microsoft.com) 、[管理センター]**のExchange** を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e950f-107">From the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), choose **Exchange** under **Admin centers**.</span></span>
1. <span data-ttu-id="e950f-108">左側のメニューから、[メール フロー] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e950f-108">From the menu on the left, choose **mail flow**.</span></span>
1. <span data-ttu-id="e950f-109">[ルール] タブで、プラス記号 (+) の横にある矢印を選択し、[新しいルールの作成] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e950f-109">On the rules tab, choose the arrow next to the plus (+) symbol, and then choose **Create a new rule**.</span></span>
1. <span data-ttu-id="e950f-110">新しい **ルール ページで** 、ルールの名前を入力し、一番下までスクロールし、[その他のオプション] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e950f-110">On the **new rule** page, enter a name for your rule, scroll to the bottom, and then choose **More options**.</span></span>
1. <span data-ttu-id="e950f-111">[ **このルールを適用する場合]** で、[任意の添付 **ファイル] を** 選択し、[ファイル拡張子 **にこれらの単語が含まれる] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e950f-111">Under **Apply this rule if**, select **Any attachment**, and then select **file extension includes these words**.</span></span>
1. <span data-ttu-id="e950f-112">[単語または語句の **指定**] ボックスに、ルールを適用するファイル拡張子 (マクロを含むファイル拡張子など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="e950f-112">In the box under **specify words or phrases**, enter the file extensions that you want the rule to be applied to, such as file extensions that can contain macros.</span></span> <span data-ttu-id="e950f-113">プラス記号 (+) を使用して、一度に 1 つ追加します。</span><span class="sxs-lookup"><span data-stu-id="e950f-113">Use the plus (+) symbol to add them one at a time.</span></span>

    <span data-ttu-id="e950f-114">ファイルの種類の詳細については、「ランサムウェアから保護 [する」を参照してください](../admin/security-and-compliance/secure-your-business-data.md#ransomware)。</span><span class="sxs-lookup"><span data-stu-id="e950f-114">Learn more about file types by reading [Protect against ransomware](../admin/security-and-compliance/secure-your-business-data.md#ransomware).</span></span>

1. <span data-ttu-id="e950f-115">下にスクロールしてリストを確認し **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e950f-115">Scroll down to review your list, and then choose **OK**.</span></span>
1. <span data-ttu-id="e950f-116">新しい **ルール ページで、[** 条件の追加] **を** 選択し、[次の操作] で条件 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e950f-116">On the **new rule** page, choose **add condition**, and then choose a condition under **Do the following**.</span></span>
1. <span data-ttu-id="e950f-117">選択できるルール オプションは多数存在しますが、この例では[メッセージで受信者に通知する **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e950f-117">You have many rule options to choose from, but in this example we'll choose to **Notify the recipient with a message**.</span></span>
1. <span data-ttu-id="e950f-118">通知のメッセージ テキストを入力し **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e950f-118">Enter message text for your notification, and then chose **OK**.</span></span>
1. <span data-ttu-id="e950f-119">オプション: 新しい **ルール ページで**、[例外の追加] を選択し、ルールに対する例外の詳細 (信頼できる送信者からのメッセージなど) を入力します。 </span><span class="sxs-lookup"><span data-stu-id="e950f-119">Optional: On the **new rule** page, choose **add exception**, and enter any details for exceptions to your rule, such as messages from trusted senders.</span></span>
1. <span data-ttu-id="e950f-120">新しいルール ページで、[保存] **を選択** し、提供されたルールの概要情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="e950f-120">On the new rule page, choose **Save**, and review the rule summary information provided.</span></span>