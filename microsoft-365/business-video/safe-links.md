---
title: '[リンクセーフ管理]'
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
description: 悪意のあるサイトからビジネスセーフリンクを管理する方法について学習します。
ms.openlocfilehash: 7e6b4507cd363a448812b48e3eafc7f4c077be3c
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177515"
---
# <a name="manage-safe-links"></a><span data-ttu-id="67860-103">[リンクセーフ管理]</span><span class="sxs-lookup"><span data-stu-id="67860-103">Manage Safe Links</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

<span data-ttu-id="67860-104">Microsoft Defender for Office 365 (以前は Microsoft 365 ATP、または Advanced Threat Protection) は、ユーザーが Office アプリのリンクをクリックすると、悪意のあるサイトからビジネスを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="67860-104">Microsoft Defender for Office 365 , formerly called Microsoft 365 ATP, or Advanced Threat Protection, helps protect your business against malicious sites when people click links in Office apps.</span></span>

## <a name="try-it"></a><span data-ttu-id="67860-105">お試しください!</span><span class="sxs-lookup"><span data-stu-id="67860-105">Try it!</span></span>

1. <span data-ttu-id="67860-106">管理センターに移動 [し、[セットアップ](https://admin.microsoft.com)] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="67860-106">Go to the [admin center](https://admin.microsoft.com), and select **Setup**.</span></span>
2. <span data-ttu-id="67860-107">下にスクロールして **高度な脅威からの保護を強化します**。</span><span class="sxs-lookup"><span data-stu-id="67860-107">Scroll down to **Increase protection from advanced threats**.</span></span> <span data-ttu-id="67860-108">[管理 **]** を選択し、[**リンクセーフクリックします**。</span><span class="sxs-lookup"><span data-stu-id="67860-108">Select **Manage**,and then **Safe Links**.</span></span>
3. <span data-ttu-id="67860-109">[**グローバル 設定]** を選択し、[次の URL をブロックする] で、ブロックする URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="67860-109">Select **Global Settings** and in **Block the following URLs**, enter the URL that you want to block.</span></span>
4. <span data-ttu-id="67860-110">**[Office 365** アプリで セーフ リンクを使用する] を選択し、[ユーザーが **Office 365** アプリで保護されたリンクをクリックした場合は追跡しない] を選択し、[Office 365 アプリの元の URL にユーザーがクリックしない]**を選択** します。</span><span class="sxs-lookup"><span data-stu-id="67860-110">Select **Use Safe Links in Office 365 app**, select **Do not track when users click protected links in Office 365 apps**, and select **Do not let users click through to the original URL in Office 365 apps**.</span></span> <span data-ttu-id="67860-111">既定のポリシーを設定した場合、これらは既に選択されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="67860-111">These might already be selected if you set up the default policy.</span></span> <span data-ttu-id="67860-112">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="67860-112">Select **Save**.</span></span>

<span data-ttu-id="67860-113">セーフこれで、リンクが構成されます。</span><span class="sxs-lookup"><span data-stu-id="67860-113">Safe Links are now configured.</span></span> <span data-ttu-id="67860-114">変更を有効にするには、最大 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="67860-114">Allow up to 30 minutes for your changes to take effect.</span></span>

<span data-ttu-id="67860-115">ユーザーがリンク付きメールを受信すると、リンクがスキャンされます。</span><span class="sxs-lookup"><span data-stu-id="67860-115">When a user receives an email with links, the links will be scanned.</span></span> <span data-ttu-id="67860-116">リンクが安全であると判断された場合は、クリック可能です。</span><span class="sxs-lookup"><span data-stu-id="67860-116">If the links are deemed safe, they'll be clickable.</span></span> <span data-ttu-id="67860-117">ただし、リンクがブロックリストにある場合、ユーザーにはブロックされたというメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="67860-117">However, if the link is on the blocked list, users will see a message that it's been blocked.</span></span>
