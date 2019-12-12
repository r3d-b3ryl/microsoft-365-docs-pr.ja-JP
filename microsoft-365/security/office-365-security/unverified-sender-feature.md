---
title: 未確認の送信者
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/11/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: フィッシングメッセージがメールボックスに到達しないようにするため、Outlook.com および web 上の Outlook では、送信者が本人であることを確認し、疑わしいメッセージを迷惑メールとしてマークします。
ms.openlocfilehash: 4c8b8a0711ab66607d0db5923c1115c436537bd0
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970933"
---
# <a name="unverified-sender"></a><span data-ttu-id="402cb-103">未確認の送信者</span><span class="sxs-lookup"><span data-stu-id="402cb-103">Unverified Sender</span></span>

> [!NOTE]
> <span data-ttu-id="402cb-104">これらの更新プログラムは現在ロールアウトされており、すべてのユーザーに対してまだ使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="402cb-104">These updates are rolling out now, and might not be available yet for all users.</span></span> <span data-ttu-id="402cb-105">この機能は、エンタープライズ outlook.com ユーザーに対してサポートされています。</span><span class="sxs-lookup"><span data-stu-id="402cb-105">This feature is supported for Enterprise outlook.com users.</span></span> <span data-ttu-id="402cb-106">現時点では、コンシューマー outlook.com では使用できません。</span><span class="sxs-lookup"><span data-stu-id="402cb-106">It is not currently available for consumer outlook.com.</span></span>

<span data-ttu-id="402cb-107">フィッシングメッセージがメールボックスに到達しないようにするため、Outlook.com および web 上の Outlook では、送信者が本人であることを確認し、疑わしいメッセージを迷惑メールとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="402cb-107">To prevent phishing messages from reaching your mailbox, Outlook.com and Outlook on the web verify that the sender is who they say they are and mark suspicious messages as junk email.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="402cb-108">メッセージがフィッシング詐欺としてマークされている場合、Outlook.com および web 上の Outlook では、ページの上部に警告が表示されますが、メッセージ内のすべてのリンクを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="402cb-108">When a message is marked as a phishing scam, Outlook.com and Outlook on the web display a warning at the top of the page, but any links in the message can still be opened.</span></span>

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a><span data-ttu-id="402cb-109">受信トレイ内の疑わしいメッセージを特定するには、どうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="402cb-109">How can I identify a suspicious message in my inbox?</span></span>

<span data-ttu-id="402cb-110">Web 上の Outlook.com および Outlook on the メッセージの送信者が識別できない場合、または送信者アドレスに表示されているものとは異なる場合のインジケーターを表示します。</span><span class="sxs-lookup"><span data-stu-id="402cb-110">Outlook.com and Outlook on the web show indicators when the sender of a message either can't be identified or their identity is different from what you see in the From address.</span></span>

## <a name="you-see-a--in-the-sender-image"></a><span data-ttu-id="402cb-111">送信者の画像に '? ' が表示される</span><span class="sxs-lookup"><span data-stu-id="402cb-111">You see a '?' in the sender image</span></span>

<span data-ttu-id="402cb-112">Outlook.com と web 上の Outlook が電子メール認証手法を使用して送信者の身元を確認できない場合は、送信者の写真に '? ' が表示されます。</span><span class="sxs-lookup"><span data-stu-id="402cb-112">When Outlook.com and Outlook on the web can't verify the identity of the sender using email authentication techniques, they display a '?' in the sender photo.</span></span>

![メッセージが検証に合格しませんでした](../media/message-did-not-pass-verification.jpg)

<span data-ttu-id="402cb-114">認証に失敗したすべてのメッセージが悪意のあるものであるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="402cb-114">Not every message that fails to authenticate is malicious.</span></span> <span data-ttu-id="402cb-115">ただし、送信者を認識しない場合は、認証されないメッセージの操作について注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="402cb-115">However, you should be careful about interacting with messages that don't authenticate if you don't recognize the sender.</span></span> <span data-ttu-id="402cb-116">または、通常は送信者の画像に '? ' が含まれていない送信者を認識したが、突然表示を開始した場合は、送信者がスプーフィングされているという署名になることがあります。</span><span class="sxs-lookup"><span data-stu-id="402cb-116">Or, if you recognize a sender that normally doesn't have a '?' in the sender image, but you suddenly start seeing it, that could be a sign the sender is being spoofed.</span></span>

## <a name="how-to-manage-which-messages-receive-the-unverified-sender-treatment"></a><span data-ttu-id="402cb-117">未確認の送信者の処理を受信するメッセージを管理する方法</span><span class="sxs-lookup"><span data-stu-id="402cb-117">How to manage which messages receive the unverified sender treatment</span></span> 

<span data-ttu-id="402cb-118">Office 365 をご利用のお客様の場合は、セキュリティ & コンプライアンスセンターを使用してこの機能を管理できます。</span><span class="sxs-lookup"><span data-stu-id="402cb-118">If you are an Office 365 customer you can manage this feature through the Security & Compliance Center.</span></span> 

- <span data-ttu-id="402cb-119">Office 365 セキュリティ & コンプライアンスセンターでは、フィッシングポリシーの下にあるスプーフィング対策保護を使用して、グローバルまたはセキュリティ管理者がこの機能を有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="402cb-119">In the Office 365 Security & Compliance Center, global or security administrators can turn the feature on or off, through anti-spoofing protection under the Anti-Phish policy.</span></span> <span data-ttu-id="402cb-120">また、' Get-antiphishpolicy ' コマンドレットを使用して管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="402cb-120">Additionally, it can be managed through the ‘Set-AntiPhishPolicy’ cmdlet.</span></span> <span data-ttu-id="402cb-121">詳細については、「 [Office 365 のフィッシング対策保護](anti-phishing-protection.md)」および「 [get-antiphishpolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="402cb-121">For more details, see [Anti-phishing protection in Office 365](anti-phishing-protection.md) and [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy).</span></span>

    ![グラフィックインターフェイスで認証されていない送信者を編集する。](../media/unverified-sender-article-editing-unauthenticated-senders.jpg)

- <span data-ttu-id="402cb-123">管理者が誤検知を識別し、送信者が未確認の送信者による処理を受信しないようにした場合は、次のいずれかの操作を行って、スプーフィングインテリジェンススプーフィング許可リストに送信者を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="402cb-123">If an admin has identified a false positive, and a sender should not be receiving the unverified sender treatment, one of the following actions can be taken to add the sender to the Spoof Intelligence spoof allow list:</span></span>

  - <span data-ttu-id="402cb-124">スプーフィングインテリジェンスの洞察を通じてドメインペアを追加します。</span><span class="sxs-lookup"><span data-stu-id="402cb-124">Add the domain pair through the Spoof Intelligence Insight.</span></span> <span data-ttu-id="402cb-125">詳細については、「[チュートリアル: スプーフィングインテリジェンスの洞察](walkthrough-spoof-intelligence-insight.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="402cb-125">For more details, see [Walkthrough: spoof intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

  - <span data-ttu-id="402cb-126">Get-phishfilterpolicy コマンドレットを使用して、ドメインペアを追加します。</span><span class="sxs-lookup"><span data-stu-id="402cb-126">Add the domain pair through the PhishFilterPolicy cmdlet.</span></span> <span data-ttu-id="402cb-127">詳細については、「 [get-phishfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy) 」および「 [set UP Office 365 ATP フィッシング対策」および「set up Office](set-up-anti-phishing-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="402cb-127">For more details, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy) and [Set up Office 365 ATP anti-phishing and anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

<span data-ttu-id="402cb-128">また、電子メールトランスポートルール (Etr)、安全なドメインリスト (スパム対策ポリシー)、安全な送信者リスト、またはユーザーがこのユーザーを自分のドメイン内の "安全な送信者" として設定している場合にも、未検証の送信者の処理は適用されません。ボックス.</span><span class="sxs-lookup"><span data-stu-id="402cb-128">Additionally, we do not apply the unverified sender treatment if it was delivered to the inbox via an admin allow list, including Email Transport Rules (ETRs), Safe Domain List (Anti-Spam Policy), Safe Sender List or a user has set this user as a “Safe Sender” in their inbox.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="402cb-129">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="402cb-129">Frequently asked questions</span></span>

### <a name="what-criteria-does-outlookcom-and-outlook-on-the-web-use-to-add-the--and-the-via-properties"></a><span data-ttu-id="402cb-130">Outlook.com と web 上の Outlook で、'? ' および ' via ' プロパティを追加するために使用する条件とは何ですか。</span><span class="sxs-lookup"><span data-stu-id="402cb-130">What criteria does Outlook.com and Outlook on the web use to add the '?' and the 'via' properties?</span></span>

<span data-ttu-id="402cb-131">送信者イメージの '? ' の場合: Outlook.com では、メッセージが SPF 認証または DKIM 認証のいずれかを通過し、dmarc パスを受け取るか、または Office 365 スプーフィングインテリジェンスからのコンポジット認証パスを受け取ることが要求されます。</span><span class="sxs-lookup"><span data-stu-id="402cb-131">For the '?' in the sender image:  Outlook.com requires that the message pass either SPF or DKIM authentication and receive either a dmarc pass, or a composite authentication pass from Office 365 Spoof Intelligence.</span></span> <span data-ttu-id="402cb-132">詳細については、「 [Set UP SPF In office 365](set-up-spf-in-office-365-to-help-prevent-spoofing.md) 」を参照して、スプーフィングを防止し、 [Dkim を使用して office 365 のカスタムドメインから送信される送信電子メールを検証](use-dkim-to-validate-outbound-email.md)します。</span><span class="sxs-lookup"><span data-stu-id="402cb-132">For more details, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) and [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="402cb-133">Via タグの場合: From アドレスのドメインが DKIM シグネチャまたは SMTP メールのドメインと異なる場合、Outlook.com は、この2つのフィールドのいずれかにドメインを表示します (DKIM シグネチャを優先します)。</span><span class="sxs-lookup"><span data-stu-id="402cb-133">For the via tag: If the domain in the From address is different from the domain in the DKIM signature or the SMTP MAIL FROM, Outlook.com displays the domain in one of those two fields (preferring the DKIM signature).</span></span>

### <a name="how-do-i-remove-the-"></a><span data-ttu-id="402cb-134">'? ' を削除する方法</span><span class="sxs-lookup"><span data-stu-id="402cb-134">How do I remove the '?'</span></span>

<span data-ttu-id="402cb-135">送信者の画像の '? ' の場合は、送信者として、SPF または DKIM のいずれかを使用してメッセージを認証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="402cb-135">For the '?' in the sender image: As a sender, you should authenticate your message with either SPF or DKIM.</span></span>

<span data-ttu-id="402cb-136">Via タグ: 送信者としての場合は、DKIM 署名のドメインまたは SMTP メールが、From アドレスのドメインと同じかサブドメインのものであることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="402cb-136">For the via tag: As a sender, you should ensure that either the domain in the DKIM signature or the SMTP MAIL FROM is the same as, or is a subdomain of, the domain in the From address.</span></span>

### <a name="does-outlookcom-and-outlook-on-the-web-show-this-for-every-message-that-doesnt-pass-authentication"></a><span data-ttu-id="402cb-137">Outlook.com と web 上の Outlook は、認証を通過しないすべてのメッセージに対してこのように表示されます。</span><span class="sxs-lookup"><span data-stu-id="402cb-137">Does Outlook.com and Outlook on the web show this for every message that doesn’t pass authentication?</span></span>

<span data-ttu-id="402cb-138">必ずしもそうではありません。</span><span class="sxs-lookup"><span data-stu-id="402cb-138">Not necessarily.</span></span> <span data-ttu-id="402cb-139">Outlook.com および web 上の Outlook は、メッセージ内に送信者を認証するためのその他のプロパティがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="402cb-139">Outlook.com and Outlook on the web may have other properties within the message to authenticate the sender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="402cb-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="402cb-140">Related topics</span></span>

[<span data-ttu-id="402cb-141">Outlook.com メールアカウントを保護する</span><span class="sxs-lookup"><span data-stu-id="402cb-141">Help protect your Outlook.com email account</span></span>](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[<span data-ttu-id="402cb-142">Outlook.com でのフィッシングまたはスプーフィングに対処する</span><span class="sxs-lookup"><span data-stu-id="402cb-142">Deal with phishing or spoofing in Outlook.com</span></span>](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[<span data-ttu-id="402cb-143">Outlook on the web で迷惑メールおよびスパムをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="402cb-143">Filter junk email and spam in Outlook on the web</span></span>](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)
