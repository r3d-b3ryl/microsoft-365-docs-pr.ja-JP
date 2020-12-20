---
title: 安全なリンクを管理する
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
description: 安全なリンクを管理して悪意のあるサイトからビジネスを保護する方法について学習します。
ms.openlocfilehash: eabb2c1f71b1183867ffcb005ba4f7e44ed6e4b7
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702661"
---
# <a name="manage-safe-links"></a><span data-ttu-id="ce9d7-103">安全なリンクを管理する</span><span class="sxs-lookup"><span data-stu-id="ce9d7-103">Manage Safe Links</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

<span data-ttu-id="ce9d7-104">Office アプリでリンクをクリックすると、Microsoft Defender for Office 365 (以前の Microsoft 365 ATP または Advanced Threat Protection) は、悪意のあるサイトからビジネスを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ce9d7-104">Microsoft Defender for Office 365 , formerly called Microsoft 365 ATP, or Advanced Threat Protection, helps protect your business against malicious sites when people click links in Office apps.</span></span>

## <a name="try-it"></a><span data-ttu-id="ce9d7-105">演習</span><span class="sxs-lookup"><span data-stu-id="ce9d7-105">Try it!</span></span>

1. <span data-ttu-id="ce9d7-106">管理センターに [移動し、[](https://admin.microsoft.com)セットアップ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="ce9d7-106">Go to the [admin center](https://admin.microsoft.com), and select **Setup**.</span></span>
1. <span data-ttu-id="ce9d7-107">下にスクロールして **高度な脅威からの保護を強化します**。</span><span class="sxs-lookup"><span data-stu-id="ce9d7-107">Scroll down to **Increase protection from advanced threats**.</span></span> <span data-ttu-id="ce9d7-108">[表示 **]、[\*\*\*\*管理]、ATP** の [安全なリンク **] の順に選択します**。</span><span class="sxs-lookup"><span data-stu-id="ce9d7-108">Select **View**, **Manage**,and then **ATP Safe Links**.</span></span>
1. <span data-ttu-id="ce9d7-109">[**組織全体に適用するポリシー**] で、[既定のポリシー] を選択し、[編集] アイコン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="ce9d7-109">Under **Policies that apply to the entire organization**, choose the **Default** policy, and then select the **Edit** icon.</span></span>
1. <span data-ttu-id="ce9d7-110">ブロックする URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="ce9d7-110">Enter a URL that you want to block.</span></span>
1. <span data-ttu-id="ce9d7-111">[アプリ **で安全なリンクをOffice、iOS および Android Officeを使用する] を選択します**。[ユーザー **が安全なリンクをクリックしても追跡しない] を選択します**。[元の **URL への安全なリンクをユーザーがクリックさせない] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ce9d7-111">Select **Use safe links in Office apps, Office for iOS and Android**; select **Do not track when users click safe links**; and select **Do not let users click through safe links to original URL**.</span></span> <span data-ttu-id="ce9d7-112">既定のポリシーを設定する場合、これらは既に選択されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ce9d7-112">These might already be selected if you set up the default policy.</span></span> <span data-ttu-id="ce9d7-113">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce9d7-113">Select **Save**.</span></span>
1. <span data-ttu-id="ce9d7-114">[**特定の受信者に適用** するポリシー] で、[推奨される安全なリンクルール] を選択し、[編集] アイコン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="ce9d7-114">Under **Policies that apply to specific recipients**, choose **Recommended safe links rule**, and then select the **Edit** icon.</span></span>
1. <span data-ttu-id="ce9d7-115">設定 **を** 選択し、下にスクロールして、チェックしない URL を入力して、[追加] アイコン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="ce9d7-115">Select **settings**, scroll down, enter the URL that you do not want to be checked, and then select the **Add** icon.</span></span>
1. <span data-ttu-id="ce9d7-116">Select **applied to,** and then select your domain name.</span><span class="sxs-lookup"><span data-stu-id="ce9d7-116">Select **applied to**, and then select your domain name.</span></span> <span data-ttu-id="ce9d7-117">ルールを適用する追加のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="ce9d7-117">Select any additional domains that you want the rule applied to.</span></span> <span data-ttu-id="ce9d7-118">[追加 **]、[OK]、** および [保存] の順 **に選択します**。 </span><span class="sxs-lookup"><span data-stu-id="ce9d7-118">Select **add**, **OK**, and then **Save**.</span></span>

<span data-ttu-id="ce9d7-119">ATP の安全なリンクが構成されています。</span><span class="sxs-lookup"><span data-stu-id="ce9d7-119">ATP Safe Links are now configured.</span></span> <span data-ttu-id="ce9d7-120">変更が有効にな最大 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="ce9d7-120">Allow up to 30 minutes for your changes to take effect.</span></span>

<span data-ttu-id="ce9d7-121">ユーザーがリンク付きメールを受信すると、リンクがスキャンされます。</span><span class="sxs-lookup"><span data-stu-id="ce9d7-121">When a user receives an email with links, the links will be scanned.</span></span> <span data-ttu-id="ce9d7-122">リンクが安全であると判断された場合は、クリック可能になります。</span><span class="sxs-lookup"><span data-stu-id="ce9d7-122">If the links are deemed safe, they'll be clickable.</span></span> <span data-ttu-id="ce9d7-123">ただし、リンクがブロックリストにある場合、ブロックされたというメッセージがユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce9d7-123">However, if the link is on the blocked list, users will see a message that it's been blocked.</span></span>