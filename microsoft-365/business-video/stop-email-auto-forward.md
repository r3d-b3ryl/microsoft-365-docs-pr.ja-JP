---
title: 自動転送メールを停止する
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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: メールの自動転送を停止する方法について学習します。
ms.openlocfilehash: 0683e133f6c261dc19cc098b13be298cd8086001
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702591"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="d816d-103">メールの自動転送を停止する</span><span class="sxs-lookup"><span data-stu-id="d816d-103">Stop email auto-forward</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="d816d-104">ハッカーがユーザーのメールボックスにアクセスした場合、ハッカーはユーザーの電子メールを外部のアドレスに自動転送し、専有情報を盗む可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d816d-104">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="d816d-105">これを停止するには、メール フロー ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="d816d-105">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="d816d-106">演習</span><span class="sxs-lookup"><span data-stu-id="d816d-106">Try it!</span></span>

1. <span data-ttu-id="d816d-107">Microsoft 365 管理センターから **Exchange、** メール フローを選択し、[ルール] タブでプラス記号を選択し、新しいルールの作成 **を選択します**。 </span><span class="sxs-lookup"><span data-stu-id="d816d-107">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="d816d-108">[その **他のオプション] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d816d-108">Select **More options**.</span></span> <span data-ttu-id="d816d-109">新しいルールに名前を付け、</span><span class="sxs-lookup"><span data-stu-id="d816d-109">Name your new rule.</span></span>
1. <span data-ttu-id="d816d-110">次に、このルールを適用するドロップダウンを開きます **(** 送信者を選択し、外部 **内部の** 場合)。</span><span class="sxs-lookup"><span data-stu-id="d816d-110">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="d816d-111">[**組織内] を選択し\*\*\*\*、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="d816d-111">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="d816d-112">[**条件の追加]** を選択し、ドロップダウンを開き、[メッセージのプロパティ] を **選択** して **、メッセージの種類を含める。**</span><span class="sxs-lookup"><span data-stu-id="d816d-112">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="d816d-113">[メッセージの **種類の選択]** ドロップダウンを開き、[自動転送]**を選択し\*\*\*\*、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d816d-113">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="d816d-114">Open the **Do the following** drop-down, select Block the **message,** then **reject the message and include an explanation**.</span><span class="sxs-lookup"><span data-stu-id="d816d-114">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="d816d-115">説明のメッセージ テキストを入力し **、[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d816d-115">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="d816d-116">一番下までスクロールし、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d816d-116">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="d816d-117">ルールが作成され、ハッカーはメッセージを自動転送できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d816d-117">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>