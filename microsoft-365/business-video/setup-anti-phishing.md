---
title: フィッシング対策の保護を設定する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: フィッシング対策保護を設定する方法について学習します。
ms.openlocfilehash: 8cef8f916a8a3e2b27dd7f76ddecd921d59ca0c4
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50422005"
---
# <a name="set-up-anti-phishing"></a><span data-ttu-id="61062-103">フィッシング詐欺対策を設定する</span><span class="sxs-lookup"><span data-stu-id="61062-103">Set up anti-phishing</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

<span data-ttu-id="61062-104">フィッシングは、電子メールが使い慣れたソースから送信されたように見えるが、個人情報の収集を試みる悪意のある攻撃です。</span><span class="sxs-lookup"><span data-stu-id="61062-104">Phishing is a malicious attack where an email looks like it was sent from a familiar source, but it attempts to collect your personal information.</span></span> <span data-ttu-id="61062-105">既定では、Microsoft 365 にはフィッシング対策保護がいくつか含まれていますが、設定を絞り込み、その保護を強化できます。</span><span class="sxs-lookup"><span data-stu-id="61062-105">By default, Microsoft 365 includes some anti-phishing protection, but you can increase that protection by refining the settings.</span></span> <span data-ttu-id="61062-106">それでは、見てみよ。</span><span class="sxs-lookup"><span data-stu-id="61062-106">Let's take a look.</span></span>

## <a name="try-it"></a><span data-ttu-id="61062-107">演習</span><span class="sxs-lookup"><span data-stu-id="61062-107">Try it!</span></span>

1. <span data-ttu-id="61062-108">管理センターで、[セキュリティ [https://admin.microsoft.com](https://admin.microsoft.com) ] 、[**脅威** 管理] 、[**ポリシー**] 、[ATP フィッシング対策]**の順に選択します**。 </span><span class="sxs-lookup"><span data-stu-id="61062-108">In the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), select **Security**, **Threat Management**, **Policy**, then **ATP Anti-phishing**.</span></span>
1. <span data-ttu-id="61062-109">[既定 **のポリシー] を** 選択して絞り込む。</span><span class="sxs-lookup"><span data-stu-id="61062-109">Select **Default Policy** to refine it.</span></span>
1. <span data-ttu-id="61062-110">[偽装 **] セクションで、[** 編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="61062-110">In the **Impersonation** section, select **Edit**.</span></span>
1. <span data-ttu-id="61062-111">[ドメインの **追加] に移動して、** 自分が所有するドメインを自動的に含めるトグルを保護して選択します。</span><span class="sxs-lookup"><span data-stu-id="61062-111">Go to **Add domains to protect** and select the toggle to automatically include the domains you own.</span></span>
1. <span data-ttu-id="61062-112">[アクション **] に移動** し、ドロップダウンを **開きます** 偽装ユーザーからメールが送信された場合は、必要なアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="61062-112">Go to **Actions**, open the drop-down **If email is sent by an impersonated user**, and choose the action you want.</span></span>

    <span data-ttu-id="61062-113">[偽装されたドメインから **メールが** 送信された場合] ドロップダウンを開き、必要なアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="61062-113">Open the drop-down **If email is sent by an impersonated domain** and choose the action you want.</span></span>
1. <span data-ttu-id="61062-114">[偽装 **の安全ヒントを有効にする] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="61062-114">Select **Turn on impersonation safety tips**.</span></span> <span data-ttu-id="61062-115">システムが偽装ユーザー、ドメイン、または異常な文字を検出した場合に、ヒントをユーザーに提供するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="61062-115">Choose whether tips should be provided to users when the system detects impersonated users, domains, or unusual characters.</span></span> <span data-ttu-id="61062-116">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="61062-116">Select **Save**.</span></span>
1. <span data-ttu-id="61062-117">[ **メールボックス インテリジェンス] を** 選択し、オンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="61062-117">Select **Mailbox intelligence** and verify that it's turned on.</span></span> <span data-ttu-id="61062-118">これにより、使用パターンを学習することで、電子メールの効率が向上します。</span><span class="sxs-lookup"><span data-stu-id="61062-118">This allows your email to be more efficient by learning usage patterns.</span></span>
1. <span data-ttu-id="61062-119">[信頼 **できる送信者とドメインの追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="61062-119">Choose **Add trusted senders and domains**.</span></span> <span data-ttu-id="61062-120">ここでは、偽装として分類しない電子メール アドレスまたはドメインを追加できます。</span><span class="sxs-lookup"><span data-stu-id="61062-120">Here you can add email addresses or domains that shouldn't be classified as an impersonation.</span></span>
1. <span data-ttu-id="61062-121">[ **設定の確認] を** 選択し、すべてが正しいか確認し、[保存] 、[ **閉** じる] の順に **選択します**。</span><span class="sxs-lookup"><span data-stu-id="61062-121">Choose **Review your settings**, make sure everything is correct, select **Save**, then **Close**.</span></span>

    <span data-ttu-id="61062-122">組織では、フィッシングの脅威からの保護が強化されました。</span><span class="sxs-lookup"><span data-stu-id="61062-122">Your organization now has better protection from phishing threats.</span></span>