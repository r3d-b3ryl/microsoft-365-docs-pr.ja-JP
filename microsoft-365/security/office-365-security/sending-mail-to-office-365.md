---
title: Microsoft 365 へのメールの送信
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f9d4b5b6-8f4c-44df-9b06-2f9b3058ca20
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 外部の送信者として、Microsoft 365 でユーザーに電子メールを配信する機能を向上させる方法を説明します。 また、外部ユーザーとして迷惑メール & フィッシングの試行を報告する方法についても説明します。
ms.openlocfilehash: c464d09ddd5f6324c9b3e22e9cad6a613862c9a1
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209825"
---
# <a name="sending-mail-to-microsoft-365"></a><span data-ttu-id="1d754-104">Microsoft 365 へのメールの送信</span><span class="sxs-lookup"><span data-stu-id="1d754-104">Sending mail to Microsoft 365</span></span>

<span data-ttu-id="1d754-105">これらの記事は、外部の送信者が評価を改善し、Microsoft 365 でユーザーに電子メールを配信する能力を向上させるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1d754-105">These articles help external senders improve their reputation and increase their ability to deliver email to users in Microsoft 365.</span></span> <span data-ttu-id="1d754-106">また、Microsoft 365 ユーザーではない場合でも、迷惑メールとフィッシングの試行を報告する方法についての情報も提供します。</span><span class="sxs-lookup"><span data-stu-id="1d754-106">They also provide some information about how you can report junk email and phishing attempts even if you aren't a Microsoft 365 user yourself.</span></span>

<span data-ttu-id="1d754-107">お客様ではないが、であるユーザーにメールを送信しようとしている場合は、適切な場所にいます。</span><span class="sxs-lookup"><span data-stu-id="1d754-107">If you are not a customer, but are trying to send mail to someone in who is, you are in the right place.</span></span> <span data-ttu-id="1d754-108">管理者であり、スパムへの対処についてのサポートが必要な場合は、このセクションは適していません。</span><span class="sxs-lookup"><span data-stu-id="1d754-108">If you are an administrator and you need help fighting spam, this is not the right section for you.</span></span> <span data-ttu-id="1d754-109">代わりに、 [Microsoft 365 のスパム対策とマルウェア対策保護](anti-spam-and-anti-malware-protection.md)に移動します。</span><span class="sxs-lookup"><span data-stu-id="1d754-109">Instead, go to [Anti-spam and anti-malware protection in Microsoft 365](anti-spam-and-anti-malware-protection.md).</span></span>

|<span data-ttu-id="1d754-110">**以下についての関連情報...**</span><span class="sxs-lookup"><span data-stu-id="1d754-110">**For information about...**</span></span>|<span data-ttu-id="1d754-111">**参照...**</span><span class="sxs-lookup"><span data-stu-id="1d754-111">**See...**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1d754-112">お客様に電子メールを送信する電子メールシステムの管理者に提供されるサービス。</span><span class="sxs-lookup"><span data-stu-id="1d754-112">Services we provide to administrators of email systems that are sending individual and bulk email to customers.</span></span>|[<span data-ttu-id="1d754-113">Office 365 にメールを送信するユーザー以外に対するサービス</span><span class="sxs-lookup"><span data-stu-id="1d754-113">Services for non-customers sending mail to Office 365</span></span>](services-for-non-customers.md)|
|<span data-ttu-id="1d754-114">Microsoft 365 でのお客様への電子メールによる問題の解決方法。</span><span class="sxs-lookup"><span data-stu-id="1d754-114">How to fix problems reaching customers in Microsoft 365 through email.</span></span> <span data-ttu-id="1d754-115">Microsoft 365 の受信者にバルクメールを送信するためのベストプラクティス。</span><span class="sxs-lookup"><span data-stu-id="1d754-115">Best practices for sending bulk mail to Microsoft 365 recipients.</span></span>|[<span data-ttu-id="1d754-116">Office 365 に送信されるメールのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="1d754-116">Troubleshooting mail sent to Office 365</span></span>](troubleshooting-mail-sent-to-office-365.md)|
|<span data-ttu-id="1d754-117">Microsoft 365 は、フィッシングやスプーフィング電子メールを含む迷惑メールをお客様に送信することを禁止しています。</span><span class="sxs-lookup"><span data-stu-id="1d754-117">How Microsoft 365 prevents junk email, including phishing and spoofing email, from being sent to our customers.</span></span>|[<span data-ttu-id="1d754-118">Microsoft 365 でのスパム対策保護</span><span class="sxs-lookup"><span data-stu-id="1d754-118">Anti-spam protection in Microsoft 365</span></span>](anti-spam-protection.md)|
|<span data-ttu-id="1d754-119">Microsoft 365 のお客様に電子メールを送信する管理者は、スパム対策ポリシーに準拠してメールがブロックされないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="1d754-119">How you, an administrator sending email to Microsoft 365 customers, can avoid having email blocked by adhering to our anti-spam policies.</span></span> <span data-ttu-id="1d754-120">これは、理解しておく必要のある法的事項です。</span><span class="sxs-lookup"><span data-stu-id="1d754-120">This is the legal stuff you need to know.</span></span>|[<span data-ttu-id="1d754-121">リファレンス:ポリシー、プラクティス、ガイドライン</span><span class="sxs-lookup"><span data-stu-id="1d754-121">Reference: Policies, practices, and guidelines</span></span>](reference-policies-practices-and-guidelines.md)|
