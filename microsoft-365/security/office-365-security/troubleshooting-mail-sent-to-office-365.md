---
title: Microsoft 365 に送信されるメールのトラブルシューティング
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: この記事では、Microsoft 365 & の受信トレイにメールを送信する際の Microsoft 365 ユーザーへのバルク メールのベスト プラクティスに関する問題のトラブルシューティング情報を提供します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1e4a91f70b59debc770a5811638bd64a1eef36dd
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286383"
---
# <a name="troubleshooting-mail-sent-to-microsoft-365"></a><span data-ttu-id="8eb93-103">Microsoft 365 に送信されるメールのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="8eb93-103">Troubleshooting mail sent to Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8eb93-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="8eb93-104">**Applies to**</span></span>
- [<span data-ttu-id="8eb93-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8eb93-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="8eb93-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="8eb93-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)

<span data-ttu-id="8eb93-107">この記事では、Microsoft 365 の受信トレイにメールを送信しようとするときに問題が発生している送信者のトラブルシューティング情報と、顧客へのバルク メールのベスト プラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8eb93-107">This article provides troubleshooting information for senders who are experiencing issues when trying to send email to inboxes in Microsoft 365 and best practices for bulk mailing to customers.</span></span>

## <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a><span data-ttu-id="8eb93-108">IP およびドメインの評価の管理者ですか</span><span class="sxs-lookup"><span data-stu-id="8eb93-108">Are you managing your IP and domain's sending reputation?</span></span>

<span data-ttu-id="8eb93-109">EOP フィルタリング テクノロジは、Microsoft 365 や他の Microsoft 製品 (Exchange Server など) に対してスパム対策保護を提供するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="8eb93-109">EOP filtering technologies are designed to provide anti-spam protection for Microsoft 365 as well as other Microsoft products like Exchange Server.</span></span> <span data-ttu-id="8eb93-110">また、SPF、DKIM、および DMARC も活用しています。スプーフィングとフィッシングの問題に対処するために役立つ電子メール認証テクノロジ。電子メールを送信するドメインが許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8eb93-110">We also leverage SPF, DKIM, and DMARC; email authentication technologies that help address the problem of spoofing and phishing by verifying that the domain sending the email is authorized to do so.</span></span> <span data-ttu-id="8eb93-111">EOP フィルター処理は、送信 IP、ドメイン、認証、リストの精度、苦情率、コンテンツに関連する多くの要因によって影響されます。</span><span class="sxs-lookup"><span data-stu-id="8eb93-111">EOP filtering is influenced by a number of factors related to the sending IP, domain, authentication, list accuracy, complaint rates, content and more.</span></span> <span data-ttu-id="8eb93-112">このうち、送信者の評判を下げ、メールを配信する能力を向上する主な要因の 1 つは、迷惑メールの苦情率です。</span><span class="sxs-lookup"><span data-stu-id="8eb93-112">Of these, one of the principal factors in driving down a sender's reputation and their ability to deliver email is their junk email complaint rate.</span></span>

## <a name="are-you-sending-email-from-new-ip-addresses"></a><span data-ttu-id="8eb93-113">新しい IP アドレスから電子メールを送信していますか</span><span class="sxs-lookup"><span data-stu-id="8eb93-113">Are you sending email from new IP addresses?</span></span>

<span data-ttu-id="8eb93-p102">通常、電子メールを送信するために初めて使用する IP アドレスには、当社のシステムで構築された評価はありません。その結果、新しい IP アドレスからの電子メールでは、配信の問題が発生する可能性が高くなります。迷惑メールを送信しないための評価が IP で構築されると、通常 EOP の電子メール配信エクスペリエンスは向上します。</span><span class="sxs-lookup"><span data-stu-id="8eb93-p102">IP addresses not previously used to send email typically don't have any reputation built up in our systems. As a result, emails from new IPs are more likely to experience delivery issues. Once the IP has built a reputation for not sending spam, EOP will typically allow for a better email delivery experience.</span></span>

<span data-ttu-id="8eb93-p103">既存の SPF レコードで認証されているドメインに追加される新しい IP アドレスの場合、通常、そのドメインの送信評価の一部を継承できるという利点があります。ご使用のドメインの送信評価が優れていると、新しい IP の評価もすぐに向上します。新しい IP は、ボリューム、配布リストの正確さ、迷惑メールの苦情の割合に応じて、数週間またはすぐにでも、評価が向上することを期待できます。</span><span class="sxs-lookup"><span data-stu-id="8eb93-p103">New IPs that are added for domains that are authenticated under existing SPF records typically experience the added benefit of inheriting some of the domain's sending reputation. If your domain has a good sending reputation new IPs may experience a faster ramp up time. A new IP can expect to be fully ramped within a couple of weeks or sooner depending on volume, list accuracy, and junk email complaint rates.</span></span>

## <a name="confirm-that-your-dns-is-set-up-correctly"></a><span data-ttu-id="8eb93-120">DNS が正しく設定されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="8eb93-120">Confirm that your DNS is set up correctly</span></span>

<span data-ttu-id="8eb93-121">メールのルーティングに必要な MX レコードなど、DNS レコードの作成と保守の手順については、DNS ホスティング プロバイダーに確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8eb93-121">For instructions about how to create and maintain DNS records, including the MX record required for mail routing, you will need to contact your DNS hosting provider.</span></span>

## <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a><span data-ttu-id="8eb93-122">ルーティング不能な IP で自分をアドバタイズしていないことを確認する</span><span class="sxs-lookup"><span data-stu-id="8eb93-122">Ensure that you do not advertise yourself as a non-routable IP</span></span>

<span data-ttu-id="8eb93-p104">DNS 逆引き参照を行えない送信者からの電子メールは受け付けないことがあります。場合によっては、正当な送信者が、EOP に対して接続しようとするときに、インターネット ルーティング不能な IP で自身をアドバタイズすることがあります。プライベート (ルーティング不能な) ネットワーク用に予約されている IP アドレスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8eb93-p104">We may not accept email from senders who fail a reverse-DNS lookup. In some cases, legitimate senders advertise themselves incorrectly as a non-internet routable IP when attempting to open a connection to EOP. IP addresses that are reserved for private (non-routable) networking include:</span></span>

- <span data-ttu-id="8eb93-126">192.168.0.0/16 (または 192.168.0.0 ～ 192.168.255.255)</span><span class="sxs-lookup"><span data-stu-id="8eb93-126">192.168.0.0/16 (or 192.168.0.0 - 192.168.255.255)</span></span>
- <span data-ttu-id="8eb93-127">10.0.0.0/8 (または 10.0.0.0 ～ 10.255.255.255)</span><span class="sxs-lookup"><span data-stu-id="8eb93-127">10.0.0.0/8 (or 10.0.0.0 - 10.255.255.255)</span></span>
- <span data-ttu-id="8eb93-128">172.16.0.0/11 (または 172.16.0.0 ～ 172.31.255.255)</span><span class="sxs-lookup"><span data-stu-id="8eb93-128">172.16.0.0/11 (or 172.16.0.0 - 172.31.255.255)</span></span>

## <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a><span data-ttu-id="8eb93-129">Office 365 でユーザーに電子メールを送信すると、配信不能レポート (NDR) を受信する</span><span class="sxs-lookup"><span data-stu-id="8eb93-129">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>

<span data-ttu-id="8eb93-p105">一部の配信の問題の原因は、Microsoft によって送信者の IP アドレスがブロックされていることや、ユーザーのアカウントが以前の迷惑メール処理によって禁止された送信者として識別されていることにあります。エラーがあって NDR を受信したと分かっている場合には、まず、NDR メッセージに記載されている指示に従って問題を解決してください。</span><span class="sxs-lookup"><span data-stu-id="8eb93-p105">Some delivery issues are the result of the sender's IP address being blocked by Microsoft or because the user account is identified as banned sender due to previous spam activity. If you believe that you have received the NDR in error, first follow any instructions in the NDR message to resolve the issue.</span></span>

<span data-ttu-id="8eb93-132">受信したエラーの詳細については、Exchange Online のメール配信不可レポートのエラー コードの一覧 [を参照してください](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)。</span><span class="sxs-lookup"><span data-stu-id="8eb93-132">For more information about the error you received, see the list of error codes in [Email non-delivery reports in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

 <span data-ttu-id="8eb93-133">たとえば、次の NDR を受け取った場合、送信 IP アドレスが Microsoft によってブロックされたと示されます。</span><span class="sxs-lookup"><span data-stu-id="8eb93-133">For example, if you receive the following NDR, it indicates that the sending IP address was blocked by Microsoft:</span></span>

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

<span data-ttu-id="8eb93-134">このリストからの削除を要求するには、リストから削除するポータルを使用して、受信拒否リストから自分自身 [を削除できます](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)。</span><span class="sxs-lookup"><span data-stu-id="8eb93-134">To request removal from this list, you can [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="my-email-landed-in-the-recipients-junk-email-folder"></a><span data-ttu-id="8eb93-135">受信者の [迷惑メール] フォルダーにメールが届く</span><span class="sxs-lookup"><span data-stu-id="8eb93-135">My email landed in the recipient's Junk Email folder</span></span>

<span data-ttu-id="8eb93-136">メッセージが EOP によってスパムとして誤って識別された場合は、受信者と一緒にこの誤検知メッセージを Microsoft スパム分析チームに送信し、メッセージを評価および分析できます。</span><span class="sxs-lookup"><span data-stu-id="8eb93-136">If a message was incorrectly identified as spam by EOP, you can work with the recipient to submit this false positive message to the Microsoft Spam Analysis Team, who will evaluate and analyze the message.</span></span> <span data-ttu-id="8eb93-137">詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8eb93-137">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a><span data-ttu-id="8eb93-138">自分の IP アドレスからのトラフィックが EOP によって調整される</span><span class="sxs-lookup"><span data-stu-id="8eb93-138">Traffic from my IP address is throttled by EOP</span></span>

<span data-ttu-id="8eb93-139">IP アドレスが EOP によって調整されたことを示す NDR を EOP から受信することがあります。例:</span><span class="sxs-lookup"><span data-stu-id="8eb93-139">If you receive an NDR from EOP that indicates that your IP address is being throttled by EOP, for example:</span></span>

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

<span data-ttu-id="8eb93-p107">不審な動作が対象の IP アドレスで検出され、さらに詳しく評価される間、一時的に制限されているために NDR を受信しました。評価によって疑いが晴れると、この制限はすぐ解除されます。</span><span class="sxs-lookup"><span data-stu-id="8eb93-p107">You received the NDR because suspicious activity has been detected from the IP address and it has been temporarily restricted while it is being further evaluated. If the suspicion is cleared through evaluation, this restriction will be lifted shortly.</span></span>

## <a name="i-cant-receive-email-from-senders-in-microsoft-365"></a><span data-ttu-id="8eb93-142">Microsoft 365 で送信者からメールを受信できない</span><span class="sxs-lookup"><span data-stu-id="8eb93-142">I can't receive email from senders in Microsoft 365</span></span>

 <span data-ttu-id="8eb93-143">Microsoft ユーザーからのメッセージを受信するには、ご使用のネットワークが Microsoft データセンター内で EOP が使用している IP アドレスからの接続を許可していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8eb93-143">In order to receive messages from our users, make sure your network allows connections from the IP addresses that EOP uses in our datacenters.</span></span> <span data-ttu-id="8eb93-144">詳細については [、「Exchange Online Protection IP アドレス」を参照してください](../../enterprise/urls-and-ip-address-ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="8eb93-144">For more information, see [Exchange Online Protection IP addresses](../../enterprise/urls-and-ip-address-ranges.md).</span></span>

## <a name="best-practices-for-bulk-emailing-to-microsoft-365-users"></a><span data-ttu-id="8eb93-145">Microsoft 365 ユーザーへのバルク メール送信のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="8eb93-145">Best practices for bulk emailing to Microsoft 365 users</span></span>

<span data-ttu-id="8eb93-146">Microsoft 365 ユーザーにバルク メール キャンペーンを頻繁に実施し、メールが安全かつ適切な時期に届く必要がある場合は、このセクションのヒントに従ってください。</span><span class="sxs-lookup"><span data-stu-id="8eb93-146">If you often conduct bulk email campaigns to Microsoft 365 users and want to ensure that your emails arrive in a safe and timely manner, follow the tips in this section.</span></span>

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a><span data-ttu-id="8eb93-147">From 名がメッセージを送信しているユーザーを反映するようにします。</span><span class="sxs-lookup"><span data-stu-id="8eb93-147">Ensure that the From name reflects who is sending the message</span></span>

<span data-ttu-id="8eb93-p109">[件名] はメッセージの内容に関する要約で、メッセージ本文には、オファリング、サービス、製品について明瞭かつ簡潔に記されている必要があります。 例：</span><span class="sxs-lookup"><span data-stu-id="8eb93-p109">The Subject should be a brief summary of what the message is about, and the message body should clearly and succinctly indicate what the offering, service, or product is about. For example:</span></span>

<span data-ttu-id="8eb93-150">正しい:</span><span class="sxs-lookup"><span data-stu-id="8eb93-150">Correct:</span></span>

> <span data-ttu-id="8eb93-151">From: marketing@shoppershandbag.com</span><span class="sxs-lookup"><span data-stu-id="8eb93-151">From: marketing@shoppershandbag.com</span></span> <br> <span data-ttu-id="8eb93-152">件名: クリスマスシーズンのカタログを更新しました。</span><span class="sxs-lookup"><span data-stu-id="8eb93-152">Subject: Updated catalog for the Christmas season!</span></span>

<span data-ttu-id="8eb93-153">正しくない:</span><span class="sxs-lookup"><span data-stu-id="8eb93-153">Incorrect:</span></span>

> <span data-ttu-id="8eb93-154">From: someone@outlook.com</span><span class="sxs-lookup"><span data-stu-id="8eb93-154">From: someone@outlook.com</span></span> <br> <span data-ttu-id="8eb93-155">件名: カタログ</span><span class="sxs-lookup"><span data-stu-id="8eb93-155">Subject: Catalogs</span></span>

<span data-ttu-id="8eb93-156">送信元について、また実行内容について分かりやすくすれば、ほとんどのスパム フィルターに引っかかることなく配信しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="8eb93-156">The easier you make it for people to know who you are and what you are doing, the less difficulty you will have delivering through most spam filters.</span></span>

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a><span data-ttu-id="8eb93-157">キャンペーン電子メールには必ず登録解除オプションを含める</span><span class="sxs-lookup"><span data-stu-id="8eb93-157">Always include an unsubscribe option in campaign emails</span></span>

<span data-ttu-id="8eb93-p110">マーケティング電子メール、特にニュースレターなどでは、その後の電子メールを登録解除する方法を必ず含める必要があります。例：</span><span class="sxs-lookup"><span data-stu-id="8eb93-p110">Marketing emails, especially newsletters, should always include a way of unsubscribing from future emails. For example:</span></span>

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe&trade; | Privacy Policy`

<span data-ttu-id="8eb93-p111">一部の送信者は、「登録解除」という件名で特定のエイリアスに電子メールを送信することを受信者に求めています。これよりも、上記の例の 1 回のクリックで完了する操作を推奨します。受信者に電子メールを送信することを要求する場合、ユーザーがリンクをクリックする際に、すべての必須フィールドにあらかじめデータが入っているようにしてください。</span><span class="sxs-lookup"><span data-stu-id="8eb93-p111">Some senders include this option by requiring recipients to send an email to a certain alias with "Unsubscribe" in the subject. This is not preferable to the one-click example above. If you do choose to require recipients to send a mail, ensure that when they click the link, all the required fields are pre-populated.</span></span>

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a><span data-ttu-id="8eb93-163">マーケティング電子メールまたはニュースレターの登録にダブル オプトイン オプションを使用する</span><span class="sxs-lookup"><span data-stu-id="8eb93-163">Use the double opt-in option for marketing email or newsletter registration</span></span>

<span data-ttu-id="8eb93-p112">業界におけるこのベスト プラクティスは、会社の製品またはサービスを利用するためにユーザーによる連絡先情報の登録が必須である、または推奨される場合に適しています。一部の会社では、登録プロセスの際にマーケティング電子メールまたはニュースレターにユーザーを自動的にサインアップするようになっていますが、これは電子メールのフィルタリングにおいては問題のあるマーケティング手法であると見なされています。</span><span class="sxs-lookup"><span data-stu-id="8eb93-p112">This industry best practice is recommended if your company requires or encourages users to register their contact information in order to access your product or services. Some companies make it a practice to automatically sign up their users for marketing emails or e-newsletters during the registration process, but this is considered a questionable marketing practice in the world of email filtering.</span></span>

<span data-ttu-id="8eb93-166">登録プロセスで、「はい、ニュースレターを送信してください」、「はい、特別なオファーを送信してください」などのチェックボックスが既定で選択されていると、不注意なユーザーが、受信の必要のないマーケティング電子メールやニュースレターに意図せずにサインアップする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8eb93-166">During the registration process, if the "Yes, please send me your newsletter" or "Yes, please send me special offers" checkbox is selected by default, users who do not pay close attention may unintentionally sign up for marketing email or newsletters that they do not want to receive.</span></span>

 <span data-ttu-id="8eb93-p113">代わりに、ダブル オプトイン オプションの使用をお勧めします。このオプションでは、マーケティング電子メールまたはニュースレターのチェックボックスは既定で選択されていない状態になっています。さらに、登録フォームが送信されると、確認の電子メールがユーザーに送信されます。そのメールには、マーケティング電子メールを受信する意思を確認するための URL が記載されています。</span><span class="sxs-lookup"><span data-stu-id="8eb93-p113">We recommend the double opt-in option instead, which means that the checkbox for marketing emails or newsletters is unchecked by default. Additionally, once the registration form has been submitted, a verification email is sent to the user with a URL that allows them to confirm their decision to receive marketing emails.</span></span>

 <span data-ttu-id="8eb93-169">これにより、マーケティング電子メールを本当に受信する意志があるユーザーだけが電子メールにサインアップするようになり、以降は、問題のあるマーケティング電子メール手法を送信元の会社から排除できます。</span><span class="sxs-lookup"><span data-stu-id="8eb93-169">This helps ensure that only those users who want to receive marketing email are signed up for the emails, subsequently clearing the sending company of any questionable email marketing practices.</span></span>

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a><span data-ttu-id="8eb93-170">電子メール メッセージの内容が透過的かつトレース可能であることを確認する</span><span class="sxs-lookup"><span data-stu-id="8eb93-170">Ensure that email message content is transparent and traceable</span></span>

<span data-ttu-id="8eb93-p114">電子メールの送信方法と同様、その内容も重要になります。電子メール コンテンツを作成するときは、次のベスト プラクティスを使用して、電子メールがフィルタリング サービスによってフラグ設定されないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8eb93-p114">Just as important as the way the emails are sent is the content they contain. When creating email content, use the following best practices to ensure that your emails will not be flagged by email filtering services:</span></span>

- <span data-ttu-id="8eb93-173">送信者をアドレス帳に追加するよう、電子メール・メッセージが受信者に要求する場合、そうした操作がメールの配信を保証するものではないことを明記する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8eb93-173">When the email message requests that recipients add the sender to the address book, it should clearly state that such action is not a guarantee of delivery.</span></span>

- <span data-ttu-id="8eb93-p115">メッセージ本文に含まれるリダイレクトは、類似性と一貫性があるべきで、多種多様であってはなりません。このコンテキストのリダイレクトとは、リンクやドキュメントなど、メッセージから離れた任意の対象のことです。広告や登録解除リンク、またはプロファイルの更新リンクがたくさんある場合には、すべてが同じドメインを指していなければなりません。例：</span><span class="sxs-lookup"><span data-stu-id="8eb93-p115">Redirects included in the body of the message should be similar and consistent, and not multiple and varied. A redirect in this context is anything that points away from the message, such as links and documents. If you have a lot of advertising or Unsubscribe links or Update the Profile links, they should all point to the same domain. For example:</span></span>

  <span data-ttu-id="8eb93-178">正しい (すべてのドメインが同じ):</span><span class="sxs-lookup"><span data-stu-id="8eb93-178">Correct (all domains are the same):</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  <span data-ttu-id="8eb93-179">正しくありません (すべてのドメインが異なります)。</span><span class="sxs-lookup"><span data-stu-id="8eb93-179">Incorrect (all domains are different):</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.excite.com`

  `options.yahoo.com`

- <span data-ttu-id="8eb93-180">サイズの大きな画像や添付ファイル、画像だけのメッセージは避けてください。</span><span class="sxs-lookup"><span data-stu-id="8eb93-180">Avoid content with large images and attachments, or messages that are solely composed of an image.</span></span>

- <span data-ttu-id="8eb93-181">パブリック プライバシーまたは P3P 設定では、トラッキング ピクセルが存在することを明記する必要があります (Web バグまたはビーコン)。</span><span class="sxs-lookup"><span data-stu-id="8eb93-181">Your public privacy or P3P settings should clearly state the presence of tracking pixels (web bugs or beacons).</span></span>

### <a name="remove-incorrect-email-aliases-from-your-databases"></a><span data-ttu-id="8eb93-182">データベースから不正な電子メール エイリアスを削除する</span><span class="sxs-lookup"><span data-stu-id="8eb93-182">Remove incorrect email aliases from your databases</span></span>

<span data-ttu-id="8eb93-p116">バウンス バックを作成するデータベース内のすべての電子メール エイリアスは不要であり、電子メールのフィルタリング サービスによってさらにセキュリティを確保するうえで送信メールを危険にさらすものです。電子メール データベースを最新の情報に保ってください。</span><span class="sxs-lookup"><span data-stu-id="8eb93-p116">Any email alias in your database that creates a bounce-back is unnecessary and puts your outbound emails at risk for further scrutiny by email filtering services. Ensure that your email database is up-to-date.</span></span>
