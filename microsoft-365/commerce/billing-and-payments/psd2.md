---
title: 商用顧客向け Payment Services ディレクティブ 2 と強力な顧客認証
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jamitche, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_billing
search.appverid: MET150
description: 2019 年 9 月 14 日現在、欧州経済地域の 31 か国の銀行は、支払いを処理する前に、オンライン購入を行う人物の身元を確認する必要があります。
keywords: payment services ディレクティブ 2、強力な顧客認証、多要素認証
ms.date: 11/03/2020
ms.openlocfilehash: bbbbe9f53c11fcae9c35cda1fd4e7d4b51a9c767
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2021
ms.locfileid: "52331945"
---
# <a name="payment-services-directive-2-and-strong-customer-authentication-for-commercial-customers"></a><span data-ttu-id="6e6e1-104">商用顧客向け Payment Services ディレクティブ 2 と強力な顧客認証</span><span class="sxs-lookup"><span data-stu-id="6e6e1-104">Payment Services Directive 2 and Strong Customer Authentication for commercial customers</span></span>

<span data-ttu-id="6e6e1-105">2019 年 9 月 14 日現在、欧州経済地域の 31 か国の銀行は、支払いを処理する前に、オンライン購入を行う人物の身元を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e6e1-105">As of September 14, 2019, banks in the 31 countries of the European Economic Area are required to verify the identity of the person making an online purchase before the payment can be processed.</span></span> <span data-ttu-id="6e6e1-106">この検証では、オンライン購入の安全性と保護を確保するために多要素認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="6e6e1-106">This verification requires multi-factor authentication to help ensure your online purchases are secure and protected.</span></span> <span data-ttu-id="6e6e1-107">この検証要件の日付は、一部の国では遅れる予定です。</span><span class="sxs-lookup"><span data-stu-id="6e6e1-107">The date for this verification requirement will be delayed for some countries.</span></span>

<span data-ttu-id="6e6e1-108">詳細については、「Payment Services ディレクティブ 2」および「強力な顧客認証」に関する Microsoft [FAQ を参照してください](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication)。</span><span class="sxs-lookup"><span data-stu-id="6e6e1-108">For more information, see [Microsoft FAQ about Payment Services Directive 2 and Strong Customer Authentication](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication).</span></span>

## <a name="when-is-multi-factor-authentication-required"></a><span data-ttu-id="6e6e1-109">多要素認証が必要な場合</span><span class="sxs-lookup"><span data-stu-id="6e6e1-109">When is multi-factor authentication required?</span></span>

<span data-ttu-id="6e6e1-110">現在、多要素認証を使用したこのディレクティブの検証要件は、欧州経済地域の 31 か国の銀行のクレジット カードを使用しているお客様にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="6e6e1-110">Currently, verification requirements for this directive using multi-factor authentication only apply to customers using credit cards from banks in the 31 countries of the European Economic Area.</span></span> <span data-ttu-id="6e6e1-111">ユーザーが実行したアクションが理由でメッセージが表示される場合や、既存のサブスクリプションまたはサービスのイベントのためにメッセージが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="6e6e1-111">Sometimes customers will be prompted because of an action that they took, and sometimes they are prompted because of events with their existing subscriptions or services.</span></span>

### <a name="customer-actions"></a><span data-ttu-id="6e6e1-112">顧客のアクション</span><span class="sxs-lookup"><span data-stu-id="6e6e1-112">Customer Actions</span></span>

<span data-ttu-id="6e6e1-113">銀行では、多要素認証による検証が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="6e6e1-113">Your bank may require verification through multi-factor authentication.</span></span> <span data-ttu-id="6e6e1-114">以下に例を挙げます。</span><span class="sxs-lookup"><span data-stu-id="6e6e1-114">Some examples include:</span></span>

- <span data-ttu-id="6e6e1-115">新しいサブスクリプションにサインアップする</span><span class="sxs-lookup"><span data-stu-id="6e6e1-115">Signing up for a new subscription</span></span>
- <span data-ttu-id="6e6e1-116">サブスクリプションへのライセンスの追加</span><span class="sxs-lookup"><span data-stu-id="6e6e1-116">Adding licenses to a subscription</span></span>
- <span data-ttu-id="6e6e1-117">サブスクリプションまたはサービスの支払いに使用するクレジット カードの追加または交換</span><span class="sxs-lookup"><span data-stu-id="6e6e1-117">Adding or replacing the credit card used to pay for a subscription or service</span></span>
- <span data-ttu-id="6e6e1-118">請求プロファイルでのクレジット カードの追加または置き換え</span><span class="sxs-lookup"><span data-stu-id="6e6e1-118">Adding or replacing a credit card on a billing profile</span></span>
- <span data-ttu-id="6e6e1-119">アプリの購入</span><span class="sxs-lookup"><span data-stu-id="6e6e1-119">Buying apps</span></span>

### <a name="subscription-lifecycle-events"></a><span data-ttu-id="6e6e1-120">サブスクリプション ライフサイクル イベント</span><span class="sxs-lookup"><span data-stu-id="6e6e1-120">Subscription lifecycle events</span></span>

<span data-ttu-id="6e6e1-121">定期的な支払いの料金が失敗する場合があります。</span><span class="sxs-lookup"><span data-stu-id="6e6e1-121">Charges for recurring payments might fail.</span></span> <span data-ttu-id="6e6e1-122">その場合は、フォローする指示が記載されたメールが届きます。</span><span class="sxs-lookup"><span data-stu-id="6e6e1-122">If they do, you’ll receive an email with instructions to follow.</span></span> <span data-ttu-id="6e6e1-123">確認要求に応答し、現在の支払いを行うメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e6e1-123">You’ll be prompted to respond to the verification request and make your current payment.</span></span>

## <a name="need-more-help"></a><span data-ttu-id="6e6e1-124">ヘルプを表示</span><span class="sxs-lookup"><span data-stu-id="6e6e1-124">Need more help?</span></span>

<span data-ttu-id="6e6e1-125">金融機関は、次のシナリオに最適な連絡先です。</span><span class="sxs-lookup"><span data-stu-id="6e6e1-125">Your financial institution is the best contact for these scenarios:</span></span>

- <span data-ttu-id="6e6e1-126">確認コードを受け取りなかった。</span><span class="sxs-lookup"><span data-stu-id="6e6e1-126">You didn't receive a verification code.</span></span>  
- <span data-ttu-id="6e6e1-127">確認コードを送信した後、検証プロセスが機能しなかった。</span><span class="sxs-lookup"><span data-stu-id="6e6e1-127">The verification process didn't work after you submitted the verification code.</span></span>
- <span data-ttu-id="6e6e1-128">クレジット カードの連絡先情報が正しいかは不明です。</span><span class="sxs-lookup"><span data-stu-id="6e6e1-128">You're not sure if the contact info for your credit card is correct.</span></span>
