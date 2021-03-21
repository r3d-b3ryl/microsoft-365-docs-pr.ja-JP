---
title: リファレンスポリシー、プラクティス、ガイドライン
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ff3f140b-b005-445f-bfe0-7bc3f328aaf0
ms.collection:
- M365-security-compliance
description: Microsoft は、さまざまなポリシー、手順を開発し、ユーザーを悪用、望ましくない、または悪意のあるメールから保護するために、いくつかの業界のベスト プラクティスを採用しています。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8ed78e4a0f233e8d04fbcfb7d7fa7b3859bc0e17
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925234"
---
# <a name="reference-policies-practices-and-guidelines"></a><span data-ttu-id="f8351-103">リファレンス: ポリシー、プラクティス、ガイドライン</span><span class="sxs-lookup"><span data-stu-id="f8351-103">Reference: Policies, practices, and guidelines</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f8351-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="f8351-104">**Applies to**</span></span>
- [<span data-ttu-id="f8351-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f8351-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f8351-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="f8351-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="f8351-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8351-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="f8351-108">Microsoft は、Web 上におけるユーザー エクスペリエンスの信頼性を高めるための支援に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="f8351-108">Microsoft is dedicated to helping provide the most trusted user experience on the web.</span></span> <span data-ttu-id="f8351-109">そのため、さまざまなポリシー、手順を作成し、業界のいくつものベスト プラクティスを採用して、ユーザーが不適切で望ましくない、または悪意のあるメールから保護されるよう取り組んできました。</span><span class="sxs-lookup"><span data-stu-id="f8351-109">Therefore, Microsoft has developed various policies, procedures, and adopted several industry best practices to help protect our users from abusive, unwanted, or malicious email.</span></span> <span data-ttu-id="f8351-110">ユーザーに電子メールを送信しようとする送信者は、この記事のガイダンスを十分に理解し、この取り組みを支援し、潜在的な配信の問題を回避するために従っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8351-110">Senders attempting to send email to users should ensure they fully understand and are following the guidance in this article to help in this effort and to help avoid potential delivery issues.</span></span>

<span data-ttu-id="f8351-111">これらのポリシーとガイドラインに準拠していない場合、Microsoft サポート チームの支援を受けられないことがあります。</span><span class="sxs-lookup"><span data-stu-id="f8351-111">If you are not in compliance with these policies and guidelines, it may not be possible for our support team to assist you.</span></span> <span data-ttu-id="f8351-112">この資料に記されているガイドライン、プラクティス、ポリシーを遵守しているものの、送信 IP アドレスに関して配信の問題が解決されない場合、以下の手順に従って除外要求を送信してください。</span><span class="sxs-lookup"><span data-stu-id="f8351-112">If you are adhering to the guidelines, practices, and policies presented in this article and are still experiencing delivery issues based on your sending IP address, please follow the steps to submit a delisting request.</span></span> <span data-ttu-id="f8351-113">手順については、「削除ポータルを [使用して、ブロックされた](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)送信者リストから自分を削除する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8351-113">For instructions, see [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="general-microsoft-policies"></a><span data-ttu-id="f8351-114">一般的な Microsoft ポリシー</span><span class="sxs-lookup"><span data-stu-id="f8351-114">General Microsoft policies</span></span>

<span data-ttu-id="f8351-115">Microsoft 365 ユーザーに送信される電子メールは、電子メールの送信と Microsoft 365 の使用を管理する Microsoft のすべてのポリシーに準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8351-115">Email sent to Microsoft 365 users must comply with all Microsoft policies governing email transmission and use of Microsoft 365.</span></span>

- <span data-ttu-id="f8351-116">Microsoft 365 に適用されるサービスの条件。特に、スパムやマルウェアの配布にサービスを使用する禁止。</span><span class="sxs-lookup"><span data-stu-id="f8351-116">Terms of Services applicable to Microsoft 365; in particular, the prohibition against using the service to spam or distribute malware.</span></span>

- [<span data-ttu-id="f8351-117">Microsoft サービス規約</span><span class="sxs-lookup"><span data-stu-id="f8351-117">Microsoft Services Agreement</span></span>](https://www.microsoft.com/servicesagreement/)

## <a name="governmental-regulations"></a><span data-ttu-id="f8351-118">政府の規制</span><span class="sxs-lookup"><span data-stu-id="f8351-118">Governmental regulations</span></span>

<span data-ttu-id="f8351-119">Microsoft 365 ユーザーに送信される電子メールは、該当する管轄区域の電子メール通信を管理する適用される法律および規制に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8351-119">Email sent to Microsoft 365 users must adhere to all applicable laws and regulations governing email communications in the applicable jurisdiction.</span></span>

- [<span data-ttu-id="f8351-120">CAN-SPAM 法:ビジネスのためのコンプライアンス ガイド</span><span class="sxs-lookup"><span data-stu-id="f8351-120">CAN-SPAM Act: A Compliance Guide for Business</span></span>](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)

- [<span data-ttu-id="f8351-121">「削除してください」。応答と責任: 電子メールのマーケティング担当者は「登録解除」要求を受け入れる必要がある</span><span class="sxs-lookup"><span data-stu-id="f8351-121">"Remove Me" Responses and Responsibilities: Email Marketers Must Honor "Unsubscribe" Claims</span></span>](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.html)

## <a name="technical-guidelines"></a><span data-ttu-id="f8351-122">テクニカル ガイドライン</span><span class="sxs-lookup"><span data-stu-id="f8351-122">Technical guidelines</span></span>

<span data-ttu-id="f8351-123">Microsoft 365 に送信される電子メールは、以下のドキュメントに記載されている該当する推奨事項に準拠している必要があります (一部のリンクは英語でのみ利用可能です)。</span><span class="sxs-lookup"><span data-stu-id="f8351-123">Email sent to Microsoft 365 should comply with the applicable recommendations listed in the documents below (some links are only available in English).</span></span>

- [<span data-ttu-id="f8351-124">RFC 2505:SMTP MTA のスパム対策の推奨事項</span><span class="sxs-lookup"><span data-stu-id="f8351-124">RFC 2505: Anti-Spam Recommendations for SMTP MTAs</span></span>](https://www.ietf.org/rfc/rfc2505.txt)

- [<span data-ttu-id="f8351-125">RFC 2920:コマンド パイプラインの SMTP サービス拡張機能</span><span class="sxs-lookup"><span data-stu-id="f8351-125">RFC 2920: SMTP Service Extension for Command Pipelining</span></span>](https://www.ietf.org/rfc/rfc2920.txt)

<span data-ttu-id="f8351-126">さらに、Microsoft 365 に接続する電子メール サーバーは、次の要件に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8351-126">In addition, email servers connecting to Microsoft 365 must adhere to the following requirements:</span></span>

- <span data-ttu-id="f8351-127">送信者は、インターネット協会のインターネット技術標準化委員会 (IETF) が発行しているインターネット電子メールの送信に関する技術的な標準 (RFC 5321、RFC 5322 など) すべてに準拠していなければなりません。</span><span class="sxs-lookup"><span data-stu-id="f8351-127">Sender is expected to comply with all technical standards for the transmission of Internet email, as published by The Internet Society's Internet Engineering Task Force (IETF), including RFC 5321, RFC 5322, and others.</span></span>

- <span data-ttu-id="f8351-128">500 から 599 までの数字の SMTP エラー メッセージ コード (別名、永続的な配信不能レポート (NDR)) を受け取る場合、送信者はそのメッセージを対象の受信者に再送信してはなりません。</span><span class="sxs-lookup"><span data-stu-id="f8351-128">After given a numeric SMTP error response code between 500 and 599 (also known as a permanent non-delivery response or NDR), the sender must not attempt to retransmit that message to that recipient.</span></span>

- <span data-ttu-id="f8351-129">何度か配信不能応答が出されたなら、送信者は対象の受信者に対して電子メールの送信を中止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8351-129">After multiple non-delivery responses, the sender must cease further attempts to send email to that recipient.</span></span>

- <span data-ttu-id="f8351-130">安全でない電子メール中継サーバーまたはプロキシ サーバー経由でメッセージを転送しないでください。</span><span class="sxs-lookup"><span data-stu-id="f8351-130">Messages must not be transmitted through insecure email relay or proxy servers.</span></span>

- <span data-ttu-id="f8351-131">登録解除する方法は、個別のリストからであれ、送信者がホストするすべてのリストからであれ、受信者が簡単に見つけて実行できるように明記されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8351-131">The mechanism for unsubscribing, either from individual lists or all lists hosted by the sender, must be clearly documented and easy for recipients to find and use.</span></span>

- <span data-ttu-id="f8351-132">動的 IP 領域からの接続は受け付けられません。</span><span class="sxs-lookup"><span data-stu-id="f8351-132">Connections from dynamic IP space may not be accepted.</span></span>

- <span data-ttu-id="f8351-133">電子メール サーバーでは逆引き DNS レコードを有効にしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8351-133">Email servers must have valid reverse DNS records.</span></span>

## <a name="reputation-management"></a><span data-ttu-id="f8351-134">評判の管理</span><span class="sxs-lookup"><span data-stu-id="f8351-134">Reputation management</span></span>

<span data-ttu-id="f8351-135">送信者、ISP、およびその他のサービス プロバイダーは、積極的に、外部 IP アドレスの評価を管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8351-135">Senders, ISP's, and other service providers should actively manage the reputation of your outbound IP addresses.</span></span>

## <a name="microsoft-365-limits"></a><span data-ttu-id="f8351-136">Microsoft 365 の制限</span><span class="sxs-lookup"><span data-stu-id="f8351-136">Microsoft 365 limits</span></span>

<span data-ttu-id="f8351-137">送信者は、Exchange Online Protection Limits に記載されている Microsoft 365 [の制限に従う必要があります](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)。</span><span class="sxs-lookup"><span data-stu-id="f8351-137">Senders must adhere to Microsoft 365 limits listed in [Exchange Online Protection Limits](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits).</span></span>

## <a name="email-delivery-resources-and-organizations"></a><span data-ttu-id="f8351-138">電子メール配信リソースと組織</span><span class="sxs-lookup"><span data-stu-id="f8351-138">Email delivery resources and organizations</span></span>

<span data-ttu-id="f8351-p103">Microsoft は、インターネットと電子メールのエコシステムを改善するために業界団体およびサービス プロバイダーと積極的に連携しています。これらの組織は、Microsoft がサポートし、送信者が準ずるよう推奨されているベスト プラクティスに関する資料を公開しています。これによって、世界の複数の電子メール サービス プロバイダー間で電子メールを配信することがより容易になります。</span><span class="sxs-lookup"><span data-stu-id="f8351-p103">Microsoft actively works with industry bodies and service providers in order to improve the internet and email ecosystem. These organizations have published best practice documents that we support and recommend senders adhere to. This improves your ability to deliver email among several email service providers around the world.</span></span>

- [<span data-ttu-id="f8351-142">Messaging Malware Mobile Anti-Abuse Working Group</span><span class="sxs-lookup"><span data-stu-id="f8351-142">Messaging Malware Mobile Anti-Abuse Working Group</span></span>](https://www.m3aawg.org/)

- [<span data-ttu-id="f8351-143">オンライン信頼アライアンス</span><span class="sxs-lookup"><span data-stu-id="f8351-143">Online Trust Alliance</span></span>](https://www.internetsociety.org/ota/)

- [<span data-ttu-id="f8351-144">電子メール送信者&プロバイダーの連合</span><span class="sxs-lookup"><span data-stu-id="f8351-144">Email Sender & Provider Coalition</span></span>](https://www.espcoalition.org/)

## <a name="abuse-and-spam-reporting"></a><span data-ttu-id="f8351-145">迷惑行為とスパムの報告</span><span class="sxs-lookup"><span data-stu-id="f8351-145">Abuse and spam reporting</span></span>

<span data-ttu-id="f8351-146">違法、虐待、望ましくない、または悪意のあるメールを報告するには、「メッセージとファイルを Microsoft に報告する」 [を参照してください](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="f8351-146">To report unlawful, abusive, unwanted or malicious email, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span> <span data-ttu-id="f8351-147">これらの種類の通信を送信すると、Microsoft ポリシーに違反し、確認済みレポートに対して適切なアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="f8351-147">Sending these types of communications is a violation of Microsoft policy, and appropriate action will be taken on confirmed reports.</span></span>

## <a name="law-enforcement"></a><span data-ttu-id="f8351-148">法的処置</span><span class="sxs-lookup"><span data-stu-id="f8351-148">Law enforcement</span></span>

<span data-ttu-id="f8351-149">司法当局の一員で Office 365 に関する法的文書に関して Microsoft Corporation を支援してくださる方、または Microsoft に提出した法的文書に関して質問がある方は、(1) (425) 722-1299 までお電話ください。</span><span class="sxs-lookup"><span data-stu-id="f8351-149">If you are a member of law enforcement and wish to serve Microsoft Corporation with legal documentation regarding Office 365, or if you have questions regarding legal documentation you have submitted to Microsoft, please call (1) (425) 722-1299.</span></span>