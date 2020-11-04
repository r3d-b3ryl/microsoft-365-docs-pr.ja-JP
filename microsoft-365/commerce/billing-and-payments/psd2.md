---
title: 一般法人向けお客様向けのお支払いサービス指令2および強力な顧客認証
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: 2019年9月14日の場合、この金額を処理する前に、オンライン購入を行うユーザーの id を確認するには、欧州経済地域の31国の銀行が必要になります。
keywords: 支払いサービスディレクティブ2、強力な顧客認証、多要素認証
ms.openlocfilehash: d6564a8c6d31bd0758f1084e7ee9b6857aed034e
ms.sourcegitcommit: 7355cc8871cde5fac6d7d6dcecc3e41e35601623
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2020
ms.locfileid: "48906611"
---
# <a name="payment-services-directive-2-and-strong-customer-authentication-for-commercial-customers"></a><span data-ttu-id="65c68-104">一般法人向けお客様向けのお支払いサービス指令2および強力な顧客認証</span><span class="sxs-lookup"><span data-stu-id="65c68-104">Payment Services Directive 2 and Strong Customer Authentication for commercial customers</span></span>

<span data-ttu-id="65c68-105">2019年9月14日の場合、この金額を処理する前に、オンライン購入を行うユーザーの id を確認するには、欧州経済地域の31国の銀行が必要です。</span><span class="sxs-lookup"><span data-stu-id="65c68-105">As of September 14, 2019, banks in the 31 countries of the European Economic Area are required to verify the identity of the person making an online purchase before the payment can be processed.</span></span> <span data-ttu-id="65c68-106">この検証では、オンライン購入が安全で保護されていることを確認するために、多要素認証が必要になります。</span><span class="sxs-lookup"><span data-stu-id="65c68-106">This verification requires multi-factor authentication to help ensure your online purchases are secure and protected.</span></span> <span data-ttu-id="65c68-107">この検証要件の日付は、一部の国では遅延されます。</span><span class="sxs-lookup"><span data-stu-id="65c68-107">The date for this verification requirement will be delayed for some countries.</span></span>

<span data-ttu-id="65c68-108">詳細については、「Microsoft FAQ」を参照してください。 [支払いサービスディレクティブ2と強力な顧客認証について説明](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication)します。</span><span class="sxs-lookup"><span data-stu-id="65c68-108">For more information, see [Microsoft FAQ about Payment Services Directive 2 and Strong Customer Authentication](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication).</span></span>

## <a name="when-is-multi-factor-authentication-required"></a><span data-ttu-id="65c68-109">多要素認証が必要になるのはいつですか?</span><span class="sxs-lookup"><span data-stu-id="65c68-109">When is multi-factor authentication required?</span></span>

<span data-ttu-id="65c68-110">現時点では、多要素認証を使用したこのディレクティブの検証要件は、欧州経済地域の31か国の銀行のクレジットカードを使用しているお客様にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="65c68-110">Currently, verification requirements for this directive using multi-factor authentication only apply to customers using credit cards from banks in the 31 countries of the European Economic Area.</span></span> <span data-ttu-id="65c68-111">場合によっては、ユーザーが実行したアクションのためにユーザーにメッセージが表示され、既存のサブスクリプションまたはサービスに対するイベントによってメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="65c68-111">Sometimes customers will be prompted because of an action that they took, and sometimes they are prompted because of events with their existing subscriptions or services.</span></span>

### <a name="customer-actions"></a><span data-ttu-id="65c68-112">顧客のアクション</span><span class="sxs-lookup"><span data-stu-id="65c68-112">Customer Actions</span></span>

<span data-ttu-id="65c68-113">銀行が多要素認証を使用して検証する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="65c68-113">Your bank may require verification through multi-factor authentication.</span></span> <span data-ttu-id="65c68-114">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="65c68-114">Some examples include:</span></span>
- <span data-ttu-id="65c68-115">新しいサブスクリプションにサインアップする</span><span class="sxs-lookup"><span data-stu-id="65c68-115">Signing up for a new subscription</span></span>
- <span data-ttu-id="65c68-116">サブスクリプションにライセンスを追加する</span><span class="sxs-lookup"><span data-stu-id="65c68-116">Adding licenses to a subscription</span></span>
- <span data-ttu-id="65c68-117">サブスクリプションまたはサービスの支払いに使用するクレジットカードを追加または置換する</span><span class="sxs-lookup"><span data-stu-id="65c68-117">Adding or replacing the credit card used to pay for a subscription or service</span></span>
- <span data-ttu-id="65c68-118">課金プロファイルのクレジットカードを追加または置換する</span><span class="sxs-lookup"><span data-stu-id="65c68-118">Adding or replacing a credit card on a billing profile</span></span>
- <span data-ttu-id="65c68-119">アプリの購入</span><span class="sxs-lookup"><span data-stu-id="65c68-119">Buying apps</span></span>

### <a name="subscription-lifecycle-events"></a><span data-ttu-id="65c68-120">サブスクリプションライフサイクルイベント</span><span class="sxs-lookup"><span data-stu-id="65c68-120">Subscription lifecycle events</span></span>

<span data-ttu-id="65c68-121">定期的な支払いに対する請求は失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="65c68-121">Charges for recurring payments might fail.</span></span> <span data-ttu-id="65c68-122">その場合は、手順に従って電子メールを受信します。</span><span class="sxs-lookup"><span data-stu-id="65c68-122">If they do, you’ll receive an email with instructions to follow.</span></span> <span data-ttu-id="65c68-123">確認要求に応答して、現在の支払いを行うように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="65c68-123">You’ll be prompted to respond to the verification request and make your current payment.</span></span>

## <a name="need-more-help"></a><span data-ttu-id="65c68-124">ヘルプを表示</span><span class="sxs-lookup"><span data-stu-id="65c68-124">Need more help?</span></span>

<span data-ttu-id="65c68-125">これらのシナリオでは、金融機関が最適な連絡先です。</span><span class="sxs-lookup"><span data-stu-id="65c68-125">Your financial institution is the best contact for these scenarios:</span></span>
- <span data-ttu-id="65c68-126">確認コードを受信していません。</span><span class="sxs-lookup"><span data-stu-id="65c68-126">You didn't receive a verification code.</span></span>  
- <span data-ttu-id="65c68-127">検証コードを送信した後、検証プロセスが正常に実行されませんでした。</span><span class="sxs-lookup"><span data-stu-id="65c68-127">The verification process didn't work after you submitted the verification code.</span></span>
- <span data-ttu-id="65c68-128">クレジットカードの連絡先情報が正しいかどうかがわからない。</span><span class="sxs-lookup"><span data-stu-id="65c68-128">You're not sure if the contact info for your credit card is correct.</span></span>
