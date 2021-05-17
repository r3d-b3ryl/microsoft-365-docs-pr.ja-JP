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
ms.openlocfilehash: ce0c1ba6e4099b6eaf4ec974938170020b8a5892
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580632"
---
# <a name="manage-safe-links"></a><span data-ttu-id="a0964-103">[リンクセーフ管理]</span><span class="sxs-lookup"><span data-stu-id="a0964-103">Manage Safe Links</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

<span data-ttu-id="a0964-104">Microsoft Defender for Office 365 (以前は Microsoft 365 ATP、または Advanced Threat Protection) は、ユーザーが Office アプリのリンクをクリックすると、悪意のあるサイトからビジネスを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a0964-104">Microsoft Defender for Office 365 , formerly called Microsoft 365 ATP, or Advanced Threat Protection, helps protect your business against malicious sites when people click links in Office apps.</span></span>

## <a name="try-it"></a><span data-ttu-id="a0964-105">お試しください!</span><span class="sxs-lookup"><span data-stu-id="a0964-105">Try it!</span></span>

1. <span data-ttu-id="a0964-106">管理センターに移動 [し、[セットアップ](https://admin.microsoft.com)] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a0964-106">Go to the [admin center](https://admin.microsoft.com), and select **Setup**.</span></span>
1. <span data-ttu-id="a0964-107">下にスクロールして **高度な脅威からの保護を強化します**。</span><span class="sxs-lookup"><span data-stu-id="a0964-107">Scroll down to **Increase protection from advanced threats**.</span></span> <span data-ttu-id="a0964-108">[表示 **] 、[\*\*\*\*管理]** の順に選択し **、[ATP セーフリンク] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a0964-108">Select **View**, **Manage**,and then **ATP Safe Links**.</span></span>
1. <span data-ttu-id="a0964-109">[ **組織全体に適用されるポリシー] で**、[既定のポリシー] **を** 選択し、[編集] アイコン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="a0964-109">Under **Policies that apply to the entire organization**, choose the **Default** policy, and then select the **Edit** icon.</span></span>
1. <span data-ttu-id="a0964-110">ブロックする URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="a0964-110">Enter a URL that you want to block.</span></span>
1. <span data-ttu-id="a0964-111">[**アプリで安全なリンクをOfficeする] を選択Office iOS と Android の場合は[安全なリンクを使用する] を選択します**。[ユーザー **が安全なリンクをクリックしても追跡しない] を選択します**。をクリック **し、[ユーザーが元の URL への安全なリンクをクリックさせない] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a0964-111">Select **Use safe links in Office apps, Office for iOS and Android**; select **Do not track when users click safe links**; and select **Do not let users click through safe links to original URL**.</span></span> <span data-ttu-id="a0964-112">既定のポリシーを設定した場合、これらは既に選択されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a0964-112">These might already be selected if you set up the default policy.</span></span> <span data-ttu-id="a0964-113">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0964-113">Select **Save**.</span></span>
1. <span data-ttu-id="a0964-114">[ **特定の受信者に適用されるポリシー]** で、[推奨される安全なリンクルール] を **選択** し、[編集] アイコン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="a0964-114">Under **Policies that apply to specific recipients**, choose **Recommended safe links rule**, and then select the **Edit** icon.</span></span>
1. <span data-ttu-id="a0964-115">[ **設定]** を選択し、下にスクロールして、チェックしない URL を入力し、[追加] アイコン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="a0964-115">Select **settings**, scroll down, enter the URL that you do not want to be checked, and then select the **Add** icon.</span></span>
1. <span data-ttu-id="a0964-116">[ **適用] を** 選択し、ドメイン名を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0964-116">Select **applied to**, and then select your domain name.</span></span> <span data-ttu-id="a0964-117">ルールを適用する追加のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="a0964-117">Select any additional domains that you want the rule applied to.</span></span> <span data-ttu-id="a0964-118">[ **追加]** **、[OK] の順** に選択し、[保存] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a0964-118">Select **add**, **OK**, and then **Save**.</span></span>

<span data-ttu-id="a0964-119">ATP セーフリンクが構成されています。</span><span class="sxs-lookup"><span data-stu-id="a0964-119">ATP Safe Links are now configured.</span></span> <span data-ttu-id="a0964-120">変更を有効にするには、最大 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="a0964-120">Allow up to 30 minutes for your changes to take effect.</span></span>

<span data-ttu-id="a0964-121">ユーザーがリンク付きメールを受信すると、リンクがスキャンされます。</span><span class="sxs-lookup"><span data-stu-id="a0964-121">When a user receives an email with links, the links will be scanned.</span></span> <span data-ttu-id="a0964-122">リンクが安全であると判断された場合は、クリック可能です。</span><span class="sxs-lookup"><span data-stu-id="a0964-122">If the links are deemed safe, they'll be clickable.</span></span> <span data-ttu-id="a0964-123">ただし、リンクがブロックリストにある場合、ユーザーにはブロックされたというメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0964-123">However, if the link is on the blocked list, users will see a message that it's been blocked.</span></span>