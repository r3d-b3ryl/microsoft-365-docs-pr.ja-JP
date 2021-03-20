---
title: 課金プロファイルを使用したサブスクリプションの支払い
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
- M365-subscription-management
- Adm_O365
search.appverid:
- MET150
description: 課金プロファイルを使用してサブスクリプションに支払う支払い方法について説明します。
ms.custom:
- okr_SMB
- AdminSurgePortfolio
- commerce
ms.openlocfilehash: 750420b6fac8fff16130710ef96a9ceb6345a87a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911832"
---
# <a name="how-to-pay-for-your-subscription-with-a-billing-profile"></a><span data-ttu-id="1a87f-103">課金プロファイルを使用してサブスクリプションの支払いを行う方法</span><span class="sxs-lookup"><span data-stu-id="1a87f-103">How to pay for your subscription with a billing profile</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="1a87f-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="1a87f-104">The admin center is changing.</span></span> <span data-ttu-id="1a87f-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](../../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a87f-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="1a87f-106">サブスクリプションを購入する場合は、課金プロファイルを使用してサブスクリプションの支払いを行います。</span><span class="sxs-lookup"><span data-stu-id="1a87f-106">When you buy a subscription, you pay for it with a billing profile.</span></span> <span data-ttu-id="1a87f-107">請求プロファイルは、特定の支払い方法にリンクされ、クレジット カードまたはデビットカード、または請求書になりますが、銀行口座にはリンクされません。</span><span class="sxs-lookup"><span data-stu-id="1a87f-107">The billing profile is linked to a specific payment method and can be a credit or debit card, or an invoice, but not a bank account.</span></span>

<span data-ttu-id="1a87f-108">アカウントに課金プロファイルがあるかどうかわからない場合は、「[課金プロファイルを理解する](manage-billing-profiles.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1a87f-108">If you’re not sure if your account has a billing profile, see [Understand billing profiles](manage-billing-profiles.md).</span></span> <span data-ttu-id="1a87f-109">課金プロファイルを持ってない場合は、「サブスクリプションの [支払い方法」を参照してください](pay-for-your-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="1a87f-109">If you don’t have a billing profile, see [How to pay for your subscription](pay-for-your-subscription.md).</span></span>

## <a name="paying-with-recurring-billing-turned-on-or-off"></a><span data-ttu-id="1a87f-110">定期的な請求を有効または無効にした場合の支払い</span><span class="sxs-lookup"><span data-stu-id="1a87f-110">Paying with recurring billing turned on or off</span></span>

<span data-ttu-id="1a87f-111">既定では、定期的な課金を使用しているすべての有料サブスクリプションに対して、定期的な課金が自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="1a87f-111">By default, recurring billing is automatically turned on for all paid subscriptions that use recurring billing.</span></span> <span data-ttu-id="1a87f-112">請求期間ごとに、請求プロファイルに関連付けられた支払い方法を自動的に請求し、その請求プロファイルを使用するサブスクリプションの支払いを行います。</span><span class="sxs-lookup"><span data-stu-id="1a87f-112">Every billing period, we automatically charge the payment method associated with the billing profile to pay for any subscriptions that use that billing profile.</span></span> <span data-ttu-id="1a87f-113">支払い方法が拒否された場合は、請求書の[今すぐ支払う] ボタンを使用して、サブスクリプションの一時支払いを行います。</span><span class="sxs-lookup"><span data-stu-id="1a87f-113">If your payment method is declined, you can use the **Pay now** button on your invoice to make a one-time payment for your subscription.</span></span>

<span data-ttu-id="1a87f-114">請求プロファイルで定期的な請求がオフになっている場合は、請求プロファイルにリンクされている支払い方法に関係なく、請求書の [今すぐ支払う] ボタンを使用して、請求期間ごとに支払いを行えます。</span><span class="sxs-lookup"><span data-stu-id="1a87f-114">If recurring billing is turned off for a billing profile, you can use the **Pay now** button on your invoice to pay for it every billing period, regardless of what payment method is linked with the billing profile.</span></span> <span data-ttu-id="1a87f-115">また、チェックまたは電子資金移動 (EFT) による支払いも可能です。</span><span class="sxs-lookup"><span data-stu-id="1a87f-115">You can also pay by check or electronic funds transfer (EFT).</span></span> <span data-ttu-id="1a87f-116">請求書の PDF コピーに記載されている方法の手順。</span><span class="sxs-lookup"><span data-stu-id="1a87f-116">Instructions for how to do that are included on the PDF copy of your invoice.</span></span>

## <a name="paying-by-invoice"></a><span data-ttu-id="1a87f-117">請求書での支払い</span><span class="sxs-lookup"><span data-stu-id="1a87f-117">Paying by invoice</span></span>

<span data-ttu-id="1a87f-118">請求書による支払いを設定されている請求プロファイルがある場合は、チェックまたは EFT を使用してサブスクリプションの支払いを行います。</span><span class="sxs-lookup"><span data-stu-id="1a87f-118">If you have a billing profile that is set up to be paid by invoice, you can pay for your subscription with a check or EFT.</span></span> <span data-ttu-id="1a87f-119">請求書の [今すぐ支払う] ボタンを使用して、クレジット カードを使用して **オンライン支払い** を行う方法も可能です。</span><span class="sxs-lookup"><span data-stu-id="1a87f-119">You can also use a credit card to make an online payment by using the **Pay now** button on your invoice.</span></span>

<span data-ttu-id="1a87f-120">請求書で支払う資格を得るには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a87f-120">To be eligible to pay by invoice, you must:</span></span>

- <span data-ttu-id="1a87f-121">既存の顧客になる</span><span class="sxs-lookup"><span data-stu-id="1a87f-121">Be an established customer</span></span>
- <span data-ttu-id="1a87f-122">サブスクリプション代金が特定の金額を超えている (この金額はサービスの場所によって異なります)</span><span class="sxs-lookup"><span data-stu-id="1a87f-122">Have a subscription cost that exceeds a certain amount (this amount varies by service location)</span></span>
- <span data-ttu-id="1a87f-123">信用調査に合格する</span><span class="sxs-lookup"><span data-stu-id="1a87f-123">Pass a credit check</span></span>

<span data-ttu-id="1a87f-124">与信審査が必要な場合、サブスクリプションを購入したときに通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="1a87f-124">If a credit check is required, you’re notified when you buy your subscription.</span></span> <span data-ttu-id="1a87f-125">Microsoft から連絡することをご了承いただいた場合、メールを受信します。メールには、クレジットの承認を申請するうえで詳細な情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1a87f-125">If you agree to be contacted, you get an email that includes more information about applying for credit approval.</span></span> <span data-ttu-id="1a87f-126">与信審査は、通常 2 営業日内に完了します。</span><span class="sxs-lookup"><span data-stu-id="1a87f-126">Credit checks are usually completed within two business days.</span></span>

<span data-ttu-id="1a87f-127">請求プロファイルが請求書に裏付けされている場合は、請求明細書を表示する準備が整ったときにメールが届きます。</span><span class="sxs-lookup"><span data-stu-id="1a87f-127">If your billing profile is backed by an invoice, you get an email when your billing statement is ready to view.</span></span> <span data-ttu-id="1a87f-128">このメールには、請求明細書のコピーは含まれません。</span><span class="sxs-lookup"><span data-stu-id="1a87f-128">This email doesn’t contain a copy of your billing statement.</span></span> <span data-ttu-id="1a87f-129">ただし、[請求明細書のコピーをメールで受け取る](view-your-bill-or-invoice.md#receive-a-copy-of-your-billing-statement-in-email) ことを選択できます。</span><span class="sxs-lookup"><span data-stu-id="1a87f-129">However, you can choose to [receive a copy of your billing statement in email](view-your-bill-or-invoice.md#receive-a-copy-of-your-billing-statement-in-email).</span></span> <span data-ttu-id="1a87f-130">請求明細書には、支払いに関するオプションとその送付先の詳細が記載されています。</span><span class="sxs-lookup"><span data-stu-id="1a87f-130">Your billing statement includes details about your options for making a payment, and where to send it.</span></span> <span data-ttu-id="1a87f-131">請求プロファイルに発注書 (PO) 番号を入力すると、その番号が請求明細書に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a87f-131">If you enter a purchase order (PO) number in your billing profile, the number appears on your billing statement.</span></span> <span data-ttu-id="1a87f-132">請求明細書へのアクセスの詳細については、「[課金内容または請求書を表示する](view-your-bill-or-invoice.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a87f-132">For information about accessing billing statements, see [View your bill or invoice](view-your-bill-or-invoice.md).</span></span>

## <a name="where-do-i-send-my-check-or-eft-payment"></a><span data-ttu-id="1a87f-133">小切手または EFT の送信はどこでできますか?</span><span class="sxs-lookup"><span data-stu-id="1a87f-133">Where do I send my check or EFT payment?</span></span>

<span data-ttu-id="1a87f-134">支払い方法については、[請求書](view-your-bill-or-invoice.md)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="1a87f-134">[Check your invoice](view-your-bill-or-invoice.md) for payment instructions.</span></span> <span data-ttu-id="1a87f-135">以下のドロップダウンを使用して、お客様の国の支払い方法を確認できます。</span><span class="sxs-lookup"><span data-stu-id="1a87f-135">You can also use the drop-down below to find payment instructions for your country.</span></span> <span data-ttu-id="1a87f-136">未払い額がわからない場合は、<a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">[請求書と支払い]</a> ページの **[請求書]** タブで、請求書と請求履歴をオンラインで確認できます。</span><span class="sxs-lookup"><span data-stu-id="1a87f-136">If you're not sure how much you owe, you can check your bill and billing history online on the **Invoices** tab of the <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>

> [!NOTE]
> <span data-ttu-id="1a87f-137">小切手による支払いはいくつかの国のみで利用可能です。</span><span class="sxs-lookup"><span data-stu-id="1a87f-137">Paying by check is only available in a few countries.</span></span>

 <span data-ttu-id="1a87f-138">**下のドロップダウン メニューから、"請求書" の国または地域を選択します。**</span><span class="sxs-lookup"><span data-stu-id="1a87f-138">**Choose your "bill-to" country or region from the drop-down menu below.**</span></span>

> [!div class="op_single_selector"]
> - **国または地域を選択します**
> - [アフガニスタン](../pay/afghanistan.md)
> - [アルバニア](../pay/albania.md)
> - [アルジェリア](../pay/algeria.md)
> - [アンゴラ](../pay/angola.md)
> - [アルゼンチン](../pay/argentina.md)
> - [アルメニア](../pay/armenia.md)
> - [オーストラリア](../pay/australia.md)
> - [Austria](../pay/austria.md)
> - [アゼルバイジャン](../pay/azerbaijan.md)
> - [バハマ](../pay/bahamas.md)
> - [バーレーン](../pay/bahrain.md)
> - [バングラデシュ](../pay/bangladesh.md)
> - [Barbados](../pay/barbados.md)
> - [Belarus (Белару́сь)](../pay/belarus.md)
> - [Belgium](../pay/belgium.md)
> - [ベリーズ](../pay/belize.md)
> - [バミューダ諸島](../pay/bermuda.md)
> - [ボリビア](../pay/bolivia.md)
> - [ボスニア・ヘルツェゴビナ](../pay/bosnia-and-herzegovina.md)
> - [ボツワナ](../pay/botswana.md)
> - [ブラジル](../pay/brazil.md)
> - [ブルネイ](../pay/brunei.md)
> - [ブルガリア](../pay/bulgaria.md)
> - [カメルーン](../pay/cameroon.md)
> - [カナダ](../pay/canada.md)
> - [Cape Verde](../pay/cape-verde.md)
> - [ケイマン諸島](../pay/cayman-islands.md)
> - [チリ](../pay/chile.md)
> - [中華人民共和国](../pay/china-prc.md)
> - [コロンビア](../pay/colombia.md)
> - [コスタリカ](../pay/costa-rica.md)
> - [Ivory Coast (Côte d'Ivoire)](../pay/cote-divoire.md)
> - [Croatia](../pay/croatia.md)
> - [Curacao](../pay/curacao.md)
> - [キプロス](../pay/cyprus.md)
> - [チェコ共和国](../pay/czech-republic.md)
> - [Democratic Republic of Congo](../pay/democratic-republic-of-congo.md)
> - [デンマーク](../pay/denmark.md)
> - [ドミニカ共和国](../pay/dominican-republic.md)
> - [エクアドル](../pay/ecuador.md)
> - [エジプト](../pay/egypt.md)
> - [エルサルバドル](../pay/el-salvador.md)
> - [エストニア](../pay/estonia.md)
> - [エチオピア](../pay/ethiopia.md)
> - [フェロー諸島](../pay/faroe-islands.md)
> - [Fiji](../pay/fiji.md)
> - [フィンランド](../pay/finland.md)
> - [France](../pay/france.md)
> - [フランス領ギアナ](../pay/french-guiana.md)
> - [ジョージア](../pay/georgia.md)
> - [Germany](../pay/germany.md)
> - [ガーナ](../pay/ghana.md)
> - [ギリシャ](../pay/greece.md)
> - [グレナダ](../pay/grenada.md)
> - [グアドループ](../pay/guadeloupe.md)
> - [グアム](../pay/guam.md)
> - [グアテマラ](../pay/guatemala.md)
> - [ガイアナ](../pay/guyana.md)
> - [ハイチ](../pay/haiti.md)
> - [ホンジュラス](../pay/honduras.md)
> - [香港特別行政区](../pay/hong-kong.md)
> - [ハンガリー](../pay/hungary.md)
> - [アイスランド](../pay/iceland.md)
> - [India](../pay/india.md)
> - [Indonesia](../pay/indonesia.md)
> - [Iraq](../pay/iraq.md)
> - [アイルランド](../pay/ireland.md)
> - [イスラエル](../pay/israel.md)
> - [イタリア](../pay/italy.md)
> - [ジャマイカ](../pay/jamaica.md)
> - [日本](../pay/japan.md)
> - [ヨルダン](../pay/jordan.md)
> - [カザフスタン](../pay/kazakhstan.md)
> - [ケニア](../pay/kenya.md)
> - [韓国](../pay/korea.md)
> - [クウェート](../pay/kuwait.md)
> - [キルギスタン](../pay/kyrgyzstan.md)
> - [ラトビア](../pay/latvia.md)
> - [レバノン](../pay/lebanon.md)
> - [リビア](../pay/libya.md)
> - [Liechtenstein](../pay/liechtenstein.md)
> - [Lithuania](../pay/lithuania.md)
> - [ルクセンブルク](../pay/luxembourg.md)
> - [マカオ](../pay/macao.md)
> - [マケドニア、旧ユーゴスラビア共和国](../pay/macedonia.md)
> - [マレーシア](../pay/malaysia.md)
> - [マルタ](../pay/malta.md)
> - [モーリシャス](../pay/mauritius.md)
> - [メキシコ](../pay/mexico.md)
> - [モルドバ](../pay/moldova.md)
> - [Monaco](../pay/monaco.md)
> - [Mongolia](../pay/mongolia.md)
> - [モンテネグロ](../pay/montenegro.md)
> - [モロッコ](../pay/morocco.md)
> - [ナミビア](../pay/namibia.md)
> - [ネパール](../pay/nepal.md)
> - [オランダ](../pay/netherlands.md)
> - [ニュージーランド](../pay/new-zealand.md)
> - [ニカラグア](../pay/nicaragua.md)
> - [ナイジェリア](../pay/nigeria.md)
> - [ノルウェー](../pay/norway.md)
> - [オマーン](../pay/oman.md)
> - [パキスタン](../pay/pakistan.md)
> - [パレスチナ自治政府](../pay/palestinian-authority.md)
> - [パナマ](../pay/panama.md)
> - [パラグアイ](../pay/paraguay.md)
> - [Peru](../pay/peru.md)
> - [フィリピン](../pay/philippines.md)
> - [ポーランド](../pay/poland.md)
> - [Portugal](../pay/portugal.md)
> - [Puerto Rico](../pay/puerto-rico.md)
> - [カタール](../pay/qatar.md)
> - [ルーマニア](../pay/romania.md)
> - [Russia](../pay/russia.md)
> - [ルワンダ](../pay/rwanda.md)
> - [セントクリストファー・ネーヴィス](../pay/saint-kitts-and-nevis.md)
> - [セントルシア](../pay/saint-lucia.md)
> - [セントビンセント グレナディーン](../pay/saint-vincent-and-the-grenadines.md)
> - [サウジアラビア](../pay/saudi-arabia.md)
> - [Senegal](../pay/senegal.md)
> - [セルビア](../pay/serbia.md)
> - [シンガポール](../pay/singapore.md)
> - [スロバキア](../pay/slovakia.md)
> - [スロベニア](../pay/slovenia.md)
> - [南アフリカ](../pay/south-africa.md)
> - [スペイン](../pay/spain.md)
> - [スリランカ](../pay/sri-lanka.md)
> - [スリナム](../pay/suriname.md)
> - [スウェーデン](../pay/sweden.md)
> - [Switzerland](../pay/switzerland.md)
> - [台湾](../pay/taiwan.md)
> - [Tajikistan](../pay/tajikistan.md)
> - [Tanzania](../pay/tanzania.md)
> - [タイ](../pay/thailand.md)
> - [Trinidad and Tobago](../pay/trinidad-and-tobago.md)
> - [トルクメニスタン](../pay/turkmenistan.md)
> - [チュニジア](../pay/tunisia.md)
> - [トルコ](../pay/turkey.md)
> - [ウガンダ](../pay/uganda.md)
> - [ウクライナ](../pay/ukraine.md)
> - [アラブ首長国連邦](../pay/united-arab-emirates.md)
> - [英国](../pay/united-kingdom.md)
> - [米国](../pay/united-states.md)
> - [Uruguay](../pay/uruguay.md)
> - [ウズベキスタン](../pay/uzbekistan.md)
> - [ベネズエラ](../pay/venezuela.md)
> - [Vietnam](../pay/vietnam.md)
> - [ヴァージン諸島 (米国)](../pay/virgin-islands.md)
> - [イエメン](../pay/yemen.md)
> - [ザンビア](../pay/zambia.md)
> - [ジンバブエ](../pay/zimbabwe.md)

## <a name="can-i-pay-my-invoice-online"></a><span data-ttu-id="1a87f-291">請求書をオンラインで支払うことはできますか?</span><span class="sxs-lookup"><span data-stu-id="1a87f-291">Can I pay my invoice online?</span></span>

<span data-ttu-id="1a87f-292">請求プロファイルで定期的な請求がオフになっている場合は、クレジット カードを使用して請求書をオンラインで支払えます。</span><span class="sxs-lookup"><span data-stu-id="1a87f-292">If recurring billing is turned off for your billing profile, you can use a credit card to pay your invoice online.</span></span> <span data-ttu-id="1a87f-293">支払いを行う場合は、Microsoft 365 管理センターの請求書の [今すぐ支払う] ボタンを使用します。</span><span class="sxs-lookup"><span data-stu-id="1a87f-293">To make a payment, use the **Pay now** button on your invoice in the Microsoft 365 admin center.</span></span> <span data-ttu-id="1a87f-294">請求書を見つけるには、「請求書または [請求書を表示する」を参照してください](view-your-bill-or-invoice.md)。</span><span class="sxs-lookup"><span data-stu-id="1a87f-294">To find your invoice, see [View your bill or invoice](view-your-bill-or-invoice.md).</span></span>

## <a name="can-i-change-from-my-current-payment-method-to-paying-by-invoice"></a><span data-ttu-id="1a87f-295">現在の支払い方法から請求書による支払いに変更できますか?</span><span class="sxs-lookup"><span data-stu-id="1a87f-295">Can I change from my current payment method to paying by invoice?</span></span>

<span data-ttu-id="1a87f-296">請求プロファイルがクレジット カードまたはデビットカードに裏付けされている場合は、支払い方法を別のクレジット カードまたはデビットカードにのみ変更できます。</span><span class="sxs-lookup"><span data-stu-id="1a87f-296">If your billing profile is backed by credit or debit card, you can only change the payment method to another credit or debit card.</span></span> <span data-ttu-id="1a87f-297">請求書による支払いには変更できない。</span><span class="sxs-lookup"><span data-stu-id="1a87f-297">You can’t change to paying by invoice.</span></span>

## <a name="can-i-change-from-paying-by-invoice-to-using-a-different-payment-method"></a><span data-ttu-id="1a87f-298">請求書による支払いから別の支払い方法の使用に変更できますか?</span><span class="sxs-lookup"><span data-stu-id="1a87f-298">Can I change from paying by invoice to using a different payment method?</span></span>

<span data-ttu-id="1a87f-299">請求プロファイルが請求書支払いによって裏付けられている場合は、支払い方法を変更できます。</span><span class="sxs-lookup"><span data-stu-id="1a87f-299">If your billing profile is backed by invoice payments, you can’t change the payment method.</span></span> <span data-ttu-id="1a87f-300">請求書の [今 **すぐ支払う** ] ボタンを使用して、クレジット カードまたはデビットカード、またはチェックまたは EFT で支払いを行います。</span><span class="sxs-lookup"><span data-stu-id="1a87f-300">You can use the **Pay now** button on your invoice to pay with a credit or debit card, or by check or EFT.</span></span>

## <a name="related-content"></a><span data-ttu-id="1a87f-301">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="1a87f-301">Related content</span></span>

<span data-ttu-id="1a87f-302">[支払方法を管理する](manage-payment-methods.md) (article)</span><span class="sxs-lookup"><span data-stu-id="1a87f-302">[Manage payment methods](manage-payment-methods.md) (article)</span></span>\
<span data-ttu-id="1a87f-303">[課金内容または請求書を表示する](view-your-bill-or-invoice.md) (article)</span><span class="sxs-lookup"><span data-stu-id="1a87f-303">[View your bill or invoice](view-your-bill-or-invoice.md) (article)</span></span>\
<span data-ttu-id="1a87f-304">[課金内容または請求書の内容を理解する](understand-your-invoice.md) (article)\</span><span class="sxs-lookup"><span data-stu-id="1a87f-304">[Understand your bill or invoice](understand-your-invoice.md) (article)</span></span>