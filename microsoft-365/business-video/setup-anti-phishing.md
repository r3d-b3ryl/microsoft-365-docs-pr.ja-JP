---
title: フィッシング対策保護を設定する
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
description: フィッシング対策保護を設定する方法について学習します。
ms.openlocfilehash: f3a1399c8a6a51c7b14af7ffea8fbaea39cd1541
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702889"
---
# <a name="set-up-anti-phishing"></a><span data-ttu-id="607b5-103">フィッシング詐欺対策を設定する</span><span class="sxs-lookup"><span data-stu-id="607b5-103">Set up anti-phishing</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

<span data-ttu-id="607b5-104">フィッシングは悪意のある攻撃で、メールは使い慣れたソースから送信されたように見えますが、個人情報の収集を試みてきます。</span><span class="sxs-lookup"><span data-stu-id="607b5-104">Phishing is a malicious attack where an email looks like it was sent from a familiar source, but it attempts to collect your personal information.</span></span> <span data-ttu-id="607b5-105">既定では、Microsoft 365 にはフィッシング対策保護がいくつか含まれていますが、設定を調整することでその保護を強化できます。</span><span class="sxs-lookup"><span data-stu-id="607b5-105">By default, Microsoft 365 includes some anti-phishing protection, but you can increase that protection by refining the settings.</span></span> <span data-ttu-id="607b5-106">見て見てみしましょう。</span><span class="sxs-lookup"><span data-stu-id="607b5-106">Let's take a look.</span></span>

## <a name="try-it"></a><span data-ttu-id="607b5-107">演習</span><span class="sxs-lookup"><span data-stu-id="607b5-107">Try it!</span></span>

1. <span data-ttu-id="607b5-108">In the admin center [https://admin.microsoft.com](https://admin.microsoft.com) at, select **Security**, **Threat Management**, **Policy**, then **ATP Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="607b5-108">In the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), select **Security**, **Threat Management**, **Policy**, then **ATP Anti-phishing**.</span></span>
1. <span data-ttu-id="607b5-109">[既定 **のポリシー] を** 選択して絞り込む。</span><span class="sxs-lookup"><span data-stu-id="607b5-109">Select **Default Policy** to refine it.</span></span>
1. <span data-ttu-id="607b5-110">[偽装 **] セクションで、[** 編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="607b5-110">In the **Impersonation** section, select **Edit**.</span></span>
1. <span data-ttu-id="607b5-111">Go to **Add domains to protect** and select the toggle to automatically include the domains you own.</span><span class="sxs-lookup"><span data-stu-id="607b5-111">Go to **Add domains to protect** and select the toggle to automatically include the domains you own.</span></span>
1. <span data-ttu-id="607b5-112">[アクション **] に** 移動し、ドロップダウンを開きます。偽装したユーザーからメールが送信された場合は、必要なアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="607b5-112">Go to **Actions**, open the drop-down **If email is sent by an impersonated user**, and choose the action you want.</span></span>

    <span data-ttu-id="607b5-113">[偽装されたドメインから **メール** が送信された場合] ドロップダウンを開き、必要なアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="607b5-113">Open the drop-down **If email is sent by an impersonated domain** and choose the action you want.</span></span>
1. <span data-ttu-id="607b5-114">[偽装 **の安全性のヒントを有効にする] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="607b5-114">Select **Turn on impersonation safety tips**.</span></span> <span data-ttu-id="607b5-115">偽装されたユーザー、ドメイン、または異常な文字が検出された場合に、ユーザーにヒントを提供するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="607b5-115">Choose whether tips should be provided to users when the system detects impersonated users, domains, or unusual characters.</span></span> <span data-ttu-id="607b5-116">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="607b5-116">Select **Save**.</span></span>
1. <span data-ttu-id="607b5-117">メールボックス **インテリジェンスを選択** し、有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="607b5-117">Select **Mailbox intelligence** and verify that it's turned on.</span></span> <span data-ttu-id="607b5-118">これにより、使用パターンを学習することで、電子メールの効率が向上します。</span><span class="sxs-lookup"><span data-stu-id="607b5-118">This allows your email to be more efficient by learning usage patterns.</span></span>
1. <span data-ttu-id="607b5-119">[信頼 **できる送信者とドメインの追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="607b5-119">Choose **Add trusted senders and domains**.</span></span> <span data-ttu-id="607b5-120">ここでは、偽装として分類しない電子メール アドレスまたはドメインを追加できます。</span><span class="sxs-lookup"><span data-stu-id="607b5-120">Here you can add email addresses or domains that shouldn't be classified as an impersonation.</span></span>
1. <span data-ttu-id="607b5-121">Choose **Review your settings,** make sure everything is correct, select **Save,** then **Close**.</span><span class="sxs-lookup"><span data-stu-id="607b5-121">Choose **Review your settings**, make sure everything is correct, select **Save**, then **Close**.</span></span>

    <span data-ttu-id="607b5-122">組織では、フィッシングの脅威からの保護が強化されました。</span><span class="sxs-lookup"><span data-stu-id="607b5-122">Your organization now has better protection from phishing threats.</span></span>