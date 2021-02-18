---
title: Microsoft 365 にメールを送信するユーザー以外のサービス
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
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: 電子メールをユーザーが安心して使用できるようにするため、Microsoft は各種ポリシーやテクノロジを用いて、ユーザーを保護しています。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 879d2c9d3bc2af0f78a25eb1381a74b67171e939
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "50290765"
---
# <a name="services-for-non-customers-sending-mail-to-microsoft-365"></a><span data-ttu-id="44a12-103">Microsoft 365 にメールを送信するユーザー以外のサービス</span><span class="sxs-lookup"><span data-stu-id="44a12-103">Services for non-customers sending mail to Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="44a12-104">電子メールの不正使用、迷惑メール、詐欺メール (フィッシング詐欺) は、引き続き電子メール エコシステム全体にとって負担となっています。</span><span class="sxs-lookup"><span data-stu-id="44a12-104">Email abuse, junk email, and fraudulent emails (phishing) continue to burden the entire email ecosystem.</span></span> <span data-ttu-id="44a12-105">電子メールの使用に対するユーザーの信頼を維持するために、Microsoft では、ユーザーを保護するためにさまざまなポリシーとテクノロジを導入しています。</span><span class="sxs-lookup"><span data-stu-id="44a12-105">To help maintain user trust in the use of email, Microsoft has put various policies and technologies in place to help protect our users.</span></span> <span data-ttu-id="44a12-106">ただし、正当な電子メールが不利を被らないようにするべきであることも理解しています。</span><span class="sxs-lookup"><span data-stu-id="44a12-106">However, Microsoft understands that legitimate email should not be negatively affected.</span></span> <span data-ttu-id="44a12-107">そのため、送信者が送信評価を積極的に管理して Microsoft 365 ユーザーに電子メールを配信する能力を向上させる一組のサービスを確立しました。</span><span class="sxs-lookup"><span data-stu-id="44a12-107">Therefore, we have established a suite of services to help senders improve their ability to deliver email to Microsoft 365 users by proactively managing their sending reputation.</span></span>

<span data-ttu-id="44a12-108">この概要では、お客様でない場合でも、組織に提供するメリットに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="44a12-108">This overview provides information about benefits we provide to your organization even if you aren't a customer.</span></span>

## <a name="sender-solutions"></a><span data-ttu-id="44a12-109">送信者のソリューション</span><span class="sxs-lookup"><span data-stu-id="44a12-109">Sender solutions</span></span>

****

|<span data-ttu-id="44a12-110">サービス</span><span class="sxs-lookup"><span data-stu-id="44a12-110">Service</span></span>|<span data-ttu-id="44a12-111">利点</span><span class="sxs-lookup"><span data-stu-id="44a12-111">Benefits</span></span>|
|---|---|
|<span data-ttu-id="44a12-112">このオンライン ヘルプ コンテンツ</span><span class="sxs-lookup"><span data-stu-id="44a12-112">This online help content</span></span>|<span data-ttu-id="44a12-113">提供内容：</span><span class="sxs-lookup"><span data-stu-id="44a12-113">Provides:</span></span> <ul><li><span data-ttu-id="44a12-114">EOP ユーザーへの通信の配信に関連する質問の開始点。</span><span class="sxs-lookup"><span data-stu-id="44a12-114">A starting point for any questions related to delivering communications to EOP users.</span></span></li><li><span data-ttu-id="44a12-115">ポリシーと要件を含む簡単なオンライン ガイドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="44a12-115">Includes a simple online guide with our policies and requirements.</span></span></li><li><span data-ttu-id="44a12-116">Microsoft が採用している迷惑メール フィルターと認証テクノロジの概要。</span><span class="sxs-lookup"><span data-stu-id="44a12-116">An overview of the junk email filters and authentication technologies employed by Microsoft.</span></span></li><ul>|
|[<span data-ttu-id="44a12-117">Microsoft サポート</span><span class="sxs-lookup"><span data-stu-id="44a12-117">Microsoft support</span></span>](#microsoft-support)|<span data-ttu-id="44a12-118">配信の問題に対するセルフヘルプと充実したサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="44a12-118">Provides self-help and escalation support for delivery issues.</span></span>|
|[<span data-ttu-id="44a12-119">スパム対策 IP リストから削除ポータル</span><span class="sxs-lookup"><span data-stu-id="44a12-119">Anti-Spam IP Delist Portal</span></span>](#anti-spam-ip-delist-portal)|<span data-ttu-id="44a12-p102">IP リストからの除外要求を送信するためのツール。この要求を送信する前に、送信者は、疑わしい IP から不正なメールや悪意のあるメールが送信されないことを確認する責任があります。</span><span class="sxs-lookup"><span data-stu-id="44a12-p102">A tool to submit IP delist request. Before submitting this request it is the sender's responsibility to ensure that any further mail originating from the IP in question is not abusive or malicious.</span></span>|
|[<span data-ttu-id="44a12-122">Exchange Online からの迷惑メールの不正使用とスパムの報告</span><span class="sxs-lookup"><span data-stu-id="44a12-122">Abuse and spam reporting for junk email originating from Exchange Online</span></span>](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|<span data-ttu-id="44a12-123">スパムや他の不要なメールが Exchange Online から送信され、インターネットとメール システムが乱雑になじむのを防きます。</span><span class="sxs-lookup"><span data-stu-id="44a12-123">Keeps spam and other unwanted mail from being sent from Exchange Online and cluttering up the internet and your mail system.</span></span>|
|

## <a name="microsoft-support"></a><span data-ttu-id="44a12-124">Microsoft サポート</span><span class="sxs-lookup"><span data-stu-id="44a12-124">Microsoft support</span></span>

<span data-ttu-id="44a12-125">Microsoft では、Microsoft 365 受信者にメールを送信する場合に問題が発生した場合に、いくつかのサポート オプションを提供しています。</span><span class="sxs-lookup"><span data-stu-id="44a12-125">Microsoft offers several support options for people having trouble sending mail to Microsoft 365 recipients.</span></span> <span data-ttu-id="44a12-126">次のことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="44a12-126">We recommend that you:</span></span>

- <span data-ttu-id="44a12-127">受信するあらゆる配信不能レポートの指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="44a12-127">Follow the instructions in any non-delivery report you receive.</span></span>

- <span data-ttu-id="44a12-128">「[Office 365 に送信されるメールのトラブルシューティング](troubleshooting-mail-sent-to-office-365.md)」で、ユーザー以外が経験する一般的な問題について確認します。</span><span class="sxs-lookup"><span data-stu-id="44a12-128">Check out the most common problems that non-customers encounter in [Troubleshooting mail sent to Office 365](troubleshooting-mail-sent-to-office-365.md).</span></span>

- <span data-ttu-id="44a12-129">Microsoft [365](https://sender.office.com) のリストから削除されたポータルを使用して、受信拒否リストから IP を削除する要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="44a12-129">Use the [Microsoft 365 delist portal](https://sender.office.com) to submit a request to have your IP removed from the blocked sender's list.</span></span>

- <span data-ttu-id="44a12-130">[Microsoft コミュニティ フォーラム](https://community.office365.com/f/)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="44a12-130">Read the [Microsoft community forums](https://community.office365.com/f/).</span></span>

- <span data-ttu-id="44a12-131">別の方法でメールを送信しようとしている顧客に連絡し、Microsoft サポートに問い合わせ、代わりにサポート チケットを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="44a12-131">Contact the customer you're trying to email using another method and ask them to contact Microsoft Support and open a support ticket on your behalf.</span></span> <span data-ttu-id="44a12-132">場合によっては、Microsoft サポートは法的な理由から、ブロックされている IP 領域を所有している送信者と直接やり取りする必要が生じます。</span><span class="sxs-lookup"><span data-stu-id="44a12-132">In some cases, for legal reasons, Microsoft Support must communicate directly with the sender who owns the IP space that is being blocked.</span></span> <span data-ttu-id="44a12-133">ただし通常は、ユーザー以外はサポート チケットをオープンできません。</span><span class="sxs-lookup"><span data-stu-id="44a12-133">However, non-customers typically can't open support tickets.</span></span>

  <span data-ttu-id="44a12-134">Office 365 の Microsoft 製品サポートについて詳しくは、「 [サポート](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/support)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="44a12-134">For more information about Microsoft Technical support for Office 365, see [Support](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/support).</span></span>

## <a name="anti-spam-ip-delist-portal"></a><span data-ttu-id="44a12-135">スパム対策 IP リストから削除ポータル</span><span class="sxs-lookup"><span data-stu-id="44a12-135">Anti-Spam IP Delist Portal</span></span>

<span data-ttu-id="44a12-136">これは、Microsoft 365 の受信拒否リストから自分自身を削除するために使用できるセルフサービス ポータルです。</span><span class="sxs-lookup"><span data-stu-id="44a12-136">This is a self-service portal you can use to remove yourself from the Microsoft 365 blocked senders list.</span></span> <span data-ttu-id="44a12-137">このポータルは、メール アドレスが Microsoft 365 にある受信者に電子メールを送信しようとするときにエラー メッセージが表示される場合に、このポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="44a12-137">Use this portal if you are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365 and you don't think you should be.</span></span> <span data-ttu-id="44a12-138">詳細については、「[リストから除外ポータルを使って、受信拒否リストから自分自身を削除する](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44a12-138">For more information, see [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a><span data-ttu-id="44a12-139">Exchange Online からの迷惑メールの不正使用とスパムの報告</span><span class="sxs-lookup"><span data-stu-id="44a12-139">Abuse and spam reporting for junk email originating from Exchange Online</span></span>

<span data-ttu-id="44a12-140">Microsoft の使用条件とポリシーに違反して、サード パーティが迷惑メールを送信するために Microsoft365 を使用することがあります。</span><span class="sxs-lookup"><span data-stu-id="44a12-140">Sometimes Microsoft365 is used by third parties to send junk email, in violation of our terms of use and policy.</span></span> <span data-ttu-id="44a12-141">Office 365 から迷惑メールを受信した場合は、これらのメッセージを Microsoft に報告できます。</span><span class="sxs-lookup"><span data-stu-id="44a12-141">If you receive any junk email from Office 365, you can report these messages to Microsoft.</span></span> <span data-ttu-id="44a12-142">手順については、「メッセージとファイル [を Microsoft に報告する」を参照してください](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="44a12-142">For instructions, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>
