---
title: サブスクリプションの支払い
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
search.appverid: MET150
description: Microsoft 365 for business サブスクリプションのお支払いには、クレジット カード、デビット カード、銀行口座をご利用ください。場合によっては、請求書によるお支払いも可能です。
ms.custom:
- okr_SMB
- fwlink 808700 for SEPA UI glink 906 for older uI
- AdminSurgePortfolio
- commerce_billing
- AdminTemplateSet
ms.date: 05/04/2021
ms.openlocfilehash: 128107630580bb1594d61313c6469bb83a4adfc1
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394607"
---
# <a name="how-to-pay-for-your-subscription"></a><span data-ttu-id="59109-103">サブスクリプションの支払い方法</span><span class="sxs-lookup"><span data-stu-id="59109-103">How to pay for your subscription</span></span>

> [!IMPORTANT]
> <span data-ttu-id="59109-104">2021 年 1 月 26 日をもって、ベルギー、フランス、イタリア、ルクセンブルグ、ポルトガル、スペイン、および米国のお客様に、新しい銀行口座をサポートしなくなりました。</span><span class="sxs-lookup"><span data-stu-id="59109-104">As of January 26, 2021, new bank accounts are no longer supported for customers in Belgium, France, Italy, Luxembourg, Portugal, Spain, and the United States.</span></span> <span data-ttu-id="59109-105">これらの国のいずれかの既存のお客様である場合、既存の銀行口座で引き続きサブスクリプションの支払いを行い、新しいサブスクリプションを追加できますが、銀行口座が良好な状態である場合に限ります。</span><span class="sxs-lookup"><span data-stu-id="59109-105">If you’re an existing customer in one of those countries, you can continue paying for your subscription with an existing bank account, and you can add new subscriptions to it, but only as long as the bank account is in good standing.</span></span>

<span data-ttu-id="59109-106">クレジットカード、デビットカード、または銀行口座を使用して、サブスクリプションの支払いを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="59109-106">You can use a credit or debit card, or bank account to pay for your subscription.</span></span> <span data-ttu-id="59109-107">場合によっては、小切手または銀行口座振込 (EFT) を使用して、請求書で支払うこともできます。</span><span class="sxs-lookup"><span data-stu-id="59109-107">In some cases, you can pay by invoice, using check or electronic funds transfer (EFT).</span></span> <span data-ttu-id="59109-108">課金プロファイルがある場合、オプションは少し異なります。</span><span class="sxs-lookup"><span data-stu-id="59109-108">If you have a billing profile, your options are slightly different.</span></span> <span data-ttu-id="59109-109">詳細については、「[課金プロファイルを使用してサブスクリプションの支払いをする方法](pay-for-subscription-billing-profile.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59109-109">For more information, see [How to pay for your subscription with a billing profile](pay-for-subscription-billing-profile.md).</span></span> <span data-ttu-id="59109-110">アカウントに課金プロファイルがあるかどうかわからない場合は、「[課金プロファイルを理解する](manage-billing-profiles.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="59109-110">If you’re not sure if your account has a billing profile, see [Understand billing profiles](manage-billing-profiles.md).</span></span>

<span data-ttu-id="59109-111">**請求書の支払い先をお知りになりたいですか?**</span><span class="sxs-lookup"><span data-stu-id="59109-111">**Just want to find out where to send your invoice payment?**</span></span> <span data-ttu-id="59109-112">小切手または銀行口座振込 (EFT) で請求書を支払う場合は、「[小切手または EFT の送信はどこでできますか?](#where-do-i-send-my-check-or-eft-payment)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59109-112">If you pay your invoice by check or electronic funds transfer (EFT), see [Where do I send my check or EFT payment?](#where-do-i-send-my-check-or-eft-payment)</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="59109-113">はじめに</span><span class="sxs-lookup"><span data-stu-id="59109-113">Before you begin</span></span>

- <span data-ttu-id="59109-114">この記事で説明されている手順を実行するには、全体管理者または課金管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="59109-114">You must be a Global or Billing admin to do the steps described in this article.</span></span> <span data-ttu-id="59109-115">詳細については、「[管理者ロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59109-115">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="59109-p105">チェックアウト時に選択するお支払い方法は、今後のすべての請求期間に使用されるお支払い方法です。いつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="59109-p105">The payment method that you choose during checkout is the payment method that we use for all future billing periods. You can change it at any time.</span></span>

## <a name="paying-by-credit-or-debit-card-or-bank-account"></a><span data-ttu-id="59109-118">クレジット カード、デビット カード、または銀行口座引き落としでの支払い</span><span class="sxs-lookup"><span data-stu-id="59109-118">Paying by credit or debit card, or bank account</span></span>

> [!IMPORTANT]
> <span data-ttu-id="59109-119">一部の国または地域では、銀行口座引き落としによる支払いを利用できません。</span><span class="sxs-lookup"><span data-stu-id="59109-119">Paying by bank account is not available in some countries or regions.</span></span>

<span data-ttu-id="59109-120">サブスクリプションはクレジット カード、デビット カード、または銀行口座引き落としでお支払いいただけます。</span><span class="sxs-lookup"><span data-stu-id="59109-120">You can pay for your subscription with a credit or debit card, or a bank account.</span></span> <span data-ttu-id="59109-121">これらの支払い方法のいずれかでお支払いの場合、サブスクリプションの有効期限が切れるまで、またはキャンセルされるまで、その支払い方法に引き続き請求されます。</span><span class="sxs-lookup"><span data-stu-id="59109-121">When you pay with one of these payment methods, we continue to charge that payment method until the subscription expires, or is canceled.</span></span> <span data-ttu-id="59109-122">いつでも必要なときに[支払い方法を管理する](manage-payment-methods.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="59109-122">You can [manage payment methods](manage-payment-methods.md) whenever you need to.</span></span> <span data-ttu-id="59109-123">また、[請求明細書のコピーをメールで受け取る](view-your-bill-or-invoice.md#receive-a-copy-of-your-billing-statement-in-email) こともできます。</span><span class="sxs-lookup"><span data-stu-id="59109-123">You can also choose to [receive a copy of your billing statement in email](view-your-bill-or-invoice.md#receive-a-copy-of-your-billing-statement-in-email).</span></span>

## <a name="paying-by-invoice"></a><span data-ttu-id="59109-124">請求書での支払い</span><span class="sxs-lookup"><span data-stu-id="59109-124">Paying by invoice</span></span>

<span data-ttu-id="59109-125">場合によっては、小切手または EFT を使用した請求書でサブスクリプションの支払いを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="59109-125">In some cases, you can pay for your subscription by invoice with a check or EFT.</span></span> <span data-ttu-id="59109-126">請求書で支払う資格を得るには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="59109-126">To be eligible to pay by invoice, you must:</span></span>

- <span data-ttu-id="59109-127">既存の顧客になる</span><span class="sxs-lookup"><span data-stu-id="59109-127">Be an established customer</span></span>
- <span data-ttu-id="59109-128">サブスクリプション代金が特定の金額を超えている (この金額はサービスの場所によって異なります)</span><span class="sxs-lookup"><span data-stu-id="59109-128">Have a subscription cost that exceeds a certain amount (this amount varies by service location)</span></span>
- <span data-ttu-id="59109-129">信用調査に合格する</span><span class="sxs-lookup"><span data-stu-id="59109-129">Pass a credit check</span></span>

<span data-ttu-id="59109-p108">与信審査が必要な場合、サブスクリプションの購入時に、その必要性がお客様に知らされます。Microsoft からの連絡にご同意いただいた場合、クレジット カードの承認申請に関して詳細な情報が記載されたメールがお客様宛てに送信されます。与信審査は、通常 2 営業日以内で完了します。</span><span class="sxs-lookup"><span data-stu-id="59109-p108">If a credit check is required, you’re notified when you buy your subscription. If you agree to be contacted, you get an email that includes more information about applying for credit approval. Credit checks are usually completed within two business days.</span></span>

> [!NOTE]
> <span data-ttu-id="59109-133">ブラジルにお住まいのお客様は、Boleto Bancario でサブスクリプションの支払いを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="59109-133">Customers who live in Brazil can pay for a subscription with a Boleto Bancario.</span></span> <span data-ttu-id="59109-134">このオプションを選択すると、サブスクリプションの購入により、注文日から 10 日以内に支払いについての連絡が指定のメールに送信されます。</span><span class="sxs-lookup"><span data-stu-id="59109-134">If you have selected this option, the billet for payment is sent to the email provided during subscription purchase within 10 working days after the order date.</span></span> <span data-ttu-id="59109-135">期限は、注文日から 30 日です。</span><span class="sxs-lookup"><span data-stu-id="59109-135">The due date is 30 days after the order date.</span></span> <span data-ttu-id="59109-136">Boleto のメールを受信しない場合は、迷惑メール フォルダーを確認するか、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="59109-136">If you don't receive your Boleto by email, check your spam folder or contact support.</span></span>
>
> <span data-ttu-id="59109-137">もしくは、口座間の電子決済により支払いを行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="59109-137">If you prefer, you can pay by electronic transfer between accounts.</span></span> <span data-ttu-id="59109-138">銀行と口座番号は請求書の下部に記載されています。</span><span class="sxs-lookup"><span data-stu-id="59109-138">The Agency and account number are at the bottom of your invoice.</span></span> <span data-ttu-id="59109-139">振替 ID の欄に請求書番号を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59109-139">You must enter your invoice number in the Transfer identification field.</span></span>

<span data-ttu-id="59109-p111">サブスクリプションを請求書でお支払いになる場合、請求明細書が閲覧できるようになったとき、通知メールが届きます。このメールには、請求明細書のコピーは含まれません。しかし、[請求明細書のコピーをメールで受け取る](view-your-bill-or-invoice.md#receive-a-copy-of-your-billing-statement-in-email)ことを選択することができます。請求明細書には、支払いに関するオプションとその送付先に関する詳細が記載されています。サブスクリプションを購入するときに発注書番号 (PO) を入力した場合、請求明細書にその番号が表示されます。請求明細書にアクセスする詳細については、「[課金内容または請求書を表示する](view-your-bill-or-invoice.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59109-p111">If you pay by invoice for your subscription, you get an email when your billing statement is ready to view. This email doesn’t contain a copy of your billing statement. However, you can choose to [receive a copy of your billing statement in email](view-your-bill-or-invoice.md#receive-a-copy-of-your-billing-statement-in-email). Your billing statement includes details about your options for making a payment, and where to send it. If you enter a purchase order (PO) number when you buy a subscription, the number appears on your billing statement. For information about accessing billing statements, see [View your bill or invoice](view-your-bill-or-invoice.md).</span></span>

## <a name="what-if-i-have-an-outstanding-balance"></a><span data-ttu-id="59109-146">未払額がある場合、どうなりますか。</span><span class="sxs-lookup"><span data-stu-id="59109-146">What if I have an outstanding balance?</span></span>

<span data-ttu-id="59109-147">登録されているお支払い方法に請求できない場合は、問題があることを通知するメールを送信します。</span><span class="sxs-lookup"><span data-stu-id="59109-147">If we’re unable to charge the payment method on file, we send an email that lets you know there’s a problem.</span></span> <span data-ttu-id="59109-148">メールには、問題が何であるかが簡単に記載されており、未払いの残高を確認できるリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="59109-148">The email briefly states what the problem is and includes a link where you can check the outstanding balance.</span></span> <span data-ttu-id="59109-149">30 日間、数日ごとにトランザクションを再試行し続けます。その間、サブスクリプションは猶予期間中です。</span><span class="sxs-lookup"><span data-stu-id="59109-149">We continue to retry the transaction every few days for 30 days, during which time the subscription is in a grace period.</span></span> <span data-ttu-id="59109-150">トランザクションが失敗するたびに、失敗に関するメール アラートを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="59109-150">Every time a transaction fails, you receive an email alert about the failure.</span></span>

<span data-ttu-id="59109-151">延滞金額のあるお支払い方法を個人的に追加した場合は、**決済残高** を使用して支払いを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="59109-151">If you personally added the payment method that has a past due amount, you can use **Settle balance** to make a payment.</span></span> <span data-ttu-id="59109-152">延滞金額の支払いに使用する支払い方法は、拒否された支払い方法を使用したすべてのサブスクリプションの新しい支払い方法になります。</span><span class="sxs-lookup"><span data-stu-id="59109-152">The payment method that you use to pay the overdue amount becomes the new payment method for all subscriptions that used the declined payment method.</span></span>

1. <span data-ttu-id="59109-153">管理センターで、**[課金]** > **[請求と支払い]** ページに移動し、<a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">[支払い方法]</a> タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="59109-153">In the admin center, go to the **Billing** > **Bills & payments** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> tab.</span></span>
1. <span data-ttu-id="59109-154">警告メッセージは、どの支払い方法が拒否されたかを示します。</span><span class="sxs-lookup"><span data-stu-id="59109-154">A warning message says which payment method was declined.</span></span> <span data-ttu-id="59109-155">**[残高の決済]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="59109-155">Select **Settle balance**.</span></span>
1. <span data-ttu-id="59109-156">右側のウィンドウで、別の支払い方法を選択するか、**[新しい支払い方法を追加する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="59109-156">In the right pane, choose a different payment method, or select **Add a new payment method**.</span></span>
1. <span data-ttu-id="59109-157">お支払い方法の情報を更新したら、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="59109-157">After you've updated the payment method information, select **Save**.</span></span>

<span data-ttu-id="59109-158">サブスクリプションの支払いに使用した支払い方法を追加しなかった場合は、以前に追加した支払い方法または新しい支払い方法に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="59109-158">If you didn’t add the payment method used to pay for the subscription, you must replace the payment method with one you previously added, or with a new one.</span></span>

## <a name="where-do-i-send-my-check-or-eft-payment"></a><span data-ttu-id="59109-159">小切手または EFT の送信はどこでできますか?</span><span class="sxs-lookup"><span data-stu-id="59109-159">Where do I send my check or EFT payment?</span></span>

<span data-ttu-id="59109-160">支払い方法については、[請求書](view-your-bill-or-invoice.md)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="59109-160">[Check your invoice](view-your-bill-or-invoice.md) for payment instructions.</span></span> <span data-ttu-id="59109-161">下のドロップダウンを使用して、お住まいの国または地域で利用できるお支払い方法を見つけることもできます。</span><span class="sxs-lookup"><span data-stu-id="59109-161">You can also use the drop-down below to find payment instructions for your country or region.</span></span> <span data-ttu-id="59109-162">未払い額がわからない場合は、<a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">[請求書と支払い]</a> ページの **[請求書]** タブで、請求書と請求履歴をオンラインで確認できます。</span><span class="sxs-lookup"><span data-stu-id="59109-162">If you're not sure how much you owe, you can check your bill and billing history online on the **Invoices** tab of the <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>

> [!NOTE]
> <span data-ttu-id="59109-163">小切手による支払いはいくつかの国のみで利用可能です。</span><span class="sxs-lookup"><span data-stu-id="59109-163">Paying by check is only available in a few countries.</span></span>

 <span data-ttu-id="59109-164">**下のドロップダウン メニューから、"請求書" の国または地域を選択します。**</span><span class="sxs-lookup"><span data-stu-id="59109-164">**Choose your "bill-to" country or region from the drop-down menu below.**</span></span>

> [!div class="op_single_selector"]
>
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

## <a name="can-i-pay-my-invoice-online"></a><span data-ttu-id="59109-317">請求書をオンラインで支払うことはできますか?</span><span class="sxs-lookup"><span data-stu-id="59109-317">Can I pay my invoice online?</span></span>

<span data-ttu-id="59109-318">請求書をオンラインで支払うことはできません。</span><span class="sxs-lookup"><span data-stu-id="59109-318">You can’t pay your invoice online.</span></span> <span data-ttu-id="59109-319">小切手または EFT のいずれかで送金する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59109-319">You must remit payment via either check or EFT.</span></span>

## <a name="can-i-change-from-my-current-payment-method-to-paying-by-invoice"></a><span data-ttu-id="59109-320">現在の支払い方法から請求書による支払いに変更できますか?</span><span class="sxs-lookup"><span data-stu-id="59109-320">Can I change from my current payment method to paying by invoice?</span></span>

<span data-ttu-id="59109-321">サブスクリプションの費用が特定の金額を超えている場合にのみ、請求書による支払いに変更できます。</span><span class="sxs-lookup"><span data-stu-id="59109-321">You can only change to paying by invoice if your subscription costs above a certain amount.</span></span> <span data-ttu-id="59109-322">請求書による支払いに変更する前に、まずクレジット カード、デビット カード、または銀行口座の未払い分を支払う必要があります。</span><span class="sxs-lookup"><span data-stu-id="59109-322">You must first pay any outstanding balance on the credit or debit card or bank account before you can change to paying by invoice.</span></span> <span data-ttu-id="59109-323">支払い方法を変更する方法については、「[1 つのサブスクリプションの支払い方法を変更する](manage-payment-methods.md#change-a-payment-method-for-a-single-subscription)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59109-323">To learn how to change payment methods, see [Change a payment method for a single subscription](manage-payment-methods.md#change-a-payment-method-for-a-single-subscription).</span></span>

## <a name="can-i-change-from-paying-by-invoice-to-using-a-different-payment-method"></a><span data-ttu-id="59109-324">請求書による支払いから別の支払い方法の使用に変更できますか?</span><span class="sxs-lookup"><span data-stu-id="59109-324">Can I change from paying by invoice to using a different payment method?</span></span>

<span data-ttu-id="59109-325">請求書による支払いから別の支払い方法による支払いに自動的に変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="59109-325">You can’t automatically change from paying by invoice to paying with a different payment method.</span></span> <span data-ttu-id="59109-326">代わりに、クレジット カード、デビット カード、または銀行口座引き落としで支払われた[別のサブスクリプションを購入](../try-or-buy-microsoft-365.md#buy-a-different-subscription)し、[すべてのユーザーを新しいサブスクリプションに移動](../subscriptions/move-users-different-subscription.md)してから、[以前のサブスクリプションをキャンセル](../subscriptions/cancel-your-subscription.md)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59109-326">Instead, you must [buy a different subscription](../try-or-buy-microsoft-365.md#buy-a-different-subscription) paid for with a credit or debit card or bank account, [move all users to the new subscription](../subscriptions/move-users-different-subscription.md), and then [cancel the old subscription](../subscriptions/cancel-your-subscription.md).</span></span>

## <a name="related-content"></a><span data-ttu-id="59109-327">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="59109-327">Related content</span></span>

<span data-ttu-id="59109-328">[支払方法を管理する](manage-payment-methods.md) (article)</span><span class="sxs-lookup"><span data-stu-id="59109-328">[Manage payment methods](manage-payment-methods.md) (article)</span></span>\
<span data-ttu-id="59109-329">[課金内容または請求書を表示する](view-your-bill-or-invoice.md) (article)</span><span class="sxs-lookup"><span data-stu-id="59109-329">[View your bill or invoice](view-your-bill-or-invoice.md) (article)</span></span>\
<span data-ttu-id="59109-330">[課金内容または請求書の内容を理解する](understand-your-invoice2.md) (article)\</span><span class="sxs-lookup"><span data-stu-id="59109-330">[Understand your bill or invoice](understand-your-invoice2.md) (article)</span></span>
