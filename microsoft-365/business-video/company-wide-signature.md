---
title: 全社的な署名を作成する
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
description: 会社全体の電子メール署名を作成する方法について学習します。
ms.openlocfilehash: 3a9623837b3a68fa8cc0fb378293ec463d9bb789
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928305"
---
# <a name="create-a-company-wide-email-signature"></a><span data-ttu-id="c687b-103">会社全体の電子メール署名を作成する</span><span class="sxs-lookup"><span data-stu-id="c687b-103">Create a company-wide email signature</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf?autoplay=false]

<span data-ttu-id="c687b-104">会社全体の電子メール署名は、組織内のユーザーによって送信される電子メールごとに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c687b-104">A company-wide email signature appears on every email sent by people in your organization.</span></span> <span data-ttu-id="c687b-105">会社の連絡先情報や法的免責事項など、重要な詳細を表示するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="c687b-105">You can use it to display important details, like your company contact information or a legal disclaimer.</span></span> 

## <a name="try-it"></a><span data-ttu-id="c687b-106">演習</span><span class="sxs-lookup"><span data-stu-id="c687b-106">Try it!</span></span>

1. <span data-ttu-id="c687b-107">Microsoft 365 管理センターで **、[Exchange]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c687b-107">In the Microsoft 365 admin center, select **Exchange**.</span></span>
1. <span data-ttu-id="c687b-108">[メール **フロー] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c687b-108">Select **Mail flow**.</span></span>
1. <span data-ttu-id="c687b-109">[ **追加 +] を選択** し、[免責事項の適用 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c687b-109">Select **Add +**, and then select **Apply disclaimers**.</span></span>
1. <span data-ttu-id="c687b-110">[新しい **ルール] ページで、次の設定を** 行います。</span><span class="sxs-lookup"><span data-stu-id="c687b-110">On the **New rule** page:</span></span>
    1. <span data-ttu-id="c687b-111">ルールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c687b-111">Enter a name for the rule.</span></span>
    1. <span data-ttu-id="c687b-112">From the **Apply this rule if** drop-down list, select Apply to all **messages**.</span><span class="sxs-lookup"><span data-stu-id="c687b-112">From the **Apply this rule if** drop-down list, select **Apply to all messages**.</span></span>
    1. <span data-ttu-id="c687b-113">[実行 **する操作] ドロップダウン** リストで、免責事項の **追加が表示されるのを** 確認します。</span><span class="sxs-lookup"><span data-stu-id="c687b-113">In the **Do the following** drop-down list, verify that **Append the disclaimer** is displayed.</span></span>
    1. <span data-ttu-id="c687b-114">ページの右側で [テキストの入力] を選択し、[免責事項の指定] テキスト ボックスに電子メール署名のテキスト **を** 入力します。</span><span class="sxs-lookup"><span data-stu-id="c687b-114">On the right side of the page, select **Enter text**, and then enter the text for your email signature in the **Specify disclaimer** text box.</span></span> <span data-ttu-id="c687b-115">HTML でテキストを書式設定することで、署名の外観を向上できます。</span><span class="sxs-lookup"><span data-stu-id="c687b-115">You can improve the look of your signature by formatting the text with HTML.</span></span>
    1. <span data-ttu-id="c687b-116">署名に画像を表示する場合は、その画像に公開されている URL を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c687b-116">If you want an image to appear in your signature, you'll need to use a publicly available URL for that image.</span></span> <span data-ttu-id="c687b-117">Web 上のイメージを参照し、右クリックして、[イメージ アドレスのコピー **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c687b-117">Browse to the image on the web, right-click it, and select **Copy image address**.</span></span> <span data-ttu-id="c687b-118">[免責事項の指定] テキスト **ボックスにアドレスを** 貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="c687b-118">Paste the address into the **Specify disclaimer** text box.</span></span> <span data-ttu-id="c687b-119">**[OK] を** 選択し、下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="c687b-119">Select **OK**, then scroll down.</span></span>
    1. <span data-ttu-id="c687b-120">署名が暗号化された電子メールで機能するには、フォールバック オプションを追加します。</span><span class="sxs-lookup"><span data-stu-id="c687b-120">To make sure the signature works with encrypted emails, add a fallback option.</span></span> <span data-ttu-id="c687b-121">On the right of the page, choose **Select one,** choose **Wrap,** and then select **OK**.</span><span class="sxs-lookup"><span data-stu-id="c687b-121">On the right of the page, choose **Select one**, choose **Wrap**, and then select **OK**.</span></span>
    1. <span data-ttu-id="c687b-122">下にスクロールし、モードを[強制] のままにして、[保存] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="c687b-122">Scroll down and leave the mode set to **Enforce**, and then select **Save**.</span></span>
1. <span data-ttu-id="c687b-123">警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c687b-123">A warning message will appear.</span></span> <span data-ttu-id="c687b-124">今後 **のすべてのメッセージに** ルールを適用するには、[はい] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c687b-124">Select **Yes** to apply the rule to all future messages.</span></span>

    <span data-ttu-id="c687b-125">署名が作成されました。</span><span class="sxs-lookup"><span data-stu-id="c687b-125">Your signature has been created.</span></span> <span data-ttu-id="c687b-126">次のメールを送信すると、作成した署名は表示されませんが、メールの受信者には表示されます。</span><span class="sxs-lookup"><span data-stu-id="c687b-126">When you send your next email, you won't see the signature you just created, but the email recipients will see it.</span></span>