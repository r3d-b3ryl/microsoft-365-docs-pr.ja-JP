---
title: Microsoft 365 へのメールの送信
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f9d4b5b6-8f4c-44df-9b06-2f9b3058ca20
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 外部送信者として、Microsoft 365 のユーザーに電子メールを配信する機能を増やす方法について説明します。 また、フィッシング詐欺の試みを外部ユーザー&迷惑メールを報告する方法も学習します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4869b0f02415b3802b34625789817068cbe14c57
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205631"
---
# <a name="sending-mail-to-microsoft-365"></a><span data-ttu-id="63b36-104">Microsoft 365 へのメールの送信</span><span class="sxs-lookup"><span data-stu-id="63b36-104">Sending mail to Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="63b36-105">これらの記事は、外部の送信者が評判を向上し、Microsoft 365 のユーザーに電子メールを配信する能力を高めるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="63b36-105">These articles help external senders improve their reputation and increase their ability to deliver email to users in Microsoft 365.</span></span> <span data-ttu-id="63b36-106">また、Microsoft 365 ユーザーでない場合でも、迷惑メールやフィッシングの試みを報告する方法に関する情報も提供します。</span><span class="sxs-lookup"><span data-stu-id="63b36-106">They also provide some information about how you can report junk email and phishing attempts even if you aren't a Microsoft 365 user yourself.</span></span>

<span data-ttu-id="63b36-107">顧客ではなく、誰かにメールを送信しようとしている場合は、適切な場所にいます。</span><span class="sxs-lookup"><span data-stu-id="63b36-107">If you are not a customer, but are trying to send mail to someone in who is, you are in the right place.</span></span> <span data-ttu-id="63b36-108">管理者であり、スパムと戦うヘルプが必要な場合、これは適切なセクションではありません。</span><span class="sxs-lookup"><span data-stu-id="63b36-108">If you are an administrator and you need help fighting spam, this is not the right section for you.</span></span> <span data-ttu-id="63b36-109">代わりに、Microsoft 365 の [スパム対策とマルウェア対策 [の保護] に移動します](anti-spam-and-anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="63b36-109">Instead, go to [Anti-spam and anti-malware protection in Microsoft 365](anti-spam-and-anti-malware-protection.md).</span></span>

****

|<span data-ttu-id="63b36-110">以下についての関連情報...</span><span class="sxs-lookup"><span data-stu-id="63b36-110">For information about...</span></span>|<span data-ttu-id="63b36-111">「...」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63b36-111">See...</span></span>|
|---|---|
|<span data-ttu-id="63b36-112">お客様に個別の一括メールを送信する電子メール システムの管理者に提供するサービス。</span><span class="sxs-lookup"><span data-stu-id="63b36-112">Services we provide to administrators of email systems that are sending individual and bulk email to customers.</span></span>|[<span data-ttu-id="63b36-113">Office 365 にメールを送信するユーザー以外に対するサービス</span><span class="sxs-lookup"><span data-stu-id="63b36-113">Services for non-customers sending mail to Office 365</span></span>](services-for-non-customers.md)|
|<span data-ttu-id="63b36-114">電子メールを介して Microsoft 365 のお客様に届く問題を修正する方法。</span><span class="sxs-lookup"><span data-stu-id="63b36-114">How to fix problems reaching customers in Microsoft 365 through email.</span></span> <span data-ttu-id="63b36-115">Microsoft 365 受信者にバルク メールを送信するためのベスト プラクティス。</span><span class="sxs-lookup"><span data-stu-id="63b36-115">Best practices for sending bulk mail to Microsoft 365 recipients.</span></span>|[<span data-ttu-id="63b36-116">Office 365 に送信されるメールのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="63b36-116">Troubleshooting mail sent to Office 365</span></span>](troubleshooting-mail-sent-to-office-365.md)|
|<span data-ttu-id="63b36-117">Microsoft 365 が、フィッシングメールやスプーフィングメールなどの迷惑メールが顧客に送信されるのを防ぐ方法。</span><span class="sxs-lookup"><span data-stu-id="63b36-117">How Microsoft 365 prevents junk email, including phishing and spoofing email, from being sent to our customers.</span></span>|[<span data-ttu-id="63b36-118">Microsoft 365 のスパム対策保護</span><span class="sxs-lookup"><span data-stu-id="63b36-118">Anti-spam protection in Microsoft 365</span></span>](anti-spam-protection.md)|
|<span data-ttu-id="63b36-119">Microsoft 365 のお客様に電子メールを送信する管理者が、スパム対策ポリシーに従って電子メールをブロックしないようにする方法。</span><span class="sxs-lookup"><span data-stu-id="63b36-119">How you, an administrator sending email to Microsoft 365 customers, can avoid having email blocked by adhering to our anti-spam policies.</span></span> <span data-ttu-id="63b36-120">これは、理解しておく必要のある法的事項です。</span><span class="sxs-lookup"><span data-stu-id="63b36-120">This is the legal stuff you need to know.</span></span>|[<span data-ttu-id="63b36-121">リファレンス:ポリシー、プラクティス、ガイドライン</span><span class="sxs-lookup"><span data-stu-id="63b36-121">Reference: Policies, practices, and guidelines</span></span>](reference-policies-practices-and-guidelines.md)|
|
