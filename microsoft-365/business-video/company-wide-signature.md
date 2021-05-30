---
title: 全社的な署名を作成する
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: 会社全体の電子メール署名を作成する方法について学習します。
ms.openlocfilehash: 669c61d17784641d1ecc88ac0952a46575c7898b
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706264"
---
# <a name="create-a-company-wide-email-signature"></a><span data-ttu-id="8a621-103">会社全体のメール署名を作成する</span><span class="sxs-lookup"><span data-stu-id="8a621-103">Create a company-wide email signature</span></span>

## <a name="watch-create-a-company-wide-email-signature"></a><span data-ttu-id="8a621-104">ウォッチ: 会社全体のメール署名を作成する</span><span class="sxs-lookup"><span data-stu-id="8a621-104">Watch: Create a company-wide email signature</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf?autoplay=false]

<span data-ttu-id="8a621-105">会社全体の電子メール署名は、組織内のユーザーが送信したメールごとに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a621-105">A company-wide email signature appears on every email sent by people in your organization.</span></span> <span data-ttu-id="8a621-106">会社の連絡先情報や法的免責事項など、重要な詳細を表示するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="8a621-106">You can use it to display important details, like your company contact information or a legal disclaimer.</span></span> 

## <a name="try-it"></a><span data-ttu-id="8a621-107">お試しください!</span><span class="sxs-lookup"><span data-stu-id="8a621-107">Try it!</span></span>

1. <span data-ttu-id="8a621-108">管理センターで **、[Microsoft 365]** を選択Exchange。</span><span class="sxs-lookup"><span data-stu-id="8a621-108">In the Microsoft 365 admin center, select **Exchange**.</span></span>
1. <span data-ttu-id="8a621-109">[メール **フロー] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8a621-109">Select **Mail flow**.</span></span>
1. <span data-ttu-id="8a621-110">[ **追加+] を選択** し、[免責事項の **適用] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8a621-110">Select **Add +**, and then select **Apply disclaimers**.</span></span>
1. <span data-ttu-id="8a621-111">[新しい **ルール] ページで、次の設定を** 行います。</span><span class="sxs-lookup"><span data-stu-id="8a621-111">On the **New rule** page:</span></span>
    1. <span data-ttu-id="8a621-112">ルールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="8a621-112">Enter a name for the rule.</span></span>
    1. <span data-ttu-id="8a621-113">[このルール **を適用する場合] ドロップダウン** リストから、[すべての **メッセージに適用] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8a621-113">From the **Apply this rule if** drop-down list, select **Apply to all messages**.</span></span>
    1. <span data-ttu-id="8a621-114">[次 **の操作] ドロップダウン** リストで、[免責事項の追加 **] が表示されます** 。</span><span class="sxs-lookup"><span data-stu-id="8a621-114">In the **Do the following** drop-down list, verify that **Append the disclaimer** is displayed.</span></span>
    1. <span data-ttu-id="8a621-115">ページの右側で、[テキストの入力]を選択し、[免責事項の指定] テキスト ボックスに電子メール署名のテキスト **を** 入力します。</span><span class="sxs-lookup"><span data-stu-id="8a621-115">On the right side of the page, select **Enter text**, and then enter the text for your email signature in the **Specify disclaimer** text box.</span></span> <span data-ttu-id="8a621-116">HTML を使用してテキストを書式設定することで、署名の外観を改善できます。</span><span class="sxs-lookup"><span data-stu-id="8a621-116">You can improve the look of your signature by formatting the text with HTML.</span></span>
    1. <span data-ttu-id="8a621-117">署名に画像を表示する場合は、その画像に公開されている URL を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a621-117">If you want an image to appear in your signature, you'll need to use a publicly available URL for that image.</span></span> <span data-ttu-id="8a621-118">Web 上の画像を参照し、右クリックし、[イメージ アドレスのコピー **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8a621-118">Browse to the image on the web, right-click it, and select **Copy image address**.</span></span> <span data-ttu-id="8a621-119">アドレスを [免責事項の指定 **] テキスト ボックスに** 貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="8a621-119">Paste the address into the **Specify disclaimer** text box.</span></span> <span data-ttu-id="8a621-120">**[OK] を** 選択し、下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="8a621-120">Select **OK**, then scroll down.</span></span>
    1. <span data-ttu-id="8a621-121">署名が暗号化されたメールで動作する場合は、フォールバック オプションを追加します。</span><span class="sxs-lookup"><span data-stu-id="8a621-121">To make sure the signature works with encrypted emails, add a fallback option.</span></span> <span data-ttu-id="8a621-122">ページの右側で、[1つ選択] を選択し、[折り返し]**を選択し\*\*\*\*、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8a621-122">On the right of the page, choose **Select one**, choose **Wrap**, and then select **OK**.</span></span>
    1. <span data-ttu-id="8a621-123">下にスクロールし、モードを [強制] に **設定したまま** にし、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="8a621-123">Scroll down and leave the mode set to **Enforce**, and then select **Save**.</span></span>
1. <span data-ttu-id="8a621-124">警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a621-124">A warning message will appear.</span></span> <span data-ttu-id="8a621-125">[ **はい] を** 選択して、将来のすべてのメッセージにルールを適用します。</span><span class="sxs-lookup"><span data-stu-id="8a621-125">Select **Yes** to apply the rule to all future messages.</span></span>

    <span data-ttu-id="8a621-126">署名が作成されました。</span><span class="sxs-lookup"><span data-stu-id="8a621-126">Your signature has been created.</span></span> <span data-ttu-id="8a621-127">次のメールを送信すると、作成した署名は表示されませんが、電子メール受信者にはその署名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a621-127">When you send your next email, you won't see the signature you just created, but the email recipients will see it.</span></span>