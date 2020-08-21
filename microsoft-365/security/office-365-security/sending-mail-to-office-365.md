---
title: Microsoft 365 へのメール送信
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f9d4b5b6-8f4c-44df-9b06-2f9b3058ca20
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 外部の送信者として、Microsoft 365 のユーザーにメールを配信する機能を強化する方法について説明します。 フィッシングデータを外部&する迷惑メールを報告する方法についても説明します。
ms.openlocfilehash: f20d5d64bccb69db47c159a8166fa3532b51e3db
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825187"
---
# <a name="sending-mail-to-microsoft-365"></a><span data-ttu-id="9b5f6-104">Microsoft 365 へのメール送信</span><span class="sxs-lookup"><span data-stu-id="9b5f6-104">Sending mail to Microsoft 365</span></span>

<span data-ttu-id="9b5f6-105">これらの記事は、外部の送信者が自分の評価や Microsoft 365 のユーザーにメールを送信する能性を高めるために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9b5f6-105">These articles help external senders improve their reputation and increase their ability to deliver email to users in Microsoft 365.</span></span> <span data-ttu-id="9b5f6-106">また、Microsoft 365 ユーザーでない場合であっても、迷惑メールとフィッシング行う報告方法に関する情報も提供します。</span><span class="sxs-lookup"><span data-stu-id="9b5f6-106">They also provide some information about how you can report junk email and phishing attempts even if you aren't a Microsoft 365 user yourself.</span></span>

<span data-ttu-id="9b5f6-107">顧客でないが、その顧客に対してはメールを送信しようとしている場合、この情報は当ては取り中です。</span><span class="sxs-lookup"><span data-stu-id="9b5f6-107">If you are not a customer, but are trying to send mail to someone in who is, you are in the right place.</span></span> <span data-ttu-id="9b5f6-108">管理者でスパムへの対立サポートが必要な場合は、このセクションの情報は当てはまりません。</span><span class="sxs-lookup"><span data-stu-id="9b5f6-108">If you are an administrator and you need help fighting spam, this is not the right section for you.</span></span> <span data-ttu-id="9b5f6-109">代わりに [、Microsoft 365 のスパム対策とマルウェア対策の保護に移動してください](anti-spam-and-anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="9b5f6-109">Instead, go to [Anti-spam and anti-malware protection in Microsoft 365](anti-spam-and-anti-malware-protection.md).</span></span>

****

|<span data-ttu-id="9b5f6-110">以下についての関連情報...</span><span class="sxs-lookup"><span data-stu-id="9b5f6-110">For information about...</span></span>|<span data-ttu-id="9b5f6-111">関連...</span><span class="sxs-lookup"><span data-stu-id="9b5f6-111">See...</span></span>|
|---|---|
|<span data-ttu-id="9b5f6-112">個別のメールやバルク メールをお客様に送信する電子メール システムの管理者に提供するサービス。</span><span class="sxs-lookup"><span data-stu-id="9b5f6-112">Services we provide to administrators of email systems that are sending individual and bulk email to customers.</span></span>|[<span data-ttu-id="9b5f6-113">Office 365 にメールを送信するユーザー以外に対するサービス</span><span class="sxs-lookup"><span data-stu-id="9b5f6-113">Services for non-customers sending mail to Office 365</span></span>](services-for-non-customers.md)|
|<span data-ttu-id="9b5f6-114">Microsoft 365 の顧客へのメールの侵害に関する問題の解決方法。</span><span class="sxs-lookup"><span data-stu-id="9b5f6-114">How to fix problems reaching customers in Microsoft 365 through email.</span></span> <span data-ttu-id="9b5f6-115">Microsoft 365 の受信者にバルク メールを送信するためのベスト プラクティス。</span><span class="sxs-lookup"><span data-stu-id="9b5f6-115">Best practices for sending bulk mail to Microsoft 365 recipients.</span></span>|[<span data-ttu-id="9b5f6-116">Office 365 に送信されるメールのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="9b5f6-116">Troubleshooting mail sent to Office 365</span></span>](troubleshooting-mail-sent-to-office-365.md)|
|<span data-ttu-id="9b5f6-117">Microsoft 365 で、フィッシングやスプーフィング メールなどの迷惑メールがユーザーに送信されないようにする方法。</span><span class="sxs-lookup"><span data-stu-id="9b5f6-117">How Microsoft 365 prevents junk email, including phishing and spoofing email, from being sent to our customers.</span></span>|[<span data-ttu-id="9b5f6-118">Microsoft 365 のスパム対策保護</span><span class="sxs-lookup"><span data-stu-id="9b5f6-118">Anti-spam protection in Microsoft 365</span></span>](anti-spam-protection.md)|
|<span data-ttu-id="9b5f6-119">Microsoft 365 ユーザーにメールを送信する管理者が、スパム対策ポリシーに導入してメールがブロックされるのを回避する方法。</span><span class="sxs-lookup"><span data-stu-id="9b5f6-119">How you, an administrator sending email to Microsoft 365 customers, can avoid having email blocked by adhering to our anti-spam policies.</span></span> <span data-ttu-id="9b5f6-120">これは、理解しておく必要のある法的事項です。</span><span class="sxs-lookup"><span data-stu-id="9b5f6-120">This is the legal stuff you need to know.</span></span>|[<span data-ttu-id="9b5f6-121">リファレンス:ポリシー、プラクティス、ガイドライン</span><span class="sxs-lookup"><span data-stu-id="9b5f6-121">Reference: Policies, practices, and guidelines</span></span>](reference-policies-practices-and-guidelines.md)|
|
