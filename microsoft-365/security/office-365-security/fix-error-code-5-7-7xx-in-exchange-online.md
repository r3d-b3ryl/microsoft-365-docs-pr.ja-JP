---
title: Exchange Online でエラーコード 5.7.7 xx のメール配信の問題を修正する
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Exchange Online でエラーコード 5.7.7 xx の電子メールの問題を解決する方法について説明します (テナントがメールの送信をブロックされた場合)。
ms.openlocfilehash: ff0e26447a7bcdeccfcc1983af63abea905849e4
ms.sourcegitcommit: 3063e351e21614c236167e9cde40994d8b532bd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989532"
---
# <a name="fix-email-delivery-issues-for-error-code-577xx-in-exchange-online"></a><span data-ttu-id="a6497-103">Exchange Online でエラーコード 5.7.7 xx のメール配信の問題を修正する</span><span class="sxs-lookup"><span data-stu-id="a6497-103">Fix email delivery issues for error code 5.7.7xx in Exchange Online</span></span>

<span data-ttu-id="a6497-104">このトピックでは、配信不能レポート (NDR、バウンスメッセージ、配信状態通知、または DSN とも呼ばれる) に状態コード 550 5.7.7 xx が表示される場合に実行できる操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="a6497-104">This topic describes what you can do if you see status code 550 5.7.7xx in a non-delivery report (also known as an NDR, bounce message, delivery status notification, or DSN).</span></span> <span data-ttu-id="a6497-105">この自動通知は、テナントが1つまたは別の方法で電子メールの送信を制限されている場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6497-105">You'll see this automated notification when your tenant is restricted from sending email in one way or another.</span></span> <span data-ttu-id="a6497-106">これらのエラーコードは通常、705または750として表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6497-106">These error codes will usually come in as 705 or 750.</span></span>

## <a name="57705-tenant-has-exceeded-threshold-restriction-what-you-need-to-know"></a><span data-ttu-id="a6497-107">5.7.705: テナントがしきい値制限を超過しました: 知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="a6497-107">5.7.705: Tenant has exceeded threshold restriction: What you need to know</span></span>

<span data-ttu-id="a6497-108">ユーザーが特定の量の疑わしい電子メールをサービス経由で送信すると、その問題が解決されるまで、すべてのユーザーが電子メールを送信できなくなります。</span><span class="sxs-lookup"><span data-stu-id="a6497-108">Once your users (collectively, as organization) send a certain amount of suspicious email through the service, all users can be prevented from sending any email until the problem is fixed.</span></span> <span data-ttu-id="a6497-109">これは通常、侵害 (最も一般的) または大量のメールを送信した結果です。</span><span class="sxs-lookup"><span data-stu-id="a6497-109">This is usually the result of a compromise (most common) or sending too much bulk mail.</span></span> <span data-ttu-id="a6497-110">ユーザーは、次のような状態の NDR を受信します。</span><span class="sxs-lookup"><span data-stu-id="a6497-110">Users will receive an NDR that states:</span></span>

`550 5.7.705 Access denied, tenant has exceeded threshold`

<span data-ttu-id="a6497-111">まれに、既に期限が切れた後にサブスクリプションを更新した場合にも発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a6497-111">In rare cases, this could also happen if you renew your subscription after it has already expired.</span></span> <span data-ttu-id="a6497-112">サービスが新しいサブスクリプション情報 (通常は1日以内) を同期するのには時間がかかりますが、組織がメールを送信できないようにブロックされることがあります。</span><span class="sxs-lookup"><span data-stu-id="a6497-112">It takes time for the service to sync the new subscription information (typically, no more than one day), but your organization could be blocked from sending email in the meantime.</span></span> <span data-ttu-id="a6497-113">これを回避する最善の方法は、サブスクリプションの有効期限が切れないようにすることです。</span><span class="sxs-lookup"><span data-stu-id="a6497-113">The best way to prevent this is to make sure your subscription does not expire.</span></span>

## <a name="57750-unregistered-domain-email-restriction-what-you-need-to-know"></a><span data-ttu-id="a6497-114">5.7.750: 登録が解除されるドメインの電子メール制限: 理解しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="a6497-114">5.7.750: Unregistered Domain Email restriction: What you need to know</span></span>

<span data-ttu-id="a6497-115">Office 365 では、テナントが Exchange Online Protection (EOP) を介して一部のメッセージを中継することが許可されています。</span><span class="sxs-lookup"><span data-stu-id="a6497-115">Office 365 allows tenants to relay some messages through Exchange Online Protection (EOP).</span></span> <span data-ttu-id="a6497-116">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a6497-116">For example:</span></span>

- <span data-ttu-id="a6497-117">Office 365 メールボックスは、外部の送信者から電子メールを受信します。</span><span class="sxs-lookup"><span data-stu-id="a6497-117">An Office 365 mailbox receives email from an external sender.</span></span> <span data-ttu-id="a6497-118">メール転送は Office 365 メールボックスで構成されているため、メッセージはユーザーの外部の電子メールアドレスに戻されます。</span><span class="sxs-lookup"><span data-stu-id="a6497-118">Mail forwarding is configured on the Office 365 mailbox, so the message goes back out to the user's external email address.</span></span> <span data-ttu-id="a6497-119">このシナリオは、学生が自分の個人用メールアカウントを使用して学校関連のメッセージを表示する教育環境で最もよく見られます。</span><span class="sxs-lookup"><span data-stu-id="a6497-119">This scenario is most common in education environments where students want to use their personal email accounts to view school-related messages.</span></span>

- <span data-ttu-id="a6497-120">EOP を経由して送信メールを送信するオンプレミスの電子メールサーバーを持つハイブリッド envrionments。</span><span class="sxs-lookup"><span data-stu-id="a6497-120">Hybrid envrionments that have on-premises email servers that send outgoing mail through EOP.</span></span>

### <a name="problems-with-unregistered-domains"></a><span data-ttu-id="a6497-121">未登録のドメインに関する問題</span><span class="sxs-lookup"><span data-stu-id="a6497-121">Problems with unregistered domains</span></span>

<span data-ttu-id="a6497-122">問題は、社内のメールサーバーが危険にさらされた場合に、EOP を介して大量のスパムを中継することです。</span><span class="sxs-lookup"><span data-stu-id="a6497-122">The problem is when compromised on-premises email servers relay a large volume of spam through EOP.</span></span> <span data-ttu-id="a6497-123">ほとんどの場合、コネクタは正しく設定されていますが、未登録の (プロビジョニングされていない) ドメインからメールが送信されています。</span><span class="sxs-lookup"><span data-stu-id="a6497-123">In almost all cases, the connectors are set up correctly, but email is being sent from unregistered (also known as unprovisioned) domains.</span></span> <span data-ttu-id="a6497-124">Office 365 では、登録されていないドメインからの十分な量の電子メールを使用できますが、電子メールを承認済みドメインとして送信するために使用するすべてのドメインを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6497-124">Office 365 allows a reasonable amount of email from unregistered domains, but you should configure every domain that you use to send email as an accepted domain.</span></span>

<span data-ttu-id="a6497-125">いったん侵害されると、テナントは未登録ドメインの送信電子メールを送信できなくなります。</span><span class="sxs-lookup"><span data-stu-id="a6497-125">Once compromised, tenants will be prevented from sending outbound email for unregistered domains.</span></span> <span data-ttu-id="a6497-126">ユーザーは、次のような状態の NDR を受信します。</span><span class="sxs-lookup"><span data-stu-id="a6497-126">Users will receive an NDR that states:</span></span>

`550 5.7.750 Service unavailable. Client blocked from sending from unregistered domains`

## <a name="how-to-unblocking-tenant-in-order-to-send-again"></a><span data-ttu-id="a6497-127">再送信のためにテナントのブロックを解除する方法</span><span class="sxs-lookup"><span data-stu-id="a6497-127">How to unblocking tenant in order to send again</span></span>

<span data-ttu-id="a6497-128">テナントが電子メールの送信をブロックされている場合は、いくつかの作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6497-128">There are several things you need to do if your tenant is blocked from sending email:</span></span>

1. <span data-ttu-id="a6497-129">すべての電子メールドメインが登録されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6497-129">Verify that all of your email domains are registered.</span></span> <span data-ttu-id="a6497-130">詳細については、「 [Office 365 へのドメインの追加](https://docs.microsoft.com/office365/admin/setup/add-domain)」および「 [Exchange Online で承認済みドメインを管理](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6497-130">For more information, see [Add a domain to Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain) and [Manage accepted domains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

2. <span data-ttu-id="a6497-131">Office 365 組織内のすべての管理者に対して[MFA を有効に](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)します。</span><span class="sxs-lookup"><span data-stu-id="a6497-131">[Enable MFA](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) for all admins in your Office 365 organization.</span></span>

3. <span data-ttu-id="a6497-132">すべての電子メールドメインが登録されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6497-132">Verify that all of your email domains are registered.</span></span> <span data-ttu-id="a6497-133">詳細については、「 [Office 365 へのドメインの追加](https://docs.microsoft.com/en-us/office365/admin/setup/add-domain)」および「 [Exchange Online で承認済みドメインを管理](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6497-133">For more information, see [Add a domain to Office 365](https://docs.microsoft.com/en-us/office365/admin/setup/add-domain) and [Manage accepted domains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

4. <span data-ttu-id="a6497-134">異常な[コネクタ](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)を探します。</span><span class="sxs-lookup"><span data-stu-id="a6497-134">Look for unusual [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> <span data-ttu-id="a6497-135">悪意のある俳優は、スパムを送信するために Office 365 組織に新しい受信コネクタを作成することがよくあります。</span><span class="sxs-lookup"><span data-stu-id="a6497-135">Malicious actors will often create new inbound connectors in your Office 365 organization to send spam.</span></span> <span data-ttu-id="a6497-136">既存のコネクタを表示するには、「 [Office 365 でコネクタを検証](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6497-136">To view your existing connectors, see [Validate connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors).</span></span>

5. <span data-ttu-id="a6497-137">「 [Office 365 で侵害された電子メールアカウントに応答する](responding-to-a-compromised-email-account.md)」の説明に従って、侵害されたユーザーをチェックします。</span><span class="sxs-lookup"><span data-stu-id="a6497-137">Check for compromised users as described in [Responding to a compromised email account in Office 365](responding-to-a-compromised-email-account.md).</span></span>

6. <span data-ttu-id="a6497-138">オンプレミスの電子メールサーバーをロックし、侵害されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6497-138">Lock down your on-premises email servers and verify that they are not compromised.</span></span>

   > [!TIP]
   > <span data-ttu-id="a6497-139">特にサードパーティ製サーバーを使用している場合は、多くの要因があります。</span><span class="sxs-lookup"><span data-stu-id="a6497-139">There are many factors here, especially if you're using third-party servers.</span></span> <span data-ttu-id="a6497-140">いずれにしても、すべての送信メールが正当であることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6497-140">Regardless, you'll need to verify that all of your outgoing email is now legitimate.</span></span>

7. <span data-ttu-id="a6497-141">Microsoft サポートに連絡して、再度電子メールを送信するようにテナントのブロック解除を取得するように依頼します。</span><span class="sxs-lookup"><span data-stu-id="a6497-141">Call Microsoft Support and ask to get your tenant unblocked to send email again.</span></span> <span data-ttu-id="a6497-142">エラーコードは役に立ちますが、環境がセキュリティで保護されており、スパムを送信することができないことを証明する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6497-142">The error code is helpful, but you'll need to prove that your environment has been secured and is incapable of sending spam.</span></span> <span data-ttu-id="a6497-143">サポート案件を開くには、「 [business products のサポートへのお問い合わせ-管理者向けヘルプ](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6497-143">To open a support case, see [Contact support for business products - Admin Help](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="a6497-144">関連情報</span><span class="sxs-lookup"><span data-stu-id="a6497-144">For more information</span></span>

[<span data-ttu-id="a6497-145">Office 365 メールのスパム対策保護</span><span class="sxs-lookup"><span data-stu-id="a6497-145">Office 365 email anti-spam protection</span></span>](anti-spam-protection.md)

[<span data-ttu-id="a6497-146">Exchange Online サービスの説明の「送信制限」セクションのバルクメールガイダンス</span><span class="sxs-lookup"><span data-stu-id="a6497-146">Bulk Mail guidance in the sending limits section of the Exchange Online service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits)

[<span data-ttu-id="a6497-147">Office 365 でのメール配信不能レポート</span><span class="sxs-lookup"><span data-stu-id="a6497-147">Email non-delivery reports in Office 365</span></span>](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)

[<span data-ttu-id="a6497-148">メールボックスへの電子メールの転送を構成する</span><span class="sxs-lookup"><span data-stu-id="a6497-148">Configure email forwarding for a mailbox</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[<span data-ttu-id="a6497-149">Office 365 を使用してメールを送信するように多機能デバイスまたはアプリケーションをセット アップする方法</span><span class="sxs-lookup"><span data-stu-id="a6497-149">How to set up a multifunction device or application to send email using Office 365</span></span>](https://docs.microsoft.com/Exchange/mail-flow-best-practices/how-to-set-up-a-multifunction-device-or-application-to-send-email-using-office-3)

<span data-ttu-id="a6497-150">[Exchange Online で承認済みドメインを管理](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)します。</span><span class="sxs-lookup"><span data-stu-id="a6497-150">[Manage accepted domains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>
